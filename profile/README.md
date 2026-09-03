<p align="center"><img src="https://raw.githubusercontent.com/feedback-loop-ai/.github/main/brand/avatar.svg" width="96" alt="Feedback Loop AI — a cycle, closed by the signal coming back"></p>

<h1 align="center">Feedback Loop AI</h1>

<p align="center"><strong>Feedback loops in an AI-native world — the software delivery cycle first.</strong></p>

Agents can write code all day. What they cannot do on their own is close the loop: prove the work was verified, reviewed, shipped, and recorded in a form a person can replay and audit. Every project here is one piece of that loop: the engine that runs the cycle, the hands an agent uses to reach real infrastructure, the channels a result ships on. Brokkr is the largest piece. It is not the only one, and the organisation is not built around it — it is built around the loop.

## The loop we mean

A feedback loop is not a chat with an agent. It is a cycle with stages, and a signal that comes back to where it started:

| Stage | Who acts | What comes back |
|---|---|---|
| Implement | an agent, in a seat | a diff |
| Verify | the machine | test, lint, and coverage results — pass or fail, no opinion |
| Review | an agent, a different one | a ruling with reasons |
| Ship | the machine | a release the install can verify by checksum |
| Record | the journal | every result and ruling, replayable |

The record is the point. Without it the other four stages are anecdotes.

## Pieces of the loop

Three kinds of piece so far. An **engine** runs the cycle and keeps the record. **Hands** are MCP servers — the way an agent acts on a cloud, an identity store, anything with an API — so the verify and ship stages touch real systems, not mocks. **Channels** carry an attested result to the machine that installs it.

| Project | What it is | Licence | State |
|---|---|---|---|
| [**brokkr**](https://github.com/feedback-loop-ai/brokkr) | **Engine.** Deterministic delivery engine for autonomous multi-agent software delivery. An event-sourced phase machine is the outermost layer; agent sessions are leaf effects inside it. Runs you can replay, releases you can prove. | MIT OR Apache-2.0 | [v0.8.0](https://github.com/feedback-loop-ai/brokkr/releases/latest) · Rust |
| [**homebrew-tap**](https://github.com/feedback-loop-ai/homebrew-tap) | **Channel.** Homebrew formulas for Brokkr, rendered from attested releases. | MIT | `brew install feedback-loop-ai/tap/brokkr` |
| [**scoop-bucket**](https://github.com/feedback-loop-ai/scoop-bucket) | **Channel.** Scoop manifests for Brokkr, rendered from attested releases. | MIT | `scoop bucket add brokkr https://github.com/feedback-loop-ai/scoop-bucket` |
| [**mcp-scaleway**](https://github.com/feedback-loop-ai/mcp-scaleway) | **Hands.** An MCP server for the Scaleway APIs — compute, storage, networking, an agent can reach through a tool call. | MIT | TypeScript |
| [**mcp-ory-kratos**](https://github.com/feedback-loop-ai/mcp-ory-kratos) | **Hands.** An MCP server for Ory Kratos — identities, sessions, recovery, through the same door. | MIT | TypeScript |

## Start here

To see a whole loop close, end to end, run one delivery through Brokkr — one shell line, and its proof on screen:

```console
brokkr run --recipe fast --repo . --feature "add one visible improvement" && brokkr inspect --run latest
```

The [quickstart](https://github.com/feedback-loop-ai/brokkr/blob/main/docs/guides/quickstart.md) takes it from install to a shipped run in sixty seconds; the [decision record](https://github.com/feedback-loop-ai/brokkr/tree/main/docs/decisions) is where the engine's rules come from and why. To give an agent hands on your own infrastructure instead, start from one of the MCP servers: each is a small TypeScript project that maps one API onto tools, and the pattern transfers.

## What we believe

A feedback loop is only as honest as the principles it runs on. These are ours — each one is a constraint on what we build, not a slogan.

- **Open source, permissively.** What we publish, you can use, ship, fork, and outgrow. Software that closes a loop for you should never be the thing that locks you in.
- **Vendor agnostic.** Which model, which cloud, which identity store is a parameter of the loop, not its foundation. Brokkr drives `claude`, `codex`, or `dsh` through the same recipe — an Anthropic, an OpenAI, or a DeepSeek/Qwen model, one line apart; an MCP server maps an API, whoever the agent behind the tool call is. When a vendor changes its terms, you change a line, not a system.
- **Open data.** The journal a run produces, the evidence a release carries, the numbers a decision rests on — documented formats, readable without our tools, yours to publish. Data you can't take with you isn't yours.
- **Transparency.** Decisions are written down with their reasons, numbered, and kept — including the ones that turned out wrong. The reasoning is public even when the code is the smaller part.
- **Provenance.** Every artefact says where it came from: a release is attested and checksummed, a pull request names the run that produced it, a result names the ruling it rests on. If you can't trace it, you can't trust it — and neither can we.
- **Deterministic over stochastic.** Models are stochastic and that's fine — inside a machine that is not. The state machine, the verifier, the record, the release: those are deterministic, replayable, and the same on the second run as the first. Probability belongs in the leaves, never in the trunk.
- **Critical thinking.** A model's output is a claim, not a result. Claims get verified by something that cannot be persuaded; numbers get reconciled before they're quoted; a confident answer earns the same scrutiny as a hesitant one.
- **Fairness.** Credit, cost, and blame attach to the work that was actually done, by whoever — or whatever — did it, measured the same way each time. No hidden subsidies, no unpriced labour, no laundering a stochastic guess into a deterministic-looking fact.
- **Neutrality.** We do not prefer a technology because of where it comes from. A model from Hangzhou gets the same seat, the same charter, and the same scrutiny as one from San Francisco; a cloud in Paris is as first-class as one in Virginia. The pieces already say so — `dsh` beside `claude` in the engine, Scaleway and Ory as the first hands. Neutral today, and built to stay neutral when it becomes inconvenient.
- **AI, used ethically.** Agents act only within a scope a person authorised, on record, with a person keeping the final word on what ships. We build tools that make people more capable and more accountable, never tools that make accountability disappear.

## How we work

- **The machine is the outer loop.** Agents are effects inside a state machine, not the other way round. Nothing an agent says is a result until the machine records it.
- **Proof over trust.** Releases are attested. Installs verify a checksum before they run anything. The journal is the evidence, not the changelog.
- **Brokkr builds Brokkr.** Every pull request on the engine goes through the engine, and the run that produced it is linked from the PR. See [`CONTRIBUTING.md`](https://github.com/feedback-loop-ai/brokkr/blob/main/CONTRIBUTING.md).
- **Rulings are written down.** When a question has two defensible answers, the operator rules and the ruling is a numbered decision in the repo, so the next person can read why instead of asking.

## Commitments

- **Every public repository in this organisation carries a permissive open-source licence.** MIT, Apache-2.0, or both — never copyleft, never source-available, never a licence that changes later. If you can read it here, you can use it, ship it, and fork it.
- **If the organisation succeeds, the work goes to a foundation.** The long-term commitment is that these projects end up governed by a neutral foundation rather than by whichever company owns the account. That is a stated intent, not a done deed: it is redeemed when there is something worth handing over, and this page is where you hold us to it.

---

<p align="center">Part of CMD Bulgaria LTD · the organisation mark and its rules live in <a href="https://github.com/feedback-loop-ai/.github/tree/main/brand"><code>brand/</code></a></p>
