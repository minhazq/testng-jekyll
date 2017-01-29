---
title: Parallelism
date: 2017-01-29 10:19:00 -05:00
---

In TestNG There is two main way you can make your Test methods , Test classes run in different thread. You can also run your tests in instance based. For example all firefox webdriver instance related test will run in one thread and all chrome webdriver instance reltated test will run in different thread. Here is the two main way:
<p>1. Defining in <u>testng.xml</u> file</p>
<p>2. Defining in <u>annotation</u> right above in test methods.</p>
<p>
<u>**xml way**</u>
<p>the following will run each test methods in different thread or the amount threads that you assigned.
<p>
<pre style='color:#000000;background:#ffffff;'><span style='color:#004a43; '>&lt;!</span><span style='color:#800000; font-weight:bold; '>DOCTYPE</span> <span style='color:#bb7977; font-weight:bold; '>suite</span> <span style='color:#004a43; '>SYSTEM</span> <span style='color:#800000; '>"</span><span style='color:#666616; '>http</span><span style='color:#800080; '>:</span><span style='color:#800000; font-weight:bold; '>//</span><span style='color:#5555dd; '>testng.org</span><span style='color:#40015a; '>/testng-1.0.dtd</span><span style='color:#800000; '>"</span><span style='color:#004a43; '>></span>
<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>suite</span> <span style='color:#274796; '>name</span> <span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>My sutie</span><span style='color:#800000; '>"</span>  <span style='color:#274796; '>parallel</span><span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>methods</span><span style='color:#800000; '>"</span> <span style='color:#274796; '>thread-count</span><span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>2</span><span style='color:#800000; '>"</span><span style='color:#a65700; '>></span>

	<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>test</span> <span style='color:#274796; '>name</span> <span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>My Test</span><span style='color:#800000; '>"</span> <span style='color:#a65700; '>></span>
		<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>classes</span><span style='color:#a65700; '>></span>
			<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>class</span> <span style='color:#274796; '>name</span><span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>mq.demo.selenium.AppTest</span><span style='color:#800000; '>"</span><span style='color:#a65700; '>/></span>
		<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>classes</span><span style='color:#a65700; '>></span>
	
	<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>test</span><span style='color:#a65700; '>></span>

<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>suite</span><span style='color:#a65700; '>></span>
</pre>
</p>

</p>
</p>