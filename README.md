# overthinkos/arch

The **Arch Linux image family** for [OpenCharly](https://github.com/overthinkos/overthink),
split into its own repository and mounted as a git submodule at `image/arch`
of the main repo.

## What's here

| Kind | Entries |
|---|---|
| `image:` | `arch-coder`, `charly-arch`, `arch-test`, `arch-pacstrap-builder`, `arch-pacstrap` |
| `vm:` | `arch-pacstrap` (bootstrap), `arch` (cloud-image) |
| `deploy:` | `eval-arch-pacstrap-vm`, `eval-arch-vm` (+ nested `arch-host`, `charly-cachyos-tailscale-test`) |

## Composition by reference — nothing is vendored

This repo contains **no layers and no build-config of its own**. Everything is
pulled from `github.com/overthinkos/overthink` by **github reference**:

- every layer in `box.yml` / `deploy.yml` is an `@github.com/overthinkos/overthink/candy/<name>:<tag>` ref;
- the shared build-config (`build.yml` — distro/builder/init) and the
  `arch` base + `arch-builder` pair (`arch-base.yml`) are remote
  `include:`s in `charly.yml`.

All references pin to a single tag of the upstream repo, so a build is
reproducible. There is exactly one definition of every layer and of the
base/builder pair — no duplication.

## Build

```bash
# Inside the submodule (the build verb defaults to charly.yml):
charly box build arch-coder

# From the parent opencharly repo:
charly -C image/arch image build arch-coder

# Standalone, against the published repo:
charly --repo overthinkos/arch image build arch-coder
```

The first build resolves the upstream github references into
`~/.cache/charly/repos/` and materializes the referenced layers under
`.build/_layers/`.

## Requirements

A build of any image here fetches from the upstream repo, so it needs network
access and a `charly` recent enough to understand the config's schema version
(`charly` hard-fails with an "update charly" message if the config is newer than the
binary supports).

---
*Assisted-by: Claude*
