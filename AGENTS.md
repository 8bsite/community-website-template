# AGENTS.md: community website template

Community and members' club website for a women's social house. One file, `index.html`, with inline CSS and scripts (GSAP, ScrollTrigger, Lenis from jsDelivr); no build step, and none is needed for copy, colour or photo edits.

## Files
Edit these files, not a page fetched by URL (that arrives as a summary).
```bash
curl -LO https://raw.githubusercontent.com/8bsite/community-website-template/main/index.html
curl -LO https://raw.githubusercontent.com/8bsite/community-website-template/main/AGENTS.md
curl -LO https://raw.githubusercontent.com/8bsite/community-website-template/main/LICENSE
curl -LO https://raw.githubusercontent.com/8bsite/community-website-template/main/CREDITS.md
```
Upload `index.html`, LICENSE and CREDITS.md; not this file, README.md or `previews/`.

## Keep
- Every `id`, `data-8b-section`, `data-8b-motion` and `data-8b-part` (`section:<id>` styles, `scene:<id>` animation).
- Selectors the scripts use:
  - `scene:hero`: `.hero__dome` `.hero__slot` `.hero__word--soft` `.hero__word--life` `.hero__tag` `.hero__group--l` `.hero__group--r` `.hero__photo-frame` `.hero__lede-inner`
  - `scene:manifesto`: `.manifesto__ground` `.hero__slot` `.manifesto__inner` `.manifesto__text`
  - `scene:week`: `.week__day` `.week__frame` `.week__swatch` `.week__title` `.week__note`
  - `scene:board`: `.board__grid` `.board__tile`
  - `scene:edit`: `.edit__shot` `.edit__list` `.edit__slide` `.edit__hold` `.edit__arch`
  - `scene:journal`: `.journal__poster` `.journal__word`
  - `scene:letter`: `.letter__motto`
  - `scene:membership`: `.membership__card` `.membership__title` `.membership__back` `.membership__flip` `.membership__cards`
  - `scene:contact`: `.contact__door` `.contact__leaf--l` `.contact__leaf--r`
  - `section-script:nav`: `.nav__bar` `.nav__toggle` `.menu` `.menu__close`
  - `section-script:contact`: `.contact__form` `.contact__status`
- `hero` directly above `manifesto`, `letter` directly above `membership`: the animation crosses that border and stops if they are split.
- `style="--len:N"` = characters in that display line, spaces included: `Rest responsibly.` is 17, `Join the club` is 13.
- The hero wordmark is split into spans so each half can move; the sparkle over the i is a separate span. For a new name, edit the visible spans and the screen-reader text in the h1, and update --len.
- The palette chips in the hero, the week's swatches and the club and card colours come from the CSS variables in :root: recolour there.
- Colours and fonts are variables in `:root` (`data-8b-part="tokens"`): `--color-1` #fcf8f3 (cream page background), `--color-2` #720808 (text, oxblood ground), `--color-3` #a10728 (crimson headings and buttons), `--color-4` #fec6d3 (pink panels and footer), `--color-5` #f6e6e5 (blush panels), `--color-6` #bad4ed (powder blue tiles, gingham), `--color-7` #dae9f7 (pale blue stripes), `--color-8` #efe4d8 (linen behind arch photos); body text needs 4.5:1 contrast.
- With reduced motion the page must read in full.
- Keep the header comment and `<meta name="generator">`. Keep the "Design: 8B" footer link unless the site owner asks to remove it.

