# abhisheksarkar30.github.io

My personal CV / portfolio site, served by GitHub Pages at
**https://abhisheksarkar30.github.io**.

It's a Jekyll site: one content file (`_config.yml`) feeding a set of HTML partials.
Pushing to the default branch is all it takes to publish — GitHub Pages builds and
deploys on push, so nothing generated is ever committed (see `.gitignore`).

The repo also hosts privacy pages for my Android apps, since Play Store listings
need a public URL for them.

## Pages

| Path | What it is |
| --- | --- |
| `/` | The CV/portfolio front page — intro, skills, work experience, education, featured GitHub projects |
| `/online-cv` | A print-friendly, single-page CV (`online-cv.html`) |
| `/call-blocker-privacy` | Privacy policy for the ABS Call Blocker app |

## Editing the content

All the copy lives in [`_config.yml`](_config.yml). Normal updates don't require
touching any HTML:

- `primarylinks` — the navbar links
- `intro`, `additionalinfo` — the free-text blocks on the front page
- `skills` — the skill list
- `roles` — work experience
- `education` — schools and degrees
- `github` — which repositories get featured
- `coursera`, `speakerdeck`, `stackoverflow`, `blogfeed` — optional sections; they
  ship commented out, so uncomment and fill them in to enable

`index.html` is just a list of `_includes/section_*.html` partials, so adding a new
block to the page means adding an include there.

## Running it locally

GitHub Pages builds this remotely, so a local run is only for previewing changes.
There is no `Gemfile` — the Pages build uses its own toolchain — so either install
Jekyll yourself or use the container:

```bash
# with Jekyll installed
jekyll serve            # http://localhost:4000

# or, containerised
docker run --rm -it -p 4000:4000 -v "$PWD":/srv/jekyll -w /srv/jekyll \
  jekyll/jekyll jekyll serve
```

## Layout

```
_config.yml              all site content
index.html               front page, assembled from partials
online-cv.html           standalone printable CV
call-blocker-privacy.md  app privacy policy
_includes/               section_*.html partials, plus head/header/footer
_layouts/default.html    the single layout every page uses
css/  js/  img/          styles, scripts, images
```

## Credits

The CV layout started from Rob Hinds' NerdAbility CV generator and has been adapted
since. Licensed under the [MIT License](LICENSE).
