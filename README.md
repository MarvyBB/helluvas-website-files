# The Helluvas – Website

## Setup Instructions

### 1. Create the GitHub repo
1. Go to github.com → New repository
2. Name it exactly: `thehelluvas.github.io`  
   *(or any name — but `username.github.io` gets auto-published)*
3. Set it to **Public**, leave everything else default, click Create

### 2. Upload the files
Your repo needs this structure:

```
thehelluvas.github.io/
├── index.html
├── CNAME
└── images/
    ├── logo.png              ← your logo (image 17)
    ├── hero.jpg              ← full band on stage (image 8 or 11 works great)
    ├── about-main.jpg        ← vocalist singing (image 16)
    ├── about-accent.jpg      ← crowd shot (image 10)
    ├── member-vocals.jpg     ← vocalist close-up (image 13)
    ├── member-guitar.jpg     ← tattooed guitarist (image 2)
    ├── member-bass.jpg       ← bass player (image 1)
    ├── member-drums.jpg      ← drummer (image 14)
    ├── gallery-1.jpg         ← full band outdoor (image 12)
    ├── gallery-2.jpg         ← vocalist arm raised (image 7)
    ├── gallery-3.jpg         ← crowd (image 10)
    ├── gallery-4.jpg         ← bass close-up (image 6)
    ├── gallery-5.jpg         ← drummer (image 5)
    ├── gallery-6.jpg         ← full band red lights (image 11)
    ├── gallery-7.jpg         ← vocalist on stage (image 15)
    └── gallery-8.jpg         ← outdoor gig (image 4)
```

### 3. Enable GitHub Pages
1. In your repo → **Settings** → **Pages**
2. Source: `Deploy from a branch` → `main` → `/ (root)` → Save

### 4. Connect your domain (thehelluvas.com)
In your **domain registrar** (e.g. Namecheap, GoDaddy), add these DNS records:

**A Records** (point to GitHub Pages):
```
Type    Host    Value
A       @       185.199.108.153
A       @       185.199.109.153
A       @       185.199.110.153
A       @       185.199.111.153
```

**CNAME Record** (for www):
```
Type    Host    Value
CNAME   www     thehelluvas.github.io
```

Then in GitHub Pages settings, enter `thehelluvas.com` in the Custom Domain box and tick **Enforce HTTPS**.

DNS changes can take up to 24–48 hours to fully propagate.

---

## Customising the site

### Add upcoming gigs
In `index.html`, find the `<!-- ADD YOUR UPCOMING GIGS HERE -->` comment and uncomment/copy the gig template:

```html
<a href="YOUR_TICKET_LINK" class="gig-item">
  <div>
    <div class="gig-date">26 APR</div>
    <div class="gig-date-sub">Saturday</div>
  </div>
  <div>
    <div class="gig-venue">The Venue Name</div>
    <div class="gig-location">City · Doors 8pm</div>
  </div>
  <div class="gig-tag">Tickets</div>
</a>
```

For sold out shows, change `gig-tag` to `gig-tag sold-out` and set text to "Sold Out".

### Enable the contact form (free)
1. Sign up at **formspree.io** (free tier = 50 submissions/month)
2. Create a new form, copy your endpoint URL
3. In `index.html`, find `<form id="bookingForm">` and add `action="YOUR_ENDPOINT"` and `method="POST"`
4. Remove the `e.preventDefault()` line in the JavaScript

### Update band member names
Search for `band-name` divs in the Band section and replace the role text with actual first names.

### Social media links
Find the `social-links` section in Contact and replace `href="#"` with your actual URLs.

### Update email
Replace `booking@thehelluvas.com` with your real booking email.
