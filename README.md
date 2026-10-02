# tyan-site

Source for my personal website, <https://tyanlee.com/>. Built with [Hugo](https://gohugo.io/) and deployed to GitHub Pages by the workflow in `.github/workflows/deploy.yml` on every push to `main`.

## Layout of the repository

| Path | What it holds |
|---|---|
| `hugo.yaml` | Site settings: title, menu, my name, role, and email |
| `content/_index.md` | Homepage intro |
| `content/bio/index.md` | Bio & C.V. page |
| `content/publication/`, `content/talk/` | One folder per paper, project, or presentation |
| `content/music/index.md`, `data/music.yaml` | Music page and the list of its tiles |
| `data/research_areas.json` | Research areas shown on the homepage |
| `assets/css/custom.css` | All styling |
| `layouts/` | Page templates |
| `i18n/en.yaml` | Interface labels |
| `static/images/`, `static/media/`, `static/files/` | Photos, video clips, PDFs |

## Common edits

**Homepage intro or bio.** Edit `content/_index.md` or `content/bio/index.md`. Each C.V. row is a `<dt>` (dates) followed by a `<dd>` (description).

**Photo.** Replace `static/images/tyan-lee.jpg` with a landscape image (3:2, about 1100×733).

**Add a paper or project.** Create a folder under `content/publication/` with a short hyphenated name. The folder name is the page's permanent address, so it should not be renamed later. Inside it, add `index.md`:

```yaml
---
title: "Paper Title"
date: 2027-01-15
authors: ["Tyan Lee", "Co-Author Name"]
publication_types: ["journal_article"]
publication: "Journal Name, 12(3), 45–67"
abstract: "One paragraph."
links:
  - name: Article (PDF)
    url: "files/my-paper.pdf"
tags: ["homelessness", "causal inference"]
research_areas: ["homelessness-policy"]
home_blurb: "One or two sentences shown under the title on the homepage."
---
```

`publication_types` sets the tab on the research list: `journal_article`, `work_in_progress`, `working_paper`, `thesis`, `book`, `presentation`, `software`, or `data`. Presentations go under `content/talk/` instead. Optional fields: `date_label` (text shown instead of the date), `status_label`, and `home_url` (where the homepage title links, if not the item's own page).

**Research areas.** Edit `data/research_areas.json`. Each area has a `slug` (used in `research_areas:` above), a `title`, an optional `description`, and an optional `other_work` list for work I contributed to but did not author.

**Music page.** Add tiles to `data/music.yaml`; the file has an example of each kind (Spotify player, YouTube video, video file, photo). Media files go in `static/media/`.

**Menu and labels.** The menu is the `menu:` section of `hugo.yaml`; button and label wording is in `i18n/en.yaml`; colours and spacing are at the top of `assets/css/custom.css`.

## Conventions

- URLs in front matter, data files, and the menu have no leading slash, and templates use `relURL`.
- Photos and clips are re-encoded before being added so they carry no location or device metadata.
- The Music page is not in the menu, is marked `noindex`, and is kept out of the sitemap with `private: true`.
- The automatic "See Also" list on item pages is switched off with `see_also: false` in `hugo.yaml`.

## Building locally

```
npm ci
hugo --gc --minify
```

Requires Hugo extended 0.148.2 or later (CI uses 0.152.2).
