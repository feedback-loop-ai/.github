<p align="center"><img src="https://raw.githubusercontent.com/feedback-loop-ai/.github/main/brand/avatar.svg" width="96" alt="Feedback Loop AI — a cycle, closed by the signal coming back"></p>

<h1 align="center">Feedback Loop AI</h1>

<p align="center"><strong>Feedback loops in an AI-native world — the software delivery cycle first.</strong></p>

Agents can write code all day. What they cannot do on their own is close the loop: prove the work was verified, reviewed, shipped, and recorded in a form a person can replay and audit. Every project here exists to make that loop deterministic, inspectable, and provable — first for software delivery, then for whatever else a feedback loop runs through.

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

## Projects

| Project | What it is | State |
|---|---|---|
| [**brokkr**](https://github.com/feedback-loop-ai/brokkr) | Deterministic delivery engine for autonomous multi-agent software delivery. An event-sourced phase machine is the outermost layer; agent sessions are leaf effects inside it. Runs you can replay, releases you can prove. | [v0.7.0](https://github.com/feedback-loop-ai/brokkr/releases/latest) · Rust · MIT OR Apache-2.0 |
| [**homebrew-tap**](https://github.com/feedback-loop-ai/homebrew-tap) | Homebrew formulas for Brokkr, rendered from attested releases. | `brew install feedback-loop-ai/tap/brokkr` |
| [**scoop-bucket**](https://github.com/feedback-loop-ai/scoop-bucket) | Scoop manifests for Brokkr, rendered from attested releases. | `scoop bucket add brokkr https://github.com/feedback-loop-ai/scoop-bucket` |
| [**mcp-scaleway**](https://github.com/feedback-loop-ai/mcp-scaleway) | An MCP server for the Scaleway APIs — the cloud an agent can reach through a tool call. | TypeScript |
| [**mcp-ory-kratos**](https://github.com/feedback-loop-ai/mcp-ory-kratos) | An MCP server for Ory Kratos identity — sessions, identities, recovery, through the same door. | TypeScript |

## Start here

One shell line runs a delivery through Brokkr and puts its proof on screen:

```console
brokkr run --recipe fast --repo . --feature "add one visible improvement" && brokkr inspect --run latest
```

The [quickstart](https://github.com/feedback-loop-ai/brokkr/blob/main/docs/guides/quickstart.md) takes it from install to a shipped run in sixty seconds; the [decision record](https://github.com/feedback-loop-ai/brokkr/tree/main/docs/decisions) is where the engine's rules come from and why.

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
