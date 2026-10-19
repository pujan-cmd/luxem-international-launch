# Luxem International — Website Launch Package

This folder has everything needed to put luxeminternational.co live.

## What's in this package

| File | Purpose |
|---|---|
| `index.html` | The entire website (all pages, styles, scripts and product photos are built into this one file). |
| `favicon.ico`, `favicon.svg`, `favicon-16.png`, `favicon-32.png`, `favicon-48.png`, `favicon-512.png`, `android-chrome-192.png`, `apple-touch-icon.png`, `site.webmanifest` | Browser-tab, phone home-screen and Google search-result icons (gold leaf emblem inside a ring, on brand green). |
| `favicon.ico`, `favicon.png`, `favicon-16x16.png`, `favicon-32x32.png`, `apple-touch-icon.png`, `android-chrome-192x192.png`, `android-chrome-512x512.png`, `site.webmanifest` | Luxem hexagon favicon in every size browsers, iPhones and Android need. |
| `logo.png` | Full logo, used by search engines / social previews. |
| `og-image.jpg` | The image shown when the site is shared on WhatsApp, Facebook, LinkedIn, etc. |
| `robots.txt` | Tells search engines they're allowed to index the site. |
| `sitemap.xml` | Helps Google find and index the homepage. |

**Important:** All the icon files, `logo.png`, `og-image.jpg`, `robots.txt` and `sitemap.xml` must sit in the same top-level folder as `index.html` (not in a subfolder), because the HTML links to them as `/favicon.png`, `/og-image.jpg`, etc.

---

## Step-by-step for GoDaddy (Web Hosting / cPanel)

This assumes you bought **GoDaddy Web Hosting** (the plan that includes a cPanel account) — the standard setup when you buy hosting and a domain together from GoDaddy.

### Step 1 — Open File Manager
1. Go to your [GoDaddy product page](https://www.godaddy.com/account/products) and sign in.
2. Under **Web Hosting**, next to the hosting account for `luxeminternational.co`, select **Manage**.
3. On the hosting Dashboard, under **Websites**, select **File Manager** for your domain (or select **cPanel Admin → File Manager** if you land on the classic cPanel view).

### Step 2 — Upload into public_html
1. In File Manager, navigate into the **public_html** folder — this is the folder GoDaddy serves your domain from. (If you see `public_html/luxeminternational.co/` as a subfolder because of an add-on domain setup, go into that folder instead.)
2. **Important:** `index.html` is ~5 MB because all the product photos are built into it. Rather than uploading the files one by one, upload the **zip file** (`luxem-international-launch.zip`) I gave you — it's faster and more reliable:
   - Click **Upload**, drag the zip in (or use **Select File**), and wait for it to reach 100%.
   - Go back into File Manager, right-click the uploaded zip, and choose **Extract**.
   - Move the extracted files (`index.html`, the favicon/icon files, `logo.png`, `og-image.jpg`, `robots.txt`, `sitemap.xml`, `site.webmanifest`) so they sit directly inside `public_html` — not inside an extra subfolder.
3. If GoDaddy already placed a placeholder `index.html` or `home.html` in `public_html` (common on a fresh account), delete or rename it first so it doesn't conflict with yours.
4. Visit `https://www.luxeminternational.co` — the site should now load live.

### Step 3 — Confirm the domain is pointed correctly
If you bought the domain **and** hosting together from GoDaddy, this is usually automatic — GoDaddy connects them for you. To double check:
1. From the same product page, go to your domain **luxeminternational.co → DNS** (or **Manage DNS**).
2. Confirm there's an **A record** for `@` pointing at your Web Hosting account's IP address, and a **CNAME** for `www` pointing to `@` or to your hosting domain.
3. If you bought the domain elsewhere and only hosting from GoDaddy, GoDaddy's hosting Dashboard will show you the exact IP/records to add at your domain registrar.

DNS changes can take a few minutes up to 24–48 hours to fully propagate everywhere.

### Step 4 — Turn on free SSL (HTTPS)
GoDaddy's Web Hosting (cPanel) plans include free **AutoSSL**:
1. From the hosting Dashboard, select **cPanel Admin**.
2. On the cPanel home page, under **Security**, select **SSL/TLS Status**.
3. Tick the checkbox next to `luxeminternational.co` (or select the top checkbox to select all), then select **Run AutoSSL**.
4. Wait for the success message — this installs a free certificate and GoDaddy auto-renews it.
5. Once installed, make sure visitors are redirected to `https://` (cPanel's SSL section has a toggle for "Force HTTPS Redirect" — turn it on).

This matters both for buyer trust (the padlock icon) and for Google ranking.

## Step 5 — Verify everything works

Once live, check:
- [ ] Site loads at `https://www.luxeminternational.co`
- [ ] All 5 pages (Home, About, Products, Quality, Tools/Blog, Contact) work from the top menu
- [ ] The WhatsApp button (bottom-right, and in the header/footer) opens a chat correctly
- [ ] The Contact form shows the confirmation message on submit *(note: the form currently only shows an on-page confirmation — it does not yet email you. See "Optional next step" below if you want real email delivery.)*
- [ ] Share the link in WhatsApp — a logo + banner preview card should appear using `og-image.jpg`

## Step 6 — Tell Google the site exists

1. Go to [Google Search Console](https://search.google.com/search-console).
2. Add `luxeminternational.co` as a property and verify ownership (your host usually gives a one-click DNS verification option).
3. Submit `https://www.luxeminternational.co/sitemap.xml` under **Sitemaps**.

---

## Optional next step: make the contact form actually send you emails

Right now the quote form on the Contact page just shows a "Thank you" message in the browser — it doesn't deliver anywhere yet. The easiest free fix, once the site is live on a real domain, is a form-handling service like **Formspree** or **Web3Forms** (a few lines added to the form). Just ask and I can wire that in once you've picked a host — it needs a live domain to work.

---

If anything in these steps doesn't match what you see in your hosting panel, send a screenshot and I'll walk you through the exact buttons to click.
