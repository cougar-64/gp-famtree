# Grandpa's Family Tree

A simple, elegant family tree website hosted free on GitHub Pages.

---

## Files

| File | Purpose |
|------|---------|
| `index.html` | The website — do not edit unless you know HTML/JS |
| `family.json` | **The family data — this is what you edit** |

---

## How to Deploy (One-time setup)

1. Go to [github.com](https://github.com) and sign in (or create a free account).
2. Click the **+** → **New repository**.
3. Name it anything (e.g. `family-tree`). Set it to **Public**. Click **Create repository**.
4. Click **uploading an existing file** and drag in both `index.html` and `family.json`.
5. Commit the files.
6. Go to **Settings** → **Pages** → under "Branch" select `main` → click **Save**.
7. After ~60 seconds your site is live at:
   `https://YOUR-USERNAME.github.io/family-tree/`

Share that URL with Grandpa — it works in any browser.

---

## How to Edit the Family Data

Open `family.json` in any text editor (Notepad, TextEdit, VS Code).

### Person structure

```json
{
  "id": "unique_id",
  "name": "First Name",
  "lastName": "Last Name",
  "born": "1965",
  "died": "",
  "children": []
}
```

- **id** — must be unique across the whole file. Use simple codes like `c1`, `c1a`, `c1a1`.
- **born / died** — year only (e.g. `"1965"`), or fuller date as text (e.g. `"14 Mar 1965"`). Leave as `""` if unknown or still living.
- **children** — a list of person objects. Empty list `[]` means no children.
- **deceased** — if `died` has any value, a small ✝ appears on the card.

### Adding a new person

Find the parent in the JSON and add to their `children` array:

```json
{
  "id": "c1",
  "name": "Robert",
  "lastName": "Smith",
  "born": "1962",
  "died": "",
  "children": [
    {
      "id": "c1a",
      "name": "Emily",
      "lastName": "Chen",
      "born": "1990",
      "died": "",
      "children": []
    }
    ← add new person here, separated by a comma
  ]
}
```

### After editing

1. Go to your GitHub repository.
2. Click on `family.json`.
3. Click the **pencil icon** (Edit).
4. Paste in your updated JSON.
5. Click **Commit changes**.

The site updates automatically within a few seconds.

---

## Color coding

The tree automatically assigns a distinct color to each of Grandpa's children and their entire branch. The legend appears in the header. Colors are assigned in order — if you add or reorder Grandpa's children, the colors may shift.

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| Site shows "Could not load family.json" | Make sure both files are in the same folder/repo root |
| Tree looks broken | Validate your JSON at [jsonlint.com](https://jsonlint.com) |
| Changes not showing | Hard-refresh: Ctrl+Shift+R (Windows) or Cmd+Shift+R (Mac) |
| Need more than 8 branch colors | Add more `--b9`, `--b10` etc. in the CSS `:root` block |
