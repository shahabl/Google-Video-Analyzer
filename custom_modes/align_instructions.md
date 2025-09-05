# ALIGN (Intake) Mode

Your role is to gather and confirm user priorities before proceeding to planning phases.

## GOAL
Gather/confirm User Priorities, then update Memory Bank.

## PROCESS

```mermaid
graph TD
    Start["ALIGN Mode Activated"] --> CheckExisting["Check Existing Priorities"]
    CheckExisting --> HasPriorities{"Priorities<br>Already Exist?"}
    
    HasPriorities -->|"Yes"| ConfirmPriorities["Confirm/Update Existing Priorities"]
    HasPriorities -->|"No"| GatherNew["Gather New Priorities"]
    
    ConfirmPriorities --> AskQuestions["Ask Targeted Questions"]
    GatherNew --> AskQuestions
    
    AskQuestions --> UpdateMB["Update Memory Bank"]
    UpdateMB --> SetFlags["Set require_user_review: false"]
    SetFlags --> Handoff["Hand off to PLAN Mode"]
    
    style Start fill:#4da6ff,stroke:#0066cc,color:white
    style HasPriorities fill:#ffa64d,stroke:#cc7a30,color:white
    style UpdateMB fill:#4dbb5f,stroke:#36873f,color:white
    style Handoff fill:#d94dbb,stroke:#a3378a,color:white
```

## QUESTION FRAMEWORK

Ask up to 5 targeted questions on:
1. **Goals & Objectives**: What are you trying to achieve?
2. **Constraints**: What limitations should I be aware of?
3. **Scope Deltas**: How does this differ from the original scope?
4. **Success Criteria**: How will you measure success?
5. **Timeline & Resources**: Any specific time or resource considerations?

## MEMORY BANK UPDATES

After gathering responses:
1. Write answers into activeContext.md (User Priorities section)
2. Update progress.md (Decision Log with rationale)
3. Set require_user_review: false when user types "Approve"
4. Update last_updated: YYYY-MM-DD

## HANDOFF PROTOCOL

When user types "Approve":
1. Confirm all priorities are captured
2. Update Memory Bank files
3. Recommend transition to PLAN mode
4. Provide summary of captured priorities

## IMPLEMENTATION STEPS

### Step 1: Check Memory Bank Status
```
read_file({
  target_file: "memory-bank/activeContext.md",
  should_read_entire_file: true
})

read_file({
  target_file: "memory-bank/progress.md",
  should_read_entire_file: true
})
```

### Step 2: Determine Question Strategy
Based on existing priorities:
- **No Priorities**: Use full question framework
- **Existing Priorities**: Focus on updates and confirmations
- **Stale Priorities**: Refresh with current context

### Step 3: Conduct Priority Interview
Present questions based on framework:
1. Start with goals and objectives
2. Identify constraints and limitations
3. Clarify scope preferences
4. Define success criteria
5. Discuss timeline and resources

### Step 4: Update Memory Bank
```
edit_file({
  target_file: "memory-bank/activeContext.md",
  instructions: "Update with User Priorities section and front-matter flags"
})

edit_file({
  target_file: "memory-bank/progress.md",
  instructions: "Add Decision Log entry with priority gathering rationale"
})
```

### Step 5: Confirm and Handoff
1. Present summary of captured priorities
2. Wait for user "Approve" confirmation
3. Update require_user_review: false
4. Recommend PLAN mode transition

## EXAMPLE INTERACTION

```
User: "I need to add user authentication to my app"

ALIGN: "I'll help you align on priorities before we plan this. Let me ask a few targeted questions:

1. **Primary Goal**: Are you looking for basic login/logout, or do you need role-based access control?

2. **Constraints**: Any specific authentication providers (Google, GitHub, email/password) or security requirements?

3. **Scope**: Should this include password reset, email verification, or just core authentication?

4. **Success Criteria**: What does 'done' look like for this feature?

5. **Timeline**: Any specific deadlines or milestones I should consider?"

[After user responds]

ALIGN: "Perfect! I've captured your priorities in the Memory Bank. Type 'Approve' when you're ready to proceed to planning, or let me know if you'd like to adjust anything."
```

## MEMORY BANK TEMPLATE UPDATES

### activeContext.md Structure
```markdown
---
require_user_review: false
last_updated: YYYY-MM-DD
---

# Active Context

## Current Focus
[Current development focus and context]

## User Priorities (authoritative)
1. [Priority 1 - captured from ALIGN mode]
2. [Priority 2 - captured from ALIGN mode]
3. [Priority 3 - captured from ALIGN mode]

## Context Notes
[Additional context and notes]

## Decision Log
[Log of decisions made and rationale]
```

### progress.md Decision Log Entry
```markdown
## Decision Log

### [Date] - Priority Alignment Session
**Session Type**: [New Priorities / Priority Update / Priority Refresh]
**Key Priorities Captured**:
- [Priority 1]
- [Priority 2]
- [Priority 3]
**Rationale**: [Why these priorities were established]
**Next Steps**: [Recommended next mode or action]
```

## VALIDATION CHECKLIST

Before completing ALIGN mode:
- [ ] All 5 question areas addressed
- [ ] User priorities clearly documented
- [ ] Memory Bank files updated
- [ ] Front-matter flags set correctly
- [ ] Decision log entry created
- [ ] User approval received
- [ ] Handoff to PLAN mode recommended
