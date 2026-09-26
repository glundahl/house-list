# House List

Static comparison page for a Charlotte-metro house shortlist — schools, Honeywell commute (855 S Mint / BoA Stadium), and golf access notes.

**Live:** https://glundahl.github.io/house-list/

Same pattern as [quiz-mechanic](https://glundahl.github.io/quiz-mechanic/): this folder is its **own git repo** (`github.com/glundahl/house-list`). Push `main` here; GitHub Pages serves the site. Continuity notes: `continuity/working-topics/house-list.md`.

## Local preview

Open via a tiny static server (`fetch` needs `http`, not `file://`):

```bash
npx --yes serve .
```

Then open the URL it prints.

## Update listings

1. Edit `data/homes.json` (add/edit a home object; keep `peakCommuteMin` / `Avg` / `Max` + `commuteOffPeak` in sync with the rush text).
2. Update `meta.updated` and add a `meta.caveats` line if the change needs a note.
3. Commit and push **this** repo’s `main` (not only the parent monorepo).

```bash
git add data/homes.json
git commit -m "Add/update listing …"
git push origin main
```

4. On the phone or browser: tap **Reload latest** until the build tag matches (listings-only deploys may keep the same `APP_BUILD` — hard-refresh still picks up new JSON).

## Update UI / filters / columns

1. Edit `index.html`.
2. **Bump `APP_BUILD`** near the top of the script (e.g. `2026-09-26e` → next date/letter). Phones use this to confirm cache bust.
3. If you touch the Priority table or Cards, keep the **Off-peak** column/badge (easy to lose when adding columns).
4. Commit, push `main`, then **Reload latest** on devices.

## Personal excludes

Checkboxes + “Hide excluded” save to **this device/browser only** (`localStorage`). They do not sync across phones or people. Clearing is local via **Clear my excludes**.

## Notes

- Commute times are estimates, not live GPS. Peak filter uses rush min/avg/max to Honeywell.
- Golf is access-type only (no quality score).
- Confirm school assignments with the district before offering.
- Prices and status change daily — verify on the listing link.
