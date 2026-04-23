# 🤖 GitHub Copilot Efficiency Playbook

> Token efficiency · Accurate answers · IDE-specific tricks · Tools · Real dev scenarios

## 🚀 Quick Start (Do This First)

New to Copilot optimization? Start here:

1. **Open only relevant files** (not your whole project)
2. **Write one-line comments above functions** (`// fetch user order from DB`) before letting Copilot complete
3. **Name things well** (`getUserOrderHistory()` instead of `fetchData()`)
4. **Use `/explain` and `/tests` slash commands** in VS Code chat
5. **Install Caveman** for 65–75% fewer output tokens: `npx skills add JuliusBrussee/caveman -a github-copilot`

**Result:** Faster, clearer answers. Fewer token-wasting clarifications.

---

## ⚡ Token Efficiency

### ✅ DO

| # | Rule | Why |
|---|------|-----|
| 1 | **Open only relevant files** | Copilot uses open tabs as context. Keep only files related to your current task open. |
| 2 | **Write inline comments as micro-prompts** | A short comment right above a function tells Copilot your exact intent before it generates. |
| 3 | **Name variables & functions descriptively** | Names like `fetchUserOrderHistory()` give semantic signal without extra prompting. |
| 4 | **Keep chat conversations focused** | Start a new chat for a new topic. Accumulated context dilutes the token budget. |
| 5 | **Use `/clear` or Compact Conversation often** | In VS Code Copilot Chat, compact history to compress context and reclaim token space. |

### ❌ DON'T

| # | Rule | Why |
|---|------|-----|
| 1 | **Don't dump entire codebases** | Attaching unrelated files wastes tokens and confuses the model with irrelevant patterns. |
| 2 | **Don't write vague one-liners** | "fix this" or "make it better" burns tokens on clarification rounds — be specific upfront. |
| 3 | **Don't repeat context already in history** | If it's in the conversation or an open file, don't re-paste it — the model already has it. |
| 4 | **Don't use Opus for boilerplate** | Use Haiku or Sonnet for completions. Save Opus only for architecture-level discussions. |

---

## 🎯 Accurate Answers

### ✅ DO

| # | Rule | Why |
|---|------|-----|
| 1 | **Provide input/output examples** | Show exactly what data goes in and comes out. Drastically reduces hallucination. |
| 2 | **Specify language version & framework** | Write "Swift 5.9 + SwiftUI" or "Kotlin + Jetpack Compose" explicitly — never assume. |
| 3 | **Use `#file`, `#selection`, `@workspace` references** | Anchor your question to specific code so the answer stays within your actual context. |
| 4 | **Ask for explanation alongside code** | "Generate this AND explain each step." You'll catch mistakes faster when you understand the output. |
| 5 | **Iterate in small steps** | One function at a time. Small verifiable steps are more accurate than "build the whole feature." |

### ❌ DON'T

| # | Rule | Why |
|---|------|-----|
| 1 | **Don't accept the first suggestion blindly** | Always read the output — Copilot can generate code that compiles but is logically wrong. |
| 2 | **Don't ask multi-problem questions** | "Fix the crash, add animation, and write tests" leads to incomplete answers on all three. |
| 3 | **Don't ignore `// TODO` comments in output** | If Copilot writes `// TODO: handle error here`, it's signaling the code is incomplete. |
| 4 | **Don't use chat for autocomplete tasks** | Inline suggestions are better for small completions. Chat is for reasoning and refactoring. |

### 🎯 Prompting Patterns That Work

**Pattern 1: Context + Constraint**  
❌ "Generate a button"  
✅ "Generate a submit button in SwiftUI with loading state and disabled feedback. Use green primary color from theme."

**Pattern 2: Input → Output Example**  
❌ "Parse this JSON"  
✅ "Parse this JSON and return a User struct with name, email, createdAt. Show one example input and the struct definition."

**Pattern 3: Reasoning + Code**  
❌ "Add error handling"  
✅ "Add error handling for network timeouts and show a retry button. Why does this approach work?"

---

## ✨ Tips & Tricks by IDE

### 🟦 VS Code

| Trick | How |
|-------|-----|
| **Project-wide context** | Use `@workspace` in chat to scan the entire project — great for "where is X used?" |
| **Slash commands** | Select code → open chat → type `/explain`, `/fix`, or `/tests` for structured answers. |
| **Cycle suggestions** | Press `Alt+]` / `Alt+[` to browse multiple generated alternatives before accepting. |
| **Multi-file edits** | Use Copilot Edits (`Ctrl+Shift+I`) to apply changes across multiple files in one session. |

