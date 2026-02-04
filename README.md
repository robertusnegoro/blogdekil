# Jekyll Premium Blog Template

A simple, elegant, professional Jekyll blog template with readability-first typography, featured images, and configurable integrations. Compatible with **GitHub Pages** (Jekyll 3.10, Ruby 3.3.4).

## Features

- **Typography**: Source Serif 4 (body) and DM Sans (headings), modular scale, comfortable line length
- **Featured image**: Set `image` or `featured_image` in post front matter (relative path or full URL, e.g. Unsplash); optional `image_alt`
- **Authors**: Define authors in `_data/authors.yml`; reference in posts with `author: id`
- **Optional integrations** (off by default): Disqus, Google Analytics, ads (AdSense placeholder)
- **Plugins**: jekyll-paginate, jekyll-sitemap, jekyll-feed, jekyll-seo-tag
- **Optional**: jekyll-archives (use with local build or GitHub Actions; see below)

## Quick start

1. **Install dependencies** (Ruby 3.3.4):

   ```bash
   bundle install
   ```

2. **Run locally**:

   ```bash
   bundle exec jekyll serve
   ```

3. **Build**:

   ```bash
   bundle exec jekyll build
   ```

## Configuration

Edit **`_config.yml`**:

| Option | Description |
|--------|-------------|
| `name`, `title`, `description` | Site / blog name, page title, meta description |
| `url`, `baseurl` | Production URL and base path (e.g. `/blog` for project pages) |
| `logo`, `favicon` | Paths to logo and favicon (e.g. `/assets/images/logo.svg`) |
| `permalink` | Post URL pattern (e.g. `/:year/:month/:day/:title/`) |
| `include`, `exclude` | Files/dirs to include or exclude from the site |
| `disqus_shortname` | Disqus shortname (leave blank to disable comments) |
| `google_analytics` | GA4 measurement ID (e.g. `G-XXXXXXXXXX`) |
| `ads` | Set to `true` to show ad block; set `ads_client` and `ads_slot` for AdSense |
| `paginate`, `paginate_path` | Posts per page and path (e.g. `/page:num/`) |

### Authors

Add entries in **`_data/authors.yml`**:

```yaml
jane:
  name: Jane Doe
  display_name: Jane
  gravatar: "https://www.gravatar.com/avatar/abc123"
  twitter: janedoe
  description: "Writer and developer."
```

Reference in posts: `author: jane`.

### Kramdown

Markdown is rendered with **Kramdown** (GFM input, Rouge syntax highlighting). Options are in `_config.yml` under `kramdown:`.

### jekyll-archives (optional)

**jekyll-archives** is not on the GitHub Pages whitelist. To use it:

1. Uncomment `gem "jekyll-archives"` in **Gemfile**.
2. Uncomment the `jekyll-archives` plugin and `jekyll_archives:` config block in **`_config.yml`**.
3. Use **GitHub Actions** to build and deploy:
   - In the repo: **Settings → Pages → Build and deployment → Source**: choose **GitHub Actions**.
   - Disable “Build from branch” if it was enabled.
   - Push to `main`; the workflow in `.github/workflows/jekyll-pages.yml` will build and deploy.

If you do not need jekyll-archives, you can keep using **Pages → Build from branch** with the default branch; the same Gemfile and config work.

## Project structure

```
├── _config.yml       # Site and plugin config
├── Gemfile           # github-pages gem (+ optional jekyll-archives)
├── _layouts/         # default, post, page, home
├── _includes/        # head, header, footer, disqus, google_analytics, ads, author
├── _data/authors.yml # Author records
├── _sass/            # Typography, layout, components
├── assets/css/       # main.scss → main.css
├── assets/images/    # Logo, favicon, post images
├── _posts/           # Blog posts
├── _pages/           # Optional pages (about, etc.) via “pages” collection
├── index.html        # Home (layout: home, paginated)
└── .github/workflows/jekyll-pages.yml  # Optional: build + deploy with custom plugins
```

## License

Use and modify as you like.
