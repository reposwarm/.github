# 🤖 RepoSwarm

**AI-powered multi-repo architecture discovery platform**

RepoSwarm automatically analyzes your entire codebase portfolio and generates standardized architecture documentation. Point it at your GitHub repos (or CodeCommit, GitLab, Azure DevOps, Bitbucket) and get back clean, structured `.arch.md` files — perfect as AI agent context, onboarding docs, or architecture reviews.

```bash
curl -fsSL https://raw.githubusercontent.com/reposwarm/reposwarm-cli/main/install.sh | sh
reposwarm new --local && reposwarm investigate my-app
```

🎬 [**Watch the demo →**](https://www.youtube.com/watch?v=rOMf9xvpgtc)

---

## Repositories

| Repo | What it does |
|------|-------------|
| [**reposwarm**](https://github.com/reposwarm/reposwarm) | Core engine — Temporal workflows + AI analysis worker |
| [**reposwarm-cli**](https://github.com/reposwarm/reposwarm-cli) | CLI — setup, investigate, diagnose, view results. Single binary, zero deps |
| [**reposwarm-api**](https://github.com/reposwarm/reposwarm-api) | REST API server for repos, workflows, prompts, and wiki |
| [**reposwarm-ui**](https://github.com/reposwarm/reposwarm-ui) | Next.js dashboard for browsing investigations and results |
| [**reposwarm-askbox**](https://github.com/reposwarm/reposwarm-askbox) | AI agent for querying architecture docs via natural language |
| [**ask-cli**](https://github.com/reposwarm/ask-cli) | CLI for querying architecture docs — the read side of RepoSwarm |
| [**e2e-arch-hub**](https://github.com/reposwarm/e2e-arch-hub) | E2E test architecture hub (generated `.arch.md` output) |

## How It Works

**Cache check → Clone → Type detection → Structure analysis → Prompt selection → AI analysis → Store results → Cleanup**

RepoSwarm uses specialized prompts for different repo types (backend, frontend, mobile, infra, libraries) and supports multiple LLM providers (Anthropic, Amazon Bedrock, LiteLLM). Investigations run as Temporal workflows with automatic retries and incremental updates.

All Docker images are multi-arch (`linux/amd64` + `linux/arm64`) and published automatically on every push to `main`.
