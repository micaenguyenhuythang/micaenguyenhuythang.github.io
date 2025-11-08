# Deploy to GitHub Pages

This guide will help you deploy your DearFlip flipbook to GitHub Pages for free hosting.

## Prerequisites

- A GitHub account
- Git installed on your computer

## Deployment Steps

### Option 1: User/Organization Pages (username.github.io)

1. **Create a new repository** on GitHub:
   - Repository name: `yourusername.github.io` (replace `yourusername` with your GitHub username)
   - Make it **public**
   - Initialize with a README (optional)

2. **Clone and setup**:
   ```bash
   git clone https://github.com/yourusername/yourusername.github.io.git
   cd yourusername.github.io
   ```

3. **Copy your files**:
   ```bash
   # Copy all files from dearflip-js-flipbook to the repository
   cp -r /path/to/dearflip-js-flipbook/* .
   cp -r /path/to/dearflip-js-flipbook/.github .
   ```

4. **Commit and push**:
   ```bash
   git add .
   git commit -m "Initial commit: DearFlip flipbook"
   git push -u origin main
   ```

5. **Enable GitHub Pages**:
   - Go to repository Settings → Pages
   - Under "Source", select **"GitHub Actions"**
   - The workflow will automatically deploy your site

6. **Access your site**:
   - Your flipbook will be available at: `https://yourusername.github.io`
   - It may take a few minutes for the first deployment

### Option 2: Project Pages (repository.github.io/project-name)

1. **Create a new repository** on GitHub:
   - Repository name: `dearflip-flipbook` (or any name you prefer)
   - Make it **public**
   - Initialize with a README (optional)

2. **Clone and setup**:
   ```bash
   git clone https://github.com/yourusername/dearflip-flipbook.git
   cd dearflip-flipbook
   ```

3. **Copy your files**:
   ```bash
   # Copy all files from dearflip-js-flipbook to the repository
   cp -r /path/to/dearflip-js-flipbook/* .
   cp -r /path/to/dearflip-js-flipbook/.github .
   ```

4. **Commit and push**:
   ```bash
   git add .
   git commit -m "Initial commit: DearFlip flipbook"
   git push -u origin main
   ```

5. **Enable GitHub Pages**:
   - Go to repository Settings → Pages
   - Under "Source", select **"GitHub Actions"**
   - The workflow will automatically deploy your site

6. **Access your site**:
   - Your flipbook will be available at: `https://yourusername.github.io/dearflip-flipbook`
   - It may take a few minutes for the first deployment

## File Structure

Your repository should have this structure:

```
.
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Actions workflow
├── dflip/                      # DearFlip library files
│   ├── css/
│   ├── js/
│   ├── images/
│   └── ...
├── examples/
│   └── example-assets/
│       └── books/
│           └── intro.pdf       # Your PDF file
├── index.html                  # Main entry point
├── standalone.html             # Alternative entry point
├── .gitignore
└── README.md
```

## Customizing Your PDF

To use your own PDF file:

1. Place your PDF in `examples/example-assets/books/` (or any location)
2. Update `index.html` and change the `source` attribute:
   ```html
   <div class="_df_book" 
        source="examples/example-assets/books/your-pdf.pdf"
        ...>
   ```

## Troubleshooting

### Site not loading
- Wait 5-10 minutes after first push for GitHub Pages to build
- Check the Actions tab in your repository for build errors
- Verify all file paths are correct

### PDF not loading
- Ensure PDF file is committed to the repository
- Check browser console (F12) for errors
- Verify the `source` path in `index.html` matches your file location

### Assets not loading
- Make sure the `dflip` folder is in the repository root
- Check that all files in `dflip/` are committed
- Verify `dFlipLocation` is set correctly in the console

## Updating Your Site

After making changes:

```bash
git add .
git commit -m "Update flipbook"
git push
```

GitHub Actions will automatically rebuild and deploy your site.

## Custom Domain (Optional)

To use a custom domain:

1. Add a `CNAME` file to your repository root with your domain:
   ```
   yourdomain.com
   ```

2. Configure DNS settings with your domain provider:
   - Add a CNAME record pointing to `yourusername.github.io`

3. Update repository Settings → Pages → Custom domain

## License

Remember: DearFlip Lite is for non-commercial use only. See LICENSE file for details.


