# Handling a Report That Isn't DONE

Part of superpowers:subagent-driven-development.

**DONE_WITH_CONCERNS:** The implementer completed the work but flagged doubts. Read the concerns before proceeding. If the concerns are about correctness or scope, address them before review. If they're observations (e.g., "this file is getting large"), note them and proceed to review.

**NEEDS_CONTEXT:** The implementer needs information that wasn't provided. Provide the missing context and resume the implementer (steer it if it is still running). Its context stays intact, so a fresh dispatch pays only for what a resume gives free.

**BLOCKED:** The implementer cannot complete the task. Assess the blocker:
1. If it's a context problem, provide more context and resume the implementer (steer it if it is still running), keeping the same model
2. If the task requires more reasoning, propose a more capable model to your human partner and give the reason. Re-dispatch on a tier different from the caller's only after your partner approves that name
3. If the task is too large, break it into smaller pieces
4. If the plan itself is wrong, rule on the correction, ledger it, and re-dispatch with the ruling carried in the dispatch

**Never** ignore an escalation or force the same model to retry without changes. If the implementer said it's stuck, something needs to change.
