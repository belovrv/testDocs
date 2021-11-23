<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="sortBy" title="sortBy" _md-based="true"> 
<p _o="92" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="557e8492">Returns <code _o="100" _o-sc="4,9" _o-l="4" _o-e="4,19" _o-tl="-1" _o-s="4,8" _o-cl="8" id="acff6fc7">DataFrame</code> sorted by one or several columns.</p>
<p _o="147" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="e1be92e6">By default, columns are sorted in ascending order with <code _o="202" _o-sc="6,56" _o-l="6" _o-e="6,61" _o-tl="-1" _o-s="6,55" _o-cl="55" id="a9eaf635">null</code> values going first. Available modifiers:</p>
<list _o="250" _o-sc="7,0" _o-l="7" _o-e="9,0" _o-tl="-1" _o-s="7,0" _o-cl="0" id="a4c15d82">
<li _o="250" _o-sc="7,2" _o-l="7" _o-e="8,0" _o-tl="-1" _o-s="7,0" _o-cl="0" id="5e93b955"><code _o="252" _o-sc="7,3" _o-l="7" _o-e="7,9" _o-tl="-1" _o-s="7,2" _o-cl="2" id="3b75803e">.desc</code> - changes column sort order from ascending to descending</li>
<li _o="317" _o-sc="8,2" _o-l="8" _o-e="9,0" _o-tl="-1" _o-s="8,0" _o-cl="0" id="f8a6d364"><code _o="319" _o-sc="8,3" _o-l="8" _o-e="8,14" _o-tl="-1" _o-s="8,2" _o-cl="2" id="4075b28e">.nullsLast</code> - forces <code _o="341" _o-sc="8,25" _o-l="8" _o-e="8,30" _o-tl="-1" _o-s="8,24" _o-cl="24" id="8877c403">null</code> values to be placed at the end of the order</li>
</list>

<tabs id="adda1599">
<tab id="f78a1f8d" title="Properties">
<code _o="445" _o-sc="15,0" _o-l="14" _o-e="18,3" _o-tl="-1" _o-s="14,0" style="block" _o-cl="0" id="4c29be14" lang="kotlin">df.sortBy { age }
df.sortBy { age and name.firstName.desc }
df.sortBy { weight.nullsLast }
</code>
</tab>
<tab _o="551" _o-sc="20,6" _o-l="20" _o-e="22,0" _o-tl="5" _o-s="20,0" _o-cl="0" id="4532404d" title="Accessors">
<code _o="583" _o-sc="24,0" _o-l="23" _o-e="32,3" _o-tl="31" _o-s="23,0" style="block" _o-cl="0" id="2a722423" lang="kotlin">val age by column&lt;Int>()
val weight by column&lt;Int?>()
val name by columnGroup()
val firstName by name.column&lt;String>()

df.sortBy { age }
df.sortBy { age and firstName }
df.sortBy { weight.nullsLast }
</code>
</tab>
<tab _o="799" _o-sc="34,6" _o-l="34" _o-e="36,0" _o-tl="5" _o-s="34,0" _o-cl="0" id="cb8470e8" title="Strings">
<code _o="829" _o-sc="38,0" _o-l="37" _o-e="41,3" _o-tl="-1" _o-s="37,0" style="block" _o-cl="0" id="e84019e7" lang="kotlin">df.sortBy("age")
df.sortBy { "age" and "name"["firstName"].desc }
df.sortBy { "weight".nullsLast }
</code>
</tab></tabs>

<chapter _o="970" _o-sc="46,3" _o-l="46" _o-e="46,13" _o-tl="-1" _o-s="46,0" _o-cl="0" id="sortbydesc" title="sortByDesc">
<p _o="985" _o-sc="48,0" _o-l="48" _o-e="49,0" _o-tl="-1" _o-s="48,0" _o-cl="0" id="b169e717">Returns <code _o="993" _o-sc="48,9" _o-l="48" _o-e="48,19" _o-tl="-1" _o-s="48,8" _o-cl="8" id="8b320965">DataFrame</code> sorted by one or several columns in descending order.</p>

<tabs id="2ff4d776">
<tab id="2ce8dc13" title="Properties">
<code _o="1116" _o-sc="55,0" _o-l="54" _o-e="56,3" _o-tl="-1" _o-s="54,0" style="block" _o-cl="0" id="b9a65816" lang="kotlin">df.sortByDesc { age and weight }
</code>
</tab>
<tab _o="1164" _o-sc="58,6" _o-l="58" _o-e="60,0" _o-tl="5" _o-s="58,0" _o-cl="0" id="8231956f" title="Accessors">
<code _o="1196" _o-sc="62,0" _o-l="61" _o-e="66,3" _o-tl="31" _o-s="61,0" style="block" _o-cl="0" id="94ce134b" lang="kotlin">val age by column&lt;Int>()
val weight by column&lt;Int?>()

df.sortByDesc { age and weight }
</code>
</tab>
<tab _o="1299" _o-sc="68,6" _o-l="68" _o-e="70,0" _o-tl="5" _o-s="68,0" _o-cl="0" id="f7cbcbe3" title="Strings">
<code _o="1329" _o-sc="72,0" _o-l="71" _o-e="73,3" _o-tl="-1" _o-s="71,0" style="block" _o-cl="0" id="d7029bd8" lang="kotlin">df.sortByDesc("age", "weight")
</code>
</tab></tabs>

</chapter><chapter _o="1402" _o-sc="78,3" _o-l="78" _o-e="78,11" _o-tl="-1" _o-s="78,0" _o-cl="0" id="sortwith" title="sortWith">
<p _o="1415" _o-sc="80,0" _o-l="80" _o-e="81,0" _o-tl="-1" _o-s="80,0" _o-cl="0" id="2b15fdef">Returns <code _o="1423" _o-sc="80,9" _o-l="80" _o-e="80,19" _o-tl="-1" _o-s="80,8" _o-cl="8" id="e261bbea">DataFrame</code> sorted with comparator.</p>

<code _o="1482" _o-sc="85,0" _o-l="84" _o-e="92,3" _o-tl="36" _o-s="84,0" style="block" _o-cl="0" id="cf7c44ee" lang="kotlin">df.sortWith { row1, row2 ->
    when {
        row1.age &lt; row2.age -> -1
        row1.age > row2.age -> 1
        else -> row1.name.firstName.compareTo(row2.name.firstName)
    }
}
</code>

</chapter></topic>