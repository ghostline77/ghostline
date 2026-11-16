# Ghostline

The Ghostline quest series. GQ001 is the opening quest: Patch's offer, cache extraction, Iris's handoff and delivery to Morrow. GQ002 continues the story.

`series.json` selects quests and defines shared character projects. Quests request character names in `resources.characters`; the build exports each required character once and automatically includes its resources and TweakXL when packaging. `project.json` declares depot ownership and dependencies. Game resource identities are independent of the repository layout.

```text
quests/<id>/quest.json       Quest behavior and resource inputs
quests/<id>/scenes/          Authored scene specs
quests/<id>/world/           Authored world and building specs
quests/<id>/script/          Dialogue manifests and written scripts
quests/<id>/voice/source/    Reviewed source audio
quests/<id>/voice/wem/       Published game voiceovers
quests/<id>/lipsync/         Published facial animation sets
quests/shared/              Series continuity, cast and terminology
characters/                 Character authoring and references
voices/                     Full-reference voice library
tweaks/                     Authored TweakXL records
packaging/                  Native package profiles
work/                       Ignored builds, exports and local evidence
```

## Build and edit

Follow [the authoring guide](docs/authoring.md) for setup, scoped builds and
package creation. Run from this repository with the sibling quest builder compiled:

```powershell
../quest-builder/target/release/ghostline-quest-builder.exe series . --out work/builds --game 'path/to/Cyberpunk 2077'
../quest-builder/target/release/ghostline-quest-builder.exe package packaging/story.json --out work/packages/story --plan
```

The series command compiles ready quests and reports plans separately. It refuses an existing destination. Quest phases, journals, scenes, worlds and localization are generated from their authoring inputs. Character and building resources come from their owning standalone builders. No per-quest generator scripts or copied CR2W templates are build inputs.

Generated resources and diagnostic evidence belong in ignored `work/`. Native readback does not establish in-game behavior.
