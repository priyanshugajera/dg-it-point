# DG it Point v8 — Video structured data and founder entity SEO QA

## Changes
- Added the required `uploadDate` property to both VideoObject JSON-LD entities.
- Added video publication date metadata to `video-sitemap.xml`.
- Created dedicated, indexable profile pages for Gamara Karan and Dhrumil Dhanani using the existing premium profile design.
- Added Person, ProfilePage and BreadcrumbList structured data to both new founder pages.
- Added the founder profile URLs and portrait image references to `sitemap.xml`.
- Added all three founder profile URLs to `llms.txt` for clearer entity discovery.
- Original image and MP4 files were not recompressed or modified.

## Date note
The `2026-10-16` upload/publication date was inferred from the supplied archive timestamp for the video files. Confirm this matches the actual first-publication date before deployment; if it does not, replace it with the true date.

## Validation
- Video pages: both JSON-LD blocks parse as JSON and contain `uploadDate`.
- Founder pages: profile pages contain valid JSON-LD and canonical URLs.
- Sitemap XML parses and includes all three founder profile URLs.
- All source image/video assets are preserved.
- Search Console video indexing still depends on Google's recrawl and video eligibility; no ranking or indexing guarantee is implied.
