---
title: "@Factory in TestNG"
date: 2017-01-30 22:41:00 -05:00
---

@Factory annotation is used to execute same set of methods execute with different data. Lets say i have a Script that printouts numbers with different set of numbers. So i need to run this same script with different parameter. One way you can use dataprovider and return Object[][] of the dataprovider method , based on how many data are there , it will execute. 2nd Option is use @Factory.
<pre style='color:#000000;background:#ffffff;'><span style='color:#800000; font-weight:bold; '>package</span><span style='color:#004a43; '> mq</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>demo</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>selenium_testng</span><span style='color:#800080; '>;</span>

<span style='color:#800000; font-weight:bold; '>import</span><span style='color:#004a43; '> org</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>testng</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>annotations</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>Test</span><span style='color:#800080; '>;</span>

<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#800000; font-weight:bold; '>class</span> Script01 <span style='color:#800080; '>{</span>

	<span style='color:#800000; font-weight:bold; '>private</span> <span style='color:#bb7977; '>int</span> number <span style='color:#808030; '>=</span> <span style='color:#008c00; '>0</span><span style='color:#800080; '>;</span>
	
	<span style='color:#800000; font-weight:bold; '>public</span> Script01<span style='color:#808030; '>(</span><span style='color:#bb7977; '>int</span> number<span style='color:#808030; '>)</span> <span style='color:#800080; '>{</span>
		<span style='color:#800000; font-weight:bold; '>this</span><span style='color:#808030; '>.</span>number <span style='color:#808030; '>=</span> number<span style='color:#800080; '>;</span>
	<span style='color:#800080; '>}</span>
	
	<span style='color:#808030; '>@</span>Test
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> m1<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		<span style='color:#bb7977; font-weight:bold; '>System</span><span style='color:#808030; '>.</span>out<span style='color:#808030; '>.</span>println<span style='color:#808030; '>(</span><span style='color:#0000e6; '>"The number is "</span><span style='color:#808030; '>+</span>number<span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>
	<span style='color:#800080; '>}</span>
<span style='color:#800080; '>}</span>
</pre> 
To use @Factory you have to do the following: 
<ul>
<li> Create a separate Class</li>
<li> Create a method which has a return of Object[]. Create new instance of your Script class with different parameter .
</ul>