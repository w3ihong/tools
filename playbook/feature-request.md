# Feature Development Playbook (AI-First Workflow)

A reusable process for taking a vague feature request from idea to production in a structured, repeatable manner. This workflow is optimized for modern AI-assisted development and can scale from small bug fixes to large production features.

---

# Core Principle

Requirements define outcomes.

Implementation plans define execution.

Rollout plans define how changes are introduced safely.

Keep these concerns separate:

- What needs to be built and why → Feature Request / PRD
- How it will be built → Technical Design / Implementation Plan
- How it will be released safely → Rollout Plan

---

# Standard Operating Procedure

Clarify → Triage → Plan → Build → Validate → Release → Learn

---

# High-Level Workflow

Feature Request
→ Triaging
→ Optional PRD / Requirement Specification
→ Implementation Plan
→ Implementation
→ Testing and Validation
→ Rollout Plan
→ Production Release
→ Post-Release Review

---

# 1. Feature Request

## Purpose

Capture the desired outcome in business and user terms.

The feature request should describe:

- The problem being solved
- Who the feature is for
- What the expected behavior is
- Constraints and success criteria

The feature request should not contain technical implementation details such as:

- Database tables
- API endpoints
- Specific components or classes
- Framework-specific instructions
- Code-level recommendations

## Example

Users should be able to save products to a wishlist and access them later from their profile.

## Typical Contents

- Title
- Problem statement
- User story
- Acceptance criteria
- Constraints
- Success metrics

---

# 2. Triaging

## Purpose

Perform a rapid assessment to determine:

- Priority
- Complexity
- Risk
- Estimated effort
- Dependencies
- Required documentation
- Recommended next step

Triaging determines how much process and documentation the feature requires.

## Triage Template

- Problem
- Priority
- Complexity (Low / Medium / High)
- Risk (Low / Medium / High)
- Estimated Effort
- Dependencies
- Documentation Needed
- Recommended Next Step

## Output Example

- Priority: High
- Complexity: Medium
- Risk: Low
- Estimated Effort: 2–3 days
- Dependencies: None
- Documentation Needed: Lightweight Feature Spec
- Recommended Next Step: Generate Implementation Plan

---

# 3. PRD (Product Requirements Document) — Optional

## Purpose

Formalize detailed requirements when the feature is complex, ambiguous, or involves multiple stakeholders.

## Use When

- Requirements are unclear
- Business logic is substantial
- Multiple stakeholders must align
- Scope must be documented explicitly

## Skip When

- The feature is small and straightforward
- You are working alone
- The feature request already contains enough detail

## Typical Contents

- Executive summary
- Problem statement
- Goals
- Non-goals
- User stories
- Functional requirements
- Non-functional requirements
- Acceptance criteria
- Success metrics
- Open questions

---

# 4. Technical Design (Optional)

## Purpose

Describe the proposed system architecture and major technical decisions.

## Use When

- The feature affects core architecture
- Multiple implementation approaches exist
- Significant technical tradeoffs must be evaluated
- Security, scalability, or performance concerns are important

## Typical Contents

- Current architecture overview
- Proposed architecture
- Affected systems and components
- Data model changes
- API contracts
- Alternatives considered
- Risks
- Rollback strategy

---

# 5. Implementation Plan

## Purpose

Translate requirements into concrete engineering tasks.

This is the most important artifact for coding agents.

## Inputs

- Feature request
- PRD (if used)
- Technical design (if used)
- Existing codebase
- Project constraints

## Typical Contents

- Objective
- Assumptions
- Impact analysis
- Affected files and modules
- Data flow changes
- Task breakdown
- Execution order
- Testing strategy
- Risks and rollback notes

## Output

A detailed, step-by-step plan that can be executed by a developer or coding agent.

---

# 6. Implementation

## Purpose

Build the feature according to the implementation plan.

## Best Practices

- Work in small, reviewable increments
- Follow existing project patterns
- Keep tests close to code
- Use feature flags for risky changes
- Validate continuously

---

# 7. Testing and Validation

