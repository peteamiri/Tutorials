### **Chapter 4: Salesforce Development with Apex and Lightning**  
**Title**: *Building Custom Logic and Modern User Interfaces*  

---

#### **4.1 Apex Fundamentals**  
**Objective**: Master Salesforce’s proprietary programming language for backend logic.  

**4.1.1 Apex Syntax and Structure**  
- **Class Structure**:  
  - **Triggers**: Event-driven code (e.g., `before insert`, `after update`).  
    ```apex
    trigger AccountTrigger on Account (before insert) {
      for (Account acc : Trigger.new) {
        acc.Description = 'Created by trigger';
      }
    }
    ```  
  - **Batch Classes**: Process large datasets asynchronously.  
    ```apex
    global class CleanupBatch implements Database.Batchable<sObject> {
      global Database.QueryLocator start(Database.BatchableContext bc) {
        return Database.getQueryLocator('SELECT Id FROM Account WHERE IsActive__c = false');
      }
      global void execute(Database.BatchableContext bc, List<Account> scope) {
        delete scope;
      }
      global void finish(Database.BatchableContext bc) { /* Notify admin */ }
    }
    ```  
- **Governor Limits**:  
  - **CPU Time**: 10,000 milliseconds per transaction.  
  - **SOQL Queries**: 100 synchronous, 200 asynchronous.  
  - **Best Practices**: Bulkify code, avoid nested loops, use `@future` for async operations.  

**4.1.2 Testing and Debugging**  
- **Test Classes**:  
  - **Minimum Coverage**: 75% for deployment.  
  - **Example**:  
    ```apex
    @isTest
    private class AccountTriggerTest {
      @isTest static void testDescriptionUpdate() {
        Account acc = new Account(Name = 'Test');
        insert acc;
        System.assertEquals('Created by trigger', [SELECT Description FROM Account WHERE Id = :acc.Id].Description);
      }
    }
    ```  
- **Debug Tools**:  
  - **Debug Logs**: Track execution in Setup → Debug → Logs.  
  - **Anonymous Apex**: Execute snippets in Developer Console.  

---

#### **4.2 Lightning Web Components (LWC)**  
**Objective**: Develop dynamic, responsive UIs using modern web standards.  

**4.2.1 Component Lifecycle and Decorators**  
- **Lifecycle Hooks**:  
  - `connectedCallback()`: Runs when component loads.  
  - `renderedCallback()`: Fires after DOM rendering.  
- **Decorators**:  
  - `@track`: Marks reactive properties (UI updates on change).  
  - `@api`: Exposes properties/methods to parent components.  
  - **Example**:  
    ```javascript
    import { LightningElement, track, api } from 'lwc';
    export default class HelloWorld extends LightningElement {
      @track greeting = 'World';
      @api updateGreeting(name) {
        this.greeting = name;
      }
    }
    ```  

**4.2.2 Data Binding and Apex Integration**  
- **Wire Service**: Fetch data reactively from Apex.  
  ```javascript
  import { LightningElement, wire } from 'lwc';
  import getContacts from '@salesforce/apex/ContactController.getContacts';
  export default class ContactList extends LightningElement {
    @wire(getContacts) contacts;
  }
  ```  
- **Imperative Apex Calls**:  
  ```javascript
  import getContacts from '@salesforce/apex/ContactController.getContacts';
  // Inside a method:
  getContacts({ accountId: this.recordId })
    .then(result => { /* Handle data */ })
    .catch(error => { /* Handle errors */ });
  ```  

**4.2.3 Lightning Data Service (LDS)**  
- **Benefits**: Caching, offline support, automatic CRUD checks.  
- **Usage**:  
  ```javascript
  import { getRecord } from 'lightning/uiRecordApi';
  export default class ViewAccount extends LightningElement {
    @api recordId;
    @wire(getRecord, { recordId: '$recordId', fields: ['Account.Name'] })
    account;
  }
  ```  

---

#### **4.3 Integration Patterns**  
**Objective**: Connect Salesforce with external systems and services.  

**4.3.1 REST/SOAP APIs**  
- **REST API**:  
  - **Outbound**: Call external APIs via `HttpRequest`.  
    ```apex
    HttpRequest req = new HttpRequest();
    req.setEndpoint('https://api.example.com/data');
    req.setMethod('GET');
    HttpResponse res = new Http().send(req);
    ```  
  - **Inbound**: Expose Apex classes as REST endpoints.  
    ```apex
    @RestResource(urlMapping='/cases/*')
    global class CaseAPI {
      @HttpGet
      global static List<Case> getOpenCases() {
        return [SELECT Id, Subject FROM Case WHERE IsClosed = false];
      }
    }
    ```  
- **SOAP API**: Generate WSDLs for legacy system integration.  

**4.3.2 Platform Events and Streaming API**  
- **Platform Events**: Decoupled, event-driven architecture.  
  - **Publish**:  
    ```apex
    EventBus.publish(new Order_Update__e(OrderId__c = '001xx000003DGb0'));
    ```  
  - **Subscribe**:  
    ```javascript
    // LWC: Subscribe via Lightning Message Service.
    import { subscribe, MessageContext } from 'lightning/messageService';
    import ORDER_UPDATE_CHANNEL from '@salesforce/messageChannel/Order_Update__c';
    export default class Subscriber extends LightningElement {
      @wire(MessageContext) messageContext;
      subscription;
      connectedCallback() {
        this.subscription = subscribe(
          this.messageContext,
          ORDER_UPDATE_CHANNEL,
          (message) => { /* Handle event */ }
        );
      }
    }
    ```  
- **Streaming API**: Real-time updates to UIs via CometD.  

**4.3.3 Salesforce Connect**  
- **External Objects**: Virtualize data from OData 2.0/4.0 endpoints.  
- **Example**: Integrate SAP ERP data without replication.  

---

### **Real-World Example**  
**Use Case**: A logistics company:  
1. Develops a **batch Apex** class to nightly sync inventory levels from an external warehouse system.  
2. Builds a **LWC dashboard** displaying real-time shipment status using Platform Events.  
3. Exposes order APIs for partners via REST endpoints.  

---

### **Key Takeaways**  
1. **Apex**: Prioritize bulkification and test coverage to avoid deployment failures.  
2. **LWC**: Leverage reactive data binding and LDS for performant UIs.  
3. **Integration**: Use Platform Events for scalable real-time communication.  

---

### **Review Questions**  
1. How do governor limits impact Apex trigger design?  
2. What is the difference between `@wire` and imperative Apex calls?  
3. When would you choose Salesforce Connect over REST API?  

---

### **Visual Aids (Suggested)**  
- **Diagram**: Apex transaction lifecycle with governor limits.  
- **Code Snippet**: Bulkified trigger handling 10,000 records.  
- **Flowchart**: LWC component communication via events.  

---

This chapter bridges declarative configuration with programmatic solutions, empowering developers to build scalable, secure, and interactive Salesforce applications.
