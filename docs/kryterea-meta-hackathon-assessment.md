# Kryterea — Meta Global AI Developer Hackathon Assessment

**Assessment date:** 24 October 2026
**Event window:** 26 October–4 November 2026; judging 4–8 November; winners 9 November
**Recommended track:** Startup track
**Recommended theme:** Build for Your World

## Executive verdict

Kryterea is technically stronger than the average hackathon project but currently weaker as a competition entry because its value is diffuse and its proof is hidden. It reads as a broad execution platform for structured analysis rather than one product that a judge can understand, use, and remember in three minutes.

My board-level verdict is **conditional support**: continue, but freeze the platform expansion and convert the existing foundation into one undeniable workflow. My judge-level verdict is **not a finalist in its current presentation**. With a focused wedge, a visible Meta-model implementation, a reliable seeded demo, and a clean submission story, it can become a serious contender.

The event’s published structure favors this strategy: the startup track is judged on technical execution and whether the project holds up in production; the Build for Your World theme favors a domain problem the builder understands firsthand. Meta’s current documentation also makes integration practical because Meta Model API is OpenAI-compatible, supports structured output, tool calling, file handling, reasoning, and long context.

## Evidence from the repository

### Strengths

- The product has a coherent architecture: conversation → context engine → capability resolver → AI orchestrator → work → quality → provenance.

- There is substantial domain depth in the Business Analysis OS, capability registry, playbooks, artefacts, evaluation, traceability, sign-off, and assurance surfaces.

- The repository has a real AI boundary in `packages/ai`, with adapters and provider/catalogue abstractions rather than provider calls scattered across the product.

- A dedicated Meta adapter exists in the implementation history (`feat/i4-meta-model-adapter`), including Meta configuration, gateway changes, activation documentation, catalogue tests, gateway tests, and worker environment wiring.

- The product surface is broad enough to support a compelling end-to-end demo: projects, conversations, playbooks, research, artefacts, evaluations, traceability, GitHub attachments, assurance runs, findings, and sign-off.

- Security and governance intent are unusually mature for a hackathon project: Clerk-derived identity, ownership boundaries, secret hygiene checks, webhook validation intent, read-only OS rules, and provenance requirements.

### Weaknesses and verified risks

- The public homepage says only: “Turn ideas into structured, evidence-backed work.” That is accurate but generic and does not communicate the breakthrough.

- The product has too many possible stories: business analysis, research, deliverables, quality, assurance, knowledge, billing, integrations, and enterprise-style governance. Judges will not infer the core value from architecture.

- `pnpm check` currently fails at the architecture gate. Secret hygiene passed, but six routes were reported as database-boundary violations: email unsubscribe, GitHub health, signing routes, and Resend webhook handling.

- Full verification is currently unavailable in this worktree because `node_modules` is missing. The check therefore did not reach reliable lint, typecheck, test, OS validation, or registry validation evidence.

- The presence of a Meta adapter is not enough. The final demo must prove that Meta’s model materially performs the core reasoning, tool use, or structured-output step.

- The likely hackathon failure mode is spending the remaining time on infrastructure breadth, billing, settings, or generic polish instead of one golden path.

- A judge may encounter authentication, empty state, missing environment variables, unseeded data, slow background work, or an integration failure before seeing the product’s differentiator.

- The current architecture is production-minded, but production-minded code is not the same as production proof. You need observable quality, failure recovery, latency, and a repeatable demo.

## Scorecard

| Dimension | Current estimate | Why | Target before submission |
| --- | --- | --- | --- |
| Problem clarity | 5/10 | Broad platform language; pain is not concrete | 9/10 |
| Originality | 6/10 | Governed, traceable work is differentiated, but hidden | 8/10 |
| Meta fit | 4/10 visible / 8/10 potential | Adapter exists, but the judge-facing experience does not prove it | 9/10 |
| Technical ambition | 8/10 | Strong orchestration, capability, assurance, and provenance concepts | 9/10 |
| Demo reliability | 4/10 verified | Quality gate fails and dependencies are not installed | 9/10 |
| Production credibility | 6/10 | Architecture is serious; evidence and operational proof are incomplete | 8/10 |
| Business potential | 7/10 | Clear path to professional and team workflows | 8/10 |
| Memorability | 4/10 | Current wording sounds like many AI productivity products | 9/10 |