## Purpose

Verify that the feature satisfies requirements and does not introduce regressions.

## Types of Testing

- Unit tests
- Integration tests
- End-to-end tests
- Regression tests
- Performance tests
- Security tests

## Validation Questions

- Does the feature satisfy all acceptance criteria?
- Are edge cases handled?
- Were existing features affected?
- Are performance and reliability acceptable?

---

# 8. Rollout Plan

## Purpose

Deploy safely and maintain the ability to recover quickly.

## Use When

- Production-critical behavior is modified
- Database migrations are involved
- Breaking changes are possible
- Gradual rollout is desired

## Typical Contents

- Deployment steps
- Feature flag strategy
- Monitoring metrics
- Rollback procedure

---

# 9. Production Release

## Purpose

Deploy the feature to production and monitor system health.

## Monitor

- Error rates
- Latency
- Resource usage
- Business metrics
- User feedback

---

# 10. Post-Release Review

## Purpose

Confirm that the feature achieved its intended outcome.

## Activities

- Review usage and adoption metrics
- Analyze incidents or regressions
- Gather stakeholder feedback
- Identify follow-up improvements

---

# Decision Matrix

| Complexity | Risk | Recommended Process |
|----------|----------|----------------|
| Low | Low | Feature Request → Implementation Plan |
| Medium | Low | Feature Request → Lightweight PRD → Implementation Plan |
| Medium | High | PRD → Technical Design → Implementation Plan |
| High | High | Full planning, staged rollout, and monitoring |

---

# Lean AI-First Workflows

## Small Features

Feature Request
→ Triaging
→ Implementation Plan
→ Implementation
→ Testing
→ Merge

## Medium Features

Feature Request
→ Triaging
→ Lightweight PRD
→ Implementation Plan
→ Implementation
→ Testing
→ Deploy

## Large or High-Risk Features

Feature Request
→ Triaging
→ PRD
→ Technical Design
→ Implementation Plan
→ Implementation
→ Staged Rollout
→ Monitoring

---

# Minimal Recommended Workflow

For most solo and AI-assisted development work:

1. Receive Feature Request
2. Triage the Request
3. Clarify Requirements if Necessary
4. Generate Implementation Plan
5. Review and Refine the Plan
6. Execute with a Coding Agent
7. Validate Against Acceptance Criteria
8. Deploy with Rollback Capability
9. Monitor and Iterate

---

# Documents and Their Purpose

| Document | Core Question Answered |
|------|------|
| Feature Request | What should be built and why? |
| PRD | What are the detailed requirements? |
| Technical Design | How should the system solve the problem? |
| Implementation Plan | What tasks need to be executed and in what order? |
| Test Plan | How will correctness be verified? |
| Rollout Plan | How will the feature be released safely? |

---

# Recommended Project Structure

docs/
- feature-request.md
- prd.md (optional)
- technical-design.md (optional)
- implementation-plan.md
- test-plan.md (optional)
- rollout-plan.md (optional)

---

# Practical Rules of Thumb

- Every feature should be triaged.
- Every non-trivial feature should have an implementation plan.
- PRDs are optional and should be created when ambiguity or complexity warrants them.
- Technical design documents are used when architecture decisions and tradeoffs are significant.
- Rollout plans are necessary when production risk is meaningful.
- The implementation plan is the primary artifact used by coding agents.

---

# AI-First Development Philosophy

The feature request defines the desired outcome.

The implementation plan defines the execution path.

The coding agent analyzes the codebase, identifies affected areas, and executes tasks incrementally.

The developer's role is to:

- Clarify requirements
- Review plans
- Validate assumptions
- Monitor execution
- Approve deployment

---

# Final Mental Model

When starting any new feature, think in terms of:

1. What problem are we solving?
2. How important and risky is it?
3. How much documentation is required?
4. What is the implementation plan?
5. How will we verify correctness?
6. How will we deploy safely?
7. Did the feature achieve its intended outcome?

---

# Personal SOP

Clarify → Triage → Plan → Build → Validate → Release → Learn
