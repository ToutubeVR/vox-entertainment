Publishing & submitting Voxtek (quick guide)

This document outlines easy ways to host the static site and submit it to Google for indexing. Opera GX is a browser — once your site is live it will be accessible from Opera/GX; to feature in GX-specific channels you may need to contact Opera.

1) Quick hosting options (pick one)

A) GitHub Pages (recommended for small static sites)
- Create a GitHub repo (public or private with Pages enabled)
- Push the files from this folder to the repository root (index.html or your entry file)
- In the repo Settings → Pages, select the branch and folder (root) and enable HTTPS
- Your site will be available at https://<username>.github.io/<repo>/ (or https://<username>.github.io/ for user site)

B) Netlify (drag & drop)
- Create a Netlify account
- Drag & drop the site folder (or connect the GitHub repo)
- Netlify provides a free HTTPS site and automatic deploys

C) Vercel
- Create a Vercel account and import the Git repo
- Configure build settings for a static site (no build needed)

2) Make a sitemap & robots
- Edit `sitemap-template.xml`: replace BASE_URL with your live site URL and save as `sitemap.xml` at the publish root
- Edit `robots-template.txt`: replace BASE_URL and save as `robots.txt` at the publish root

3) Submit to Google Search Console
- Go to https://search.google.com/search-console
- Add property: choose "URL prefix" and enter your exact site URL (including https://)
- Verify ownership (recommended: HTML file method or DNS record if you own the domain)
- In the Console, go to "Sitemaps" and submit `/sitemap.xml`
- Use "URL Inspection" to request indexing for important pages

Notes about verification: you must be able to upload a verification file to the site or add a DNS TXT record for the domain to prove ownership.

4) Opera / Opera GX
- Opera GX is a browser; once your site is live, Opera users can open it as normal.
- If you want to be featured in Opera/GX channels (GX Corner or official features), you'll need to contact Opera's editorial/partnership team — there's no automated public submission like Google Search Console.

5) Anti-raid & privacy
- If you plan to add analytics, use privacy-friendly options and disclose it in a small privacy note.

6) Optional help I can do for you now (pick any):
- Create a ready-to-publish `sitemap.xml` and `robots.txt` (I created templates in the repo; I can replace BASE_URL if you tell me the final URL)
- Create a `index.html` redirect or root index if you want `vox website.html` to be your homepage
- Prepare a GitHub repo README and .github/workflows for automatic deploys on push
- Prepare a ZIP of the site to upload to Netlify

Tell me which hosting option you'd like and your final site URL (or GitHub username/repo) and I will prepare the sitemap, robots, and index redirect for you.
 
 ---
 Prepared artifacts (created for you):

 - `index.html` — root redirect to `vox website.html` so the site root loads the main page.
 - `sitemap.xml` — ready-to-edit sitemap with placeholders. Replace `https://YOUR_SITE_URL` with your final URL before publishing.
 - `robots.txt` — ready-to-edit robots file pointing to the sitemap (update the URL accordingly).
 - `voxtek_site.zip` — a ZIP archive created at `E:\\voxtek_site.zip` containing the site folder, ready to upload to Netlify or other hosts.

 If you provide your final site URL or GitHub repo, I can update `sitemap.xml`/`robots.txt` and (optionally) create a GitHub Actions workflow for automatic deploys.

---
If you want to publish to GitHub Pages under your account `ToutubeVR` and repository `ToutubeVR`, here are exact commands to run locally (PowerShell):

```powershell
# from the site folder (e:\funny meme voxcord)
git init
git add --all
git commit -m "Initial site commit"
git branch -M main
git remote add origin https://github.com/ToutubeVR/ToutubeVR.git
git push -u origin main
```

Notes:
- I added a GitHub Actions workflow at `.github/workflows/deploy_pages.yml` that will automatically deploy the repository contents to GitHub Pages when you push to `main`.
- Make sure to create the empty repository `ToutubeVR` under your GitHub account before pushing, or follow GitHub's instructions to create and push.
- `sitemap.xml` and `robots.txt` were already updated to point at `https://ToutubeVR.github.io/ToutubeVR/`.

After pushing, go to your repo -> Settings -> Pages and confirm Pages is using the `gh-pages` deployment or the Pages action (it should show the deployment status). The Actions log will show the Pages deployment progress.