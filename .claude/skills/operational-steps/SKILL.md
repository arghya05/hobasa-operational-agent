---
name: operational-steps
description: Procedures, inputs, outputs and gates for every Operational agent step in the Hobasa agentic SDLC. Use when running any OPS-01, OPS-02, OPS-03, OPS-04, OPS-05, OPS-06… step.
---

# Operational agent steps

## OPS-01 Release Goals

- Trigger: Business Goals
- Action: Not defined in workbook; complete the readiness action
- Outcome: Release Goals
- Reads: org.business_goals
- Writes: iter.release_goals
- Gate: automated checks; sampled human evaluation

## OPS-02 Feature Kick off/Backlog Grooming

- Trigger: Release goals
- Action: Backlog grooming
- Outcome: Groomed backlog
- Reads: iter.release_goals
- Writes: iter.backlog
- Gate: automated checks; sampled human evaluation

## OPS-03 Iteration Planning ¹

- Trigger: Scheduled Iteration Planning Meeting
Availability of resource
User stories available in the azure board
- Action: Release and Iteration goals planning and clarifications
From the leave information, identify the team availability and plan a review without any blockers
Priority will be decided based on release and iteration goals
- Outcome: Iteration Goal

Clear Priorities

Timelines for the features to be shipped
Human reviewer availability plan so that we can get notification for blocker
Prioritized backlog for the iteration
- Reads: iter.backlog, org.capacity, org.calendar_rules
- Writes: iter.plan
- Gate: SM

## OPS-04 Daily Coordination Meeting

- Trigger: Scheduled meeting
- Action: Identify blockers and dependencies and mitigate them
- Outcome: Each team member is unblocked with Clear work items for the day
- Reads: iter.plan, org.dependency_tracker
- Writes: iter.blockers
- Gate: automated checks; sampled human evaluation

## OPS-05 Iteration Review Meeting

- Trigger: Scheduled meeting
- Action: Identify any gaps and share the feedback on the planned goal and readiness for the stakeholders demo
- Outcome: Confirmed Demo Readiness
Status of Planned Goal or Features
- Reads: iter.plan, iter.blockers
- Writes: iter.review
- Gate: automated checks; sampled human evaluation

## OPS-06 Iteration Retrospective Meeting

- Trigger: Scheduled meeting
- Action: Identify the concerns and feedbacks and log them so that we can resolve them and take learnings to improve
- Outcome: Learnings to improve
- Reads: iter.review
- Writes: iter.retro
- Gate: automated checks; sampled human evaluation

## OPS-07 Predemo ²

- Trigger: Completion of Iteration
- Action: Not defined in workbook; complete the readiness action
- Outcome: Scheduled event for all the attendees on the calendar
- Reads: iter.plan, org.calendar_rules
- Writes: iter.events
- Gate: automated checks; sampled human evaluation

## OPS-08 System Demo ²

- Trigger: Completion of Iteration
- Action: Not defined in workbook; complete the readiness action
- Outcome: Scheduled event for all the attendees on the calendar
- Reads: iter.plan, org.calendar_rules
- Writes: iter.events
- Gate: automated checks; sampled human evaluation

