---
title: Annotation in TestNG
date: 2017-01-30 15:53:00 -05:00
---

**@BeforeSuite or @AfterSuite:**
<p>The annotated method will be executed before and after any tests declared inside a TestNG suite.</p>
**@BeforeTest or @AfterTest**
<p>The annotated methods will be executed before and after each test section declared inside a TestNG suite</p>
**@BeforeGroups or @AfterGroups**
<p>These annotations are associated with the groups feature in TestNG. BeforeGroups annotated method will run before any of the test method of the specified group is executed. AfterGroups annotated method will run after any of the test method of the specified group gets executed. For this method to be executed, the user has to mention the list of groups this method belongs to using groups attribute with the said annotation. You can specify more than multiple groups if required.</p>
**@BeforeClass or @AfterClass**
<p>BeforeClass annotated method is executed before any of the test method of a test class. AfterClass annotated method is executed after the execution of every test methods of a test class are executed.</p>
**@BeforeMethod or @AfterMethod**
<p>These annotated methods are executed before/ after the execution of each test method.</p>
**@DataProvider**
<p>Marks a method as a data providing method for a test method. The said method has to return an Object double array (Object[ ][ ]) as data.</p>
**@Factory**
<p> Marks a annotated method as a factory that returns an array of class objects (Object[ ]). These class objects will then be used as test classes by TestNG. This is used to run a set of test cases with different values.</P>
<p>@Listeners</P>
<p> Applied on a test class. Defines an array of test listeners classes extending org.testng.ITestNGListener. Helps in tracking the execution status and logging purpose.</p>
<p>@Parameters</p>
<p> This annotation is used to pass parameters to a test method. These parameter values are provided using the testng.xml configuration file at runtime.</p>
<p>@Test</p>
<p> Marks a class or a method as a test method. If used at class level, all the public methods of a class will be considered as a test method. </p>  
    

  