# Portfolio site

A static, no-backend portfolio. Your info lives in two files:

- `data/profile.json` — your name, tagline, links, bio, skills
- `data/projects.json` — your project list

## Editing

Everything is edited in `data/profile.json` and `data/projects.json` — there's no edit mode in the site itself.

1. Open the `portfolio-site` folder in VS Code.
2. Edit `data/profile.json` for your name, tagline, bio, skills, and links.
3. Edit `data/projects.json` to add, remove, or change projects. Each entry looks like:
   ```json
   {
     "id": "p3",
     "year": "2026",
     "title": "New Project",
     "description": "What it does and the problem it solves.",
     "tags": ["Python", "AWS"],
     "link": "https://github.com/you/new-project"
   }
   ```
   Add a new object to the array (comma-separated) for a new project, delete one to remove it, or edit values in place.
4. Save the file(s).
5. If you're using the VS Code **Live Server** extension (see below), the page auto-refreshes as you save.
6. Redeploy when you're happy (see below) — commit and push if using GitHub Pages, or re-drag the folder if using Netlify.

### Previewing changes live in VS Code
Install the **Live Server** extension (by Ritwick Dey) from the Extensions panel, then right-click `index.html` → **Open with Live Server**. It opens the page in your browser and refreshes automatically every time you save a JSON file — much faster than redeploying to check each change.

## Deploying

Any static host works. Two easy free options:

**Netlify (drag and drop)**
1. Go to https://app.netlify.com/drop
2. Drag the whole `portfolio-site` folder onto the page.
3. You'll get a live URL immediately. Re-drag the folder any time you update the JSON files.

**GitHub Pages**
1. Create a new GitHub repo and push these files to it.
2. In the repo settings, go to Pages, and set the source to the `main` branch (root).
3. Your site will be live at `https://yourusername.github.io/reponame`.
4. To update, edit the JSON files, commit, and push — Pages redeploys automatically.

## Local preview

Because the page loads `data/*.json` with `fetch`, opening `index.html` directly by double-clicking it may fail due to browser CORS rules on `file://` paths. To preview locally, run a tiny local server from inside the folder:

```
python3 -m http.server 8000
```

Then visit `http://localhost:8000` in your browser.
