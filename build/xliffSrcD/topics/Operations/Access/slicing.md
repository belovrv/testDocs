<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="slicing" title="Slicing" _md-based="true"> <p _o="26" _o-sc="2,0" _o-l="2" _o-e="3,0" _o-tl="-1" _o-s="2,0" _o-cl="0" id="b16c22f0">Slicing means cutting a portion of <code _o="61" _o-sc="2,36" _o-l="2" _o-e="2,46" _o-tl="-1" _o-s="2,35" _o-cl="35" id="ad3918ee">DataFrame</code> by continuous range of rows or columns.</p>

<chapter _o="181" _o-sc="6,3" _o-l="6" _o-e="6,13" _o-tl="-1" _o-s="6,0" _o-cl="0" id="slice-rows" title="Slice rows">
<p _o="196" _o-sc="8,0" _o-l="8" _o-e="9,0" _o-tl="-1" _o-s="8,0" _o-cl="0" id="4c9e4832">by row indices (including boundaries):</p>

<code _o="272" _o-sc="13,0" _o-l="12" _o-e="15,3" _o-tl="-1" _o-s="12,0" style="block" _o-cl="0" id="fbf80a18" lang="kotlin">df[1..2]
df[0..2, 4..5]
</code>

<p _o="324" _o-sc="19,0" _o-l="19" _o-e="20,0" _o-tl="-1" _o-s="19,0" _o-cl="0" id="89361089">See <a _o="328" _o-sc="19,5" LinkStatus="UNKNOWN" _o-l="19" _o-e="19,30" _o-tl="-1" _o-s="19,4" href="sliceRows.md" _o-cl="4" id="516a64ce">slice rows</a> for other ways to select subset of rows.</p>
</chapter><chapter _o="397" _o-sc="21,3" _o-l="21" _o-e="21,16" _o-tl="-1" _o-s="21,0" _o-cl="0" id="slice-columns" title="Slice columns">
<p _o="415" _o-sc="23,0" _o-l="23" _o-e="24,0" _o-tl="-1" _o-s="23,0" _o-cl="0" id="dfc0df7b">by column indices (including boundaries):</p>

<code _o="491" _o-sc="28,0" _o-l="27" _o-e="29,3" _o-tl="-1" _o-s="27,0" style="block" _o-cl="0" id="ec62c502" lang="kotlin">df.select { cols(1..3) }
</code>

<p _o="544" _o-sc="33,0" _o-l="33" _o-e="34,0" _o-tl="-1" _o-s="33,0" _o-cl="0" id="1fcd47c3">by column names:</p>

<tabs id="bab3138c">
<tab id="99d867f1" title="Properties">
<code _o="620" _o-sc="40,0" _o-l="39" _o-e="41,3" _o-tl="-1" _o-s="39,0" style="block" _o-cl="0" id="1a321c9f" lang="kotlin">df.select { age..weight }
</code>
</tab>
<tab _o="661" _o-sc="43,6" _o-l="43" _o-e="45,0" _o-tl="5" _o-s="43,0" _o-cl="0" id="83aca866" title="Accessors">
<code _o="693" _o-sc="47,0" _o-l="46" _o-e="51,3" _o-tl="31" _o-s="46,0" style="block" _o-cl="0" id="e2631256" lang="kotlin">val age by column&lt;Int>()
val weight by column&lt;Int?>()

df.select { age..weight }
</code>
</tab>
<tab _o="789" _o-sc="53,6" _o-l="53" _o-e="55,0" _o-tl="5" _o-s="53,0" _o-cl="0" id="21754282" title="Strings">
<code _o="819" _o-sc="57,0" _o-l="56" _o-e="58,3" _o-tl="-1" _o-s="56,0" style="block" _o-cl="0" id="61f8c3c" lang="kotlin">df.select { "age".."weight" }
</code>
</tab></tabs>

<p _o="891" _o-sc="63,0" _o-l="63" _o-e="64,0" _o-tl="-1" _o-s="63,0" _o-cl="0" id="7b4b3de">See <a _o="895" _o-sc="63,5" LinkStatus="UNKNOWN" _o-l="63" _o-e="63,42" _o-tl="-1" _o-s="63,4" href="ColumnSelectors.md" _o-cl="4" id="988882ed">Column Selectors</a> for other ways to select subset of columns.</p>
</chapter></topic>