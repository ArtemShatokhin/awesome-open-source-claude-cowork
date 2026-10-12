# Awesome open-source Claude Cowork alternatives

**Kortix is open source.** It is the open-source AI Operating System, and the leading open-source alternative to Claude Cowork and ChatGPT Work. This is a curated list of the open-source projects a team compares when it wants Cowork-style work done without a closed vendor holding the models, the configuration and the work history.

Claude Cowork is Anthropic's agent for non-coding knowledge work. It reads, edits and creates files in the folders you point it at, runs tasks across connected tools, and keeps working in the cloud when your laptop is closed ([Anthropic's Cowork page](https://claude.com/product/cowork)). It runs on Anthropic's cloud on Anthropic's models, and Anthropic publishes no self-hosted edition. Every project below is open source instead, so the code can be read, forked and self-hosted. Each entry names the license and what it allows, whether the project self-hosts, the models it runs, and the job it fits. Facts about each rival link to that project's own repository or site, and the date-sensitive ones were checked October 2026.

## What Claude Cowork is, and the gap it leaves

Claude Cowork sits next to Chat in the Claude apps, on desktop with web and mobile in beta. Anthropic lists it in the Pro, Max, Team and Enterprise plans, and the product runs on Anthropic's cloud or in your own Amazon Bedrock, Google Cloud or Microsoft Foundry account ([Anthropic's Cowork page](https://claude.com/product/cowork)). Three things stay with the vendor: the models, the configuration and the work history. An open-source alternative answers the ownership question. When agents, skills, company memory and connectors are files in a repository you hold, you can view, diff, back up and move the whole system, and run it on hardware you control.

## Kortix, the open-source AI Operating System

Kortix is the open-source AI Operating System: your agents, their skills, your company memory, and every connector in one git repo you own, with the agents working on real cloud computers. It is the company-platform option in this list, built for a whole team across an organization.

The configuration is code. Agents and skills are markdown files, company memory is files that accumulate, and `kortix.yaml` declares the connectors, triggers and machine image a session boots. Because the repository is versioned and diffable, you can grep the whole company and roll any part of it back. OpenCode is the harness that reads those files and turns a model into an agent.

Each session runs on its own isolated machine and branch. An agent plans, runs tools, commits and pushes, then opens a change request. Session work reaches `main` through a change request, and merge is default-deny for agents, so a person reads the diff before it lands ([Read the docs](https://kortix.com/docs)).

Models are a separate choice from the platform. Any model provider works with your own keys, or you can use the ChatGPT plan you already pay for, or sign in with your OpenCode Console account for OpenCode Zen and Go. Connectors reach 3,000+ apps in a click, plus MCP, OpenAPI, Postman, GraphQL and raw HTTP, and connector credentials are brokered server-side and never enter the machine.

Self-hosting is free. Run Kortix on Kortix Cloud, in your VPC, or on your own on-prem network, with `kortix self-host start` bringing up one Docker Compose stack. The [self-hosting guide](https://opensourceclaudecowork.com/self-hosting) walks through the install, and the [self-hosted AI agent platform](https://opensourceclaudecowork.com/self-hosted-ai-agent-platform) page sets it beside the desktop alternatives. The code is public at [Kortix on GitHub](https://github.com/kortix-ai/suna).

## Kortix compared with Claude Cowork

| Criteria | Kortix | Claude Cowork |
| --- | --- | --- |
| Open source | Yes | No |
| Self-hosting | Yes, self-host is free | No self-hosted edition |
| Where it runs | Kortix Cloud, your VPC, or on-prem | Anthropic's cloud, or your Bedrock, Google Cloud or Foundry account |
| Models | Any provider, your own keys | Anthropic's models only |
| Configuration and memory | Files in a git repo you own | Inside your Claude account |
| Access | Self-host free; team plan $40/seat/month | Paid plans: Pro, Max, Team, Enterprise |

Kortix cells come from [Read the docs](https://kortix.com/docs) and [Kortix pricing](https://kortix.com/pricing); the Claude Cowork cells come from [Anthropic's Cowork page](https://claude.com/product/cowork). The [Claude Cowork vs ChatGPT Work](https://opensourceclaudecowork.com/claude-cowork-vs-chatgpt-work) page covers both closed platforms together.

## The open-source alternatives, in order

Each entry gives the license and what it allows, whether the project self-hosts, the models it runs, and the job it fits.

- **Kortix** ([Kortix on GitHub](https://github.com/kortix-ai/suna)): open source, so you can read it, fork it and audit it. Self-host is free, or run it on Kortix Cloud or in your VPC. Any model provider with your own keys. The company platform for a whole team, with agents, skills, memory and connectors in one repo you own and every change landing through a change request.
- **OpenWork** ([repository](https://github.com/different-ai/openwork)): the desktop app and core packages are MIT, and the team control plane under `ee/` is free for up to five users and needs a subscription for larger production use. Self-host the desktop locally, and run the control plane on your own infrastructure. Any model OpenCode supports, 50+ providers with your own keys, or local models through Ollama. A desktop Cowork alternative built on OpenCode, where files stay on your machine and teammates share skills and MCP servers.
- **Eigent** ([repository](https://github.com/eigent-ai/Eigent)): Apache-2.0. Run it locally, or self-host the deployment on your own infrastructure. Model agnostic, with cloud providers, an enterprise gateway, or local models on your own keys. A multi-agent Cowork desktop built on the CAMEL framework, organizing work as spaces, sessions and tasks.
- **OpenHands** ([repository](https://github.com/OpenHands/OpenHands)): MIT. Run it locally, in Docker, on a VM, or on your company infrastructure. Bring your own model, and use it with any LLM. A self-hosted control center for coding agents and automations, which fits an engineering team more than a company doing general knowledge work.
- **Open WebUI** ([repository](https://github.com/open-webui/open-webui)): the Open WebUI License, permissive with a branding clause that needs a separate commercial license to rebrand above 50 users. Built to run entirely offline. Ollama and any OpenAI-compatible API. A self-hosted AI interface with agents, tools and a terminal, strongest as a chat and knowledge workspace.
- **AnythingLLM** ([repository](https://github.com/Mintplex-Labs/anything-llm)): MIT. Local-first, with Docker and desktop builds. Local or cloud LLMs, including Ollama, LM Studio and OpenAI. An all-in-one private chat-with-your-docs app with built-in agents and scheduled tasks.
- **CrewAI** ([repository](https://github.com/crewAIInc/crewAI)): MIT for the framework, with a commercial control plane sold alongside it. You run the Python framework and the application around it. The LLM providers you configure. A framework for role-based multi-agent workflows, where the runtime, the memory and the approval step are still yours to build.
- **AutoGPT** ([repository](https://github.com/Significant-Gravitas/AutoGPT)): MIT for the classic agent, and the platform folder under the Polyform Shield License, free for personal and internal business use and not for resale as a competing hosted service. Self-hosting is the free path, with your own infrastructure and model keys. Hundreds of AI models with your own keys. An autonomous agent that chases a goal, with a hosted platform and a visual builder.

## How to choose

Start from the job you need done. A governed system for a whole company points to Kortix. A workspace for one person on their own files points to a desktop app such as OpenWork or Eigent. Coding work points to OpenHands. Chat over documents points to AnythingLLM or Open WebUI. Coordination code you write yourself points to CrewAI or AutoGPT.

The [decision guide](docs/choosing-an-open-source-claude-cowork-alternative.md) sets out the five dimensions to compare: ownership, self-hosting, models, connectors and governance. The [open-source AI agent platforms](https://opensourceclaudecowork.com/open-source-ai-agent-platforms) page sorts the field into categories, and the [AI agent orchestration](https://opensourceclaudecowork.com/ai-agent-orchestration) page covers running many agents at once.

## More on the open-source Claude Cowork hub

- [Open source Claude Cowork](https://opensourceclaudecowork.com/): the open-source AI Operating System, and why you keep the repo.
- [Self-hosting an open-source Claude Cowork alternative](https://opensourceclaudecowork.com/self-hosting): the install, command by command.
- [Self-hosted AI workspace](https://opensourceclaudecowork.com/self-hosted-ai-workspace): the two layers behind the phrase, and what each one costs.
- [Claude Cowork vs ChatGPT Work](https://opensourceclaudecowork.com/claude-cowork-vs-chatgpt-work): the two closed platforms, and the open-source third option.

## Docs in this repository

- [Choosing an open-source Claude Cowork alternative](docs/choosing-an-open-source-claude-cowork-alternative.md)
- [Self-hosting an open-source Claude Cowork alternative](docs/self-hosting-claude-cowork-alternative.md)
- [FAQ](docs/faq.md)

## Contributing

Add a project only when you can name its license and what it allows, whether it self-hosts, the models it runs, and a link to its own repository or site. Keep Kortix first, keep the open-source row accurate, and move the checked date when a fact changes.
