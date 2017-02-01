---
title: How to execute Tests in a group
date: 2017-01-31 22:25:00 -05:00
---

You can do the following:
<ul>
<li>Running Test in a group</li>
<li>Including/Excluding group</li>
<li>Using Regular Expression in group to include/exclude</li>
<li>Group of groups</li>
</ul>
Let's begin how to do grouping. You can use **groups** parameter in the @Test annotation to include that Test method belongs to a group. So whenever you execute only that group it will run.
<pre style='color:#000000;background:#ffffff;'><span style='color:#800000; font-weight:bold; '>package</span><span style='color:#004a43; '> mq</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>demo</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>selenium</span><span style='color:#800080; '>;</span>
<span style='color:#800000; font-weight:bold; '>import</span><span style='color:#004a43; '> org</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>testng</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>annotations</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>Test</span><span style='color:#800080; '>;</span>

<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#800000; font-weight:bold; '>class</span> AppTest <span style='color:#800000; font-weight:bold; '>extends</span> Scriptbase <span style='color:#800080; '>{</span>
	
	<span style='color:#808030; '>@</span>Test<span style='color:#808030; '>(</span>groups<span style='color:#808030; '>=</span><span style='color:#0000e6; '>"qa"</span><span style='color:#808030; '>)</span>
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> m1<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		<span style='color:#bb7977; font-weight:bold; '>System</span><span style='color:#808030; '>.</span>out<span style='color:#808030; '>.</span>println<span style='color:#808030; '>(</span><span style='color:#0000e6; '>"This is qa"</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>
	<span style='color:#800080; '>}</span>

	<span style='color:#808030; '>@</span>Test<span style='color:#808030; '>(</span>groups<span style='color:#808030; '>=</span><span style='color:#0000e6; '>"prod"</span><span style='color:#808030; '>)</span>
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> m2<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		<span style='color:#bb7977; font-weight:bold; '>System</span><span style='color:#808030; '>.</span>out<span style='color:#808030; '>.</span>println<span style='color:#808030; '>(</span><span style='color:#0000e6; '>"This is prod"</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>
	<span style='color:#800080; '>}</span>
	
	<span style='color:#808030; '>@</span>Test
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> m3<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		<span style='color:#bb7977; font-weight:bold; '>System</span><span style='color:#808030; '>.</span>out<span style='color:#808030; '>.</span>println<span style='color:#808030; '>(</span><span style='color:#0000e6; '>"This is no group"</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>
	<span style='color:#800080; '>}</span>
		
<span style='color:#800080; '>}</span>
</pre>
I have declared 2 groups and 1 no group( or default). Now how to run them? They way you can run from the eclipse just create a new configuration for execution and select group and then brows group and you will see your group is in the option and select which group you want to run and then run.
<p>If you want to run using XML then you have to add "groups" tag right after "suite" tag declaration and inside the groups tag you add "run" tag and inside the run tag you add "include" tag. See there is no tag saying group. instead of group it says run. </p>
<pre style='color:#000000;background:#ffffff;'><span style='color:#004a43; '>&lt;!</span><span style='color:#800000; font-weight:bold; '>DOCTYPE</span> <span style='color:#bb7977; font-weight:bold; '>suite</span> <span style='color:#004a43; '>SYSTEM</span> <span style='color:#800000; '>"</span><span style='color:#666616; '>http</span><span style='color:#800080; '>:</span><span style='color:#800000; font-weight:bold; '>//</span><span style='color:#5555dd; '>testng.org</span><span style='color:#40015a; '>/testng-1.0.dtd</span><span style='color:#800000; '>"</span><span style='color:#004a43; '>></span>
<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>suite</span> <span style='color:#274796; '>name</span> <span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>My sutie</span><span style='color:#800000; '>"</span>  <span style='color:#a65700; '>></span>
<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>groups</span><span style='color:#a65700; '>></span>
<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>run</span><span style='color:#a65700; '>></span>
	<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>include</span> <span style='color:#274796; '>name</span><span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>prod</span><span style='color:#800000; '>"</span><span style='color:#a65700; '>></span><span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>include</span><span style='color:#a65700; '>></span>
<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>run</span><span style='color:#a65700; '>></span>
<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>groups</span><span style='color:#a65700; '>></span>
	<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>test</span> <span style='color:#274796; '>name</span> <span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>My Test</span><span style='color:#800000; '>"</span> <span style='color:#a65700; '>></span>
  		<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>classes</span><span style='color:#a65700; '>></span>
			<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>class</span> <span style='color:#274796; '>name</span><span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>mq.demo.selenium.AppTest</span><span style='color:#800000; '>"</span><span style='color:#a65700; '>/></span>
		<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>classes</span><span style='color:#a65700; '>></span>
	<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>test</span><span style='color:#a65700; '>></span>
