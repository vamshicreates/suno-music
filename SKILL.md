---
name: suno-music
description: Describe the song you want and get original lyrics plus the complete Suno v6 setup to paste and press Create: style prompt, exclude styles, sliders and model. Tuned for Telugu and Hindi.
---

# Suno Music

Describe the song you want — "a Telugu devotional song for Lord Venkateswara, female voice, calm" — and this skill writes original lyrics and gives the complete Suno setup. Reply with ONE paste-ready block set, in the exact order of Suno's Create form, so they copy each box and press Create. No essay before it; at most one line of framing, and a short "after generating" section at the end.

## How Suno v6 works (verified Nov 2026)

- Models: **v6** (Pro/Premier, most control, default pick for finished songs), **v6-wild** (experimental, drifts from prompt; only for unusual fusion), **v6-mini** (fast drafts). All generate up to 8 min per take. 10 credits = 2 songs.
- Use **Advanced / Custom** mode, never Simple, when lyrics are given.
- Fields: Title (~100 chars), **Styles** (1,000 chars), **Lyrics** (5,000 chars), **Exclude Styles** (1,000 chars) under More Options, plus Vocal Gender, Duration (Auto/Custom), **Max Mode**, **Weirdness** (Safe↔Chaos, 50 = normal), **Style Influence** (Loose↔Strong, default 50%), **Variety** (5 steps, default Normal; it REWRITES the style prompt — set Off), Personalize/My Taste, Persona.
- Count characters as code points (Python `len(str)`), never `wc -m` in a C locale — Devanagari/Telugu are 3 bytes per character, so byte counts come out ~2-3× too high.
- v6 reads section cues in the lyrics and uses them. Bracket tags are hints, not commands.
- Negatives in Styles backfire ("no autotune" can add autotune). Every "don't want" goes in Exclude Styles only.
- Avoid artist names and words that look like artist names in Styles; describe the sound instead.
- Max Mode: more credits, better consistency; use for songs over 2 min and the take you intend to keep.
- Remaster (Subtle/Normal/High) polishes sound, mix and pronunciation without changing the song. Cover changes voice or style. Song Editor → Edit Lyrics / Replace Section fixes one bad word or line. Personas save a voice+style for reuse across a series. Stems are available for mixing.

## Step 1 — Read the request

Pull out: song or theme, language (Hindi / Telugu / mixed), voice (male / female / duet / chorus), mood and energy, use (devotional, film, reel, folk, party), and length. If something is missing, pick the obvious default and say so in one line rather than asking.

## Step 2 — Lyrics

- **Traditional/public-domain text** (Hanuman Chalisa, Annamacharya, Tyagaraja, Vemana, Kabir, Tulsidas, stotras): Suno's lyric checker blocks well-known texts even when they are public domain ("Your lyrics contain copyrighted material"). Suno's policy is that you only enter lyrics you wrote yourself. So by default, write an ORIGINAL devotional song on the same deity or theme, and say why in one line. If the user still wants the exact traditional text, give an instrumental-only Suno prompt (backing track) so they or a singer can record the vocals over it. Never suggest misspellings or homophone swaps to get past the checker.
- **User's own lyrics**: use them as given; only add section tags and pronunciation fixes, and list any change you made.
- **No lyrics given (the default)**: write original lyrics from the description: fresh, singable lines (short lines, open vowels at line ends, a chorus that differs from the verses on paper), in the requested language and script.
- **Copyrighted film or album songs**: do not reproduce the lyrics. Offer an original song in that mood or style instead.
- **Script**: Hindi in Devanagari (Suno handles it reasonably); Telugu in Telugu script (తెలుగు). Mixed Hindi-English or Telugu-English: native script for the native-language lines, English in Latin. If a word comes out wrong, the fallback is a phonetic Latin spelling of that word only, then fix it with Edit Lyrics.
- **Structure**: every section starts with a short bracket tag that also carries its performance cue, for example `[Verse 2: bigger, chorus doubles line endings]`. Keep cues consistent with the Styles text. Repeat the refrain/chorus as written text. Finish with an `[End: …]` tag so the last line isn't cut off and the outro doesn't run long.
- Long texts: if over 5,000 characters, split the lyrics into Part 1 (Create) and Part 2 (Extend from the end of Part 1 with the remaining lyrics and the same Styles).

