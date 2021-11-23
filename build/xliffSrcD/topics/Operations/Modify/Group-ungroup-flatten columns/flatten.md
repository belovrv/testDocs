<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="flatten" title="flatten" _md-based="true"> 
<p _o="93" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="c87b9ced">Returns <code _o="101" _o-sc="4,9" _o-l="4" _o-e="4,19" _o-tl="-1" _o-s="4,8" _o-cl="8" id="bcf93026">DataFrame</code> without column groupings under selected columns</p>
<code _o="162" _o-sc="7,0" _o-l="6" _o-e="8,3" _o-tl="-1" _o-s="6,0" style="block" _o-cl="0" id="f4592018" lang="kotlin">flatten  [ { columns } ]
</code>

<code _o="223" _o-sc="13,0" _o-l="12" _o-e="16,3" _o-tl="29" _o-s="12,0" style="block" _o-cl="0" id="e5bf26cb" lang="kotlin">// name.firstName -> firstName
// name.lastName -> lastName
df.flatten { name }
</code>

<p _o="331" _o-sc="20,0" _o-l="20" _o-e="21,0" _o-tl="-1" _o-s="20,0" _o-cl="0" id="e0c5cedb">Potential column name clashes are resolved by adding minimal required prefix from ancestor column names.</p>
<p _o="437" _o-sc="22,0" _o-l="22" _o-e="23,0" _o-tl="-1" _o-s="22,0" _o-cl="0" id="a6e85d21">To remove all column groupings in <code _o="471" _o-sc="22,35" _o-l="22" _o-e="22,45" _o-tl="-1" _o-s="22,34" _o-cl="34" id="560c2445">DataFrame</code>, invoke <code _o="491" _o-sc="22,55" _o-l="22" _o-e="22,63" _o-tl="-1" _o-s="22,54" _o-cl="54" id="4bfb7224">flatten</code> without parameters:</p>

<code _o="546" _o-sc="27,0" _o-l="26" _o-e="28,3" _o-tl="-1" _o-s="26,0" style="block" _o-cl="0" id="d00a7e3a" lang="kotlin">df.flatten()
</code>

</topic>