# Opachii Studio — Website v1

A clean, data-driven homepage for GitHub Pages, with a separate **local-only** publishing backend.

## Frontend deployment

Upload `index.html`, `assets/`, and `data/` to the **root** of your GitHub Pages repository (`main` branch). Keep your existing `CNAME` file (`opachii.studio`) and do not replace it. The public site reads `data/site.json` and displays only content that exists. There are **no demo slides, demo articles, or stock photos**. Sections with no items are hidden.

## Homepage editing

`data/site.json` contains `site`, `hero.slides`, and `sections`. Edit card `title`, `description`, `image`, `href`, and `visible`; add or remove sections and slides. Images can use `/assets/uploads/filename.jpg` after upload. Use the `hero.slides` array for photographs and quotations. Use `sections` for 3-column cards or prose. The empty fourth section is ready for later customization.

## Local backend (publishes to GitHub)

Install Node.js 18 or newer. The backend runs **on your own computer**, not on GitHub Pages. It edits JSON and uploads photos to your GitHub repository using the GitHub Contents API.

In PowerShell:

```powershell
$env:GITHUB_TOKEN="YOUR_FINE_GRAINED_GITHUB_TOKEN"
$env:GITHUB_REPO="wowgoldenroutes/Opachii.studio"
cd backend
node server.js
```

Open `http://127.0.0.1:4177`. The server prints an **Admin key** in the terminal; paste it into the publisher's Admin key field. Select **Load current content**, make changes, then **Publish homepage**. Upload photographs separately and use the returned image paths in your content.

Create a fine-grained GitHub personal access token restricted to **this repository**, with **Contents: Read and write**. **Never** put your token in frontend files, `site.json`, screenshots, or GitHub commits. Do not upload the `backend/` folder to GitHub Pages; keep it locally. The backend binds to localhost only. For a remotely hosted backend, proper account authentication, authorization, secure storage, and a hosting service are required.

**Note:** The publisher reads the local `data/site.json` when loading; it doesn't automatically pull edits made elsewhere on GitHub. Work from one publisher or sync the repository before using it to avoid overwriting newer changes.

This v1 backend is a functional technical foundation, not a WordPress-style graphical editor. Future versions can add forms, drag-and-drop, content types, media library, and authenticated remote access.
