# DG it Point — Mobile Spotlight, Performance & SEO Update (v5)

**Prepared:** 16 October 2026  
**Base:** user-provided `DG_IT_Point_Cinematic_Spotlight_Modal_v4.zip`  
**Scope:** Keep homepage visible copy unchanged; desktop spotlight design unchanged; fix mobile spotlight placement; improve discovery and media loading without lossy image/video re-encoding.

## Implemented

### Mobile and responsive UI
- Kept the existing desktop spotlight/stage-light CSS rules unchanged.
- At the existing 760px mobile breakpoint, hide the single shared stage light and show a dedicated CSS lamp + beam above each of the two video cards.
- Both mobile cards retain the same shared video card styling and 9:16 media ratio; increased mobile card-to-card gap.
- Preserved the existing launch/thank-you titles and video player controls; no additional visible descriptive copy was added to the homepage.

### Search discovery
- Created focused watch pages:
  - `/videos/dg-it-point-launch.html`
  - `/videos/thank-you-amreli-gujarat.html`
- Added `VideoObject` metadata to the homepage and each watch page, with canonical URLs, title, description, thumbnail, content URL, duration, publisher and language.
- Added `video-sitemap.xml` with entries for both videos and referenced it from `robots.txt`.
- Updated `sitemap.xml` to include the two watch pages plus 33 image references, including 23 newsroom/press gallery images and relevant brand/founder/mockup/video poster images.
- Updated image `alt` attributes to describe the image subject without changing user-visible captions or text.
- Kept an accurate Organization/Person relationship for DG it Point and founder Priyanshu Gajera, alongside existing co-founder entities. No claims about rankings, awards or client results were fabricated.
- Kept AI search crawler access separate from model-training crawler preferences: `OAI-SearchBot`, `ChatGPT-User`, `Claude-SearchBot`, and `Claude-User` are allowed; `GPTBot` and `ClaudeBot` are disallowed. This policy can be changed by the site owner if model-training access is desired; it is separate from search-crawler access.

### Media performance and preservation
- Created lossless WebP versions of the in-page DG it Point logo, mockup, and Karan founder image; verified pixel data remained exactly equal to the PNG originals. Original PNG files remain in the project for metadata/fallback uses.
- Added image dimensions, `loading="lazy"`, and `decoding="async"` where suitable for lower-page imagery.
- Remuxed both MP4 videos with `faststart` without video/audio re-encoding. H.264 video stream hashes matched the source stream hashes. Both videos fully decoded without errors in the media validation pass.
- Current media metadata:
  - Launch video: H.264/AAC, 720×1280, 25.379 seconds, about 9.28 MB.
  - Thank-you video: H.264/AAC, 1080×1920, 41.280 seconds, about 22.68 MB.

## QA results

| Check | Result |
|---|---|
| Homepage and 2 dedicated video pages present | PASS |
| Canonical/title metadata present on each page | PASS |
| Duplicate DOM IDs | 0 found |
| Homepage image elements missing `alt` attribute | 0 found |
| Homepage video elements | 2 found |
| Mobile-only spotlight elements | 2 found |
| JSON-LD parse | PASS on all 3 HTML pages |
| XML parse: `sitemap.xml` | PASS; 5 page URLs |
| XML parse: `video-sitemap.xml` | PASS; 2 video entries |
| Image sitemap references | 33 entries |
| Inline JavaScript syntax | PASS; 11 inline blocks checked |
| CSS parser validation | PASS; 53 inline style blocks checked, no parse errors |
| Local images, scripts, video and poster paths | PASS; no missing local paths found by static reference check |
| MP4 codec, dimensions and duration inspection | PASS |
| MP4 decode pass | PASS |
| Archive integrity | PASS; ZIP CRC tested after packaging |

## Important limitations / action still required

1. **Real upload date:** The original public upload date for each video was not supplied and is not embedded in the MP4 metadata. `VideoObject.uploadDate` has therefore not been invented. Add the true public upload date to the relevant VideoObject markup if available; Google may not grant the fullest video rich-result eligibility while required metadata is missing.
2. **Live search results cannot be guaranteed:** Sitemaps and structured data help discovery; they do not guarantee indexing, Google Images/Video/News inclusion, AI citations, or #1 ranking. Google Search Console and Bing Webmaster Tools access is required to submit sitemaps and observe indexing after deployment.
3. **Google News:** The current News & Media area is a gallery of press/news images, not a set of independently authored news articles. It was not mislabeled with fabricated `NewsArticle` schema. Google News inclusion depends on the content/publisher and Google's systems; image sitemap entries alone cannot force those images into Google News.
4. **Visual browser QA limitation:** Automated navigation/screenshot testing of the latest v5 build was blocked by the runtime's browser navigation policy (`ERR_BLOCKED_BY_ADMINISTRATOR`). Static code, asset, CSS, JavaScript, schema, sitemap, and media checks passed, but this report does not claim that final v5 browser rendering or click interactions were visually verified in the restricted environment. Recheck desktop and mobile after staging/deployment.
5. **Ranking scope:** The homepage's visible copy was deliberately preserved as requested. Competitive terms such as “IT company in India”, “best IT company”, AI development, ERP and software development generally need genuinely useful service-specific pages, verified case studies, legitimate external references and ongoing Search Console-led iteration. This package implements technical/media foundations, not a guarantee of top rankings for every query or AI tool.

## Official guidance consulted

- Google Search guidance for AI features and its generative-AI search optimization guide: https://developers.google.com/search/docs/appearance/ai-features and https://developers.google.com/search/docs/fundamentals/ai-optimization-guide
- Google Image Sitemaps: https://developers.google.com/search/docs/crawling-indexing/sitemaps/image-sitemaps
- Google Video SEO / VideoObject guidance: https://developers.google.com/search/docs/appearance/video and https://developers.google.com/search/docs/appearance/structured-data/video
