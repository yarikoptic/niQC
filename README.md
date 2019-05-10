# NeuroImaging Quality Control (niQC)

Repository for the niQC website.

## Basic Structure

This website is built over Gatsby, a static site generator. After each commit on branch `master`, it will rebuild the entire website with the new changes and deploy it to https://incf.github.io/niQC/

All the content is inside the folder `content` in Markdown format.

To create a new page, follow the structure of pages under `content/pages`. It requires a folder, containing an `index.md` file.
The `index.md` file may contain the page content, with the following header:

```markdown
---
path: "/about"
title: "About"
---
```

The `path` key indicates the URL for the page. In the example, the full URL will be: `https://incf.github.io/niQC/about`. A trailing slash is not required.

The `title` key indicates the page title, replicated on the page title tag (`<title>`) and in the beginning of the page.

Everything beyond the last `---` will be considered page content.

## How to collaborate

In order to suggest modifications, you need to open a pull request from your fork of this website. After proper review, your code will be merged into the `master` branch.

## Running locally using Docker

You can start a development server using Docker:

```bash
docker run -it -p 9000:9000 -v `pwd`:/opt/code -w /opt/code node:11.15.0 bash -c 'npm i; npm run develop'
```

This command will spawn a container, install the required dependencies for the project, and start the development server. You can access it at `http://localhost:9000`. The website content will be recompiled and refreshed every time a file is changed.
