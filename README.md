# copilot.kleosresearch.xyz

A mirror of the 0xCopilot website, served at
[copilot.kleosresearch.xyz](https://copilot.kleosresearch.xyz). The original is
[0xcopilot.tech](https://0xcopilot.tech). 0xCopilot is a local-first desktop
agent; the site explains what it does and how to install it.

## What is here

This repository holds the built website only, copied file for file from
[0x-copilot-dev/0x-copilot-dev.github.io](https://github.com/0x-copilot-dev/0x-copilot-dev.github.io),
which serves 0xcopilot.tech. Only `CNAME` differs. Each page's canonical link
still points at 0xcopilot.tech on purpose, so search engines treat this site as
a copy rather than a second site.

| Page | File |
| --- | --- |
| Home | `index.html` |
| Install | `install.html` |
| Documentation | `docs.html` |
| Moodboard | `moodboard.html` |
| Generated styles and scripts | `_astro/` |
| Images and icons | `media/`, `favicon.*`, `apple-touch-icon.png`, `mark-512.png` |

The source is the Astro project in `apps/website/` of
[0x-copilot-dev/0x-copilot](https://github.com/0x-copilot-dev/0x-copilot). Make
changes there; anything edited here is overwritten by the next copy.

## Preview it locally

From the repository root:

```sh
python3 -m http.server 8000
```

Then open http://localhost:8000.

## How it deploys

GitHub Pages serves the `main` branch at copilot.kleosresearch.xyz, and
`.nojekyll` tells it to serve the files as they are. Nothing updates this copy
automatically. When 0xcopilot.tech changes, refresh the copy from the
repository root, keeping this repository's `CNAME`:

```sh
git clone --depth 1 https://github.com/0x-copilot-dev/0x-copilot-dev.github.io /tmp/0xcopilot-site
rsync -a --delete --exclude .git --exclude CNAME --exclude README.md /tmp/0xcopilot-site/ ./
```

Review the changes, commit them and merge to `main`. Merging publishes.

## Licence

This repository has no licence file of its own. The site is built from
[0x-copilot-dev/0x-copilot](https://github.com/0x-copilot-dev/0x-copilot), which
is MIT-licensed.
