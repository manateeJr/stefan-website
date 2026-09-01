# stefan-website

A static one-page personal site. No build step - just HTML/CSS.

Files: `index.html`, `style.css`, `favicon.svg`. Optional: drop `cv.pdf` next to
`index.html` and uncomment the CV link in `index.html`.

## Before deploying
1. **Rewrite the bio** in `index.html` (the `.about` paragraph) in your own words.
2. Optionally add `cv.pdf` and uncomment its link.
3. Add the Rust/kernel project to the Projects section once it is public.
4. Tweak the accent colour in `style.css` (`--accent`) if you like.

## Deploy on Cloudflare Pages
1. Create a GitHub repo and push these files:
   ```sh
   cd ~/stefan-website
   git init && git add -A && git commit -m "Personal site"
   git branch -M main
   git remote add origin git@github.com:manateeJr/stefan-website.git   # create the repo first
   git push -u origin main
   ```
2. Cloudflare dashboard -> **Workers & Pages** -> **Create** -> **Pages** ->
   **Connect to Git** -> pick the repo.
3. Build settings: **Framework preset: None**, **Build command: (leave empty)**,
   **Build output directory: `/`**. Deploy.
4. Pages project -> **Custom domains** -> add `stefan-andonov.com` (and `www.stefan-andonov.com`).
   Since the domain is on Cloudflare Registrar, Cloudflare creates the DNS records + TLS cert
   automatically.
5. Push to `main` = live in ~30s.

## Local preview
```sh
cd ~/stefan-website
python3 -m http.server 8000   # then open http://localhost:8000
```
