---
name: wanwu-chengpian
description: "Create or improve AI prompts for coding, writing, analysis and creative tasks. For video prompts, plan precise target timelines, varied purposeful shots, natural dialogue and layered realistic sound. Use when the user asks to write, structure or optimize a prompt."
metadata:
  category: automation
  risk: safe
  source: community
  tags: "[wanwu-chengpianing, optimization, frameworks, ai-enhancement, video-prompts]"
  date_added: "2026-02-27"
  version: "1.1.0"
---

## Purpose

This skill transforms raw, unstructured user prompts into highly optimized prompts using established prompting frameworks. It analyzes user intent, identifies task complexity, and intelligently selects the most appropriate framework(s) to improve clarity. Output quality depends on the model and task and requires evaluation.

The skill operates in "magic mode" - it works silently behind the scenes, only interacting with users when clarification is critically needed. Users receive polished, ready-to-use prompts without technical explanations or framework jargon.

This is a **universal skill** that works in any terminal context, not limited to Obsidian vaults or specific project structures.

## Video Prompt Route

When writing or revising a video-generation prompt, video script or shot timeline, read [视频时间轴、镜头与声音规范](references/video-prompts.md) before drafting. Use that reference for video-specific decisions; retain the general framework workflow for other tasks.

Carry forward the user's relevant approved prompts and corrections when available. Preserve explicit duration, framing, language, exact dialogue and reference-image roles. In video work, speed comes from editing and performance beats while speech remains clear and natural. Deliver prompts only unless the user also asks to generate media.

## When to Use
Invoke this skill when:

- User provides a vague or generic prompt (e.g., "help me code Python")
- User has a complex idea but struggles to articulate it clearly
- User's prompt lacks structure, context, or specific requirements
- Task requires step-by-step reasoning (debugging, analysis, design)
- User needs a prompt for a specific AI task but doesn't know prompting frameworks
- User wants to improve an existing prompt's effectiveness
- User wants a video prompt with precise timing, richer shots, natural dialogue or realistic sound
- User asks variations of "how do I ask AI to..." or "create a prompt for..."

## Workflow

### Step 1: Analyze Intent

**Objective:** Understand what the user truly wants to accomplish.

**Actions:**
1. Read the raw prompt provided by the user
2. Detect task characteristics:
   - **Type:** coding, writing, analysis, design, learning, planning, decision-making, creative, video, etc.
   - **Complexity:** simple (one-step), moderate (multi-step), complex (requires reasoning/design)
   - **Clarity:** clear intention vs. ambiguous/vague
   - **Domain:** technical, business, creative, academic, personal, etc.
3. Identify implicit requirements:
   - Does user need examples?
   - Is output format specified?
   - Are there constraints (time, resources, scope)?
   - Is this exploratory or execution-focused?

**Detection Patterns:**
- **Simple tasks:** Short prompts, single verb, no context (weak hints, not reliable complexity tests)
- **Complex tasks:** Multiple requirements and conditional logic; length alone does not establish complexity
- **Ambiguous tasks:** Generic verbs ("help", "improve"), missing object/context
- **Structured tasks:** Mentions steps, phases, deliverables, stakeholders


### Step 2: Ask Clarifying Questions (Conditional)

**Objective:** Gather missing information only when it is critical to framework selection or prompt quality.

**Trigger Conditions** — ask only if:
- Task type is completely ambiguous (cannot determine coding vs. writing vs. analysis)
- Target audience is unknown and materially affects the output
- Scope is undefined and choosing wrong scope would invalidate the prompt
- Requested output format conflicts or is missing and cannot be inferred

**Question Limits:**
- Maximum 3 questions per invocation
- Combine related questions into one when possible
- If enough context exists, skip this step entirely (most cases)

**Example Clarifying Exchange:**

```
User: "help me with AI"

Step 2 (triggered — task type ambiguous):
"To craft the best prompt, I need one quick clarification:
1. What do you want to do with AI — build something, learn about it, or use an AI tool for a task?"
```

**Critical Rule:** When in doubt, skip clarification and generate the best prompt with available context. Over-asking breaks the "magic mode" experience.


### Step 3: Select Framework(s)

**Objective:** Map task characteristics to optimal prompting framework(s).

**Framework Mapping Logic:**

