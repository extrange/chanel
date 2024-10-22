# Shared Website

Our personal website.

Structure:

-   Blog
-   Stories
-   Trips

It will not be indexed by Google due to the presence of [`noindex` as a meta tag][google-noindex].

A [Github workflow][github-workflow] is set to trigger on pushes to the `master` branch, which will build and deploy the site to [Github Pages][github-pages].

## Serving

_We have moved away from devcontainers, to speed up loading time._

Ensure that you have [uv] installed on your system.

Run `uv sync` to sync dependencies.

Then, simply open the repo, and serve the blog by running `mkdocs serve`. You may have to close/reopen your terminal for the virtual environment to be activated.

[github-pages]: https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages
[github-workflow]: https://docs.github.com/en/actions/using-workflows/triggering-a-workflow
[google-noindex]: https://developers.google.com/search/docs/advanced/crawling/block-indexing
[uv]: https://docs.astral.sh/uv/getting-started/installation/
