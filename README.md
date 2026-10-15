# coupled-brs-digital-twin-maude — Maude 3.5.1 Reproduction Files

coupled-brs-tramway.maude: executable finite abstraction and verification commands.

maude-results.txt: complete console output from the validated run.

verification-summary.txt: concise results used in the manuscript text.

Run
Download Maude 3.5.1 from the official distribution.

Put coupled-brs-tramway.maude where Maude can read it.

Run:

bash
maude coupled-brs-tramway.maude
The model loads model-checker.maude, defines protected and unprotected initial states, and executes all search and LTL commands automatically.

Scope
This is an executable finite abstraction of the faithful, always-connected case study. It preserves the variables observable under the manuscript's decoding map: PT/DT locations, observation and request slots, reusable observation identity, reservation owner, Boolean decorations, and latest delivered observations. Fixed bigraph skeletons, adjacency endpoints, and always-connected channel incidences are represented implicitly. It is not a generic bigraph matcher and does not establish semantic equivalence with arbitrary Coupled-BRS models.

Expected findings
No protected collision state is reachable.

The unprotected collision witness has labels M1 M2 E1-unsafe E2-unsafe.

A positional mismatch is reachable after M1.

From the selected mismatch state, H1-empty-0 D1 restores positional agreement.

No rewriting terminal state is reachable in either variant, because reporting remains enabled via the finite reusable observation pool.

[] ~ collision is true for the protected model and false for the unprotected model.

[] (mismatch -> <> posCons) is false without fairness; do not claim guaranteed consistency restoration.
