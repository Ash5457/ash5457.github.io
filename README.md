# ash5457.github.io

My portfolio site. Plain HTML and one CSS file, no build step and no JavaScript.

```
index.html                          home page
projects/ad-lab.html                one page per project
projects/secure-remote-access.html
projects/fedora-hardening.html
assets/css/site.css                 all the styling, shared by every page
assets/fonts/                       Red Hat Display, Text and Mono (SIL Open Font License, see OFL.txt)
assets/images/                      headshot, cropped screenshots, link preview image
assets/icons/                       favicon
DESIGN.md                           colours, type and the rules the pages follow
```

## Preview it locally

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000. Use the server, since the links between pages point at folders and won't resolve if you open the files straight from disk.

## Deploy

Push to `main`. GitHub Pages serves the repo root, and the site updates a minute or so later.

## Editing

The header and footer are repeated in all four HTML files, so a change to the nav has to be made in each one.

- Role, certs and status: the `<dl>` inside the terminal block on `index.html`.
- A new certification: add an `<li>` to the first `.creds` list on `index.html`.
- Fedora progress: on `projects/fedora-hardening.html`, change a module's `<li>` to the published form and update the "5 of 8" text. The same count is on its card on `index.html`, along with the small SVG list in that card.
- A new project: copy one of the files in `projects/`, then copy one `<article class="card">` on `index.html` and point it at the new file.
