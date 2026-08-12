# DMV City Slickerz — Static Site

A plain HTML/CSS static rebuild of thepublicstitch.com, built to run on GitHub Pages
for $0/month instead of a paid Wix plan. No build step, no framework — just edit the
HTML files directly (in Cowork, or any editor) and push.

## What's here

```
index.html          Home
about.html           About Us
events.html          Events (RECESS + National Harbor)
partnerships.html    Sponsorship tiers
contact.html         Contact form + email
css/style.css        All styling (single stylesheet, uses CSS variables for brand colors)
js/main.js           Mobile nav toggle only
images/              40 real photos from Photos-1-001, web-optimized (full_ = large, thumb_ = gallery-size)
```

Brand colors live at the top of `css/style.css` under `:root` — change `--green`,
`--rust`, `--gold`, `--cream` there to retheme the whole site at once.

## Deploying to GitHub Pages

This repo (`lawrencetotimeh/dmv-city-slickerz`) is already live on GitHub. To turn
on Pages hosting:

1. In the repo: **Settings → Pages → Source → Deploy from a branch → main / (root)**.
2. GitHub gives you a URL like `https://lawrencetotimeh.github.io/dmv-city-slickerz/`
   within a few minutes.
3. To use a real domain (e.g. thepublicstitch.com or a DMV City Slickerz domain):
   in **Settings → Pages → Custom domain**, enter it, then at your domain registrar
   add a `CNAME` record pointing to `lawrencetotimeh.github.io` (or the four GitHub
   Pages `A` records if using the apex domain — GitHub's docs list the current IPs).

## Swapping in Google Forms

Two forms are stubbed with working fallbacks so nothing is broken today:

- **Contact form** (`contact.html`): currently submits via a `mailto:` link to
  DmvCitySlickerz@gmail.com. To use a Google Form instead: create the form in
  Google Forms, click **Send → Embed (`<>`)**, copy the `<iframe>` tag, and paste it
  in place of the `<form>` block in `contact.html` (there's an HTML comment marking
  exactly where).
- **Newsletter signup** (`index.html`, bottom): currently points at a placeholder
  Formspree URL that won't work yet. Replace the `action="..."` with your Google
  Form's embed, a real Formspree endpoint, or a Mailchimp embed.

## Notes on content

All copy, event details, and photos were pulled directly from the live Wix site and
your Photos-1-001 folder — nothing was invented. A few things to double check before
you consider this final:

- **RSVP flow**: originally handled by Wix Events (built-in confirmation emails,
  guest limits, etc). This static version routes RSVPs to your inbox — fine for two
  events, but if RSVP volume grows you may want a lightweight form tool with its own
  guest list rather than raw email.
- **Instagram feed**: the old site had a broken "Instagram Feed Embed Placeholder."
  This rebuild just links to your Instagram profile instead — swap in Instagram's
  official embed widget if you want live posts on the page.
- **Partner logos**: the sponsorship tiers section never had real logos (they were
  just labeled placeholder boxes on the Wix site too) — this rebuild uses text-only
  tier cards. Add logos to `images/` and drop `<img>` tags in `partnerships.html`
  once you have them.
- **Volunteer section**: removed from the Home page per request.
