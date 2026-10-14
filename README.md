# VANTA Cinematic Studio

Web-only frontend at https://smimran-alt.github.io/AI-Video-Studio/

## Publish
In repository Settings → Pages, choose **GitHub Actions**. The workflow in .github/workflows/pages.yml publishes docs/. Check the Actions tab.

## Cloud backend
No GPU runs on GitHub Pages. Create a Hugging Face Gradio Space with an actual image-to-video model, expose a Gradio `/generate` endpoint that accepts inputs `image`, `prompt`, `negative_prompt`, `aspect_ratio` and returns a video file. Set `window.SPACE_URL = 'https://YOURNAME-YOURSPACE.hf.space'` in docs/config.js. This frontend requires that endpoint contract and won't generate videos until configured.

## Limitations
The UI is functional; generation is not enabled without a matching cloud backend. Hugging Face's free GPU allocations are finite. Reference-image reuse alone does not guarantee character consistency. Never embed private API keys in GitHub Pages.
