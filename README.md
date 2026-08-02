# Alan Li — Academic Website

This folder is your entire website. It's a single self-contained page (`index.html`)
plus this guide. No build tools, no frameworks, nothing to install. You edit the HTML,
push it to GitHub, and GitHub serves it to the world for free.

---

## 0. The big picture (how this works)

```
   You edit index.html  ─push→  GitHub repo "alan2326.github.io"  ─auto→  https://alan2326.github.io
                                          │
                                          └── (optional, later) point alanli.me at it
```

- **Host:** GitHub Pages — free, reliable, standard for academics.
- **Live URL immediately:** `https://alan2326.github.io`
- **Custom domain later:** attach `alanli.me` (or `.net`) with a one-line change. No rebuild.

---

## 1. What you need to do first (one-time setup)

1. **Have a GitHub account** — you do: `alan2326`.
2. **Install git** (if not already). Check by running `git --version` in Terminal.
   If missing, macOS will prompt to install the developer tools, or run `xcode-select --install`.
3. **Personalize the site.** Open `index.html` and search for `EDIT ME`. Each one marks
   something to change (your bio, links, email, news, publications). Take 15 minutes here.
4. **Add a photo (optional).** Put a square photo at `assets/profile.jpg`.
   (If you skip it, the page just hides the image automatically.)
5. **Add your CV (optional).** Drop a `assets/cv.pdf`.

To preview locally before publishing, just **double-click `index.html`** — it opens in your
browser. (Or run `python3 -m http.server` in this folder and visit `http://localhost:8000`.)

---

## 2. Publish it to the web (GitHub Pages)

### A. Create the repository
1. Go to https://github.com/new
2. **Repository name must be exactly:** `alan2326.github.io`
   (This exact name is what makes it a personal site served at that URL.)
3. Set it to **Public**. Don't add a README (this folder already has one).
4. Click **Create repository**.

### B. Push this folder to it
Open Terminal, then run these commands from inside this folder:

```bash
cd "/Users/alanli/Desktop/alan2326.github.io"
git init
git add .
git commit -m "Initial website"
git branch -M main
git remote add origin https://github.com/alan2326/alan2326.github.io.git
git push -u origin main
```

(The first push may ask you to log in to GitHub — follow the browser prompt.)

### C. Turn on Pages
1. In the repo on GitHub: **Settings → Pages**.
2. Under "Build and deployment", **Source = Deploy from a branch**.
3. Branch = **`main`**, folder = **`/ (root)`**. Save.
4. Wait ~1 minute, then visit **https://alan2326.github.io** 🎉

> For a repo named `username.github.io`, Pages is often on by default — check the URL first.

---

## 3. Updating the site later

Every time you change something:

```bash
cd "/Users/alanli/Desktop/alan2326.github.io"
git add .
git commit -m "Update news / add paper"
git push
```

The live site refreshes within a minute. That's the whole workflow.

---

## 4. (Optional) Use a custom domain like alanli.me

Available right now (checked July 2026): **alanli.me**, **alanli.net**, **alanli.xyz**.
`alanli.com/.org/.dev/.io/.ai` are all taken.

Once you buy one (Namecheap, Cloudflare, Porkbun — ~$10–20/yr):

1. **Create a file named `CNAME`** in this folder (no extension) containing just your domain:
   ```
   alanli.me
   ```
   Commit and push it. (Or set it in GitHub → Settings → Pages → Custom domain, which
   creates this file for you.)

2. **At your domain registrar's DNS settings**, add these records:

   | Type  | Host / Name | Value |
   |-------|-------------|-------|
   | A     | `@`         | `185.199.108.153` |
   | A     | `@`         | `185.199.109.153` |
   | A     | `@`         | `185.199.110.153` |
   | A     | `@`         | `185.199.111.153` |
   | CNAME | `www`       | `alan2326.github.io.` |

   (These four IPs are GitHub Pages' — they're stable and public.)

3. Back in **GitHub → Settings → Pages**, enter your domain and check
   **"Enforce HTTPS"** (may take a few minutes to a few hours to go green).

DNS can take up to ~24h to propagate, but usually it's minutes.

---

## 5. If you outgrow this later

This plain-HTML page is deliberately simple and will serve you well for years. If you
ever want automatic publication lists, a blog, or a fancier theme, popular academic
upgrades are:
- **al-folio** (Jekyll) — https://github.com/alshedivat/al-folio
- **academicpages** — https://github.com/academicpages/academicpages.github.io

Both deploy to the same GitHub Pages setup you just learned. No rush — start simple.

---

## File map

```
alan2326.github.io/
├── index.html        ← your whole website (edit the "EDIT ME" spots)
├── README.md         ← this guide
└── assets/
    ├── profile.jpg   ← (add) square headshot
    └── cv.pdf        ← (add) your CV
```
