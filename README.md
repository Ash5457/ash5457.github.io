# akash-bahl-site

Personal portfolio for Akash Bahl. One static page, no build step.

```
index.html          page, styles and script in one file
assets/fonts/       Red Hat Display, Text and Mono (SIL Open Font License, see OFL.txt)
assets/images/      headshot and cropped evidence screenshots
assets/icons/       favicon
DESIGN.md           colors, type, components and rules the page follows
.nojekyll           tells GitHub Pages to serve the files as they are
```

## Deploy on GitHub Pages

1. Create a public repository.
   - Named `Ash5457.github.io`, the site is served at `https://ash5457.github.io/`.
   - With any other name, it is served at `https://ash5457.github.io/<repo-name>/`.
2. Upload everything in this folder to the `main` branch, keeping the folder structure.
3. In the repository, open Settings, then Pages. Under "Build and deployment" choose "Deploy from a branch", pick `main` and `/ (root)`, and save.
4. Wait a minute or two, then open the address shown on that page.

All asset paths are relative, so the page works at either address and when opened straight from disk.

## After the address is final

Add these two lines inside `<head>` in `index.html`, with the real address, so link previews show an image:

```html
<meta property="og:url" content="https://YOUR-ADDRESS/">
<meta property="og:image" content="https://YOUR-ADDRESS/assets/images/og.png">
```

For a custom domain, set it under Settings, Pages, "Custom domain" and follow GitHub's DNS instructions there.

## Updating content

- Role, certs and status lines: the `<dl>` inside the first `.term` block in `index.html`, and the matching rows in the Contact block.
- A new certification: add an `<li>` to the first `.creds` list in the Background section.
- Fedora hardening progress: change `<li>` items in `.modules` from "to do" to the published form, and update the "5 of 8 modules" line above it.
- A new project: copy one `<article class="case">` block and replace its content.
