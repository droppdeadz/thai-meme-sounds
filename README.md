# Thai Memes CC

Thai meme sound effects for [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

## Install

### Option A: Inside Claude Code (easiest)

1. Type `/plugin` in Claude Code
2. Enter `droppdeadz/thai-meme-sounds` as marketplace source
3. Select **thai-memes** and install
4. Restart Claude Code

### Option B: Terminal

```bash
claude plugin marketplace add droppdeadz/thai-meme-sounds
claude plugin install thai-memes@droppdeadz
```

### Option C: Git clone

```bash
git clone https://github.com/droppdeadz/thai-meme-sounds.git ~/.claude/plugins/thai-memes
```

Then restart Claude Code.

## Sound Packs

| Pack | Sounds |
|------|--------|
| **khom** (default) | ez kids, more harder, lets go, smell bad, stab, i sus, please don't, ubah, slap, this is my ways, u know me?, thuy, want more |
| **master daeng (NSFW)** | say hello, for what, u cool?, u good?, khaeng, hom, tell u, lick, shark wow |
| **phiicchaa (NSFW)** | phiicchaa jaaa, nam ja taek, ah ah ah, mai wai laew haaaaa, ouyyy, mai hai taek, eh, seaw |

## Switch Packs

**From Claude Code:**

```
/thai-memes pack khom
```

**From terminal:**

```bash
thai-memes switch           # interactive picker
thai-memes switch khom      # direct switch
thai-memes list             # show all packs
thai-memes volume 0.3       # set volume (0.0-1.0)
thai-memes test session-start  # play a test sound
thai-memes status           # current config
```

## Sound Categories

Each pack covers these Claude Code events:

| Category | Trigger |
|----------|---------|
| `session-start` | When Claude Code starts |
| `session-end` | When Claude Code session ends |
| `task-acknowledge` | When you submit a prompt |
| `task-complete` | When Claude finishes a task |
| `subagent-start` | When a subagent is launched |
| `error` | On errors |
| `permission` | On permission requests |

## Adding Custom Packs

Create a new directory under `sounds/` with your pack name:

```
sounds/
└── my-pack/
    ├── session-start/
    ├── session-end/
    ├── task-acknowledge/
    ├── task-complete/
    ├── subagent-start/
    ├── error/
    └── permission/
```

Add `.mp3`, `.wav`, or `.ogg` files to each category folder. Then switch:

```
/thai-memes pack my-pack
```

## Platform Support

- **macOS**: `afplay` (built-in)
- **Linux**: `paplay` (PulseAudio), `pw-play` (PipeWire), or `ffplay` (FFmpeg)
