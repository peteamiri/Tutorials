### **Chapter 2: Salesforce Configuration and Customization**  
**Title**: *Building Scalable and Secure Business Solutions*  

---

#### **2.1 Data Model Design**  
**Objective**: Design a robust data architecture aligned with business processes.  

**2.1.1 Standard vs. Custom Objects**  
- **Standard Objects**: Pre-built tables (e.g., `Account`, `Contact`, `Opportunity`) for common CRM use cases.  
- **Custom Objects**: User-defined tables (e.g., `Project__c`, `Inventory__c`) tailored to unique needs.  
  - **Best Practice**: Use standard objects where possible to reduce maintenance overhead.  

**2.1.2 Field Types**  
- **Core Types**:  
  - **Text/Number**: Basic data storage.  
  - **Picklist**: Predefined dropdown values (e.g., Status: Open, Closed).  
  - **Formula**: Dynamically calculated values (e.g., `Total_Price__c = Quantity__c * Unit_Price__c`).  
  - **Lookup/Master-Detail**: Relationships between objects.  
    - **Lookup**: Non-cascading (e.g., linking a `Contact` to a `Department__c`).  
    - **Master-Detail**: Parent-child dependency (e.g., `Order__c` and `Order_Line_Item__c`).  
- **Advanced Types**:  
  - **External Lookups**: Integrate external data (via Salesforce Connect).  
  - **Encrypted Fields**: Store sensitive data securely (e.g., credit card numbers).  

**2.1.3 Schema Builder and ERDs**  
- **Schema Builder**: Drag-and-drop tool for visualizing/editing object relationships.  
- **Entity-Relationship Diagrams (ERDs)**: Blueprint for data architecture.  
  - **Example**: Mapping `Opportunity` → `Product__c` → `Invoice__c`.  

---

#### **2.2 Automation Tools**  
**Objective**: Streamline business processes with declarative automation.  

**2.2.1 Process Builder and Workflow Rules**  
- **Workflow Rules**: Legacy tool for field updates, email alerts, and outbound messages.  
  - **Limitations**: No support for screen interactions or complex logic.  
- **Process Builder**: Graphical workflow engine for multi-step automation.  
  - **Use Case**: Auto-create a `Task` when an `Opportunity` stage changes to "Closed Won."  

**2.2.2 Flow Builder**  
- **Flow Types**:  
  - **Screen Flows**: User-facing forms (e.g., onboarding wizards).  
  - **Auto-Launched Flows**: Triggered by processes, Apex, or schedules.  
  - **Scheduled Flows**: Recurring actions (e.g., nightly data cleanup).  
- **Best Practices**:  
  - Use **debug logs** to troubleshoot flow errors.  
  - Avoid nested loops to prevent CPU timeout.  

**2.2.3 Approval Processes and Assignment Rules**  
- **Approval Processes**: Multi-step workflows for record sign-offs.  
  - **Example**: Route a `Contract` to Legal, then Finance for approval.  
- **Assignment Rules**: Auto-route records (e.g., Cases) to users/queues based on criteria.  

---

#### **2.3 Security and Access Control**  
**Objective**: Enforce least privilege and data protection.  

**2.3.1 Profiles, Permission Sets, and Role Hierarchies**  
- **Profiles**: Baseline permissions (object/field access, tabs, apps).  
  - **Standard Profiles**: Read-Only, System Administrator.  
  - **Custom Profiles**: Tailored to departments (e.g., Sales, HR).  
- **Permission Sets**: Grant additional privileges without modifying profiles.  
  - **Example**: Allow temporary access to `View All Data` for auditors.  
- **Role Hierarchies**: Control data visibility (e.g., Managers see subordinate records).  

**2.3.2 Sharing Rules, OWD, and Manual Sharing**  
- **OWD (Organization-Wide Defaults)**: Baseline record access (Private, Public Read/Write).  
- **Sharing Rules**: Extend access beyond OWD (e.g., share `Opportunities` with regional teams).  
- **Manual Sharing**: Grant ad-hoc access to individual users (e.g., a contractor).  

**2.3.3 Field-Level Security (FLS) and Object Permissions**  
- **FLS**: Restrict access to sensitive fields (e.g., `Salary__c`).  
- **Object Permissions**: CRUD (Create, Read, Update, Delete) controls.  

---

### **Real-World Example**  
**Use Case**: A healthcare provider configures Salesforce to:  
1. Create a custom object `Patient__c` with Master-Detail to `Account`.  
2. Build a Flow to auto-schedule follow-up tasks post-appointment.  
3. Restrict access to `Medical_History__c` fields via FLS for HIPAA compliance.  

---

### **Key Takeaways**  
1. **Data Modeling**: Balance flexibility and simplicity to avoid technical debt.  
2. **Automation**: Prefer Flow over Process Builder for complex logic.  
3. **Security**: Combine OWD, roles, and permission sets for granular control.  

---

### **Review Questions**  
1. When would you use a master-detail vs. lookup relationship?  
2. How do sharing rules interact with OWD settings?  
3. What are the risks of overusing workflow rules in a large org?  

---

### **Visual Aids (Suggested)**  
- **Diagram**: ERD for a sample CRM data model.  
- **Screenshot**: Flow Builder interface with decision nodes.  
- **Matrix**: Profile vs. Permission Set permissions.  

---

This chapter equips admins and developers with the tools to design scalable, secure, and automated Salesforce solutions, emphasizing best practices to avoid common pitfalls like over-customization or security gaps.
