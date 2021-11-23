<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="explode" title="explode" _md-based="true"> 
<p _o="93" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="91275e23">Splits list-like values in one or several columns and spreads them vertically. Values in other columns are duplicated.</p>
<p _o="215" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="f2e47cae">This is reverse operation to <a _o="244" _o-sc="6,30" LinkStatus="UNKNOWN" _o-l="6" _o-e="6,52" _o-tl="-1" _o-s="6,29" href="implode.md" _o-cl="29" id="ff71cf64"><code _o="245" _o-sc="6,31" _o-l="6" _o-e="6,39" _o-tl="-1" _o-s="6,30" _o-cl="30" id="c945384d">implode</code></a></p>
<p _o="269" _o-sc="8,0" _o-l="8" _o-e="9,0" _o-tl="-1" _o-s="8,0" _o-cl="0" id="399dedf8">Exploded columns will change their types:</p>
<list _o="311" _o-sc="9,0" _o-l="9" _o-e="11,0" _o-tl="9" _o-s="9,0" _o-cl="0" id="76af7185">
<li _o="311" _o-sc="9,2" _o-l="9" _o-e="10,0" _o-tl="9" _o-s="9,0" _o-cl="0" id="1bd68ff8"><code _o="313" _o-sc="9,3" _o-l="9" _o-e="9,11" _o-tl="7" _o-s="9,2" _o-cl="2" id="7d7edcba">List&lt;T></code> to <code _o="326" _o-sc="9,16" _o-l="9" _o-e="9,18" _o-tl="-1" _o-s="9,15" _o-cl="15" id="d8cba72b">T</code></li>
<li _o="330" _o-sc="10,2" _o-l="10" _o-e="11,0" _o-tl="-1" _o-s="10,0" _o-cl="0" id="39f79479"><code _o="332" _o-sc="10,3" _o-l="10" _o-e="10,13" _o-tl="-1" _o-s="10,2" _o-cl="2" id="437bb837">DataFrame</code> to <code _o="347" _o-sc="10,18" _o-l="10" _o-e="10,26" _o-tl="-1" _o-s="10,17" _o-cl="17" id="b138f93c">DataRow</code></li>
</list>
<p _o="358" _o-sc="12,0" _o-l="12" _o-e="13,0" _o-tl="-1" _o-s="12,0" _o-cl="0" id="984ee677">Note that exploded <a _o="377" _o-sc="12,20" LinkStatus="UNKNOWN" _o-l="12" _o-e="12,61" _o-tl="-1" _o-s="12,19" href="DataColumn.md#framecolumn" _o-cl="19" id="47aa9830"><code _o="378" _o-sc="12,21" _o-l="12" _o-e="12,33" _o-tl="-1" _o-s="12,20" _o-cl="20" id="340d0965">FrameColumn</code></a> will convert into <a _o="438" _o-sc="12,81" LinkStatus="UNKNOWN" _o-l="12" _o-e="12,122" _o-tl="-1" _o-s="12,80" href="DataColumn.md#columngroup" _o-cl="80" id="a7ba837"><code _o="439" _o-sc="12,82" _o-l="12" _o-e="12,94" _o-tl="-1" _o-s="12,81" _o-cl="81" id="d174b3c">ColumnGroup</code></a></p>
<p _o="482" _o-sc="14,0" _o-l="14" _o-e="15,0" _o-tl="-1" _o-s="14,0" _o-cl="0" id="6c32db26">Rows with empty lists will be skipped. If you want to keep such rows with <code _o="556" _o-sc="14,75" _o-l="14" _o-e="14,80" _o-tl="-1" _o-s="14,74" _o-cl="74" id="8ddeb476">null</code> value in exploded columns, set <code _o="594" _o-sc="14,113" _o-l="14" _o-e="14,123" _o-tl="-1" _o-s="14,112" _o-cl="112" id="99a0a97d">dropEmpty</code> flag to <code _o="614" _o-sc="14,133" _o-l="14" _o-e="14,139" _o-tl="-1" _o-s="14,132" _o-cl="132" id="92594d31">false</code>.</p>

<tabs id="a3eeb94a">
<tab id="c6ce28cb" title="Accessors">
<code _o="676" _o-sc="21,0" _o-l="20" _o-e="27,3" _o-tl="-1" _o-s="20,0" style="block" _o-cl="0" id="35630479" lang="kotlin">val a by columnOf(1, 2)
val b by columnOf(listOf(1, 2), listOf(3, 4))

val df = dataFrameOf(a, b)

df.explode { b }
</code>
</tab>
<tab _o="807" _o-sc="29,6" _o-l="29" _o-e="31,0" _o-tl="5" _o-s="29,0" _o-cl="0" id="b9840203" title="Strings">
<code _o="837" _o-sc="33,0" _o-l="32" _o-e="39,3" _o-tl="-1" _o-s="32,0" style="block" _o-cl="0" id="c3cf923d" lang="kotlin">val df = dataFrameOf("a", "b")(
    1, listOf(1, 2),
    2, listOf(3, 4)
)

df.explode("b")
</code>
</tab></tabs>

<p _o="971" _o-sc="44,0" _o-l="44" _o-e="45,0" _o-tl="-1" _o-s="44,0" _o-cl="0" id="296eed4">When several columns are exploded in one operation, lists in different columns will be aligned.</p>

<code _o="1096" _o-sc="49,0" _o-l="48" _o-e="54,3" _o-tl="-1" _o-s="48,0" style="block" _o-cl="0" id="86011ff2" lang="kotlin">val a by columnOf(listOf(1, 2), listOf(3, 4, 5))
val b by columnOf(listOf(1, 2, 3), listOf(4, 5))

val df = dataFrameOf(a, b)
df.explode { a and b }
</code>

<p _o="1273" _o-sc="58,0" _o-l="58" _o-e="59,0" _o-tl="22" _o-s="58,0" _o-cl="0" id="180db2ae"><code _o="1273" _o-sc="58,1" _o-l="58" _o-e="58,24" _o-tl="22" _o-s="58,0" _o-cl="0" id="184e938c">DataColumn&lt;Collection></code> or <code _o="1301" _o-sc="58,29" _o-l="58" _o-e="58,41" _o-tl="-1" _o-s="58,28" _o-cl="28" id="dacc69cb">FrameColumn</code> can also be exploded:</p>

<code _o="1369" _o-sc="63,0" _o-l="62" _o-e="66,3" _o-tl="-1" _o-s="62,0" style="block" _o-cl="0" id="4aea188d" lang="kotlin">val col by columnOf(listOf(1, 2), listOf(3, 4))

col.explode()
</code>


<code _o="1493" _o-sc="73,0" _o-l="72" _o-e="79,3" _o-tl="-1" _o-s="72,0" style="block" _o-cl="0" id="55b82bc0" lang="kotlin">val col by columnOf(
    dataFrameOf("a", "b")(1, 2, 3, 4),
    dataFrameOf("a", "b")(5, 6, 7, 8)
)

col.explode()
</code>

</topic>