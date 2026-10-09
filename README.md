GitHub Pages builds the site with Jekyll on every push, so there is nothing to run locally
unless you want a preview before publishing (see below).

## How the site is laid out

```
royk999.github.io/
├─ index.html          home page: profile, research, honors, and the five newest posts
├─ _config.yml         site settings (title, sections, permalinks, plugins)
├─ _layouts/           default.html (shell + nav), post.html, section.html
├─ assets/
│   ├─ css/            site.css (all styling) and syntax.css (code highlighting)
│   └─ img/            profile.jpg and any images used in posts
├─ _posts/
│   ├─ icpc/           one .md file per post; the folder decides the section
│   ├─ papers/
│   └─ research/
├─ _drafts/            unpublished posts; post-template.md shows the format
├─ icpc/  papers/  research/   section pages, filled in automatically from _posts/
└─ README.md           this file (excluded from the built site)
```

The three sections are defined once in `_config.yml` under `sections:`. The nav, the section
pages, and the post headers all read from that list, so renaming or adding a section is a
one-place change plus a matching folder under `_posts/` and a stub page like `icpc/index.md`.

## Writing a post

1. Copy `_drafts/post-template.md` to `_posts/<section>/YYYY-MM-DD-short-slug.md`, where
   `<section>` is `icpc`, `papers`, or `research`. The date prefix is required; without it
   Jekyll ignores the file. A date in the future keeps the post hidden until that day.
2. Fill in `title` and `description` in the front matter, then write in Markdown.
3. Commit and push. The post appears at `/<section>/short-slug/`, on that section's page, and
   under **Writing** on the home page within a minute or two.

Formatting notes:

- **Math:** wrap both inline and display math in double dollar signs: `$$O(n \log n)$$`.
  Single `$` is left alone. Display math goes on its own lines. MathJax loads on every post.
- **Code:** fenced blocks with a language name (` ```cpp `) are highlighted.
- **Images:** put them in `assets/img/` and reference them as `/assets/img/name.png`.
- **Drafts:** anything in `_drafts/` is never published. Move it to `_posts/` when ready.

## Previewing locally (optional)

Install Ruby from <https://rubyinstaller.org/> (pick the version with Devkit), then:

```bash
gem install bundler
bundle install
bundle exec jekyll serve --drafts --livereload
```

Open <http://localhost:4000>. The `Gemfile` pins the same Jekyll version GitHub uses, so what
you see locally is what will be published. If you change `_config.yml`, restart the server.

If you would rather not install Ruby, just push: a broken build shows up as a failed
"pages build and deployment" run under the repository's **Actions** tab, and GitHub emails you.

A first post is the single highest-value addition to this site. Right now the page tells people
what you've done; one good technical post shows them how you think. Something like "what Effective
Receptive Distance actually measures, and why accuracy alone can't tell you" would be read by
exactly the people you want reading it. Jane Street and PhD admissions committees both weight
"can explain a subtle idea clearly" very heavily, and it's the one signal a CV structurally
cannot carry.

## Optional: your own domain

If you later want `yoonwooku.com` instead of `royk999.github.io` (~$12/year at Namecheap,
Cloudflare, or Porkbun):

1. Buy the domain.
2. At your registrar, add four `A` records for `@` pointing to `185.199.108.153`,
   `185.199.109.153`, `185.199.110.153`, `185.199.111.153`, and a `CNAME` for `www` pointing to
   `royk999.github.io`.
3. In **Settings → Pages → Custom domain**, enter the domain and save, then tick
   **Enforce HTTPS** once the certificate is issued (usually under an hour).

The `github.io` URL keeps working and redirects, so nothing you've already submitted breaks. Worth
doing eventually; not worth blocking the application on.

---

## Where the numbers came from

Every figure on the site was taken from your own documents rather than from the older resume PDFs:

- **GPA 4.11 / 4.30, major GPA 4.22 / 4.30, 98.1 / 100** — the 총계 row of
  `성적증명서_20250725.pdf`. The 4.08 / 4.30 and "major 4.30 / 4.30" figures on the older resumes
  are out of date and are not used here.
- **Course grades** — the same transcript. Note that Linear Algebra 1 (A+) and Introduction to
  Analysis 1 (A0) are now completed, not "in progress" as the old resumes still say.
- **5.76% faster / 71.4% fairer, 40.1% fairer at 1.16% speed cost, n ≤ 100, 300-line C++** —
  `2025년 과학활동내역서.pdf`.
- **ERD / CKA / Hessian findings** — `연구계획서_핵심흐름_브리핑.md`.
- **ICPC, KOI, Baekjoon, Codeforces, MWVC 25%, EV 8–9%** — `Yoonwoo_Ku_Resume_JaneStreet.pdf`.

Two things to confirm before you submit, because I could not verify them from the folder:

- The site links **Prof. Jaesik Park** to `jaesik.info`. Check that's the right page, and confirm
  he's comfortable being named on a public site.
- **BK21 Outstanding Undergraduate Researcher** is listed as a 2026 honor on the strength of your
  saying you were accepted. If the result letter words the title differently, match its wording.
