+++
title = "Philosophy"
weight = 1
disableToc = false
+++

## My goal

In my case, with experience comes... dissatisfaction with technical state of projects I've worked with.

{{% notice style="tip" title="Nathan Myhrvold" %}}
Software is a gas.
{{% /notice %}}

The quote above is very true for lots of projects and not only in aspect of hardware usage, but also in aspect of error 
capacity. If there is a lot of space for errors, you'll see this space filled with errors sooner or later. It means that 
huge software, especially large games of AAA level, are plagued with errors and inefficiency on the multiple levels. And
it makes me sad, very sad.

{{% notice style="tip" title="Goal" %}}
My goal is to make game software engineering better by introducing techniques that limit space for errors and make it 
easier to search for them and analize them.
{{% /notice %}}

## My design philosophy

I've started working with data-driven software design approach in 2020 when I joined 
[Press Fire Games](https://www.pressfire.com/). Althrough their approach was not perfect, I've started thinking about
Entity-Component-System and data-driven paradigm as a good alternative to classical object-oriented approach. 
Data-driven approaches, including ECS but not limiting to it, provide several advantages:

{{% notice style="info" title="Limited capacity for errors" %}}
Data-driven approaches are usually more strict and have more requirements for code than classic object-oriented 
approaches. Developer is responsible for designing data structures and their processing units, and there is not that 
much space for design fantasies, therefore, not much space for errors.
{{% /notice %}}

{{% notice style="info" title="Strict data and logic separation" %}}
Separating data from logic is usually a good idea in system design, because it makes it easier to process data in 
different contexts without adding unnecessary dependencies. Of course, it might come with optimization concerns, but 
personally I don't think it is worth making archetecture worse for small optimizations.
{{% /notice %}}

{{% notice style="info" title="Easier CPU parallelism" %}}
When program is centered around data and its processing pipeline, it is much easier to execute this pipeline in 
parallel. We know exactly which pipeline node processes which data, therefore we can safely split independent nodes to 
different cores.
{{% /notice %}}

{{% notice style="info" title="Easier serialization" %}}
It is much easier to serialize packages of data that reference each other by unique ids, than to serialize objects that 
connect to each other using pointers. Also, data-driven approach guarantees that data is just data, while in 
object-oriented approach there can be lots of pre-save and post-load logic.
{{% /notice %}}

{{% notice style="info" title="Easier networking" %}}
As a continuation of serialization topic, networking also benefits from data-driven approach. It is much easier to
create snapshots, send data, apply data, resimulate data and so on without thinking about object state consistency.
{{% /notice %}}

That's not all, but I think it is enough to give an understanding of why I've choosen data-driven approach as a center
of my personal research.

{{% notice style="warning" title=" " icon=" " %}}
But ECS is not an an answer to the "how to design games" question.
{{% /notice %}}

In my opinion, ECS is only a part of the answer to this question. I'm researching a kind of "more advanced" answer: 
data management and processing system that allows user to work with data through range of prepared queries that are 
backed by automatically created indices. Technically, ECS is a subset of this approach: it can be viewed as a design 
with prepared queries only on some kind of entity_id field. I believe that my research will result in better and more 
convenient paradigm that ECS.