DG IT Point — Cinematic Video Section Update (v4)

Implemented in index.html:
- Replaced the previous scattered spotlight overlays with one centered overhead lamp/fixture, one broad warm-gold light cone, a soft floor reflection, and subtle reflected light across the two video frames.
- Kept the premium DG IT Point black/purple/gold palette, transparent card surfaces, animated border, soft 3D depth, and removed the old multiple-triangle/extra decorative spotlight treatment.
- Locked both desktop cards to the same width and card-height system, both video windows to the same 9:16 portrait ratio, and added a wider desktop gap. Smaller screens stack the cards cleanly.
- Kept only the two requested titles under the videos: “Introducing DG IT Point” and “Thank You, Amreli & Gujarat Social Media”.
- Added a top-right expand control and made clicking the video frame open a premium lightbox/modal with a large portrait player, native timeline controls, custom Play/Pause and Sound On/Off buttons, close button, Escape-to-close, backdrop-to-close, focus return, and a viewport-safe mobile layout.
- Preserved muted viewport-based inline autoplay, looping, and the existing rule that only one inline video should have sound at once. Inline videos pause while the modal is open and resume according to visibility/user pause state after closing.
- Did not embed the supplied stock spotlight photo because it contains a watermark; the lamp and light effects are original CSS.
- Kept the rest of the website content and existing SEO setup unchanged; this update only changes the video section, its controls, and update documentation/manifest.

QA performed:
- DOM/structure checks: one video section, exactly two video cards, one lamp fixture, one light cone, two expand controls, one modal, required titles intact, no duplicate element IDs.
- Responsive layout smoke test in an isolated browser preview using the real section HTML/CSS and the supplied poster images: desktop cards were equal at 380 × 744 px; both desktop video frames were 364 × 647 px (9:16). At 390 px viewport width, both mobile video frames were equal at 354 × 629 px.
- Modal interaction smoke tests: open from each card, close via Escape, close via backdrop, close button, mobile viewport fit, Sound On/Off state toggle, and restoration/close behavior all passed.
- No browser page errors were observed in the isolated UI preview.
- 11 inline JavaScript blocks passed Node syntax checks; 50 CSS style blocks parsed and the new v4 spotlight CSS had no parser errors; JSON-LD parsed successfully; no duplicate IDs.
- Both local MP4 and poster file paths exist. ffprobe confirmed the launch video is H.264/AAC, 720 × 1280, 25.379 seconds; the community video is H.264/AAC, 1080 × 1920, 41.28 seconds.

Validation scope / deployment note:
- The modal/interaction browser smoke test used a local isolated UI fixture with poster images; video source files were deliberately omitted from that fixture so modal behavior and layout could be tested independently. The actual MP4 files were separately checked for existence, codecs, dimensions and duration.
- No changes have been deployed to the live dgitpoint.com website. After upload, check the section on the production domain and confirm the hosting/CDN serves both MP4 files and posters correctly.
