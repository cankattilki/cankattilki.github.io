# Personal Academic Website

Welcome, and thanks for visiting this repository.
This site is designed to be personalized by editing **one file**: `site-data.json`.

In most cases, you do **not** need to edit `index.html`.

## JSON Basics

If you are not familiar with JSON, use this quick guide:

- **String** = text in quotes  
  Example: `"name": "Your Name"`
- **Number** = number without quotes  
  Example: `"footer_year": 2026`
- **Object** = key-value block in `{ }`  
  Example: `"profile": { "name": "Your Name" }`
- **Array (list)** = multiple values in `[ ]`  
  Example: `"research_interests": ["Model Reduction", "Data Driven Modeling"]`

## Quick Start

1. Fork this repo and rename it as `<your_Github_username>.github.io`.
2. Update `site-data.json` either from GitHub directly or in your local.
3. If you work on local, run your website locally by running this in your command line:
   - `python -m http.server 8000`
   - open `http://localhost:8000`
4. Commit and Push to GitHub (`master` branch in this repo).
5. Publish it by navigating to Settings -> Pages -> Publish site

## What You Can Edit in `site-data.json`

- `theme`: colors
- `social_links`: ORCID, Scholar, GitHub links
- `profile`: name, title, image, email, office, bio, research interests
- `publications.journal_articles`
- `publications.conference_papers` (optional, same template as journal articles)
- `publications.preprints`
- `conferences.presentations`
- `conferences.seminar_talks`
- `conferences.organizational_roles`
- `cv.education`
- `cv.research_visits`, `cv.teaching`, `cv.service` (optional, hidden when missing)
- `cv.awards`
- `site.footer_year`

## Profile Example

```json
"profile": {
  "image": "./your-photo.jpg",
  "name": "Your Name",
  "title": "Your Title",
  "university": "Your University",
  "department": "Your Department",
  "email": "you@example.com",
  "office": "Building Room",
  "research_interests": ["Interest 1", "Interest 2"],
  "bio": "Short bio...",
  "research_summary": "Research summary..."
}
```

Notes:
- `image` should be a relative path in this repository.
- `research_interests` must be a JSON **array (list)**, not a single string.
  Correct:
  - `"research_interests": ["Model Reduction", "Data Driven Modeling"]`
  Not correct:
  - `"research_interests": "Model Reduction, Data Driven Modeling"`

## Publications and BibTeX

For **journal articles** and **preprints**, you can paste BibTeX directly.
The page can auto-read common fields (title, authors, venue/status, year).

### Steps

1. Copy BibTeX from Google Scholar / journal / arXiv.
2. Add a new object under:
   - `publications.journal_articles`, or
   - `publications.preprints`
3. Paste BibTeX into `bibtex`.
   - Recommended format: array of lines, for example:
     - `"bibtex": ["@article{...}", "  title={...}", "...", "}"]`
   - You can also use one long string seperated by `\n`.
4. Add button links in `links` (`PDF`, `DOI`, `arXiv`, etc.).

### Journal Article Template

```json
{
  "title": "",
  "authors": "",
  "venue": "",
  "bibtex": [],
  "links": [
    { "label": "", "url": "" }
  ]
}
```

### Preprint Template

```json
{
  "title": "",
  "authors": "",
  "status": "",
  "bibtex": [],
  "links": [
    { "label": "", "url": "" }
  ]
}
```

## Other Empty Templates

### Conference Presentation

```json
{
  "date": "",
  "title": "",
  "type": "",
  "talk": "",
  "url": ""
}
```

`url` is optional and links the conference name to its website.

### Seminar Talk

```json
{
  "date": "",
  "title": "",
  "location": ""
}
```

### Organizational Role

```json
{
  "date": "",
  "title": "",
  "location": "",
  "details": ""
}
```

### CV Education

```json
{
  "degree": "",
  "institution": "",
  "gpa": "",
  "period": "",
  "details": []
}
```

`details` is an optional list of bullet points. Each one is either plain text or `{ "text": "", "url": "" }` for a linked bullet.

### CV Research Visit / Teaching / Service

```json
{
  "title": "",
  "subtitle": "",
  "period": "",
  "details": []
}
```

### CV Award

```json
{
  "title": "",
  "organization": "",
  "period": ""
}
```

## GitHub Pages

This repo is configured to publish from `master`.
After push, your site updates at:

- `https://<your_Github_username>.github.io/`
