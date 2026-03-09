# Thai Memes CC

Thai meme sound effects for [Claude Code](https://docs.anthropic.com/en/docs/claude-code).

## Sound Categories

Each sound pack contains sounds for these events:

| Category | Trigger |
|----------|---------|
| `session-start` | When Claude Code starts |
| `task-acknowledge` | When you submit a prompt |
| `task-complete` | When Claude finishes a task |
| `error` | On errors |
| `permission` | On permission requests |

## Adding Sound Packs

Create a new directory under `sounds/` with your pack name:

```
sounds/
└── my-pack/
    ├── session-start/
    ├── task-acknowledge/
    ├── task-complete/
    ├── error/
    └── permission/
```

Add `.mp3`, `.wav`, or `.ogg` files to each category folder. Then switch:

```
/thai-memes pack my-pack
```

## CLI

```bash
thai-memes switch [pack]    # interactive picker or direct switch
thai-memes list             # show all packs
thai-memes volume 0.3       # set volume (0.0-1.0)
thai-memes test task-complete  # play a test sound
thai-memes status           # current config
```

## Platform Support

- **macOS**: `afplay` (built-in)
- **Linux**: `paplay` (PulseAudio), `pw-play` (PipeWire), or `ffplay` (FFmpeg)
