What is Secure Code Review?
Security code review is the process of auditing the source code for an application to verify that the proper security controls are present, that they work as intended, and that they have been invoked in all the right places.

This course covers the following topics_

-   **What is Secure Code Review**
    
-   **Secure Code Review in the SDLC**
    
-   **Code Review Metrics**
    
-   **Security Code Review Coverage**
    
-   **Code Level Security Defects - Authentication and authorization**
    
-   **Code Level Security Defects - Input Validation and Session Management**
    
-   **Reviewing Code for SQL Injection & Cross Site Scripting**
    
-   **Using Secure Code Review in Projects**


##### Laying the Groundwork

The first step in an effective code review involves understanding the business scope of the application and the most crucial business impacts. 

This involves identifying the different threat agents, the motivation involved, as well as potential attack methods.

All this information can be aggregated into a high-level threat model of the application that represents all of information that is relevant to application security.

The ultimate aim is to ensure that the key risks have been properly addressed by security controls that work properly and are used in all the right places.


##### Before Getting Started...

The reviewer(s) need to be familiar with:

**Code:**  The language(s) used, the features and issues of that language from a security perspective.

-   The issues that need to be considered and best practices from security and performance perspective.

**Context**: The working of the application being reviewed. All security is in context of what we are trying to secure.

-   What type of data is being manipulated or processed, and what would be the damage to the organization if this data was compromised?

**Audience**: The intended users of the application.

-   Does this application interact with other entities (machines/services)?
    
-   Is it externally facing or internal to “trusted” users?
    

**Importance**: The size of the consequences of failure.

-   Will the enterprise be affected in any significant way if the application fails to perform its functions as intended?



##### Discovery: Information Gathering

In order for the process to be effective, the review team would need some information to review the application.

The information gathered should be organized into a threat model that can be used to prioritize the review.

Ideally, the information required can be obtained by studying design documents, functional specifications, business requirements, test results, and the like.

-   However, in most real-world projects, the documentation is significantly out of date and almost never has appropriate security information.

Hence, one of the most effective ways to get started, and probably the most accurate, is to interact with the developers and the lead architect for the application.

A walk through of the actual running application is very effective in gaining a good understanding about how the application is intended to work.



##### Understanding the Context

`Security code review is not simply about reviewing code.`

The ultimate aim behind code review is to ensure that the code adequately protects the information and assets it has been entrusted with, such as money, intellectual property, trade secrets, data, etc.

The context in which the application is intended to operate is a very important issue in establishing potential risk.

If the business context is not clear to the reviewers, critical risks may be missed while focusing on issues that are insignificant to the business.



##### Understanding the Context

As preparation for a security code review, a high level threat model should be prepared which incorporates the information that are vital for a successful review process.

The major areas are listed here:

-   Threat Agents
    
-   Attack Surface (including any public and backend interfaces)
    
-   Possible Attacks
    
-   Required Security Controls (both to stop likely attacks and to meet corporate policy)
    
-   Potential Technical Impacts
    
-   Important Business Impacts


##### Understanding the Context

Defining the context should help understand the following clearly:

-   The importance of the application to the enterprise.
    
-   The boundaries of the application context.
    
-   Trust relationships between entities.
    
-   The potential threats and possible controls.


##### The Checklist

Defining a generic checklist which can be filled out by the development team can help significantly in understanding the context of the application.

The checklist is a good measure for the level of security the developers have attempted or thought of.

The checklist should cover the most critical security controls and vulnerability areas such as:

-   Data Validation
-   Authentication
-   Session Management
-   Authorization
-   Cryptography
-   Error Handling
-   Logging
-   Security Configuration
-   Network Architecture


##### Waterfall SDLC Example

1.  Requirements definition
    
    -   Application Security Requirements
2.  Architecture and Design
    
    -   Application Security Architecture and/or Threat Model
3.  Development
    
    -   Secure Coding Practices
        
    -   Security Testing
        
    -   Security Code Review

4.  Test
    
    -   Penetration Testing
5.  Deployment
    
    -   Secure Configuration Management
        
    -   Secure Deployment
        
6.  Maintenance



##### Agile Security Methodology Example

