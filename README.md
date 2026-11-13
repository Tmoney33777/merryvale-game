# Merryvale — Midnight Mischief (v8.2)

This repository is prepared to host the **Godot web/iPhone edition** of Merryvale. The original Steam Deck game remains a separate local project.

## Finish publishing from a phone or computer

**The actual game archive has not been uploaded yet.** The workflow in `.github/workflows/deploy-web.yml` is ready, but cannot build until the archive is uploaded.

1. Download **Merryvale.zip** (or **Merryvale-GitHub-Pages-Ready-v8.2.zip**) from your ChatGPT conversation. **Keep it zipped.**
2. In this GitHub repository, choose **Add file → Upload files**, select the ZIP, and commit it to **main**. Upload it to the repository root using either filename above; do not extract it.
3. Go to the **Actions** tab and open **Build and publish Merryvale**. GitHub will build the Godot web game using its own runner, so your Steam Deck does not need to export anything.
4. In **Settings → Pages → Build and deployment**, choose **GitHub Actions** as the source.
5. After both build and deployment complete successfully, get the live link from **Settings → Pages** or the deployment. Its expected URL format is `https://tmoney33777.github.io/merryvale-game/`; this is **not yet confirmed live**.

**Repository visibility:** This repository is currently **private**. GitHub Free requires a **public repository** for GitHub Pages; paid plans may support Pages for private repositories. If using Free, change visibility under Settings → General → Danger Zone → Change repository visibility. GitHub Pages sites are publicly accessible, so first ensure you have rights to share all assets.

## Technical details

- Godot version: **4.5.2**, using `barichello/godot-ci:4.5.2`.
- Game: Godot Compatibility renderer, single-threaded **Web** preset, potentially usable on iPhone Safari.
- Build outputs: the `merryvale-web-v8.2` downloadable workflow artifact, plus a GitHub Pages deployment.
- Uploading or replacing the named ZIP on `main` triggers a build automatically. You can also use **Run workflow** under Actions.
- This is a website/PWA, **not** an App Store iOS app.
- The browser build has **not yet been tested**; a successful export does not guarantee good iPhone performance.

## If the workflow fails

Open **Actions → Build and publish Merryvale → failed job → failed step** to see the underlying error. Missing export templates, Godot parser/import errors, or Pages setup and visibility can cause a failure.
