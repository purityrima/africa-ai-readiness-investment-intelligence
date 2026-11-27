Project Tracker — AI-Readiness Investment Intelligence for Africa
Technical target: 19 November 2026
Project Work submission: 27 November 2026
Defense: 4 December 2026
Status: In progress
Scope and working rules
- Five analytical deliverables only. No interactive dashboard required.
- Use existing data and preliminary K-Means / Agglomerative experiments; add methods or data only to resolve a critical issue.
- Keep GitHub management lean: one issue per major work package, a focused branch, meaningful commits, push and merge.
- Update this tracker as work progresses; do not create separate administrative reports.
- Interpret results as preliminary infrastructure screening, not verified AI readiness, investment returns or project bankability.
Technical sprint — 17–19 November
Day 1 — Model evaluation and infrastructure profiles (17 Nov)
- [X] Review Notebook 02 results and Notebook 03 status.
- [X] Select and justify a defensible clustering configuration using internal metrics, stability and sensitivity evidence.
- [x] Save final cluster assignments and evaluation summary.
- [x] Output 1: Describe and name interpretable urban infrastructure-readiness profiles.
- [x] Commit, push and record the GitHub issue/PR link below.
Day 2 — Spatial, infrastructure and sustainability interpretation (18 Nov)
- [x] Output 2: Produce Africa-wide cluster map and useful geographic comparisons.
- [x] Output 3: Compare relative infrastructure strengths, gaps and constraints across profiles.
- [x] Output 4: Interpret solar PV potential, temperature and relevant sustainability indicators.
- [x] Check figures, joins, labels and substantive interpretation.
- [x] Commit, push and record the GitHub issue/PR link below.
Day 3 — Investment screening and technical handover (19 Nov)
- [x] Output 5: Develop preliminary investment-screening archetypes, constraints and follow-up evidence needs.
- [x] Synthesize the five outputs into a decision-support narrative for the final report.
- [x] Update README, requirements and indicator metadata/data dictionary only where needed.
- [x] Verify notebook execution order, key outputs, data provenance and repository status.
- [x] Commit, push and merge reviewed changes.
Writing and submission — 20–27 November
- [ ] 20–21 Nov: Introduction, literature, methodology.
- [ ] 22–23 Nov: Results, maps, profile interpretation.
- [ ] 24–25 Nov: Discussion, limitations, sustainability implications, reflection, conclusions.
- [ ] 26 Nov: Final citations, figures, formatting and PDF check.
- [ ] 27 Nov: Submit Project Work; record confirmation.
- [ ] 28 Nov–3 Dec: Prepare defense for 4 December.
GitHub links and decisions
Evaluation + profiles | Completed | Notebook 03: Model evaluation and selection
Maps + infrastructure + sustainability | Completed | Notebook 04: Geographical analysis and cluster interpretation
Investment screening + handover | In progress | Screening archetypes completed; GitHub integration and final handover pending
Geographical analysis and interpretation | PR #7 | Merged into main
https://github.com/purityrima/africa-ai-readiness-investment-intelligence/pull/7

Blockers / decisions requiring attention
- Decision: K-Means (k=3) selected for primary exploratory
  infrastructure profiling and geographical interpretation.
  K-Means k=2 and k=6 retained for sensitivity comparisons.
- Documentation: Final dataset contains 2,172 urban centres,
  12 clustering predictors, one supplementary PeeringDB indicator,
  three identification fields and three cluster-assignment columns.
- Next: Geographical analysis, descriptive cluster naming,
  and infrastructure/sustainability interpretation in Notebook 04.
Completion criteria
Technical work is complete when all five outputs are saved and interpretable, the chosen clustering solution is defensible, and the repository contains the minimum documentation needed to reproduce and explain the analysis.
