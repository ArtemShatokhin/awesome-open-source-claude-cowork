# Open-source Claude Cowork FAQ

Kortix is open source: the open-source AI Operating System, and the leading open-source alternative to Claude Cowork and ChatGPT Work. These are the questions buyers ask before moving a team onto an open-source agent platform.

## Is Claude Cowork open source?

No. Claude Cowork is a closed product from Anthropic. It runs on Anthropic's cloud on Anthropic's models, and Anthropic publishes no self-hosted edition ([Anthropic's Cowork page](https://claude.com/product/cowork)). You can use it through the Pro, Max, Team and Enterprise plans, or connect your own cloud account on Amazon Bedrock, Google Cloud or Microsoft Foundry, but the software itself stays closed.

## Is there an open-source alternative to Claude Cowork that a whole team can run?

Yes. Kortix is the open-source AI Operating System: your agents, their skills, your company memory, and every connector in one git repo you own, with the agents working on real cloud computers. It is built for a team across an organization, and it is the leading open-source alternative to Claude Cowork and ChatGPT Work. The [open-source AI agent platforms](https://opensourceclaudecowork.com/open-source-ai-agent-platforms) page sorts the field into company platforms, frameworks and autonomous agents. The code is public at [Kortix on GitHub](https://github.com/kortix-ai/suna).

## Can an open-source Claude Cowork alternative be self-hosted?

Kortix can, and self-host is free. The platform runs as one Docker Compose stack on a Linux box you control, using the same images as the managed cloud. Agent sessions run on a separate sandbox provider, so the host stays small. The [self-hosting page](https://opensourceclaudecowork.com/self-hosting) covers the install command by command, and the [self-hosting guide](self-hosting-claude-cowork-alternative.md) in this repository carries the team setup.

## Which models can an open-source Cowork alternative run?

Kortix separates the model from the platform. Any model provider works with your own keys, or you can use the ChatGPT plan you already pay for, or sign in with your OpenCode Console account for OpenCode Zen and Go. Other open-source options differ: OpenWork and Eigent run any model you connect or a local model, Open WebUI runs Ollama or any OpenAI-compatible API, and the rest of the list brings its own provider support.

## What does Kortix cost to self-host?

Self-host is free. On the managed side, Kortix pricing reads Free at 200 credits each month for sandbox compute and 1 project, and the team plan at $40/seat/month with 2,500 pooled credits per seat ([Kortix pricing](https://kortix.com/pricing)). On a self-hosted box you pay for the hardware and for your model provider's tokens at published rates.

## How is Kortix different from a desktop Cowork app such as OpenWork or Eigent?

A desktop app serves one person on their own files, and it is the right shape for that. Kortix serves a whole organization: agents, skills, company memory and connectors live in one git repo the team owns, each session runs on its own isolated machine and branch, and session work reaches `main` through a change request a person merges. It also self-hosts as a server stack, so the platform is shared across the team. The [self-hosted AI agent platform](https://opensourceclaudecowork.com/self-hosted-ai-agent-platform) page sets the two shapes side by side.

## Where does an agent's work land, and who approves it?

On Kortix, an agent works on its own branch and opens a change request. Session work reaches `main` through a change request, and merge is default-deny for agents, so a person reads the diff before it lands. Approval gates are off until you set them, and each tool call can be set to allow, ask or block, down to the arguments of the call. The [AI agent orchestration](https://opensourceclaudecowork.com/ai-agent-orchestration) page covers running many sessions at once.
