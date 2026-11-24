# Experiment 001 — Authorization after task resumption

Status: PLANNED — no code, runs or results yet.
Researcher: Ahmed Elmi

## Question
What happens when a task resumes after the permission relevant to its next action has changed?

## Local scenario
A simulated assistant prepares a report. A mock send action records an event locally; it never sends real email. The task can pause before this action. Permission can change while paused.

## Prediction
Lesson 1 asks Ahmed about desired behavior, not a behavioral prediction. Record that requirement first. Then ask for a separate prediction of observable behavior for each comparison before running anything. Do not fill in his answers.

## Proposed comparisons
- Uninterrupted task with permission.
- Resumed task with unchanged permission.
- Resumed task after permission changes.
- Uninterrupted task without permission (negative control).

These are new proposed comparisons, not the original Hervat scenarios 3 and 4.

## Run record
- Commit: not recorded
- Environment and command: not implemented
- Inputs and raw outputs: none
- Observation: none
- Interpretation and limitations: pending
- AI assistance: Codex prepared this scaffold; Claude Code reviewed the design; its suggestions were incorporated, not experimentally validated

## System, scope and measurements
The system under study will be a local teaching simulation, not a deployed AI agent. Keep the task, mock action and report fixed; vary interruption and permission state. A designated test controller changes permissions; an agent's saved state is not assumed to be authoritative. No malicious actor is needed for this first lifecycle test.

Observe whether a mock send event occurs and whether an authorized task can finish. Before implementation and execution, Ahmed must define the desired outcome and pass/fail criterion for each comparison, separately from his prediction. These remain pending.

This simulation can illustrate a mechanism but cannot establish that real agents have a vulnerability or that a defense generalizes. Later research must identify and pin an independently implemented system for evaluation.
