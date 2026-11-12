# Tlou Family Tree

An interactive website for the Tlou family tree (from the chart dated 13 Nov 2022): 103 people across seven generations.

- **`index.html`**: the website. It is one file with no other files needed. Open it in any browser.
- **`Tlou-Family-Tree.docx`**: a printable Word version (family lines plus a table for each generation).

## What the site does
- Click anyone to see their parents, partner, brothers and sisters, children and grandchildren. Every name in the panel is clickable, so you can move from one relative to the next. **Back** returns to the last person you viewed.
- **How are we related?** Pick a second person to get the relationship (for example "first cousin once removed" or "great-aunt-in-law"). The path between the two people is highlighted on the tree.
- Search by name, drag to move around, scroll or pinch to zoom, and fold or open branches.
- Each person has their own link (for example `index.html#42`), so you can send someone straight to a relative.

## Free hosting

### Option A: GitHub Pages (recommended)
1. Make the repository **public**. On a free account, Pages only works for public repositories.
2. Open **Settings → Pages**. Under "Build and deployment", choose **Deploy from a branch**, then pick the branch and `/ (root)`. Click **Save**.
3. After about a minute the site is live at `https://<your-github-username>.github.io/thamaga/`.

### Option B: Google Sites
1. Go to <https://sites.google.com> and create a blank site.
2. Choose **Insert → Embed → By URL** and paste the GitHub Pages link from Option A.
   You can also use **Embed code** and paste the whole contents of `index.html`.
3. Resize the embed box so it fills the page, then click **Publish**.

### Option C: Google Docs
Upload `Tlou-Family-Tree.docx` to Google Drive and open it with Google Docs. Then use **Share** so family members can see it.

## Updating the tree
The family data is near the top of `index.html`, inside `window.FAMILY = {...}`. To add a person, add an entry like this to the right `children: [...]` list:

```js
{ name: "New Person Tlou", g: "f" }   // g: "f" female, "m" male, "u" not recorded; add  late: true  for someone who has passed
```

To add a partner, use `spouse: { name: "...", g: "m" }`.
