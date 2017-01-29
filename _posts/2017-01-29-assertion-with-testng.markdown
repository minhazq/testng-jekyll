---
title: Assertion with TestNG
date: 2017-01-29 11:25:00 -05:00
---

All assert is the part of **org.testng.Assert** class. The **assertEquals()** will throw an **java.lang.AssertionError**.
<p>
<pre style='color:#000000;background:#ffffff;'><span style='color:#800000; font-weight:bold; '>package</span><span style='color:#004a43; '> mq</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>demo</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>selenium</span><span style='color:#800080; '>;</span>
<span style='color:#800000; font-weight:bold; '>import</span><span style='color:#004a43; '> org</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>testng</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>Assert</span><span style='color:#800080; '>;</span>
<span style='color:#800000; font-weight:bold; '>import</span><span style='color:#004a43; '> org</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>testng</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>annotations</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>Test</span><span style='color:#800080; '>;</span>
<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#800000; font-weight:bold; '>class</span> AppTest <span style='color:#800080; '>{</span>

	<span style='color:#808030; '>@</span>Test
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> before<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		Assert<span style='color:#808030; '>.</span>assertEquals<span style='color:#808030; '>(</span><span style='color:#800000; font-weight:bold; '>true</span><span style='color:#808030; '>,</span><span style='color:#800000; font-weight:bold; '>false</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>	
	<span style='color:#800080; '>}</span>
	
	
<span style='color:#800080; '>}</span>
</pre>
</P>