<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>suite</span><span style='color:#a65700; '>></span>
</pre>
How to include a test method to multiple groups? You just send a group of names as an array to the @Test notation.
<pre style='color:#000000;background:#ffffff;'><span style='color:#800000; font-weight:bold; '>package</span><span style='color:#004a43; '> mq</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>demo</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>selenium</span><span style='color:#800080; '>;</span>
<span style='color:#800000; font-weight:bold; '>import</span><span style='color:#004a43; '> org</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>testng</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>annotations</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>Test</span><span style='color:#800080; '>;</span>

<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#800000; font-weight:bold; '>class</span> AppTest <span style='color:#800000; font-weight:bold; '>extends</span> Scriptbase <span style='color:#800080; '>{</span>
	
	<span style='color:#808030; '>@</span>Test<span style='color:#808030; '>(</span>groups<span style='color:#808030; '>=</span><span style='color:#800080; '>{</span><span style='color:#0000e6; '>"qa"</span><span style='color:#808030; '>,</span><span style='color:#0000e6; '>"prod"</span><span style='color:#808030; '>,</span><span style='color:#0000e6; '>"staging"</span><span style='color:#808030; '>,</span><span style='color:#0000e6; '>"dev"</span><span style='color:#800080; '>}</span><span style='color:#808030; '>)</span>
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> m1<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		<span style='color:#bb7977; font-weight:bold; '>System</span><span style='color:#808030; '>.</span>out<span style='color:#808030; '>.</span>println<span style='color:#808030; '>(</span><span style='color:#0000e6; '>"This is qa prod staging dev"</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>
	<span style='color:#800080; '>}</span>

	<span style='color:#808030; '>@</span>Test
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> m3<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		<span style='color:#bb7977; font-weight:bold; '>System</span><span style='color:#808030; '>.</span>out<span style='color:#808030; '>.</span>println<span style='color:#808030; '>(</span><span style='color:#0000e6; '>"This is no group"</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>
	<span style='color:#800080; '>}</span>
		
<span style='color:#800080; '>}</span>
</pre>
Now how to run them? This time your group tag will go inside the "Test" tag instead of going right after "suite" tag.
<pre style='color:#000000;background:#ffffff;'><span style='color:#004a43; '>&lt;!</span><span style='color:#800000; font-weight:bold; '>DOCTYPE</span> <span style='color:#bb7977; font-weight:bold; '>suite</span> <span style='color:#004a43; '>SYSTEM</span> <span style='color:#800000; '>"</span><span style='color:#666616; '>http</span><span style='color:#800080; '>:</span><span style='color:#800000; font-weight:bold; '>//</span><span style='color:#5555dd; '>testng.org</span><span style='color:#40015a; '>/testng-1.0.dtd</span><span style='color:#800000; '>"</span><span style='color:#004a43; '>></span>
<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>suite</span> <span style='color:#274796; '>name</span> <span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>My sutie</span><span style='color:#800000; '>"</span>  <span style='color:#a65700; '>></span>

<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>test</span> <span style='color:#274796; '>name</span> <span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>My Test1</span><span style='color:#800000; '>"</span> <span style='color:#a65700; '>></span>
	<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>groups</span><span style='color:#a65700; '>></span>
		<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>run</span><span style='color:#a65700; '>></span>
			<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>include</span> <span style='color:#274796; '>name</span><span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>prod</span><span style='color:#800000; '>"</span><span style='color:#a65700; '>></span><span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>include</span><span style='color:#a65700; '>></span>
		<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>run</span><span style='color:#a65700; '>></span>
	<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>groups</span><span style='color:#a65700; '>></span>
 <span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>classes</span><span style='color:#a65700; '>></span>
	<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>class</span> <span style='color:#274796; '>name</span><span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>mq.demo.selenium.AppTest</span><span style='color:#800000; '>"</span><span style='color:#a65700; '>/></span>
 <span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>classes</span><span style='color:#a65700; '>></span>
<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>test</span><span style='color:#a65700; '>></span>

