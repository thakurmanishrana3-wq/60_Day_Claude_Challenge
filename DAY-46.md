INPUT
# Autonomous Agent Studio

You are an expert AI systems architect, agentic workflow designer, prompt engineer, automation engineer, conversation designer, UX designer, and senior frontend developer.

**Interview first, one question at a time, MCQ only** (free text only for a final "Other" option):
1. What kind of autonomous AI agent should we build? (offer domains/use cases)
2. Narrow follow-ups until the workflow is specific enough to automate — don't stop at just a domain.
3. Primary success criteria (accuracy, speed, quality score, approval, etc.)
4. Stopping condition — offer options suited to the chosen workflow.
5. Auto-design vs. customize components (if customize, ask which agents to include).

After the interview, build a single-page HTML app, **"Autonomous Agent Studio,"** that runs a real multi-agent orchestration pipeline live against the Claude API (`fetch` to `https://api.anthropic.com/v1/messages`, no key needed) — planning, executing, evaluating, remembering, improving, and repeating until a stopping condition is met.

Choose from these agents based on the workflow: Planner, Executor, Evaluator, Critic, Improver, Memory Manager, Safety Monitor, Final Reviewer. Give each a production-quality system prompt.

## Non-negotiable: it must be a real loop
- Implement the round portion as an actual `while`/`for` loop that re-calls Evaluator → Critic → Improver each pass with a **live API call every time**. No fixed/hardcoded sequence, and no pre-set round count — the number of rounds is a runtime result of the stop check, not a value chosen upfront.
- Every agent output shown in the UI (score, critique, reasoning) must be the literal text from that round's API response. No regex, canned strings, or rule-based scoring standing in for a model call.
- State must thread forward: each Improver call gets the prior round's evaluation + critique; each Evaluator call gets the current draft + rubric. Keep a running history array (score, critique, draft, delta) that the UI can display.
- Check every round, in order: (1) plateau — score improved less than a small delta for 2 straight rounds; (2) threshold — score crossed the target set at interview; (3) hard iteration cap (safety fallback only, not the intended ending). Log and surface which one fired.

## Dashboard
Show: workflow visualization (draw the loop as a real cycle — return arrow from Improver to Evaluator, with a separate branch to Final Reviewer once a stop condition fires, not a straight pipeline), active agent, live status, iteration history, activity log, intermediate outputs, memory updates, evaluation reports, round-over-round improvements, retry count, and final summary naming the exact stop reason. Round indicator should read as open-ended ("Round 3 — checking stop condition…"), not "Round 3 of 5."

Explain each agent's responsibility and how the stop-check governs information flow between rounds.

## Close with
Final output, agent performance summary, execution stats, architecture overview, extension ideas, and further prompts for building more advanced autonomous systems.

## Build constraints
Single self-contained HTML file, vanilla HTML/CSS/JS only, no external libraries. Commercial-grade polish: responsive, dark mode, smooth animations, interactive visualizations, robust error handling/retries, loading states, graceful failure recovery, zero syntax errors.

OUTPUT
[autonomous-agent-studio.html](https://github.com/user-attachments/files/31657139/autonomous-agent-studio.html)
Now the LinkedIn card and caption.Overlap between the chips and the mini diagram. Fixing the layout.Clean. Now the LinkedIn caption and delivery.**LinkedIn caption:**

---

Most "AI agent" demos are a lie.

They show you 5 pretty steps in a straight line and call it "autonomous." Fixed round count. No real feedback loop. No actual decision about when to stop.

So for Day 46 of #60DaysOfClaude, I built the real thing: **Autonomous Agent Studio.**

It's a LinkedIn post generator — but the point isn't the post. The point is the loop.

7 agents, one shared state:
→ Planner sets the strategy + rubric
→ Executor writes draft #1
→ Evaluator scores it live, every round
→ Critic finds what the Evaluator missed
→ Improver rewrites using both
→ Memory Manager logs the full round history
→ Final Reviewer closes it out

Then it actually loops — Evaluator → Critic → Improver → back to Evaluator — with a live Claude API call every single time. No hardcoded round count. It stops when one of three real conditions fires: the score plateaus, it crosses the target threshold, or it hits a safety cap.

Every score, critique, and rewrite you see in the UI is the literal model output from that round. Nothing simulated.

This is the difference between a workflow and an agent — the agent decides when it's done.

Try it, break it, watch the loop run.

#60DaysOfClaude #ABTalks60DayChallenge #LearnWithClaude #ABTalks
