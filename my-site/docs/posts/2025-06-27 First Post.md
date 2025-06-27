# 🚀 Building My Tech Blog with MkDocs and GitHub Actions

Today I officially launched the framework for my personal tech blog — a space where I'll be writing about the tools I use, projects I build, and lessons I learn along the way. In this first post, I’ll walk through how I set up the site using **MkDocs**, the **Material for MkDocs** theme, and deployed it automatically with **GitHub Actions**.

---

## 🛠️ Step 1: Setting Up MkDocs

I chose [**MkDocs**](https://www.mkdocs.org/) because it’s:
- Lightweight and fast
- Markdown-based (perfect for writing tutorials and notes)
- Easy to customize
- Excellent when paired with the [Material theme](https://squidfunk.github.io/mkdocs-material/)

To get started, I ran:

```bash
pip install mkdocs mkdocs-material
mkdocs new my-site
cd my-site
mkdocs serve
```

I moved the generated files into a GitHub repo and edited the `mkdocs.yml` configuration to use the Material theme and define sections for:
- Home
- About
- Posts (where this article lives)

---

## 🏗️ Step 2: Structuring the Site

My current project structure looks like this:

```
my-tech-blog/
├── docs/
│   ├── index.md        # Home
│   ├── about.md        # About me
│   └── posts/
│       └── first-post.md  # ← This post
├── mkdocs.yml
└── .github/
    └── workflows/
        └── deploy.yml     # GitHub Actions for deployment
```

I also enabled features in `mkdocs.yml` like navigation tabs and table-of-contents integration.

---

## 🚀 Step 3: Deploying with GitHub Actions

Instead of deploying manually each time, I configured GitHub to build and publish the site automatically using **GitHub Actions**.

Here’s what happens every time I push to the `main` branch:

1. GitHub creates a temporary **Ubuntu runner**
2. It checks out my repo, installs Python and MkDocs
3. It builds the site using `mkdocs build`
4. It runs `mkdocs gh-deploy --force` to push the site to the `gh-pages` branch

This is all controlled by a YAML file located at `.github/workflows/deploy.yml`.

GitHub handles the entire process automatically — I don’t need to run any deployment steps myself.

And when the process finishes, the Ubuntu runner is completely deleted. No servers to maintain. No costs involved (as long as the repo is public).

---

## 🌐 Going Live

Once the GitHub Pages settings were pointed to the `gh-pages` branch (root folder), the site went live at:

```
https://yourusername.github.io/my-tech-blog/
```

Eventually, I’ll hook up a custom domain too.

---

## 🧐 What I Learned

- **MkDocs** is super fast and intuitive for dev blogging.
- **GitHub Actions** gives you hands-off deployments with minimal setup.
- Hosting with **GitHub Pages is free**, reliable, and fast — great for personal projects and documentation.

---

## 💜 What’s Next?

In upcoming posts, I’ll be sharing:
- How to customize MkDocs with themes, plugins, and styling
- How I’ll embed YouTube videos into posts
- How I plan to monetize the blog (affiliate links, consulting, and more)

If you have questions about setting up MkDocs or want to see specific tutorials (monitoring tools, dev workflows, cloud configs), leave a comment on the companion YouTube video for this post!
