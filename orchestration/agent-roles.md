# Agent Roles

This document summarizes the current custom agent roles defined under `.github/agents/` for the Project Pulse orchestration exercise.

## Orchestrator
- Source: `.github/agents/orchestrator.agent.md`
- Role: Coordinate the work across the specialist agents.
- Responsibilities:
  - Turn the Planner's implementation strategy into phases.
  - Assign explicit file scopes and dependencies.
  - Run work in parallel only when scopes do not overlap.
  - Keep overlapping or dependent work sequential.
  - Verify that the integrated result hangs together.
  - Report progress clearly and surface blockers.
- Restrictions:
  - Does not implement code itself.
  - Does not stage, commit, or push changes.

## Planner
- Source: `.github/agents/planner.agent.md`
- Role: Create implementation plans and research the repository.
- Responsibilities:
  - Read relevant files and repository context before planning.
  - Identify edge cases, risks, dependencies, and implicit requirements.
  - Produce a practical ordered plan with file assignments.
  - Specify what can run in parallel and what must be sequential.
  - Provide validation expectations and open questions.
- Restrictions:
  - Does not write code.
  - Does not stage, commit, or push changes.

## Coder
- Source: `.github/agents/coder.agent.md`
- Role: Implement code and runnable application support.
- Responsibilities:
  - Write code and fix bugs within the assigned file scope.
  - Create support config when assigned, including `.vscode/launch.json`.
  - Use clear, deterministic, and testable implementation.
  - Validate changes before reporting completion.
- Restrictions:
  - Stays within the Orchestrator-assigned file scope.
  - Does not stage, commit, or push changes.

## Designer
- Source: `.github/agents/designer.agent.md`
- Role: Handle UI/UX, visual design, and information hierarchy.
- Responsibilities:
  - Create polished dashboard styling and layout guidance.
  - Focus on usability, accessibility, and readable spacing.
  - Use deterministic CSS hooks such as `.dashboard` and `.project-card`.
  - Prioritize user outcomes over decorative changes.
- Restrictions:
  - Stays within the assigned design scope.
  - Does not stage, commit, or push changes.
