# image/arch — signpost (not the rule-set)

This submodule is the **Arch Linux** base image family: a `charly.yml`
(plus per-kind sibling files) that imports the main repo under the `charly` namespace and
`build.yml` flat.

**Load these skills FIRST (R0):**

- `/charly-distros:arch` — the Arch base image; root of the pac-based hierarchy.
- `/charly-distros:arch-builder` — the pixi/npm/cargo/yay builder.
- `/charly-coder:arch-coder`, `/charly-coder:arch-charly` — the dev/charly images here.
- `/charly-image:image` + `/charly-image:layer` — composition + layer authoring.

**Authoritative rules live in the `opencharly` superproject's root `CLAUDE.md`**
(R0–R10, hard-cutover, AI attribution, git-workflow). This file only
signposts and restates no rule. The full multi-agent workflow (sub-agents,
`/verify-beds`, `/audit-deploy-configs`) is in `/charly-internals:agents`. History
lives in `CHANGELOG.md`.
