# image/arch — signpost (not the rule-set)

This submodule is the **Arch Linux** base image family: a single
`overthink.yml` that imports the main repo under the `ov` namespace and
`build.yml` flat.

**Load these skills FIRST (R0):**

- `/ov-distros:arch` — the Arch base image; root of the pac-based hierarchy.
- `/ov-distros:arch-builder` — the pixi/npm/cargo/yay builder.
- `/ov-coder:arch-coder`, `/ov-coder:arch-ov` — the dev/ov images here.
- `/ov-image:image` + `/ov-image:layer` — composition + layer authoring.

**Authoritative rules live in the `overthink` superproject's root `CLAUDE.md`**
(R0–R10, hard-cutover, AI attribution, git-workflow). This file only
signposts and restates no rule. The full multi-agent workflow (sub-agents,
`/verify-beds`, `/audit-deploy-configs`) is in `/ov-internals:agents`. History
lives in `CHANGELOG.md`.
