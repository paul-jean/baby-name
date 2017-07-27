---
layout: post
title: "ss name data 40 name quality metric"
gif: assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_47.gif
date: 2017-07-27
---

# define a quality score for names

I need a way to objectively score a name I\[CloseCurlyQuote]ve generated. I\[CloseCurlyQuote]ve been using a metric I developed to sort the names I generate, using correlations between letters at increasing distances within the name, based on the typical frequencies of letters at that distance in database names.

The score had a bug in it though: the Partition  of the list of letters in the name being done here should depend on the correlationDistance parameter, but it\[CloseCurlyQuote]s hard-coded to \[OpenCurlyDoubleQuote]3\[CloseCurlyDoubleQuote] (prolly a copy-paste error):

![ss-name-data-40-name-quality-metric_4.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_4.gif)

The idea is to create a distance metric that captures how close a name is to typical patterns in database names. So it finds the frequencies of letters at distance 1, 2, 3, etc and generates a transition matrix for each of those distances:

![ss-name-data-40-name-quality-metric_6.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_6.gif)

![ss-name-data-40-name-quality-metric_7.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_7.gif)

![ss-name-data-40-name-quality-metric_8.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_8.gif)

![ss-name-data-40-name-quality-metric_9.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_9.gif)

![ss-name-data-40-name-quality-metric_10.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_10.gif)

![ss-name-data-40-name-quality-metric_11.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_11.gif)

![ss-name-data-40-name-quality-metric_12.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_12.gif)

![ss-name-data-40-name-quality-metric_13.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_13.gif)

That covers the pattern of how letters appear relative to one another, but it doesn\[CloseCurlyQuote]t cover the frequency of letters at specific positions in names. For example it\[CloseCurlyQuote]s probably unlikely that a name ends with the letter \[OpenCurlyDoubleQuote]z\[CloseCurlyDoubleQuote], but \[OpenCurlyDoubleQuote]z\[CloseCurlyDoubleQuote] may be more frequent at the beginning or middle of the name.

So the second part of the metric is to score the name by how commonly each letter appears at that position in database names.

![ss-name-data-40-name-quality-metric_16.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_16.gif)

![ss-name-data-40-name-quality-metric_17.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_17.gif)

![ss-name-data-40-name-quality-metric_18.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_18.gif)

![ss-name-data-40-name-quality-metric_19.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_19.gif)

![ss-name-data-40-name-quality-metric_20.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_20.gif)

The test of the metric is that it should be as large as possible for names from the database.

# letters at specific distances in a name

![ss-name-data-40-name-quality-metric_23.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_23.gif)

![ss-name-data-40-name-quality-metric_24.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_24.gif)

![ss-name-data-40-name-quality-metric_25.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_25.gif)

Letters directly next to each other are at distance = 1:

![ss-name-data-40-name-quality-metric_27.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_27.gif)

![ss-name-data-40-name-quality-metric_28.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_28.gif)

Letters with one letter between them are at distance = 2:

![ss-name-data-40-name-quality-metric_30.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_30.gif)

![ss-name-data-40-name-quality-metric_31.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_31.gif)

To get the frequency of letters distance 1, count the pairs that occur at distance 1:

![ss-name-data-40-name-quality-metric_33.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_33.gif)

![ss-name-data-40-name-quality-metric_34.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_34.gif)

![ss-name-data-40-name-quality-metric_35.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_35.gif)

![ss-name-data-40-name-quality-metric_36.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_36.gif)

![ss-name-data-40-name-quality-metric_37.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_37.gif)

![ss-name-data-40-name-quality-metric_38.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_38.gif)

![ss-name-data-40-name-quality-metric_39.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_39.gif)

![ss-name-data-40-name-quality-metric_40.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_40.gif)

![ss-name-data-40-name-quality-metric_41.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_41.gif)

![ss-name-data-40-name-quality-metric_42.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_42.gif)

![ss-name-data-40-name-quality-metric_43.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_43.gif)

![ss-name-data-40-name-quality-metric_44.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_44.gif)

![ss-name-data-40-name-quality-metric_45.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_45.gif)

![ss-name-data-40-name-quality-metric_46.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_46.gif)

![ss-name-data-40-name-quality-metric_47.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_47.gif)

![ss-name-data-40-name-quality-metric_48.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_48.gif)

![ss-name-data-40-name-quality-metric_49.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_49.gif)

![ss-name-data-40-name-quality-metric_50.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_50.gif)

![ss-name-data-40-name-quality-metric_51.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_51.gif)

![ss-name-data-40-name-quality-metric_52.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_52.gif)

![ss-name-data-40-name-quality-metric_53.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_53.gif)

![ss-name-data-40-name-quality-metric_54.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_54.gif)

![ss-name-data-40-name-quality-metric_55.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_55.gif)

