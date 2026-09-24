# bilingual-jekyll-resume-demo

Official live showcase and demonstration website for [**bilingual-jekyll-resume-theme**](https://github.com/kmutahar/bilingual-jekyll-resume-theme).

Featuring Sherlock Holmes' consulting detective resume in 6 languages (English, Arabic, Spanish, French, German, Urdu) with full LTR/RTL support, dark mode toggle, and responsive layouts.

## Architecture

This site functions as a standalone consuming Jekyll site using `theme: bilingual-jekyll-resume-theme`.

- **Landing Page (`/`)**: Built using `layout: profile` with Holmes' bio, portrait, and links to all resumes.
- **Resumes (`/<lang>/cv/`)**: Built using `layout: resume` rendering YAML data from `_data/<lang>/`.
- **Error Page (`/404.html`)**: Built using `layout: error` displaying localized error states.

## Local Development

```bash
bundle install
bundle exec jekyll serve
```
Open `http://localhost:4000` in your browser.
