# DG it Point v7 — Mobile Spotlight, Entity SEO, Image SEO and Performance QA

## Implemented
- Mobile-only grid gap increased from 54px to `clamp(92px, 16vw, 116px)`, so the second lamp and beam sit in the gap immediately before the second video card instead of overlapping the first card title. Desktop spotlight CSS is unchanged.
- Kept existing poster/video source files unchanged; no video transcoding or image recompression in this update.
- Reduced eager network activity by changing video IntersectionObserver rootMargin from `80px 0px` to `0px`, retaining autoplay when a card actually enters the viewport.
- Added a dedicated indexable founder profile at `/founders/priyanshu-gajera.html`, with `ProfilePage`/`Person` structured data and the verified public portrait.
- Added a dedicated press coverage archive at `/press-coverage.html` with the 23 original press-gallery JPEGs, descriptive alt text, captions, `CollectionPage` and `ItemList` metadata. It explicitly labels the images as press clippings/company media, not articles published by DG it Point.
- Added contextual internal links on the existing founder name and “News & Media” heading without changing the displayed text.
- Updated `sitemap.xml` with the founder and press archive URLs plus image titles/captions; added the page/image relations for press imagery. Updated `llms.txt` and added explicit AI-search crawler access groups while preserving existing `GPTBot` and `ClaudeBot` training opt-outs.

## Preservation
- Existing homepage text and section content were not rewritten. The two MP4 video files and original JPEG images were not recompressed, cropped, or replaced.
- No fabricated `uploadDate`, publication date, publisher, press byline, certification, search ranking or customer evidence was added.

## Validation done locally
- Parsed 8 HTML pages.
- Parsed all 5 JSON-LD script blocks as JSON.
- Syntax-checked 12 inline JavaScript blocks with Node.js.
- Parsed all 59 inline CSS style blocks; no top-level CSS parser errors were reported.
- Parsed the sitemap XML; 7 page URLs, 66 image references and 2 video sitemap entries validated.
- Confirmed the press archive contains 23 original image files and the ProfilePage mainEntity points to Priyanshu Gajera.
- Checked local asset references and sitemap URLs; 0 missing references.
- Checked duplicate HTML IDs; none found.
- Checked source assets remain byte-identical to the v6 archive inputs (no image or video recompression).
- Checked final ZIP CRC integrity.
- Browser visual testing could not be completed in this environment because Chromium navigation was blocked by the environment (`ERR_BLOCKED_BY_ADMINISTRATOR`), so the mobile spacing still needs a final staging/device visual check.

## Important limits / remaining owner actions
- Google Search Console, Bing Webmaster Tools, Google Business Profile, and AI citation/rankings could not be accessed from this local source-editing environment. Submit updated `sitemap.xml` and `video-sitemap.xml` after deployment, then request indexing for the homepage, founder profile, press archive and both video watch pages.
- No Google News sitemap/article markup was fabricated: the 23 assets are press-clipping images, not independently authored articles with verified publishers, bylines and publication dates. Publish real dated editorial updates only when those details are verified.
- Google Video rich-result markup requires the actual first-publication `uploadDate`; it is omitted until the owner confirms the original publication date for each video.
- Rankings and image/video indexing are controlled by Google and other services; implementation increases discoverability but cannot guarantee placement or timing.
