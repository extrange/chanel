# Shared Website

Our personal website.

Structure:

-   Blog
-   Stories
-   Trips

It will not be indexed by Google due to the presence of [`noindex` as a meta tag][google-noindex].

A [Github workflow][github-workflow] is set to trigger on pushes to the `master` branch, which will build and deploy the site to [Github Pages][github-pages].

[github-pages]: https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages
[github-workflow]: https://docs.github.com/en/actions/using-workflows/triggering-a-workflow
[google-noindex]: https://developers.google.com/search/docs/advanced/crawling/block-indexing