![ss-name-data-40-name-quality-metric_56.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_56.gif)

![ss-name-data-40-name-quality-metric_57.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_57.gif)

![ss-name-data-40-name-quality-metric_58.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_58.gif)

After the transition matrix is memoized the correlation is several orders of magnitude faster:

![ss-name-data-40-name-quality-metric_60.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_60.gif)

![ss-name-data-40-name-quality-metric_61.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_61.gif)

![ss-name-data-40-name-quality-metric_62.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_62.gif)

![ss-name-data-40-name-quality-metric_63.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_63.gif)

Add another speed increase for the correlation score by using a dispatch table for the letter -> index conversion:

![ss-name-data-40-name-quality-metric_65.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_65.gif)

![ss-name-data-40-name-quality-metric_66.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_66.gif)

![ss-name-data-40-name-quality-metric_67.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_67.gif)

![ss-name-data-40-name-quality-metric_68.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_68.gif)

![ss-name-data-40-name-quality-metric_69.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_69.gif)

An extra 2x speed isn\[CloseCurlyQuote]t bad for such a simple change.

How should the correlation be normalized? It would be nice if it had minimum 0 and maximum 1.

What is the maximum correlation score of any pair of letters? The maximum is 1 if it\[CloseCurlyQuote]s the only case in the row of the transition matrix. The average case is 1/26, where each item in the row of the transition matrix is equal. The minimum is 0, where that letter pair has zero frequency.

Should the total correlation from a set of individual pair correlations be a sum or a product of the individual pairs?

The correlation score should be independent of the number of letters in the name. So somehow it needs to be normalized by the total number of pairs considered.

One possibility would be to sum the transition frequencies from each pair, and divide by n:

![ss-name-data-40-name-quality-metric_76.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_76.gif)

![ss-name-data-40-name-quality-metric_77.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_77.gif)

![ss-name-data-40-name-quality-metric_78.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_78.gif)

![ss-name-data-40-name-quality-metric_79.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_79.gif)

I only want to spend about a second to compute a bunch of these correlations as a test:

![ss-name-data-40-name-quality-metric_81.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_81.gif)

![ss-name-data-40-name-quality-metric_82.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_82.gif)

![ss-name-data-40-name-quality-metric_83.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_83.gif)

![ss-name-data-40-name-quality-metric_84.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_84.gif)

![ss-name-data-40-name-quality-metric_85.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_85.gif)

![ss-name-data-40-name-quality-metric_86.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_86.gif)

The average case is a frequency of 1/26 for any given pair correlation:

![ss-name-data-40-name-quality-metric_88.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_88.gif)

![ss-name-data-40-name-quality-metric_89.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_89.gif)

.... which is way out in the low tail of the distribution of scores.

The average of the distribution I just measured is more like 0.15.

What is the distribution of frequencies in the transition matrix?

![ss-name-data-40-name-quality-metric_93.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_93.gif)

![ss-name-data-40-name-quality-metric_94.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_94.gif)

![ss-name-data-40-name-quality-metric_95.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_95.gif)

![ss-name-data-40-name-quality-metric_96.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_96.gif)

![ss-name-data-40-name-quality-metric_97.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_97.gif)

![ss-name-data-40-name-quality-metric_98.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_98.gif)

The more accurate way to test this is to sample from the transition matrix using the frequencies of pairs occurring in actual database names.

![ss-name-data-40-name-quality-metric_100.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_100.gif)

![ss-name-data-40-name-quality-metric_101.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_101.gif)

![ss-name-data-40-name-quality-metric_102.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_102.gif)

![ss-name-data-40-name-quality-metric_103.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_103.gif)

The distribution of transition frequencies is much different when sampled using a representative sample of pairs occurring in actual names.

Computing the mean frequency again using this more realistic sampling:

![ss-name-data-40-name-quality-metric_106.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_106.gif)

![ss-name-data-40-name-quality-metric_107.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_107.gif)

This is more like the mean correlation score of ~0.15 I got above.

So the correlation score has an average case around 0.15, and is normalized to 1, and is distributed something like a normal distribution. The correlation score is a sum of pair transition frequencies, and each frequency in the sum is independent (I think) and identically distributed (I think), so the correlation score should be normally distributed (by the central limit theorem).

Okay so this seems like a decent correlation score:

![ss-name-data-40-name-quality-metric_111.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_111.gif)

![ss-name-data-40-name-quality-metric_112.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_112.gif)

![ss-name-data-40-name-quality-metric_113.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_113.gif)

![ss-name-data-40-name-quality-metric_114.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_114.gif)

![ss-name-data-40-name-quality-metric_115.gif](../../../assets/2017/07/27/ss-name-data-40-name-quality-metric-600px/ss-name-data-40-name-quality-metric_115.gif)

This is the average transition probability of all the transition pairs at distance d in the name.

