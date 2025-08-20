# Zero-Cost Static Blog (No Backend)

This is a simple, production-ready starter for a blog built with **only HTML, CSS, and JavaScript**.  
No frameworks, no build step, free hosting via GitHub Pages.

## Structure
```
.
├── index.html              # Home page (lists posts)
├── post.html               # Post template (loads content by ?p=slug)
├── assets/
│   ├── style.css
│   └── main.js
└── posts/
    ├── posts.json          # Site + posts metadata
    └── hello-world.html    # Example post content
```

## How to run locally
Just open `index.html` in your browser. For full functionality in some browsers, you might need a local server.
If so, run one of these in the project folder:
- Python 3: `python -m http.server 8000`
- Node.js: `npx http-server -p 8000`

Then visit `http://localhost:8000`

## Deploy on GitHub Pages (free)
1. Create a new GitHub repo (public).
2. Upload **all files** from this folder to the repo root (or drag & drop via the web UI).
3. In the repo: **Settings → Pages → Build and deployment → Source = Deploy from a branch**.
4. Select the **main** branch and root (`/`) folder. Save.
5. Your blog will be live at: `https://<your-username>.github.io/<your-repo>/`

## Custom domain (optional, free if you already own one)
- In **Settings → Pages**, add your domain (e.g., `blog.example.com`).
- Add DNS CNAME pointing `blog.example.com` → `<your-username>.github.io`.
- Add a `CNAME` file at the repo root containing your domain.

## Add a new post
1. Duplicate `posts/hello-world.html` (e.g., `posts/my-second-post.html`). Edit the HTML content.
2. Open `posts/posts.json` and add a new entry to the `"posts"` array:
```json
{
  "slug": "my-second-post",
  "title": "My Second Post",
  "date": "2025-08-20",
  "description": "What this post is about…",
  "tags": ["howto","notes"],
  "cover": "assets/cover-placeholder.png",
  "author": "Your Name"
}
```
3. Commit & push. The new post will appear on the homepage and at:
`post.html?p=my-second-post`

## SEO checklist
- Titles & descriptions are set dynamically. Cover images get Open Graph tags.
- JSON-LD `BlogPosting` is injected for each post.
- `robots.txt` and a starter `sitemap.xml` are included (edit the domain & add each new post URL).
- Add a `<meta name="robots" content="index,follow">` if you ever disable indexing and re-enable.

## Extras (optional, all free)
- **Analytics:** [Plausible](https://plausible.io/) free trial or [GoatCounter](https://www.goatcounter.com/) free for non‑commercial.
- **Comments:** [Giscus](https://giscus.app/) (GitHub Discussions) or [Utterances](https://utteranc.es/).
- **Contact form:** [Formspree](https://formspree.io/) or [Netlify Forms] (if you ever migrate).

## License
MIT — do whatever you want, just keep the license.
