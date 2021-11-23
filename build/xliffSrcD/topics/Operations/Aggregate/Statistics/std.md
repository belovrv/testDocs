<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="std" title="std" _md-based="true"> 
<p _o="90" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="98343835">Computes the standard deviation of values.</p>
<p _o="134" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="715ef33e">Is available for numeric columns. Computed value has type <code _o="192" _o-sc="6,59" _o-l="6" _o-e="6,66" _o-tl="-1" _o-s="6,58" _o-cl="58" id="8822a994">Double</code>.</p>

<code _o="225" _o-sc="11,0" _o-l="10" _o-e="15,3" _o-tl="-1" _o-s="10,0" style="block" _o-cl="0" id="fdd4e303" lang="kotlin">df.std() // std of values per every numeric column
df.std { age and weight } // std of all values in `age` and `weight`
df.stdFor { age and weight } // std of values per `age` and `weight` separately, skips NA
df.stdOf { (weight ?: 0) / age } // std of expression evaluated for every row
</code>


<code _o="570" _o-sc="22,0" _o-l="21" _o-e="27,3" _o-tl="-1" _o-s="21,0" style="block" _o-cl="0" id="34769d61" lang="kotlin">df.std()
df.age.std()
df.groupBy { city }.std()
df.pivot { city }.std()
df.pivot { city }.groupBy { name.lastName }.std()
</code>

<p _o="720" _o-sc="31,0" _o-l="31" _o-e="32,0" _o-tl="-1" _o-s="31,0" _o-cl="0" id="c8240e53">See <a _o="724" _o-sc="31,5" LinkStatus="UNKNOWN" _o-l="31" _o-e="31,50" _o-tl="-1" _o-s="31,4" href="statistics.md#groupby-statistics" _o-cl="4" id="d207a932">statistics</a> for details on complex data aggregations.</p>
</topic>