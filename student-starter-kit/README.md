# Student Starter Kit — Future-Proof AI Automation

> Everything you need to set up a production-grade AI development environment.

---

## What's Inside

```
student-starter-kit/
├── skills/              # 15 reusable automation skills
├── agents/              # 10 specialized AI agent definitions
├── coding-rules/        # 15 engineering rules + 9 doc templates
│   ├── rules/           # Production coding standards
│   ├── docs/            # Project documentation templates
│   └── claude/          # CLAUDE.md + compose script
└── README.md            # You are here
```

---

## Quick Setup (5 minutes)

### 1. Install Claude Code

```bash
npm install -g @anthropic-ai/claude-code
```

### 2. Copy Skills to Your Project

```bash
# Copy all skills into your project
cp -r skills/ your-project/.claude/skills/

# Or copy specific skills
cp -r skills/video-edit your-project/.claude/skills/
```

### 3. Copy Agents (Global — works across all projects)

```bash
# Copy agents to your global Claude config
mkdir -p ~/.claude/agents
cp agents/*.md ~/.claude/agents/
```

### 4. Set Up Coding Rules for a Project

```bash
# Option A: Copy all rules into your project's CLAUDE.md
cd coding-rules/claude
chmod +x compose.sh

# Pick only the rules you need (by number):
./compose.sh 00 10 30 70 80 99 > ~/your-project/CLAUDE.md

# Option B: Copy everything
cat rules/*.md > ~/your-project/CLAUDE.md
```

### 5. Use Doc Templates When Starting Projects

```bash
# Copy templates you need into your project's docs/ folder
cp coding-rules/docs/PRD.md your-project/docs/
cp coding-rules/docs/ARCHITECTURE.md your-project/docs/
cp coding-rules/docs/API_SPEC.md your-project/docs/
```

---

## Skills Reference (15)

### Content & Video
| Skill | What It Does |
|-------|-------------|
| `video-edit` | Video editing — silence removal, captions, crop, compression (FFmpeg + Whisper) |
| `image-to-video` | Animate images with 11+ AI models (Kling, Hailuo, Luma, Runway, Veo, etc.) |
| `nano-banana-images` | Hyper-realistic AI image generation via fal.ai |
| `handdrawn-diagram` | Hand-drawn whiteboard infographic prompts for Gemini |
| `excalidraw-diagram` | Editable Excalidraw JSON diagrams |
| `excalidraw-visuals` | Hand-drawn PNG visuals via fal.ai |
| `gamma-presentation` | AI slides, docs, webpages via Gamma MCP |

### Infrastructure & Automation
| Skill | What It Does |
|-------|-------------|
| `modal-deploy` | Cloud deployment on Modal |
| `add-webhook` | Modal webhook creation for event-driven workflows |
| `local-server` | Local FastAPI + Cloudflare tunnel server |
| `design-website` | Website design automation with mockups |

### Browser & Voice
| Skill | What It Does |
|-------|-------------|
| `ghost-browser` | Browser automation — LinkedIn, web scraping, human-like interaction |
| `whisper-voice` | Local speech-to-text Mac app (WhisperKit, fully offline) |

### Security & Meta
| Skill | What It Does |
|-------|-------------|
| `guardrail-pipeline` | 6-layer AI safety pipeline (RBAC, injection defense, output filtering) |
| `skill-builder` | Build your own skills (meta-skill) |

---

## Agents Reference (10)

These are specialized AI agents that Claude Code can spawn for specific tasks.

