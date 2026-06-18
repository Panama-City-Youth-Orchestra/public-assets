# Public Assets Repository

Stores public PDF files for the Panama City Youth Orchestra website. Files are uploaded through GitHub Releases for stable, permanent download links.

## Toggling Audition Links in Website
The Join page in the website contains download links for the audition materials. Toggling the `revealAuditions` flag in `audition.json` between true and false will toggle visibility of the links without happening to deploy a new version of the website to Netlify.

Security note: Users can still discover the links by digging into the inspector. As such, it may be a good idea to **not** update the release with the correct audition files until we are ready to set the `revealAuditions` flag to `true`.

## Uploading Audition PDFs

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
- No Git or code required. Everything is done through the web interface.

If something doesn't look right, contact the site administrator.
