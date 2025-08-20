# Silavind

A minimalist single-page Hugo theme + Customize for Porfolio

## Change logs

Change logs of theme, hugo version and addtion features.

|No.|Change| Description|Date|Status|
|--|--|--|--|--|
|4|Responsive menu |Add responsive menu for mobile|2025-08-20|finished|
|3|Multi language support|Add multi language support|2025-08-20|preview|
|2|Copy code block|Add custom css/js| 2025-08-20|preview|
|1|`.Site.Author` -> `.Site.Params.Author`| `>=v0.124.0` |2025-08-19|finished|

## 2. Usage

### 2.0 Before start

Make sure [Git](https://git-scm.com/) and [Hugo Extended](https://github.com/gohugoio/hugo/) are installed.

> 💡 **Windows users:**  
> Download and install the Hugo Extended version from the [release page](https://github.com/gohugoio/hugo/releases).

Create and enter `Website` folder and run the `git init` command:

```bash
git init
```

### 2.1 Add and Update Theme

Add theme by git submodule:

```bash
git submodule init
git submodule add https://github.com/thnhan1/silavind themes/silavind
```

And updated Theme:

```bash
git submodule update --remote --merge
```

### Content Management

Add a new common article:

```bash
hugo new content writings/20xx-xx-xx-Titile.md
```

Or easily manage images:

```bash
hugo new content writings/20xx-xx-xx-Titile/index.md
cp ~/images/cover.webp content/writings/20xx-xx-xx-Titile/cover.webp
```

## Deployments

[Github Actions Workflow](https://github.com/ertzizart/silavind/blob/pages/.github/workflows/gh-pages.yml)

If you have a domain, add `CNAME` and configure the domain dns settings.

```bash
echo "yourdomain.com" >> CNAME
```

Push to git platforms like Github.

```bash
git add .
git commit -m "first commit"
git branch -M trunk
git remote add origin https://github.com/your-name/repo-name.git
git push -u origin trunk
```

## Copyright

Licensed under [The GNU General Public License v3.0](https://github.com/ertzizart/silavind/blob/trunk/LICENSE)
