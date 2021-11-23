<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="distinct" title="distinct" _md-based="true"> 
<p _o="94" _o-sc="4,0" _o-l="4" _o-e="6,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="f83f4d20">Removes duplicate rows.
The rows in the resulting <code _o="144" _o-sc="5,27" _o-l="5" _o-e="5,37" _o-tl="-1" _o-s="5,26" _o-cl="26" id="edecb436">DataFrame</code> are in the same order as they were in the original <code _o="207" _o-sc="5,90" _o-l="5" _o-e="5,100" _o-tl="-1" _o-s="5,89" _o-cl="89" id="60de301e">DataFrame</code>.</p>

<code _o="243" _o-sc="10,0" _o-l="9" _o-e="11,3" _o-tl="-1" _o-s="9,0" style="block" _o-cl="0" id="4c819ecd" lang="kotlin">df.distinct()
</code>

<p _o="285" _o-sc="15,0" _o-l="15" _o-e="16,0" _o-tl="-1" _o-s="15,0" _o-cl="0" id="4fa02eee">If columns are specified, resulting <code _o="321" _o-sc="15,37" _o-l="15" _o-e="15,47" _o-tl="-1" _o-s="15,36" _o-cl="36" id="c8df79b8">DataFrame</code> will have only given columns with distinct values.</p>

<tabs id="1605aae1">
<tab id="c04a0464" title="Properties">
<code _o="446" _o-sc="22,0" _o-l="21" _o-e="25,3" _o-tl="-1" _o-s="21,0" style="block" _o-cl="0" id="4ecd64dd" lang="kotlin">df.distinct { age and name }
// same as
df.select { age and name }.distinct()
</code>
</tab>
<tab _o="539" _o-sc="27,6" _o-l="27" _o-e="29,0" _o-tl="5" _o-s="27,0" _o-cl="0" id="5e350abc" title="Accessors">
<code _o="571" _o-sc="31,0" _o-l="30" _o-e="36,3" _o-tl="31" _o-s="30,0" style="block" _o-cl="0" id="764816f9" lang="kotlin">val age by column&lt;Int>()
val name by columnGroup()
df.distinct { age and name }
// same as
df.select { age and name }.distinct()
</code>
</tab>
<tab _o="715" _o-sc="38,6" _o-l="38" _o-e="40,0" _o-tl="5" _o-s="38,0" _o-cl="0" id="e5ea01c6" title="Strings">
<code _o="745" _o-sc="42,0" _o-l="41" _o-e="45,3" _o-tl="-1" _o-s="41,0" style="block" _o-cl="0" id="f43ffb18" lang="kotlin">df.distinct("age", "name")
// same as
df.select("age", "name").distinct()
</code>
</tab></tabs>

<chapter _o="861" _o-sc="50,3" _o-l="50" _o-e="50,13" _o-tl="-1" _o-s="50,0" _o-cl="0" id="distinctby" title="distinctBy">
<p _o="876" _o-sc="52,0" _o-l="52" _o-e="53,0" _o-tl="-1" _o-s="52,0" _o-cl="0" id="c2e4a236">Keep only the first row for every group of rows grouped by some condition.</p>

<tabs id="8400c70e">
<tab id="41d74f9c" title="Properties">
<code _o="1008" _o-sc="59,0" _o-l="58" _o-e="62,3" _o-tl="-1" _o-s="58,0" style="block" _o-cl="0" id="50295a6e" lang="kotlin">df.distinctBy { age and name }
// same as
df.groupBy { age and name }.mapToRows { group.first() }
</code>
</tab>
<tab _o="1121" _o-sc="64,6" _o-l="64" _o-e="66,0" _o-tl="5" _o-s="64,0" _o-cl="0" id="4514b49a" title="Accessors">
<code _o="1153" _o-sc="68,0" _o-l="67" _o-e="75,3" _o-tl="31" _o-s="67,0" style="block" _o-cl="0" id="79c7957a" lang="kotlin">val age by column&lt;Int>()
val name by columnGroup()
val firstName by name.column&lt;String>()

df.distinctBy { age and name }
// same as
df.groupBy { age and name }.mapToRows { group.first() }
</code>
</tab>
<tab _o="1357" _o-sc="77,6" _o-l="77" _o-e="79,0" _o-tl="5" _o-s="77,0" _o-cl="0" id="9e06dd88" title="Strings">
<code _o="1387" _o-sc="81,0" _o-l="80" _o-e="84,3" _o-tl="-1" _o-s="80,0" style="block" _o-cl="0" id="1844f27c" lang="kotlin">df.distinctBy("age", "name")
// same as
df.groupBy("age", "name").mapToRows { group.first() }
</code>
</tab></tabs>

</chapter></topic>