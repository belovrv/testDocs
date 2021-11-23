<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="minmax" title="min / max" _md-based="true"> 
<p _o="96" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="987534b6">Computes the minimum / maximum of values.</p>
<p _o="139" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="8f97d12e">Is available for <code _o="156" _o-sc="6,18" _o-l="6" _o-e="6,29" _o-tl="-1" _o-s="6,17" _o-cl="17" id="670fd0f3">Comparable</code> columns. <code _o="178" _o-sc="6,40" _o-l="6" _o-e="6,45" _o-tl="-1" _o-s="6,39" _o-cl="39" id="f317d3ea">null</code> and <code _o="189" _o-sc="6,51" _o-l="6" _o-e="6,55" _o-tl="-1" _o-s="6,50" _o-cl="50" id="542e7624">NaN</code> values are ignored.</p>

<code _o="241" _o-sc="11,0" _o-l="10" _o-e="16,3" _o-tl="-1" _o-s="10,0" style="block" _o-cl="0" id="5d98d863" lang="kotlin">df.min() // min of values per every comparable column
df.min { age and weight } // min of all values in `age` and `weight`
df.minFor { age and weight } // min of values per `age` and `weight` separately
df.minOf { (weight ?: 0) / age } // min of expression evaluated for every row
df.minBy { age } // DataRow with minimal `age`
</code>


<code _o="629" _o-sc="23,0" _o-l="22" _o-e="28,3" _o-tl="-1" _o-s="22,0" style="block" _o-cl="0" id="e5bd8aff" lang="kotlin">df.min()
df.age.min()
df.groupBy { city }.min()
df.pivot { city }.min()
df.pivot { city }.groupBy { name.lastName }.min()
</code>

<p _o="779" _o-sc="32,0" _o-l="32" _o-e="33,0" _o-tl="-1" _o-s="32,0" _o-cl="0" id="ed9e8e60">See <a _o="783" _o-sc="32,5" LinkStatus="UNKNOWN" _o-l="32" _o-e="32,50" _o-tl="-1" _o-s="32,4" href="statistics.md#groupby-statistics" _o-cl="4" id="b1b8126b">statistics</a> for details on complex data aggregations.</p>
</topic>