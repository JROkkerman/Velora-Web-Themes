# Velora Web theme API 1

This colour-only format is shared across Velora web applications. Velora Music
implements it today; other applications can use the same packages by implementing
the token mapping and loading rules below. Themes contain no application data.

## Package layout

```
themes/<id>/
  velora-plugin.json
  README.md
  LICENSE
```

Each theme has its own stable ID and version. Multiple themes can share a
repository; the folder path identifies the package within it. In this repository
the path is always `themes/<id>`. The manifest's `repository` is
`https://github.com/JROkkerman/Velora-Web-Themes`.

## Manifest

| Field | Contract |
| --- | --- |
| `manifest_version`, `plugin_api` | Both `1` |
| `type` | `theme` |
| `id` | 1–64 lowercase ASCII letters, digits and hyphens; starts with a letter |
| `name`, `author`, `description` | Plain text; at most 80, 120 and 300 characters |
| `version` | Numeric `major.minor.patch`, without leading zeroes |
| `repository` | HTTPS GitHub repository root URL, without query or fragment |
| `color_scheme` | `light` or `dark`, also used for native controls |
| `colors` | Named tokens below, in `#RRGGBB` or `#RRGGBBAA` |
| `preview` | `paper`, `surface`, `line`, `ink`, `accent`, `art-from`, `art-to` |

IDs `light`, `dark`, `system` and `none` are reserved for built-in choices.
Unknown fields and tokens, unsupported API versions and non-hexadecimal colours
must be rejected. A manifest must not exceed 32 KiB.

Required colours:

```
paper surface ink muted accent line soft
```

Optional colours:

```
green primary-text primary-hover primary-background player-surface
nav-text nav-icon nav-hover selected-text cover-surface
avatar-surface avatar-text badge-surface badge-text badge-overlay
fact-text star unavailable summary search-surface search-icon
player-art-surface player-glow toast-surface toast-text
error feedback-error eyebrow
```

The collection defines all 35 tokens and all seven preview colours. Optional
tokens fall back to the application's neutral light/dark palette when absent.
Some tokens apply only to certain applications: Receipts and Finance can leave
player-specific tokens unused. Keeping them in the manifest preserves API 1
compatibility without requiring those applications to include music features.

## Application behaviour

- Keep neutral Light, Dark and Device available without any plugins. Device
  follows the operating system and is stored as `system` in Velora Music.
- Load validated bundled themes, then validated installed themes. An installed
  theme overrides only the same ID. Invalid replacements leave the bundled copy
  available. Use a neutral fallback when a selected theme is unavailable.
- Treat palettes as data. Map allowed tokens to application-owned CSS variables;
  do not execute scripts, load remote assets or accept raw CSS from manifests.
- Keep layout, typography and application behaviour under application control.
- Preserve stable IDs in saved preferences. Keep version, source repository,
  package path and source commit in the consuming application's provenance lock.

Velora Music reads packages on startup, ignores symlinked directories/manifests,
and examines up to 256 directories per source. It installs individual folders
under `<private-data>/plugins/themes/<id>/`. Other applications should document
their own installation location and lifecycle.