| Task Type | Recommended Framework(s) | Rationale |
|-----------|-------------------------|-----------|
| **Role-based tasks** (act as expert, consultant) | **RTF** (Role-Task-Format) | Clear role definition + task + output format |
| **Step-by-step reasoning** (debugging, proof, logic) | **Chain of Thought** | Encourages explicit reasoning steps |
| **Structured projects** (multi-phase, deliverables) | **RISEN** (Role, Instructions, Steps, End goal, Narrowing) | Comprehensive structure for complex work |
| **Complex design/analysis** (systems, architecture) | **RODES** (Role, Objective, Details, Examples, Sense check) | Balances detail with validation |
| **Summarization** (compress, synthesize) | **Chain of Density** | Iterative refinement to essential info |
| **Communication** (reports, presentations, storytelling) | **RACE** (Role, Audience, Context, Expectation) | Audience-aware messaging |
| **Investigation/analysis** (research, diagnosis) | **RISE** (Research, Investigate, Synthesize, Evaluate) | Systematic analytical approach |
| **Contextual situations** (problem-solving with background) | **STAR** (Situation, Task, Action, Result) | Context-rich problem framing |
| **Documentation** (medical, technical, records) | **SOAP** (Subjective, Objective, Assessment, Plan) | Structured information capture; clinical assessment requires a qualified clinician and verified inputs |
| **Goal-setting** (OKRs, objectives, targets) | **CLEAR** (Collaborative, Limited, Emotional, Appreciable, Refinable) | Goal clarity and actionability |
| **Coaching/development** (mentoring, growth) | **GROW** (Goal, Reality, Options, Will) | Developmental conversation structure |

**Blending Strategy:**
- **Combine 2-3 frameworks** when task spans multiple types
- Example: Complex technical project → **RODES + Chain of Thought** (structure + reasoning)
- Example: Leadership decision → **CLEAR + GROW** (goal clarity + development)

**Selection Criteria:**
- Primary framework = best match to core task type
- Secondary framework(s) = address additional complexity dimensions
- Avoid over-engineering: simple tasks get simple frameworks

**Critical Rule:** This selection happens **silently** - explain framework choice when the user requests it.

```
Role: You are a senior software architect. [RTF - Role]

Objective: Design a microservices architecture for [system]. [RODES - Objective]

Approach this step-by-step: [Chain of Thought]
1. Analyze current monolithic constraints
2. Identify service boundaries
3. Design inter-service communication
4. Plan data consistency strategy

Details: [RODES - Details]
- Expected traffic: [X]
- Data volume: [Y]
- Team size: [Z]

Output Format: [RTF - Format]
Provide architecture diagram description, service definitions, and migration roadmap.

Sense Check: [RODES - Sense check]
Validate that services are loosely coupled, independently deployable, and aligned with business domains.
```

### Step 4: Compose and Check the Prompt

Preserve the user's intended task and constraints. Use the selected framework as a drafting aid, with concise findings or a decision rationale where useful rather than requests for private internal reasoning. For video, apply the linked video reference, reconcile shot and dialogue timings, and include the needed reference-material roles in the copy-ready prompt. Treat plausible timing estimates as planning estimates until actual audio or footage has been checked.

**4.5. Language Adaptation**
- If original prompt is in Portuguese, generate prompt in Portuguese
- If original prompt is in English, generate prompt in English
- If mixed, follow the user's requested instruction language and preserve quoted content in its intended language. A Chinese video prompt can contain exact English dialogue; do not translate that dialogue or switch the whole prompt to English merely because it contains English product text.

**4.6. Quality Checks**
Before finalizing, verify:
- [ ] Prompt is self-contained: restate required context and identify any reference files the user must attach; do not pretend those files are already bound
- [ ] Task is specific and measurable
- [ ] Output format is clear
- [ ] No ambiguous language
- [ ] Appropriate level of detail for task complexity


## Critical Rules

### **NEVER:**

