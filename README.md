# Tlou Family Tree

An interactive website for the Tlou family tree. It started from the chart dated 13 Nov 2022 and holds 103 people across seven generations.

- **`index.html`**: the whole website in one file. Open it in any browser; nothing needs installing.
- **`Tlou-Family-Tree.docx`**: a printable Word copy of the original chart. It does **not** update when you edit the website. For an up-to-date printout, use **List → Print list** on the site.

## Viewing
- **Tap a person** to see their parents, partner, brothers and sisters, children and grandchildren. Tap any of those names to keep exploring. **← Back** returns to the last person you viewed.
- **Search** with the box at the top. You can also press `/` on a keyboard.
- **Tree / List** switches between the picture tree and a simple outline you can print.
- **How are we related?** (in the side panel) names the relationship between two people, for example "first cousin once removed".
- Every person has their own link (for example `…/index.html#1.2.1`) that you can send to relatives.

## Adding, editing and removing family members
1. Press **✎ Edit family**.
2. Tap a person, then use the yellow buttons in the side panel:
   - **＋ Add child** (each card also has a small ＋ button for this)
   - **＋ Add partner**
   - **✎ Edit details**: name, gender, year born, year passed, notes
   - **◀ Move left / Move right ▶**: changes the birth order
   - **🗑 Remove**: if the person has children, you choose whether to keep the children (they move up a level) or remove the whole branch
3. Made a mistake? Press **↶ Undo**, or Ctrl+Z.

Your edits are saved automatically **on the device you're using**. Other people won't see them until you publish them.

## Publishing your changes for the whole family
1. In edit mode, press **⬇ Download updated website**. This saves a new `index.html` with your changes.
2. On github.com, open this repository → **Add file → Upload files**. Drag in the new `index.html` and click **Commit changes**.
3. The website updates in about a minute.

The **More…** button can also save a backup file of your edits (`.json`) and load one back. This is useful for moving edits to another computer.

## Free hosting

### GitHub Pages (recommended)
1. Make the repository **public**. On a free account, Pages only works for public repositories.
2. Open **Settings → Pages → Build and deployment → Deploy from a branch**. Choose the branch with `index.html` and `/ (root)`, then click **Save**.
3. The site appears at `https://<your-github-username>.github.io/thamaga/`.

### Google Sites
Create a site at <https://sites.google.com>, choose **Insert → Embed → By URL**, paste your GitHub Pages link, then **Publish**.

## Editing the data by hand (optional)
The family is stored as JSON inside `index.html`, in `<script id="family-data" type="application/json">`. Each person looks like this:

```json
{ "name": "Lindiwe Tlou", "g": "f", "born": "2021", "late": true, "notes": "…",
  "spouse": { "name": "…", "g": "m" },
  "children": [ … ] }
```

`g` is `"f"` (female), `"m"` (male) or `"u"` (not recorded). `late: true` marks someone who has passed.
