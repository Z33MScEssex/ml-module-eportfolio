# Evaluating my final project (Unit 11) against the team project (Unit 6)

<!-- DRAFT written for Zee to edit. Every fact below is checked against the Unit 6 repo, meeting notes and the
Unit 11 notebook; the opinions are Zee's to keep, change or cut. -->

The Unit 6 team project was where I learned what goes wrong in a machine learning project. Unit 11 was where I
tried to design those problems out from the start. This page compares the two and is honest about where I still
fell short.

## The two projects in one line each

- **Unit 6 (team of five):** predict New York Airbnb asking prices with regression, and segment the market
  with K-Means. Grade 74%.
- **Unit 11 (individual, built with an AI coding assistant under my direction):** predict a Bliss symbol's word class from its drawing, comparing a classical model
  with two deep learning models.

## What changed, and why

| | Unit 6 team project | Unit 11 individual project | Why I changed it |
|---|---|---|---|
| **The question** | Changed twice mid-project. "Mispriced listings" had no answer in the data (my Bug Report #25), then "strictly spatial" didn't match the features we used | Fixed at the start and checked against the data before any modelling | Changing the question after three weeks of coding cost us writing time and left the report chasing the code |
| **Test data** | 80/20 split. The first notebook scored the model on its own training rows (R² 0.95 vs 0.64) | Test set split off first, before any preprocessing, then scored once at the very end after the model list was locked | Nouh's advice on our call, and the Unit 6 bug. A test score only means something if nothing was tuned on it |
| **Leakage** | Price-derived columns (PCA components, cluster labels) were fed back into the price model. Caught late, on 28 August | Related symbols kept on the same side of every split (2,867 families). Overlap between training and validation cut from 51% to 3% | In Bliss, compound symbols share parts. Without this, a model could score well by recognising the shared part instead of the class |
| **Baseline** | A no-ML baseline was only added after I argued for it in Bug Report #25 | Every model compared on the same folds, with a classical baseline as a full contender | "Better than what?" is the first question anyone asks of a result |
| **Changing the plan** | Decisions made in chat and calls, often after seeing results | Each extra experiment written down with its pass/fail rule *before* it ran | So I couldn't talk myself into a result after seeing it. When the test set surprised me, I didn't switch my headline model |
| **Explanations** | Feature importance only | LIME and Grad-CAM, checked against a rule a person would use (the action and description marks) | Unit 6 feedback: say *why* a model behaves as it does, not just what it scored |
| **Who it's for** | Hosts and Airbnb, implied | A written section on who would use it and who would pay | Nouh asked me this directly on our call |

## What worked better

- **The results are more trustworthy.** In Unit 6 we found three evaluation problems in our own notebook
  during the last fortnight. In Unit 11 the design stopped them before they could happen.
- **I could explain the surprises.** On the test set, ResNet18 dropped on one unseen family of symbols, the Norse
  gods. Because I had written down my choices in advance, I reported it as a finding instead of quietly
  switching to the model that happened to score best.
- **The critical analysis is in the write-up.** Nouh's main criticism of Unit 6 was that we described results
  more than we analysed them. In Unit 11 every result has a "what this shows" section.

## What didn't, or what I'd still change

- **Working alone removed the human review step.** In Unit 6 every pull request had a second pair of eyes. In
  Unit 11 I made the design decisions and an AI coding assistant wrote much of the code. A tool that wrote the
  code isn't an independent reviewer of it, so I leaned on tests, pre-written rules and my call with Nouh
  instead. A human peer reviewer would still have been better.
- **The test set is small for the rare classes.** With only 53 "people" symbols, one family moved the score by
  several points. That's a design limit I accepted, not one I solved.
- **I over-built in places.** Ten model variants is more than a 20-minute presentation can carry. In Unit 6 the
  team stopped coding to protect writing time, and I should have applied that lesson harder here.
- **Some of my explanations were wrong at first.** I thought the small CNN struggled with unseen families; it
  was the loss settings. Writing rules in advance meant the data corrected me, but I needed the reruns to see it.

## What I'm taking forward

1. Check the question has an answer in the data before building anything.
2. Split off the test set first, and only look at it once.
3. Write down what would count as success before running an experiment.
4. Put the reasoning in the report, not just in the issues and the chat.
5. Get someone else to review the work, even on a solo project.
