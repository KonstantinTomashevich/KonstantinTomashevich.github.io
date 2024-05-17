+++
title = 'About'
date = 2024-05-17T12:55:08+03:00
+++

## Who am I?

I prefer to call myself a hedge knight of game programming, because I am more of a generalist rather than specialized 
developer. I've worked both as gameplay and engine developer and I have experience with various engines and 
technologies. It gives me good understanding of the common concepts and approaches in game development. But it also
makes me not qualified enough for roles that require 5+ in some particular game engine. :D

## Ultimate skill

Question of "my ultimate skill" (in RPG terms) is as dualistic as my experience.

From one point of view, my experience lets me dig into code that has no documentation and "no living witnesses" and
still understand, fix and improve it when it is needed. I've worked with different technologies including custom
proprientary engines with almost zero documentation (and developers who forgot why they've written it like that),
therefore I'm able to see code as it is without prejustice and excessive expectations, then examine it and find ways 
to make it better for our project goals. Is there a thing in your project that no one knows how it works, but you need
to optimize it? I can do it, but I'm not usually enjoying doing that. :)

On the other hand, I like to design and implement new features and systems. It is sometimes exhausting, but it is also
much more fun than digging into old code. I've developed lots of different features for gameplay and I'm developing
my own game engine as a pet project, therefore there is a lot of invested experience points in this stat too.

To summarize, it looks like I am some kind of dwarf. I'm digging and designing underground fortresses. :D

## My goal

In my case, with experience comes... dissatisfaction with technical state of projects I've worked with.

As it was said by Nathan Myhrvold: "Software is a gas". And it is very true for lots of projects and not only in aspect
of hardware usage, but also in aspect of error capacity. If there is a lot of space for errors, you'll see this space
filled with errors sooner or later. It means that huge software, especially large games of AAA level, are plagued with
errors and inefficiency on the multiple levels. And it makes me sad, very sad.

Therefore, my goal is to make game software engineering better by introducing techniques that limit space for errors 
and make it easier to search for them and analize them.

## My design philosophy

I've started working with data-driven software design approach in 2020 when I joined 
[Press Fire Games](https://www.pressfire.com/). Althrough their approach was not perfect, I've started thinking about
Entity-Component-System and data-driven paradigm as a good alternative to classical object-oriented approach. 
Data-driven approaches, including ECS but not limiting to it, provide several advantages:

- Limited capacity for errors. Data-driven approaches are usually more strict and have more requirements for code
  than classic object-oriented approaches. Developer is responsible for designing data structures and their processing
  units, and there is not that much space for design fantasies, therefore, not much space for errors.

- Strict data and logic separation. Separating data from logic is usually a good idea in system design, because it makes
  it easier to process data in different contexts without adding unnecessary dependencies. Of course, it might come with
  optimization concerns, but personally I don't think it is worth making archetecture worse for small optimizations.

- Easier CPU parallelism. When program is centered around data and its processing pipeline, it is much easier to
  execute this pipeline in parallel. We know exactly which pipeline node processes which data, therefore we can
  safely split independent nodes to different cores.

- Easier serialization. It is much easier to serialize packages of data that reference each other by unique ids,
  than to serialize objects that connect to each other using pointers. Also, data-driven approach guarantees that
  data is just data, while in object-oriented approach there can be lots of pre-save and post-load logic.

- Easier networking. As a continuation of serialization topic, networking also benefits from data-driven approach.
  It is much easier to create snapshots, send data, apply data, resimulate data and so on without thinking about
  object state consistency.

That's not all, but I think it is enough to give an understanding of why I've choosen data-driven approach as a center
of my personal research.

But I don't think that ECS is an answer to the "how to design games" question. In my opinion, it is only a part of the
answer. I'm researching a kind of "more advanced" answer: data management and processing system that allows user
to work with data through range of prepared queries that are backed by automatically created indices. Technically,
ECS is a subset of this approach: it can be viewed as a design with prepared queries only on some kind of `entity_id`
field. I believe that my research will result in better and more convenient paradigm that ECS.

## My main personal project

My main project is a game engine that is based on my research paradigm, described above. I've started working on it
in 2021, but I've started from scratch two times since that time due to discovering ideas how I could make my project 
a lot better and more useful.

Current iteration is [Kan](https://github.com/KonstantinTomashevich/Kan), which is written in pure C. Pure C was choosen
due to fast compile times, light weight of artefacts and "directness" of the code: you can read the code and understand 
its weight, that is not hidden under layers of templates and abstraction. Despite using "old-style pure C", Kan utilizes
autogenerated reflection to be as robust and convenient as possible without losing advantages of pure C.

As of May 2024, Kan core logic and architecture is implemented and I'm working on adding modules required to make games,
like transform, render and resource system.

## My other personal projects

My path in game development started when I was 14 years old and I had lots of different pet projects along the way.
I will list some of them just for historical reasons from newer ones to older ones:

- [CMakeUnitFramework](https://github.com/KonstantinTomashevich/CMakeUnitFramework) -- basic CMake framework for modular
  libraries, applications and frameworks, that is used in Kan and its previous iteration -- Emergence.
- [Emergence](https://github.com/KonstantinTomashevich/Emergence) -- previous iteration of my game engine project.
  It's core is implemented along with 2d render and physics integrations. It was abandoned, because some architecture
  design mistakes that were made during early development started to hinder development and cost too much.
- [Sober](https://github.com/KonstantinTomashevich/Sober) -- CMake framework for modular libraries and frameworks, that
  was initially used for Emergence. Although it didn't go well in the end, it is still interesting from design point of
  view and its best ideas have formed CMakeUnitFramework.
- [Colonization](https://github.com/KonstantinTomashevich/colonization) -- the game that I was making when I was
  16-17 years old. Here just for historical reasons. :)
- [as-bind-gen](https://github.com/KonstantinTomashevich/as-bin-gen-sample-project) -- tool for generating AngelScript
  bindings for Urho3D engine, made for Colonization project. My first experience in making build tools, here just for
  historical reasons. :)


## My commercial experience

From newest to oldest.

### Saber Interactive - Software Engineer

From November 2023 to present.

I'm currently working on 2 projects: desktop multiplayer shooter and open-world RPG on UE5. I'm specializing in Unreal 
Engine improvement and customization systems development. Examples of tasks:

- I've improved [Mutable](https://github.com/anticto/Mutable-Documentation/wiki) experimental plugin mesh generation
  performance by 7 times for Unreal Engine 5.3.2.
- I've made lots of project-specific improvements to Mutable experimental plugin.
- I've participated in client optimization, including ragdoll optimization and movement optimization.

### Gamemod LLC - Game Developer

From December 2022 to October 2023.

I was working in a team on desktop multiplayer shooter on UE5, specializing in gameplay programming. Examples of tasks:

- I've designed and developed system for character and weapon customization, including having custom animations for
  legendary weapons.
- Researched and implemented seamless animated loading screen approach. We've needed to show players party with 
  animations in full equipment while connecting to server and loading all the assets.
- Implemented various gameplay features using Gameplay Ability System when needed.

### Globant - Game Developer

From December 2021 to December 2022.

I was working in a team as an editor and tools programmer on client RPG project. Examples of tasks:

- Migrated shader compilation pipeline to new architecture. Also, improved new shader pipelines architecture performance
  by almost two times by imroving how this pipeline interacts with Incredibuild.
- Improved game-instance-to-editor messaging system.
- Detected issues in client's file system watcher and implemented new safer file system watching approach.

### Press Fire Games - Software Engineer

From September 2020 to December 2021.

I was working in a team on mobile multiplayer shooter 
[BattlePrime](https://play.google.com/store/apps/details?id=com.blitzteam.battleprime),
specializing in gameplay, but sometimes solving engine-level tasks too. Examples of tasks:

- Developement of generic object positioning and spawn system for character abilities with previews. For example,
  spawning of turrets, tripwires, etc..
- Development of gameplay zones features, like fire pits, toxic clouds, battle-royale circle, etc..
- Improvement and developement of character abilities.

### Vizor Interactive - Software Engineer

From July 2019 to Septer 2020.

I was working in a team on midcore mobile game, specializing in gameplay, but sometimes solving engine-level tasks too.
Examples of tasks:

- I've developed quest framework.
- I've developed framework for animated crafting minigames.
- Improved object sorting for isometric projection and pathfinding algorithms.

## Education

Belarusian State University, Faculty of Applied Math and Computer Science, Applied Computer Science specialty.

Graduated in 2021 with 9.5 grade average out of 10.
