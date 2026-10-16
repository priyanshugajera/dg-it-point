# DG it Point — Mobile Spotlight Spacing & Search Discovery Update (v6)

**Prepared:** 16 October 2026
**Base:** user-provided `DG_IT_Point_SEO_Mobile_Spotlight_Performance_v5.zip`
**Visible-copy constraint:** Existing homepage headings, captions and body copy remain unchanged. Only CSS, non-visible alt text/metadata, sitemap captions, the machine-readable `llms.txt` index, and internal project reports were updated.

## Implemented

### Mobile spotlight refinement
- Desktop spotlight CSS/layout rules remain unchanged.
- On mobile (760px and below), each video card has its own lamp and beam.
- Increased top breathing room by moving each mobile fixture upward and increasing stage top padding. Shortened each visible beam so it fades approximately 7–8 CSS pixels before the video card's outer top; the poster retains only a soft warm light spill.
- Increased the stacked mobile card gap and kept reduced-motion handling.

### Image SEO and AI retrieval
- Kept the existing image sitemap structure and URL list; all unique local image sources used by homepage `<img>` elements are represented in `sitemap.xml`.
- Rewrote alt text on 23 Gujarati press/gallery JPEGs to uniquely and accurately describe their visible subject without keyword stuffing. Visible card labels/captions did not change.
- Kept the image sitemap to current `image:loc` entries; Google has deprecated image sitemap title/caption tags, so descriptive context is supplied through the page text and each image’s useful alt attribute.
- Expanded the machine-readable `llms.txt` with a list of press-gallery image URLs and factual descriptions. This may help tools that read the file but is not a ranking guarantee or a Google-specific ranking feature.
- Added `fetchpriority="high"` to the first intro logo, a likely above-the-fold image. Existing below-the-fold newsroom images retain lazy loading and async decoding.

### Existing technical discovery setup retained
- Canonical URL and social metadata on the homepage and two dedicated video watch pages.
- `robots.txt` allows public search crawlers and keeps model-training crawler choices separate.
- Organization/Person JSON-LD, `VideoObject` markup, `sitemap.xml`, `video-sitemap.xml`, and two portrait video watch pages are retained.
- Did not label the press-image gallery as `NewsArticle`: these are gallery images/press clippings, not independently authored article pages with verified publication dates and author bylines.

## QA results (local source build)

Latest validation summary: {"html_files_parsed": 5, "jsonld_blocks_parsed": 3, "css_blocks_parsed": 55, "inline_js_blocks_checked": 11, "image_sitemap_entries": 33, "video_sitemap_entries": 2, "press_gallery_images": 23, "unique_press_gallery_alt": 23, "mobile_spotlight_elements": 2, "errors": []}


| Check | Result |
|---|---|
| Homepage and watch pages parsed | PASS — 3 HTML documents |
| JSON-LD parsing | PASS — 3 JSON-LD blocks parsed |
| Sitemap XML parsing | PASS — current image sitemap namespace parses; 31 image URLs |
| Video sitemap XML parsing | PASS — 2 video entries |
| Homepage `<img>` sources covered by image sitemap | PASS — no unmatched local image sources |
| Missing local image references | 0 found |
| Duplicate HTML IDs | 0 found |
| `<img>` without alt | 0 found (one intentionally empty hidden modal image has alt="") |
| Inline JavaScript syntax | PASS — no `node --check` errors |
| CSS parser | PASS — no parser errors from `tinycss2` |
| Desktop/mobile browser screenshot QA | NOT RUN: Chromium navigation is blocked by environment policy (`ERR_BLOCKED_BY_ADMINISTRATOR`) for both localhost and file URLs |

## Important external requirements and limits

1. Google Search Console and Bing Webmaster Tools account access is required to submit sitemaps, inspect URL indexing and request recrawls after deployment. The local ZIP cannot act on owner accounts by itself.
2. The two videos' original public upload dates are not supplied and are absent from MP4 metadata. `VideoObject.uploadDate` is therefore not invented. Google lists `uploadDate` as a required property for video rich-result eligibility; add the true first-publication date for each video if known.
3. Google Images/video sitemaps and structured data assist discovery but do not guarantee indexing or a search position.
4. The News & Media section is currently a gallery of press images. Google News/news surfaces require eligible editorial article content, transparent author/publisher details and real dates; a gallery image or image sitemap cannot force inclusion in Google News. No fabricated `NewsArticle` markup or news sitemap was added.
5. Competitive searches such as “best IT company”, “IT company in India” or worldwide terms cannot be guaranteed #1 by code. The homepage copy was deliberately kept unchanged as requested; sustained improvement also requires legitimate references, eligible business profile work, relevant service content and Search Console-led iterations.
6. Deploy the whole project after backup, then inspect mobile and desktop live, submit both sitemaps in Search Console and monitor indexing/performance.

## Official guidance
- Google Video SEO: https://developers.google.com/search/docs/appearance/video
- VideoObject structured data: https://developers.google.com/search/docs/appearance/structured-data/video
- Google News policies: https://support.google.com/news/publisher-center/answer/6204050/google-news-policies
- General structured-data guidelines: https://developers.google.com/search/docs/appearance/structured-data/sd-policies
