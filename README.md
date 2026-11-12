# convertX – All-in-One File Converter

convertX is a browser-based file conversion website. It provides six tools for working with PDF, Word documents, and images.

## Features

- **PDF to Word** – Extracts selectable PDF text into an editable `.docx` file.
- **Word to PDF** – Converts the text in `.docx` files into a PDF.
- **Images to PDF** – Combines JPG, PNG, or WebP images into one PDF.
- **PDF to Images** – Exports PDF pages as PNG or JPG images.
- **Merge PDFs** – Combines multiple PDF files into one PDF.
- **Image Converter** – Converts images to PNG, JPG, or WebP.

## Privacy

File processing is performed in the user's browser. The website does not upload selected files to an application server.

## Technologies Used

- HTML5
- CSS3
- JavaScript
- PDF.js
- pdf-lib
- jsPDF
- Mammoth.js
- docx

The conversion libraries are loaded from public CDNs, so an internet connection is required to load them.

## Run Locally

1. Download or clone this repository.
2. Open `index.html` in a modern web browser.

For a local development server, you can also run:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## Deploy on Amazon S3

This is a static website and can be hosted using an Amazon S3 bucket.

1. Create an S3 bucket with a globally unique name.
2. In the bucket's **Properties**, enable **Static website hosting**.
3. Set the index document to `index.html`.
4. Upload `index.html` to the bucket.
5. Configure the bucket's public-access and bucket-policy settings only if you intend to make the website publicly accessible. Review the security warning before changing account- or bucket-level Block Public Access settings.
6. Open the **Bucket website endpoint** shown in the Static website hosting section.

For production use, consider serving the site through Amazon CloudFront with HTTPS rather than exposing the S3 website endpoint directly. S3 static website endpoints do not provide HTTPS by themselves.

## Deploy with GitHub Pages (Optional)

1. Push this repository to GitHub.
2. Open the repository's **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select the `main` branch and `/ (root)` folder, then save.

## Important Limitations

- PDF-to-Word extracts selectable text; it does not preserve complex page layouts, tables, or images. Scanned PDFs are not supported because OCR is not included.
- Word-to-PDF converts document text; images and advanced formatting are not preserved.
- Very large files may be limited by the memory and performance of the user's device.
- The conversion libraries are loaded from third-party CDNs. Their availability and versions can affect the site.

## Project Structure

```text
convertX/
├── index.html
└── README.md
```

## License

No license has been specified yet. Add a license file before allowing others to reuse or redistribute the project.
