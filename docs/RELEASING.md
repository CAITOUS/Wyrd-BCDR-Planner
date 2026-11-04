# Releasing & update checks

Every copy of Wyrd has a version number (footer → **About & license**). Downloaded copies check a small public file, `wyrd.json`, each time they open, and show a banner when a newer version exists. The hosted copy on GitHub Pages is always current, so it doesn't check. No login or credentials are involved.

## One-time setup

1. Publish this repository. The update file must be publicly readable.
2. In `wyrd.json`, set `download` to your releases page, e.g. `https://github.com/CAITOUS/Wyrd-BDCR-Planner/releases/latest`.
3. In `Wyrd.html`, in the `WYRD` settings block in the script, set:

   ```js
   manifestUrl:"https://raw.githubusercontent.com/CAITOUS/Wyrd-BDCR-Planner/main/wyrd.json"
   ```

   Leave it as `""` to turn update checks off.
4. Turn on GitHub Pages: **Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)`**.

## Publishing a new version

1. In `Wyrd.html`, update `version` and `released` in the `WYRD` settings block.
2. Add an entry to `CHANGELOG.md`, headed `## <version> — <date>`.
3. Update `wyrd.json`:

   ```json
   { "latest": "1.1.0", "released": "2026-12-01", "download": "https://github.com/CAITOUS/Wyrd-BDCR-Planner/releases/latest", "notes": "One-line summary shown in the banner." }
   ```

4. Commit and push to `main`.
   - The hosted app on GitHub Pages updates within a minute or two.
   - The **Release** workflow sees a version that hasn't been released yet. It creates the `v1.1.0` tag and a GitHub Release with `Wyrd.html` and `wyrd-1.1.0.zip` (app, guides, license), using the CHANGELOG entry as the release notes.
   - Pushes that don't change the version don't create a release. To re-upload assets for the current version, run the workflow manually with **rebuild** ticked.

Copies with an older version show: *"Wyrd 1.1.0 is available. Get the update / Later"*.

## Moving the repository

Keep the old `wyrd.json` in place and replace its contents with:

```json
{ "moved_to": "https://raw.githubusercontent.com/NEW-OWNER/NEW-REPO/main/wyrd.json" }
```

Existing copies follow the pointer (up to three hops). New releases should use the new `manifestUrl`.
