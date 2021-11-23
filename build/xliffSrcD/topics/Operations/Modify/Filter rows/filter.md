<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="filter" title="filter" _md-based="true"> 
<p _o="92" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="1fd7f9f7">Returns <code _o="100" _o-sc="4,9" _o-l="4" _o-e="4,19" _o-tl="-1" _o-s="4,8" _o-cl="8" id="afe10bdc">DataFrame</code> with rows that satisfy <a _o="135" _o-sc="4,44" LinkStatus="UNKNOWN" _o-l="4" _o-e="4,85" _o-tl="-1" _o-s="4,43" href="DataRow.md#row-conditions" _o-cl="43" id="69990010">row condition</a></p>

<tabs id="85b2ab9c">
<tab id="10828b22" title="Properties">
<code _o="231" _o-sc="11,0" _o-l="10" _o-e="12,3" _o-tl="26" _o-s="10,0" style="block" _o-cl="0" id="a26c78df" lang="kotlin">df.filter { age > 18 &amp;&amp; name.firstName.startsWith("A") }
</code>
</tab>
<tab _o="303" _o-sc="14,6" _o-l="14" _o-e="16,0" _o-tl="5" _o-s="14,0" _o-cl="0" id="600fe5a3" title="Accessors">
<code _o="335" _o-sc="18,0" _o-l="17" _o-e="25,3" _o-tl="31" _o-s="17,0" style="block" _o-cl="0" id="261bec0c" lang="kotlin">val age by column&lt;Int>()
val name by columnGroup()
val firstName by name.column&lt;String>()

df.filter { age() > 18 &amp;&amp; firstName().startsWith("A") }
// or
df.filter { it[age] > 18 &amp;&amp; it[firstName].startsWith("A") }
</code>
</tab>
<tab _o="563" _o-sc="27,6" _o-l="27" _o-e="29,0" _o-tl="5" _o-s="27,0" _o-cl="0" id="af70e3b" title="Strings">
<code _o="593" _o-sc="31,0" _o-l="30" _o-e="32,3" _o-tl="31" _o-s="30,0" style="block" _o-cl="0" id="f185c1d7" lang="kotlin">df.filter { "age"&lt;Int>() > 18 &amp;&amp; "name"["firstName"]&lt;String>().startsWith("A") }
</code>
</tab></tabs>

<chapter _o="716" _o-sc="37,3" _o-l="37" _o-e="37,11" _o-tl="-1" _o-s="37,0" _o-cl="0" id="filterby" title="filterBy">
<p _o="729" _o-sc="39,0" _o-l="39" _o-e="40,0" _o-tl="-1" _o-s="39,0" _o-cl="0" id="81f8d6d">Returns <code _o="737" _o-sc="39,9" _o-l="39" _o-e="39,19" _o-tl="-1" _o-s="39,8" _o-cl="8" id="29aef525">DataFrame</code> with rows that have value <code _o="775" _o-sc="39,47" _o-l="39" _o-e="39,52" _o-tl="-1" _o-s="39,46" _o-cl="46" id="840588c3">true</code> in given column of type <code _o="806" _o-sc="39,78" _o-l="39" _o-e="39,86" _o-tl="-1" _o-s="39,77" _o-cl="77" id="4178871e">Boolean</code>.</p>

<tabs id="c615278f">
<tab id="e2dc41f1" title="Properties">
<code _o="872" _o-sc="46,0" _o-l="45" _o-e="47,3" _o-tl="-1" _o-s="45,0" style="block" _o-cl="0" id="fc72b50f" lang="kotlin">df.filterBy { isHappy }
</code>
</tab>
<tab _o="911" _o-sc="49,6" _o-l="49" _o-e="51,0" _o-tl="5" _o-s="49,0" _o-cl="0" id="62a01075" title="Accessors">
<code _o="943" _o-sc="53,0" _o-l="52" _o-e="55,3" _o-tl="39" _o-s="52,0" style="block" _o-cl="0" id="5f21e60d" lang="kotlin">val isHappy by column&lt;Boolean>()
df.filterBy { isHappy }
</code>
</tab>
<tab _o="1015" _o-sc="57,6" _o-l="57" _o-e="59,0" _o-tl="5" _o-s="57,0" _o-cl="0" id="7a5d59bb" title="Strings">
<code _o="1045" _o-sc="61,0" _o-l="60" _o-e="62,3" _o-tl="-1" _o-s="60,0" style="block" _o-cl="0" id="e4f5b86b" lang="kotlin">df.filterBy("isHappy")
</code>
</tab></tabs>

</chapter></topic>