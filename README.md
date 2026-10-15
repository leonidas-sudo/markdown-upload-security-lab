# Markdown Upload Security Lab

A static, browser-only practice website intended for authorized security testing and GitHub Pages hosting.

## Features
- Client-side filename/MIME observation for `.md`, `.markdown`, and `.pdf`
- Safe text/Markdown preview that escapes raw HTML
- Optional raw-HTML preview inside a sandboxed iframe without `allow-same-origin`
- Sample Markdown payloads and a checklist for follow-up tests

## Deploy to GitHub Pages
1. Create a new GitHub repository (for example, `markdown-upload-security-lab`).
2. Upload `index.html`, this `README.md`, and the `samples/` folder to the repository root.
3. Open **Settings → Pages**.
4. Under the build/deployment section, choose **Deploy from a branch**.
5. Select the `main` branch and `/ (root)`, then save.
6. Wait for GitHub Pages to publish the site and open the URL shown in Settings → Pages.

## Important limitations
This is a static frontend. It does not upload files to a server, persist documents, parse PDFs, perform server-side URL fetching, access internal networks, or demonstrate SSRF. Use a backend lab you control for those tests.

The isolated preview deliberately uses a sandboxed iframe to reduce risk when hosted publicly. Do not turn this into an unsandboxed public XSS demo. Only test systems for which you have explicit authorization.


## Add your deployed AI agent widget
The `index.html` includes the widget script details visible in the screenshot. The `data-key` was transcribed from the screenshot, so verify it against the exact snippet using the app's **Copy** button before publishing.
1. Open `index.html` and find the widget script near the bottom.
2. Compare it with the exact snippet copied from your agent deployment screen; replace the script block if any character differs.
3. Commit the change and wait for GitHub Pages to redeploy.
4. Visit the public site and confirm the chat bubble loads.

Because the agent is set to **Anyone with the link**, anyone who can access the published page may be able to chat with it. Avoid exposing secrets or private knowledge-base content, and use a test agent with non-sensitive data.
