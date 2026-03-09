---
name: thai-memes
description: Manage Thai meme sound effects — change volume, switch sound packs, list available sounds
user_invocable: true
---

# /thai-memes — Thai Meme Sound Manager

Manage your Thai meme sound effects for Claude Code.

## Usage

When the user invokes `/thai-memes`, parse their arguments and execute the appropriate action:

### Commands

- `/thai-memes` — Show current config (active pack, volume, enabled events)
- `/thai-memes volume <0.0-1.0>` — Set volume level
- `/thai-memes pack <name>` — Switch active sound pack
- `/thai-memes list` — List available sound packs and their sounds
- `/thai-memes toggle <event>` — Enable/disable a specific event category
- `/thai-memes test [category]` — Play a test sound from the given category (default: session-start)

## Implementation

Read and modify the config file at `$CLAUDE_PLUGIN_ROOT/config.json`.

For **volume**: Update the `volume` field (float 0.0 to 1.0).
For **pack**: Update `active_pack` field. Verify the pack directory exists in `$CLAUDE_PLUGIN_ROOT/sounds/`.
For **toggle**: Flip the boolean in `enabled_events.<event>`.
For **test**: Run `bash $CLAUDE_PLUGIN_ROOT/scripts/play-sound.sh <category>`.
For **list**: Scan `$CLAUDE_PLUGIN_ROOT/sounds/` directories and list packs with file counts.

Use the Bash tool to read/write config.json and the Read tool to display current settings.

### Example responses

**Status**: "🎵 Thai Memes: default pack, volume 0.5, all events enabled"
**Volume change**: "🔊 Volume set to 0.3"
**Pack switch**: "🎵 Switched to my-pack"
