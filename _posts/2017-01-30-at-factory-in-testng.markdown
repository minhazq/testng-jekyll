---
title: "@Factory in TestNG"
date: 2017-01-30 22:41:00 -05:00
---

@Factory annotation is used to execute same set of methods execute with different data.
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