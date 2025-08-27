# Deploy HabitForge Landing Page to Cloudflare Pages

## Quick Start Guide

### 1. Generate Placeholder Images
1. Open `placeholder-generator.html` in your browser
2. Click each button to generate and download placeholder images
3. Move downloaded images to appropriate folders:
   - Phone screenshots → `screenshots/` folder
   - Avatar images → `avatars/` folder

### 2. Prepare for Deployment

Create these folders in your landing-page directory:
```
landing-page/
├── index.html
├── styles.css
├── script.js
├── logo.svg
├── icons/
│   ├── ai-brain.svg
│   ├── smart-notify.svg
│   ├── coach.svg
│   └── insights.svg
├── screenshots/
│   ├── hero-screen.png
│   ├── dashboard.png
│   ├── ai-coach.png
│   ├── analytics.png
│   ├── gamification.png
│   ├── step-1.png
│   ├── step-2.png
│   └── step-3.png
└── avatars/
    ├── user1.jpg
    ├── user2.jpg
    └── user3.jpg
```

### 3. Update TestFlight Link
In `script.js`, replace `YOUR_CODE` with your actual TestFlight code:
```javascript
window.open('https://testflight.apple.com/join/YOUR_CODE', '_blank');
```

### 4. Deploy to Cloudflare Pages

#### Option A: Direct Upload (Fastest)
1. Go to [dash.cloudflare.com](https://dash.cloudflare.com)
2. Select "Pages" from sidebar
3. Click "Create a project"
4. Choose "Upload assets"
5. Drag and drop your entire `landing-page` folder
6. Name your project (e.g., "habitforge-landing")
7. Click "Deploy site"

#### Option B: Git Integration
1. Create a GitHub repo for the landing page
2. Push your landing-page folder:
   ```bash
   cd landing-page
   git init
   git add .
   git commit -m "Initial landing page"
   git remote add origin YOUR_GITHUB_REPO
   git push -u origin main
   ```
3. In Cloudflare Pages:
   - Connect to GitHub
   - Select your repository
   - Build settings: leave empty (static site)
   - Deploy

### 5. Configure Custom Domain
1. After deployment, go to your project settings
2. Click "Custom domains"
3. Add `habitforge.org`
4. Follow DNS configuration instructions
5. SSL certificate will be automatically provisioned

### 6. Your Site is Live! 🎉
- Your site will be available at: https://habitforge.org
- SSL/HTTPS is automatically enabled
- Global CDN for fast loading worldwide

## Next Steps

### Replace Placeholders
Once you have real screenshots:
1. Take screenshots using iPhone simulator
2. Replace placeholder images in `screenshots/` folder
3. Redeploy (automatic if using Git)

### Update Content
- Edit testimonials in `index.html`
- Update statistics based on real beta feedback
- Add actual TestFlight link

### Add Analytics (Optional)
Add before closing `</head>`:
```html
<!-- Cloudflare Web Analytics -->
<script defer src='https://static.cloudflareinsights.com/beacon.min.js' 
        data-cf-beacon='{"token": "YOUR_TOKEN"}'></script>
```

### Launch Checklist
- [ ] Real screenshots added
- [ ] TestFlight link updated
- [ ] Testimonials updated
- [ ] Privacy policy page created
- [ ] Terms of service page created
- [ ] Analytics configured
- [ ] Social media links updated

## Troubleshooting

**Domain not working?**
- DNS propagation can take up to 24 hours
- Check Cloudflare DNS settings

**Images not loading?**
- Ensure all files are in correct folders
- Check file names match exactly (case-sensitive)

**Need help?**
- Cloudflare Pages docs: https://developers.cloudflare.com/pages
- Email forwarding: Check Email > Email Routing in Cloudflare dashboard