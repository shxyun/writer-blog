+++
title = "Content Components Toolbox"
date = 2026-10-10T10:00:00+08:00
draft = true
tags = ["Toolbox", "Guide"]
categories = ["Site Guide"]
summary = "A live demo of every shortcode component on this site: book and product cards, coupon codes, download cards, YouTube, Spotify, media players, pull quotes and more."
language = "en"
+++

This page demonstrates **every content component** available on this site. When writing a post, copy the markup from any code block below, paste it into your Markdown draft, and replace the sample values with your own. All components support light and dark mode.

## 1. Book / Product Card

A mobile-friendly card for book recommendations, web-novel spotlights or any affiliate product. The outbound link is automatically tagged with `rel="nofollow sponsored noopener"`.

**Syntax:**

```
{{</* product img="https://example.com/cover.jpg" badge="Editor's Pick" title="Book Title" desc="A one-line hook for the story." old="$14.99" price="$4.99" rating="4.8" link="https://www.amazon.com/" btn="Get It on Kindle" */>}}
```

All parameters except `title` and `link` are optional. `badge`, `old` (strikethrough price), and `rating` can be omitted.

**Result:**

{{< product img="/images/shortcodes-demo-book.jpg" badge="Editor's Pick" title="The Last Ember of Aeloria" desc="A forgotten heir. A blade that burns with starlight. A kingdom that has already lost the war — or thinks it has." old="$14.99" price="$4.99" rating="4.8" link="https://www.amazon.com/" btn="Get It on Kindle" >}}

{{< alert type="info" title="Affiliate disclosure" >}}
If you earn commissions, add a short FTC-style disclosure near the card, for example: *"As an Amazon Associate I earn from qualifying purchases."*
{{< /alert >}}

## 2. Coupon Code

A one-click copyable coupon or promo code — useful for platform discounts, free-chapter codes or store promos.

**Syntax:**

```
{{</* coupon code="EMBER25" title="25% off this week only" note="Enter the code at checkout. Click to copy." */>}}
```

**Result:**

{{< coupon code="EMBER25" title="25% off this week only" note="Enter the code at checkout. Click to copy." >}}

## 3. Download Card

A resource card for Google Drive, Dropbox, OneDrive, MEGA, Gumroad, GitHub, iCloud, MediaFire, TeraBox or a direct link. Each platform gets its own brand-colored badge.

**Syntax:**

```
{{</* drive platform="Google Drive" name="Worldbuilding Worksheet (PDF, 6 MB)" url="https://drive.google.com/" code="AB12-CD34" */>}}
```

Parameters: `platform` (drives the badge color), `name`, `url`, `code` (optional access code), `btn` (optional, defaults to **Download**).

**Result:**

{{< drive platform="Google Drive" name="Worldbuilding Worksheet (PDF, 6 MB)" url="https://drive.google.com/" code="AB12-CD34" >}}

{{< drive platform="Gumroad" name="Character Profile Template" url="https://gumroad.com/" >}}

## 4. YouTube Video

Embed a book trailer, author interview or review. Pass either a video `id` or a full `url`; the player is responsive (16:9).

**Syntax:**

```
{{</* youtube id="jNQXAC9IVRw" title="Me at the zoo" */>}}
```

**Result:**

{{< youtube id="jNQXAC9IVRw" title="Me at the zoo" >}}

## 5. Spotify Player

Embed a soundtrack playlist, `track`, `album`, `episode` or `show`. The ID is the last part of the Spotify share URL.

**Syntax:**

```
{{</* spotify type="playlist" id="37i9dQZF1DXcBWIGoYBM5M" */>}}
```

**Result:**

{{< spotify type="playlist" id="37i9dQZF1DXcBWIGoYBM5M" >}}

## 6. Local Video and Audio

Put media files in your `static/` folder (for example `static/media/trailer.mp4`) and reference them with an absolute path. Audio files (`.mp3`, `.m4a`, `.wav`, `.ogg`, `.aac`, `.flac`) render as an audio player automatically — great for podcast readings or author voice notes.

**Syntax:**

```
{{</* video src="/media/trailer.mp4" poster="/media/poster.jpg" */>}}
{{</* video src="/media/reading.mp3" */>}}
```

**Result (hosted samples used for demonstration):**

{{< video src="https://media.w3.org/2010/05/sintel/trailer.mp4" >}}

