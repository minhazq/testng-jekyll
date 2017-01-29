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
If you want to execute each **class** or each **test** parallel then change the "methods" to "classes" or "tests" in parallel attribute. Notice that all of them are plural. if you want to run instance based then you have to add in "test" level or in "suite" level attribute in xml. For example: 
<p>
<pre style='color:#000000;background:#ffffff;'><span style='color:#004a43; '>&lt;!</span><span style='color:#800000; font-weight:bold; '>DOCTYPE</span> <span style='color:#bb7977; font-weight:bold; '>suite</span> <span style='color:#004a43; '>SYSTEM</span> <span style='color:#800000; '>"</span><span style='color:#666616; '>http</span><span style='color:#800080; '>:</span><span style='color:#800000; font-weight:bold; '>//</span><span style='color:#5555dd; '>testng.org</span><span style='color:#40015a; '>/testng-1.0.dtd</span><span style='color:#800000; '>"</span><span style='color:#004a43; '>></span>
<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>suite</span> <span style='color:#274796; '>name</span> <span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>My sutie</span><span style='color:#800000; '>"</span>  <span style='color:#274796; '>parallel</span><span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>methods</span><span style='color:#800000; '>"</span> <span style='color:#274796; '>thread-count</span><span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>2</span><span style='color:#800000; '>"</span><span style='color:#a65700; '>></span>
	<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>test</span> <span style='color:#274796; '>name</span> <span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>My Test</span><span style='color:#800000; '>"</span> <span style='color:#274796; '>group-by-instances</span><span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>true</span><span style='color:#800000; '>"</span><span style='color:#a65700; '>></span>
  		<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>classes</span><span style='color:#a65700; '>></span>
			<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>class</span> <span style='color:#274796; '>name</span><span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>mq.demo.selenium.AppTest</span><span style='color:#800000; '>"</span><span style='color:#a65700; '>/></span>
		<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>classes</span><span style='color:#a65700; '>></span>
	<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>test</span><span style='color:#a65700; '>></span>
<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>suite</span><span style='color:#a65700; '>></span>
</pre>
</P></p></p>
<p><u>**annotation way**</u></p>
<p> There is **3** attributes goes with @Test annotation. <u>threadPoolSize = "2</> , <u>invocationCount="3"</u> and <u>timeOut="1000"</u>. These are very self explanatory. threadPoolSize is for how many threads you want to use for this method to execute . invocationCount is for how many time you want to execute this same method and timeOut is for after how many milliseconds you want to mark this method fail if it does not complete execution of this method.
<p>
<pre style='color:#000000;background:#ffffff;'><span style='color:#800000; font-weight:bold; '>package</span><span style='color:#004a43; '> mq</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>demo</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>selenium</span><span style='color:#800080; '>;</span>
<span style='color:#800000; font-weight:bold; '>import</span><span style='color:#004a43; '> org</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>testng</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>annotations</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>Test</span><span style='color:#800080; '>;</span>
<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#800000; font-weight:bold; '>class</span> AppTest <span style='color:#800080; '>{</span>

	<span style='color:#808030; '>@</span>org<span style='color:#808030; '>.</span>testng<span style='color:#808030; '>.</span>annotations<span style='color:#808030; '>.</span>BeforeMethod
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> before<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		<span style='color:#bb7977; font-weight:bold; '>System</span><span style='color:#808030; '>.</span>out<span style='color:#808030; '>.</span>println<span style='color:#808030; '>(</span><span style='color:#0000e6; '>"Before "</span><span style='color:#808030; '>+</span> <span style='color:#bb7977; font-weight:bold; '>Thread</span><span style='color:#808030; '>.</span>currentThread<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#808030; '>.</span>getId<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>	
	<span style='color:#800080; '>}</span>
	
	<span style='color:#808030; '>@</span>Test<span style='color:#808030; '>(</span>threadPoolSize<span style='color:#808030; '>=</span><span style='color:#008c00; '>1</span> <span style='color:#808030; '>,</span> invocationCount<span style='color:#808030; '>=</span><span style='color:#008c00; '>1</span><span style='color:#808030; '>,</span> timeOut<span style='color:#808030; '>=</span><span style='color:#008c00; '>1000</span><span style='color:#808030; '>)</span>
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> m1<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		<span style='color:#bb7977; font-weight:bold; '>System</span><span style='color:#808030; '>.</span>out<span style='color:#808030; '>.</span>println<span style='color:#808030; '>(</span><span style='color:#0000e6; '>"m1 "</span><span style='color:#808030; '>+</span><span style='color:#bb7977; font-weight:bold; '>Thread</span><span style='color:#808030; '>.</span>currentThread<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#808030; '>.</span>getId<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>	
	<span style='color:#800080; '>}</span>
	
	<span style='color:#808030; '>@</span>Test<span style='color:#808030; '>(</span>threadPoolSize<span style='color:#808030; '>=</span><span style='color:#008c00; '>1</span> <span style='color:#808030; '>,</span> invocationCount<span style='color:#808030; '>=</span><span style='color:#008c00; '>1</span><span style='color:#808030; '>,</span> timeOut<span style='color:#808030; '>=</span><span style='color:#008c00; '>1000</span><span style='color:#808030; '>)</span>
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> m2<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		<span style='color:#bb7977; font-weight:bold; '>System</span><span style='color:#808030; '>.</span>out<span style='color:#808030; '>.</span>println<span style='color:#808030; '>(</span><span style='color:#0000e6; '>"m2 "</span><span style='color:#808030; '>+</span><span style='color:#bb7977; font-weight:bold; '>Thread</span><span style='color:#808030; '>.</span>currentThread<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#808030; '>.</span>getId<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>	
	<span style='color:#800080; '>}</span>
	
	
	<span style='color:#808030; '>@</span>org<span style='color:#808030; '>.</span>testng<span style='color:#808030; '>.</span>annotations<span style='color:#808030; '>.</span>AfterMethod
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> after<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		<span style='color:#bb7977; font-weight:bold; '>System</span><span style='color:#808030; '>.</span>out<span style='color:#808030; '>.</span>println<span style='color:#808030; '>(</span><span style='color:#0000e6; '>"Before "</span><span style='color:#808030; '>+</span> <span style='color:#bb7977; font-weight:bold; '>Thread</span><span style='color:#808030; '>.</span>currentThread<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#808030; '>.</span>getId<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>	
	<span style='color:#800080; '>}</span>
<span style='color:#800080; '>}</span>
</pre>
</P>
<p> The question in the above example, can you tell how many times @before method and @after method will be execute? The answer is only once. 
Thats all for parallelism. 