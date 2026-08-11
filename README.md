# HELLO — a short film

Website for *HELLO*, a four-minute comedy written and directed by Wesley Lucas.
Point Park University · Cinema Arts · Production 2 · Fall 2026

> A man is locked out of his apartment. The locksmith needs to be satisfied
> that it is emotionally his.

## The site

A single self-contained page, styled as a municipal residency-assessment form —
the same bureaucratic object the locksmith carries in the film. Visitors can
fill out the assessment themselves, and are denied.

Sections: assessment · synopsis · cast & crew · production status · contact

## Structure

```
index.html    the entire site — markup, styles, and script in one file
```

No build step, no dependencies. Typography loads from Google Fonts
(Courier Prime, Zilla Slab, Archivo); everything else is self-contained.

## Working on it

Open `index.html` in a browser. That's the whole workflow.

## Deploying

Pushes to `main` deploy automatically. To update the site, edit `index.html`,
then:

```bash
git add -A && git commit -m "your message" && git push
```

## To do

- [ ] Crew: cinematographer, editor / sound design, location sound
- [ ] Poster or still, wired up as `og:image` for link previews
- [ ] Trailer embed once there's a cut
- [ ] Keep the Section IV status checklist current