## The product to submit

Do not submit “Kryterea, an AI operating system for analysis.” Submit this:

> **Kryterea Assurance Copilot turns a messy product change into a decision-ready, evidence-backed ship/no-ship pack. It reads the brief and connected implementation evidence, applies governed analysis capabilities, uses Meta’s model to reason over the context, identifies gaps and risks, produces acceptance criteria and a traceability map, and routes the result for human sign-off.**

This is narrower, more visual, more defensible, and better aligned with the code already present.

### The golden path

1. Start from a seeded product change: for example, “Add passwordless sign-in for a fintech app.”

1. Attach a short product brief and connect a GitHub repository or simulated change set.

1. Ask: **“Can we ship this change safely? Produce the evidence and decisions a team needs.”**

1. Kryterea uses the Meta model through the adapter, resolves the relevant Business Analysis OS capabilities, and calls tools for repository/project evidence.

1. It returns structured outputs: requirements, assumptions, risks, acceptance criteria, open questions, evidence links, and a confidence/quality score.

1. A quality pass flags unsupported claims or missing evidence.

1. The user edits or approves the result; Kryterea generates a concise decision pack and sign-off request.

1. The final screen shows model/provider, capability IDs or versions, evidence sources, quality findings, and the human approval state.

The magic moment is not a long chat response. It is the transformation from ambiguity to a defensible decision with traceability.

## What to build, in priority order

### P0 — Must exist before submission

1. **Freeze the scope.** No new billing, settings, enterprise, or catalogue work unless it directly enables the golden path.

1. **Make Meta the visible primary model.** Activate the existing adapter, expose the selected Meta model in the UI, and store model/provider metadata on each material run.

1. **Create one seeded demo project.** The judge must reach the aha moment without manual database setup, empty states, or hidden operator steps.

1. **Implement the complete golden path.** Intake → context/evidence → Meta reasoning → structured artefact → quality check → traceability → sign-off/export.

1. **Make the output visually legible.** Use a decision summary, risk severity, evidence links, acceptance criteria, and a clear “what changed / what remains unresolved” panel.

1. **Add a deterministic demo mode only as a safe fallback.** It must be clearly labelled as a fixture/fallback, never as fabricated live AI. The primary path must call Meta.

1. **Install dependencies and run the full checks.** Do not claim production readiness until typecheck, lint, unit tests, build, and the critical Playwright journey pass.

1. **Fix the six architecture violations or formally isolate them.** Do not weaken the architecture checker; move database access behind the approved application/repository boundary and add regression coverage.

1. **Deploy a stable public URL.** Test it from a clean browser, incognito mode, and a second network if possible.

1. **Record a backup demo video.** A live demo should be preferred, but the submission must survive a failed API call, cold start, or auth issue.

### P1 — Strong score multipliers

- Add a “Why this answer is trustworthy” drawer showing evidence, capability/version, model, quality checks, and unresolved uncertainty.

- Add a deliberate failure case: remove evidence or create a contradictory requirement and show Kryterea refusing to overclaim and asking for clarification.

- Add a small benchmark: compare a raw LLM response against Kryterea’s governed output on completeness, unsupported claims, traceability, and time-to-decision.

- Show model routing or reasoning configuration in an operator-safe way; do not dump implementation details into the main user experience.

- Capture real user validation from 3–5 business analysts, product managers, founders, or engineers. Use quotes and one before/after metric in the submission.

- Include a one-page architecture diagram showing Meta Model API, the capability registry, evidence/context boundary, orchestration, quality loop, and provenance.

### P2 — Only if P0 is complete

- Voice intake using Meta Voice Transcribe.

- Image/document understanding with Meta models.

- Muse Image for a visual artefact or diagram.

- Additional providers or open-weight deployment comparisons.

Do not add multimodality merely to collect logos. Add it only if it makes the golden path visibly better.

## Ten-day execution plan

### Before kickoff: 24–25 October

- Decide the startup-track positioning and lock the one-sentence pitch.

- Repair the quality gate and install dependencies.

- Activate and smoke-test the Meta adapter with a real model call.

- Prepare the seeded project, sample brief, evidence set, and expected output.

- Draw the demo journey and remove every nonessential click.

### Days 1–2: 26–27 October

