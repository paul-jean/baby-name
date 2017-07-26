---
layout: post
title: "ss name data 41 transition tensor"
gif: assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_64.gif
date: 2017-07-26
---

# transition tensor for names length \[OpenCurlyDoubleQuote]l\[CloseCurlyDoubleQuote]

The correlation score I defined previously was the average transition probability of all the pairs at distance d in the name:

![ss-name-data-41-transition-tensor_3.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_3.gif)

![ss-name-data-41-transition-tensor_4.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_4.gif)

![ss-name-data-41-transition-tensor_5.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_5.gif)

![ss-name-data-41-transition-tensor_6.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_6.gif)

![ss-name-data-41-transition-tensor_7.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_7.gif)

But I realized this does not encode the position of the letters in the name, only the distance between letters. The transition probabilities of the pairs probably depends on the position of the letters in the name.

So there is a transition tensor for names of length \[OpenCurlyDoubleQuote]l\[CloseCurlyDoubleQuote]:

![ss-name-data-41-transition-tensor_10.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_10.gif)

![ss-name-data-41-transition-tensor_11.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_11.gif)

where 

	l	length of name			3

	i	position of first letter		1

	j	position of second letter	4

	a	first letter			\[OpenCurlyDoubleQuote]o\[CloseCurlyDoubleQuote]

	b	second letter			\[OpenCurlyDoubleQuote]r\[CloseCurlyDoubleQuote]	

For a name of length 6:

![ss-name-data-41-transition-tensor_14.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_14.gif)

![ss-name-data-41-transition-tensor_15.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_15.gif)

![ss-name-data-41-transition-tensor_16.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_16.gif)

![ss-name-data-41-transition-tensor_17.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_17.gif)

![ss-name-data-41-transition-tensor_18.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_18.gif)

![ss-name-data-41-transition-tensor_19.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_19.gif)

distance 1

![ss-name-data-41-transition-tensor_21.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_21.gif)

![ss-name-data-41-transition-tensor_22.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_22.gif)

max value for name length:

![ss-name-data-41-transition-tensor_24.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_24.gif)

![ss-name-data-41-transition-tensor_25.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_25.gif)

dimensions of the array:

dim	var	min	max

1	L	1	15

2	i	1	L	max(L) = 15

3	j	1	L	max(L) = 15

4	\[Alpha]	1	26

5	\[Beta]	1	26	

![ss-name-data-41-transition-tensor_27.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_27.gif)

![ss-name-data-41-transition-tensor_28.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_28.gif)

![ss-name-data-41-transition-tensor_29.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_29.gif)

![ss-name-data-41-transition-tensor_30.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_30.gif)

![ss-name-data-41-transition-tensor_31.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_31.gif)

![ss-name-data-41-transition-tensor_32.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_32.gif)

![ss-name-data-41-transition-tensor_33.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_33.gif)

![ss-name-data-41-transition-tensor_34.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_34.gif)

![ss-name-data-41-transition-tensor_35.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_35.gif)

![ss-name-data-41-transition-tensor_36.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_36.gif)

all letter pairs at each distance

![ss-name-data-41-transition-tensor_38.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_38.gif)

![ss-name-data-41-transition-tensor_39.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_39.gif)

![ss-name-data-41-transition-tensor_40.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_40.gif)

![ss-name-data-41-transition-tensor_41.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_41.gif)

![ss-name-data-41-transition-tensor_42.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_42.gif)

![ss-name-data-41-transition-tensor_43.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_43.gif)

![ss-name-data-41-transition-tensor_44.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_44.gif)

![ss-name-data-41-transition-tensor_45.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_45.gif)

![ss-name-data-41-transition-tensor_46.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_46.gif)

![ss-name-data-41-transition-tensor_47.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_47.gif)

![ss-name-data-41-transition-tensor_48.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_48.gif)

![ss-name-data-41-transition-tensor_49.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_49.gif)

![ss-name-data-41-transition-tensor_50.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_50.gif)

![ss-name-data-41-transition-tensor_51.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_51.gif)

Each transition matrix needs to be row-normalized: each row should sum to 1

![ss-name-data-41-transition-tensor_53.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_53.gif)

![ss-name-data-41-transition-tensor_54.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_54.gif)

![ss-name-data-41-transition-tensor_55.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_55.gif)

![ss-name-data-41-transition-tensor_56.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_56.gif)

![ss-name-data-41-transition-tensor_57.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_57.gif)

![ss-name-data-41-transition-tensor_58.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_58.gif)

![ss-name-data-41-transition-tensor_59.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_59.gif)

![ss-name-data-41-transition-tensor_60.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_60.gif)

![ss-name-data-41-transition-tensor_61.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_61.gif)

transition matrix for length 6 names at distance 1 (adjacent letters):

![ss-name-data-41-transition-tensor_63.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_63.gif)

![ss-name-data-41-transition-tensor_64.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_64.gif)

transition matrices for letter positions i and j:

![ss-name-data-41-transition-tensor_66.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_66.gif)

![ss-name-data-41-transition-tensor_67.gif](../../../assets/2017/07/26/ss-name-data-41-transition-tensor-600px/ss-name-data-41-transition-tensor_67.gif)

