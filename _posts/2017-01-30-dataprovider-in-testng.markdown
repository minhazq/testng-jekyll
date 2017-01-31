---
title: "@DataProvider in TestNG"
date: 2017-01-30 16:28:00 -05:00
---

Basically you can provide data in two ways. You can create a method and add @DataProvider on the top of it or you can create a separate class and create a method and add @DataProvider on the top of that method ( Notice not class). There is three following alert for any approach:
<p> You must decleare that method as <b>static</b></p>
<p> You must add @Dataprovider annotation at the top of the method</p>
<p> You must provide the name of the dataProvider.</p>
In the case of Class level DataProvider you must add "dataProviderClass=yourClass.class" in the attribute of @Test of your test method. For example:
<pre style='color:#000000;background:#ffffff;'>@Test(dataProvider="my-data-provider", dataProviderClass=DataproviderClass.class)
	<span style='color:#800000; font-weight:bold; '>public</span> void test01(String data)<span style='color:#800080; '>{</span>
		<span style='color:#bb7977; font-weight:bold; '>System</span><span style='color:#808030; '>.</span>out<span style='color:#808030; '>.</span>println<span style='color:#808030; '>(</span>data<span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>
		
	<span style='color:#800080; '>}</span>
</pre>
Here is the example for DataProvider Class:
<pre style='color:#000000;background:#ffffff;'><span style='color:#800000; font-weight:bold; '>package</span><span style='color:#004a43; '> mq</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>demo</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>selenium</span><span style='color:#800080; '>;</span>

<span style='color:#800000; font-weight:bold; '>import</span><span style='color:#004a43; '> org</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>testng</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>annotations</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>DataProvider</span><span style='color:#800080; '>;</span>

<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#800000; font-weight:bold; '>class</span> DataproviderClass <span style='color:#800080; '>{</span>

	
	<span style='color:#696969; '>//Has to be delceared as static and must return and two dimensional array</span>
		<span style='color:#808030; '>@</span>DataProvider<span style='color:#808030; '>(</span>name<span style='color:#808030; '>=</span><span style='color:#0000e6; '>"my-data-provider"</span><span style='color:#808030; '>)</span>
		<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#800000; font-weight:bold; '>static</span> <span style='color:#bb7977; font-weight:bold; '>Object</span><span style='color:#808030; '>[</span><span style='color:#808030; '>]</span><span style='color:#808030; '>[</span><span style='color:#808030; '>]</span> dataProviderMethod<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
			<span style='color:#800000; font-weight:bold; '>return</span> <span style='color:#800000; font-weight:bold; '>new</span> <span style='color:#bb7977; font-weight:bold; '>Object</span><span style='color:#808030; '>[</span><span style='color:#808030; '>]</span><span style='color:#808030; '>[</span><span style='color:#808030; '>]</span> <span style='color:#800080; '>{</span><span style='color:#800080; '>{</span><span style='color:#0000e6; '>"data One"</span><span style='color:#800080; '>}</span><span style='color:#808030; '>,</span><span style='color:#800080; '>{</span><span style='color:#0000e6; '>"data two"</span><span style='color:#800080; '>}</span><span style='color:#800080; '>}</span><span style='color:#800080; '>;</span>	
		<span style='color:#800080; '>}</span>
		
		
<span style='color:#800080; '>}</span>
</pre>
 