- Integrate Meta into the golden path, not a side-by-side toy screen.

- Add structured output schema, tool calls, timeout/retry handling, and run metadata.

- Make the first end-to-end path work with one happy case.

### Days 3–4: 28–29 October

- Build the decision pack UI: summary, risks, evidence, acceptance criteria, traceability, and sign-off.

- Add the quality loop and the deliberate missing-evidence case.

- Add visible provenance and capability/version information.

### Days 5–6: 30–31 October

- Run user tests and collect evidence. Watch what users misunderstand.

- Remove features that do not improve time-to-decision or trust.

- Fix the six architecture violations, then run all checks.

### Days 7–8: 1–2 November

- Harden deployment, seed/reset flow, rate limits, loading states, errors, and fallback behavior.

- Run the benchmark and capture before/after metrics.

- Record a rough demo and cut anything that slows the story.

### Days 9–10: 3–4 November

- Freeze code by the morning of 3 November.

- Run a clean-browser rehearsal three times.

- Record the final video, screenshots, architecture diagram, and README.

- Submit well before the 4 November 9:00 PM ET deadline; do not optimize the last hours for new features.

## Recommended three-minute demo script

**0:00–0:20 — Problem.** “Product teams lose days turning ambiguous changes into requirements, risk decisions, and sign-off evidence. Generic chat produces prose; it does not produce accountable work.”

**0:20–0:40 — Input.** Paste the passwordless-login change brief and attach the repository evidence.

**0:40–1:25 — Meta-powered reasoning.** Show Kryterea selecting the relevant governed capabilities, using the Meta model, and producing structured requirements, risks, and open questions.

**1:25–2:05 — Trust moment.** Open evidence and traceability. Show one unsupported or missing item being flagged instead of silently invented.

**2:05–2:35 — Action.** Generate acceptance criteria and the decision pack; route it for human sign-off.

**2:35–2:55 — Technical proof.** Show the model/provider, tool call or structured-output trace, capability version/hash, and quality result.

**2:55–3:00 — Close.** “Kryterea is the governed execution layer between AI output and a decision a real team can stand behind.”

## Investor and board questions you must be able to answer

### Who pays?

Start with professional users who already pay with time, consulting fees, or project delay: business analysts, product managers, delivery leads, and boutique consultancies. The first wedge is not all knowledge work; it is high-stakes change analysis and assurance.

### Why not ChatGPT, Claude, or an internal template?

Because the product does not stop at an answer. It resolves a governed method, uses project-specific evidence, preserves traceability, detects gaps, creates a versioned artefact, and routes human approval. If the demo cannot make that difference obvious, the moat is only asserted.

### What is the moat?

The moat is the governed capability source plus the execution/provenance layer: capability registry, domain methods, evidence graph, quality checks, reusable artefacts, and feedback from real work. The model is replaceable; the operational context and quality system are not.

### What is the wedge and expansion path?

Wedge: decision-ready change analysis and assurance. Expansion: research, requirements, delivery artefacts, quality gates, sign-off, and team knowledge. Avoid claiming a universal AI operating system before the wedge has repeat usage.

### What is the key metric?

Time from ambiguous request to approved, evidence-backed decision pack. Secondary metrics: unsupported-claim rate, rework rate, evidence coverage, acceptance-criteria completeness, and weekly retained projects.

## Red flags that would make me vote against the entry

- The demo starts with a blank workspace or a login problem.

- The presenter explains architecture for two minutes before showing the user outcome.

- Meta is mentioned in the README but not visibly used in the live workflow.

- The output is a generic paragraph rather than structured work with evidence.

- The product claims “trust” but cannot show provenance, uncertainty, or failure handling.

- The team says the app is production-ready while the repository quality gate is red.

- The demo includes five features and proves none of them deeply.

- The submission overclaims customer traction, model performance, or reliability.

## Final recommendation

Do not attempt to win by building the largest system. Win by making the existing system look inevitable for one painful problem.

The winning sequence is:

**narrow the story → expose Meta in the critical path → show a measurable transformation → prove trust and failure handling → make the demo repeatable → submit a clean, credible startup narrative.**

Kryterea has enough technical substance to deserve that chance. Its biggest competitor is not another hackathon project; it is its own breadth.

## Strategic clarification: the professional AI copilot layer for software development