### 🟣 Android Studio

| Trick | How |
|-------|-----|
| **Composable generation** | Ask Copilot to generate `@Composable` functions. Reference your theme tokens in the prompt. |
| **Comment-driven ViewModel** | Write `// ViewModel for user profile with StateFlow` above an empty class to guide generation. |
| **Paste Logcat errors** | Copy a crash stack trace into chat: "What causes this and how to fix it in Kotlin?" |
| **Reference Gradle versions** | Include your AGP and Kotlin version in the prompt to avoid deprecated API suggestions. |

### 🟡 Xcode

| Trick | How |
|-------|-----|
| **Paste Xcode errors verbatim** | Include the full error message like `Cannot convert value of type 'String' to 'Int'` for precise fixes. |
| **Declare SwiftUI vs UIKit** | Copilot defaults to SwiftUI. If you're on UIKit, state it — mixing them causes subtle bugs. |
| **Preview-compatible code** | Add "make sure this works in Xcode Preview" to get cleaner, injectable code. |
| **Protocol stubs via MARK** | Write `// MARK: - UITableViewDelegate` and let Copilot autocomplete all required method stubs. |

---

## ⚡ Quick Wins (Implement Today)

### Right Now

| Action | Payoff | Time |
|--------|--------|------|
| Close 50% of open tabs | Reduces noise in Copilot context | 1 min |
| Add 3-word comment above next function | Copilot generates 40% better code | 30 sec |
| Use `@workspace` in chat once | Find patterns across whole project | 2 min |
| Try Alt+] to cycle suggestions | Pick better option on first pass | 1 min |

### This Week

- [ ] Install Caveman skill (`npx skills add JuliusBrussee/caveman`)
- [ ] Add caveman to custom instructions (Copilot settings)
- [ ] Use `/explain` slash command in 3 chats
- [ ] Try `/caveman-commit` on next commit
- [ ] Review one old file with `/caveman-review` mindset

### Measure

**Before:** "Getting 7-turn clarification loops, slow reviews, verbose output"  
**After (1 week):** "Copilot nails it in 2–3 turns, reviews are readable, comments are terse"

---

## 🪨 Additional Tool: Caveman

