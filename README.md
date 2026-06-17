# Beyond Timelines Portfolio

A premium, cinematic wedding video editing portfolio website featuring a scroll-linked frame animation intro, autoplay showcase video banner, and interactive filtering grid.

## Deployment on Vercel

To deploy this website to Vercel:
1. Connect your GitHub repository `beyondtimelines` to Vercel.
2. Vercel will automatically detect the static project and deploy it.

---

## Video Hosting Configuration

Because GitHub restricts file sizes to **100MB** and Vercel limits total deployment size to **325MB–500MB**, the **6.2GB** of raw `.mp4` video files in this project are excluded from git via `.gitignore`. 

For the deployed site to show videos, you should host them on a high-speed video hosting provider or CDN, and update the sources in `index.html`.

### Recommended Hosting Solutions
* **Vercel Blob**: Directly integrated with Vercel, optimized for streaming media.
* **AWS S3 + CloudFront CDN**: Highly scalable and cost-effective.
* **Cloudinary**: Supports automatic optimization and responsive streaming.
* **Vimeo / YouTube**: If embedding or using custom player controls (requires changing `<video>` tags to iframe embeds).

### Updating URLs in `index.html`

Search for `.mp4` in `index.html` and replace the local filenames with your hosted URLs:

1. **About Me Video** (line 113):
   ```html
   <!-- Replace 'ap_wedding_reel.mp4' with your hosted URL -->
   <video class="about-video" src="https://your-cdn.com/ap_wedding_reel.mp4" autoplay loop muted playsinline></video>
   ```

2. **Featured Portfolio Video** (line 206):
   ```html
   <!-- Replace 'hhhhhh.mp4' with your hosted URL -->
   <video id="featured-portfolio-video" src="https://your-cdn.com/hhhhhh.mp4" autoplay loop muted playsinline style="pointer-events: none;"></video>
   ```

3. **Portfolio Grid Videos** (lines 220–266):
   Update the `data-video` attribute on each `.portfolio-item` card:
   ```html
   <div class="portfolio-item" data-category="wedding-highlights" data-video="https://your-cdn.com/gautam_mehek.mp4">
   ```
