# Choosing an open-source Claude Cowork alternative

Kortix is open source: the open-source AI Operating System, and the leading open-source alternative to Claude Cowork and ChatGPT Work. This guide is for a team picking among the open-source projects that replace Cowork, and it compares them on the five things that decide whether the choice holds up after the next release.

Claude Cowork is Anthropic's agent for non-coding knowledge work, and it runs on Anthropic's cloud on Anthropic's models with no self-hosted edition ([Anthropic's Cowork page](https://claude.com/product/cowork)). An open-source alternative changes several of those facts at once, so a feature checklist ages quickly. The durable questions are about ownership and control.

## The five dimensions that decide the choice

### Ownership: where the configuration and the memory live

The first question is who holds the agents, the skills, the memory and the work history. In a closed product they sit inside the vendor's account, and leaving means losing them. In Kortix they are files in one git repo you own, versioned and diffable, so any part of the system can be read, backed up or rolled back. A desktop app such as OpenWork or Eigent keeps files on your machine, which serves one person or a small team. The question to ask is whether the material lives somewhere you can copy and move without asking the vendor.

### Self-hosting: what runs on your hardware, and what still calls out

Self-hosting means the runtime, the data and the configuration run on machines you control. Kortix self-hosts as one Docker Compose stack, and the [self-hosted AI agent platform](https://opensourceclaudecowork.com/self-hosted-ai-agent-platform) page walks the split between what you own and what stays rented. Two things usually still call out: the image registry that serves the stack, and the model provider, unless you run local models. A desktop alternative self-hosts by running on a laptop. A platform self-hosts by running on a server, which is what a team needs. The [self-hosting guide](https://opensourceclaudecowork.com/self-hosting) covers the install.

### Models: whose models, and whose keys

A closed product ties the model to the vendor. Claude Cowork runs Anthropic's models only. An open-source platform separates the two decisions. Kortix runs any model provider with your own keys, or you can use the ChatGPT plan you already pay for, or sign in with your OpenCode Console account for OpenCode Zen and Go. OpenWork, Eigent, Open WebUI and AnythingLLM all bring your own keys or run local models. The question to ask is whether you can switch providers without rebuilding the system, and who pays for the tokens.

### Connectors: what the agent can reach, and how credentials travel

The connector layer decides whether an agent can do real work in your tools. Kortix reaches 3,000+ apps in a click, plus MCP, OpenAPI, Postman, GraphQL and raw HTTP, and connector credentials are brokered server-side and never enter the machine. Each tool call is set to allow, ask or block, down to the arguments of the call. AnythingLLM and Open WebUI reach tools through MCP and OpenAI-compatible servers. The question to ask is what the agent can reach, and where the credential sits when it does.

### Governance: permissions, approval gates, audit and identity

Governance is the dimension teams skip and later need. A closed product draws its own boundary. On an open-source platform you place the gate. Kortix ships per-resource permissions for people and agents, roles, groups and an audit trail, SAML 2.0 single sign-on and SCIM 2.0, and secrets encrypted at rest with a key per project. Approval gates are off until you set them. Session work reaches `main` through a change request, and merge is default-deny for agents. A framework such as CrewAI leaves the gate to you, and an autonomous agent such as AutoGPT asks you to build it for a self-hosted deployment. The question to ask is who reviews a change before it lands.

## When each choice fits

| If the job is | Reach for | Because |
| --- | --- | --- |
| A governed system for a whole company | Kortix | Agents, skills, memory and connectors in one repo you own, with a review gate and free self-host |
| A workspace for one person on their own files | OpenWork or Eigent | Both are desktop apps that keep files local and need no account to start |
| Coding agents and automations for an engineering team | OpenHands | A self-hosted control center built for code, not general knowledge work |
| Chat and search over company documents | AnythingLLM or Open WebUI | Both put a private, model-agnostic chat over your own files |
| Coordination code you write yourself | CrewAI or AutoGPT | Both are starting points for a system you build, host and secure |

## A five-question checklist

1. Where do the agents, the memory and the work history live, and can I copy them out?
2. What runs on my hardware, and what still calls out to a registry or a model provider?
3. Which models can I run, with whose keys, and can I switch providers later?
4. What can an agent reach, and where does each credential sit when it does?
5. Who reviews a change before it lands, and is that gate off by default?

The [open-source AI agent platforms](https://opensourceclaudecowork.com/open-source-ai-agent-platforms) page sorts the field into company platforms, frameworks and autonomous agents, and the [AI agent orchestration](https://opensourceclaudecowork.com/ai-agent-orchestration) page covers running many agents at once. For the two closed platforms side by side, see [Claude Cowork vs ChatGPT Work](https://opensourceclaudecowork.com/claude-cowork-vs-chatgpt-work).