| Agent | Model | Specialization |
|-------|-------|---------------|
| `backend-builder` | Opus | FastAPI, Python, PostgreSQL backend APIs |
| `frontend-builder` | Sonnet | Next.js, React, Tailwind UI components |
| `code-reviewer` | Opus | Bug/security review with PASS/FAIL verdict |
| `test-runner` | Sonnet | Run tests, write missing tests, validate quality |
| `deployer` | Sonnet | Vercel, AWS, Docker, CI/CD deployment |
| `db-architect` | Sonnet | Schema design, migrations, RLS, pgvector |
| `mcp-builder` | Sonnet | Build MCP servers for any API/service |
| `api-integrator` | Sonnet | OAuth, webhooks, REST/GraphQL integrations |
| `security-auditor` | Opus | OWASP Top 10, secrets, prompt injection audit |
| `researcher` | Sonnet | Codebase exploration and technical investigation |

**Usage in Claude Code:**
```
> Use the backend-builder agent to create a FastAPI CRUD API
> Use the code-reviewer agent to review my changes
> Use the test-runner agent to run all tests
```

---

## Coding Rules Reference (15)

Production-grade engineering standards. Pick what you need.

| # | Rule | What It Enforces |
|---|------|-----------------|
| 00 | Global Architect | Clean architecture, separation of concerns |
| 10 | Backend FastAPI | Thin routes, services for logic, repositories for DB |
| 20 | Frontend Next.js | TypeScript, small components, centralized API clients |
| 30 | Database PostgreSQL | Migrations, indexes, foreign keys, no raw SQL in routes |
| 35 | API Contracts | Version APIs, typed schemas, consistent error format |
| 40 | Cache Redis | Intentional TTLs, stable keys, wrapped access |
| 45 | Environment Config | Validate at startup, .env.example, secret managers |
| 50 | RAG System | Separate ingestion from generation, chunk metadata |
| 55 | Data & Model Versioning | Version datasets, named checkpoints, reproducibility |
| 60 | Agents | Tool schemas, validated outputs, supervisor patterns |
| 70 | Security | No hardcoded secrets, prompt injection resistance |
| 80 | Testing & Quality | Tests for critical paths, deterministic units, linting |
| 85 | Error & Observability | Structured errors, request tracing, health checks |
| 90 | DevOps & Deployment | Docker, AWS, Vercel, VPS, CI/CD |
| 99 | Response Style | Minimal changes, production code, no toy implementations |

### Compose Script — Pick Only What You Need

```bash
cd coding-rules/claude
./compose.sh 00 10 30 70 80 99 > ~/my-project/CLAUDE.md
```

This creates a CLAUDE.md with only rules 00, 10, 30, 70, 80, and 99.

---

## Doc Templates (9)

Ready-to-fill templates for professional project documentation.

| Template | Purpose |
|----------|---------|
| `PRD.md` | Product Requirements Document |
| `ARCHITECTURE.md` | System architecture design |
| `API_SPEC.md` | API endpoint specification |
| `DB_SCHEMA.md` | Database schema design |
| `DEPLOYMENT.md` | Deployment and infrastructure guide |
| `SKILLS.md` | Skills documentation template |
| `AGENTS.md` | Agent definitions template |
| `LOADOUT.md` | Project manifest/loadout |
| `MCP.md` | MCP server documentation |

---

## Recommended Stack for Bootcamp Projects

```
Frontend:    Next.js + React + Tailwind CSS
Backend:     FastAPI (Python) or Next.js API Routes
Database:    Supabase (PostgreSQL + Auth + Storage)
AI:          Claude API / OpenAI API / Gemini API
Deployment:  Vercel (frontend) + Modal (backend) / AWS
Automation:  n8n (workflows) + MCP (AI tool connections)
Editor:      Cursor / VS Code + Claude Code CLI
```

---

## How Skills Work

Each skill has a `SKILL.md` file that tells Claude Code exactly how to perform a task. When you say:

```
> Use the video-edit skill to add captions to my video
```

Claude reads the SKILL.md, follows the instructions, and executes the automation.

**To build your own skill:**
```
> Use the skill-builder skill to create a new skill called "my-automation"
```

---

## Need Help?

- Claude Code docs: `claude --help`
- Skills: Read any `SKILL.md` inside `skills/`
- Rules: Read any rule in `coding-rules/rules/`
