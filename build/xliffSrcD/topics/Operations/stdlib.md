<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="stdlib" title="Interop with Stdlib" _md-based="true"> 
<p _o="105" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="70570b86"><code _o="105" _o-sc="4,1" _o-l="4" _o-e="4,11" _o-tl="-1" _o-s="4,0" _o-cl="0" id="65922881">DataFrame</code> doesn't implement <code _o="135" _o-sc="4,31" _o-l="4" _o-e="4,40" _o-tl="-1" _o-s="4,30" _o-cl="30" id="43fb3152">Iterable</code> interface, but redefines some of extension functions available for <code _o="213" _o-sc="4,109" _o-l="4" _o-e="4,118" _o-tl="-1" _o-s="4,108" _o-cl="108" id="4013a3d8">Iterable</code>:</p>

<code _o="251" _o-sc="9,0" _o-l="8" _o-e="13,3" _o-tl="-1" _o-s="8,0" style="block" _o-cl="0" id="d6ddd53e" lang="kotlin">df.forEachRow { println(it) }
df.take(5)
df.drop(2)
df.chunked(10)
</code>

<p _o="346" _o-sc="17,0" _o-l="17" _o-e="18,0" _o-tl="-1" _o-s="17,0" _o-cl="0" id="b118da6a">To convert <code _o="357" _o-sc="17,12" _o-l="17" _o-e="17,22" _o-tl="-1" _o-s="17,11" _o-cl="11" id="6b8b4643">DataFrame</code> into <code _o="374" _o-sc="17,29" _o-l="17" _o-e="17,38" _o-tl="-1" _o-s="17,28" _o-cl="28" id="6762e981">Iterable</code>/<code _o="385" _o-sc="17,40" _o-l="17" _o-e="17,49" _o-tl="-1" _o-s="17,39" _o-cl="39" id="6c7752c3">Sequence</code> of rows, columns or cell values use the following functions:</p>

<code _o="486" _o-sc="22,0" _o-l="21" _o-e="25,3" _o-tl="41" _o-s="21,0" style="block" _o-cl="0" id="8cd82f95" lang="kotlin">df.columns() // List&lt;DataColumn>
df.rows() // Iterable&lt;DataRow>
df.values() // Sequence&lt;Any?>
</code>

</topic>