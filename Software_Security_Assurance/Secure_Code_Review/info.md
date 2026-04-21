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


##### Report Findings during Secure Code Review

Attribute Description

**Vulnerability ID**  Alpha_Numeric ID

**Severity Risk Level** `High

**Vulnerability Name** Vulnerability Title

**Root Cause** Provide technical details about problem with explanation why this is vulnerability

**Evidences** Source code snippets for major variants, provide file names also for more clarity

**Instances** Total # of instances due to same root cause]. In case of automated scans, additionally specify High[nn], Medium[nn], Low[nn] as reported by tool



##### Report Findings during Secure Code Review

Attribute Description

**File Names** All file names that requires change, if file names are not known, give entry point reference

**Component Name**  Name of the component affected by this vulnerability (you may take help from dev team)

**Severity/Risk Level**  [High / Medium / Low]* with rational for selection

**Countermeasure**  From Secure Programming Practices

**Remediation**  Exact code syntax or configuration detail to patch the vulnerability

**Taxonomy**  CWE Weakness IDs, Fortify Kingdom

**Test type**  Automated / Semi automated / Manual

**References**  Provide references for further reading or details


##### Introduction

Authentication is the process through which the identity of an entity is established to be genuine, typically with the help of credentials such as username and password.

There are several available authentication mechanisms to choose from. However, if not chosen correctly and implemented, the authentication mechanism may expose vulnerabilities that perpetrators can exploit to break into the system.

Another issue of concern is the storage of passwords and user credentials both from a defense in depth view and also from a compliance standpoint.

The topic discusses authentication constraints, password storage and what to review for.



##### Weak Passwords and Password Functionality

It is necessary to enforce password strength upon a user setting or while selecting a password.

In general passwords should be complex in composition.

Such checks should be performed on the backend/server side of the application upon an attempt to submit a new password.

Bad Example

A simple check to ensure that the password is not NULL is not good enough:

```
String password = request.getParameter("Password");
if (password == Null) 
   {throw InvalidPasswordException()
   }
