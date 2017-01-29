---
title: Assertion with TestNG
date: 2017-01-29 11:25:00 -05:00
---

All assert is the part of **org.testng.Assert** class. All assert will throw an **java.lang.AssertionError**. We can verify the following using one override methods "assertEqual(data,data,String fail message)".
<p><li>

1. All primitive

2. String

3. array

4. Collections

5. Iterable object

6. boolean </li></P>
<p>
<pre style='color:#000000;background:#ffffff;'><span style='color:#800000; font-weight:bold; '>package</span><span style='color:#004a43; '> mq</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>demo</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>selenium</span><span style='color:#800080; '>;</span>
   <span style='color:#800000; font-weight:bold; '>import</span><span style='color:#004a43; '> org</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>testng</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>Assert</span><span style='color:#800080; '>;</span>
   <span style='color:#800000; font-weight:bold; '>import</span><span style='color:#004a43; '> org</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>testng</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>annotations</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>Test</span><span style='color:#800080; '>;</span>
   <span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#800000; font-weight:bold; '>class</span> AppTest <span style='color:#800080; '>{</span>

   <span style='color:#808030; '>@</span>Test
   <span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> before<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
   Assert<span style='color:#808030; '>.</span>assertEquals<span style='color:#808030; '>(</span><span style='color:#800000; font-weight:bold; '>true</span><span style='color:#808030; '>,</span><span style='color:#800000; font-weight:bold; '>false</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>
   <span style='color:#696969; '>//**special**</span>
   Assert<span style='color:#808030; '>.</span>assertEquals<span style='color:#808030; '>(</span><span style='color:#800000; font-weight:bold; '>true</span><span style='color:#808030; '>,</span><span style='color:#800000; font-weight:bold; '>false</span><span style='color:#808030; '>,</span><span style='color:#0000e6; '>"This is fail message"</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>
   <span style='color:#696969; '>// The above is Not only boolean you can send all primitive type. It has lot of override methods.</span>
   <span style='color:#696969; '>// You can also send Iterable object. Asserts that two iterables return iterators with the same elements in the same order. </span>
   <span style='color:#696969; '>//If they do not, an AssertionError, with the given message, is thrown. There is a override methods for collection as well.</span>
   <span style='color:#696969; '>//**End special**</span>

        Assert<span style='color:#808030; '>.</span>assertEquals<span style='color:#808030; '>(</span><span style='color:#0000e6; '>"actual"</span><span style='color:#808030; '>,</span><span style='color:#0000e6; '>"expected"</span><span style='color:#808030; '>,</span><span style='color:#0000e6; '>"fail message"</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>
        Assert<span style='color:#808030; '>.</span>assertTrue<span style='color:#808030; '>(</span><span style='color:#800000; font-weight:bold; '>true</span><span style='color:#808030; '>,</span><span style='color:#0000e6; '>"this is fail message"</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span><span style='color:#696969; '>// in this case you will send a condtion if it is true then pass else fail</span>
        Assert<span style='color:#808030; '>.</span>assertFalse<span style='color:#808030; '>(</span><span style='color:#800000; font-weight:bold; '>false</span><span style='color:#808030; '>,</span><span style='color:#0000e6; '>"This is fail message"</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span><span style='color:#696969; '>// in this case you will send a condtion if it is false then pass else fail</span>
        Assert<span style='color:#808030; '>.</span>fail<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span><span style='color:#696969; '>// directly fail the test</span>

   <span style='color:#800080; '>}</span>

<span style='color:#800080; '>}</span>
</pre>
</P>
The above is called **Hard Assert**. Meaning it will throws an exception and also terminate the execution of the test. In some case you need to keep going. In that case you need use **<u>org.testng.asserts.SoftAssert</u>**. In order to create an instance of soft assert you have to do the following:
<p>
<pre style='color:#000000;background:#ffffff;'><span style='color:#800000; font-weight:bold; '>package</span><span style='color:#004a43; '> mq</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>demo</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>selenium</span><span style='color:#800080; '>;</span>
<span style='color:#800000; font-weight:bold; '>import</span><span style='color:#004a43; '> org</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>testng</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>annotations</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>Test</span><span style='color:#800080; '>;</span>
<span style='color:#800000; font-weight:bold; '>import</span><span style='color:#004a43; '> org</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>testng</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>asserts</span><span style='color:#808030; '>.</span><span style='color:#004a43; '>SoftAssert</span><span style='color:#800080; '>;</span>
<span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#800000; font-weight:bold; '>class</span> AppTest <span style='color:#800080; '>{</span>

    <span style='color:#808030; '>@</span>Test
    <span style='color:#800000; font-weight:bold; '>public</span> <span style='color:#bb7977; '>void</span> before<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>{</span>
        SoftAssert softAssert <span style='color:#808030; '>=</span> <span style='color:#800000; font-weight:bold; '>new</span> SoftAssert<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>
        
        softAssert<span style='color:#808030; '>.</span>assertEquals<span style='color:#808030; '>(</span><span style='color:#800000; font-weight:bold; '>true</span><span style='color:#808030; '>,</span><span style='color:#800000; font-weight:bold; '>true</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>
        softAssert<span style='color:#808030; '>.</span>assertEquals<span style='color:#808030; '>(</span><span style='color:#0000e6; '>"test1"</span><span style='color:#808030; '>,</span><span style='color:#0000e6; '>"test2"</span><span style='color:#808030; '>,</span><span style='color:#0000e6; '>"Test is failed"</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span>
        
        <span style='color:#696969; '>//**Verify Important Part***</span>
        softAssert<span style='color:#808030; '>.</span>assertAll<span style='color:#808030; '>(</span><span style='color:#808030; '>)</span><span style='color:#800080; '>;</span><span style='color:#696969; '>// This code will collect all the assert result and will be invoke</span>
        <span style='color:#696969; '>//at the end of the scripts </span>
        
    <span style='color:#800080; '>}</span>

<span style='color:#800080; '>}</span>
</pre>
</P>
**<u>How will you implement Assert to your Scripts through out the project? </u>**
The main idea is i can use Hard Assert and catch the exception or i can use Soft Assert and call **assertAll()** at the end.
