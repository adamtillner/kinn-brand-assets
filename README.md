# Kinn — brand assets

Public image library for Kinn's emails, and for anywhere else a permanent image
URL is needed. **Public on purpose**: every file here is readable by anyone with
the link, because that is what an inbox needs. Nothing unreleased, embargoed or
confidential goes in this repo — the strategy, research and copy stay in
`kinn-email-programme`, which is private.

## The URL

Every file has one, and it follows the path exactly:

```
https://cdn.jsdelivr.net/gh/adamtillner/kinn-brand-assets@main/<folder>/<file>
```

So `evening-shots/kettle-and-cup.jpg` is:

```
https://cdn.jsdelivr.net/gh/adamtillner/kinn-brand-assets@main/evening-shots/kettle-and-cup.jpg
```

Nothing to look up and no upload step — the URL exists the moment the file is
pushed. That is the reason for this repo rather than an image library inside
Shopify or Omnisend: a build can write the URL before the file is even there,
and fail loudly if it is missing rather than quietly shipping a broken image.

## Adding images

Drop the file in the right folder, commit, push. That is the whole process.

Two rules, both about the CDN rather than taste:

**Lowercase, hyphens, no spaces.** A space becomes `%20` in a URL and some email
clients mangle it. `&` is worse. Names here are already normalised.

**Never overwrite a file — add a new one.** jsDelivr caches a branch for about a
week, so replacing `wordmark.png` can keep serving the old one for days, in
emails already sent. A new version gets a new name: `wordmark-v2.png`.

## Folders

| | |
|---|---|
| `wordmarks/` | The Kinn mark. `charcoal` for light grounds, `ivory` for dark and for dark mode. **Both must ship** — charcoal alone means an invisible logo in dark mode, the failure nobody catches because nobody tests it |
| `icons/` | 100 icons, five tones each: amber, charcoal, gold, ivory, and ring variants |
| `figures/` | Explanatory diagrams used in specific emails |
| `abstract-background/` | Textures and dark grounds for headers and section breaks |
| `evening-shots/` | Lifestyle photography — the evening, the ritual, the person |
| `ingredients/` | The six actives, shot individually |
| `product/` | Pack, sachet, pour, hero shots |

## Sizing — read before adding a photograph

Email is not the web. She may be on cellular data in bed, and a heavy image
shows as a grey box until after she has decided whether to care.

**Width: 1200px maximum.** The body of an email is 600px wide in every client.
1200 covers that at 2x for retina. Anything wider is downloaded and thrown away.

**Long edge: 1600px maximum.** A phone-shaped crop at 600px wide runs over a
thousand pixels down the screen. No email uses an image that tall.

**File size: under 250KB, ideally under 150KB** for anything above the fold.
Keep the whole email under about 1MB.

**JPEG for photographs, PNG for anything with transparency.** Not WebP —
Outlook does not support it and the image simply fails to appear.

Everything currently here has been through this. Average 176KB, largest 245KB.
If you drop in a new photograph straight from a camera or a generator, it will
be five to ten times too big, and resizing it is the single highest-value thing
you can do to the email.

## Where these come from

The originals live on Adam's machine in
`Documents/Kinn/Generated Images/Images Used For Email`. This repo is the hosted
copy, with names made URL-safe. If the two ever disagree, this one is what the
emails are actually loading.