{{< video src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" >}}

{{< alert type="warning" title="Tip" >}}
Avoid committing large media files to Git — repositories quickly become slow. Host big videos on YouTube and embed them instead.
{{< /alert >}}

## 7. Pull Quote

A styled blockquote with an optional author and source.

**Syntax:**

```
{{</* quote author="Brandon Sanderson" source="Warbreaker" */>}}
A good story is a conversation between the storyteller and the audience.
{{</* /quote */>}}
```

**Result:**

{{< quote author="Brandon Sanderson" source="Warbreaker" >}}
A good story is a conversation that the storyteller starts and the audience finishes.
{{< /quote >}}

## 8. Callout Boxes

Highlight notes, warnings, tips or successes. Types: `info`, `success`, `warning`, `error`.

**Syntax:**

```
{{</* alert type="warning" title="Spoilers ahead" */>}}
This chapter reveals the ending of Book 1.
{{</* /alert */>}}
```

**Result:**

{{< alert type="info" title="Note" >}}
This is a neutral info callout.
{{< /alert >}}

{{< alert type="success" title="New release" >}}
Chapter 42 is now available to all subscribers.
{{< /alert >}}

{{< alert type="warning" >}}
A warning without a title.
{{< /alert >}}

{{< alert type="error" title="Content note" >}}
This section depictions of violence and may not suit all readers.
{{< /alert >}}

## 9. Collapsible Block (FAQ)

A native `<details>` block, ideal for FAQs or hidden bonus scenes. Add `open="true"` to expand it by default.

**Syntax:**

```
{{</* collapse title="Is this novel complete?" */>}}
Yes — all 120 chapters are published.
{{</* /collapse */>}}
```

**Result:**

{{< collapse title="Is this novel complete?" >}}
Yes. All 120 chapters are published, and the epilogue is free for newsletter subscribers.
{{< /collapse >}}

{{< collapse title="Where can I read the uncensored version?" >}}
Follow the link on the book card above — the author's platform hosts the full, uncut text.
{{< /collapse >}}

## 10. Newsletter Form

A Buttondown-powered subscribe box so readers never miss a new chapter or review.

**Syntax:**

```
{{</* subscribe */>}}
```

Optional parameters: `title`, `desc`, `ph` (placeholder), `btn`.

**Result:**

{{< subscribe >}}

## 11. Web-Novel Card (Platform Promos)

Purpose-built for promoting **serialized fiction apps** such as **Novellia, GoodNovel, PlotNovel and Novel Master**: a portrait cover, a brand-colored platform badge, an Ongoing/Completed status pill, chapter count, star rating, genre tags, a free-chapters hook and a "Start Reading" button.

**Syntax:**

```
{{</* novel platform="GoodNovel" cover="/images/cover.jpg" title="Novel Title" author="Pen Name" status="Ongoing" chapters="486" rating="4.8" genres="Werewolf, Romance" desc="A one-line hook." free="First 30 chapters free" link="https://..." btn="Start Reading" */>}}
```

Only `title` and `link` are required. Badge colors are built in for Novellia, GoodNovel, PlotNovel, Novel Master, Royal Road, Wattpad, WebNovel, Kindle, Kobo and Bookshop.org (any other platform gets a neutral blue badge). `status` accepts `Ongoing`, `Completed` or `Hiatus`; omit any field you do not need.

**Result:**

{{< novel platform="GoodNovel" cover="/images/novel-demo-werewolf.jpg" title="Her Mate, Her Enemy" author="Luna Vane" status="Ongoing" chapters="486" rating="4.8" genres="Werewolf, Romance, Paranormal" desc="On the night of the blood moon, she finds out her destined mate is the alpha who destroyed her pack — and the feeling is mutual." free="First 30 chapters free" link="https://www.goodnovel.com/" btn="Start Reading" >}}

{{< novel platform="Novellia" cover="/images/novel-demo-xianxia.jpg" title="Sword of the Ninth Heaven" author="Mo Qingchen" status="Completed" chapters="1204" rating="4.9" genres="Xianxia, Cultivation, Adventure" desc="A discarded outer disciple inherits a broken jade sword containing the will of an immortal emperor. The long climb to the ninth heaven begins tonight." free="Full book unlocked" link="https://www.novellia.com/" btn="Read the Full Novel" >}}

{{< alert type="info" title="Affiliate disclosure" >}}
Platform promo links are monetized links — keep a one-line FTC disclosure on the page, for example: *"This post contains affiliate links; I may earn a commission when you start reading at no cost to you."*
{{< /alert >}}

---

That is the full toolbox. New components will be added to this page as they are built.