```


##### Weak Passwords and Password Functionality

### Good Example

Passwords should be scrutinized for the following composition or a variance of such

-   at least: 1 uppercase character (A-Z)
-   at least: 1 lowercase character (a-z)
-   at least: 1 digit (0-9)
-   at least one special character (!"£$%&...)
-   a defined minimum length (8 chars)
-   a defined maximum length (as with all external input)
-   no contiguous characters (123abcd)
-   not more than 2 identical characters in a row (1111)

Such rules should be looked for in code and used as soon as the http request is received.



##### Weak Passwords and Password Functionality

The rules can be complex RegEx expressions or logical code statements:

```
if password.RegEx([a-z])
   and password.RegEx([A-Z])
   and password.RegEx([0-9])
   and password.RegEx({8-30})
   and password.RexEX([!"£$%^&*()])
   return true;
else
return false;

```

A regular expression statement for code above:

```
(?=^.{8,30}$)(?=.*\d)(?=.*[a-z])(?=.*[A-Z])(?=.*[!@#$%^&*()_+}{"":;'?/>.<,]).*$
```


##### Password Storage Strategy

Secure storage of passwords is another area of prime concern, as unauthorized access to an application may give perpetrators access to area where passwords are stored.

Hence to avoid such cases, a solution is to store passwords using a  **one-way hash algorithm**, so as to make them incomprehensible.

-   One way functions (SHA-256 SHA-1, ..;) are also known as  `Hashing functions`.

Authentication is performed by computing the hash of the password entered by the user with the stored hash. If the hashes are equal, the password entered by the user is correct.

#### Advantages of hashing passwords

Storing a password as a hash value which cannot be reversed makes it almost impossible to recover the plain text passwords.

It also helps mitigates the internal threat vector as even the administrative staff will not be able to misuse other user's credentials.


##### Password Storage Strategy

Example code in Java implementing SHA-1 hashing:

```
import java.security.MessageDigest;
public byte[] getHash(String password) throws NoSuchAlgorithmException {
      MessageDigest digest = MessageDigest.getInstance("SHA-1");
      digest.reset();
      byte[] input = digest.digest(password.getBytes("UTF-8"));
```


##### Password Storage: Salting

Storing hash passwords as such also has some loopholes. For example : Two identical passwords would produce identical hashes.

[Birthday attacks](https://en.wikipedia.org/wiki/Birthday_attack)  is also a threat storing hashed passwords

A solution for such issues is to introduce a  [salt](https://en.wikipedia.org/wiki/Salt_(cryptography)).

A salt is a random number of a fixed length which is different for each stored entry. It is stored as clear text next to the hashed password.

Example:

```
import java.security.MessageDigest;
public byte[] getHash(String password, byte[] salt) throws NoSuchAlgorithmException {
      MessageDigest digest = MessageDigest.getInstance("SHA-256");
      digest.reset();
      digest.update(salt);
      return digest.digest(password.getBytes("UTF-8"));
}
```



##### Vulnerabilities related to authentication

There are numerous issues relating to authentication mechanisms that make use of form fields.

Inadequate field validation can give rise to the following issues:

**SQL Injection Attacks**

SQL injection can be exploited to bypass authentication functionality and may even add a malicious user to a system.

**Issues related data validation**

Data validation of all external input must be performed. This also applies to authentication fields.

**Cross-site scripting**

Cross site scripting on the authentication page may lead to identity theft, Phishing, and session hijacking attacks.

**Issues related to error handling**

Bad/weak error handling can be exploited to give away the internal workings of the authentication functionality such as the database structure, valid and invalid user IDs, etc.



##### Introduction

Authorization is a key aspect in multi-user environments where there is a need to segregate user data.

While Authentication deals with  `“Who you are?”`, Authorization deals with  `“What you can do”`.

There are primarily two dimensions to authorization:

-   **Horizontal authorization**  - Different users/entities should not be able to access other users'/entities' data.
    
-   **Vertical authorization**  - Authorization that restricts the functionality of a subset of users. For example: admin users would have extra admin functionality that a regular user would not have access to .
    

Authorization issues involve various layers in a web application: from the functional authorization of a user to gain access to a particular function of the application at the application layer, to the database access authorization and least privilege issues at the persistence layer.

So what to look for when performing a code review?

From an attack perspective, the most common issues are a result of curiosity and also exploitation of vulnerabilities such as SQL injection.



##### Locating Potentially Vulnerable Code

Business logic errors is a main area to analyze authorization errors.

It is worth looking at areas where authorization checks are performed.

Logical conditional cases are need to be examined.

Example: malformed logic

```
if user.equals("NormalUser"){
   grantUser(Normal_Permissions);
}else{ //user must be admin/super
  grantUser("Super_Persmissions);
}

```

For classic ASP pages, authorization is typically carried out using  `include files`  that encompass the access control validations and restrictions. Hence, code reviewers usually look for something like

```
<!--#include file="ValidateUser.inc"-->

```

An additional issue arises here -  **Information disclosure**, as the include file might be invoked directly and reveal application functionality.



##### Vulnerable Patterns for Authorization Issues

It is important to analyze whether the authorization model specifies on NOT displaying functions that a user does not have authorization to view/access.

Links that are not on the users' GUI may be discovered if a crawl is performed on the application. For example, Simple HTTP Get requests can reveal "Hidden" links.

However, a map on the server-side should be utilized to ensure whether a user is authorized to perform a task, and the GUI "hiding" buttons and links should not be solely relied upon.

-   Disabling buttons on the client side as a way of implementing authorization controls will not deter the user from executing the action relating to the button.

For example

```
document.form.adminfunction.disabled=true;
<form action="./doAdminFunction.asp">

```

The disable button can be activated by simply saving the page locally, and editing the  `disabled=true`  to  `disabled=false`  and adding the absolute form action.



##### Related Vulnerabilities

**OS Command Injection**

Operating System command injection can be exploited to completely ignore authorization constraints. The key objective of system breach is to gain access to the underlying host. The application is simply a channel for access to data.

**SQL Injection**

SQL injection can be exploited to bypass authorization controls. SQL injection is in essence accessing the data through an "out of band" channel not intended by the application.

**The Secure Code Environment**

Insecure class files, folders in deployment may be exploited to attack an application outside the actual application itself.

**Session Integrity issues**

Impersonation is a threat to authorization as it can be used to gain unauthorized privilege.

**Race Conditions**

In a multi user, multi-threaded environment thread safety is important as one may erroneously gain access to another individuals session .



**Input validation**
Input validation is a highly effective technical control for application security.

It can mitigate numerous vulnerabilities including cross-site scripting, various forms of injection, and some buffer overflows.

Reviewing input validation involves more than checking form field values.



##### Data Validation

Input validation has to be performed for all external inputs to the system.

The validation rules are defined w.r.t the business requirements for the application. If possible, an exact match validator should be implemented that permits only the data that conforms to an expected value.

#### Approaches to Validation

-   `"Known-good"`  - Only permits characters/ASCII ranges defined within a white-list.
    
    -   Flexible and common approch but is a little weak.
-   `"Known-bad"`  - a black list of "bad characters".
    
    -   Not future proof and would need maintenance.
-   `"Encode-bad"`  simply encodes characters considered "bad" to a format which should not affect the functionality of the application and hence is very weak.



##### Business Validation

Business validation has to do with business logic.

Before reviewing a code which implements a particular logic it is important to have a good understanding of the business logic involved.

Business validation could be leveraged to limit the range of values or a transaction that a user inputs or reject input which does not make much business sense.

Reviewing code for business validation can also include rounding errors or floating point issues which may give rise to issues such as integer overflows which can dramatically damage the bottom line.


##### Canonicalization

_**Canonicalization is the process by which different equivalent forms of a name can be resolved to a single standard name, or the "canonical" name.**_

For example. a single character, such as a period/full-stop (.), could be represented in many different ways: ASCII 2E, Unicode C0 AE, etc.

The most popular encodings are UTF-8, UTF-16, and so on.

With the numerous ways of encoding user input, a web application's filters can be easily breached if not carefully built.

### Bad Example

```
public static void main(String[] args) {
    File x = new File("/cmd/" + args[1]);
    String absPath = x.getAbsolutePath();
}

```

### Good Example

```
public static void main(String[] args) throws IOException {
    File x = new File("/cmd/" + args[1]);
    String canonicalPath = x.getCanonicalPath();
}
```

**Session Management**

##### The Expectations

From a code review perspective, session management should focus on the creation, renewal, and destruction of a user’s session throughout the application.

The code review process should ensure the following:

**Session ID**

Authenticated users should have a cryptographically secure and robust association with their session.

The session identifier (Session ID) should not be predictable, and generation of such should be left to the underlying framework.

The development effort to produce a session with sufficient entropy is subject to errors, and best left to tried and trusted methods.



##### The Expectations

**Authorization**

-   Applications should check if the session is valid prior to servicing any user requests. The user's session object may also hold authorization data.
    
-   Session ID should be applied to a new user upon successful authentication.
    
-   Reviewing the code to identify where sessions are created and invalidated is important. A user should be assigned a new unique session once authenticated to mitigate session fixation attacks.
    
-   Sessions may need to be terminated upon authorization failures. If a logical condition exists which is not possible, unless the state transition is circumvented or an obvious attempt to escalate privileges, a session should be terminated.



##### The Expectations

**Session Transport**

Applications avoid or prevent common web attacks, such as replay, request forging, and man-in-the-middle.

-   Session identifiers should be passed to the user in a secure manner such as not using HTTP GET with the session ID being placed in the query string. Such data (query string) is logged in web server logs.
    
-   Cookie transport should be performed over a secure channel. Review the code in relation to cookie manipulation. Verify if the secure flag is set. This prevents the cookie being transported over a non-secure channel.


##### The Expectations

**Session Lifecycle**

-   Session Timeout - Sessions should have a defined inactivity timeout and also in some cases a session hard-limit. The code review should examine such session settings. They may be defined in configuration files or in the code itself. Hard limits shall kill a session regardless of session activity.
    
-   The log-out commands must do more that simply kill the browser. Review the code to verify that log-out commands invalidate the session on the server. Upon the logout request, be it a parameter or URL, one must review the code to ensure the session is invalidated.



##### Example for Session Invalidate:

```
import java.io.*;
import javax.servlet.*;
import javax.servlet.http.*;
import java.sql.*;
public class doLogout extends HttpServlet
    {
         public void doGet(HttpServletRequest req,HttpServletResponse res)throws ServletException,IOException
         {
              res.setContentType("text/html");
              HttpSession ses =req.getSession(); 	
              ses.removeValue("Login");
              ses.removeValue("password");
              ses.invalidate();	 				 
              res.sendRedirect("http://company.com/servlets/login.html");			
         }	
    }

```

##### Practical Insights

Visit the following link and go through the exercise to gain a practical understanding about the exploitation of a session injection.

This issue can be used to inject arbitrary content inside the session and therefore modify the application logic to escalate privileges.

[Pentester lab - Session Injection](https://pentesterlab.com/exercises/play_session_injection/course)


##### Locating Potentially Vulnerable Code

A secure way to build SQL statements is to construct all queries with  `PreparedStatement`  instead of  `Statement`  and/or to use  `parameterized stored procedures`.

Parameterized stored procedures makes it impossible for a perpetrator to modify the original SQL statement as they are compiled before user input is added.

The account used to make the database connection must have “Least privilege.” If an application requires read access then the account must be given read access only.

Avoid disclosing error information: Weak error handling is a very convenient method for an attacker to orchestrate SQL injection attacks. Uncaught SQL errors typically give away too much information and contain things like table names and procedure names.


##### Locating Potentially Vulnerable Code

A secure way to build SQL statements is to construct all queries with  `PreparedStatement`  instead of  `Statement`  and/or to use  `parameterized stored procedures`.

Parameterized stored procedures makes it impossible for a perpetrator to modify the original SQL statement as they are compiled before user input is added.

The account used to make the database connection must have “Least privilege.” If an application requires read access then the account must be given read access only.

Avoid disclosing error information: Weak error handling is a very convenient method for an attacker to orchestrate SQL injection attacks. Uncaught SQL errors typically give away too much information and contain things like table names and procedure names.



##### Best Practices when Dealing with Databases

Use Database stored procedures

-   But even stored procedures can be vulnerable if string concatenation is used to form sql query internally.

Use parameterized queries instead of dynamic SQL statements.

Data validate all external input: Ensure that all SQL statements recognize user inputs as variables, and that statements are precompiled before the actual inputs are substituted for the variables in Java.


##### SQL Injection Example

```
String DRIVER = "com.ora.jdbc.Driver";
String DataURL = "jdbc:db://localhost:5112/users";
String LOGIN = "admin";
String PASSWORD = "admin123";

Class.forName(DRIVER);

//Make connection to DB
Connection connection = DriverManager.getConnection(DataURL, LOGIN, PASSWORD);

String Username = request.getParameter("USER"); // From HTTP request
String Password = request.getParameter("PASSWORD"); // From HTTP request

int iUserID = -1;

String sLoggedUser = "";

String sel = "SELECT User_id, Username FROM USERS WHERE Username = '" +Username + "' AND Password = '" + Password + "'";

Statement selectStatement = connection.createStatement ();
ResultSet resultSet = selectStatement.executeQuery(sel);


if (resultSet.next()) {
       iUserID = resultSet.getInt(1);
       sLoggedUser = resultSet.getString(2);
}

PrintWriter writer = response.getWriter ();

if (iUserID >= 0) {
       writer.println ("User logged in: " + sLoggedUser);
} else {

       writer.println ("Access Denied!")
}
```



##### SQL Injection Example

When SQL statements are dynamically created as software executes, there is a window for a security breach as the input data can truncate, malform or even expand the original SQL query!

1.  In the code snippet, the  `request.getParameter`  retrieves the data for the SQL query directly from the HTTP request without any data validation.

-   This error gives rise to the ability to input SQL as the payload and alter the functionality in the statement.

2.  The application places the payload directly into the statement causing the SQL vulnerability:

```
String sel = "SELECT User_id, Username FROM USERS WHERE Username = '" Username + "' AND Password = '" + Password + "'";
```



##### Introduction

Cross-site scripting (XSS) attacks occur when an attacker uses a web application to send malicious code, generally in the form of a browser side script, to a different end user.

Flaws that allow these attacks to succeed are quite widespread and occur anywhere a web application reflects user input without validation or encoding.


##### Finding XSS during Code Review

-   Find all html output parameters
    
-   Identify invalidated inputs in the application and trace those up to output
    
-   Focus on the areas where application code returns output to a user (client).
    

Solution:

-   XSS attacks can be prevented using encoding. Server-side encoding is a function in which scripting tags in all dynamic content can be replaced with codes in a chosen character set.
    
-   Input validation can be used to prevent end users from entering malicious scripts



##### XSS: Find the bug in the code

```
<%

1. fcount = RS.Fields.count-1
2. Response.Write("<div class='label'> Search Results </div><br / >")
3. Response.Write("You Searched for :" & Request.Form("txtsearch"))
4. Response.Write("<table border=1><tr bgcolor='#EEEEEE'>")
5. Response.Write("<table border=1><tr bgcolor='#EEEEEE'>")
6. For i=0 to fcount
7. 	Response.Write("<th> &  RS(i).name & "</th>")
8. 	Next
9. 	Response.Write("</tr>")
10. 	While Not RS.EOF
11. 			Response.Write("</tr>")
12.			For i=0 to fcount
13.				Response.Write("<td>" & RS.(i).value &  ("</td>")
14.			Next
15.			Response.Write("</tr>")
16.			RS.MoveNext()
17. 	End While
	
%>
```


##### XSS - Solution

```
<%

1. fcount = RS.Fields.count-1
2. Response.Write("<div class='label'> Search Results </div><br / >")
3. Response.Write("You Searched for :" & Server.HtmlEncode(Request.Form("txtsearch")))
4. Response.Write("<table border=1><tr bgcolor='#EEEEEE'>")
5. Response.Write("<table border=1><tr bgcolor='#EEEEEE'>")
6. For i=0 to fcount
7. 	Response.Write("<th> &  Server.HtmlEncode(RS(i).name) & "</th>")
8. 	Next
9. 	Response.Write("</tr>")
10. 	While Not RS.EOF
11. 			Response.Write("</tr>")
12.			For i=0 to fcount
13.				Response.Write("<td>" & Server.HtmlEncode(RS.(i).value) &  ("</td>")
14.			Next
15.			Response.Write("</tr>")
16.			RS.MoveNext()
17. 	End While
	
%>

```

`Server.HtmlEncode`  function will help in encoding all html tags during output. (Line number 3)

Also we can see line number 7 and 13 where data is being displayed through database content. We have used output encoding also for those kind of output.


##### Applicability

-   For ADM type projects, automated code review is mandatory. For Medium risk applications manual code review for critical components, High risk applications major components and for Very High risk application, line by line code review is required
    
-   For COTS customization projects, code review for customized part
    
-   For system integration projects, interface related code and batch jobs shall be reviewed
    
-   For all other projects, it is recommended to review code for critical components of the system
    
-   For BPO, Infrastructure maintenance & Assurance projects, which are not dealing with source code, Security Code Review is not applicable
