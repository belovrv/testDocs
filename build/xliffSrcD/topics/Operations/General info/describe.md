<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="describe" title="describe" _md-based="true"> 
<p _o="95" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="a2e92b10">Returns <code _o="103" _o-sc="4,9" _o-l="4" _o-e="4,19" _o-tl="-1" _o-s="4,8" _o-cl="8" id="35dd79dc">DataFrame</code> with general statistics for all <a _o="147" _o-sc="4,53" LinkStatus="UNKNOWN" _o-l="4" _o-e="4,95" _o-tl="-1" _o-s="4,52" href="DataColumn.md#valuecolumn" _o-cl="52" id="5ba51a6b"><code _o="148" _o-sc="4,54" _o-l="4" _o-e="4,67" _o-tl="-1" _o-s="4,53" _o-cl="53" id="7ff1e539">ValueColumns</code></a>.</p>
<p _o="193" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="64afc2a0"><code _o="193" _o-sc="6,1" _o-l="6" _o-e="6,14" _o-tl="-1" _o-s="6,0" _o-cl="0" id="200e6c29">ColumnGroups</code> and <code _o="212" _o-sc="6,20" _o-l="6" _o-e="6,33" _o-tl="-1" _o-s="6,19" _o-cl="19" id="bde1dcb4">FrameColumns</code> are traversed recursively down to <code _o="261" _o-sc="6,69" _o-l="6" _o-e="6,82" _o-tl="-1" _o-s="6,68" _o-cl="68" id="b8c0ef49">ValueColumns</code>.</p>
<p _o="278" _o-sc="8,0" _o-l="8" _o-e="9,0" _o-tl="-1" _o-s="8,0" _o-cl="0" id="7459f9ed">Collected statistics:</p>
<list _o="300" _o-sc="9,0" _o-l="9" _o-e="22,0" _o-tl="-1" _o-s="9,0" _o-cl="0" id="7571e8b2">
<li _o="300" _o-sc="9,2" _o-l="9" _o-e="10,0" _o-tl="-1" _o-s="9,0" _o-cl="0" id="49f973e7">name - column name</li>
<li _o="321" _o-sc="10,2" _o-l="10" _o-e="11,0" _o-tl="-1" _o-s="10,0" _o-cl="0" id="792ceb2d">path - path to the column (for hierarchical <code _o="367" _o-sc="10,47" _o-l="10" _o-e="10,57" _o-tl="-1" _o-s="10,46" _o-cl="46" id="83455552">DataFrame</code>)</li>
<li _o="380" _o-sc="11,2" _o-l="11" _o-e="12,0" _o-tl="-1" _o-s="11,0" _o-cl="0" id="75184d30">type - type of values</li>
<li _o="404" _o-sc="12,2" _o-l="12" _o-e="13,0" _o-tl="-1" _o-s="12,0" _o-cl="0" id="e0fca6a2">count - number of rows</li>
<li _o="429" _o-sc="13,2" _o-l="13" _o-e="14,0" _o-tl="-1" _o-s="13,0" _o-cl="0" id="a578e74">unique - number of unique values</li>
<li _o="464" _o-sc="14,2" _o-l="14" _o-e="15,0" _o-tl="-1" _o-s="14,0" _o-cl="0" id="8be651e4">nulls - number of <code _o="484" _o-sc="14,21" _o-l="14" _o-e="14,26" _o-tl="-1" _o-s="14,20" _o-cl="20" id="e3b98080">null</code> values</li>
<li _o="498" _o-sc="15,2" _o-l="15" _o-e="16,0" _o-tl="-1" _o-s="15,0" _o-cl="0" id="3aabf5e5">top - the most common not <code _o="526" _o-sc="15,29" _o-l="15" _o-e="15,34" _o-tl="-1" _o-s="15,28" _o-cl="28" id="1a38e987">null</code> value</li>
<li _o="539" _o-sc="16,2" _o-l="16" _o-e="17,0" _o-tl="-1" _o-s="16,0" _o-cl="0" id="c20e7d5c">freq - <code _o="548" _o-sc="16,10" _o-l="16" _o-e="16,14" _o-tl="-1" _o-s="16,9" _o-cl="9" id="454bed15">top</code> value frequency</li>
<li _o="570" _o-sc="17,2" _o-l="17" _o-e="18,0" _o-tl="-1" _o-s="17,0" _o-cl="0" id="a80b7b8e">mean - mean value (for numeric columns)</li>
<li _o="612" _o-sc="18,2" _o-l="18" _o-e="19,0" _o-tl="-1" _o-s="18,0" _o-cl="0" id="89c90c67">std - standard deviation (for numeric columns)</li>
<li _o="661" _o-sc="19,2" _o-l="19" _o-e="20,0" _o-tl="-1" _o-s="19,0" _o-cl="0" id="e95abe87">min - minimal value (for comparable columns)</li>
<li _o="708" _o-sc="20,2" _o-l="20" _o-e="21,0" _o-tl="-1" _o-s="20,0" _o-cl="0" id="fc73a1cb">median - median value (for comparable columns)</li>
<li _o="757" _o-sc="21,2" _o-l="21" _o-e="22,0" _o-tl="-1" _o-s="21,0" _o-cl="0" id="10115a1c">max - maximum value (for comparable columns)</li>
</list>

<code _o="827" _o-sc="26,0" _o-l="25" _o-e="27,3" _o-tl="-1" _o-s="25,0" style="block" _o-cl="0" id="a66e5c55" lang="kotlin">df.describe()
</code>

<p _o="869" _o-sc="31,0" _o-l="31" _o-e="32,0" _o-tl="-1" _o-s="31,0" _o-cl="0" id="25db9090">To describe only specific columns, pass them as an argument:</p>

<tabs id="108d6952">
<tab id="56682cae" title="Properties">
<code _o="992" _o-sc="38,0" _o-l="37" _o-e="39,3" _o-tl="-1" _o-s="37,0" style="block" _o-cl="0" id="1d3b945d" lang="kotlin">df.describe { age and name.all() }
</code>
</tab>
<tab _o="1042" _o-sc="41,6" _o-l="41" _o-e="43,0" _o-tl="5" _o-s="41,0" _o-cl="0" id="b2dc2044" title="Accessors">
<code _o="1074" _o-sc="45,0" _o-l="44" _o-e="49,3" _o-tl="31" _o-s="44,0" style="block" _o-cl="0" id="8566e319" lang="kotlin">val age by column&lt;Int>()
val name by columnGroup()

df.describe { age and name.all() }
</code>
</tab>
<tab _o="1176" _o-sc="51,6" _o-l="51" _o-e="53,0" _o-tl="5" _o-s="51,0" _o-cl="0" id="f0983cf4" title="Strings">
<code _o="1206" _o-sc="55,0" _o-l="54" _o-e="56,3" _o-tl="-1" _o-s="54,0" style="block" _o-cl="0" id="c42e639b" lang="kotlin">df.describe { "age" and "name".all() }
</code>
</tab></tabs>

</topic>