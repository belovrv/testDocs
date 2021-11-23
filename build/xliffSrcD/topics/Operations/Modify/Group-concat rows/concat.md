<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="concat" title="concat" _md-based="true"> 
<p _o="92" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="9bbcdc01">Returns <code _o="100" _o-sc="4,9" _o-l="4" _o-e="4,19" _o-tl="-1" _o-s="4,8" _o-cl="8" id="47ff7077">DataFrame</code> with the union of rows from several given <code _o="154" _o-sc="4,63" _o-l="4" _o-e="4,74" _o-tl="-1" _o-s="4,62" _o-cl="62" id="fa3bfc24">DataFrames</code>.</p>
<p _o="169" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="f327e5d"><code _o="169" _o-sc="6,1" _o-l="6" _o-e="6,8" _o-tl="-1" _o-s="6,0" _o-cl="0" id="7616c5de">concat</code> is available for:</p>
<p _o="197" _o-sc="8,0" _o-l="8" _o-e="9,0" _o-tl="-1" _o-s="8,0" _o-cl="0" id="97d5a104"><code _o="197" _o-sc="8,1" _o-l="8" _o-e="8,11" _o-tl="-1" _o-s="8,0" _o-cl="0" id="f9bdf52e">DataFrame</code>:</p>

<code _o="234" _o-sc="13,0" _o-l="12" _o-e="14,3" _o-tl="-1" _o-s="12,0" style="block" _o-cl="0" id="82dd7fc8" lang="kotlin">df.concat(df1, df2)
</code>

<p _o="282" _o-sc="18,0" _o-l="18" _o-e="19,0" _o-tl="19" _o-s="18,0" _o-cl="0" id="407f51cf"><code _o="282" _o-sc="18,1" _o-l="18" _o-e="18,21" _o-tl="19" _o-s="18,0" _o-cl="0" id="819f7646">Iterable&lt;DataFrame></code>:</p>

<code _o="334" _o-sc="23,0" _o-l="22" _o-e="24,3" _o-tl="-1" _o-s="22,0" style="block" _o-cl="0" id="d5773bd8" lang="kotlin">listOf(df1, df2).concat()
</code>

<p _o="388" _o-sc="28,0" _o-l="28" _o-e="29,0" _o-tl="17" _o-s="28,0" _o-cl="0" id="19a8981b"><code _o="388" _o-sc="28,1" _o-l="28" _o-e="28,19" _o-tl="17" _o-s="28,0" _o-cl="0" id="d1986b1d">Iterable&lt;DataRow></code>:</p>

<code _o="434" _o-sc="33,0" _o-l="32" _o-e="35,3" _o-tl="-1" _o-s="32,0" style="block" _o-cl="0" id="8544eb2a" lang="kotlin">val rows = listOf(df[2], df[4], df[5])
rows.concat()
</code>

<p _o="515" _o-sc="39,0" _o-l="39" _o-e="40,0" _o-tl="-1" _o-s="39,0" _o-cl="0" id="3d8ff904"><a _o="515" _o-sc="39,1" LinkStatus="UNKNOWN" _o-l="39" _o-e="39,31" _o-tl="-1" _o-s="39,0" href="groupBy.md#groupby" _o-cl="0" id="2dbd4e77"><code _o="516" _o-sc="39,2" _o-l="39" _o-e="39,10" _o-tl="-1" _o-s="39,1" _o-cl="1" id="58f2cc5a">GroupBy</code></a>:</p>

<code _o="576" _o-sc="44,0" _o-l="43" _o-e="45,3" _o-tl="-1" _o-s="43,0" style="block" _o-cl="0" id="d610dd1f" lang="kotlin">df.groupBy { name }.concat()
</code>

<p _o="633" _o-sc="49,0" _o-l="49" _o-e="50,0" _o-tl="-1" _o-s="49,0" _o-cl="0" id="281656ac"><a _o="633" _o-sc="49,1" LinkStatus="UNKNOWN" _o-l="49" _o-e="49,42" _o-tl="-1" _o-s="49,0" href="DataColumn.md#framecolumn" _o-cl="0" id="51becb59"><code _o="634" _o-sc="49,2" _o-l="49" _o-e="49,14" _o-tl="-1" _o-s="49,1" _o-cl="1" id="30675a2a">FrameColumn</code></a>:</p>

