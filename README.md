# prepdeck — public site

The landing page and legal pages for **PrepDeck**, an Android app that turns a job
description into the interview questions that role will actually ask.

**Live:** https://nabeelahmed314.github.io/prepdeck/

| Page | Purpose |
|---|---|
| `index.html` | Landing page — what the app does, screenshots, feedback form |
| `privacy_policy.html` | Privacy policy. **Filed with Google Play — see below** |
| `terms.html` | Terms of service |
| `data-safety.html` | Unlisted. A readable copy of the Play Data safety answers; not linked from anywhere |
| `styles.css` | One stylesheet, shared by every page |
| `assets/` | App icon and the five store screenshots |

Static HTML and CSS. No framework, no build step, no JavaScript, no external requests —
every page works opened straight from disk.

## Do not move or rename `privacy_policy.html`

That exact URL —
`https://nabeelahmed314.github.io/prepdeck/privacy_policy.html` — is registered with Google
Play in three places:

1. the **Privacy policy** field on the store listing,
2. the **data deletion URL** inside the submitted Data safety form,
3. `KitConfig.PRIVACY_URL`, compiled into released builds of the app.

If it stops resolving, the Data safety declaration fails review and shipped apps link to a
dead page. Renaming the file, moving it into a folder, or turning off GitHub Pages all break
it. The page content can be edited freely; the path cannot.

## Editing

Source of truth for these files is the app repo (private), under `landing/`. The privacy
policy itself is generated there from `playstore/privacy_policy.md`, so edit it at the source
and re-copy rather than patching the HTML here — otherwise the next regeneration silently
reverts the change.

Publishing is a plain commit to `main`; GitHub Pages serves the repository root and takes a
minute or so to rebuild.
