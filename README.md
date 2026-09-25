# bilingual-jekyll-resume-demo

Official live showcase and demonstration website for [**bilingual-jekyll-resume-theme**](https://github.com/kmutahar/bilingual-jekyll-resume-theme).

Featuring Sherlock Holmes' consulting detective resume in 6 languages (English, Arabic, Spanish, French, German, Urdu) with full LTR/RTL support, dark mode toggle, and responsive layouts.

## Architecture

This site functions as a standalone consuming Jekyll site using `theme: bilingual-jekyll-resume-theme`.

- **Landing Page (`/`)**: `_pages/index.html`, using `layout: profile` with Holmes' bio, portrait, and links to all resumes.
- **Resumes (`/<lang>/cv/`)**: `_pages/<lang>.md`, using `layout: resume` rendering YAML data from `_data/<lang>/`.
- **Error Pages (`/404.html`, `/403.html`, `/500.html`)**: Synthesized at build time by the theme's `ErrorPagesGenerator` plugin (`_plugins/error_pages_generator.rb` in the theme repo), rendering `layout: error` with localized error states for every configured language. There is no physical source file for these in this repo — adding one back would silently disable the generator for that page (it skips any page that already exists on disk).

## Requirements

- Ruby >= 3.3 (see `.ruby-version`; CI tests 3.3, 3.4, and 4.0)
- Bundler 2+

## Local Development

```bash
bundle install
bundle exec jekyll serve
```
Open `http://localhost:4000` in your browser.

### Developing against a local theme checkout

The `Gemfile` automatically prefers a `bilingual-jekyll-resume-theme` checkout at `../bilingual-jekyll-resume-theme` (relative to this repo) over the published gem, so theme changes are picked up immediately by `bundle install` without needing to publish a release. Clone the theme repo as a sibling directory to get this:

```
some-folder/
├── bilingual-jekyll-resume-theme/
└── bilingual-jekyll-resume-demo/   (this repo)
```

Because dependency resolution depends on whether that sibling directory exists on a given machine, `Gemfile.lock` is intentionally gitignored here rather than committed — a lockfile generated with the local path present wouldn't reproduce correctly on a machine (or CI runner) without it, and vice versa.