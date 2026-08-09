# C.H.L.O.E - Completely Helpful Little Operating Entity

A personal study assistant project with real conversation memory, note-taking, searching your own notes, and optional GitHub sync. 100% free, runs on your personal desktop (Google Gemini powered).

# (v2)
- Real conversation memory - Chloe now remembers what you've said earlier in the session. Natural replies like "no thanks" or "tell me more about that" just work, no rigid command syntax required.
- GitHub sync - notes can auto-push to your repo the moment they're saved (optional, off by default until you configure it).
- Spotify playback - "play", "pause", "skip" (needs Spotify Premium).

# (v3)

These all lean on something Siri/Alexa/Google Assistant structurally can't do: reason over your own personal notes and study history, not just answer generically every time.

- Analogy engine - explain now checks your existing notes first, and if something genuinely relates, builds the new explanation as a bridge from what you already understand, instead of a cold generic definition.
- Auto cross-referencing - every time you save a new note, Chloe compares it against your other notes and flags (a) related notes worth linking, and (b) actual contradictions between what you've written.
- Weak-spot tracker - weak spots looks at your logged explain/ search activity over time and points out topics you keep coming back to - a real signal of what didn't stick, not a generic quiz guess.
- Session recap - recap summarizes everything you did that session and appends it to study_journal.md, building a real timeline of your learning over time.
- Readiness check - readiness <topic> gives an honest read on how solid your notes actually are on something, based only on what you've written - not a false-encouragement "you got this!"
- Portfolio summary - portfolio summary drafts a "here's what I've learned" writeup from your note history - handy for a GitHub README, LinkedIn post, or personal changelog.
- Socratic quiz mode - quiz me (or quiz me on <topic>) starts an interactive back-and-forth quiz pulled entirely from your own notes, with feedback after each answer. Say "stop quiz" to end it.
Gentle time-awareness - on startup, Chloe quietly mentions if a topic hasn't been touched in a few weeks, based on your notes' own dates - not a nagging reminder app, just a quiet nudge.
