---
layout: post
current: post
cover:  assets/images/data-bg.jpg
navigation: True
title: What the hell is data?
date: 2020-09-19 10:00:00
tags: [Data Engineering]
class: post-template
subclass: 'post'
author: krishna
---

## A brief introduction 
<br />
Welcome to the first post of this blog, my name is Krishna and I’m currently working as a Data Engineer. I find data elusive and interesting at the same time and this blog is my attempt to make things clearer and understandable to me and I hope some of the content I put up here will be beneficial to you as well.

The general theme of this blog will be around focusing on concepts with emphasis on First Principles, use of illustrations and prospective story telling. In my view, to really understand a thing, you have to understand its parts and these parts usually can further be broken down to basic facts which hold true under a given set of constraints, using these facts to actually build further hypotheses on top of the basic facts. In order to do so, it’s really important to ask a lot of “Why” questions to get to the base facts of what you’re trying to learn. Illustrations will play a key role in helping us understand some trickier concepts which are difficult to understand through words. Finally, you’ll see some concepts explained through the help of stories for increased stickiness.


## Defining Data
<br />
So, in this introductory post we’ll begin by trying to understand what the hell is data?

If we ask Wikipedia that question, here’s what the page on Data has to say, “Data are characteristics or information of a phenomenon, usually numerical, that are collected through observation.”. For some reason I had trouble wrapping my head around this, so let’s try to simplify using an example.

Let’s introduce Sam here, Sam is 15 and he likes to wake up early and see the sun rise from his window. Each day he takes his notebook and notes down the exact time he actually sees the sun rise. He’s been doing this for the past one year every day. How do we define he’s doing? Sam has collected “Data” about a phenomenon (Sunrises) through observations from his window.
This data that Sam collected has been no use to him till now, but one fine day, out of curiosity he notices that the time at which the rises is very close in terms of minutes between say a week, but when looked through a broader scope of a month, he notices that the sun rises at a delayed time every month from summer to winter.
He decides to google the reason behind this strange pattern, reading this [Quora answer](https://www.quora.com/Why-does-the-Sun-set-at-different-times-and-places), he realizes it’s due the Axial tilt of the earth!

Do you see what happened here? Sam had been collecting “raw” sun rise time data as a pet peeve, but out of random curiosity he landed up on a real insight when he decided to analyze the data and found a strange pattern. This is the power of data, what seems to be a random collection of junk characters and numbers can actually provide great insights about the world around us. No wonder people describe data as the “new oil of the digital economy”.

### Math and computers.
<br />
If we look closely at how data is defined in the world of mathematics, the definition is quite or more similar with addition of properties to the kinds of data. Data can either be “Qualitative” or “Quantitative”. By Qualitative – it means how does the data describe something. By Quantitative – it means the numerical information which can be found within the data.
Now if you’re reading this article, most likely you have a background in software (if not, then great!), what’s really interesting is what do you actually mean by data in context of software or in the context of computers.

To put simply, data in the context of software/computers is still information collected through observations but represented digitally through just two digits – 0 and 1.
Hold up – how can you possibly represent complex information with just 0’s and 1’s?
To understand this at the fundamental level, let’s take an aside and talk about binary number systems. Binary number systems are made of binary digits - A binary digit is an entity that can either be 0 or 1.

So normally if you wanted to represent fifteen as a number in the decimal system – you’d type 15. But since binary number systems can only be in two digits (0’s and 1’s), a clever technique with exponents is used, see [Binary Number Systems](https://www.mathsisfun.com/binary-number-system.html) for a better understanding of how this works. Basically, we use exponents with base 2 to translate the number from decimal to binary. Focus on how when we have 0-9 digits to use, we only have to use 2 digits to represent 15 and realize that there’s repetition involved to cater to the need to represent the larger numbers. But when we add a constraint of using just 0 and 1 digits, we need a new way to involve repetition and that is achieved via the use of exponents with the base 2.

So, 15 in binary would be represented as 1111.
This cover’s numerical data, but what about text?
Another neat trick used here for textual data is the use of something called ASCII values, these are nothing but a map of characters to a numerical value which uniquely identifies a particular character. The character ‘h’ has an ASCII value of 104. Once we have this numerical value it’s straightforward to convert this to binary.
We’ll limit the scope of this discussion to just numerical and textual data but other forms data such as image, audio etc. rely on similar translation mechanisms to eventually have the base format for data representation as a mix of 0’s and 1’s.
A point to remember is that the binary number system really just acts as a great abstraction for computers to use. All kinds of data finally resolve to a bunch of 0’s and 1’s.

## Conclusion
<br />
In this post, we looked at the different ways data is defined based on the different fields we use Data to achive different things.
Stay tuned for more!
