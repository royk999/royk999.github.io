# Putting this site online — permanently, for free

The goal: a URL like `https://royk999.github.io` that is live forever, costs nothing, and is what
you paste into Jane Street's **Website UID** field. (That field is just Greenhouse's oddly-named
box for "your personal website URL." It expects a link, not an ID number.)

---

## Step 1 — Create the repository

1. Go to <https://github.com/new> while signed in as `royk999`.
2. **Repository name:** `royk999.github.io` — exactly this, matching your username. This is the
   magic name that makes GitHub serve it at the root domain.
3. Set it to **Public**. (Private repos need a paid plan to publish Pages.)
4. Do not add a README, .gitignore, or license — leave all the checkboxes empty.
5. Click **Create repository**.

## Step 2 — Upload the files

On the empty repository page, click **uploading an existing file**, then drag in:

- `index.html`
- `profile.jpg` (your photo — see Step 3)

Scroll down, click **Commit changes**.

## Step 3 — Add your photo

Crop a photo square (roughly 400×400 px is plenty), save it as `profile.jpg`, and upload it
alongside `index.html`. Until that file exists the page shows a neutral grey "YK" circle, so the
site is never broken — it just looks unfinished. Any square JPEG works; if you'd rather use a PNG,
change `src="profile.jpg"` to `src="profile.png"` in `index.html`.

## Step 4 — Turn on Pages

1. In the repository, go to **Settings → Pages** (left sidebar).
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Branch: **main**, folder: **/ (root)**. Click **Save**.
4. Wait 1–2 minutes, refresh the page. GitHub will show:
   *Your site is live at https://royk999.github.io/*

That URL is now permanent. GitHub serves it over HTTPS from their CDN, with no server for you to
maintain, no bill, and no expiry. It stays up as long as the repository exists and is public.

## Step 5 — Verify before you submit

Open the URL in a private/incognito window (this proves it works for someone who isn't logged into
your GitHub) and check it on your phone. Then paste it into the **Website UID** field.

---

## Editing it later

**Small text changes:** open `index.html` on github.com, click the pencil icon, edit, commit. The
live site updates within a minute.

**Bigger changes:** clone it locally and work in a real editor.

```bash
git clone https://github.com/royk999/royk999.github.io.git
cd royk999.github.io
# edit index.html, open it in a browser to preview
git add -A && git commit -m "Update research section" && git push
```

Everything is in one file: HTML at the bottom, CSS in the `<style>` block at the top. No build
step, no dependencies, no framework to keep up to date. That's deliberate — a site you can edit in
thirty seconds is a site you'll actually keep current, and a stale personal page reads worse than
no page at all.

## Adding writing later

The **Writing** section currently says nothing is published yet. When you have a post:

1. Make a `posts/` folder and put e.g. `posts/effective-receptive-distance.html` in it. Copying
   `index.html` and replacing the body content is the fastest way to keep the styling consistent.
2. In `index.html`, delete the `<p class="empty">…</p>` line under `<h2>Writing</h2>` and
   uncomment the `<ul class="plain">` block right below it — it already has the correct markup.

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
