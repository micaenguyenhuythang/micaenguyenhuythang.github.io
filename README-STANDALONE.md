# Running DearFlip Standalone

## Option 1: Use a Local Web Server (Recommended)

The flipbook needs to be served via HTTP/HTTPS due to browser security restrictions (CORS). 

### Start a local server:

```bash
cd /Users/quoc.nguyenphu/dev/nht/dearflip-js-flipbook
python3 -m http.server 8080
```

Then open: **http://localhost:8080/standalone.html**

### Or use Node.js:

```bash
npx http-server -p 8080
```

## Option 2: Use 2D Mode (No WebGL)

If you want to open the file directly, edit `standalone.html` and change:
- `webgl="true"` to `webgl="false"`

This will use 2D mode which has better compatibility but less 3D effects.

## Troubleshooting

1. **"Loading WEBGL 3D..." stuck**: 
   - Use a local web server (Option 1)
   - Or disable WebGL (Option 2)

2. **PDF not loading**:
   - Check that `examples/example-assets/books/intro.pdf` exists
   - Check browser console for errors
   - Ensure all paths are relative to the HTML file

3. **Console errors**:
   - Open browser Developer Tools (F12)
   - Check Console tab for specific error messages

