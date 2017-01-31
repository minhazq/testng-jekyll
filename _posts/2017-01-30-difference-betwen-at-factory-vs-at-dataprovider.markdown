---
title: Difference betwen @Factory vs @DataProvider
date: 2017-01-30 23:01:00 -05:00
---

Below is the main difference between @Factory and @DataProvider functionalities on TestNG.

DataProvider: A test method that uses DataProvider will be executed a multiple number of times based on the data provided by the DataProvider. The test method will be executed using the same instance of the test class to which the test method belongs.
Factory: A factory will execute all the test methods present inside a test class using a separate instance of the respective class.
TestNG factory is used to create instances of test classes dynamically. This is useful if you want to run the test class any number of times. For example, if you have a test to login into a site and you want to run this test multiple times,then its easy to use TestNG factory where you create multiple instances of test class and run the tests (may be to test any memory leak issues).

Whereas, dataprovider is used to provide parameters to a test. If you provide dataprovider to a test, the test will be run taking different sets of value each time. This is useful for a scenario like where you want to login into a site with different sets of username and password each time.