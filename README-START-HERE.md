# The Word Only Deliverance Ministry — website & secure editor

Your official crest is stored at `assets/church-crest.png`. The design uses green, gold and black. The two independent prayer schedules are in `content/site.json`.

## A. First preview

Open `index.html` in your browser for a quick design preview (using the default starter content). For a preview that loads current edits from `content/site.json`, run a local server from this folder, e.g. `python -m http.server 8000`, then visit `http://localhost:8000`.

## B. Publish and activate the secure dashboard

1. Create a GitHub account (enable two-factor authentication). Create a **new repository** such as `word-only-ministry-website`. This site contains only public information; choose *Public* for straightforward publishing. Never store prayer submissions, passwords, or member records in this repository.
2. Upload **all contents** of this folder, including hidden `.pages.yml`, to the repository root (not an outer folder). GitHub's website upload sometimes hides dotfiles in file pickers; verify `.pages.yml` is present after upload, or add it separately using GitHub's Create new file action.
3. Sign in at https://app.pagescms.org with GitHub, install/authorize the Pages CMS GitHub App only for this repository, open the repository. The **Church Website Content** editor is defined by `.pages.yml`. Only authorized GitHub users/collaborators should receive edit access.
4. In Netlify https://app.netlify.com, choose **Add new project > Import an existing project** and connect the same GitHub repository. Set the publish directory to `.` (repository root), with no build command. Netlify will provide a public `.netlify.app` URL.
5. Edit content at https://app.pagescms.org > your repository > **Church Website Content**. Save. Pages CMS commits the edited JSON/media to GitHub; Netlify automatically publishes changes from the connected branch. Check Netlify's Deploys tab if a change doesn't show up.
6. Optionally buy a domain and add it under **Netlify > Domain management**. Registration/domain costs are separate from free hosting tiers. Verify the final hostname before placing it on Google Business Profile or flyers.

## C. What is editable

Church name, tagline, descriptions, leadership, address, phone, email, Sunday service, Bible study, **two prayer times**, livestream URL, secure giving URL, prayer request form URL, events, and gallery images/captions. Photos are uploaded through Pages CMS to `assets/uploads`.

## D. Important security notes

- **Do not put a username/password into `index.html`**. Editing is authenticated through Pages CMS / GitHub. Use strong passwords and GitHub two-factor authentication.
- The published website has no public admin form or password to guess. GitHub access permissions control editor access. Only invite trusted staff.
- Only HTTPS livestream, giving, and prayer form links are accepted by the website. Giving must use a legitimate payment provider; **never collect card details directly in this static site**.
- Prayer request submissions are intentionally **not implemented** until you configure a privacy-conscious form provider. Avoid displaying private prayer requests or collecting sensitive health information publicly.
- Gallery images and all text in this repository are PUBLIC. Only upload approved public photos, preferably with participant consent.
- The hosted website reads updated `content/site.json` on each page load. A `file://` HTML preview shows starter content only, because browsers typically block local JSON fetches.

## E. Troubleshooting

- Site shows old content: confirm Pages CMS saved to the branch Netlify deploys, then refresh (Ctrl+F5) and check Deploys.
- CMS missing: ensure `.pages.yml` is in GitHub repo root and Pages CMS is authorized for this repository.
- Logo missing: ensure `assets/church-crest.png` exists in repository.
- Photo missing: upload through Pages CMS; don't use personal computer file paths.
- Download failing in ChatGPT: ask ChatGPT to paste the files directly, or use a GitHub-connected workflow.

Links: https://pagescms.org/docs/quick-start/ | https://docs.netlify.com/ | https://github.com/
