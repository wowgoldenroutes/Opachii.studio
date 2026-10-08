# Opachii Studio — Simple Article Publisher

## What to upload to GitHub Pages
Upload `index.html`, `article.html`, `assets/`, and `data/` to the root of your existing GitHub repository. **Keep your existing CNAME**. These are the public website files.

## What to keep private
Keep `publisher.html` on your own computer. **Do not upload it to your public GitHub repository**. Double-click `publisher.html` to open it in your browser.

## Publishing
1. In GitHub, create a fine-grained personal access token scoped only to `wowgoldenroutes/Opachii.studio` with Contents read/write permission. Treat it like a password.
2. Open `publisher.html` locally in Chrome or Edge. Enter the token in GitHub connection. It is held in page memory for the session, not saved.
3. Write an article, add text and photos, choose a category, and click Publish article.
4. The editor uploads photos to `assets/uploads/` and adds the article to `data/articles.json`. Your homepage shows the three latest posts per category, and each post has its own article URL.

## Notes
- Requires internet and permission to write to the repository. The browser must allow requests to api.github.com from a local file; modern Chrome/Edge generally support this, but browser restrictions can vary.
- If an upload succeeds but the article JSON update fails, some orphaned photos may remain; you can delete them in GitHub.
- The editor is for *new* articles only; editing existing posts is not included yet.
- GitHub Pages is a static host; there is no server-side login, comment system, or WordPress backend.
- `data/articles.json` is public, as intended for published posts. Do not put private information in it.
- Publishing may take a few minutes to appear as GitHub Pages deploys.
