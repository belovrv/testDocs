<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="count" title="count" _md-based="true"> 
<p _o="92" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="607fb870">Counts the number of rows.</p>

<code _o="139" _o-sc="9,0" _o-l="8" _o-e="10,3" _o-tl="-1" _o-s="8,0" style="block" _o-cl="0" id="22c31210" lang="kotlin">df.count()
</code>

<p _o="178" _o-sc="14,0" _o-l="14" _o-e="15,0" _o-tl="-1" _o-s="14,0" _o-cl="0" id="376ed646">Pass <a _o="183" _o-sc="14,6" LinkStatus="UNKNOWN" _o-l="14" _o-e="14,47" _o-tl="-1" _o-s="14,5" href="DataRow.md#row-conditions" _o-cl="5" id="dbf52986">row condition</a> to count number of rows that satisfy to that condition:</p>

<code _o="311" _o-sc="19,0" _o-l="18" _o-e="20,3" _o-tl="25" _o-s="18,0" style="block" _o-cl="0" id="a07be4b3" lang="kotlin">df.count { age > 15 }
</code>

<p _o="361" _o-sc="24,0" _o-l="24" _o-e="25,0" _o-tl="-1" _o-s="24,0" _o-cl="0" id="bd1299e8">When <code _o="366" _o-sc="24,6" _o-l="24" _o-e="24,12" _o-tl="-1" _o-s="24,5" _o-cl="5" id="832081">count</code> is used in <a _o="385" _o-sc="24,25" LinkStatus="UNKNOWN" _o-l="24" _o-e="24,56" _o-tl="-1" _o-s="24,24" href="aggregateGroupBy.md" _o-cl="24" id="ea7e5be7"><code _o="386" _o-sc="24,26" _o-l="24" _o-e="24,34" _o-tl="-1" _o-s="24,25" _o-cl="25" id="3edf58bc">groupBy</code></a> or <a _o="421" _o-sc="24,61" LinkStatus="UNKNOWN" _o-l="24" _o-e="24,88" _o-tl="-1" _o-s="24,60" href="aggregatePivot.md" _o-cl="60" id="9105c94d"><code _o="422" _o-sc="24,62" _o-l="24" _o-e="24,68" _o-tl="-1" _o-s="24,61" _o-cl="61" id="4a79d6e4">pivot</code></a> aggregations, it counts rows for every data group:</p>

<code _o="532" _o-sc="29,0" _o-l="28" _o-e="32,3" _o-tl="68" _o-s="28,0" style="block" _o-cl="0" id="d66d5c08" lang="kotlin">df.groupBy { city }.count()
df.pivot { city }.count { age > 18 }
df.pivot { name.firstName }.groupBy { name.lastName }.count()
</code>

</topic>