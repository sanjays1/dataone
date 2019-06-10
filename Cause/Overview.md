---
title: "Overview"
date: 2019-06-06T18:01:45-04:00
draft: false
weight: 5
---

Is drinking red wine good for you? Is reducing taxes a good way to spur the economy? What actually causes liver cancer? Some of the most fundamental questions we ask attempt to attribute a reason to an outcome.  (ie. a cause to an effect.) By carefully examining data and applying data science principles we can start to find answers to some of these questions. 

Let's look at some reports that claim to have answers to these cause and effect questions. In early 2019, University of Michigan's Health Lab published an article summarizing an experimental study they had conducted with the following headline: **Moderate Alcohol Intake Associated with Less Chronic Pain, Depression.** 

![This image is a picture of the article posted by the University of Michigan. ](michigan.png)

In another article, the National Bureau of Economic Reserach (NBER) summarized a recent study that it had done and claimed that based on historical trends regarding tax rates and economic growth, future tax rate cuts would raise long-term growth. 

![This image is a picture of the article posted by NBER. ](tax.png)

How are researchers able to make these type of conclusions? By carefully observing the data, finding associations within the data, and drawing appropriate conclusions. 

### Observational Studies 

The past two studies were **observational studies**. An **observational study** is one in which scientists make conclusions based on data that they have observed but had no hand in generating. 

In both the Michigan and NBER study, scientists didn't actually create the data that they used to draw their conclusions. To clarify, Michigan researchers didn't force anyone to drink alcohol, (because that would be unethical). Similarily, NBER researchers have absolutely no control over the national tax rate, they instead observed data in the past and used it to fuel future predictions. 

The components of an observational studies can be broken down into three groups: 

* The **population** that's being observed
* The **treatment** that's being applied 
* the **outcome** of the study 

For Michigan's Alcohol study the **population** was the human beings they gathered data on, the **treatment** was the amount of alcohol that was being consumed, and the **outcome** was the reported symptoms by the people observed in the study. 

The practice of observing data is very common in data science, *very rarely* are data scientists the ones actively creating the data that they are doing data science on. 

### Asking Questions

When observing data, there's two "levels" of questioning that should be asked when attributing a cause to an effect: 

1. Is there a **relationship** between the treatment and the outcome?
2. Did the treatment **cause** the outcome? 

Let's take these levels of questioning and apply it to the University of Michigan's study. The quote below from the academic paper summarizes the conclusions of the study 

> Moderate alcohol users reported significantly lower FM symptoms (widespread pain and symptom severity), pain severity, interference, anxiety, depression, and catastrophizing, and they reported higher physical function.

Is there a **relationship** between moderal alcohol consumption and lower Fibromyalgia symptoms? According to the summary statement given above, yes it does seem like there is probably some sort of relationship. 

Now does alcohol consumption **cause** a reduction in Fibromyalgia symptoms? This is a actually a much harder question to answer, even with all the research done by The University of Michigan.  

Proving a cause and an effect, that a treatment directly causes an outcome, can be very difficult to prove, particulary with observational studies. This is due to the presence of **confounding variables**.

### Confounding variables

Another statistics term that's used to describe an association between a treatment and an outcome, is **correlation**. Unfortunately just because two things are **correlated** doesn't mean they cause one or the other. 

Looking at the data of household families and SAT scores, there actually is a strong positive **correlation** between the amount of televisions a family has and the SAT score of the children in that family. Does that mean that parents should try buying more TVs to bosts their child's test score? 

No, unsuprisingly having 5 TVs doesn't mean you'll get a 1600 on the SAT. While there is indeed a strong positive correlation between TVs and SAT scores, what's actually causing high SAT scores is the household income of the family. Wealthy families tend to score better on the SATs because their kids tend to go to better schools and have access to better resources. 

The wealth of families acts as a **confounding** variable here, being the real treatment that drives an observed outcome. Similarily, it would be incorrect to claim with 100% confidence that it's alcohol conumption that's driving lower pain symptoms. The type of person who drinks a glass of red wine every day may also be someone who has more time to actively relax, which could possibly be the confounding variable driving our outcome.  

Be careful to watch out for confounding variables when attributing a cause to an effect, especially in observed data! 





