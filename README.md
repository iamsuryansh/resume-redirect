# Redirect System for suryanshjain.com

This repository provides a simple redirect system for your custom domain using GitHub Pages.

## How it works

- **`index.html`**: Landing page showing all available links
- **`404.html`**: Handles redirects for `/resume`, `/portfolio`, etc.
- **`links.json`**: Configuration file containing all your redirect mappings

## Usage

### Adding a new redirect

Simply edit `links.json` and add your path and URL:

```json
{
  "resume": "https://portfolio.suryanshjain.com/SuryanshJainResume.pdf",
  "portfolio": "https://portfolio.suryanshjain.com",
  "github": "https://github.com/iamsuryansh",
  "linkedin": "https://www.linkedin.com/in/suryansh-jain",
  "newlink": "https://example.com/your-new-url"
}
```

### GitHub Pages Setup

1. Go to your repository settings
2. Navigate to Pages section
3. Set source to `master` branch
4. Configure your custom domain `suryanshjain.com`
5. Enable HTTPS

### How redirects work

When someone visits `suryanshjain.com/resume`:
1. GitHub Pages serves the `404.html` file
2. JavaScript reads the path (`/resume`)
3. Looks up the URL in `links.json`
4. Automatically redirects to the target URL

## Local Testing

Open `index.html` in a browser to see all your links. To test redirects, you'll need to run a local server:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000/resume` to test.

## License

MIT
