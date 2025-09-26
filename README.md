# Silavind Extended

A minimalist single-page Hugo theme customized for portfolio and blog websites. Features responsive design, multi-language support, and integrated comment.

Built upon the foundation of [Silavind](https://github.com/khitezza/silavind).

> [!NOTE]
> This is a customized repository, not the core Silavind Extended Theme.
>
> - **Core theme**: [Silavind](https://github.com/khitezza/silavind)
> - **Extended theme**: [Silavind Extended](https://github.com/thnhan1/silavind)

## 🌐 Live Demo

Check out the live demo: **[Demo Blog](https://nhanab.xyz)**

<img width="640" height="468" alt="Silavind Extended Theme Preview" src="https://github.com/user-attachments/assets/ba05346d-d8a2-485d-b18b-9922fc4914ae" />

---

## ✨ Features & Enhancements

| Feature | Type|Description | Date | Status |
|---------|--|-------------|------|--------|
| **Comment System Localization** |Fix| Fix Language In Comment Section | 2025-09-26 | ✅ Complete |
| **Giscus Integration** |Feat| GitHub-based comment system via [Giscus](https://giscus.app) | 2025-08-09 | ✅ Complete |
| **Responsive Navigation** |Feat| Mobile-optimized menu with smooth animations | 2025-08-20 | ✅ Complete |
| **Enhance Multi-Language Support** |Feat| Internationalization (i18n) capabilities | 2025-08-20 | 🔄 In Progress |
| **Code Copy Functionality** |Feat| One-click copy button for code blocks | 2025-08-20 | 🔄 In Progress |
| **Hugo Compatibility** |Feat| Updated for Hugo v0.124.0+ parameter structure | 2025-08-19 | ✅ Complete |

---

## 🚀 Quick Start

### Prerequisites

Ensure you have the following installed:

- **[Git](https://git-scm.com/)** - Version control system
- **[Hugo Extended](https://github.com/gohugoio/hugo/releases)** - Static site generator (v0.124.0+)

> 💡 **Note for Windows users:** Download Hugo Extended (not the standard version) from the [official releases page](https://github.com/gohugoio/hugo/releases).

---

### Installation

#### 1. Create New Hugo Site

```bash
# Create a new Hugo site
hugo new site my-blog
cd my-blog

# Initialize Git repository
git init
```

#### 2. Add Silavind Theme

Install as a Git submodule:

```bash
# Add theme as submodule
git submodule add https://github.com/thnhan1/silavind themes/silavind
git submodule init
```

#### 3. Update Theme

Keep your theme up-to-date:

```bash
# Update to latest version
git submodule update --remote --merge
```

---

## 📝 Content Management

### Creating New Posts

#### Simple Article
- Create a new post.

```bash
hugo new writings/YYYY-MM-DD/post-name.md
```

- Create a new post with language.

```bash
hugo new writtings/YYYY-MM-DD/post-name.lang.md
# example: hugo new writtings/YYYY-MM-DD/post-name.en.md
```


#### Article with Images (Page Bundle)
```bash
# Create post with dedicated folder for assets
hugo new content/writings/2025-01-01-my-first-post/index.md

# Add images to the same folder
cp ~/images/featured.webp content/writings/2025-01-01-my-first-post/
```

### Folder Structure
```
content/
├── writings/
│   ├── 2025-01-01/post-one.md # single language
│   └── 2025-01-02/ # multi post, multi language
│       ├── post-1.en.md
│       └── post-1.vi.md
├── about/
│   └── index.md
└── projects/
    └── index.md
```
### Media, Image Embed
Folder: `assets/assets/imgs/your-image.png`

Embed image in markdown
```md
![alt text](/assets/imgs/your-image.png)
```

### Relate Post Feature
Add relate post or read more post by using frontmatter (using folder and file name of other post).
```md
+++
date = '2025-09-26T10:15:09+07:00'
draft = false
title = 'Current Post'
readmore=['YYYY-MM-DD/other-post-1']
+++
```

---

## 🌐 Deployment Options

> ⚠️ **Important**: GitHub Pages disables inline scripts due to Content Security Policy (CSP).

### Netlify Deployment (Recommend)

Create `netlify.toml` in your project root:

```toml
[build]
  publish = "public"
  command = "hugo --gc --minify"

[context.production.environment]
  HUGO_VERSION = "0.148.2"
  HUGO_ENV = "production"
  HUGO_ENABLEGITINFO = "true"
```

Then connect your **GitHub** repository to [Netlify](netlify.com) for automatic deployments.
Your Website will serve in free doamain example: `your-blog.netlify.app`

---

## 🔧 Configuration

### Basic Setup

Update your `hugo.toml`:

```toml
languageCode = 'vi'
defaultContentLanguage = "vi"
title = 'Nhan Blog'
theme = 'silavind'
pagination.pagerSize = 5
hasCJKLanguage = true
enableEmoji = true
# Allow html tag
enableHTML = true
enableInlineShortcodes = true
taxonomies.tag = "tags"
# disableKinds = ["section", "taxonomy", "term"]
name = 'Huu Nhan'
license = 'GPL-3.0-or-later'
licenselink = 'https://github.com/ertzizart/silavind/LICENSE'
description = 'A simple blog and simple life notes.'
tags = ["blog", "responsive", "clean", "light", "dark"]
features = ["blog", "darkmode", "single-column", "responsive"]
min_version = "0.147.0"

[author]
name = 'Huu Nhan'
homepage = 'https://nhanabc.xyz'



[params]
disableHeroVideo = true
intro="Life is short, Live it well"
# =================Social====================
[params.social] 
[[params.social.links]]
name= "GitHub"
url ="https://github.com/thnhan1"
[[params.social.links]]
name= "LinkedIn"
url ="https://www.linkedin.com/in/trannhan10/"
#=================Social end====================

#===================Projects start==============
[params.projects]
[[params.projects.links]]
name = "Plant Shop Website"
url = "#"
desc = "Spring MVC project in subject ESD"
start_date = "2024-06-07"
license = "GPL-3.0-or-later"

[[params.projects.links]]
name = "Restaurant Reservation System"
url = "https://thnhan1.github.io/ebooking.git/"
desc = "Fullstack web application for chain restaurant booking module"
start_date = "2025-04-08"
# license = ""

#=================Projects end====================

#=============style editor===========
[markup]
[markup.goldmark]
[markup.goldmark.renderer]
unsafe = true
  [markup.goldmark.extensions]
  footnote = true
  typographer = true
  [markup.highlight]
  style = "onedark"
  guessSyntax = true
  lineNumbersInTable = true
  tabWidth = 4
#=============style end=========

#================languages==============
[languages]
[languages.en]
languageName ="English"
languageCode= "en"
weight=2

[languages.vi]
languageName ="Tiếng Việt"
languageCode= "vi"
weight=1

#=================Header start=============
[params.header]

  [[params.header.links]]
  name = "home"
  url = "/"


  [[params.header.links]]
  name = "projects"
  url = "/projects/"

  [[params.header.links]]
  name = "about"
  url = "/about/"
#=================Header end=============

```

### Advanced Features
Because I keep core themem minimal, these features only include in implement of theme.
- **💬 Comments**: Integrated via [Giscus](https://giscus.app)
- **📱 Responsive Design**: Mobile-optimized navigation
- **🌍 Multi-Language**: i18n support for international sites
- **📋 Code Copying**: One-click copy functionality for code blocks

---

## 📄 License

This project is licensed under the [GNU General Public License v3.0](https://github.com/ertzizart/silavind/blob/trunk/LICENSE).

## 🤝 Contributing

We welcome contributions! Here's how you can help:

- **🐛 Found a bug?** → [Open an Issue](https://github.com/thnhan1/silavind/issues)
- **💡 Have a feature idea?** → Create an issue with the `enhancement` label
- **🔧 Want to contribute code?** → Fork the repo and submit a pull request


