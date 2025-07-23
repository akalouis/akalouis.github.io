---
layout: post
title: "Can you mathematically measure fun? You could not. Until now!"
description: "After 50 years of subjective game design, Theory of Anticipation provides the first objective mathematical tool for quantifying engagement, with playable proofs."
date: 2025-06-28
keywords: "mathematical game design, engagement measurement, fun optimization, game mechanics, theory of anticipation"
tags: [game-design, mathematics, engagement, research, optimization]
image: "/assets/images/mathematical-fun-cover.png"
---

> "How do you measure fun with math?"

---

For 50 years, game designers have been flying blind. They rely on gut instinct and expensive, endless playtesting to answer the industry's most fundamental question: What makes a game engaging?

Blizzard spent years developing Overwatch through internal playtests. Riot Games employs armies of game designers to balance League of Legends. Valve is known for their intense playtesting-driven game development methodology for the "perfectly" engaging game experience.

But, what if I told you we just solved this with pure mathematics?

What if you could predict, before writing a single line of code, that Mechanic A will be **26.5% more engaging** than Mechanic B?

What if it was even possible to "prove" which game design is "optimal"?

I did exactly that. Here's how.

---

## The Problem of All Game Designers

![](/assets/image/2025_07_23_art.webp)

You are a game designer at a big game studio. You are developing a brand new title. You work overnight, and finally come up with an innovative, game-defining mechanic, and it gets immediately rejected.

> "No." — Your boss

So you instead submit the ultimate "proven" game mechanics.

> "Let's mix genre A with B."

Modern game development is expensive. As a professional game designer, you already know that the industry needs innovation, however, it rarely gets approved because your best ideas have not yet been "proven". Mixing two genres? Nowadays, it almost sounds like a meme.

For game design, designers rely on intuition, playtesting, and feedback. Game development takes so long and is so expensive and you only get the "true result" after launch. Post-launch, you discover player retention isn't high. Now, your game is doomed. Now it's too late for you to change any significant game mechanics.

This is the typical tragic story of modern game development. Hundreds of games launch and fail. You will be surprised just how many games you haven't heard of failed and disappeared without a trace.

While that sounds trivial to players, from the perspective of game devs, each trial was a serious attempt and each failure is genuinely heartbreaking.

So, what is the problem?

**The root problem is that we don't have a method to objectively measure game mechanics. Yet.**

Now, let's solve this problem.

---

## The Theory of Anticipation

**Theory of Anticipation (ToA)** is a recently born framework that enables objective evaluation of 'fun' in game designs.

Yes, this theory gives you a score number for your game design!

So what is this exactly? Let's get into this step by step.

First of all, how do you define fun? And so, how do you mathematically measure it?

## Anticipation

According to Theory of Anticipation, **anticipation mathematically equals engagement**.

If there's something worth your attention, either requiring your action or just attention, it is engaging, therefore fun.

Let's do some thought experiments:

```
[PAUSED GAME PROBLEM]

You're dominating in League of Legends.
Perfect position, commanding lead, about to achieve victory.

Then the game pauses, indefinitely.
```

Now, suddenly the game is no longer engaging.

Why? Because there will be zero meaningful events remaining.

****
```
[PENALTY-ONLY GAME]

Choose: lose 10 points (90% chance) or lose 100 points (10% chance).
```

Despite ALL outcomes being bad, you still feel tension. Why? Because there are **still meaningful events ahead.**

Counterintuitively, the fun — in other words, engagement — is deeply related to the "varied outcomes," not the reward or desire itself.

If you measure this "varied outcomes" in the most mathematically natural way, you end up with this beautiful equation:

## Local Anticipation Formula

```
μ(s) = Σ P(s→s') × D(s')
A(s) = √[Σ P(s→s') × (D(s') — μ(s))²]
```

**Don't panic!** There's no need to understand any of this to enjoy the article.

In plain English, it is just measuring *"How uncertain are the meaningful outcomes from this moment?"*

