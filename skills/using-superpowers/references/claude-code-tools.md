# Claude Code Tool Notes

Claude Code is the reference harness: skills speak its vocabulary
(`Agent` for a subagent dispatch, todos, `Skill`). These notes cover the
one place Claude Code can run a plan cheaper than the skills' default
shape. It is opt-in by your human partner and changes nothing the skills
require.

## Cheaper orchestration for subagent-driven development

A superpowers:subagent-driven-development run pays for the controller
session on every dispatch it reads, plus a fresh implementer and a fresh
reviewer per task, each of which re-reads the codebase from zero. The
controller is the one seat you can move, and the saving is real only when
your session model is more expensive than the tier you move it to.
Claude Code supports nested subagents (three layers below
the main conversation by default; `CLAUDE_CODE_MAX_SUBAGENT_SPAWN_DEPTH`
adjusts it), so the whole loop can run one layer down.

When your human partner asks for it — or has said the session model is
too expensive to spend on coordination — dispatch ONE orchestrator
subagent with the plan path and the instruction to use
superpowers:subagent-driven-development end to end. Ask which model to run
it on before you name one; without an approved name, leave `model` off so
it inherits your session's. The orchestrator dispatches its own
implementers and reviewers, and it cannot reach your human partner, so
collect the approved model names before you dispatch it and pass them in.
With no approvals, instruct it to leave `model` off every spawn. The
workspace and ledger live on disk, so nothing is lost to
the extra layer. Its final message must carry the "Rulings I made" list
verbatim — that list is how the decisions reach your human partner, and
you relay it, not summarize it.

Do this only for a whole plan. Nesting a single task's dispatch buys
nothing and adds a seat.