<code _o="709" _o-sc="54,0" _o-l="53" _o-e="56,3" _o-tl="-1" _o-s="53,0" style="block" _o-cl="0" id="3cf8d2a0" lang="kotlin">val frameColumn by columnOf(df[0..1], df[4..5])
frameColumn.concat()
</code>

<p _o="806" _o-sc="60,0" _o-l="60" _o-e="61,0" _o-tl="-1" _o-s="60,0" _o-cl="0" id="eff270f9">If you want to union columns (not rows) from several <code _o="859" _o-sc="60,54" _o-l="60" _o-e="60,65" _o-tl="-1" _o-s="60,53" _o-cl="53" id="b157a00">DataFrames</code>, see <a _o="877" _o-sc="60,72" LinkStatus="UNKNOWN" _o-l="60" _o-e="60,86" _o-tl="-1" _o-s="60,71" href="add.md" _o-cl="71" id="a46f0c10"><code _o="878" _o-sc="60,73" _o-l="60" _o-e="60,77" _o-tl="-1" _o-s="60,72" _o-cl="72" id="40c19767">add</code></a>.</p>
<chapter _o="895" _o-sc="62,3" _o-l="62" _o-e="62,21" _o-tl="-1" _o-s="62,0" _o-cl="0" id="schema-unification" title="Schema unification">
<p _o="918" _o-sc="64,0" _o-l="64" _o-e="65,0" _o-tl="-1" _o-s="64,0" _o-cl="0" id="715f649b">If input <code _o="927" _o-sc="64,10" _o-l="64" _o-e="64,21" _o-tl="-1" _o-s="64,9" _o-cl="9" id="da6036bf">DataFrames</code> have different schemas, every column in resulting <code _o="990" _o-sc="64,73" _o-l="64" _o-e="64,83" _o-tl="-1" _o-s="64,72" _o-cl="72" id="61130ae3">DataFrame</code> will have the most common type of the original columns with the same name.</p>
<p _o="1079" _o-sc="66,0" _o-l="66" _o-e="67,0" _o-tl="-1" _o-s="66,0" _o-cl="0" id="f403c640">For example, if one <code _o="1099" _o-sc="66,21" _o-l="66" _o-e="66,31" _o-tl="-1" _o-s="66,20" _o-cl="20" id="cbab5402">DataFrame</code> has column <code _o="1122" _o-sc="66,44" _o-l="66" _o-e="66,51" _o-tl="-1" _o-s="66,43" _o-cl="43" id="419eddd5">A: Int</code> and other <code _o="1141" _o-sc="66,63" _o-l="66" _o-e="66,73" _o-tl="-1" _o-s="66,62" _o-cl="62" id="8e4c9a43">DataFrame</code> has column <code _o="1164" _o-sc="66,86" _o-l="66" _o-e="66,96" _o-tl="-1" _o-s="66,85" _o-cl="85" id="2031a821">A: Double</code>, resulting <code _o="1187" _o-sc="66,109" _o-l="66" _o-e="66,119" _o-tl="-1" _o-s="66,108" _o-cl="108" id="c821dbf1">DataFrame</code> will have column <code _o="1216" _o-sc="66,138" _o-l="66" _o-e="66,148" _o-tl="-1" _o-s="66,137" _o-cl="137" id="ccb03db0">A: Number</code>.</p>
<p _o="1230" _o-sc="68,0" _o-l="68" _o-e="69,0" _o-tl="-1" _o-s="68,0" _o-cl="0" id="20c8b1db">Missing columns in dataframes will be filled with <code _o="1280" _o-sc="68,51" _o-l="68" _o-e="68,56" _o-tl="-1" _o-s="68,50" _o-cl="50" id="1f19c349">null</code>.</p>
</chapter></topic>