<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="median" title="median" _md-based="true"> 
<p _o="93" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="f1accc9d">Computes the median of values.</p>
<p _o="125" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="875647e0">Is available for <code _o="142" _o-sc="6,18" _o-l="6" _o-e="6,29" _o-tl="-1" _o-s="6,17" _o-cl="17" id="b77bfa03">Comparable</code> columns. <code _o="164" _o-sc="6,40" _o-l="6" _o-e="6,45" _o-tl="-1" _o-s="6,39" _o-cl="39" id="55b7790d">null</code> and <code _o="175" _o-sc="6,51" _o-l="6" _o-e="6,55" _o-tl="-1" _o-s="6,50" _o-cl="50" id="8afb6618">NaN</code> values are ignored.</p>

<code _o="227" _o-sc="11,0" _o-l="10" _o-e="15,3" _o-tl="-1" _o-s="10,0" style="block" _o-cl="0" id="fd7f04a2" lang="kotlin">df.median() // median of values per every comparable column
df.median { age and weight } // median of all values in `age` and `weight`
df.medianFor { age and weight } // median of values per `age` and `weight` separately
df.medianOf { (weight ?: 0) / age } // median of expression evaluated for every row
</code>


<code _o="592" _o-sc="22,0" _o-l="21" _o-e="27,3" _o-tl="-1" _o-s="21,0" style="block" _o-cl="0" id="fa8cd8f3" lang="kotlin">df.median()
df.age.median()
df.groupBy { city }.median()
df.pivot { city }.median()
df.pivot { city }.groupBy { name.lastName }.median()
</code>

<p _o="757" _o-sc="31,0" _o-l="31" _o-e="32,0" _o-tl="-1" _o-s="31,0" _o-cl="0" id="d82e81cd">See <a _o="761" _o-sc="31,5" LinkStatus="UNKNOWN" _o-l="31" _o-e="31,50" _o-tl="-1" _o-s="31,4" href="statistics.md#groupby-statistics" _o-cl="4" id="ce7079bd">statistics</a> for details on complex data aggregations.</p>
</topic>