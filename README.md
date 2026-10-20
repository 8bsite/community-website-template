# Free HTML community website template with GSAP scroll animations — softlife

**Community and members' club website for a women's social house: a free HTML template in one file, with GSAP scroll animations, no build step, MIT license. Made by [8B](https://8b.com/), the AI website builder.**

[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE) ![one HTML file: no build](https://img.shields.io/badge/one%20HTML%20file-no%20build-orange) ![GSAP: ScrollTrigger](https://img.shields.io/badge/GSAP-ScrollTrigger-88ce02)

**[Live demo](https://8bsite.github.io/community-website-template/)** · **[Use this template](https://github.com/new?template_name=community-website-template&template_owner=8bsite)** · **[Download ZIP](https://github.com/8bsite/community-website-template/archive/refs/heads/main.zip)** · **[Template page on 8b.com](https://8b.com/templates/softlife/)**

<a href="https://8bsite.github.io/community-website-template/"><img src="previews/desktop.png" alt="softlife, a free HTML template: first screen on a desktop" width="76.1%"></a> <a href="https://8bsite.github.io/community-website-template/"><img src="previews/phone.png" alt="softlife, a free HTML template: first screen on a phone" width="21.9%"></a>

<p align="center"><a href="https://8bsite.github.io/community-website-template/"><img src="previews/scroll.gif" alt="softlife, a free HTML template: scrolling through the first sections on a desktop" width="40%"></a><br><sub>Scroll animation</sub></p>

A one-page site for a London members' house for ambitious women, with a weekly programme, clubs, a small shop, a journal and three membership tiers. Warm pinks, oxblood and powder blue, a two-weight serif and arch-shaped photos; as you scroll, a pink-and-red palette row swells into the next section, seven colour arches turn into the week's photos, a moodboard deals itself out of a pile and membership cards turn over.

Good for: members' club or social house; women's network or community; wellness or lifestyle collective; co-working space with events; community with a weekly programme and paid tiers.

## Use it with an AI coding agent

Download the files into your project (in Windows PowerShell type `curl.exe`):

```bash
curl -LO https://raw.githubusercontent.com/8bsite/community-website-template/main/index.html
curl -LO https://raw.githubusercontent.com/8bsite/community-website-template/main/AGENTS.md
curl -LO https://raw.githubusercontent.com/8bsite/community-website-template/main/LICENSE
curl -LO https://raw.githubusercontent.com/8bsite/community-website-template/main/CREDITS.md
```

Then give your agent this prompt:

```text
Read AGENTS.md, then edit index.html. Use this template as the base for a site for a community or members' club for <your community: who it is for, where it meets, what happens each week, membership prices, how to join>. Keep the layout, the motion and the single-file format; replace the brand name, copy, photos, programme, prices, links and contacts, and recolour it through the CSS variables if needed.
```

Give the agent the downloaded file, not a link: from a link it would rebuild a different page. No agent? Click **[Use this template](https://github.com/new?template_name=community-website-template&template_owner=8bsite)**, edit `index.html` and turn on **Settings → Pages**.

## What's on the page

- **Navigation** — top bar: wordmark, section links, Join button; phone menu overlay
- **softlife l ı fe** — first screen: width-filling two-weight wordmark, tagline, intro, two buttons, portrait, a row of palette chips
- **The softlife principle** — statement on an oxblood ground: the principle in two weights, a founding note and a link
- **A week, softly** — weekly programme: seven days as seven arch photos, one colour per day
- **Four clubs, one house** — four tiles with a giant initial each: the clubs or programmes (demo: morning, supper, reading, office hours)
- **Things we're soft on** — moodboard collage of twelve tiles: photos, type posters, gingham and stripes
- **The soft edit** — small shop: four products with photo, details, price and Add to bag
- **Notes from the reading room** — blog: a tall pink poster of two words beside three article entries
- **Dear you,** — founder's letter with a handwritten signature and an arch portrait
- **Join the club** — three membership tiers on cards that turn over (demo: day pass, member, founding circle)
- **Good questions** — questions and answers (native &lt;details&gt;) beside a heading and an email link
- **Come over** — address, hours, email, phone and a contact form beside an arch photo of the front door
- **Footer** — width-filling softlife wordmark, address, hours, contacts, links, copyright and the Design: 8B credit

## Design

Palette: ![#fcf8f3](https://img.shields.io/badge/-%23fcf8f3-fcf8f3?style=flat-square) ![#720808](https://img.shields.io/badge/-%23720808-720808?style=flat-square) ![#a10728](https://img.shields.io/badge/-%23a10728-a10728?style=flat-square) ![#fec6d3](https://img.shields.io/badge/-%23fec6d3-fec6d3?style=flat-square) ![#f6e6e5](https://img.shields.io/badge/-%23f6e6e5-f6e6e5?style=flat-square) ![#bad4ed](https://img.shields.io/badge/-%23bad4ed-bad4ed?style=flat-square) ![#dae9f7](https://img.shields.io/badge/-%23dae9f7-dae9f7?style=flat-square) ![#efe4d8](https://img.shields.io/badge/-%23efe4d8-efe4d8?style=flat-square)  
Fonts: Kalnia, Onest, Playwrite US Trad (Google Fonts). Change both through the CSS variables in the `:root` block at the top of `<head>`. A big display line with `style="--len:N"` fills its width: set N to its new number of characters.

- The hero wordmark is split into spans so each half can move; the sparkle over the i is a separate span. For a new name, edit the visible spans and the screen-reader text in the h1, and update --len.
- The palette chips in the hero, the week's swatches and the club and card colours come from the CSS variables in :root: recolour there.

## Before you publish

- Replace everything marked `data-8b-placeholder` (social preview image, favicon, email, phone, form, social) and the invented demo facts: prices, dates, address. [AGENTS.md](AGENTS.md) lists them.
- The form sends nothing yet: connect it to Formspree or Netlify Forms, or remove it.

## Tech

GSAP 3.13.0, ScrollTrigger, SplitText, Lenis 1.3.11 from jsDelivr, 132 KB, no build step. Chrome and Edge 111+, Safari 16.2+, Firefox 121+ (it uses color-mix(), container query units, :has(), cascade layers, small/dynamic viewport units). With "reduce motion" on, the page is complete and still.

## License

MIT, see [LICENSE](LICENSE). Photos, fonts and libraries keep their own licences: [CREDITS.md](CREDITS.md). More free templates: [8b.com/templates](https://8b.com/templates/) · [github.com/8bsite](https://github.com/8bsite).
