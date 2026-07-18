# Public Assets Repository

Supports the Panama City Youth Orchestra website in two ways:

- Hosts public PDF files, uploaded through GitHub Releases for stable, permanent download links.
- Hosts `site-config.json`, a small file the website reads at runtime so certain content (tuition, performance dates, audition visibility, etc.) can be updated without redeploying the website itself.

## Editing Site Content Without Redeploying

`site-config.json` (in the root of this repo) mirrors part of the `SITE_CONFIG` object in the website's `components.js`. The website fetches this file at runtime, served through GitHub Pages, and overlays it on top of its local defaults — so editing a value here updates the live site without a Netlify redeploy. Values are cached in each visitor's browser for 20 minutes, so changes may take up to 20 minutes to appear for someone who already has the site open.

To make a change: edit `site-config.json` directly on GitHub (or clone/push), commit to `main`, and wait for GitHub Pages to redeploy (usually under a minute).

| Field | Purpose |
| --- | --- |
| `contactEmail` | Email address used for `mailto:` links site-wide |
| `donationFormUrl` | Link target for donation buttons |
| `feedbackFormUrl` | Link target for feedback form |
| `mailingAddress` | Physical mailing address shown in the footer/contact page |
| `tuitionIndividual` | Tuition cost (USD/year) for a single student |
| `tuitionFamily` | Tuition cost (USD/year) for two+ students from the same family |
| `upcomingPerformance` | Object with the next performance's season, tagline, date, times, venue, admission info, and program highlights |
| `revealAuditions` | `true`/`false` — shows or hides the audition PDF download links on the Join page (see below) |

Security note: even when `revealAuditions` is `false`, a determined user could still find the PDF links by digging into the browser inspector. As such, it's a good idea to **not** upload the actual audition files to the release until you're ready to set `revealAuditions` to `true`.

## Uploading Audition PDFs (Legacy)
*No longer used for providing assessment files. Links are now stored in `site-config.json`.*

1. Go to the [Releases page](https://github.com/Panama-City-Youth-Orchestra/public-assets/releases).
2. If a release already exists with a tag of "v1", skip to step 5. Otherwise, click **Create a new release**.
3. Select the "v1" tag.
4. Give the release a title (doesn't matter what the title is).
5. Scroll to **Assets**.
6. Remove any current PDFs.
7. Click **Attach binaries by dropping them here or selecting them.**
8. Select the audition files (should be 3: violin, viola, and cello).
9. Verify that only 3 files exist and that they are named `violin.pdf`, `viola.pdf`, and `cello.pdf`.
10. Click **Update release**.

## Notes

- If wanting to add or remove supported instrument types for auditions, such as guitar, flute, piano, etc., the website will need to be updated to reflect this change. It currently only supports 3 instruments.
- Both uploading PDFs and editing `site-config.json` can be done entirely through GitHub's web interface — no Git or code required.

If something doesn't look right, contact the site administrator.
