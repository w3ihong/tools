# Feature Development Playbook (AI-First Workflow)

A structured end-to-end workflow for transforming product ideas into production-ready features using AI-assisted development.

This version reflects a modern, lean engineering process where:
- Requirements are unified into a PRD-first artifact
- Technical research is explicitly separated from planning
- Implementation is split into high-level and repository-level planning

---

# Core Principle

Requirements define outcomes.

Research evaluates feasibility.

Design defines the technical approach.

Execution plans define code-level changes.

---

# Standard Workflow

Requirements (Feature Request → PRD)
→ Triaging
→ Technical Research / Solution Exploration
→ High-Level Implementation Plan
→ Repository-Level Implementation Plan
→ Implementation
→ Testing & Validation
→ Rollout
→ Post-Release Review

---

# 1. Requirements (PRD-First Approach)

## Purpose

Define *what* needs to be built and *why* in a structured, testable format.

In this workflow, the PRD replaces the traditional standalone feature request.

A "feature request" is treated as the **raw input**, which is immediately refined into a PRD.

---

## Inputs

- Stakeholder intent
- Business requirements
- User problems
- Constraints
- Success expectations

---

## PRD Contents

A PRD should include:

- Title
- Problem Statement
- Goals
- Non-Goals
- User Stories
- Functional Requirements
- Non-Functional Requirements
- Acceptance Criteria
- Success Metrics
- Constraints & Assumptions
- Open Questions

---

## Key Rule

No technical implementation details should be included in the PRD, such as:

- APIs
- Database schemas
- Framework choices
- Code structure
- Infrastructure design

---

## Output

A structured, validated PRD that becomes the single source of truth for downstream engineering work.

---

# 2. Triaging

## Purpose

Perform a rapid assessment of the PRD to determine:

- Priority
- Complexity
- Risk
- Effort estimate
- Dependencies
- Required depth of planning

---

## Outputs

- Go / No-Go decision
- Required documentation level
- Initial risk classification
- Suggested next step (research required or not)

---

## Triage Template

- Problem Summary
- Priority
- Complexity (Low / Medium / High)
- Risk (Low / Medium / High)
- Estimated Effort
- Dependencies
- Documentation Required
- Recommended Next Step

---

# 3. Technical Research / Solution Exploration

## Purpose

Evaluate possible technical approaches before committing to an architecture.

This is the **decision-making layer between PRD and design**.

---

## Inputs

- PRD
- System constraints
- Existing architecture context

---

## Activities

- Evaluate multiple implementation approaches
- Compare tools, frameworks, and services
- Assess tradeoffs:
  - scalability
  - performance
  - cost
  - complexity
  - maintainability
- Identify risks and constraints
- Validate feasibility

---

## Output

- Recommended technical approach
- Alternatives considered
- Tradeoff analysis
- Risks and mitigations

---

## Key Rule

Research does not define the final system design. It only informs it.

---

# 4. High-Level Implementation Plan

## Purpose

Translate PRD + research into a system-level solution.

This defines the **architecture and workstreams**, not code-level changes.

---

## Inputs

- PRD
- Research findings

---

## Contents

- Objective summary
- Requirements recap
- Selected technical approach
- System architecture overview
- Data flow design
- Major components affected
- Integration points
- Risks and mitigations
- Rollback strategy
- Workstream breakdown

---

## Output

A validated architectural plan that is ready for decomposition into repository-level tasks.

---

# 5. Repository-Level Implementation Plan

## Purpose

Convert the high-level design into concrete codebase changes.

This is the primary execution document for coding agents.

---

## Inputs

- High-level implementation plan
- Codebase context

---

## Contents

- File-by-file changes
- New modules/components
- API route changes
- Database migrations
- Function-level modifications
- Task ordering
- Test additions
- Validation steps

---

## Output

A deterministic execution plan that can be followed step-by-step.

---

# 6. Implementation

## Purpose

Execute the repository-level plan.

---

## Best Practices

- Small, incremental changes
- Frequent commits
- Maintain alignment with existing architecture
- Write tests alongside implementation
- Use feature flags for risky changes

---

# 7. Testing & Validation

## Purpose

Ensure correctness and prevent regressions.

---

## Testing Layers

- Unit tests
- Integration tests
- End-to-end tests
- Regression tests
- Performance checks (if needed)

---

## Validation Criteria

- Meets PRD acceptance criteria
- No regressions introduced
- Edge cases handled
- Performance acceptable

---

# 8. Rollout

## Purpose

Safely deploy the feature into production.

---

## Use When

- Production systems are affected
- Data migrations are involved
- Behavior changes are non-trivial
- Risk exists

---

## Components

- Deployment steps
- Feature flag strategy
- Gradual rollout plan
- Monitoring metrics
- Rollback procedure

---

# 9. Post-Release Review

## Purpose

Validate whether the feature achieved its intended outcome.

---

## Activities

- Monitor usage metrics
- Analyze error rates
- Collect user feedback
- Evaluate success metrics
- Identify follow-ups

---

# Decision Matrix

| Complexity | Risk | Process |
|----------|------|--------|
| Low | Low | PRD → Implementation Plan → Execution |
| Medium | Low | PRD → Triaging → Research → Implementation Plan |
| Medium | High | PRD → Research → High-Level Design → Repo Plan |
| High | High | Full pipeline with staged rollout and monitoring |

---

# Lean AI-First Variants

## Small Features

PRD → Triaging → Implementation Plan → Implementation → Testing → Merge

## Medium Features

PRD → Triaging → Research → High-Level Plan → Repo Plan → Implementation → Deploy

## Large Features

PRD → Triaging → Research → High-Level Design → Repo Plan → Implementation → Staged Rollout → Monitoring

---

# Minimal Recommended Workflow

1. Convert feature request into PRD
2. Triage PRD
3. Perform technical research if needed
4. Create high-level implementation plan
5. Convert into repository-level plan
6. Execute via coding agent
7. Validate and test
8. Deploy safely
9. Review outcomes

---

# Key Relationships Between Artifacts

| Artifact | Purpose |
|------|------|
| PRD | Defines what and why |
| Research | Evaluates possible solutions |
| High-Level Plan | Defines architecture |
| Repo-Level Plan | Defines code changes |
| Implementation | Executes changes |
| Rollout Plan | Ensures safe deployment |

---

# AI-First Engineering Philosophy

The system is optimized for AI-assisted execution:

- PRD provides structured intent
- Research reduces architectural uncertainty
- High-level planning ensures system coherence
- Repo-level planning enables deterministic execution
- Coding agents perform implementation

---

# Final Mental Model

When starting any feature:

1. What problem are we solving? (PRD)
2. How complex or risky is it? (Triage)
3. What are the possible technical approaches? (Research)
4. What is the system design? (High-level plan)
5. What exact code changes are needed? (Repo plan)
6. How do we ship safely? (Rollout)
7. Did it achieve its goal? (Review)
