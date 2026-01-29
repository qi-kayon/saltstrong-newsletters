# Salt Strong Newsletter Archive

A simple, beautiful static website for hosting chapter newsletters with a persistent "latest" link for social media sharing.

## Features

- 🎨 **Beautiful coastal-themed design** with ocean gradients and wave effects
- 📱 **Fully responsive** - works on all devices
- ⚡ **Lightning fast** - static HTML/CSS/JS, no backend required
- 🔗 **Persistent latest link** - `/latest.html` always redirects to newest newsletter
- 📊 **Timeline view** - chronological archive of all newsletters
- 💰 **Free hosting** - perfect for GitHub Pages
- 🛠️ **Easy maintenance** - just upload PDF and update one JSON file

## Quick Start

### Option 1: GitHub Pages (Recommended)

1. **Create a new GitHub repository**
   - Name it something like `saltstrong-newsletters`
   - Make it public

2. **Upload these files to your repository:**
   - `index.html`
   - `latest.html`
   - `newsletters/config.json`
   - `newsletters/` folder (with your PDF files)

3. **Enable GitHub Pages:**
   - Go to repository Settings > Pages
   - Source: Deploy from a branch
   - Branch: `main` (or `master`)
   - Folder: `/ (root)`
   - Click Save

4. **Your site will be live at:**
   - `https://yourusername.github.io/saltstrong-newsletters/`
   - Latest link: `https://yourusername.github.io/saltstrong-newsletters/latest.html`

### Option 2: Any Web Host

Simply upload all files to your web hosting via FTP or their file manager. The site works anywhere that can serve static HTML files.

## File Structure

```
saltstrong-newsletters/
├── index.html              # Main archive page
├── latest.html            # Redirect page for latest newsletter
├── newsletters/
│   ├── config.json        # Configuration (edit this!)
│   ├── 2025-01-january.pdf
│   ├── 2024-12-december.pdf
│   └── 2024-11-november.pdf
└── README.md
```

## Adding a New Newsletter

### Step 1: Upload the PDF

1. Name your PDF file with a clear convention, like: `2025-02-february.pdf`
2. Upload it to the `newsletters/` folder

### Step 2: Update config.json

Edit `newsletters/config.json` and add your new newsletter **at the top** of the array:

```json
{
  "newsletters": [
    {
      "date": "February 2025",
      "title": "Spring Prep & Tackle Tips",
      "filename": "2025-02-february.pdf"
    },
    {
      "date": "January 2025",
      "title": "Winter Fishing Strategies",
      "filename": "2025-01-january.pdf"
    }
  ]
}
```

**Important:** The first newsletter in the array is always considered the "latest"!

### Step 3: Commit Changes

If using GitHub:
```bash
git add .
git commit -m "Add February 2025 newsletter"
git push
```

That's it! The site automatically updates and `/latest.html` now points to your new PDF.

## Sharing the Latest Newsletter

Use this persistent link everywhere:
- **Social media posts** (Facebook, Twitter, Instagram bio)
- **Email signatures**
- **Your main website**
- **QR codes for print materials**

```
https://yourusername.github.io/saltstrong-newsletters/latest.html
```

This link ALWAYS redirects to your newest newsletter - you never have to update it!

## Customization

### Change Colors

Edit the CSS variables at the top of `index.html`:

```css
:root {
    --ocean-deep: #0a2540;    /* Dark blue background */
    --ocean-mid: #1a4d70;     /* Mid blue gradient */
    --seafoam: #64b5a6;       /* Accent teal/seafoam */
    --sand: #f4e8d8;          /* Light text */
    --coral: #ff6b4a;         /* Call-to-action orange */
    --wave-gray: #8ba3b0;     /* Muted text */
}
```

### Change Title

Edit these lines in `index.html`:

```html
<h1>Newsletter Archive</h1>
<p class="subtitle">Salt Strong Chapter</p>
```

And in the footer:

```html
<footer>
    Salt Strong Chapter Newsletter Archive
</footer>
```

### Newsletter Date Format

You can use any date format in `config.json`:
- "January 2025"
- "Jan 2025"
- "01/2025"
- "Issue #42 - Winter 2025"

## Troubleshooting

### Latest link shows "Unable to load"
- Make sure `config.json` exists in the `newsletters/` folder
- Check that the JSON syntax is valid (use JSONLint.com)
- Verify the PDF filename matches exactly what's in config.json

### PDFs won't open
- Ensure PDFs are actually in the `newsletters/` folder
- Check that filenames match exactly (case-sensitive!)
- Make sure PDFs aren't corrupted

### Timeline doesn't show newsletters
- Check browser console for errors (F12)
- Verify `config.json` is valid JSON
- Make sure you're accessing via HTTP/HTTPS, not as a local file

### GitHub Pages not updating
- GitHub Pages can take 1-2 minutes to rebuild
- Check the Actions tab for deployment status
- Clear your browser cache

## Advanced: Custom Domain

To use your own domain with GitHub Pages:

1. Add a `CNAME` file to your repository with your domain:
   ```
   newsletters.yourchapter.com
   ```

2. In your domain registrar, add a CNAME record:
   - Host: `newsletters` (or whatever subdomain you want)
   - Points to: `yourusername.github.io`

3. In GitHub repository Settings > Pages, add your custom domain

## Support

For issues or questions:
1. Check the troubleshooting section above
2. Verify all files are uploaded correctly
3. Check browser console for error messages (F12 > Console tab)

## License

Free to use and modify for your chapter!

---

**Pro tip:** Bookmark `https://yourusername.github.io/saltstrong-newsletters/latest.html` in your browser. You'll always have instant access to your current newsletter, and so will everyone you share the link with!
