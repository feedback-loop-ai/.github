<p align="center"><img src="https://raw.githubusercontent.com/feedback-loop-ai/.github/main/brand/avatar.svg" width="96" alt="feedback-loop-ai — a loop closed by feedback"></p>

# feedback-loop-ai

**Feedback loops in an AI-native world — the software delivery cycle first.**

Agents can write code all day. The question is whether anything closed the loop: did the work get verified, reviewed, shipped, and recorded in a form you can replay and audit? Everything here is built to make that loop deterministic, inspectable, and provable.

## Public projects

| Project | What it is | State |
|---|---|---|
| [**brokkr**](https://github.com/feedback-loop-ai/brokkr) | Deterministic delivery engine for autonomous multi-agent software delivery — an event-sourced phase machine at the outermost layer, agent sessions as leaf effects. Runs you can replay; releases you can prove. | [v0.7.0](https://github.com/feedback-loop-ai/brokkr/releases/latest) · Rust · MIT OR Apache-2.0 |
| [**homebrew-tap**](https://github.com/feedback-loop-ai/homebrew-tap) | Homebrew formulas for Brokkr, rendered from attested releases. | `brew install feedback-loop-ai/tap/brokkr` |
| [**scoop-bucket**](https://github.com/feedback-loop-ai/scoop-bucket) | Scoop manifests for Brokkr, rendered from attested releases. | `scoop bucket add brokkr …` |
| [**mcp-scaleway**](https://github.com/feedback-loop-ai/mcp-scaleway) | An MCP server for the Scaleway APIs. | TypeScript |
| [**mcp-ory-kratos**](https://github.com/feedback-loop-ai/mcp-ory-kratos) | An MCP server for Ory Kratos. | TypeScript |

## How we work

- **The machine is the outer loop.** Agents are effects inside a state machine, not the other way round. Every phase result and every ruling lands in a journal.
- **Proof over trust.** Releases are attested; installs verify a checksum before they run anything; the delivery journal is the evidence.
- **Brokkr builds Brokkr.** Every pull request on the engine goes through the engine — see [`CONTRIBUTING.md`](https://github.com/feedback-loop-ai/brokkr/blob/main/CONTRIBUTING.md).

Part of CMD Bulgaria LTD. The organisation mark and its rules live in [`brand/`](https://github.com/feedback-loop-ai/.github/tree/main/brand).