## Replace
- `data-8b-placeholder` (og-image, favicon, email, phone, form, social): real value in, attribute out; no value, remove the row (no image: drop `og:image`, set `twitter:card` to `summary`).
- Join / Become a member buttons in the nav, the hero and the phone menu: now #membership; owner's target: your sign-up or application page, or keep the anchor.
- Book a day / Become a member / Apply buttons on the membership cards: now #contact; owner's target: the sign-up, booking or payment URL of each tier.
- Add to bag buttons in the shop (edit): now nowhere (plain buttons); owner's target: your shop's product or checkout pages (as links), or remove the shop section.
- All notes and Read the note links in journal: now #journal; owner's target: your blog index and the article URLs.
- Newsletter link in the footer: now #contact; owner's target: your newsletter sign-up URL.
- Privacy and Terms links in the footer: now #footer; owner's target: your privacy policy and terms pages.
- The form in `#contact` (fields `name`, `email`, `interest`, `message`) sends nothing; `section-script:contact` validates it and shows the thank-you text. Formspree: `action="https://formspree.io/f/<id>"` and `fetch` POST `new FormData(form)` first. Netlify: `data-netlify="true"` and a hidden `form-name`. Or delete it and the script.
- The name softlife (any letter case); the favicon letter and colours in `<link rel="icon">`.
- Photos (24, Unsplash: hero 1, week 7, board 7, edit 4, journal 3, letter 1, contact 1): `src`, no `srcset`/`sizes`, `width`/`height` to the ratio, `alt`, CREDITS.md.
- `<title>`, meta description, og tags.

## Ask the owner for
All demo text, never to be invented:
- The brand and company: "softlife", "softlife Society Ltd." (footer copyright) and "A members' house in London" (footer, title, meta description, hero).
- Founding year 2019: the hero tagline split as "20" … "19", "Founded in 2019 by Margot Ellery and eleven very tired friends" (manifesto), "I started softlife in 2019" and "Six years on" (letter).
- The founder Margot Ellery: name, signature and portrait (letter), "Read Margot's note" (manifesto).
- Member numbers: "Eight hundred members" (manifesto), "there are eight hundred of us" (letter).
- The address "14 Linden Row, London W11 2QP" (contact, footer) — invented, but the postcode format is real.
- Opening hours "Mon–Fri 7:30–23:00, Sat–Sun 9:00–23:00" (contact, footer).
- Email and phone (replaced with hello@softlife.example and +44 20 0000 0000) (faq, contact, footer).
- The weekly programme with times: Mon 8:00 pilates on a reformer, Tue 10:00 co-working, Wed 20:00 reading room, Thu 19:30 supper club with a guest cook, Fri 18:00 lido swim, Sat 9:00 market, Sun all day (week).
- Club schedules: Morning Club daily 7:30–10:00, Supper Club Thursdays 19:30, Reading Room daily 12:00–23:00, Office Hours weekdays 9:00–18:00 (clubs); "two thousand well-thumbed books" and "Laptops close at six" (clubs).
- Shop products and prices: Sunday silk set £120 (washed silk, S–XL), Slow hour candle £38 ("Burns for sixty slow evenings"), Do-less planner £24 (cloth bound, comes with a gold pen), Petal soak £28 (400 g); "made in small runs", "Poured in the house kitchen" (edit).
- Membership prices and terms: Day pass £25 per visit, Member £85 per month, Founding circle £180 per month, and their perks (bring a friend twice a month, 10% off the shop, a reserved armchair, a weekend away each season, host a supper for twenty) (membership).
- Policies: "No joining fee, no minimum term" (membership, faq), "Cancel any time with thirty days' notice", pausing "for up to three months a year and without a fee", the house "built for women and non-binary people", private suppers "for up to twenty guests", screen-free rooms and a garden (faq).
- Service: "a real person answers within a day" (faq) and "we'll write back within a day" (the form's thank-you message, contact).
- Journal reading times: 6, 4 and 8 min read, and "Twelve books" (journal).
- The colour names of the days (Oxblood, Crimson, Peony, Blush, Baby blue, Powder, Linen) in week match the page's palette: rename them if you recolour the page.

## Known limits
- The shop's sticky stage runs only from 1024 px wide; smaller screens show a static mosaic and list.
- Without JavaScript the phone menu button cannot open the overlay. The hero and the footer still link The week, Membership, the letter, Journal and the newsletter (contact), but Clubs, The board and Shop have no other link on phones.
- The Add to bag buttons and the journal links go nowhere: connect them to a shop and to articles, or remove them.

## Check
375 and 1440 px, reduced motion on, console clean; `data-8b-placeholder` and softlife left only in class names.
