# softlife — notes for AI coding agents

One HTML file: markup, inline CSS and inline scripts; GSAP with ScrollTrigger and SplitText, Lenis smooth scroll, all from jsDelivr. No build step, no framework.

## Files
Work from the files: a page read through a link comes back as a summary, and a page rebuilt from it would differ.
```bash
curl -LO https://raw.githubusercontent.com/8bsite/community-website-template/main/index.html
curl -LO https://raw.githubusercontent.com/8bsite/community-website-template/main/AGENTS.md
curl -LO https://raw.githubusercontent.com/8bsite/community-website-template/main/LICENSE
curl -LO https://raw.githubusercontent.com/8bsite/community-website-template/main/CREDITS.md
```
In Windows PowerShell type `curl.exe`. Publish `index.html` with LICENSE and CREDITS.md; this file, README.md and `previews/` are not part of the site.

## Do not break
- Keep it one file unless the user asks otherwise; no framework or bundler for copy, colour or photo changes.
- Keep the ids and the `data-8b-section` / `data-8b-motion` attributes. Each section has its styles in `<style data-8b-part="section:<id>">` and its animation, if any, in `<script data-8b-part="scene:<id>">`.
- The scripts find these classes and attributes; when you change a section's markup, keep them or update the script:
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
- Colours, fonts, radii and shadows are CSS variables in the `:root` block (`data-8b-part="tokens"`); change them there and keep body text at 4.5:1 contrast or more.
- Animations run only when the visitor allows motion (`prefers-reduced-motion: no-preference`); the page must stay readable without them.
- A display line with `style="--len:N"` is sized to fill its width: N is its number of characters, spaces included (`Rest responsibly.` → 17, `Join the club` → 13).
- These neighbouring sections animate across their border: hero → manifesto, letter → membership. Keep each pair next to each other, or that transition switches off.
- Keep the header comment and `<meta name="generator">`; the "Design: 8B" footer link is optional.

## Replace before publishing
- Everything marked `data-8b-placeholder` (og-image, favicon, email, phone, form, social); remove the attribute once the real value is in. With no real value: no preview image — delete the `og:image` tag and set `twitter:card` to `summary`; no phone, email or address — remove that link or row.
- Join / Become a member buttons in the nav, the hero and the phone menu: link to #membership now; point them to your sign-up or application page, or keep the anchor.
- Book a day / Become a member / Apply buttons on the membership cards: link to #contact now; point them to the sign-up, booking or payment URL of each tier.
- Add to bag buttons in the shop (edit): link to nowhere (plain buttons) now; point them to your shop's product or checkout pages (as links), or remove the shop section.
- All notes and Read the note links in journal: link to #journal now; point them to your blog index and the article URLs.
- Newsletter link in the footer: link to #contact now; point them to your newsletter sign-up URL.
- Privacy and Terms links in the footer: link to #footer now; point them to your privacy policy and terms pages.
- **The form sends nothing.** `section-script:contact` checks the fields and shows a thank-you message without sending. Pick one:
  - Formspree: set `action="https://formspree.io/f/<id>"` on the form; in the script, before the thank-you message, `await fetch(form.action, { method: 'POST', body: new FormData(form), headers: { Accept: 'application/json' } })` and show it only if the response is ok.
  - Netlify Forms (site on Netlify): add `name="contact" data-netlify="true"` and `<input type="hidden" name="form-name" value="contact">`; send with `fetch('/', { method: 'POST', headers: { 'Content-Type': 'application/x-www-form-urlencoded' }, body: new URLSearchParams(new FormData(form)) })`.
  - No form service: remove the `<form>` together with the script that handles it (it would fail without the form) and keep the email link.
- Invented demo facts (ask the user for the real ones; do not make up prices, dates or addresses):
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
- `<title>`, the meta description and the og tags; photos (Unsplash, see CREDITS.md) when the user has their own.

## Notes
- The hero wordmark is split into spans so each half can move; the sparkle over the i is a separate span. For a new name, edit the visible spans and the screen-reader text in the h1, and update --len.
- The palette chips in the hero, the week's swatches and the club and card colours come from the CSS variables in :root: recolour there.
- The shop's sticky stage runs only from 1024 px wide; smaller screens show a static mosaic and list.
- Without JavaScript the phone menu button cannot open the overlay; the links stay reachable in the hero and the footer.
- The Add to bag buttons and the journal links go nowhere: connect them to a shop and to articles, or remove them.

## Common edits
- Rebrand: search the old name (`softlife`) in any letter case and replace every match; change the favicon letter and colours in `<link rel="icon">`.
- Photos: replace `src` and delete `srcset` and `sizes` (they list Unsplash sizes), keep `width`/`height` to the new photo's ratio, update `alt` and CREDITS.md.
- Remove a section: delete its markup, its `section:<id>` and `scene-style:<id>` styles, its `scene:<id>` and `section-script:<id>` scripts, and links to `#<id>`.
- Native scroll instead of smooth scroll: delete the Lenis block in `page-init` and the Lenis `<script>` tag.

## Check and publish
- Open the page at 375 and 1440 px, with reduced motion on, with the console open.
- Search `data-8b-placeholder` and the old name: nothing should be left but class names.
