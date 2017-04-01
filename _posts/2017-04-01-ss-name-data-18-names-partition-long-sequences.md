---
layout: post
title: "Generating names waaaay faster from one partitioned Markov sequence"
gif: assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_60.gif
date: 2017-04-01
---

# name data

![ss-name-data-18-names-partition-long-sequences_2.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_2.gif)

# generate names by partitioning a long sequence of letters

![ss-name-data-18-names-partition-long-sequences_4.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_4.gif)

![ss-name-data-18-names-partition-long-sequences_5.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_5.gif)

![ss-name-data-18-names-partition-long-sequences_6.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_6.gif)

![ss-name-data-18-names-partition-long-sequences_7.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_7.gif)

# generate ~1000 names from a long sequence

![ss-name-data-18-names-partition-long-sequences_9.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_9.gif)

![ss-name-data-18-names-partition-long-sequences_10.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_10.gif)

# generate 1000 separate sequences

![ss-name-data-18-names-partition-long-sequences_12.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_12.gif)

![ss-name-data-18-names-partition-long-sequences_13.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_13.gif)

# much slower to generate 1000 separate sequences, by orders of magnitude

how do the quality of names compare?

![ss-name-data-18-names-partition-long-sequences_15.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_15.gif)

![ss-name-data-18-names-partition-long-sequences_16.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_16.gif)

![ss-name-data-18-names-partition-long-sequences_17.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_17.gif)

![ss-name-data-18-names-partition-long-sequences_18.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_18.gif)

![ss-name-data-18-names-partition-long-sequences_19.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_19.gif)

![ss-name-data-18-names-partition-long-sequences_20.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_20.gif)

# make a more generalized sorting function that I can use with the ranked coordinates

![ss-name-data-18-names-partition-long-sequences_22.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_22.gif)

![ss-name-data-18-names-partition-long-sequences_23.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_23.gif)

![ss-name-data-18-names-partition-long-sequences_24.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_24.gif)

![ss-name-data-18-names-partition-long-sequences_25.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_25.gif)

![ss-name-data-18-names-partition-long-sequences_26.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_26.gif)

![ss-name-data-18-names-partition-long-sequences_27.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_27.gif)

![ss-name-data-18-names-partition-long-sequences_28.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_28.gif)

name quality ~ 1/d where d is the distance from the origin in ranked coordinates

![ss-name-data-18-names-partition-long-sequences_30.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_30.gif)

![ss-name-data-18-names-partition-long-sequences_31.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_31.gif)

The sum of various correlation scores isn\[CloseCurlyQuote]t normalized properly, but at least a larger correlation sum is better I guess? Unless there\[CloseCurlyQuote]s an optimal value somehow.

# top 30 names from a long sequence

Top 30 names by this sorting method:

![ss-name-data-18-names-partition-long-sequences_35.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_35.gif)

![ss-name-data-18-names-partition-long-sequences_36.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_36.gif)

And bottom 30

![ss-name-data-18-names-partition-long-sequences_38.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_38.gif)

![ss-name-data-18-names-partition-long-sequences_39.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_39.gif)

# top 30 names from individual names

![ss-name-data-18-names-partition-long-sequences_41.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_41.gif)

![ss-name-data-18-names-partition-long-sequences_42.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_42.gif)

![ss-name-data-18-names-partition-long-sequences_43.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_43.gif)

![ss-name-data-18-names-partition-long-sequences_44.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_44.gif)

# is there a difference in the distribution of quality scores between the two?

![ss-name-data-18-names-partition-long-sequences_46.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_46.gif)

![ss-name-data-18-names-partition-long-sequences_47.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_47.gif)

![ss-name-data-18-names-partition-long-sequences_48.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_48.gif)

![ss-name-data-18-names-partition-long-sequences_49.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_49.gif)

![ss-name-data-18-names-partition-long-sequences_50.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_50.gif)

![ss-name-data-18-names-partition-long-sequences_51.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_51.gif)

# need better statistics, so generate more names to test

![ss-name-data-18-names-partition-long-sequences_53.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_53.gif)

![ss-name-data-18-names-partition-long-sequences_54.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_54.gif)

![ss-name-data-18-names-partition-long-sequences_55.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_55.gif)

![ss-name-data-18-names-partition-long-sequences_56.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_56.gif)

![ss-name-data-18-names-partition-long-sequences_57.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_57.gif)

![ss-name-data-18-names-partition-long-sequences_58.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_58.gif)

![ss-name-data-18-names-partition-long-sequences_59.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_59.gif)

![ss-name-data-18-names-partition-long-sequences_60.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_60.gif)

The distributions are qualitatively similar. The names from separate sequences seem to be skewed a bit toward lower scores (more score counts in the lower score bins), and names from a partitioned long sequence are skewed toward higher scores (slightly fatter tail).

Why would there be a difference between these techniques? The Markov chain starts from a random letter when it generates a given sequence. But the first letter in the names from the long partitioned sequence are based on the transition probability from the letter before them in the sequence. So the first letter of the partitioned names tends to have a high transition weight, which means that first letter at least occurs fairly frequently in actual names. So the starting letter of the partitioned names probably has a higher letter rank than random letters do.

This is easy to test actually ...

The ranks of first letters in 5-letter names:

![ss-name-data-18-names-partition-long-sequences_65.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_65.gif)

![ss-name-data-18-names-partition-long-sequences_66.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_66.gif)

The ranks for the first letter:

![ss-name-data-18-names-partition-long-sequences_68.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_68.gif)

![ss-name-data-18-names-partition-long-sequences_69.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_69.gif)

![ss-name-data-18-names-partition-long-sequences_70.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_70.gif)

![ss-name-data-18-names-partition-long-sequences_71.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_71.gif)

![ss-name-data-18-names-partition-long-sequences_72.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_72.gif)

![ss-name-data-18-names-partition-long-sequences_73.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_73.gif)

![ss-name-data-18-names-partition-long-sequences_74.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_74.gif)

![ss-name-data-18-names-partition-long-sequences_75.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_75.gif)

![ss-name-data-18-names-partition-long-sequences_76.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_76.gif)

![ss-name-data-18-names-partition-long-sequences_77.gif](../../../assets/2017/04/01/ss-name-data-18-names-partition-long-sequences-500px/ss-name-data-18-names-partition-long-sequences_77.gif)

Hah nope it\[CloseCurlyQuote]s just the opposite. The first letter rank is evenly distributed for the individual sequence names, and weighted more heavily to lower rank for the long sequence names. So the internal letter transitions from the long sequence actually get penalized in the partitioned sequence names. But there must be a compensating factor making the partitioned names overall slightly higher score.

Anyway the fatter tail on the long partitioned sequence names is actually great news. It means I can generate names orders of magnitude faster, and even slightly improve the quality of the names!

