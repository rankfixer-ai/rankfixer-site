# RankFixer Blog - Complete Setup Guide

## 📦 What's Included

✅ **5 Complete Pages:**
- Homepage with hero, article grid, and email capture
- Article 1: "How to Hire Filipino VAs for SEO Work"
- Article 2: "What Does It Actually Cost to Rank a Business?"
- Article 3: "11 SEO Tasks You Should Delegate to a VA"
- About & Contact pages

✅ **Full SEO Infrastructure:**
- sitemap.xml
- robots.txt
- Article schema markup (for rich snippets)
- Organization schema
- FAQ schema
- Breadcrumb schema
- Open Graph tags

✅ **Analytics & Tracking:**
- Google Analytics 4 integration
- Event tracking on all CTAs
- Banner click tracking
- Email capture tracking

✅ **Design System:**
- Mobile-responsive (matches Job Copilot PH branding)
- Sticky banner linking to Job Copilot PH
- Email capture forms (Formspree integration)
- Professional typography (Fraunces + Plus Jakarta Sans)

---

## 🚀 Quick Deploy (GitHub Pages)

### Step 1: Create GitHub Repository

1. Go to GitHub.com → New Repository
2. Name: `rankfixer-blog`
3. Public repository
4. **DO NOT** initialize with README

### Step 2: Upload Files

**Option A: GitHub Web Interface**
1. Click "Upload files"
2. Drag all files from `rankfixer-site/` folder
3. Commit directly to main branch

**Option B: Command Line**
```bash
cd rankfixer-site
git init
git add .
git commit -m "Initial commit - RankFixer blog"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/rankfixer-blog.git
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to repository Settings
2. Pages (left sidebar)
3. Source: Deploy from branch
4. Branch: `main` → `/root`
5. Save

**Your site will be live at:** `https://YOUR_USERNAME.github.io/rankfixer-blog`

### Step 4: Add Custom Domain

1. In GitHub Pages settings, add custom domain: `rankfixer.co`
2. In your domain registrar (Namecheap, GoDaddy, etc.), add DNS records:

```
Type    Name    Value
A       @       185.199.108.153
A       @       185.199.109.153
A       @       185.199.110.153
A       @       185.199.111.153
CNAME   www     YOUR_USERNAME.github.io
```

3. Wait 10-30 minutes for DNS propagation
4. Enable "Enforce HTTPS" in GitHub Pages settings

---

## 🔧 Configuration Steps

### 1. Set Up Google Analytics

1. Create GA4 property at analytics.google.com
2. Get your Measurement ID (format: `G-XXXXXXXXXX`)
3. Replace `G-XXXXXXXXXX` in all HTML files:

**Files to update:**
- index.html
- hire-filipino-vas-for-seo.html
- cost-of-ranking-local-business.html
- seo-tasks-to-outsource.html
- about.html
- contact.html

**Find and replace:**
```html
<!-- OLD -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>

<!-- NEW -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-YOUR_REAL_ID"></script>
```

And:
```javascript
gtag('config', 'G-XXXXXXXXXX');
// Change to:
gtag('config', 'G-YOUR_REAL_ID');
```

### 2. Set Up Formspree (Email Capture)

1. Go to formspree.io → Sign up (free)
2. Create new form → Get form ID
3. Replace `YOUR_FORM_ID` in all HTML files:

**Files to update:**
- index.html (email capture section)
- hire-filipino-vas-for-seo.html (email capture section)
- cost-of-ranking-local-business.html (email capture section)
- seo-tasks-to-outsource.html (email capture section)
- contact.html (contact form)

**Find and replace:**
```html
<!-- OLD -->
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">

<!-- NEW -->
<form action="https://formspree.io/f/YOUR_REAL_FORM_ID" method="POST">
```

### 3. Submit to Google Search Console

1. Go to search.google.com/search-console
2. Add property: `rankfixer.co`
3. Verify ownership (DNS TXT record or HTML file upload)
4. Submit sitemap: `https://rankfixer.co/sitemap.xml`

---

## 📊 SEO Checklist

✅ **On-Page SEO:**
- [x] Unique title tags (under 60 characters)
- [x] Meta descriptions (under 160 characters)
- [x] H1 on every page
- [x] Proper heading hierarchy (H1 → H2 → H3)
- [x] Alt text for images (add your own images)
- [x] Internal linking between articles
- [x] Mobile-responsive design