- ❌ Invent facts, product claims or tool capabilities; ask only when a critical missing fact cannot be inferred, and label optional creative assumptions
- ❌ Hide framework selection when the user asks for an explanation
- ❌ Generate generic, one-size-fits-all prompts - always customize to context
- ❌ Use technical jargon in the final prompt (unless user's domain is technical)
- ❌ Ask more than 3 clarifying questions (avoid user fatigue)
- ❌ Include meta-commentary in the output ("This prompt uses...", "Note that...")
- ❌ Present output without code block formatting
- ❌ Translate exact dialogue or product lettering without instruction; keep instruction language and dialogue language intentional

### **ALWAYS:**

- ✅ Analyze intent before generating (Step 1 is mandatory)
- ✅ Ask clarifying questions if critical information is ambiguous (Step 2 conditional)
- ✅ Select framework(s) based on task type and complexity (Step 3 mapping)
- ✅ Blend multiple frameworks when it improves prompt quality
- ✅ Adapt prompt length to original input complexity (simple → short, complex → detailed)
- ✅ Include output format specification in generated prompts
- ✅ Present final prompt in clean Markdown code block
- ✅ Make prompts self-contained, explicitly identifying required image or file references when the task depends on them
- ✅ Use examples in complex prompts to illustrate expected output
- ✅ Validate prompt completeness before presenting (quality checks in Step 4.6)


### **Example 2: Complex Clear Prompt → RODES + Chain of Thought (No Clarification)**

**User Input:**
```
copilot> create prompt for: I need to build a product recommendation system considering purchase history, user preferences, and market trends
```

**Skill Internal Process:**
1. **Analyze:** Clear intent, complex task (ML system design), technical domain
2. **Clarify:** Skip (sufficient information)
3. **Select:** RODES (complex design) + Chain of Thought (reasoning needed)

**Skill Output:**

````markdown
```
Role: You are a senior machine learning engineer specializing in recommendation systems.

Objective: Design a product recommendation system that combines user purchase history, preferences, and market trends.

Details:
- Input data sources: [confirm available purchase, preference and market-trend data; do not assume surveys or API access]
- Algorithm considerations: collaborative filtering, content-based filtering, hybrid approaches
- Performance metrics: precision, recall, diversity, novelty
- Scalability: [confirmed user scale, or mark unknown]
- Latency constraints: [confirmed requirement, or mark unknown]

Approach step-by-step:
1. Analyze the three data sources and their relationships
2. Propose 2-3 algorithm approaches with trade-offs analysis
3. Design data pipeline architecture (ingestion, processing, serving)
4. Define evaluation metrics and A/B testing strategy
5. Outline implementation roadmap with phases

Examples:
- Show pseudocode for core recommendation logic
- Illustrate data flow diagram
- Provide sample API response structure

Sense Check: Validate that the proposed solution balances personalization with discovery, scales to production load, and incorporates real-time market trends effectively.

Output format: Technical design document with architecture diagrams, algorithm justification, and implementation roadmap.
```
````


### **Example 4: Code Debugging → Chain of Thought**

**User Input:**
```
copilot> optimize prompt: my Python code isn't working, needs debugging
```

**Skill Internal Process:**
1. **Analyze:** Debugging task, needs step-by-step reasoning
2. **Clarify:** Skip (user will provide code context later)
3. **Select:** Chain of Thought

**Skill Output:**

````markdown
```
You are an expert Python debugger.

Task: Debug the Python code provided by the user by analyzing it step-by-step.

Debugging approach:
1. Read and understand the code's intended purpose
2. Identify the error or unexpected behavior
3. Trace variable states at each execution step
4. Locate the root cause of the issue
5. Propose fix with explanation
6. Suggest preventive measures to avoid similar bugs

Provide concise findings, evidence and a decision rationale rather than private internal reasoning traces:
- What you're checking
- What you found
- Why it matters

Output format:
- **Issue identified:** [Describe the bug]
- **Root cause:** [Why it's happening]
- **Fix:** [Corrected code with comments]
- **Prevention:** [Best practices to avoid this in the future]

Include a working example to verify the fix.
```
````


## Notes

This skill is **platform-agnostic** and works in any terminal context where GitHub Copilot CLI is available. It does not depend on:
- Obsidian vault structure
- Specific project configurations
- A particular external template or project layout

General prompt optimization uses the guidance here. Video optimization also uses the bundled video reference; user-supplied images and files remain inputs, with their roles stated explicitly.

## Limitations
- Use this skill only when the task clearly matches the scope described above.
- Do not treat the output as a substitute for environment-specific validation, testing, or expert review.
- Stop and ask for clarification if required inputs, permissions, safety boundaries, or success criteria are missing.