This broader idea improves Kryterea as a company, but it must not become the hackathon product description.

### The stronger company thesis

> **Kryterea is the professional AI copilot layer for the software development lifecycle: it helps each role turn intent, evidence, and decisions into governed artifacts and deliverables, while preserving traceability across the lifecycle.**

Business analysis is the entry point because it is artifact-rich, methodical, and close to the ambiguity that causes downstream rework. Product management, project/program management, UX, engineering, QA, security, compliance, and release management can become expansion surfaces because each role produces structured work that depends on upstream decisions and creates inputs for downstream roles.

This is a better long-term thesis than “AI for business analysis” because it describes a larger system of value: **professional work moving through an evidence and artifact graph, with AI copilots operating inside governed workflows.**

### What this changes in the board assessment

The company becomes more investable if you can show a credible expansion architecture:

```
Business analysis
  → product management
  → project/program management
  → UX/design
  → engineering
  → QA/testing
  → security/compliance
  → release/operations
```

However, the expansion must be earned through shared primitives, not announced as a list of future personas. The shared primitives are:

- Work context and project memory

- Role-specific capability packs

- Artifact and deliverable schemas

- Evidence and source traceability

- Cross-artifact dependency mapping

- Quality gates and validation

- Human review, approval, and sign-off

- Provenance across model, method, input, and output

The strategic moat is therefore not “a chatbot for every profession.” It is a **professional work graph with governed AI execution**.

### What this changes in the hackathon pitch

Do not lead with:

> “We are building an AI copilot for every profession in the SDLC.”

That sounds expansive, premature, and difficult to judge in ten days.

Lead with:

> **“Kryterea is building the professional AI copilot layer for the SDLC. We start with business analysis because that is where ambiguity becomes requirements, risks, and decisions. In this demo, Kryterea turns one software change into a traceable, evidence-backed ship/no-ship decision pack using Meta’s model.”**

This gives the judge both the immediate product and the larger strategic direction in one sentence.

### The correct product hierarchy

Use three levels consistently:

**Vision:** The professional AI copilot layer for the software development lifecycle.

**Current wedge:** Business-analysis and assurance copilot for turning ambiguous software changes into decision-ready, evidence-backed artifacts.

**Expansion:** Product, project/program, UX, engineering, QA, security, compliance, and release copilots connected through the same work graph.

Never make the expansion list compete with the demo. The expansion should appear in one architecture slide and one closing paragraph, not as eight half-built product surfaces.

### Why business analysis is a credible starting point

Business analysis is not a random first niche. It is strategically useful because:

1. It sits upstream of many downstream SDLC artifacts.

1. Its work is highly structured and therefore suitable for capability packs and quality checks.

1. Poor requirements create measurable downstream cost and rework.

1. It naturally requires evidence, assumptions, stakeholder decisions, traceability, and sign-off.

1. It gives Kryterea a data and workflow foundation that can later serve product, delivery, engineering, QA, and compliance.

The board-level question is not “Can Kryterea serve every SDLC role?” It is:

> **Can Kryterea own one high-value artifact chain deeply enough that adjacent roles naturally need the same context and provenance?**

That is the expansion test.

### Revised company positioning

A strong company-level positioning statement is:

> **Kryterea gives every professional role in the software lifecycle an AI copilot that works from shared project context, uses role-specific methods, produces real deliverables, and preserves the evidence and decisions behind them.**

A sharper hackathon positioning statement is:

> **Kryterea Assurance Copilot helps software teams decide whether a change is ready to ship by turning briefs and repository evidence into governed requirements, risks, acceptance criteria, and sign-off artifacts.**

The first statement attracts investors and future customers. The second wins judges.

### Strategic warning

The phrase “every profession” is directionally correct but commercially dangerous if used without sequencing. Different professions have different:

- Liability and approval requirements

- Artifact standards

- Data permissions

- Quality rubrics

- Integration needs

- Buying centers

- Failure costs

Therefore, expand by adjacent artifact chains rather than by persona count. For example:

```
Change brief
  → requirements and risks
  → product decision
  → delivery plan
  → implementation evidence
  → test evidence
  → release decision
```

This is a stronger roadmap than “add a PM copilot, then an engineering copilot, then a QA copilot.” It keeps the shared context and artifact graph at the center.