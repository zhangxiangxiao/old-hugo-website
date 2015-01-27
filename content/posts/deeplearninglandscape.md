---
title: "The Landscape of Deep Learning"
date: "2015-01-27"
description: "A personal view towards what current deep learning research is about."
categories: 
    - "deep learning"
---

This blog summarizes an answer I posted to a question regarding what kinds of research are there for deep learning, in [Zhihu](http://www.zhihu.com/question/27608272/answer/37318565), a Chinese equivalence of Quora. Surprisingly, that answer drew a lot of attention from many students and young researchers in China and it is currently ranked the second best answer in the subcategory of "deep learning". I hope the summarization here could offer my bit of thought to a broader audience by translating that answer to English. Your comments and advices are welcomed!

In my opinion, the popular deep learning area contains four main research trends. They include optimization, generalization, representation and applications. For each of them, there are both a practical aspect and a theoretical aspect. Let's take a closer look at each of them.

### Optimization

It seems that almost all problems in deep learning can be reduced to solving mathematical optimization problems. Therefore, numerical optimization is one of the most important research trend for deep learing.

On the practical side, the most popular method for optimization is still stochastic gradient descent. This extremely simple method seems so stable and robust that many research projects start with it and then end with it. Of course, a lot of tricks could be used to make it faster, such as momentum, psudo-Newton methods and adaptive learning rates. Apart from these, parallelization of optimization for deep models is also a hot topic, with many papers submitted to conferences in both machine learning and distributed systems.

However, on the theoretical side, the only clear subject we know about is convex optimization. The unfortunate fact that most deep learning models are non-convex poses a huge gap between the practical and theoretical sides in optimization. Motivated by this, some researchers start to dig into the properties of some commonly seen but also narrowly defined models and loss functions, trying to get some information regarding the properties of local optima produced by such non-convex optimization procedures.

### Generalization

Generalizability concerns whether the training error of a model could approximate the true average testing error on all possible sampling of a given problem's data. We can approximately think of it as the difference between training error and testing error. Before deep learing became popular, one major problem in machine learning has been about controlling the generalization error.

For practitioners, the generalization problem anticipated by many machine learning researchers simply did not occur. On one hand this is due to the huge scale of datasets we have in this "Big Data" era. On the other hand, the development of high-performance computing devices such as GPUs enabled us to apply new regularization methods such as Dropout and DropConnect and heavy data augmentation techniques. Whether there are more effective regularization methods is one interesting topic for reseachers. Some ideas include adversarial learning and utlization of extra unlabeled samples.

For theorists, the effectiveness of deep learning has put heavy doubt on the theories of PAC-learning. All of the theories in this style are about "upper-bounds of upperbounds of upper-bounds...", for which the essence only concerns two kinds of statistical concepts -- concentration inequalities and complexity measurement. Practitioners have shown that these theories have very unrealistic estimation of generalization errors for real-world applications. Personally I believe the current gap betwen practitioners and theorists must be closed. It really should not have been like this, especially when the research in functional analysis is already pretty complete. I also feel that to make advancement in this, we need to better understand the theory in representation of deep learning models, which I will discuss in the following.

### Representation

Representation is a concept recently proposed by researchers in deep learning. For me, representation concerns the relationship between deep learning models and the problems they try to solve. Therefore, the questions about representation are bi-directional: one one hand, we want to know that given a deep learning model what kind of solutions to problems it can represent; on the other hand, we can also ask whether there exists a deep learning model to produce some representation for solving a given problem.

There are two mainstreams on the practical side. Those who deeply belive in unsupervised learning keep finding better objectives and criteria so that machines can learn to represent by themselves. These include deep belief networks, (restricted) Boltzmann machines, sparse coding and auto-encoders. In the second mainstream, researchers facing practical problems try to design deep learning models to solve them by intuition or inspiration from other disciplines. Some successful examples are convolutional networks for vision and speech, recurrent neural networks that can act upon input, and reinforcement learning models able to play games. Most of the deep learning researchers are in this trend, and it does give them the maximum impact possible.

However, we really do not have much to say about any theory concerning representation, except for some inspirational ideas borrowed from coginitive psychology or neural science. This is mostly because the theory of representation is drastically different for different problems. The only thing we currently can do now is to think whether and how humans could solve a problem, and then design a model to reduce it to a learning process. This is essentially an immitation game, which is a philosophical definition of intelligence proposed by Alan Turing in his 1950 paper "Computing Machinery and Intelligence". Intuitively I also doubt the feasibility of an ultimate representation theory, since it feels like a Laplace's demon whose existence would draw unsolvable paradoxes to the real world.

### Applications

The development of deep learning accompanies its revolutionization of other fields. In the past few years, deep learning has been something like a biased "dare or not" game -- if you dare to try, there chance of success is most likely guaranteed. Of course, this benefits largely from the explosion on the amount of data, and the availability of more powerful computational resources. At the same time, the knowledge accumulated from exploring deep learning and neural network in the past 30 years also plays an important role.

In the future, deep learning would continue to solve all kinds of recognition problems including vision (image classification, image segmentation, computational photography), speech (speech recognition), natural language processing (text understanding). At the same, we may see some breakthroughs on machine's ability in acting upon data, like describing an image using text, speech synthesis, automated translation and paragraph summarization. Deep learning may also help us to find approximated solutions to NP-hard problems when inputs are constrained to a limited set. All of these are very hot topics in applications of deep learning, and they can eventually bring huge industrial benefits.