1.  Planning
    
    -   Identify Security Stakeholder Stories
        
    -   Identify Security Controls
        
    -   Identify Security Test Cases
        
2.  Sprints
    
    -   Secure Coding
        
    -   Security Test Cases
        
    -   Peer Review (including security code review)
        
    -   Penetration Testing (high risk or with major releases)
        
3.  Deployment
    
    -   Secure Configuration Management
        
    -   Secure Deployment


##### Relative and Absolute Metrics

There are two categories of software metrics:  `Relative`  and  `Absolute`.

**Absolute metrics:**  Numerical values that describe a trait of the code such as the number of references to a particular variable in an application, or the number of lines of code (LOC).

-   Do not involve subjective context but are material facts.

**Relative metrics:**  A representation of an attribute that cannot be measured directly, and are subjective and dependent on the context of where the metric was derived.


##### Secure Development Metrics

### Defect Density

_The average occurrence of programming faults per Lines of Code (LOC)._

Provides a high level view of the code quality.

Fault density by itself does not yield a pragmatic metric. Defect density would cover minor issues as well as major security flaws in the code; all are treated the same way.

Defect density alone cannot be used to judge the security of code accurately.

### Lines of Code (LOC)

_The count of the executable lines of code_. Does not include Commented-out code or spaces.

Attempts to quantify the size of the code.

Gives a rough estimate but is may not be precise.


### Function Point

_The estimation of software size by measuring functionality._

It includes a combination of a number of statements performing a specific task, independent of the underlying programming languages or development methodology.

### Risk Density

Similar to defect density, but  _issues discovered are rated by risk (high, medium & low)_.

This can be used to gain insight into the quality of the code being developed through a  _**[X Risk / LoC]**_  or  _**[Y Risk / Function Point]**_  value.

_(X&Y being high, medium or low risks) as defined by internal application development policies and standards._



### Path complexity/complexity-to-defect/cyclomatic complexity

Cyclomatic complexity can be used to  _establish risk and stability estimations on an item of code_, such as a class or method or even a complete system.

`CC = Number of decisions +1`

A decision could be considered commands such as:

If....else switch case catch while do and so on.....

Complexity increases with the decision count. Complex code is less stable and difficult to maintain.

The more complex the code, the higher risk of defects.

Thresholds for Cyclomatic complexity can be established as follows:

-   0-10: Stable code - Acceptable complexity
-   11-15: Medium Risk - More complex
-   16-20: High Risk code -Too many decisions for a unit of code.



### Inspection Rate

Can be utilized to get a rough estimate of the required duration to perform a code review.

The inspection rate is  _the rate of coverage a code reviewer can cover per unit of time_.

It has be noted that a rate of 250 lines per hour would be a baseline. This rate is not to be used as part of a measure of review quality, but simply to determine duration of the task.

### Defect Detection Rate

This metric measures  _the defects found per unit of time_.

Can be used to measure performance of the code review team, but not as a quality measure.

Defect detection rate would normally increase as the inspection rate (above) decreases.


### Code Coverage

Measured as a  _% of LoC of function points_, the code coverage is the proportion of the code reviewed.

In the case of manual review the target is set to 100%, unlike automated testing wherein 80-90% is considered good.

A higher percentage of code coverage ensures better quality and prevents logic errors.

### Defect Correction Rate

_The amount of time used to correct detected defects._

Can be utilized to enhance a project plan within the SDLC.

### Reinspection Defect Rate

The rate at which upon re-inspection of the code more defects exist, some defects still exist, or other defects manifest through an attempt to address previously discovered defects.



##### Analyzing the Attack Surface

Analyzing the attack surface forms a major part of the actual security code review process.

A typical application takes input(s) and produces output(s) of some kind.

Attacking applications involves triggering unexpected conditions for the application to process.

The first step in the process is to identify all the input to the code.

Input, for example, can be:

-   Browser input
-   Cookies
-   Property files
-   External processes
-   Data feeds
-   Service responses
-   Flat files
-   Command line parameters
-   Environment variables


##### Exploring the Attack Surface

Exploring the attack surface incorporates dynamic and static data flow analysis:

-   When and where variables are set
-   How the variables are utilized throughout the workflow
-   How attributes of objects and parameters might influence other data within the program.