<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>test</span> <span style='color:#274796; '>name</span> <span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>My Test2</span><span style='color:#800000; '>"</span> <span style='color:#a65700; '>></span>
	<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>groups</span><span style='color:#a65700; '>></span>
		<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>run</span><span style='color:#a65700; '>></span>
			<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>include</span> <span style='color:#274796; '>name</span><span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>qa</span><span style='color:#800000; '>"</span><span style='color:#a65700; '>></span><span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>include</span><span style='color:#a65700; '>></span>
		<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>run</span><span style='color:#a65700; '>></span>
	<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>groups</span><span style='color:#a65700; '>></span>
 <span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>classes</span><span style='color:#a65700; '>></span>
	<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>class</span> <span style='color:#274796; '>name</span><span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>mq.demo.selenium.AppTest</span><span style='color:#800000; '>"</span><span style='color:#a65700; '>/></span>
 <span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>classes</span><span style='color:#a65700; '>></span>
<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>test</span><span style='color:#a65700; '>></span>
<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>suite</span><span style='color:#a65700; '>></span>
</pre>
How to Exclude a group? As you imagine simply instead of include tag add "exclude" tag. Here is the example:
<pre style='color:#000000;background:#ffffff;'><span style='color:#004a43; '>&lt;!</span><span style='color:#800000; font-weight:bold; '>DOCTYPE</span> <span style='color:#bb7977; font-weight:bold; '>suite</span> <span style='color:#004a43; '>SYSTEM</span> <span style='color:#800000; '>"</span><span style='color:#666616; '>http</span><span style='color:#800080; '>:</span><span style='color:#800000; font-weight:bold; '>//</span><span style='color:#5555dd; '>testng.org</span><span style='color:#40015a; '>/testng-1.0.dtd</span><span style='color:#800000; '>"</span><span style='color:#004a43; '>></span>
<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>suite</span> <span style='color:#274796; '>name</span> <span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>My sutie</span><span style='color:#800000; '>"</span>  <span style='color:#a65700; '>></span>

<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>test</span> <span style='color:#274796; '>name</span> <span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>My Test1</span><span style='color:#800000; '>"</span> <span style='color:#a65700; '>></span>
	<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>groups</span><span style='color:#a65700; '>></span>
		<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>run</span><span style='color:#a65700; '>></span>
			<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>include</span> <span style='color:#274796; '>name</span><span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>prod</span><span style='color:#800000; '>"</span><span style='color:#a65700; '>></span><span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>include</span><span style='color:#a65700; '>></span>
			<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>exclude</span> <span style='color:#274796; '>name</span><span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>qa</span><span style='color:#800000; '>"</span><span style='color:#a65700; '>></span><span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>exclude</span><span style='color:#a65700; '>></span>
		<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>run</span><span style='color:#a65700; '>></span>
	<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>groups</span><span style='color:#a65700; '>></span>
 <span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>classes</span><span style='color:#a65700; '>></span>
	<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>class</span> <span style='color:#274796; '>name</span><span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>mq.demo.selenium.AppTest</span><span style='color:#800000; '>"</span><span style='color:#a65700; '>/></span>
 <span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>classes</span><span style='color:#a65700; '>></span>
<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>test</span><span style='color:#a65700; '>></span>

<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>test</span> <span style='color:#274796; '>name</span> <span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>My Test2</span><span style='color:#800000; '>"</span> <span style='color:#a65700; '>></span>
	<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>groups</span><span style='color:#a65700; '>></span>
		<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>run</span><span style='color:#a65700; '>></span>
			<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>include</span> <span style='color:#274796; '>name</span><span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>qa</span><span style='color:#800000; '>"</span><span style='color:#a65700; '>></span><span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>include</span><span style='color:#a65700; '>></span>
		<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>run</span><span style='color:#a65700; '>></span>
	<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>groups</span><span style='color:#a65700; '>></span>
 <span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>classes</span><span style='color:#a65700; '>></span>
	<span style='color:#a65700; '>&lt;</span><span style='color:#5f5035; '>class</span> <span style='color:#274796; '>name</span><span style='color:#808030; '>=</span><span style='color:#800000; '>"</span><span style='color:#0000e6; '>mq.demo.selenium.AppTest</span><span style='color:#800000; '>"</span><span style='color:#a65700; '>/></span>
 <span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>classes</span><span style='color:#a65700; '>></span>
<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>test</span><span style='color:#a65700; '>></span>
<span style='color:#a65700; '>&lt;/</span><span style='color:#5f5035; '>suite</span><span style='color:#a65700; '>></span>
</pre>
How to use **Regular Expression** ? Verify verify simple. Inside the include or exclude name attribute you do just **.*** 