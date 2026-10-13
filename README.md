# Qijie (Jacquie) He - Personal Academic Website

My personal academic website built with [Jekyll](https://jekyllrb.com/) and the [Type on Strap](https://github.com/sylhare/Type-on-Strap) theme (I customized a little for my own use)

## Structure

- **About** (`/`) — Bio, research interests, education
- **Research** (`/research/`) — Project showcase with thumbnails and keywords
- **News** (`/news/`) — Academic events timeline with photos
- **Gallery** (`/gallery/`) — Photos

## Local Development

```bash
bundle install
bundle exec jekyll serve
```

Then open `http://localhost:4000/` in the browser.

## Adding Content

- **Research projects**: Add a new `.md` file in `_posts/` with the blog post template
- **News events**: Edit `pages/news.md` and copy an event block
- **Gallery photos**: Drop images into `assets/img/gallery/`
