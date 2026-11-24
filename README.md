# stocktake

A simple tap-to-count stocktake for a small number of categories, designed for a phone. A sibling of [quicktill](https://github.com/richardswinbank/quicktill).

- **Count** – one big button per category. Tap to add one to its count. Use the − on a button to take one off, or **Undo last tap** to reverse the most recent tap.
- **Summary** – the count for each category and the overall total. **Share counts** sends them as text (or copies them), and **Reset** sets every count back to zero for a new stocktake.
- **Setup** – add, rename, reorder and delete categories.

Everything is stored on the phone itself (browser local storage). There is no server and no account, and it works offline once it has been opened once.

## Putting it on a phone

It is a static site with no build step, so it can be hosted anywhere that serves files over HTTPS. With GitHub Pages: repository **Settings → Pages → Deploy from a branch → main / root**, then open `https://<user>.github.io/stocktake/` on the phone and choose **Add to Home Screen**.

Other apps hosted on the same `github.io` account share its local storage and cache storage, so stocktake prefixes its storage keys with `st.` and its caches with `stocktake-`, and only ever clears its own.

## Running locally

```bash
python -m http.server 8001
```

After changing any file, bump `CACHE` in `sw.js` so phones pick up the new version.
