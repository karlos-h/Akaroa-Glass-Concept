<div align="center">

<img src="assets/logo.svg" width="88" alt="Akaroa Glass and Glazing logo: a roofline over a four-light window pane">

# Akaroa Glass and Glazing website (concept)

**Home is where the glass is.**

</div>

---

A website concept I built for a client, Akaroa Glass and Glazing, a glazier in Akaroa covering Banks Peninsula and greater Christchurch. It shows how their site could look and work. This is a concept build only and is not a live site.

Built with plain HTML, CSS and vanilla JavaScript. There's no framework, build step, dependency or backend, so it runs on any static host.

> [!NOTE]
> Concept only. Every phone number, email address, testimonial and photo on the page is a placeholder.

## What I focused on

- A mobile-first layout with breakpoints at 40em, 60em and 80em
- WCAG AA contrast or better on every text and background pairing, with the measured ratios documented
- A page that still works with JavaScript turned off
- Te reo Māori terms marked up with `lang="mi"` and explained in plain English on first use

## Running it

Either open `index.html` straight in a browser, or serve the folder:

```bash
python -m http.server 5173
```

Then visit <http://localhost:5173>. There is nothing to install and nothing to compile.

## Layout

```
index.html          single page, eight sections; launch checklist in a comment at the top
css/styles.css      mobile-first; breakpoints at 40em / 60em / 80em
js/main.js          progressive enhancement only
assets/logo.svg     logo mark (also inlined in the page header and footer)
images/             only README.txt so far, naming the four photos still needed
.claude/launch.json dev server config for the Claude Code preview
```

## Design

| Role | Name | Hex |
|---|---|---|
| Primary | Harbour Deep | `#1B4350` |
| Secondary | Peninsula Green | `#556B4A` |
| Accent | Glass Aqua | `#8FC7C7` |
| Warm neutral | Driftwood Sand | `#DCCBA6` |
| Text | Basalt Charcoal | `#2A2926` |
| Background | Cloud White | `#F8F6F1` |

Headings are **Fraunces**, body is **Public Sans**, both from Google Fonts.

> [!WARNING]
> Glass Aqua is **1.7:1** against Cloud White. It must never be used for text or focus indicators on a light background. On light backgrounds it is confined to underlines, rules and fills; link text there is Harbour Deep. Every other pairing in use is AA or better, with measured ratios documented in the header comment of `css/styles.css`.

## Accessibility

Verified, not assumed:

- WCAG AA or better on every text/background pairing in use
- No horizontal overflow at 320, 375, 768 or 1280 pixels
- Single `h1`, correct heading order, landmark elements, every section labelled
- Skip link, visible focus rings, Escape closes the mobile nav and returns focus
- Works with JavaScript disabled: the nav stays expanded and the form shows a `<noscript>` message pointing at the phone number
- `lang="mi"` on te reo Māori terms, each glossed in plain English on first use

## What a real launch would need

Tracked under **Unreleased** in [CHANGELOG.md](CHANGELOG.md). The short version:

- [ ] Real phone number: replace `027 000 0000` and the `tel:+64270000000` hrefs
- [ ] Real email: confirm `johnny@akaroaglass.co.nz`
- [ ] Real testimonials: three placeholders are visibly flagged in the page
- [ ] Real photographs: four of them, named in [`images/README.txt`](images/README.txt)
- [ ] Connect the quote form to a handler; it currently says plainly that it isn't connected
- [ ] Build `about.html`, `services.html`, `gallery.html`, `contact.html`
- [ ] Favicon set and an `og:image`

The placeholder phone number and email also appear in `js/main.js`, not just `index.html`.

## Branches

| Branch | Purpose |
|---|---|
| `main` | Released state. Only receives merges from `develop`. |
| `develop` | Integration branch. Day-to-day work happens here. |

Commits follow [Conventional Commits](https://www.conventionalcommits.org/). Releases are tagged `vMAJOR.MINOR.PATCH` and recorded in the changelog.

## Licence

All rights reserved, see [LICENSE](LICENSE). This is a client concept, not open source.
