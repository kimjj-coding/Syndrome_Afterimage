# Copilot instructions — SYNDROME: AFTERIMAGE

## Project constraints
- This is a browser-based web game. Do not silently convert it into a native mobile or console project.
- The developer is a beginner working with a near-zero budget. Prefer small, reversible changes and explain commands and tests.
- Engine/framework, camera, controls, story, character, mental-health framing, hidden variables, thresholds, ending count, and full content scope remain undecided unless the user explicitly approves a decision.
- MBV/RI, numeric thresholds, `look back +5`, and six endings are unvalidated historical ideas. Do not implement them by default.
- Do not add chase AI, 3D/2.5D camera switching, save systems, branching trees, or distortion effects merely because older notes mention them.

## Read before implementation
- Read `docs/syndrome-afterimage/00_PROJECT_STATUS.md` and `docs/syndrome-afterimage/01_RESEARCH_ROADMAP.md`.
- Read the relevant research/spec/test document before implementing a feature.
- Distinguish verified facts, source-based interpretation, hypotheses, and pending decisions.
- If a requirement is undecided, ask for clarification or propose a minimal proof of concept rather than inventing the decision.

## Change discipline
- Implement one clearly scoped feature at a time.
- Before coding, state the goal, files expected to change, behavior, and test plan.
- Avoid unrelated refactors and unnecessary dependencies.
- Use explicit state transitions and predictable reset behavior.
- Check the repository's actual scripts and build configuration before recommending commands such as `npm run dev`.
- Include failure and restart paths in tests where relevant.

## Accessibility and portrayal
- Avoid strong flashing, severe screen shake, rapid zoom, or sudden loud audio as default effects.
- Reducing or disabling effects must not hide required puzzle or navigation information.
- Do not equate mental illness with violence, evil, moral failure, or a diagnostic score.
- Do not graphically depict or romanticize self-harm.
- Follow the checklist in `docs/syndrome-afterimage/06_ACCESSIBILITY.md`; do not claim WCAG compliance based only on a “3 Hz” rule.

## Completion report
Report: (1) changed files, (2) behavior changed, (3) checks actually run and results, (4) unverified risks, (5) next smallest test. Never claim a test passed if it was not run.
