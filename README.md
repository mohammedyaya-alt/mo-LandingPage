# mo-LandingPage

Mohammed Arshad's portfolio site — a single self-contained `index.html` (inline CSS, no JavaScript, no external dependencies besides Google Fonts).

## Security

- Strict `Content-Security-Policy` (blocks all scripts, only allows Google Fonts for style/font, no remote images/frames/forms).
- `Strict-Transport-Security`, `X-Content-Type-Options: nosniff`, `X-Frame-Options: DENY`, `Referrer-Policy`, and a locked-down `Permissions-Policy`, enforced via [`vercel.json`](vercel.json) headers.
- No forms, no inline/external scripts, no user input handling — nothing on this page accepts or executes untrusted data.
- All external links (LinkedIn, GitHub) use `rel="noopener noreferrer"`.

## Deploy (Vercel)

1. Install the CLI once: `npm i -g vercel`
2. From this directory: `vercel` (first time links/creates the project), then `vercel --prod` to publish.
   - Or connect the GitHub repo at [vercel.com/new](https://vercel.com/new) for automatic deploys on push to `main`. No build step or framework preset is needed — root directory, static output.
3. Verify headers after deploy: `curl -sI https://<your-domain>` and confirm `content-security-policy`, `strict-transport-security`, etc. are present.
