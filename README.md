# educationblog

My education blog.

## Development Instructions

General Instructions:

* Add markdown files to content folder
* Manually deploy using deploy instructions

Deploy Instructions:

```bash
# compiles the site to docs folder
make publish

# checkout gh-pages branch
git checkout gh-pages

# update docs (site files)
git add docs/*
git commit -m "update site"
git push
```
