---
title: Parallelism
date: 2017-01-29 15:19:00 Z
---

In TestNG There is two main way you can make your Test methods , Test classes run in different thread. You can also run your tests in instance based. For example all firefox webdriver instance related test will run in one thread and all chrome webdriver instance reltated test will run in different thread. Here is the two main way:
<p>1. Defining in <u>testng.xml</u> file</p>
 <p>2. Defining in <u>annotation</u> right above in test methods.</p>