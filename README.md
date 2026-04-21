# pradutta.com — Personal Portfolio

**Prachurjya Dutta** · Staff Software Engineer · [pradutta.com](https://pradutta.com)

## 🚀 Deploy to GitHub Pages + Namecheap

### Step 1 — Create the GitHub Repo

1. Go to [github.com/new](https://github.com/new)
2. Name it **exactly**: `pradutta.com` (or `prachurjyadutta.github.io` if you prefer)
3. Set it to **Public**
4. Click **Create repository**

### Step 2 — Push the files

```bash
git init
git add .
git commit -m "initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/pradutta.com.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages**
2. Under **Source**, select **Deploy from a branch**
3. Select branch: `main` / folder: `/ (root)`
4. Click **Save**
5. Under **Custom domain**, type `pradutta.com` and click **Save**
6. GitHub will verify the domain — wait a minute, then check **Enforce HTTPS** ✓

### Step 4 — Configure Namecheap DNS

1. Log in to [namecheap.com](https://namecheap.com) → **Domain List** → click **Manage** next to `pradutta.com`
2. Go to the **Advanced DNS** tab
3. Delete any existing A records and CNAME records for `@` and `www`
4. Add these **4 A records** (GitHub Pages IPs):

| Type | Host | Value            | TTL  |
|------|------|------------------|------|
| A    | @    | 185.199.108.153  | Auto |
| A    | @    | 185.199.109.153  | Auto |
| A    | @    | 185.199.110.153  | Auto |
| A    | @    | 185.199.111.153  | Auto |

5. Add a **CNAME record** for `www`:

| Type  | Host | Value                          | TTL  |
|-------|------|-------------------------------|------|
| CNAME | www  | YOUR_USERNAME.github.io.      | Auto |

> Replace `YOUR_USERNAME` with your actual GitHub username.

6. Save all records

### Step 5 — Wait & Verify

- DNS propagation can take **5–30 minutes** (up to 48 hrs worst case)
- Check propagation at [dnschecker.org](https://dnschecker.org)
- Once live, visit [https://pradutta.com](https://pradutta.com) — you should see your site over HTTPS

---

## 📁 File Structure

```
pradutta.com/
├── index.html   ← the entire site (single file, self-contained)
├── CNAME        ← tells GitHub Pages to serve on pradutta.com
└── README.md    ← this file
```

The site is a **single self-contained HTML file** — no build step, no dependencies, no Node.js required.

## ✏️ Editing Content

All content, styles, and scripts live in `index.html`. Open it in any text editor.

Key sections to update:
- **Hero stats** — search `data-target` attributes
- **Experience** — find the `<article class="timeline-row">` blocks
- **Projects** — find `<a class="project` blocks in the Work section
- **Contact email** — search `prachurjya.dutta@gmail.com` and replace
- **Social links** — search `prachurjyadutta` for LinkedIn/GitHub handles

## 🔄 Updating the Site

```bash
# Edit index.html, then:
git add index.html
git commit -m "update: [what you changed]"
git push
```

GitHub Pages automatically redeploys in ~30 seconds.
