---
title: "On April Fool's: What is Wrong with RNN?"
date: "2015-04-01"
description: "From Google's April Fool surprise to why RNNs are used in a wrong way today."
categories:
    - "deep learning"
---

Google's April fool surprise: reading characters in reverse order (https://com.google/).

It happened to be the case that the character order in Crepe (https://github.com/zhangxiangxiao/Crepe) is also reversed.

The original thought was that aligning the end of a document to a fixed position (in this case at the beginning) could make it easier for the fully-connected layers to associate meaning with the ending context window.

This may have the effect of biasing classification towards the end reading of a text, which has a somewhat distant relationship with how recurrent neural network representation can be used for classification, since it decays the influence of document at the beginning but not so much at the end.

However, later I did (only) one experiment by not reversing the character order for ending alignment, and the classification result did not change in anyway that is statistically significant.

This was quite though-provoking for me since it might mean that decaying influence like in RNNs is probably a bad thing, or at least useless. Otherwise, why do we need bi-directional RNNs? But then again, if you are using a bi-directional RNN for contextual information, why don't you just use a convolutional network who naturally associates a context for you?

Then, I went deeper in thought and started to believe that recurrent neural network is sometimes used in a wrong way in the community. Somehow regardless of situation, some researchers take RNNs for granted as the best tool for model sequences (including text, audio, time series, etc). Let me explain why this may not always make sense intuitively.

What is wrong here is that in most cases the sequence is presented as a whole, but the way RNN models them is by pretending the future values of a sequence is unknown and adapting its internal representation by what is seen so far. Why then, do we need to pretend the future sequence is unknown while in reality it is presented to you as a whole? This apparently does not make sense. The fact that bi-directional RNN gives a performance boost to various sequence modeling tasks is also an evidence for what I am arguing here.

Now we know the wrong, how do we correct it? Well, the answer is plain and simple: use a convolutional network instead! I even start to believe that convolutional network is the ultimate solution to perception and recognition, as long as the data span a time or space dimension.

Of course, not all sequences could be presented as whole, especially if the target is to produce actions (such as popping out words for translation, making a robot arm to move, etc). In this case to know both the past and the future may not be possible. Then, if you think even further, recurrent neural network is pretty similar to reinforcement learning -- the difference is that RNNs try to model the past, but RL tries to model the future. This could be the case in which RNN and RL could really shine: produce actions when an artificial agent has already perceived or recognized.

Putting all these pieces together, I do think in the future state-of-the art A.I. system should use convolutional networks as their perceptive or recognitive part, and a combined form of RNN and RL as the action-producing part. To make this system works well, some memory part might be needed (oh, you want to tell me DeepMind is likely working on this?)

By the way, today is April Fool's. I am not responsible for whatever I say here. :P
