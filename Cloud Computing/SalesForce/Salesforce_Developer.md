# SalesForce
## Sources
* [Youtube Tutorials Point](https://www.youtube.com/watch?v=BA-407HF_fM&list=PLWPirh4EWFpH2LYVIrfmA1RTredCySwP_)
* [SalesForce](https://www.youtube.com/watch?v=jDYfTfaqclk&list=PL6747B4DAE356E17C)
* [Administrator Certification Exam](https://www.youtube.com/watch?v=vji9NEdX5AY&list=PLJ12axA2fmEAux6zD2viP5kgUFMsnVKw0)
* [SalesForce Connected Apps](https://www.youtube.com/watch?v=dNB_FRw7mEs)
* [SalesForce OAuth](https://www.youtube.com/watch?v=zpToAGuhg60)
* [SalesForce Single Sign On](https://www.youtube.com/watch?v=ucmyYJ3iQoA)
* [SalesForce Single Sign On](https://www.youtube.com/watch?v=kIA1MZrNaAE)
* [SAML](https://www.youtube.com/watch?v=0fmNoqz6Urw)
* [SalesForce Learning Center](https://www.salesforce.com/eu/learning-centre/)

Additional Resources;

* [Apex TutorialsPoint](https://www.tutorialspoint.com/apex/)
* [SalesForce TutorialsPoint](https://www.tutorialspoint.com/salesforce)
* [List of some resources](https://www.geckoboard.com/blog/19-best-training-resources-to-learn-salesforce/)
* [Salesforce resources Search Engine](http://findsf.info/)
* [Apex Developers Guide](https://developer.salesforce.com/docs/atlas.en-us.apexcode.meta/apexcode/apex_dev_guide.htm)
* [SalesForce Certification](https://www.adminhero.com/beginners-guide-to-salesforce-certification/)
* [SalesFroce Admin Zero-to-Hero Course](https://www.adminhero.com/zero-hero/)
* [Youtube SalesForce Channels](https://www.youtube.com/user/salesforce/channels)
* [SalesForce Developers Center](https://developer.salesforce.com/developer-centers)
* [SalesForce Reporting Basics](https://www.geckoboard.com/blog/salesforce-reporting-basics-building-aggregating-segmenting-formatting-reports/)
* [SalesForce CheatSheets](https://developer.salesforce.com/page/Cheat_Sheets) 
* [Salesfforce Best Practices](http://ecquire.com/blog/32-salesforce-guides/)
* [Tutorial](https://developerforce.github.io/lightning-connect-tutorial/)

---
# Development
1. Apex

## Force.com Integrated Development Environment (IDE)

The Force.com IDE is a free, Salesforce.com-supported Eclipse plugin. It is an
extension to the standard Eclipse development tool that helps with developing,
modifying, testing, and deploying applications on the Force.com platform. It
communicates with Salesforce, using the metadata API, which requires a user's
profile to have the Customize Application and Modify All Data permissions.
The IDE is a plugin for Eclipse, so it requires specific compatible versions of Eclipse.

So even if you are already using an older version, which is not supported by the
IDE, you can have another newer, compatible version installed on your system as
multiple versions of Eclipse can coexist on a system. Instructions for the Force.com

* [IDE](http://wiki.developerforce.com/index.php/Force.com_IDE_Installation)

## Anonymous Execution
Another important tool in the IDE is the Execute Anonymous view, which allows
you to run an anonymous block of Apex on the server. Anonymous blocks quickly
help you to evaluate Apex on the fly. This view is usually available on the lower
right-hand side of the Force.com perspective. This view provides an equivalent
functionality to the system log present in the Salesforce web-based UI.

## Apex Test Runner
Yet another important and powerful view in the Force.com IDE is the Apex Test
Runner view in which you can run your test methods to see which Apex unit tests
are passing or failing, including code performance and test coverage. This view
displays a test results summary—which code pieces do and do not meet minimum
code coverage requirements for production deployment, including a list of all lines not included. It also displays the output of the Apex debug statements and other system log events captured during test execution. This information is necessary for troubleshooting code, performance tuning, and checking resource usage.

## Apex

Apex is a proprietary language developed by Salesforce.com. It is a strongly typed, object-oriented programming language that allows developers to execute flow and transaction control statements on the Force.com platform server in conjunction with calls to the Force.com API.

It has a Java-like syntax and acts like database stored procedures. It enables the developers to add business logic to most system events, including button clicks, related record updates, and Visualforce pages.Apex code can be initiated by Web service requests and from triggers on objects. Apex is included in Performance Edition, Unlimited Edition, Enterprise Edition, and Developer Edition.

#### Features of Apex as a Language
The followings are some of the Apex features; 

#### Integrated
* Apex has built in support for Data manipulation language (DML) operations like INSERT, UPDATE, DELETE.
* It also supports the DML Exception handling. 
* It has support for inline SOQL and SOSL query handling which returns the set of sObject records. 

#### Java like syntax and easy to use
Apex is easy to use as it uses the syntax like Java. 
* variable declaration, 
* loop syntax and conditional statements.

#### Strongly Integrated With Data
Apex is data focused and designed to execute multiple queries and DML statements together. It issues multiple transaction statements on Database.

#### Strongly Typed
Apex is a strongly typed language. It uses direct reference to schema objects like sObject and any invalid reference quickly fails if it is deleted or if is of wrong data type.

#### Multitenant Environment
Apex runs in a multitenant environment. Consequently, the Apex runtime engine is designed to guard closely against runaway code, preventing it from monopolizing shared resources. Any code that violates limits fails with easy-to-understand error messages.

#### Upgrades Automatically
Apex is upgraded as part of Salesforce releases. We don't have to upgrade it manually.

#### Easy Testing
Apex provides built-in support for unit test creation and execution, including test results that indicate how much code is covered, and which parts of your code can be more efficient.

When Should Developer Choose Apex?
Apex should be used when we are not able to implement the complex business functionality using the pre-built and existing out of the box functionalities. Below are the cases where we need to use apex over Salesforce configuration.

Apex Applications
We can use Apex when we want to −

Create Web services with integrating other systems.

Create email services for email blast or email setup.

Perform complex validation over multiple objects at the same time and also custom validation implementation.

Create complex business processes that are not supported by existing workflow functionality or flows.

Create custom transactional logic (logic that occurs over the entire transaction, not just with a single record or object) like using the Database methods for updating the records.

Perform some logic when a record is modified or modify the related object's record when there is some event which has caused the trigger to fire.

Working Structure of Apex
As shown in the diagram below (Reference: Salesforce Developer Documentation), Apex runs entirely on demand Force.com Platform

Apex is an Object Oriented Programming language very similar to Java
* It has classes, methods
* Objects
* Polymorphic
* Overloading
* Inheritance
* Overriding
* Constructors

There are data types
Langages control statement like branching and looping

in Apex we uses system.debug to see the outputs

Ananymous Colde blocks
* Complie and excute
* Matadata is not stored
* User Permissions is required

you can create apex class by either using the developer console File New Apex Class
another is use from the menu Apex -> new -> save 

When saved it is complied and it uses the class name as apex Class
to execute the code use Anonymous Window and supply the values.

Class Definition Syntex

	private | public | global
	[virtual | abstract | with sharing | without sharing]
	class ClassName [implements InterfaceNameList] [extends ClassName] {
   		// Classs Body
	} 

Sample Apex Class

	public class MySampleApexClass {       //Class definition and body
   	public static Integer myValue = 0;     //Class Member variable
   	public static String myString = '';    //Class Member variable
   
   	public static Integer getCalculatedValue () {
   		// Method definition and body
   		// do some calculation
    	  myValue = myValue+10;
      	  return myValue;
   		}
	}

### Access Modifiers

#### 1- Private
If you declare the access modifier as 'Private', then this class will be known only locally and you cannot access this class outside of that particular piece. By default, classes have this modifier.

#### 2- Public
If you declare the class as 'Public' then this implies that this class is accessible to your organization and your defined namespace. Normally, most of the Apex classes are defined with this keyword.

#### 3- Global
If you declare the class as 'global' then this will be accessible by all apex codes irrespective of your organization. If you have method defined with web service keyword, then you must declare the containing class with global keyword.

### Sharing Modes
Let us now discuss the different modes of sharing.

#### 1- With Sharing
This is a special feature of Apex Classes in Salesforce. When a class is specified with 'With Sharing' keyword then it has following implications: When the class will get executed, it will respect the User's access settings and profile permission. Suppose, User's action has triggered the record update for 30 records, but user has access to only 20 records and 10 records are not accessible. Then, if the class is performing the action to update the records, only 20 records will be updated to which the user has access and rest of 10 records will not be updated. This is also called as the User mode.

#### 2- Without Sharing
Even if the User does not have access to 10 records out of 30, all the 30 records will be updated as the Class is running in the System mode, i.e., it has been defined with Without Sharing keyword. This is called the System Mode.

#### 3- Virtual
If you use the 'virtual' keyword, then it indicates that this class can be extended and overrides are allowed. If the methods need to be overridden, then the classes should be declared with the virtual keyword.

#### 4- Abstract
If you declare the class as 'abstract', then it will only contain the signature of method and not the actual implementation.

### Class Variables

Syntax

	[public | private | protected | global] [final] [static] data_type
	variable_name [= value]

In the above syntax −

	Variable data type and variable name are mandatory
	Access modifiers and value are optional.

Example

	public static final Integer myvalue;

Apex Data Types



### Apex Test Classes

Verification of the existing Apex Classes
It is both positive and negative test cases (sunny & Rainy day)

it provides the code coverage

Create test class very similar to Apex Class
Add @isTest to the top of the Class
Add "Static testmethod void methodname" 
inside the method creat the instance of the Apex Class
and use "system.assertEquals(value,Attribute or Method); 
This is very similar to JUnit. 

### Test Class best practices
 

#### Apex Soap API
#### Apex Rest API
