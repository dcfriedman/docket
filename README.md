# Docket

A single-file writing project tracker. No build step, no backend — one HTML file.

## Important limitation

This version stores your data in your browser's `localStorage`. That means:

- It persists across page reloads and browser restarts, on the same browser, same device.
- It does **not** sync across devices (phone vs. laptop) or browsers (Chrome vs. Safari).
- If you clear browser data/site data for this domain, the docket resets to defaults.

If you want real cross-device sync, you'd need to add a small backend (e.g. a free
tier on Supabase, Firebase, or a GitHub Gist used as a JSON store) — flag it if you
want that built out later.

## Hosting on GitHub Pages

1. Create a new repository on GitHub (e.g. `docket`).
2. Add `index.html` (this file) to the root of the repo.
3. Commit and push:
   ```
   git init
   git add index.html README.md
   git commit -m "Add docket"
   git branch -M main
   git remote add origin https://github.com/<your-username>/docket.git
   git push -u origin main
   ```
4. On GitHub, go to **Settings → Pages**.
5. Under "Build and deployment", set **Source** to "Deploy from a branch",
   branch `main`, folder `/ (root)`.
6. Save. GitHub will give you a URL like:
   `https://<your-username>.github.io/docket/`
7. Bookmark it. That's your tracker.

## Making it private

GitHub Pages sites are public by default unless you're on GitHub Pro/Team/Enterprise
with a private repo. If you don't want your project titles or collaborator names
public, either:
- Use a private repo (requires a paid plan for Pages), or
- Don't host it at all — just open `index.html` directly from your local disk
  (double-click it, or drag it into a browser tab). It works the same way, just
  without a shareable URL.

## Editing content

Everything you add through the UI (title, collaborators, status, link, notes) is
stored client-side — none of it lives in this HTML file itself. If you want to
change the *default* seeded projects (what shows up on a fresh browser with no
saved data), edit the `seed()` function near the top of the `<script>` block in
`index.html`.
