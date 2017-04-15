---
layout: post
title: "transition between mixture of substring lengths"
gif: assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_41.gif
date: 2017-04-14
---

# name data

![ss-name-data-34-pair-transitions_2.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_2.gif)

# generate names from longer sub-strings

# tally up the substrings of length 2

![ss-name-data-34-pair-transitions_5.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_5.gif)

![ss-name-data-34-pair-transitions_6.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_6.gif)

![ss-name-data-34-pair-transitions_7.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_7.gif)

![ss-name-data-34-pair-transitions_8.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_8.gif)

![ss-name-data-34-pair-transitions_9.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_9.gif)

![ss-name-data-34-pair-transitions_10.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_10.gif)

![ss-name-data-34-pair-transitions_11.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_11.gif)

![ss-name-data-34-pair-transitions_12.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_12.gif)

![ss-name-data-34-pair-transitions_13.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_13.gif)

![ss-name-data-34-pair-transitions_14.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_14.gif)

![ss-name-data-34-pair-transitions_15.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_15.gif)

How does the frequency of pairs beginning with \[OpenCurlyDoubleQuote]a\[CloseCurlyDoubleQuote] compare to the frequency of the letter \[OpenCurlyDoubleQuote]a\[CloseCurlyDoubleQuote] alone? I\[CloseCurlyQuote]m going to guess the frequency differs by about a factor of ~1/26:

![ss-name-data-34-pair-transitions_17.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_17.gif)

![ss-name-data-34-pair-transitions_18.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_18.gif)

![ss-name-data-34-pair-transitions_19.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_19.gif)

![ss-name-data-34-pair-transitions_20.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_20.gif)

![ss-name-data-34-pair-transitions_21.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_21.gif)

![ss-name-data-34-pair-transitions_22.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_22.gif)

![ss-name-data-34-pair-transitions_23.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_23.gif)

![ss-name-data-34-pair-transitions_24.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_24.gif)

Yep.

Sanity check: it should be the case that the sum of the counts for all pairs beginning with \[OpenCurlyDoubleQuote]a\[CloseCurlyDoubleQuote] is the same as the count for \[OpenCurlyDoubleQuote]a\[CloseCurlyDoubleQuote] alone:

![ss-name-data-34-pair-transitions_27.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_27.gif)

![ss-name-data-34-pair-transitions_28.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_28.gif)

Huh, there\[CloseCurlyQuote]s a slight difference. Oh, not all occurrences of \[OpenCurlyDoubleQuote]a\[CloseCurlyDoubleQuote] appear in a pair starting with \[OpenCurlyDoubleQuote]a\[CloseCurlyDoubleQuote]; sometimes \[OpenCurlyDoubleQuote]a\[CloseCurlyDoubleQuote] appears at the end of the name. So that likely accounts for the discrepancy.

Okay so I can scale the counts for letter pairs to be comparable to counts for individual letters. That means I can build a transition matrix from a combination of one and two letter transitions.

This transition matrix basically has a block structure down the diagonal. a->b transitions live in the top left block, and aa->bb transitions live in the bottom right. There are also transitions of the form aa->b which would be relevant for the end of the string. It\[CloseCurlyQuote]s prolly okay to ignore these?

This gives a way to have a Markov chain generated using multiple sizes of substrings, by providing a transition matrix with multiple lengths of substring transitions.

Hmmm, if the counts are scaled to be comparable, it may be reasonable to include transitions involving different length substrings

What is a  transiton saying:

x -> y   : x immediately followed by y, e.g. \[OpenCurlyDoubleQuote]a\[CloseCurlyDoubleQuote] immediately followed by \[OpenCurlyDoubleQuote]b\[CloseCurlyDoubleQuote]

xy -> uv    : xy immediately followed by uv, e.g. \[OpenCurlyDoubleQuote]ab\[CloseCurlyDoubleQuote] then \[OpenCurlyDoubleQuote]el\[CloseCurlyDoubleQuote]  (\[OpenCurlyDoubleQuote]abel\[CloseCurlyDoubleQuote])

x -> uv   : x immediately followed by uv, e.g. \[OpenCurlyDoubleQuote]k\[CloseCurlyDoubleQuote] then \[OpenCurlyDoubleQuote]ev\[CloseCurlyDoubleQuote] (\[OpenCurlyDoubleQuote]kev\[CloseCurlyDoubleQuote])

uv -> x    : e.g. \[OpenCurlyDoubleQuote]bo\[CloseCurlyDoubleQuote] then \[OpenCurlyDoubleQuote]b\[CloseCurlyDoubleQuote] (\[OpenCurlyDoubleQuote]bob\[CloseCurlyDoubleQuote])

What is the expected scaling for the count of x -> y to be comparable to the count of uv -> pq ?

e.g. 

a -> b    vs    a -> bc  

is equiv to

a -> b   AND    b -> c

so

p(a -> bc)   ==  p(a -> b) * p(b -> c)

but that is assuming p(bc) == p(b) * p(c), which it isn\[CloseCurlyQuote]t

![ss-name-data-34-pair-transitions_36.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_36.gif)

The disordered way would be: just combine substrings of various lengths without regard to order, only according to frequency of the substring itself:

![ss-name-data-34-pair-transitions_38.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_38.gif)

![ss-name-data-34-pair-transitions_39.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_39.gif)

![ss-name-data-34-pair-transitions_40.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_40.gif)

![ss-name-data-34-pair-transitions_41.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_41.gif)

![ss-name-data-34-pair-transitions_42.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_42.gif)

![ss-name-data-34-pair-transitions_43.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_43.gif)

![ss-name-data-34-pair-transitions_44.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_44.gif)

![ss-name-data-34-pair-transitions_45.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_45.gif)

![ss-name-data-34-pair-transitions_46.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_46.gif)

![ss-name-data-34-pair-transitions_47.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_47.gif)

![ss-name-data-34-pair-transitions_48.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_48.gif)

![ss-name-data-34-pair-transitions_49.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_49.gif)

![ss-name-data-34-pair-transitions_50.gif](../../../assets/2017/04/14/ss-name-data-34-pair-transitions-500px/ss-name-data-34-pair-transitions_50.gif)

