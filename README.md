# Orbit - Space Quiz

Orbit is a self-contained space exploration quiz with ten questions about
planets, astronauts, and discoveries beyond Earth. Each attempt shuffles the
question order and includes illustrated questions, immediate answer feedback,
explanations, a final score, and a review of missed answers. The interface
supports light and dark color schemes, keyboard navigation, and accessible
progress and feedback.

**Website:** https://reblue-app.github.io/space-quiz/

## Run locally

Clone this repository and open `index.html` in a web browser. No installation,
build step, server, or external runtime dependencies are needed.

All markup, styles, quiz data, illustrations, and JavaScript live in `index.html`.
To check a change, open the file in a browser, answer questions, advance to the
results, and restart the quiz.

## Deployment

GitHub Pages uses GitHub Actions as its deployment source. The workflow in
`.github/workflows/pages.yml` prepares and uploads only `index.html` as the site
artifact; it does not publish repository documentation or configuration files.
Pull requests targeting `main` check artifact preparation without deploying.
Pushes to `main` automatically deploy the site through the `github-pages`
environment. The workflow can also be run manually from the Actions tab on
`main`.

Repository administrators can configure this under **Settings > Pages >
Build and deployment > Source > GitHub Actions**. Deployment status and logs
are available in the **Deploy GitHub Pages** workflow in the Actions tab.
