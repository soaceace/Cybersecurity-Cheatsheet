# Cybersecurity study site

Two linked, offline study pages:

- **index.html** — Security+ SY0-701 cheatsheet (SOC Tier 1 study kit). Loads at your site's root.
- **netdef.html** — Network Defense cheatsheet (study-kit format: detail view per term, flashcards, and a scored quiz).

Each page has a link to the other in its header, so you can move between them.

## Put it on GitHub (replacing the page you already host)

1. Open your existing GitHub repo (the one serving your Security+ page).
2. Click **Add file > Upload files**, then drag in `index.html` and `netdef.html`.
   - Uploading `index.html` overwrites the old root page, so your hosted URL now shows this version.
3. Commit the change.
4. Confirm **Settings > Pages** still points at your branch and **Enforce HTTPS** is on.
5. Give it a minute, then load your Pages URL. The Network Defense link should open `netdef.html`.

The two files must sit in the **same folder** in the repo, because the header links are relative (`netdef.html` and `index.html`).

## Add a new module when class unlocks one

You only edit `netdef.html`. Find the comment block `HOW TO ADD A NEW MODULE` at the top of the `<script>`.

1. Add a line to the `MODS` array: the next number, a short code, a name, and the next spare color (`--m6`, `--m7`, `--m8` are already defined):
   ```js
   {n:6,code:"M6",name:"Cryptography",v:"--m6"},
   ```
2. Append terms to the `T` array. Only `t`, `m`, and `d` are required:
   ```js
   {t:"AES", m:6, d:"Symmetric block cipher used by WPA2 and most modern encryption."},
   ```
   Optional extras per term: `x` (deeper explanation), `tip` (exam tip), `c` (a command), `rel` (related term names).
3. Save and re-upload `netdef.html` to GitHub.

The sidebar, filter chips, flashcards, and quiz all rebuild from `MODS` and `T` on their own, so nothing else needs changing. Progress and favorites are saved in your browser, not the file, so re-uploading does not erase them.
