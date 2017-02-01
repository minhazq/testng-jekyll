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
<li> 2. @Test(dependsOnGroups={"group-name-defined-in-xml"}</li>
