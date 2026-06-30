# Behavioural Effects of Supervisory Multi-Agent Control on Operator Workload

**A Pilot Study with a Waste-Sorting Robot Simulator**

E. M. Iurlasov · Bauman Moscow State Technical University, Moscow, Russia · mrjon1423@gmail.com

---

## Overview

This repository contains a preprint and the raw data for a within-subject pilot
study comparing **manual** versus **swarm (supervisory)** control of a simulated
multi-agent waste-sorting cell, measured by two operator-workload proxies: task
completion time and number of operator interventions.

**Headline result.** Across 34 participants (93 logged trials, three age/skill
groups), supervisory control reduced median task time from 48.2 s to 19.2 s and
median interventions from 43 to 13 (Wilcoxon signed-rank, p < 0.001; matched-pairs
rank-biserial r = 0.95 and 0.99). The reduction was consistent across all groups.
Operator skill affected supervisory task speed (Kruskal–Wallis p = 0.009) but not
intervention counts (p = 0.39).

This is a proof-of-concept study with a non-expert, partly school-age sample in a
simulated environment; it is reported as an informal classroom pilot. See the
paper's Limitations and Ethics sections for the full scope and caveats.

## Repository contents

| File | Description |
|------|-------------|
| `supervisory-control-workload-pilot.pdf` | The preprint (final version). |
| `supervisory-control-workload-pilot.docx` | Editable source of the preprint. |
| `data/pilot_study_data.csv` | Raw per-trial logs underlying every figure in the paper. |
| `README.md` | This file. |

## Data

The raw log is the **only** source of the numbers reported in the paper; all
statistics were computed directly from it.

**Columns of `data/pilot_study_data.csv`:**

- `Time` — wall-clock timestamp of the trial (HH:MM:SS)
- `Mode` — control condition: `Manual` or `Swarm`
- `Iter` — within-participant trial counter (1, 2, 3); a reset marks a new participant
- `Result` — trial outcome (only `SUCCESS` trials were logged)
- `Clicks` — number of operator interventions in the trial (workload proxy)
- `Duration` — task completion time in seconds (workload proxy)
- `Group` — participant group (grade 7 / grades 9–11 / Master's students)

**Note on participant counts.** Participant identifiers were not stored. Participant
boundaries were reconstructed from the logs by treating each reset of the `Iter`
counter as the start of a new participant, yielding 34 participants (10 / 20 / 4
across the three groups), of whom 26 contributed trials in both control conditions.
No personally identifying information was collected; the dataset is anonymous by
construction.

## Citation

> E. M. Iurlasov, "Behavioural Effects of Supervisory Multi-Agent Control on
> Operator Workload: A Pilot Study with a Waste-Sorting Robot Simulator," preprint, 2026.

## Status

Preprint. An arXiv version (cs.RO; cross-list cs.HC) is planned pending endorsement.
