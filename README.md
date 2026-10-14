# FIELDNOTE — SIMPLE STATIC WEBSITE

## Files

- `index.html` — The complete website. HTML, CSS, and JavaScript are all in this one file.
- `error.html` — A separate, self-contained branded 404 page for web-server or S3 error-document settings.

## Pages / Views

Home, About, Services, Contact, and a 404 error view.

Navigation uses URL hash routes, for example `#about` and `#contact`.

## Media

The website uses remote images from Unsplash and Google Fonts. An internet connection is needed for these external assets. No local assets, build tools, framework, npm, or backend are required.

## Run Locally

Open `index.html` in a browser.

## Deploy on EC2

1. Install a web server such as Apache or Nginx.
2. Copy `index.html` into the web root (for example, `/var/www/html/index.html`).
3. Open inbound HTTP port 80 in the instance security group, restricted as appropriate.
4. Visit the instance's public IP or DNS name.

For Apache or Nginx, configure the server’s custom 404/error-document setting to serve `/error.html` for missing URLs. Exact configuration depends on the server setup.

## Deploy on Amazon S3 Static Website Hosting

1. Upload both `index.html` and `error.html` to the bucket root.
2. Enable static website hosting and set the index document to `index.html`.
3. Set the error document to `error.html`. S3 can then return the separate branded error page for missing objects. S3 website endpoints are HTTP; use CloudFront with HTTPS for a public HTTPS site.

## Contact Form

The form is only a front-end demonstration. It shows a confirmation message but does not send email or save submissions. A backend or form service would be required for real submissions.

## Brand

Fieldnote is a fictional travel-inspiration brand created as a lightweight static deployment practice site.