<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="insert" title="insert" _md-based="true"> 
<p _o="92" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="79cdfba1">Inserts new column at specific position in <code _o="135" _o-sc="4,44" _o-l="4" _o-e="4,54" _o-tl="-1" _o-s="4,43" _o-cl="43" id="c40af439">DataFrame</code>.</p>
<p _o="150" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="53613aab">Similar to <a _o="161" _o-sc="6,12" LinkStatus="UNKNOWN" _o-l="6" _o-e="6,24" _o-tl="-1" _o-s="6,11" href="add.md" _o-cl="11" id="b0789523">add</a>, but supports column positioning.</p>
<code _o="210" _o-sc="9,0" _o-l="8" _o-e="14,3" _o-tl="163" _o-s="8,0" style="block" _o-cl="0" id="acf96099" lang="kotlin">insert 
    (columnName) { rowExpression } | (column)
    .under { parentColumn } | .after { column } | .at(position)

rowExpression: DataRow.(DataRow) -> Value
</code>
<p _o="386" _o-sc="16,0" _o-l="16" _o-e="17,0" _o-tl="-1" _o-s="16,0" _o-cl="0" id="902deaad">Create new column based on existing columns and insert it into <code _o="449" _o-sc="16,64" _o-l="16" _o-e="16,74" _o-tl="-1" _o-s="16,63" _o-cl="63" id="d6c2c093">DataFrame</code>:</p>

<tabs id="9987bb69">
<tab id="54ee006a" title="Properties">
<code _o="515" _o-sc="23,0" _o-l="22" _o-e="24,3" _o-tl="-1" _o-s="22,0" style="block" _o-cl="0" id="a1b8c5a8" lang="kotlin">df.insert("year of birth") { 2021 - age }.after { age }
</code>
</tab>
<tab _o="586" _o-sc="26,6" _o-l="26" _o-e="28,0" _o-tl="5" _o-s="26,0" _o-cl="0" id="990f32c" title="Accessors">
<code _o="618" _o-sc="30,0" _o-l="29" _o-e="34,3" _o-tl="31" _o-s="29,0" style="block" _o-cl="0" id="56fd15a8" lang="kotlin">val year = column&lt;Int>("year of birth")
val age by column&lt;Int>()

df.insert(year) { 2021 - age }.after { age }
</code>
</tab>
<tab _o="744" _o-sc="36,6" _o-l="36" _o-e="38,0" _o-tl="5" _o-s="36,0" _o-cl="0" id="b9b9c9b3" title="Strings">
<code _o="774" _o-sc="40,0" _o-l="39" _o-e="41,3" _o-tl="55" _o-s="39,0" style="block" _o-cl="0" id="5c2af416" lang="kotlin">df.insert("year of birth") { 2021 - "age"&lt;Int>() }.after("age")
</code>
</tab></tabs>

<p _o="880" _o-sc="46,0" _o-l="46" _o-e="47,0" _o-tl="-1" _o-s="46,0" _o-cl="0" id="420d63f5">Insert previously created column:</p>

<code _o="941" _o-sc="51,0" _o-l="50" _o-e="53,3" _o-tl="-1" _o-s="50,0" style="block" _o-cl="0" id="3454505a" lang="kotlin">val score by columnOf(4, 5, 3, 5, 4, 5, 3)
df.insert(score).at(2)
</code>

</topic>