<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="sliceRows" title="Slice rows" _md-based="true"> 
<p _o="96" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="1724f78c">Returns <code _o="104" _o-sc="4,9" _o-l="4" _o-e="4,19" _o-tl="-1" _o-s="4,8" _o-cl="8" id="81a9cd88">DataFrame</code> with rows at given indices:</p>

<code _o="182" _o-sc="9,0" _o-l="8" _o-e="10,3" _o-tl="-1" _o-s="8,0" style="block" _o-cl="0" id="cbca845d" lang="kotlin">df[0, 3, 4]
</code>

<p _o="222" _o-sc="14,0" _o-l="14" _o-e="15,0" _o-tl="-1" _o-s="14,0" _o-cl="0" id="2762808e">Returns <code _o="230" _o-sc="14,9" _o-l="14" _o-e="14,19" _o-tl="-1" _o-s="14,8" _o-cl="8" id="3e63dfd1">DataFrame</code> with rows inside given index ranges (including boundary indices):</p>

<code _o="345" _o-sc="19,0" _o-l="18" _o-e="21,3" _o-tl="-1" _o-s="18,0" style="block" _o-cl="0" id="673228d" lang="kotlin">df[1..2]
df[0..2, 4..5]
</code>

<chapter _o="397" _o-sc="25,3" _o-l="25" _o-e="25,7" _o-tl="-1" _o-s="25,0" _o-cl="0" id="take" title="take">
<p _o="406" _o-sc="27,0" _o-l="27" _o-e="28,0" _o-tl="-1" _o-s="27,0" _o-cl="0" id="bc456fc5">Returns <code _o="414" _o-sc="27,9" _o-l="27" _o-e="27,19" _o-tl="-1" _o-s="27,8" _o-cl="8" id="24f9fa70">DataFrame</code> containing first <code _o="443" _o-sc="27,38" _o-l="27" _o-e="27,40" _o-tl="-1" _o-s="27,37" _o-cl="37" id="7937be41">n</code> rows</p>

<code _o="471" _o-sc="32,0" _o-l="31" _o-e="33,3" _o-tl="-1" _o-s="31,0" style="block" _o-cl="0" id="685f1d70" lang="kotlin">df.take(5)
</code>

</chapter><chapter _o="510" _o-sc="37,3" _o-l="37" _o-e="37,11" _o-tl="-1" _o-s="37,0" _o-cl="0" id="takelast" title="takeLast">
<p _o="523" _o-sc="39,0" _o-l="39" _o-e="40,0" _o-tl="-1" _o-s="39,0" _o-cl="0" id="16a64b2e">Returns <code _o="531" _o-sc="39,9" _o-l="39" _o-e="39,19" _o-tl="-1" _o-s="39,8" _o-cl="8" id="80fb0bd0">DataFrame</code> containing last <code _o="559" _o-sc="39,37" _o-l="39" _o-e="39,39" _o-tl="-1" _o-s="39,36" _o-cl="36" id="5316c8ff">n</code> rows</p>

<code _o="591" _o-sc="44,0" _o-l="43" _o-e="45,3" _o-tl="-1" _o-s="43,0" style="block" _o-cl="0" id="81d3ac1c" lang="kotlin">df.takeLast(5)
</code>

</chapter><chapter _o="634" _o-sc="49,3" _o-l="49" _o-e="49,7" _o-tl="-1" _o-s="49,0" _o-cl="0" id="drop" title="drop">
<p _o="643" _o-sc="51,0" _o-l="51" _o-e="52,0" _o-tl="-1" _o-s="51,0" _o-cl="0" id="a55fb8e">Returns <code _o="651" _o-sc="51,9" _o-l="51" _o-e="51,19" _o-tl="-1" _o-s="51,8" _o-cl="8" id="b7b076ab">DataFrame</code> containing all rows except first <code _o="696" _o-sc="51,54" _o-l="51" _o-e="51,56" _o-tl="-1" _o-s="51,53" _o-cl="53" id="fe288622">n</code> rows</p>

<code _o="724" _o-sc="56,0" _o-l="55" _o-e="57,3" _o-tl="-1" _o-s="55,0" style="block" _o-cl="0" id="fc8d1524" lang="kotlin">df.drop(5)
</code>

</chapter><chapter _o="763" _o-sc="61,3" _o-l="61" _o-e="61,11" _o-tl="-1" _o-s="61,0" _o-cl="0" id="droplast" title="dropLast">
<p _o="776" _o-sc="63,0" _o-l="63" _o-e="64,0" _o-tl="-1" _o-s="63,0" _o-cl="0" id="48474b7d">Returns <code _o="784" _o-sc="63,9" _o-l="63" _o-e="63,19" _o-tl="-1" _o-s="63,8" _o-cl="8" id="e6d412f5">DataFrame</code> containing all rows except last <code _o="828" _o-sc="63,53" _o-l="63" _o-e="63,55" _o-tl="-1" _o-s="63,52" _o-cl="52" id="bbef8a8a">n</code> rows</p>

<code _o="860" _o-sc="68,0" _o-l="67" _o-e="69,3" _o-tl="-1" _o-s="67,0" style="block" _o-cl="0" id="bcb1eaa7" lang="kotlin">df.dropLast(5)
</code>

</chapter></topic>