# Repository Guidelines

## Project Structure & Module Organization

This repository is a static personal CV/portfolio site served from `public/` and configured for Firebase Hosting in `firebase.json`. The main page is `public/index.html`. Project-specific styles and scripts live in `public/styles/main.css` and `public/scripts/main.js`. Vendor libraries are kept under `public/css/` and `public/js/`, including Bootstrap, Now UI Kit, jQuery, and AOS. Images and downloadable documents belong in `public/images/` or `public/assets/`; current CV PDFs are stored in `public/assets/`.

## Build, Test, and Development Commands

There is no package manager manifest or build pipeline in this repository. Edit the static files directly.

- `python3 -m http.server 8000 -d public`: preview the site locally at `http://localhost:8000`.
- `firebase serve --only hosting`: preview with Firebase Hosting behavior, including rewrites, if Firebase CLI is installed.
- `firebase deploy --only hosting`: deploy the `public/` directory to Firebase Hosting.
- `git status --short`: check pending changes before committing.

## Coding Style & Naming Conventions

Use two-space indentation in HTML, CSS, and JavaScript where practical, matching the existing static-site style. Keep custom code in `public/styles/main.css` and `public/scripts/main.js`; avoid editing vendored files in `public/css/` and `public/js/` unless updating the library itself. Prefer descriptive CSS class names that reflect page sections or components, and keep asset filenames readable, for example `cv-luis-ucan.pdf` or `profile-headshot.jpg`.

## Testing Guidelines

No automated test framework is configured. Validate changes manually by running a local preview and checking the main responsive breakpoints: mobile, tablet, and desktop. For JavaScript edits, verify browser console output is clean and that smooth scrolling and AOS animations still work. For content or asset updates, confirm links, images, and PDF downloads resolve from the deployed `public/` paths.

## Commit & Pull Request Guidelines

The current history uses short Spanish commit messages such as `se configuro firebase` and `se quito temporalmente el portafolio`. Keep commits concise and action-oriented; use either Spanish or English consistently within a change set. Good examples include `actualiza cv en assets` or `fix mobile navbar spacing`.

Pull requests should include a short summary, screenshots for visual changes, and any manual verification performed. Link related issues when applicable, and call out Firebase configuration or asset changes explicitly because they affect deployment behavior.

## Security & Configuration Tips

Do not commit Firebase credentials, private keys, or unpublished personal documents. Keep hosting configuration minimal in `firebase.json`, and verify new downloadable files are intended for public access before placing them in `public/assets/`.
