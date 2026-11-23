# Keeping up with upstream

Tinycast Legacy is a one-way fork of [`abue-ammar/tinycast`](https://github.com/abue-ammar/tinycast).
It does not track `upstream/main` and has no merge commit. Upstream changes are reviewed one commit
at a time and cherry-picked when they matter on macOS 14.4.

The fork's base is `58168bf7` (2026-11-08). The `upstream` remote points at the original repository:

```sh
git fetch upstream
git log --oneline 58168bf7..upstream/main
git cherry-pick -x <sha>            # -x keeps the upstream hash in the message
```

## Resolving the usual conflicts

- **`Tinycast.xcodeproj/project.pbxproj`** is generated. Keep the fork's copy (`git checkout --ours`)
  and run `xcodegen generate`; the target sources are folder references, so new files are picked up.
- **`Scripts/run-tests.sh` and `docs/testing.md`** name harnesses in kebab-case here, while upstream
  renamed them to `*Tests` in `fd3c32fc` (not ported). Keep the fork's names and only add the new
  source files a commit introduces.
- **`Tinycast/Resources/Localizable.xcstrings`** carries the fork's removed support strings. Take the
  upstream hunk, then run `./Scripts/sync-strings.sh` so the compiler-extracted keys win.
- **API floor.** Upstream builds with the macOS 26 SDK. Guard anything newer than 14.4 with
  `if #available`, or adapt it to Swift 6.0 (`isolated deinit` becomes `deinit { MainActor.assumeIsolated { … } }`).
- **Swift 6.0 rethrows inference** rejects a nested `@MainActor` function passed straight to
  `allSatisfy` or `contains(where:)`; wrap the call in a closure (`{ registered($0) }`).
- **Never take** `website/`, `.github/`, bundle-id migrations, or notarization/update plumbing.

## Ported since the fork point

| Commit    | Change                                                       | Adaptation                                          |
| --------- | ------------------------------------------------------------ | --------------------------------------------------- |
| `d9414598` | Yandex Telemost meeting links                               | none                                                |
| `0f1c6392` | AI chat accessibility crash; web search for OpenAI/Anthropic | none                                                |
| `142e3a06` | Quicklink prompt hides on a second shortcut press           | none                                                |
| `e4c9bd5c` | Calendar stops re-checking access every minute              | none                                                |
| `3d6384e5` | A note closed with text selected stays closed                | `writingToolsBehavior` guarded to macOS 15           |
| `e61ba33c` | Calculator groups numbers by the region's widths             | none                                                |
| `bc5cd0cc` | Notes word count                                            | none                                                |
| `d153da15` | Keeps a sandboxed app's staged image copy                    | none                                                |
| `91ae75c9` | Calculator constants, molar mass, text functions, new engine | none                                                |
| `44a1501d` | Toggle Hidden Files no longer fails when the key is unset    | none                                                |
| `08dda28d` | Calculator sats conversion                                   | none                                                |
| `99d1d17a` | File Search folder matching and Include hidden files         | none                                                |
| `6f479455` | Unregisters hotkeys of disabled features                     | none                                                |
| `1156212e` | Removes the 🎤 dictation-key remap                            | none                                                |
| `fe94d6f8` | Removes two self-logged errors                               | none                                                |
| `c1eeb12f` | Keyboard-driven snippet argument prompt                      | none                                                |
| `9e9be988` | Forwarded Hyper chords no longer toggle Caps Lock            | Swift 6.0 concurrency + deinit adaptation            |

## Deliberately skipped

| Commit(s)              | Why                                                                                         |
| ---------------------- | ------------------------------------------------------------------------------------------- |
| `1ad90058`             | In-app update checks; the fork has no updater.                                              |
| `2536865a`, `6fa8ba12`, `4a3d4440` | Upstream's bundle-id move and its migrations; the fork has its own identity.       |
| `9c3c8995`             | iCloud Sync; needs a Developer ID signing profile and a deployed CloudKit schema.           |
| `876b61dc`, `970bf4e4` | Settings in its own process and its follow-up; a large architecture change tied to CloudSync. |
| `5370cf64`             | macOS 26 glass-shadow fix; the fork does not draw Liquid Glass.                             |
| `af5e7c2e`             | Icon pack; a 38-file UI restyle that conflicts with the fork's existing symbol tinting.     |
| `fd3c32fc`             | Snippets copy/pin and the `*Tests` file rename; revisit as two focused ports.               |
| website, `.github`, templates, `README` revisions | Not part of the app.                                              |

## Known divergence

`fd3c32fc` renamed every test file and harness to `*Tests`. Skipping it keeps the fork's kebab-case
names, so later upstream commits touch those names in context. Each port pays for that in
`run-tests.sh` and `docs/testing.md`; porting the rename alone would end the tax, at the cost of a
large mechanical commit.
