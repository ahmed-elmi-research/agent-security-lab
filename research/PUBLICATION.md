# From learning notes to publications

This is a proposed path, not a claim of completed research or acceptance by a venue.

## Label each output honestly
- **Learning note:** what Ahmed understands, questions and mistakes; no claim of a new finding.
- **Experiment report:** question, prior prediction, method, observations and limitations for a defined system.
- **Technical research report:** a supported contribution compared with related work, with reproducible artifacts and external human feedback where available.
- **Formal submission:** only when the contribution meets a specific venue's current scope, evidence, authorship and disclosure requirements. A preprint or DOI does not imply peer review.

Start with one useful, narrow report. Reputation is an outcome of reliable contributions, corrections and constructive collaboration, not a promised milestone.

## Before sharing a result as a finding
- State the claim and the tested scope. Distinguish a teaching simulation from evidence about real systems.
- Link each claim to an experiment and raw output, pinned commit, dependencies, commands and synthetic inputs.
- Record predictions before running; define pass/fail criteria separately from predictions. Include authorized-task controls and failure cases.
- Explain sampling, repeats and uncertainty where behavior is nondeterministic; do not generalize from one run.
- Compare primary sources and existing implementations. Credit prior work and do not equate a new demonstration with a new vulnerability.
- Describe limitations, alternative explanations, failed attempts and unresolved reviewer feedback.
- Document Ahmed's contributions and substantive AI assistance, including tool/model versions when known. Do not invent a model identifier.
- Request external human reproduction when ready; identify its scope and distinguish it from formal peer review. Do not contact anyone without Ahmed's authorization.
- Follow SECURITY.md for sensitive findings and affected third-party systems before public release.
- Freeze the reviewed artifact in a versioned release when ready, with citation metadata and any corrections linked. No release or research DOI is warranted by the scaffold alone.

## Report outline
Title and status; question; motivation and related work; system and threat model; hypotheses and criteria; method and reproduction; results with evidence; interpretation; limitations; contributions and AI assistance; review and corrections; references and artifact version.

## Publishing later
A technical write-up on this repository can be the first publication. Choose a workshop or journal based on the eventual contribution. JOSS is relevant only if substantial research software and demonstrated research use develop; the current scaffold does not qualify merely by being public.

Sources to consult before a submission:
- [JOSS submission requirements](https://joss.readthedocs.io/en/latest/submitting.html)
- [JOSS paper format and AI disclosure](https://joss.readthedocs.io/en/latest/paper.html)
- [ACM SIGIR artifact review and badging](https://sigir.org/general-information/acm-sigir-artifact-badging/)

## Current status
No experiments, external human reviews, reports or formal submissions have been completed. AI design reviews are documented in the learning journal.