For technical details, check out the [GitHub repository](https://github.com/akalouis/anticipation-theory) and [academic paper](https://doi.org/10.5281/zenodo.15826917).

---

## So, What Does This Do?

Here's what it does:

<p align="center">
  <img src="/assets/image/2025_07_23_experiment1.webp">
  <br>
  <em>Game A. Game Design Score: 0.430483</em>
</p>
<p align="center">
  <img src="/assets/image/2025_07_23_experiment2.webp">
  <br>
  <em>Game B. Game Design Score: 0.544004</em>
</p>

Those are 2 games with different game mechanics.

You see, Game B is 26.5% (0.43 → 0.544) superior to Game A, mathematically.

This is not an artificial example for understanding, but real experimental data, real game mechanics, and real results that ToA produced.

## Reality Check

Wow, can you believe it? I am almost sure that if you are a game designer or have an academic background, you would be quite surprised by now.

So, what's the caveat?

```
Q. It works on one genre, right?

Q. It gives you the number but does not match perceived fun, right?

Q. It is not yet applicable in the field, right?
```

Calm down! You stopped breathing for a while there!

Here's what Claude 4 had to say about this research:

```
"This research represents genuine genius-level intellectual achievement through its transformative creation of the first mathematically rigorous framework for quantifying player engagement, fundamentally restructuring game design from subjective intuition into objective optimization..."
```

While this is definitely a comically overhyped (😜) verdict, Theory of Anticipation is showing very promising initial results.

Let's unpack those 2 mechanics and have a closer look.

---

## The Two Benchmark Games

**Game A** was actually named **HpGam**e — a simple baseline game that models 1v1 fighting games like Street Fighter, King of Fighters, Tekken.

**Game B** is called **HpGame_Rage**. It's HpGame with additional novel game mechanics added to it.

### HpGame:

```
2 Players play with 5 HP each. Every turn, both players attack each other.
If you reduce Player 2's HP to 0 while you are alive, you win
```

### Rage/Crit system:
```
You gain Rage each time you take or give damage
Rage increases with the amount of damage taken or given
Rage never decreases (accumulates throughout the match)
On critical hit, you deal additional damage amplified by Rage
```

The result is:

<p align="center">
  <img src="/assets/image/2025_07_23_experiment3.webp">
  <br>
  <em>HpGame. Sorted. Most engaging moments come first.</em>
</p>

<p align="center">
  <img src="/assets/image/2025_07_23_experiment4.webp">
  <br>
  <em>HpGame_Rage. Sorted. Most engaging moments come first.</em>
</p>

When you run this program, it computes precise values of fun (anticipation 1–5) for all possible game states.

To help generate design insights, the program sorts these moments by engagement.

A full state-by-state analysis can be boring to read through here, so the details are in the [Paper](https://doi.org/10.5281/zenodo.15826917).

> Q. Oh, this actually computes the anticipation of all game states?

**Yes!** And when we summarize the anticipation for all states combined, we get the Game Design Score Makes sense, doesn't it?

This way of viewing a game design reveals fascinating insights.

For example, did you know you get more engaged when the match is **slightly unbalanced**?

For more exciting details, I recommend visiting [GitHub](https://github.com/akalouis/anticipation-theory) and [Paper](https://github.com/akalouis/anticipation-theory/blob/main/LaTeX/theory_of_anticipation_academic_publication_version.pdf).

---

## Playable Demos

<p align="center">
  <img src="/assets/image/2025_07_23_game_screenshot1.webp">
  <br>
  <em>HpGame_Rage_Optimized</em>
</p>

You can play the experimental game models directly in your browser.

[🎮 Play HpGame (Baseline)](https://akalouis.github.io/anticipation-theory/Html/hpgame.html)
The baseline 1v1 game used in our research.

[🎮 Play HpGame_Rage_Optimized](https://akalouis.github.io/anticipation-theory/Html/hpgame_rage_optimized.html)
An enhanced version demonstrating a **+51.7% improvement** in Game Design Score (0.653412) compared to the baseline.

Which game did you find more engaging?
Which one did you play longer?

We predict that most people will find the optimized version more compelling and play it longer. If this is the case for you, it serves as powerful **empirical evidence** for our "Theory of Anticipation."

It is important to note that the game's parameters were improved using only our Game Design Score (GDS) metric — an objective measurement based on the Theory of Anticipation(ToA) — without any subjective input from designers.

---

## Industry Application

One profound strength of Theory of Anticipation is that it is readily applicable to game design right now.

Did you know we can apply mathematical optimization algorithms? We can use genetic algorithms or gradient descent to automatically discover optimal...

Hmm, I think it's getting a little boring. How about this?

> "Dear my boss. Mister, my novel mechanics achieve a FREAKIN' +26.5% compared to baseline model. This time, please accept. Sincerely."
> 
> — Game Designer

---

## The "Subjectivity" Problem

> Q. How about Subjectivity? I am sure your theory will break down like every other existing theory.
> 
> A. Haha, this time, no.

Subjectivity is **the most overused excuse** for avoiding quantification of fun historically.

We don't even have proper academia for game design, which is a sad story. Why?

Because it's all **subjective**! How do you do science if there's no math!?

The way ToA deals with subjectivity reveals its most compelling aspects.

Let us show off about that aspect.

**Problem: Games Get Old Over Time**

> Same game, getting bored over time...
>
> "It is me, ...therefore subjective, right?"

Have you ever experienced a game getting boring over time?

The Local Anticipation Formula shown above was so general, beautiful, gorgeous, elegant, pure, generous, marvelous, robust, lovely, ... it could be applied **recursively!**

By applying it recursively, we can extract multiple components of anticipation with varying depth, such as **A₁ + A₂ + A₃ + ...**

This recursive structure elegantly resolves the problem.

This is the most sophisticated aspect of ToA.

It definitely deserves a dedicated section. 😉

---

## Hierarchical Anticipation

So, you recursively apply the same anticipation formula to extract multiple components?

Why even do that? What does each component even mean?

Each component A₁, A₂, A₃... captures continuously deeper and longer-term layers of anticipation. This coincidentally equals...

**Players' perceived anticipation shifts: A₁ → A₂ → A₃ over time as they develop mastery.**

> No! You're making that up, right?

Haha. Well, hear me out, closely!

When you play a game, the game gets old because you become familiar with how the game works — in other words, you build a model of the game and become able to predict outcomes.

Naturally, you feel less variance in lower components like A₁ and higher components like A₃ continuously become the dominant driver, over time.

However, this recursive anticipation is not something that was artificially developed to deal with subjectivity.

It was a coincidental and beautiful mathematical equivalence.

Let's dive into it more deeply.

## The Game Ending Button Problem

Local Anticipation calculates the anticipation A₁.

However, this anticipation A₁ was not sufficient to represent multi-turn games' engagement precisely.

Let's have another thought experiment:

You play a long session of a MOBA game. However, you are given a game-ending button that will end the game with 50% win probability, immediately after you press that button.

In this hypothetical game session, the value of A₁ indicates 0.5 all the time, which is the proven theoretical limit of A₁'s value.

In other words, the non-recursive version of ToA thinks this game is **optimally fun and there exists no more fun** game than this!

Hmm, something's very wrong here, right?

The existence of the game-ending button effectively eliminates all strategic value. In the end, only the game ending button matters.

Now the magic begins.

It turns out, that the fun, anticipation, was not a single value. But a **recursively structured, multi-dimensional value!**

## Recursive Nature of Anticipation

Multiple ways of explaining this. Let me explain intuitively.

Looking at the formula of Local Anticipation, there is D. Which stands for 'desire.'

Naturally, people **want** more fun moments within a game session, right? Therefore, it is plausible to treat **anticipation as new desire**, establishing this recursive structure.

It turns out, these components correspond to each layer of strategic branches.

Intuitively speaking:
```
A₁ "What button do I press next?"
A₂ "What's my next combo?"
A₃ "What's my next positioning?"
A₄ "Is it better not to take this fight?"
A₅ "How do I break the established meta?"
```

Remember the perceived fun changes over time as you get familiar with the game?

If your mastery is at the A₁ level, since you cannot predict the game beyond the button press level, you cannot perceive A₂. A₁ is all of your fun.

However, if you keep playing, your prediction capabilities get better and better, you perceive higher components like A₂, A₃, and so on.

Yes, your fun changes over time, from the A₁ level to A₂, A₃, ...

In this very predictable manner.

But A₁, A₂... also correspond to strategic layer depth, right?

So that means...

We've accidentally proven that **highly strategic games mathematically equate to highly replayable games...**

**Wow. Just wow. Isn't it?**

However, it is not yet the end of the surprise...

---

## Narrative Structure

Studying the mathematical properties of nested components, we have found a very interesting implication.

Basically, A₂ is anticipation of A₁. To have non-zero A₂, we need to have "variances" in A₁. Which means...

**We need to sacrifice A₁ to some degree to gain non-zero A₂.**

This equates to a **mathematical proof that games should not be "always fun" to be "more fun" in the long term.**

In other words, this indicates that the optimally fun game needs to have **Ups and Downs** — sometimes a little boring, sometimes exciting — strongly suggesting rhythmic, unpredictable, deep narrative structure.

> Wow, what? So the optimal game should be a **narrative experience?**

**Yes!** Amazing mathematical discovery, isn't it?

---

## Full Implication of Theory of Anticipation

> "It was meant to be a game design tool but..."

Movies, novels, and anime are all fun because you anticipate what will happen next. You don't know what will happen next, and you anticipate something important will happen in the future with a dramatic reversal of fortune.

Yes, you **anticipate** something in the show, so the show is fun.

We have found that Theory of Anticipation explains engagement across different media.

It was meant to be a game design tool, but it turns out that we've cracked something far more fundamental than this.

The theory and GitHub source code are not yet optimized for this use, however, it is **very** plausible that ToA could be applied to narrative content in a systematic way in the future.

While not yet formally proven, I have a strong gut feeling that optimizing higher components (A₃, A₄...) will result in traditional narrative principles like Freytag's Pyramid or the Three-Act Structure.

---

## Thank You For Reading!

Thank you for staying with me through this journey. I hope it was a thought-provoking experience for you.

I certainly did my best to keep the anticipation high! 😉

## Birth of Theory of Anticipation

> "That is your subjective idea."

I'd explain "This design is superior because...," only to be met with the infamous **"That's your subjective idea."**

ToA was initially developed to address this difficulty in discussing game designs.

Now I am ready to reply, "Nah, mine's **objective!**"

---

## Let's Connect

Questions? Discussions?

Feel free to reach out.

**aka.louis [at] outlook [dot] com**
[Discord](https://discord.gg/t5wPx8DdUK)

I am eager to discuss various insightful opinions and feedback from around the world!

**Links:**
- 🔬 [Academic Paper](https://doi.org/10.5281/zenodo.15826917)
- 💻 [GitHub Repository](https://github.com/akalouis/anticipation-theory)
- 🎮 [Interactive Demos](https://akalouis.github.io/anticipation-theory/)
- 💬 [Discord Community](https://discord.gg/t5wPx8DdUK)