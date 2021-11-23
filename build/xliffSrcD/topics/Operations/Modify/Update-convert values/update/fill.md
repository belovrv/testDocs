<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="fill" title="fill" _md-based="true"> 
<p _o="90" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="1230d292">Replace missing values.</p>
<chapter _o="115" _o-sc="6,3" _o-l="6" _o-e="6,12" _o-tl="-1" _o-s="6,0" _o-cl="0" id="fillnulls" title="fillNulls">
<p _o="129" _o-sc="8,0" _o-l="8" _o-e="9,0" _o-tl="-1" _o-s="8,0" _o-cl="0" id="3692c148">Replaces <code _o="138" _o-sc="8,10" _o-l="8" _o-e="8,15" _o-tl="-1" _o-s="8,9" _o-cl="9" id="9bfded1c">null</code> values with given value or expression.</p>

<code _o="209" _o-sc="13,0" _o-l="12" _o-e="16,3" _o-tl="-1" _o-s="12,0" style="block" _o-cl="0" id="c8ec2d28" lang="kotlin">df.fillNulls { intCols() }.with { -1 }
// same as
df.update { intCols() }.where { it == null }.with { -1 }
</code>

</chapter><chapter _o="344" _o-sc="20,3" _o-l="20" _o-e="20,11" _o-tl="-1" _o-s="20,0" _o-cl="0" id="fillnans" title="fillNaNs">
<p _o="357" _o-sc="22,0" _o-l="22" _o-e="23,0" _o-tl="-1" _o-s="22,0" _o-cl="0" id="d0910d0c">Replaces <code _o="366" _o-sc="22,10" _o-l="22" _o-e="22,21" _o-tl="-1" _o-s="22,9" _o-cl="9" id="39bc686e">Double.NaN</code> and <code _o="383" _o-sc="22,27" _o-l="22" _o-e="22,37" _o-tl="-1" _o-s="22,26" _o-cl="26" id="cd9fda75">Float.NaN</code> values with given value or expression.</p>

<code _o="457" _o-sc="27,0" _o-l="26" _o-e="28,3" _o-tl="-1" _o-s="26,0" style="block" _o-cl="0" id="802c5eb" lang="kotlin">df.fillNaNs { doubleCols() }.withZero()
</code>

</chapter><chapter _o="525" _o-sc="32,3" _o-l="32" _o-e="32,9" _o-tl="-1" _o-s="32,0" _o-cl="0" id="fillna" title="fillNA">
<p _o="536" _o-sc="34,0" _o-l="34" _o-e="35,0" _o-tl="-1" _o-s="34,0" _o-cl="0" id="44231a1b">Replaces <code _o="545" _o-sc="34,10" _o-l="34" _o-e="34,15" _o-tl="-1" _o-s="34,9" _o-cl="9" id="9f5aba52">null</code>, <code _o="553" _o-sc="34,18" _o-l="34" _o-e="34,29" _o-tl="-1" _o-s="34,17" _o-cl="17" id="5050da86">Double.NaN</code> and <code _o="570" _o-sc="34,35" _o-l="34" _o-e="34,45" _o-tl="-1" _o-s="34,34" _o-cl="34" id="4cba2990">Float.NaN</code> values with given value or expression.</p>

<code _o="642" _o-sc="39,0" _o-l="38" _o-e="40,3" _o-tl="-1" _o-s="38,0" style="block" _o-cl="0" id="3b538237" lang="kotlin">df.fillNA { weight }.withValue(-1)
</code>

</chapter></topic>