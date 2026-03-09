# 🤖 RepoSwarm

**Give your AI agents the architecture context they need — across hundreds of repositories.**

RepoSwarm is an AI-powered platform that automatically analyzes your entire codebase portfolio and generates standardized `.arch.md` architecture documents. Feed them to your coding agents, use them for onboarding, or keep them as living architecture docs. Works with GitHub, CodeCommit, GitLab, Azure DevOps, and Bitbucket.

```bash
curl -fsSL https://raw.githubusercontent.com/reposwarm/reposwarm-cli/main/install.sh | sh
reposwarm new --local && reposwarm investigate my-app
```

🎬 [**Watch the demo →**](https://www.youtube.com/watch?v=rOMf9xvpgtc) · 📋 [**Sample output →**](https://github.com/royosherove/repo-swarm-sample-results-hub)

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

Point RepoSwarm at your repos. It clones, detects the repo type (backend, frontend, mobile, infra, library), picks specialized analysis prompts, and sends the codebase to an LLM for deep architecture analysis. The output — clean, structured `.arch.md` files — gets committed to a results hub repo that your agents can reference.

Investigations run as Temporal workflows with automatic retries, incremental updates (only re-analyzes repos with new commits), and parallel execution across your entire portfolio. Supports Anthropic, Amazon Bedrock, and LiteLLM as providers.

All Docker images are multi-arch (`linux/amd64` + `linux/arm64`) and published automatically on every push to `main`.
