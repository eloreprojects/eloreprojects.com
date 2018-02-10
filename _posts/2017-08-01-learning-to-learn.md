---
layout: post
title: "Learning To Learn"
categories: Development
description: A non-technical introduction to artificial intelligence.
keywords: ai
---

![How machine learning works in one (oversimplified) equation](/images/posts/development/ltl_1.png)

How machine learning works in one (oversimplified) equation

## Introduction

The very first and most audacious goal of computing has always been artificial intelligence. If you’ve paid attention to the software scene lately, you may have noticed its sensationalism once again. However this time, it’s different; artificial intelligence isn’t just a dream for nerds, it’s become a necessary reality. Almost every player in the industry has their eye on the benefits of artificial intelligence and some companies are putting some lofty statements out there.

    “The last 10 years have been about building a world that  is mobile-first…
    but in the next 10 years, we will shift to a world that is AI-first.”

    - Sundar Pichai, CEO of Google

However, artificial intelligence is a very broad term used to describe all sorts of decision making processes from if-then statements to sensor fusion. Describing all computer “thinking” as artificial intelligence is what turns the ultimate goal of computing into a meaningless buzzword. So what are we actually talking about during the recent “artificial intelligence” resurgence? What do we call the brainpower behind Google Translate knowing more languages than the Rosetta Stone or computers defeating the genius-level grandmasters of ancient board games?

The answer is machine learning (now with 100% more crude doodles!).

## Machine Learning

We’ll start by saying that machine learning is not a new concept. The idea’s for machine learning and neural networks have existed since the previous century and although they haven’t become technically useful until technology generally became better recently, their early creators had a very good idea of the potential that comes with machine learning, forecasting that the perceptron would be fundamental to all types of learning.

![](/images/posts/development/ltl_2.png)

What does any of this mean?? What’s a neural network?? Don’t worry, we’ll cover this soon.

I like to describe machine learning using an analogy:

Forget about computers altogether, and think about how you learned any kind of concept growing up. You probably learned how to do arithmetic in school (or some other educational setting) and remembered some core concepts (e.g. multiplication is repeated addition). You were able to learn from your previous experiences — namely your memories that involved multiplication. Whether your memories were of your teacher showing you how to do long division or your wrong answers while practicing division problems, pretty much any sort of memory contributed to your understanding of the concept and thinking process.

![](/images/posts/development/ltl_3.png)

Some broad generalizations that can be useful when discussing how computers relate to humans when thinking.

Thinking of learning in that sense (although not entirely accurate) is helpful for understanding how computers are able to learn. The ways that machines learn have been modeled after human brains learning from experience, with two main differences between a computer mind and a human mind:

1. Machines memories are in the form of data.
2. Machines can learn from the experience (i.e. the data) of other computers.


## Types of Learning

How machines (and humans) learn can be split into two main umbrellas. The first umbrella is called **supervised learning** — the type of learning most people are familiar with. Supervised learning involves learning from explicit rules or “right” answers. If you think back to the analogy of learning multiplication as a student, you probably remember doing exercises of something looking like “2 x 2 = 4” and having a teacher mark your answer of 8 as “correct”. We can think of this memory as data, specifically as **labeled data**.

*Data* might be starting to sound technical but it’s just a fancy way to describe a memory. Labeled data is a “memory” that has some kind of tag associated with it to describe its outcome to a computer. For example, if “2 x 2 = 4” had a label of “correct” then “4 x 4 = 19” would have a label of “incorrect”. Because computers can’t understand what the definition multiplication really means without an engineer making a program with explicit rules using code, it will have to teach itself what the use of the multiplication sign through examples of equations. We probably couldn’t have learned what the definition of multiplication was using the two equations above, but given enough equations that follow the format of the previous examples, a machine can theoretically learn through this process. We use supervised learning all the time in the software you and I use, such as spellcheck (*trained* using labeled data of correct words) and computer vision to detect cats (*trained* using labeled data of cats), which made use of millions, if not billions of data entries.

![](/images/posts/development/ltl_4.png)

Supervised learning at its finest — but this does raise a serious question about how machines taught evil things will be preprogrammed to do evil things (the reason why Mark Zuckerberg and Elon Musk are fighting on currently fighting on social media).

But what about if we didn’t have any labels denoting if the equation was correct or not? Turns out, that brings us two the second main type of learning called *unsupervised learning*. And believe it or not, but you’ve been doing plenty of unsupervised learning too (probably the most ubiquitous type of learning).

Your parents probably didn’t tell tell you the temperatures of every object (labeled data) for you to know that fire was hot. Instead, you noticed the patterns and behavior of fire from your memories of it without sticking your hand in it to confirm (this problem could be modeled using supervised learning but intuitively it isn’t). This human-level creativity and ability to develop an understanding of the world without supervision make unsupervised learning one of the biggest goals of both machine learning and artificial intelligence as a whole. A machine might not be able to understand multiplication in the example before without labels, but today’s computers are still able to detect patterns in other areas. For example, Google Photos and iCloud Photos can both notice the same unnamed faces reappearing in your images and can offer to take their names so you can ask Siri to show you photos of “Kevin” in a process that adds supervised learning (labelling “Kevin”) to unsupervised learning. Google Maps and Apple Maps can even reason to determine where your home and workplaces are without being told so (albeit somewhat creepily).

![](/images/posts/development/ltl_5.png)
Unsupervised learning at an early age. Note: the bigger human is irrelevant in this scenario.

## What’s Next?

This entry aims to be a comprehensive introduction to machine learning but only scratches the surface of the different types of learning. Many machine learning implementations are even combinations of different types of learning such as deep learning. One famous example of another type of learning is called *reinforcement learning*, in which machines continuously repeat a task and either give themselves rewards or punishments upon completion to determine an optimal strategy often organically. Reinforcement learning works great in certain projects like teaching a computer to dominate at 1980s Mario from no understanding of video games at all.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qv6UVOQ0F44?rel=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

A cool project that uses machine learning to play Mario at superhuman levels of clout.

In addition, its worth mentioning the “No Free Lunch Theorem” which essentially means that no one machine learning type of learning (or *algorithm*) will work in all scenarios. Somebody buying you free lunch isn’t always just a kind gesture; usually an ulterior motive with compromises and tradeoffs are a part of the meal.

![](/images/posts/development/ltl_6.png)

The No Free Lunch Theorem acted out with your sneaky friend and an even sneakier computer.

Your next steps to understand machine learning should focus on how it is implemented in modern software, the pre-requisites to understanding how machine learning works, and how to finally use machine learning in your own small projects using Python. Machine learning is one of the most revolutionary technologies to touch computers, and democratizing its benefits and knowledge is crucial to preventing (or creating) the Singularity.

![](/images/posts/development/ltl_7.jpeg)

Coming soon to a reality near you.