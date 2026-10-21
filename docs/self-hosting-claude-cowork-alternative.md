# Self-hosting an open-source Claude Cowork alternative

Kortix is open source: the open-source AI Operating System, and the leading open-source alternative to Claude Cowork and ChatGPT Work. This is the setup guide for a team that wants the platform on its own hardware, with the configuration, the memory and the data kept in a repository and a disk it controls.

Claude Cowork has no self-hosted edition. It runs on Anthropic's cloud or in your own Amazon Bedrock, Google Cloud or Microsoft Foundry account, and Anthropic keeps the configuration and the work history ([Anthropic's Cowork page](https://claude.com/product/cowork)). Kortix self-hosts as one Docker Compose stack that carries the frontend, the API, the LLM gateway and a bundled Supabase distribution, and self-host is free. The [self-hosting page](https://opensourceclaudecowork.com/self-hosting) on the hub carries the same route in a shorter form.

## What you need before you start

- A Linux box that will hold the stack. An 8 GiB host runs it with the documented defaults.
- A domain, with A or AAAA records for the domain and for `api.<domain>`.
- Ports 80 and 443 open, so the bundled Caddy proxy can issue its TLS certificate.
- Docker on the host, or let the bootstrap script install it.
- A Platinum API key (`PLATINUM_API_KEY`). Sessions do not start without it.
- Model keys, connected in the dashboard's model picker. A self-hosted instance uses your key by default.

Agent sessions do not run on this box. They run on the sandbox provider, which keeps the host small and lets parallel work scale off it.

## Route one: the bootstrap script

On a bare Linux box, one script installs Docker, installs the `kortix` CLI and starts the stack:

```bash
curl -fsSL https://kortix.com/install | bash
```

The script runs on Linux only. On another operating system, install the CLI and use the manual route, which shows exactly what the script automates.

## Route two: the manual install

Four steps take the stack from a clean CLI to a running instance.

```bash
# 1. Install the CLI
curl -fsSL https://kortix.com/install | bash

# 2. Render the stack. This writes the Compose file, .env, a Caddyfile
#    and an updater script, with ports, URLs and keys already generated.
kortix self-host init --domain kortix.example.com

# 3. Start it
kortix self-host start

# 4. Watch it settle
kortix self-host status
kortix self-host logs
kortix self-host doctor
```

For an evaluation that skips DNS, `kortix self-host init --tunnel cloudflare` brings the stack up behind a tunnel URL that changes on each restart.

## Add the credentials and the models

```bash
kortix self-host configure
```

The command prompts for a sandbox provider key and, optionally, a managed-git token. GitHub connects separately in the dashboard under Settings then Git. Models are bring-your-own-key in the app: connect your own provider key in the model picker, or point the platform at an OpenAI-compatible endpoint in front of a local model server.

## Where the instance lives, and what to back up

One directory holds the whole instance:

```
~/.config/kortix/self-host/<instance>/
  .env                 every secret and signing key the instance uses
  volumes/db/data      the Postgres database
  volumes/storage      file storage
```

Kortix has no separate backup system. Copy those three items off the box before any destructive command, and copy them on a schedule once a team depends on the instance.

## Sizing the host

An 8 GiB host runs the stack with its documented defaults, and the API ships with a 640 MiB memory limit sized for that box. On a 16 GiB host whose API traffic reaches the limit, raise it and confirm the result:

```bash
kortix self-host env set KORTIX_API_MEMORY_LIMIT=1024m
docker stats --no-stream
```

The same rendered stack runs unchanged on a laptop, a VPS, a VPC or on-prem hardware. Moving from a trial to production changes the domain plus the DNS records and open ports a stable domain needs.

## What still touches the internet

Two dependencies stay outside the box, and both are worth planning for.

The first is the image registry. `kortix self-host start` pulls its images from a registry, so the host needs outbound access, and the bundled updater checks for new images once a day. To hold a release still, pin an exact version instead of tracking the updater:

```bash
kortix self-host update --tag <version>
```

The second is the sandbox provider. Agent sessions run on Platinum, the reference sandbox provider, and the API reaches that provider over egress. A self-hosted Kortix is not a fully offline install, and the trade is deliberate: parallel sessions consume the provider's compute instead of your box's CPU and memory.

## Keep the review gate on a self-hosted box

Self-hosting does not remove the gate. Each session has its own isolated machine and branch. OpenCode is the harness, and the agent plans, runs tools, commits and pushes, then opens a change request. Session work reaches `main` through a change request, and merge is default-deny for agents. From the CLI the review works three ways:

```bash
kortix cr ls      # list change requests
kortix cr diff    # read the patch
kortix cr merge   # land it
```

On a self-hosted box this gate is the point. The agent holds broad tool access inside its sandbox, and the change request is where the team keeps control. The [self-hosted AI workspace](https://opensourceclaudecowork.com/self-hosted-ai-workspace) page covers how the repo, the memory and the connectors fit together once the stack is up, and the [AI agent orchestration](https://opensourceclaudecowork.com/ai-agent-orchestration) page covers coordinating many sessions across a team.

## Before you onboard the team

- A persistent domain with A or AAAA records for the domain and `api.<domain>`, and ports 80 and 443 open.
- A Platinum API key, so sessions can start.
- Model keys connected in the dashboard's model picker.
- Off-box copies of the database, the storage and the `.env` file.
- An update policy: the stable channel, or a pinned version with auto-update off.
- Named reviewers who read and merge each change request.

With the domain, the keys and the backup copies in place, the first session runs the same way it does on the managed cloud. [Read the docs](https://kortix.com/docs) carry the reference behind each command.
