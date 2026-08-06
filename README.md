# Xylea LLC website

A lightweight, framework-free company website for **Xylea LLC**, ready for GitHub Pages and the custom domain `xylea.org`.

## Before publishing

1. Confirm that `hello@xylea.org` exists. If you prefer another address, replace it in:
   - `index.html`
   - `support.html`
   - `privacy.html`
2. Review the privacy policy and adapt it whenever the website or an app begins collecting data.
3. Keep the legal company name **Xylea LLC** visible on the homepage and footer so the domain is clearly associated with the organization.

## Publish with GitHub Pages

### 1. Create the repository

Create a new GitHub repository, for example `xylea-site`. Upload all files from this folder to the repository root, including the hidden `.nojekyll` file.

Using Git from a terminal:

```bash
git init
git add .
git commit -m "Launch Xylea website"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/xylea-site.git
git push -u origin main
```

### 2. Turn on GitHub Pages

In the repository:

1. Open **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select the `main` branch and `/ (root)` folder.
4. Save.
5. Under **Custom domain**, enter `xylea.org` and save.

The included `CNAME` file already contains `xylea.org`.

### 3. Point the domain to GitHub Pages

At the DNS provider for `xylea.org`, remove conflicting parking or web-hosting records, then add these four `A` records for the apex/root domain:

| Type | Name | Value |
| --- | --- | --- |
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

Also add a `CNAME` record for `www`:

| Type | Name | Value |
| --- | --- | --- |
| CNAME | www | YOUR-USERNAME.github.io |

Use only the GitHub username or organization domain in the CNAME target—do not add the repository name.

### 4. Enable HTTPS

After GitHub reports a successful DNS check, return to **Settings → Pages** and enable **Enforce HTTPS**. DNS and certificate changes can take time to propagate.

## Local preview

From this folder, run:

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080`.

## Adding an app later

Replace one of the “Exploring” cards on `index.html` with the app name, a short description, App Store link, privacy-policy link, and support link. For app-specific policies, create a folder such as:

```text
apps/
  your-app/
    index.html
    privacy.html
    support.html
```

## Files

- `index.html` — company homepage
- `support.html` — general support page
- `privacy.html` — website privacy policy
- `404.html` — custom not-found page
- `assets/site.css` — all styles
- `assets/site.js` — mobile navigation, reveal motion, current year
- `CNAME` — GitHub Pages custom domain
- `.nojekyll` — serves files directly without Jekyll processing
