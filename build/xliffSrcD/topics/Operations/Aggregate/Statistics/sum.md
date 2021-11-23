<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="sum" title="sum" _md-based="true"> 
<p _o="90" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="f1d20243">Computes the sum of values.</p>
<p _o="119" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="ee8ad6e0">Is available for numeric columns. <code _o="153" _o-sc="6,35" _o-l="6" _o-e="6,40" _o-tl="-1" _o-s="6,34" _o-cl="34" id="5acc3c60">null</code> and <code _o="164" _o-sc="6,46" _o-l="6" _o-e="6,50" _o-tl="-1" _o-s="6,45" _o-cl="45" id="ac14f51d">NaN</code> values are ignored.</p>

<code _o="219" _o-sc="11,0" _o-l="10" _o-e="15,3" _o-tl="-1" _o-s="10,0" style="block" _o-cl="0" id="7f42fe57" lang="kotlin">df.sum() // sum of values per every numeric column
df.sum { age and weight } // sum of all values in `age` and `weight`
df.sumFor { age and weight } // sum of values per `age` and `weight` separately
df.sumOf { (weight ?: 0) / age } // sum of expression evaluated for every row
</code>


<code _o="554" _o-sc="22,0" _o-l="21" _o-e="26,3" _o-tl="-1" _o-s="21,0" style="block" _o-cl="0" id="b86cf5f7" lang="kotlin">df.age.sum()
df.groupBy { city }.sum()
df.pivot { city }.sum()
df.pivot { city }.groupBy { name.lastName }.sum()
</code>

<p _o="695" _o-sc="30,0" _o-l="30" _o-e="31,0" _o-tl="-1" _o-s="30,0" _o-cl="0" id="b6fe232">See <a _o="699" _o-sc="30,5" LinkStatus="UNKNOWN" _o-l="30" _o-e="30,50" _o-tl="-1" _o-s="30,4" href="statistics.md#groupby-statistics" _o-cl="4" id="d485b1c3">statistics</a> for details on complex data aggregations.</p>
</topic>