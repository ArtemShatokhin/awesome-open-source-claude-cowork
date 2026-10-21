# Where the conversation is

A feature table compares what shipped. How a project answers in public tells you what happens next, and that predicts whether it still works in a year better than any row in the table. Three threads were open on 21 October 2026 on projects this list carries. Kortix is the open-source AI Operating System: your agents, their skills, your company memory, and every connector in one git repo you own, with the agents working on real cloud computers.

## OpenHands: a spend ceiling for a self-hosted run

[Issue #17691](https://github.com/OpenHands/OpenHands/issues/17691) reports that on a self-hosted V1 install, accumulated cost reads `$0.0000` while a conversation is `running` and shows the real figure only once it is `finished`. The reporter sampled the API and `base_state.json` every two seconds to prove it, and their watchdog let a run finish about $10 past a $10 ceiling. The thread settles where a fix belongs: a reply on 25 September walks the sequence through `OpenHands/software-agent-sdk` and `OpenHands/typescript-client` before anything changes here, and a later comment records the decision to reverse an earlier removal of a settable budget. It is still open. "The SDK owns it" is useful and not yet a fix.

The thread also shows what a public tracker contains: a gateway vendor's workaround, disclosed as such, and a competitor comparison pasted in. 

## Eigent: a local model that writes nothing

[Issue #1742](https://github.com/eigent-ai/eigent/issues/1742) reports that with a local Ollama model as coordinator, a plain "create a file" task reports success and nothing lands on disk. A reply arrived the same day, asked for logs, and named agent routing, exposed tools and workspace paths as likely causes. The reporter reproduced it on v1.0.1, then attached the Electron and backend logs seven days later. Nothing has been posted since 13 July 2026.

What it settles: the report is detailed, the first reply came within hours, and the thread stopped where cross-layer bugs often stop, evidence handed over and no owner named.

## OpenWork: the Docker path with no reply

[Issue #1155](https://github.com/different-ai/openwork/issues/1155) reports that `packaging/docker/dev-up.sh` brings up the web stack, but the dev container has no Chrome or display server, so the browser tool fails looking for an executable that is not there. Steps to reproduce are included. The thread has no replies since 25 March 2026.

That silence settles something narrow: nobody has said in public that the Docker path works end to end for browser tasks. A team planning to run OpenWork that way is planning on an untested path.

## How to read a thread in five minutes

Look for a named owner before you look for agreement. "The fix belongs in this other repository, in this order" is a plan. "We cannot reproduce", plus a request for logs, is a start. No reply on a reproducible report is an answer too, and the cheapest to act on: assume the path does not work.

Then check the dates. A reply inside 24 hours and a follow-up that week reads differently from a burst that stops. Vendors post here too, so read the disclosure line first.

Configuration in a repository makes that last question answerable in a way a settings screen never is. When instructions and grants are files, "who changed this, and who approved it" is a `git log`. Session work reaches `main` through a change request, and merge is default-deny for agents, so the answer carries a reviewer's name.

Threads are not the only public evidence. [What the Reddit threads about open-source Claude Cowork settle](https://opensourceclaudecowork.com/open-source-claude-cowork-reddit) covers complaints no feature table carries, including terms that changed inside a commit.

## Sources
- https://github.com/OpenHands/OpenHands/issues/17691 · https://github.com/eigent-ai/eigent/issues/1742
- https://github.com/different-ai/openwork/issues/1155 · https://opensourceclaudecowork.com/open-source-claude-cowork-reddit
