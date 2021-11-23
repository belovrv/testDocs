<?xml version='1.0' encoding='UTF-8'?><topic xsi:noNamespaceSchemaLocation="https://resources.jetbrains.com/stardust/topic.v2.xsd" meta-keywords="" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" id="mean" title="mean" _md-based="true"> 
<p _o="91" _o-sc="4,0" _o-l="4" _o-e="5,0" _o-tl="-1" _o-s="4,0" _o-cl="0" id="49163c7b">Computes the mean of values.</p>
<p _o="121" _o-sc="6,0" _o-l="6" _o-e="7,0" _o-tl="-1" _o-s="6,0" _o-cl="0" id="8c7347ca">Is available for numeric columns. Computed value has type <code _o="179" _o-sc="6,59" _o-l="6" _o-e="6,66" _o-tl="-1" _o-s="6,58" _o-cl="58" id="582e394c">Double</code>. Use <code _o="193" _o-sc="6,73" _o-l="6" _o-e="6,80" _o-tl="-1" _o-s="6,72" _o-cl="72" id="71d4d418">skipNA</code> flag to skip <code _o="215" _o-sc="6,95" _o-l="6" _o-e="6,100" _o-tl="-1" _o-s="6,94" _o-cl="94" id="5f274909">null</code> and <code _o="226" _o-sc="6,106" _o-l="6" _o-e="6,110" _o-tl="-1" _o-s="6,105" _o-cl="105" id="e3482018">NaN</code> values.</p>

<code _o="264" _o-sc="11,0" _o-l="10" _o-e="15,3" _o-tl="-1" _o-s="10,0" style="block" _o-cl="0" id="bf0c877b" lang="kotlin">df.mean() // mean of values per every numeric column
df.mean(skipNA = true) { age and weight } // mean of all values in `age` and `weight`, skips NA
df.meanFor(skipNA = true) { age and weight } // mean of values per `age` and `weight` separately, skips NA
df.meanOf { (weight ?: 0) / age } // median of expression evaluated for every row
</code>


<code _o="660" _o-sc="22,0" _o-l="21" _o-e="27,3" _o-tl="-1" _o-s="21,0" style="block" _o-cl="0" id="a0bda388" lang="kotlin">df.mean()
df.age.mean()
df.groupBy { city }.mean()
df.pivot { city }.mean()
df.pivot { city }.groupBy { name.lastName }.mean()
</code>

<p _o="815" _o-sc="31,0" _o-l="31" _o-e="32,0" _o-tl="-1" _o-s="31,0" _o-cl="0" id="3892eb00">See <a _o="819" _o-sc="31,5" LinkStatus="UNKNOWN" _o-l="31" _o-e="31,50" _o-tl="-1" _o-s="31,4" href="statistics.md#groupby-statistics" _o-cl="4" id="de042f9d">statistics</a> for details on complex data aggregations.</p>
</topic>