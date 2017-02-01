---
title: How to execute Test depends on Other test
date: 2017-02-01 11:54:00 -05:00
---

This called Test Dependency. We need to know following:
<ul>
<li>Writing a dependency test single/multiple</li>
<li>Use regular expression for Dependency</li>
<li>Define Dependency through XML</li>
</ul>
**T**he Important part to now that Method dependency **only works** if the dependent methods are in the same class or inherited class. Now how will you do if you need a test depends on another test that exists in different class? You simply can achieve that by "dependsOnGroups" attribute of @Test annotation. So For dependency there is mainly two attribute exists for scripts ( not xml). 
<li> 1. @Test(dependsOnMethods={"methodName"})</li>
<li> 2. @Test(dependsOnGroups={"group-name-defined-in-xml"})</li>
Here is the example for Methods dependency with the same or inherited class.
<pre style='color:#000000;background:#ffffff;'><span style='color:#800000; font-weight:bold; '>package</span><span style='color:#004a43; '> mq</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>demo</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>selenium</span><span style='color:#800080; '>;</span>
<span style='color:#800000; font-weight:bold; '>import</span><span style='color:#004a43; '> org</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>testng</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>annotations</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>Test</span><span style='color:#800080; '>;</span>

<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#800000; font-weight:bold; '>class</span> AppTest <span style='color:#800000; font-weight:bold; '>extends</span> Scriptbase <span style='color:#800080; '>{</span>
	
	<span style='color:#808030; '>@</span>Test<span style='color:#808030; '>(</span>dependsOnMethods<span style='color:#808030; '>=</span><span style='color:#800080; '>{</span><span style='color:#0000e6; '>"m2"</span><span style='color:#800080; '>}</span><span style='color:#808030; '>)</span>
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> m1<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		<span style='color:#bb7977; font-weight:bold; '>System</span><span style='color:#808030; '>.</span>out<span style='color:#808030; '>.</span>println<span style='color:#808030; '>(</span><span style='color:#0000e6; '>"This is m1"</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>
	<span style='color:#800080; '>}</span>
	
	<span style='color:#808030; '>@</span>Test
	<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> m2<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
		<span style='color:#bb7977; font-weight:bold; '>System</span><span style='color:#808030; '>.</span>out<span style='color:#808030; '>.</span>println<span style='color:#808030; '>(</span><span style='color:#0000e6; '>"This is m2"</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>
	<span style='color:#800080; '>}</span>

		
<span style='color:#800080; '>}</span>
</pre>

Here is the example if the methods exist in different class. Assume i have declared groups in the xml like this:

