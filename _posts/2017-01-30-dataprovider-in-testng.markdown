---
title: DataProvider in TestNG
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
 