# Traffic Generation Prompt

**Authors:** rehartley & Claude (Anthropic)

## Overview

This is a hand-practice exercise for decoding OTP-encrypted Morse traffic. It runs as a six-stage pipeline: establish a continuity bible, write Cold War scenarios, write in-character intelligence reports about them, encrypt the reports with a one-time pad, convert the ciphertext to Morse text, then render that Morse as WAV audio.

The OTP tool has been built as a standalone executable at `c:\dev\bin\otp.exe`.

**Work through each stage completely before starting the next.**

## Folder structure

Create these folders under `claude`:

| Folder | Contents |
|---|---|
| `0-continuity-bible` | Master cast, organization, and timeline documents |
| `1-scenario-samples` | Scenario background documents |
| `2-message-cleartext-report` | Plaintext intelligence reports |
| `3-message-text-otp` | OTP-encrypted reports |
| `4-message-text-morse` | Morse-code text of the encrypted reports |
| `5-message-text-morse-audio` | Morse-code WAV audio of the encrypted reports |

## Voice and style (applies to Stages 1 and 2)

- Write as an insider, not an observer: someone who was a participant, ran the operation, or is working from primary sources — not a journalist summarizing events.
- **Name names.** No "journalist sympathetic to...", "NAME REDACTED", "NAMED PERSON 1", or "FOREIGN LEADER 2" placeholders. Redaction only happens after intel officers and analysts have assessed and sanitized raw reporting for wider distribution — this is the raw reporting itself, straight from the field.
- Real historical texture is welcome (e.g., the US placing Pershing missiles in Turkey, and Soviet anxiety over US expansion into European affairs post-WWII feeding into the Cuban Missile Crisis), but so is invention. Feel free to fabricate names, events, or details a real participant might know but the public wouldn't.
- Playful, over-the-top conspiracy theories are fair game for flavor — e.g., "the Australian PM presumed lost at sea in 1967 actually swam out to board a Chinese submersible, tipped off that the CIA was coming for him and MI6 planned to replace him with a body double." Keep it grounded in Cold War tradecraft, though — no homing shark torpedoes, no killer lipstick.
- Let tone track the geopolitical mood of the era: brash confidence in the early Kennedy years, weary caution through 1970s détente, a jump back to sharp paranoia in the early Reagan years, and the first cracks of openness creeping in by the mid-1980s.

## Continuity requirements (applies to Stages 0–2)

This is meant to read as one continuous world, not ten disconnected vignettes, so:

- **Codenames, not real names, in the field.** Handlers and reports refer to agents by codename (e.g. STARLING); the mapping from codename to real identity lives only in the continuity bible, not spelled out in the traffic itself.
- **Recurring cast.** Each scenario after the first should carry forward at least two or three characters, or one organization/front, from an earlier scenario — aged appropriately, and in a different position than we last saw them.
- **Handlers have arcs too.** The people receiving the dead drops aren't a faceless mailbox — give them careers, marriages, burnout, and their own chance to be compromised over the decades.
- **Double and triple agents.** At least a few recurring characters should eventually be revealed as playing more sides than the reader (or the handler) initially believes.
- **Comms discipline has consequences.** A missed scheduled contact should sometimes mean the next report opens under the shadow of "did they think I was blown."
- **Burned covers force reinvention.** A character can resurface later under a new identity or codename — reconcile this in the bible so it reads as a reveal, not a continuity error.
- **Cryptic callbacks are encouraged.** A later report can reference an earlier event in shorthand ("as I warned you after Vienna...") without re-explaining it — reward readers following the whole arc.

## Stage 0 — Continuity bible

**Goal:** before writing any scenarios, establish the shared reference documents that keep ten independently-drafted scenarios consistent with each other. Update these documents after finishing each scenario in Stage 1, before starting the next.

**`continuity-bible.md`** — a running master cast and organization list. For each character: name, codename(s)/aliases, era of birth, nationality, agency/affiliation, role, key relationships, and current status (alive / dead / captured / turned / retired / unknown), updated as of the most recent scenario touching them. For each organization or front: name, type, cover story, who really controls it, and current status.

**`timeline.md`** — a single chronology interleaving real Cold War anchor events (e.g. the Cuban Missile Crisis, Prague Spring, the Helsinki Accords, Able Archer 83) with the invented events from your scenarios, so later scenarios can be placed accurately relative to earlier ones.

**Output:** `continuity-bible.md`, `timeline.md` in `0-continuity-bible`.

## Stage 1 — Scenario samples

**Goal:** ten plausible Cold War scenarios to serve as background material for Stage 2's reports.

**Setting:** early 1960s to mid-1980s. One side of each scenario should be the USSR or a Soviet interest.