✅ **Technical SEO:**
- [x] Sitemap.xml
- [x] Robots.txt
- [x] HTTPS (via GitHub Pages)
- [x] Fast loading (static HTML)
- [x] Clean URLs (no .html in marketing - optional to remove)

✅ **Schema Markup:**
- [x] Organization schema
- [x] WebSite schema
- [x] Article schema (all 3 posts)
- [x] Breadcrumb schema
- [x] FAQ schema (Article 1)

✅ **Social:**
- [x] Open Graph tags
- [ ] Twitter Card tags (optional to add)
- [ ] Share images (create 1200x630 images)

---

## 🎨 Customization Guide

### Change Colors

Edit `style.css` → `:root` section:

```css
:root {
  --bg: #FAFAF7;        /* Background color */
  --surface: #FFFFFF;   /* Card backgrounds */
  --accent: #C8490A;    /* CTA buttons, links */
  --text: #1A1714;      /* Body text */
  --text-muted: #6B6762; /* Metadata, captions */
  --border: #E8E6E3;    /* Borders, dividers */
}
```

### Add Logo

1. Create logo image (PNG, SVG recommended)
2. Upload to root directory
3. Update header in all HTML files:

```html
<!-- OLD -->
<div class="logo">RankFixer</div>

<!-- NEW -->
<div class="logo">
  <img src="logo.png" alt="RankFixer" style="height: 32px;">
</div>
```

### Update Banner Link

All pages have this banner:
```html
<div class="banner">
  🇵🇭 Hiring a VA? Browse 3,162 active profiles → 
  <a href="https://jobcopilotph.vercel.app">View Jobs</a>
</div>
```

Change the link to your Job Copilot PH URL or remove entirely.

---

## 📝 Adding New Articles

1. Duplicate an existing article HTML file
2. Update:
   - `<title>` tag
   - `<meta name="description">`
   - `<h1>` heading
   - Article content
   - `datePublished` in schema
3. Add to `sitemap.xml`:

```xml
<url>
  <loc>https://rankfixer.co/your-new-article.html</loc>
  <lastmod>2026-05-20</lastmod>
  <changefreq>monthly</changefreq>
  <priority>0.9</priority>
</url>
```

4. Add to homepage `index.html` article grid

---

## 🔍 Target Keywords

**Article 1:** hire filipino va, seo virtual assistant, filipino va rates
**Article 2:** cost to rank on google, seo pricing, how much does seo cost
**Article 3:** seo tasks to outsource, delegate seo work, va seo tasks

**Next article ideas:**
- "7 Interview Questions to Ask Filipino SEO VAs"
- "How to Onboard a Remote VA in 48 Hours"
- "DIY vs VA vs Agency: What Each Actually Costs"
- "Filipino VA Timezone Guide for US Agencies"

---

## 📈 Analytics Events to Track

**Banner clicks:**
```javascript
gtag('event', 'click', {
  'event_category': 'banner',
  'event_label': 'homepage'
});
```

**Email captures:**
```javascript
gtag('event', 'submit', {
  'event_category': 'email_capture',
  'event_label': 'article_1'
});
```

**Inline CTAs:**
```javascript
gtag('event', 'click', {
  'event_category': 'inline_cta',
  'event_label': 'article_1_section_1'
});
```

View in GA4: Reports → Engagement → Events

---

## 🚨 Important Notes

- Replace `G-XXXXXXXXXX` with your real GA4 ID
- Replace `YOUR_FORM_ID` with your real Formspree form ID
- Create actual images for articles (currently no images)
- Test all forms before launch
- Submit sitemap to Google Search Console
- Enable HTTPS in GitHub Pages settings

---

## 💰 Total Cost

- Domain (rankfixer.co): **$12/year**
- GitHub Pages hosting: **$0**
- Formspree (50 submissions/mo): **$0**
- Google Analytics: **$0**

**Total: $12/year**

---

## 🎯 Launch Checklist

- [ ] Upload all files to GitHub
- [ ] Enable GitHub Pages
- [ ] Add custom domain DNS records
- [ ] Replace GA4 tracking ID
- [ ] Replace Formspree form IDs
- [ ] Test all forms
- [ ] Submit sitemap to Search Console
- [ ] Check mobile responsiveness
- [ ] Test all internal links
- [ ] Share on social media

---

## 📞 Support

Questions? Issues? Email: [your-email@example.com]

Built with ❤️ for Filipino VA hiring.
