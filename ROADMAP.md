# Harness Template Roadmap

> Tracked next steps for expanding the harness library. Come back here to pick up where we left off.

---

## Phase 1 — Model Seeds (In Progress)

Seed harnesses for the most widely-used models using publicly known prompt architectures.

- [x] `harnesses/claude-code/` — seeded from Claude Code's layered context assembly
- [x] `harnesses/cursor/` — seeded from Cursor Agent's known prompt architecture
- [ ] `harnesses/gpt-4o/` — seed from ChatGPT/GPT-4o known patterns
- [ ] `harnesses/grok/` — seed from xAI Grok public persona + tool framing
- [ ] `harnesses/gemini/` — seed when sufficient public info is available
- [ ] `harnesses/copilot/` — seed from GitHub Copilot's leaked prompt (coding context)

---

## Phase 2 — Domain Forks

Fork this template into purpose-built harness repos for specific products and use cases.

### LashFit Harness
- **Repo**: `lashfit-harness` (fork of this template)
- **Type**: `customer-service` + `scheduling` + `medical`
- **Estimated prompts**: 50–60
- **Prompt categories to build**:
  - [ ] Client intake & consultation
  - [ ] Booking assistant
  - [ ] Aftercare advisor
  - [ ] Contraindication checker
  - [ ] Follow-up & retention sequences
  - [ ] Lash style recommender
  - [ ] Complaint & resolution handler
  - [ ] Staff training assistant
- **Tools needed**: calendar-tool, crm-lookup, image-analyzer
- **Webhooks**: booking-confirmed, appointment-reminder, follow-up-trigger

### Studio-OS Dev Harness
- **Repo**: `studio-os-dev-harness` (fork of this template)
- **Type**: `dev-assistant`
- **Purpose**: The harness used by the AI when building Studio-OS-Chat itself
- **Prompt categories to build**:
  - [ ] Spec writer
  - [ ] Component builder (React/Vite)
  - [ ] IndexedDB / storage layer assistant
  - [ ] GitHub push/read agent
  - [ ] Chat response formatter
  - [ ] Debug assistant
  - [ ] Commit message generator
- **Tools needed**: github_read, github_push, file_search, codebase_search
- **Skills needed**: studio-os-architecture.md, naming-conventions.md, type-system.md

---

## Phase 3 — Harness Registry

Build a browsable index of all harnesses across repos so they are discoverable and connectable.

- [ ] Create `studio-os-harness-registry` repo
- [ ] Define registry schema (harness card: name, type, model_target, repo_url, tags, version)
- [ ] Auto-index all `harness.index.json` files from known harness repos
- [ ] Build a simple browsable UI (static site or Studio-OS Library tab)
- [ ] Add connect/fork/download actions per harness

---

## Phase 4 — Studio-OS Integration

Connect the harness system directly into Studio-OS-Chat so harnesses can be loaded, switched, and customized in-app.

- [ ] Add `HarnessRecord` type to `types.ts`
- [ ] Add harness selector to chat settings panel
- [ ] Load active harness's system prompt as the session system prompt
- [ ] Inject active harness tools into the tool registry
- [ ] Show active harness name in chat header
- [ ] Allow per-session harness overrides
- [ ] Support loading a harness directly from a GitHub repo URL

---

## Phase 5 — Marketplace / Distribution

Package harnesses as sellable or shareable stacks.

- [ ] Define harness versioning and changelog conventions
- [ ] Add license field to `HARNESS.md` (MIT, commercial, private)
- [ ] Define harness pricing tiers (free, pro, enterprise)
- [ ] Build install flow: `fork → configure → connect → activate`
- [ ] Document how to sell a harness (what's included, what's customizable)

---

## Notes

- Every harness should be independently forkable and usable without Studio-OS
- The template is the contract — any harness that follows the schema is compatible
- Model-specific harnesses and task-specific harnesses can be combined at load time
- A single software product (e.g. a calendar app) may need 3–5 harnesses for different user contexts (work, personal, medical)
