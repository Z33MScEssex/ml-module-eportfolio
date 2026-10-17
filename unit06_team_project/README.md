# Unit 6: Development Team Project (Airbnb pricing, Track 1)

**Learning outcomes:** LO1, LO2, LO3, LO4 · **Team:** Group 2, "Lorem Ipsum", five members · **Grade:** 74% (Distinction)

**Final business question:** *How can an Automated Valuation Model (AVM) use listing, host, review and spatial
features to predict Airbnb asking prices in New York City, and which geographic areas show the greatest pricing
uncertainty?*

**Team repository:** [julesrif/ML-Airbnb-Business-Analysis](https://github.com/julesrif/ML-Airbnb-Business-Analysis)
(private; the tutor has been added as a collaborator). The issue links below point into it.

## Files here

| File | What it is |
|---|---|
| [Airbnb Business Analysis Using a Data Science Approach Track 1.docx](Airbnb%20Business%20Analysis%20Using%20a%20Data%20Science%20Approach%20Track%201.docx) | The submitted team report |
| [main.pdf](main.pdf) and [Code Execution.pdf](Code%20Execution.pdf) | The executed notebook, submitted alongside the report |
| Feedback AS1 Group 2.pdf (held privately, available on request) | Tutor feedback on the team report |
| Peer evaluation (submitted).pdf (held privately, available on request) | My peer evaluation of the four teammates |

## How the team worked

We were five people across several time zones, and on 3 August we found there was no slot when all of us were
free. So we set up a way of working that didn't depend on everyone being in the same call:

- **A GitHub Projects kanban board** for every task and every meeting, with a ticket per job.
- **Branches and pull requests**, with at least one reviewer before anything reached `main`. GitHub wouldn't
  enforce branch protection on a free private repo, so it was a team agreement rather than a rule.
- **Weekly Saturday calls**, with notes written up as a GitHub issue each time.
- **Telegram** for day-to-day chat, polls and quick decisions.

### Meeting notes

There are six sets of meeting notes, written up as issues on the team repository. Patrick took most of them and
John-Jon took Meeting 3.

| Meeting | Date | What we decided |
|---|---|---|
| [01](https://github.com/julesrif/ML-Airbnb-Business-Analysis/issues/7) | 8 Aug | Track 1. Kanban board. One reviewer per pull request within 3 days. Weekly calls. Ask the tutor whether we could add outside datasets. |
| [02](https://github.com/julesrif/ML-Airbnb-Business-Analysis/issues/8) | 15 Aug | First random forest merged as the baseline. I flagged that the notebook needed a way to evaluate the model. I took the report outline and the literature review. |
| [03](https://github.com/julesrif/ML-Airbnb-Business-Analysis/issues/24) | 22 Aug | **We changed our business question**, from spotting mispriced listings to a pricing tool for new listings, following my bug report. Report sections assigned; mine was business recommendations. |
| [04](https://github.com/julesrif/ML-Airbnb-Business-Analysis/issues/34) | 29 Aug | Code frozen to protect writing time. Dropped "strictly spatial" from the question. |
| [05](https://github.com/julesrif/ML-Airbnb-Business-Analysis/issues/35) | 2 Sep | Resolved conflicting figures between the report and the notebook. Dropped the "cold start" framing. |
| [06](https://github.com/julesrif/ML-Airbnb-Business-Analysis/issues/38) | 5 Sep | Submission checklist: Turnitin sandbox, notebook PDF alongside the report, formatting. |

## My role and contributions

**Agreed role (4 August):** editor, research and referencing, and owner of the business question. Later also
the business recommendations section, final editing and submission.

1. **Setting up the roles.** I ran a short skills check-in in the team chat (Python comfort, past experience,
   what each person wanted to own) and turned the answers into the role split the team adopted. I also
   proposed the shared GitHub repo, so contributions would be visible and reviewable.
2. **[Bug Report #25](https://github.com/julesrif/ML-Airbnb-Business-Analysis/issues/25), 15 to 21 August.** We
   agreed nobody had checked the notebook's numbers yet, so I re-ran it.
   - The model was being scored on its own training data. It got R² 0.95 on the rows it had seen and 0.64 on rows
     it hadn't, so the "anomaly map" was mostly a map of which rows happened to be in training.
   - More importantly, the business question had no answer in the data. If the price gap really showed
     mispricing, cheaper-than-expected listings should get more bookings. The correlation was 0.01, effectively
     none.
   - Track 1 needed clustering, and we didn't have any yet.
   - I wrote it up so anyone could reproduce it, gave the one-line fix, and said I'd rather be told if I'd got
     something wrong. The team fixed the scoring and changed the question to a pricing model for new listings
     (Meeting 3).
3. **Follow-up analysis on the new question.** I tested the new framing before we committed to it:
   - Review counts had to come out of the model, because a brand new listing has none. That cost us very
     little (R² 0.637 to 0.623).
   - We should publish a "no machine learning" baseline. A simple lookup of median price by neighbourhood and
     room type got 0.550, so the model's real gain was 0.073.
   - We should report the error in dollars and per cent, not just R².
4. **Checking the final notebook, 28 to 29 August.** I ran it through an AI coding assistant (Claude Code) to
   check it and posted the findings in the team chat:
   - Columns built from the price itself were being fed back into the price model (target leakage).
   - The volatility map was coloured by dollar error, so it mostly showed the most expensive areas.
   - The baseline was scored on its own training rows.
   The team fixed the leakage. Julio asked me to summarise because my first post was too dense, which was fair.
5. **Editing and submission, 1 to 6 September.** I wove the sections into one report, queried the figures that
   didn't match the notebook, rewrote the introduction and conclusion to match the final question, ran the
   Turnitin sandbox check and submitted. Before submitting I raised the volatility map one last time. As a
   team we agreed to keep it and state it as a limitation rather than change code on the deadline day.

**Where I fell short.** I missed the seminar on 8 August and watched the recording. My checking was useful, but a few of my posts
were long and technical, and the team had to ask for a plain summary. That's something I've worked on since.

## Tutor feedback, and what I'm taking from it

Nouh praised the clear business question, the structured method, the model comparison and the visuals. The
main criticism was that the report described results more than it analysed *why* models behaved as they did,
and that the clustering was brief. That matches what I saw from inside the project. We had the critical
analysis, but much of it lived in issues and chat rather than in the report. In my individual project (Unit 11)
I put that reasoning in the write-up itself. See the [evaluation](../unit11_individual_project/evaluation_vs_unit06.md).

## Peer assessment

The peer evaluation form I submitted is held privately, since it names my teammates. I rated all four
teammates 4 out of 5 ("above average") on every criterion. That was honest: everyone delivered their part,
reviewed each other's pull requests and turned up to most meetings. Nobody was absent enough to deserve a low
score, and no single person carried the project enough for a 5.
