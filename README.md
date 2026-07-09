# BasicGym Riverside - Presale Pacing Tracker

A single static page. No build step, no dependencies, no framework.
The page has already been tested and runs with zero errors, so if a deploy is
failing it is the hosting setup, not the file.

## Files (put all of these at the repo ROOT)
- `index.html` - the tracker (HTML, CSS and JS in one file)
- `.nojekyll` - stops GitHub from trying to build with Jekyll
- `.github/workflows/deploy.yml` - deploys the file directly, no build
- `README.md` - this file

## Recommended: deploy with the included Actions workflow (no build)
1. Put every file above at the root of the repo, keeping the `.github/workflows/` folder.
2. Push to the `main` branch. (If your default branch is `master`, open
   `deploy.yml` and change `main` to `master`.)
3. Repo Settings > Pages > Build and deployment > Source: choose **GitHub Actions**.
4. Open the Actions tab, watch "Deploy static site to Pages" run green.
5. The live URL is on the Settings > Pages screen and in the workflow summary.

This path uploads the file as-is and never runs Jekyll, which removes the
usual cause of a failing Pages build.

## Simpler alternative (branch deploy)
If you would rather not use Actions: Settings > Pages > Source
"Deploy from a branch", branch `main`, folder `/ (root)`. The `.nojekyll`
file makes this serve the raw HTML with no build.

## If it still will not run, check these first
- The file must be named `index.html` and sit at the repo root, not in a subfolder.
  If it is in a subfolder like `pacing-tracker/`, the page lives at
  `your-site/pacing-tracker/`, not the root URL.
- Default branch name matches the workflow (`main` vs `master`).
- Pages "Source" matches the method you picked (GitHub Actions vs branch).
- Give it a minute after the green tick; first publish can lag.

## Notes
- Data saves per browser via `localStorage`, so it is a personal planning view.
- Seeded with the real starting point: 101 members on 9 July, target 2,000 by
  22 August, back-weighted weekly ladder. Adjust baseline, cost per sign-up and
  paid share in the settings panel.

## Other hosts (also zero build)
Netlify, Vercel or Cloudflare Pages: set build command to none and the publish
directory to the folder holding `index.html`. Or drag the folder onto
Netlify Drop for an instant link.
