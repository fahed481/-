import os
import zipfile

# الملفات المطلوبة لمشروع الموقع
files = {
    "index.html": """<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>NewPipe - Lightweight YouTube Experience</title>
  <link rel="stylesheet" href="styles.css" />
</head>
<body>
  <header>
    <h1>NewPipe</h1>
    <p>A lightweight, open-source YouTube experience.</p>
    <a href="#download" class="btn">Download Now</a>
  </header>

  <section id="features">
    <h2>Features</h2>
    <ul>
      <li>No ads, pure content experience</li>
      <li>Download videos & audio easily</li>
      <li>Play in background or pop-up mode</li>
      <li>Open-source and privacy friendly</li>
    </ul>
  </section>

  <section id="download">
    <h2>Get NewPipe</h2>
    <p>You can download the latest APK from the official sources:</p>
    <a href="https://newpipe.net" class="btn">Official Website</a>
    <a href="https://github.com/TeamNewPipe/NewPipe/releases" class="btn">GitHub Releases</a>
  </section>

  <footer>
    <p>© 2025 NewPipe Fan Website | Open Source Project</p>
  </footer>
</body>
</html>""",
    "styles.css": """body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  text-align: center;
  background: #f8f9fa;
  color: #333;
}
header {
  background: #d32f2f;
  color: #fff;
  padding: 2rem 1rem;
}
header h1 {
  margin: 0;
  font-size: 2.5rem;
}
header .btn {
  display: inline-block;
  margin-top: 1rem;
  padding: 0.7rem 1.5rem;
  background: #fff;
  color: #d32f2f;
  border-radius: 8px;
  text-decoration: none;
  font-weight: bold;
}
section {
  padding: 2rem 1rem;
}
.btn {
  display: inline-block;
  margin: 0.5rem;
  padding: 0.7rem 1.5rem;
  background: #d32f2f;
  color: #fff;
  border-radius: 8px;
  text-decoration: none;
  font-weight: bold;
}
footer {
  background: #222;
  color: #bbb;
  padding: 1rem;
  margin-top: 2rem;
}""",
    "README.md": """# NewPipe Landing Page

This is a simple landing page for **NewPipe**, a lightweight YouTube experience.

## Features
- Clean and simple design
- Sections for features, download links, and footer
- Responsive layout

## Deployment
You can deploy this page easily using **GitHub Pages** or **Vercel**.

### GitHub Pages
1. Push this repository to GitHub.
2. Go to **Settings > Pages** and enable GitHub Pages from the `main` branch.
3. Your site will be live at `https://your-username.github.io/newpipe-landing`.

### Vercel
1. Import the repo into [Vercel](https://vercel.com/).
2. Deploy with default settings.
3. Done 🎉

---

© 2025 NewPipe Fan Website
"""
}

# إنشاء ملف ZIP
zip_path = "/mnt/data/newpipe-landing.zip"
with zipfile.ZipFile(zip_path, 'w') as zipf:
    for filename, content in files.items():
        with open(filename, "w", encoding="utf-8") as f:
            f.write(content)
        zipf.write(filename)
        os.remove(filename)

zip_path