It analyzes if the parameters, method calls, and data exchange mechanisms affect the required security.

All transactions within the application along with the security functions involved need to be identified and analyzed.


##### Exploring the Attack Surface

The areas that are covered during transaction analysis are:

-   Data/Input Validation of data from all untrusted sources
-   Authentication
-   Session Management
-   Authorization
-   Cryptography (Data at rest and in transit)
-   Error Handling /Information Leakage
-   Logging /Auditing
-   Secure Code Environment


##### Understand What You Are Reviewing

Frameworks are extensively used to develop many modern applications.

-   Advantage: Less work for the developers as the framework handles most of the "housekeeping"

The objects developed by the development team extend the functionality of the framework.

It is here that the knowledge of a given framework, and language in which the framework and application is implemented, is of paramount importance.


##### An Example - Java

_In struts the struts-config.xml and the web.xml files are the core points to view the transactional functionality of an application._

```
<?xml version="1.0" encoding="ISO-8859-1" ?>
<!DOCTYPE struts-config PUBLIC
         "-//Apache Software Foundation//DTD Struts Configuration 1.0//EN"
         "http://jakarta.apache.org/struts/dtds/struts-config_1_0.dtd">
<struts-config>
 <form-beans>
 	<form-bean name="login" type="test.struts.LoginForm" />
 </form-beans>
 <global-forwards>
 </global-forwards>
 <action-mappings>
   <action
       path="/login"
       type="test.struts.LoginAction" >
           <forward name="valid" path="/jsp/MainMenu.jsp" />
           <forward name="invalid" path="/jsp/LoginView.jsp" />
   </action>
 </action-mappings>
<plug-in className="org.apache.struts.validator.ValidatorPlugIn">
 <set-property property="pathnames"
value="/test/WEB-INF/validator-rules.xml, /WEB-INF/validation.xml"/>
</plug-in>
</struts-config>
```


The struts-config.xml file contains the action mappings for each HTTP request where as the web.xml file contains the deployment descriptor.

----------

Example: The struts framework has a validator engine, which depends on regular expressions to validate the input data.

An attractive feature of the validator is that no code has to be written for each form bean. (Form bean is the Java object which received the data from the HTTP request).

The validator is not enabled by default in struts.

To enable the validator, a plug-in must be defined in the <plug-in> section of struts-config.xml in Red above.

The property defined tells the struts framework where the custom validation rules are defined (validation.xml) and a definition of the actual rules themselves (validation-rules.xml).

----------

Without a proper understanding of the struts framework, and by simply auditing the Java code, the validation being executed cannot be identified, and it is hard to understand the relationship between the defined rules and the Java functions.


##### Example - .NET

ASP.NET / IIS applications utilize an optional XML-based configuration file, named web.config, to maintain application configuration settings.

This takes care of issues such as authorization, authentication, , Error pages, HTTP settings, web service settings, debug settings, etc.

Without knowledge of these files, a transactional analysis would be tedious and inaccurate.

Optionally, a file web.config maybe provided at the root of the virtual directory for a web application.

If the file is absent, the default configuration settings in machine.config will be used. If the file is present, any settings in web.config will override the default settings.


##### Example - .NET

Example of a web.config file:

```
<authentication mode="Forms">
  <forms name="name"
         loginUrl="url" 
         protection="Encryption"
         timeout="30" path="/" >
         requireSSL="true|"
         slidingExpiration="false">
     <credentials passwordFormat="Clear">
        <user name="username" password="password"/>
     </credentials>
  </forms>
  <passport redirectUrl="internal"/>
</authentication>
```


From this config file snippet we can see:

**authentication mode**: The default authentication mode is ASP.NET forms-based authentication.

**loginUrl**: Specifies the URL where the request is redirected for login if no valid authentication cookie is found.

**protection**: Specifies that the cookie is encrypted using 3DES or DES but DV is not performed on the cookie. Beware of plaintext attacks!!

**timeout**: Cookie expiry time in minutes

The point to make here is that many of the important security settings are not set in the code per se, but in the framework configuration files.

Knowledge of the framework is of paramount importance when reviewing framework-based applications.