## Step 3 — Styles (≤1,000 chars, aim for 700–950)

Write in this order, as short descriptive phrases, front-loading what matters most:
1. Genre and sub-genre + "singing in Hindi/Telugu" with diction (e.g. clear Awadhi diction, clear Telugu diction)
2. Lead vocal: gender, register, placement ("front and centre, close-miked"), and performance verbs (holds, pushes, breathes, pulls back); then chorus or backing
3. BPM as a number
4. Arrangement arc: intro → verse → chorus → bridge → ending, naming 3–5 real instruments and what each does
5. Production: "polished modern studio production, wide stereo, vocal clear above the band, clean loud master"
6. The ending

Never put negatives, artist names or slider values in Styles.

### Tag banks

**Hindi**: Bollywood / filmi, Hindi pop, Hindi devotional bhajan, aarti, Sufi qawwali, ghazal, Hindustani classical fusion, Punjabi bhangra. Instruments: dhol, dholak, tabla, harmonium, tanpura drone, sitar, sarangi, shehnai, bansuri, santoor, manjira, conch, temple bells.

**Telugu**: Tollywood film song, Telugu melody (romantic), Tollywood mass number, Telugu folk / janapadam, teenmaar dappu beat, Telugu devotional, Carnatic-inspired kriti/keertana, bhajana. Instruments: mridangam, ghatam, kanjira, thavil, nadaswaram, veena, venu flute, violin (Carnatic), dappu, urumi, tabla, harmonium.

**Devotional rule**: the vocal leads, the refrain repeats, the build is prayer-like, and the ending is resolved. Don't pile on EDM, orchestral and folk all at once.

## Step 4 — Exclude Styles

List up to 10 things as comma-separated nouns: the opposite gender, autotune, rap or spoken word unless wanted, EDM drop or trap hi-hats for traditional songs, lo-fi, muffled vocals, humming intro, English lyrics (for single-language songs).

## Step 5 — Settings

| Setting | Default | Change when |
|---|---|---|
| Model | v6 | v6-wild for experimental fusion; v6-mini only for quick drafts |
| Mode | Advanced / Custom | — |
| Vocal Gender | as requested | leave unset for duets or choirs |
| Variety | Off (0) | raise only to explore new directions |
| Style Influence | 75% | 85%+ if it drifts from the genre; 50% to let it improvise |
| Weirdness | 30% | 50% for pop/film; 20% for strict devotional |
| Max Mode | On | Off for quick tests under 2 min |
| Duration | Auto | Custom for reel-length cuts |
| Persona | none | pick the series Persona once one exists |

The slider numbers are tested community starting points, not official Suno values. Say so once.

## Output format (always exactly this)

```
**Model recommendation / setup:** v6 · Advanced · Max Mode On
**Title:** <title>
**Styles** (<n>/1000):
<code block>
**Exclude Styles** (<n>/1000):
<code block>
**More Options:** Vocal Gender <x> · Variety Off · Style Influence <x>% · Weirdness <x>% · Duration Auto · Max Mode On
**Lyrics** (<n>/5000):
<code block>
**After generating:** 3–5 short bullets
```

Before replying, count every field with Python `len()` and report the numbers.

## After generating (include the relevant bullets)

- Listen to both takes, and run 2–3 generations before judging: takes vary more than small prompt edits do.
- Wrong word → Song Editor → select that line → Edit Lyrics with the corrected spelling (phonetic Latin if the script version fails).
- Good song but thin sound → Remaster (Subtle); unclear diction → Remaster (Normal).
- Voice you love → Make Persona (set it private) and reuse it for the series.
- For video edits → download stems.
- Always have a fluent speaker check pronunciation before release.
