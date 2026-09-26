# House List

Static comparison page for a Charlotte-metro house shortlist — schools, Honeywell commute (855 S Mint / BoA Stadium), and golf access notes.

**Live (after Pages is on):** https://glundahl.github.io/house-list/

Same pattern as [quiz-mechanic](https://glundahl.github.io/quiz-mechanic/): push `main`, GitHub Pages serves the site.

## Local preview

Open `index.html` via a tiny static server (fetch needs http, not `file://`):

```bash
npx --yes serve .
```

Then open the URL it prints.

## Update listings

Edit `data/homes.json`, commit, push `main`. Hard-refresh the Pages URL.

## Notes

- Commute times are estimates, not live GPS.
- Golf is access-type only (no quality score).
- Confirm school assignments with the district before offering.
