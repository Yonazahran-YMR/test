# C.H.L.O.E - Completely Helpful Little Operating Entity

A personal AI assistant I built from scratch in Python, inspired by
Jarvis from Iron Man. Started as "can I actually build this" curiosity
and turned into a genuinely useful daily study tool. Runs off an
external drive, free to run (Gemini's free API tier), and calls me
"Sir" because why not.

## Why I built this

I wanted something that wasn't just a chatbot. Generic AI tools forget
everything the moment you close the tab. Chloe reads my own notes,
remembers our conversations, and gets smarter about my specific
learning gaps over time, not just general knowledge.

## Core features

**Notes & explaining**
- `note <topic>` writes study notes in my own casual, first-person voice
  and saves them as markdown
- `explain <topic>` gives a quick explanation on demand
- `search <question>` searches through everything I've already written
  and answers using only my own notes, honest about what I haven't
  covered yet instead of guessing

**GitHub integration**
- Notes auto-push straight to this repo the moment they're saved, via
  the GitHub API
- `sync` catches up any notes made before GitHub sync was configured

**Spotify control**
- `play <song>`, `pause`, `skip`, full playback control through
  Spotify's Web API (needs Premium on the account, a real Spotify
  requirement, not a Chloe limitation)

**Real conversation memory**
- Chloe runs on a persistent chat session, so she remembers what I said
  earlier and I can talk to her naturally instead of memorizing exact
  command syntax

**The stuff that makes this different from Siri or Alexa**
This is the part I'm most proud of. None of it works without Chloe
having read/write access to my own notes and study history, which a
generic assistant just doesn't have.
- **Analogy engine.** When explaining something new, she checks my
  existing notes first and bridges the explanation from something I
  already understand instead of starting cold.
- **Auto cross-referencing.** Every new note gets checked against my
  older ones for related connections, and for actual contradictions if
  I misunderstood something earlier and wrote something different later.
- **Weak spot tracking.** She quietly logs what I ask her to explain or
  search, then can point out topics I keep circling back to, which is a
  pretty honest signal of what didn't stick.
- **Session recaps.** `recap` summarizes what I covered and logs it to a
  running study journal, building an actual timeline of my learning.
- **Readiness checks.** `readiness <topic>` gives me an honest read on
  how solid my notes are on something, gaps included, no false
  encouragement.
- **Socratic quiz mode.** `quiz me` runs an interactive back-and-forth
  quiz pulled entirely from my own notes, not generic trivia.
- **Gentle time-awareness.** She quietly flags topics I haven't touched
  in a few weeks, based on my notes' own dates.

## Tech stack

Python for the core script, Google's Gemini API (`gemini-3.5-flash-lite`)
as the actual brain, the GitHub REST API for syncing straight to this
repo, and Spotify's Web API through `spotipy` for playback. Everything
runs locally off an external drive, no server or hosting involved.

## What's next

- Flexible natural-language command understanding (function calling
  instead of exact command prefixes), which is really the groundwork
  before voice can work well
- Voice in and out
- A wake word so I can just say "Hey Chloe"
- Reading my screen when I need help with something visual
- Letting her open applications directly

## Honestly

The GitHub API integration ended up being way easier than I expected,
just HTTP requests and base64 encoding. What actually ate most of my
debugging time was Windows environment variables: `setx` syntax
tripping me up, and VS Code caching old env vars until I fully
restarted it. Way more hours went into that than into any of the
actual AI features.