**Each scenario needs:**
- A short **cast list block** at the top: name, codename, affiliation, status, and a one-line link back to the continuity bible for anyone who's appeared before.
- Locations and a timeline of events.
- A cast of characters — not just people, but organizations, corporations, governments, agencies, and wealthy patrons — with names, roles, relationships, driving beliefs, key virtues/flaws, and shared history. The goal is that when reports from different scenarios cross paths later, the reader understands *why*.
- The insider voice and named-names rule from [Voice and style](#voice-and-style-applies-to-stages-1-and-2) above, and the recurring-cast, codename, and callback rules from [Continuity requirements](#continuity-requirements-applies-to-stages-0-2) above.
- Characters can progress across the decades — early 20s in the '60s, 50s by the '80s. Let them finish school, marry, join the army, have and lose children — the normal texture of a life.
- The reporters are not stoic. Show them calm, cool, and collected at the start, then let more distinct personality traits emerge over time as their personal vices and virtues intensify and their composure strains to hold. These are deep-cover people, so it shouldn't be surprising if their controllers start to wonder whether they're going native, going corrupt, or have simply spent so long maintaining the cover and hiding their true selves that no one — themselves included — can tell anymore whether they've turned and their handlers are being played.
- Since they're Russian, their command of English should be adequate but initially interspersed with plenty of Russian — in Cyrillic or transliteration, things like "glupaya korova!" — evolving over time toward better English that's more to the point.
- The reports should get denser with time. The first one has less information but uses substantial, expansive words to fill it out. Because encryption is so painful, later messages favor shorter words to cut down on letters to encrypt. Later still, the phrasing turns more natural again once the agent gets hold of a cipher device — mid-to-late 1970s — that handles the OTP process for them in BASIC (more on that later).
- We need to kill off some characters to make it more real, but some of them are not dead — come back on the other side.
- Some characters get captured; some of those escape.

**Format:** up to 10,000 words per scenario; bullet/point form is fine.

**Output:** `scenario-01.txt`, `scenario-02.txt`, ... in `1-scenario-samples`.

## Stage 2 — Cleartext intelligence reports

**Goal:** for each scenario, write a short dead-drop intelligence report as if from a Soviet agent working for the West. Rotate the handling agency across reports — MI6, CIA, Mossad, ASIS, and allied European/Asian services.

**Voice:** the insider voice and named-names rule from [Voice and style](#voice-and-style-applies-to-stages-1-and-2) above, the codename and callback rules from [Continuity requirements](#continuity-requirements-applies-to-stages-0-2) above, plus:- Mix Roman and Cyrillic script, including for names and places.
- Weave in Russian words and phrases to sell the atmosphere — think of figures like Alexandr Ogorodnik, a real Russian source who worked for the CIA.
- Occasionally, if the reporter is especially tense, it can all be in Russian, with an English *"I sorry, very ascared"*, or busy or whatever explains the need for haste.  Could be heading off to honeymoon.  Whatever.

**Length:** target **~1020 characters** — enough to nearly (but not fully) exhaust the `Trianon-001.otk` key's capacity, which is roughly the size of `loremipsum.txt`. Undershooting is safer than running over. (Earlier drafts landed around 300 characters — too short.)

**Character set** — the report may use only:

```
ABCDEFGHIJKLMNOPQRSTUVWXYZ?:@/~#.,
0123456789АБВГДЕЖЗИЙКЛМНОПРСТУФХЦЧШЩЫЬЭЮЯ
```
plus the space " " and newline character `\n`.

- **Never use `#` or `~`** — they're reserved control codes (digit-shift and alphabet-shift, respectively).
- Everything will be capitalized on read-in (Morse has no lowercase), so don't rely on case for meaning.
- A newline after a sentence-ending `.` is allowed where it reads as a paragraph break — this lets you form a quote block, e.g.:

  ```
  "Ivan Ivanovitch refused our offer:
  I will never work for CIA, those lying curvas.

  "
  ```

**Output:** `report-01-01.txt` (scenario 01, report 01), `report-01-02.txt`, etc., in `2-message-cleartext-report`.

## Stage 3 — OTP encryption

Encrypt each report, retaining the key used:

```
otp -k -z -e -i report-01-01.txt -o report-01-01.otp trianon-01.otk
```

Repeat for every report.

**Output:** `report-01-01.otp`, etc., in `3-message-text-otp`.

## Stage 4 — Morse text

For each `*.otp` file, read it line by line and transliterate it into Morse code text.

**Output:** `report-01-01.otp.txt`, etc., in `4-message-text-morse`.

## Stage 5 — Morse audio

For each `*.otp` file, read it line by line and render it as Morse code audio:

- **Timing/tone:** 13 WPM, 700 Hz.
- **Format:** WAV, 8 kHz, 8-bit, mono PCM (keeps files small while staying broadly Windows-compatible).
- **Playback:** each line plays twice, with a half-second pause between repetitions.

**Output:** `report-01-01.wav`, etc., in `5-message-text-morse-audio`.
