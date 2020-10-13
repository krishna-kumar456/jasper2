---
layout: post
current: post
cover:  assets/images/spark.png
navigation: True
title: Effecient joins on array columns - Apache Spark
date: 2020-10-13 10:30:00
tags: [Data Engineering]
class: post-template
subclass: 'post'
author: krishna
---

## A Peculiar Situation
<br />


A few weeks back at work, I came across a peculiar problem which goes something like this. Within one of the workloads, I had to join two tables in Spark with one table having the join column of the type Array<Int>.


The tables were moderate in size, while trying to process the workload I noticed Spark was preparing to run around 200000 tasks and the whole workload took close to 2 hours to complete. This situation was puzzling to me. Why would Spark want to create so many tasks for moderately sized workloads.

I opened up Spark UI and right there I could see a stage displaying a logical plan involving a Cartesian Product while resolving the join within the stage. Okay, Why would there be a Cartesian Product within the logical plan? Maybe something to do with my join condition containing array_contains.

Investigating further (multiple google searches) got me toa JIRA link on Apache Spark. So apparently, if you choose to use array_contains within the join, a cartesian product will appear in your logical plan against the join, this is due to the way array_contains transformation is implemented at the Optimizer level.

Thanks to Nikolas Vanderhoof, if you manually apply the optimization as follows.
A join like this:

```

left.join(
  right,
  array_contains(left("arr"), right("value")) // Cartesian product in logical plan
)
```

will produce the same results as:

```

{
  val leftPrime = left.withColumn("exploded_arr", explode(col("arr")))

  leftPrime.join(
    right,
    leftPrime("exploded_arr") === right("value") // Fast equijoin
  ).drop("exploded_arr").distinct
}
```

Spark would use an equijoin and my workload execution time reduced from 2 hours to 5 mins.



