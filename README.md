# DataTorrent Documentation

DataTorrent documentation repository for content available on http://docs.datatorrent.com/


## Hosting Docs

Currently docs.datatorrent.com is hosted on Github Pages.  The deployment requires that a custom [CNAME](docs/CNAME) be present at docs level, and DNS entry for docs.datatorrent.com point to datatorrent.github.io.

## Deploying Docs

Deployment is done from master branch of the repository by executing the following command:

```bash
mkdocs gh-deploy --clean
```

This results in all the documentation under [docs](docs) being statically generatd into HTML files and deployed as top level in [gh-pages](https://github.com/DataTorrent/docs/tree/gh-pages).  For more details on how this is done see [MkDocs - Deploying Github Pages](http://www.mkdocs.org/user-guide/deploying-your-docs/#github-pages).



