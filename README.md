# HELLO — a short film

Website for *HELLO*, a four-minute comedy written and directed by Wesley Lucas.
Point Park University · Cinema Arts · Production 2 · Fall 2026

> A man is locked out of his apartment. The locksmith needs to be satisfied
> that it is emotionally his.

**Live at [form4b.com](https://form4b.com)**

## The idea

The film is about a man forced to prove he belongs somewhere he already lives.
So the site does the same thing to you.

You can't read it until you complete a residency assessment. You are always
denied, and denial grants *provisional access* — the site opens, but a stamped
bar follows you down the page, and your failed assessment is filed in Section I
and quoted back at you.

Details that make it work:

- **An applicant number** is assigned on arrival and persists across visits.
- **The bureaucracy remembers.** Second visit reads `SECOND APPLICATION —
  previous application denied`. By the fourth, `this frequency has been noted`.
  By the eighth, `file flagged for review`.
- **Questions escalate.** Answering reveals follow-ups, and the follow-up text
  changes based on what you said. Claim it's yours and it asks how long you've
  been certain; name someone else and it asks you to spell it as it appears on
  the lease.
- **Denials vary** by your answers, so two people who compare notes were
  rejected for different reasons.

## Structure

```
index.html            the entire site — markup, styles, and script in one file
CNAME                 custom domain for GitHub Pages
.claude/launch.json   local dev server config
```

No build step, no dependencies. Typography loads from Google Fonts
(Courier Prime, Zilla Slab, Archivo); everything else is self-contained.

## Two things not to break

**The gate is armed by JavaScript, not baked into the markup.** The site is
visible by default; JS adds `.gated` to `<body>` to hide it behind the door.
If the script fails or is disabled, visitors get the full site instead of a
locked door. Never invert this.

**Submit unlocks on the three core answers only** (`q1`, `q2`, `q7`), not on
the follow-ups, and a 45-second timer force-reveals the remaining questions.
Both exist so a stalled reveal chain can't strand someone inside the gate.

`localStorage` is wrapped in try/catch with an in-memory fallback — it throws
outright in some private-browsing modes.

## Working on it

Open `index.html` in a browser, or serve it for real (the gate needs a proper
origin, since `localStorage` is unavailable on `file://` and `data:` URLs):

```bash
python -m http.server 4173
```

To replay a first visit, clear the `f4b.applicant` and `f4b.applications`
keys in localStorage.

## Deploying

Pushes to `main` deploy to GitHub Pages automatically, usually within a minute.

```bash
git add -A && git commit -m "your message" && git push
```

## To do

- [ ] Crew: cinematographer, editor / sound design, location sound
- [ ] Poster or still, wired up as `og:image` for link previews
- [ ] Rewrite Section V in Wesley's own words — currently a draft
- [ ] Fill in Section VI as documents exist (shot list, lookbook, scouts)
- [ ] Trailer embed once there's a cut
- [ ] Keep the Section IV status checklist current
