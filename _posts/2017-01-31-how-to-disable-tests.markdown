---
title: How to Disable Tests
date: 2017-01-31 22:16:00 -05:00
---

In order to disable Test you have to do it using annotation in the script class. You can annotate in the method or you can annotate in the class level. If you do it in class level all the **public** method will not be part of the execution. Here is the example for method level:
<pre style='color:#000000;background:#ffffff;'><span style='color:#800000; font-weight:bold; '>package</span><span style='color:#004a43; '> mq</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>demo</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>selenium</span><span style='color:#800080; '>;</span>
<span style='color:#800000; font-weight:bold; '>import</span><span style='color:#004a43; '> org</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>testng</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>annotations</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>Test</span><span style='color:#800080; '>;</span>
<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#800000; font-weight:bold; '>class</span> AppTest <span style='color:#800000; font-weight:bold; '>extends</span> Scriptbase <span style='color:#800080; '>{</span>

	
	<span style='color:#808030; '>@</span>Test<span style='color:#808030; '>(</span>enabled <span style='color:#808030; '>=</span><span style='color:#800000; font-weight:bold; '>true</span><span style='color:#808030; '>)</span>
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> m1<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		
	<span style='color:#800080; '>}</span>

	<span style='color:#808030; '>@</span>Test<span style='color:#808030; '>(</span>enabled<span style='color:#808030; '>=</span><span style='color:#800000; font-weight:bold; '>false</span><span style='color:#808030; '>)</span>
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> m2<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		
	<span style='color:#800080; '>}</span>

	<span style='color:#808030; '>@</span>Test<span style='color:#808030; '>(</span>enabled<span style='color:#808030; '>=</span><span style='color:#800000; font-weight:bold; '>true</span><span style='color:#808030; '>)</span>
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> m3<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		
	<span style='color:#800080; '>}</span>

	<span style='color:#808030; '>@</span>Test<span style='color:#808030; '>(</span>enabled<span style='color:#808030; '>=</span><span style='color:#800000; font-weight:bold; '>true</span><span style='color:#808030; '>)</span>
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> m4<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		
	<span style='color:#800080; '>}</span>
		
<span style='color:#800080; '>}</span>
</pre>
Here is the example for Class level:
<pre style='color:#000000;background:#ffffff;'><span style='color:#800000; font-weight:bold; '>package</span><span style='color:#004a43; '> mq</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>demo</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>selenium</span><span style='color:#800080; '>;</span>
<span style='color:#800000; font-weight:bold; '>import</span><span style='color:#004a43; '> org</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>testng</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>annotations</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>Test</span><span style='color:#800080; '>;</span>

@Test(enabled=true)
<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#800000; font-weight:bold; '>class</span> AppTest <span style='color:#800000; font-weight:bold; '>extends</span> Scriptbase <span style='color:#800080; '>{</span>
	
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> m1<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		
	<span style='color:#800080; '>}</span>

	
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> m2<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		
	<span style='color:#800080; '>}</span>

	
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> m3<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		
	<span style='color:#800080; '>}</span>

	
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> m4<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		
	<span style='color:#800080; '>}</span>
		
<span style='color:#800080; '>}</span>
</pre>