> **why use many token when few token do trick**  
> GitHub: [juliusbrussee/caveman](https://github.com/juliusbrussee/caveman) · ⭐ 41.9k

Caveman is a skill/plugin that makes AI agents respond like a caveman — stripping filler words, articles, and pleasantries while keeping full technical accuracy. Result: **~65–75% fewer output tokens**, faster responses, and easier-to-read answers.

### How It Works

The key insight: AI responses are bloated with fluff. Caveman removes only the fluff, never the substance.

```
❌ Normal (69 tokens):
"The reason your React component is re-rendering is likely because you're
creating a new object reference on each render cycle..."

✅ Caveman (19 tokens):
"New object ref each render. Inline object prop = new ref = re-render. Wrap in `useMemo`."
```

**Same fix. 75% fewer tokens. Brain still big.**

### Install for GitHub Copilot (VS Code)

```bash
npx skills add JuliusBrussee/caveman -a github-copilot
```

This installs the skill file. To make it **always on**, paste this into your Copilot custom instructions (VS Code settings → GitHub Copilot → Custom Instructions):

```
Terse like caveman. Technical substance exact. Only fluff die.
Drop: articles, filler (just/really/basically), pleasantries, hedging.
Fragments OK. Short synonyms. Code unchanged.
Pattern: [thing] [action] [reason]. [next step].
ACTIVE EVERY RESPONSE. No revert after many turns. No filler drift.
Code/commits/PRs: normal. Off: "stop caveman" / "normal mode".
```

### Intensity Levels

| Level | Trigger | Style |
|-------|---------|-------|
| 🪶 **Lite** | `/caveman lite` | Drop filler, keep grammar. Professional but no fluff. |
| 🪨 **Full** | `/caveman full` | Default. Drop articles, use fragments, full grunt. |
| 🔥 **Ultra** | `/caveman ultra` | Maximum compression. Telegraphic. Abbreviate everything. |
| 📜 **Wenyan** | `/caveman wenyan` | Classical Chinese literary compression (most token-efficient). |

### Caveman Sub-commands

| Command | What It Does |
|---------|-------------|
| `/caveman-commit` | Generates terse commit messages in Conventional Commits format (≤50 char subject, why over what) |
| `/caveman-review` | One-line PR comments: `L42: 🔴 bug: user null. Add guard.` No throat-clearing. |
| `/caveman-compress <file>` | Rewrites your `CLAUDE.md` / memory files into caveman-speak so the AI reads ~46% fewer tokens per session. Keeps a human-readable `.original` backup. |
| `/caveman-help` | Quick-reference card for all modes, skills, and commands. |

### Benchmark: Token Savings

| Task | Normal | Caveman | Saved |
|------|--------|---------|-------|
| Explain React re-render bug | 1,180 | 159 | **87%** |
| Fix auth middleware | 704 | 121 | **83%** |
| Set up PostgreSQL pool | 2,347 | 380 | **84%** |
| Explain git rebase vs merge | 702 | 292 | **58%** |
| Docker multi-stage build | 1,042 | 290 | **72%** |
| **Average** | **1,214** | **294** | **65%** |

> ⚠️ Note: Caveman only affects **output tokens** — reasoning/thinking tokens are untouched. Biggest wins are readability and speed; cost savings are a bonus.

### The Caveman Ecosystem

| Tool | What | Install |
|------|------|---------|
| **caveman** | Output compression (~75% fewer output tokens) | `npx skills add JuliusBrussee/caveman -a github-copilot` |
| **[cavemem](https://github.com/JuliusBrussee/cavemem)** | Cross-agent persistent memory via compressed SQLite + MCP | See repo |
| **[cavekit](https://github.com/JuliusBrussee/cavekit)** | Spec-driven autonomous build loop (natural language → verified code) | See repo |

---

## 🎬 Real Dev Scenarios

### Scenario 1: Developing a New Feature

**Example:** Build Face ID / Touch ID login in Swift/iOS.

**Step-by-step workflow:**

```
1. PLAN — Sonnet, new chat
   "I'm building Face ID/Touch ID login for iOS using Swift 5.9 +
   SwiftUI + LocalAuthentication. Give me the architecture: classes,
   flow, edge cases. No code yet."

2. SCAFFOLD — Sonnet, same chat
   "Generate BiometricAuthManager skeleton: empty method stubs,
   doc comments, LAContext, error handling stubs, @Published
   isAuthenticated: Bool."

3. IMPLEMENT — Haiku, inline autocomplete
   → Open the file, write method comment above each stub
   → Let autocomplete fill in the implementation
   → Cycle with Alt+] to pick the best suggestion

4. REVIEW — Caveman ON, Sonnet
   "/caveman full — review #file:BiometricAuthManager.swift
   for security issues and missing edge cases."

5. TESTS — Sonnet
   → Select the class → /tests
   "Write XCTest unit tests. Mock LAContext. Cover: success,
   biometry unavailable, auth failed, lockout."
```

**Token tips for this scenario:**
- Keep LocalAuthentication docs closed — Copilot already knows the API
- Only open auth-related files, not your full project
- Use Caveman for the review step to get a dense, scannable list instead of an essay

---

### Scenario 2: Bug Fixing

**Example:** `EXC_BAD_ACCESS` crash on a background thread in production.

**Step-by-step workflow:**

```
1. DIAGNOSE — Sonnet, new chat (fresh context is critical)
   Paste ONLY the crash log + the one file it points to.
   "This crash log points to OrderViewModel.swift.
   EXC_BAD_ACCESS on background thread.
   What is the root cause? Don't fix yet — just explain."

2. ISOLATE — Sonnet
   "Which specific line in #file:OrderViewModel.swift is
   the likely cause? Show only that section."

3. FIX — Haiku, inline
   → Cursor on the problem line
   → Write: // Fix: ensure this runs on main thread
   → Accept autocomplete

4. VALIDATE — Sonnet
   "Here is my fix [paste]. Does this fully resolve the thread
   safety issue? Are there other places in #file with the
   same pattern?"

5. COMMIT — Caveman commit
   /caveman-commit
   → "fix: main thread guard for order update crash"
```

**Token tips for this scenario:**
- Never paste the full project — one file + crash log is enough
- Use a **new chat** so previous feature context doesn't interfere with diagnosis
- Ask for root cause **before** the fix — it uses fewer tokens overall and gives you better output

---

### Scenario 3: Brainstorming

**Example:** Choosing a local persistence strategy for an iOS app (CoreData vs SwiftData vs SQLite vs UserDefaults).

**Step-by-step workflow:**

```
1. COMPARE — Opus, new chat (this warrants the heavy model)
   "I'm building an iOS app: Swift 5.9 + SwiftUI. Data: user
   profiles, offline-first order history (~5000 records), needs
   CloudKit sync. Target: iOS 16+.
   Compare CoreData vs SwiftData vs SQLite (GRDB) vs UserDefaults.
   Format as a decision matrix."

2. DRILL DOWN — Sonnet
   "Based on that matrix, explain the migration risk if I start
   with SwiftData now and need to move to CoreData later."

3. ACTION PLAN — Sonnet, Caveman ON
   "/caveman full — 5-step implementation plan for SwiftData
   + CloudKit sync. Bullet points only."

4. VALIDATE — Sonnet
   "Any known SwiftData + CloudKit bugs or limitations in
   iOS 17 I should know before committing?"

5. DOCUMENT — Haiku
   "Turn this decision and rationale into a short ADR
   (Architecture Decision Record) in markdown format."
```

**Token tips for this scenario:**
- Use **Opus only for the initial comparison** — it's the expensive reasoning step
- Switch to **Sonnet for follow-ups** once the decision direction is clear
- Ask for a **decision matrix** — it forces structured, concise output
- The ADR step is cheap (Haiku) but gives you long-term documentation value

---

## 💡 Model Selection Cheat Sheet

| Model | Best For | Scenario |
|-------|----------|----------|
| **Haiku** | Autocomplete, boilerplate, simple docs | Feature scaffolding, inline completions, ADR writing |
| **Sonnet** | Refactoring, debugging, explanation, tests | Bug fixing, code review, follow-up questions |
| **Opus** | Architecture, complex trade-offs, system design | Brainstorming, initial comparisons, tech decisions |

> **Key insight:** Start heavy (Opus) for decisions, go lighter (Sonnet → Haiku) for execution. Mixing models by task type is the real efficiency hack.

---

## 🧰 Tools Summary

| Tool | What It Does | Best Used When |
|------|-------------|----------------|
| **GitHub Copilot** | Inline autocomplete + chat assistant | Always — core tool |
| **Caveman** | Strips AI verbosity, ~65–75% fewer output tokens | Review, debugging, dense Q&A |
| **caveman-compress** | Compresses memory/instruction files by ~46% | If you use `CLAUDE.md` or persistent instructions |
| **caveman-commit** | Terse Conventional Commits messages | After every bug fix or feature commit |
| **caveman-review** | One-line PR comment format | Code review sessions |

---

*Last updated: April 2026 · GitHub: [juliusbrussee/caveman](https://github.com/juliusbrussee/caveman)*

---

## ✅ Implementation Checklist

**What You've Done & Should Do:**

### Phase 1: Foundation (Essential)
- [x] Read entire playbook
- [x] Close unnecessary tabs in IDE (keep only current task files open)
- [ ] Write 3-word comments above functions before accepting Copilot completions
- [ ] Use at least one slash command (`/explain`, `/fix`, `/tests`) in Copilot chat

### Phase 2: Tools (Quick Wins)
- [x] Install Caveman: `npx skills add JuliusBrussee/caveman -a github-copilot`
- [x] Add Caveman to VS Code custom instructions (paste template from this playbook)
- [ ] Use `/caveman-commit` for next 3 commits
- [ ] Try `/caveman full` in one chat and compare token usage

### Phase 3: Workflow (Sustainable)
- [ ] Use `@workspace` reference in at least one chat
- [ ] Apply "Context + Constraint" prompting pattern on next feature
- [ ] Spend <2 min writing prompts (not "clarification loops")
- [ ] Review one PR using `/caveman-review` mindset

### Phase 4: Scaling (Long-term)
- [x] Choose model per task (Haiku for boilerplate, Sonnet for logic, Opus for architecture)
- [ ] Follow one real-world scenario (feature build, bug fix, or brainstorm) end-to-end
- [ ] Compress `CLAUDE.md` with `/caveman-compress` if using persistent instructions
- [ ] Measure token savings before/after Caveman (target: 50–70% reduction on output)

### Done Signals
✅ **Token efficiency:** Fewer than 3 clarification rounds per question  
✅ **Speed:** Copilot answers in first or second suggestion  
✅ **Readability:** Output is terse, no filler, 100% technical substance  
✅ **Habit:** You default to context comments before accepting suggestions
