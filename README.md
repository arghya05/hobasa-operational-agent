# Hobasa Operational agent

Operational Agent in the Hobasa agentic SDLC. Owner: PM, RTE and SM.. It runs on Claude Code: every step is one Claude Code session started by the Hobasa spine, with this agent's prompt and step skill (`.claude/`), helper subagents, guardrail hooks and the shared context server.

**Reads from GitHub:** each step's inputs are prepared in `inputs/<trace>/<STEP>/` with the repository, path and commit they came from (other agents' `outputs/`, the requirements and organisation sources in `hobasa-agentic-sdlc`, code in the `*-sample` repositories).

**Writes back to GitHub:** approved outputs in `outputs/<trace>/`; every step run in `steps/<trace>/<STEP>/` (brief, attempts, claims, checks, independent judge, human decision). Code changes go to the `*-sample` repositories. Journey, evaluations and shared memory: `hobasa-agentic-sdlc`.

## Steps

| Step | Name | Reads | Writes | Gate |
|---|---|---|---|---|
| OPS-01 | Release Goals | org.business_goals | iter.release_goals | checks + sampled evaluation |
| OPS-02 | Feature Kick off/Backlog Grooming | iter.release_goals | iter.backlog | checks + sampled evaluation |
| OPS-03 | Iteration Planning ¹ | iter.backlog, org.capacity, org.calendar_rules | iter.plan | SM |
| OPS-04 | Daily Coordination Meeting | iter.plan, org.dependency_tracker | iter.blockers | checks + sampled evaluation |
| OPS-05 | Iteration Review Meeting | iter.plan, iter.blockers | iter.review | checks + sampled evaluation |
| OPS-06 | Iteration Retrospective Meeting | iter.review | iter.retro | checks + sampled evaluation |
| OPS-07 | Predemo ² | iter.plan, org.calendar_rules | iter.events | checks + sampled evaluation |
| OPS-08 | System Demo ² | iter.plan, org.calendar_rules | iter.events | checks + sampled evaluation |
