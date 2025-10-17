# Deploy to Other Platforms

While GitHub Pages is ideal for Docsify, you can deploy to any static hosting platform.

## Netlify

### Deploy Method 1: Drag & Drop

1. Go to https://app.netlify.com/drop
2. Drag your `docs/` folder onto the page
3. Done! Your site is live

### Deploy Method 2: Git Integration

1. Push your repo to GitHub/GitLab/Bitbucket
2. Log into Netlify
3. Click "New site from Git"
4. Select your repository
5. Configure:
   - Build command: (leave empty)
   - Publish directory: `docs`
6. Click "Deploy site"

### netlify.toml (Optional)

Create `netlify.toml` in your repo root:

```toml
[build]
  publish = "docs"

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200
```

**URL:** Your site will be at `https://random-name.netlify.app`

## Vercel

### Deploy Method 1: CLI

```bash
npm install -g vercel
cd my-project
vercel
```

Follow prompts and set output directory to `docs`

### Deploy Method 2: Git Integration

1. Go to https://vercel.com
2. Click "New Project"
3. Import your Git repository
4. Configure:
   - Framework Preset: Other
   - Root Directory: `docs` (if not using root)
   - Build Command: (leave empty)
   - Output Directory: `.` (or `docs`)
5. Click "Deploy"

**URL:** Your site will be at `https://project-name.vercel.app`

## Cloudflare Pages

1. Log into Cloudflare dashboard
2. Go to Pages
3. Click "Create a project"
4. Connect your Git repository
5. Configure:
   - Build command: (leave empty)
   - Build output directory: `docs`
6. Click "Save and Deploy"

**Features:**
- Free custom domain
- Automatic HTTPS
- Fast global CDN
- Unlimited bandwidth

**URL:** `https://project-name.pages.dev`

## GitLab Pages

Create `.gitlab-ci.yml` in repo root:

```yaml
pages:
  stage: deploy
  script:
    - mkdir -p public
    - cp -r docs/* public/
  artifacts:
    paths:
      - public
  only:
    - main
```

Push to GitLab, and your site will deploy automatically.

**URL:** `https://username.gitlab.io/project-name/`

## Surge.sh

Super simple static hosting:

```bash
npm install -g surge

cd docs
surge
```

First time: Create account via CLI
Every time: Choose a domain or use random generated one

**URL:** `https://your-project.surge.sh`

## Firebase Hosting

```bash
npm install -g firebase-tools
firebase login
firebase init hosting
```

Configure:
- Public directory: `docs`
- Single-page app: Yes
- GitHub deploys: Optional

Deploy:
```bash
firebase deploy
```

**Features:**
- Free SSL
- Custom domain support
- Fast CDN
- Good analytics

**URL:** `https://project-id.web.app`

## Amazon S3 + CloudFront

### Step 1: Create S3 Bucket

```bash
aws s3 mb s3://my-docs-bucket
aws s3 website s3://my-docs-bucket --index-document index.html
```

### Step 2: Upload Files

```bash
cd docs
aws s3 sync . s3://my-docs-bucket --acl public-read
```

### Step 3: Configure CloudFront (Optional)

For HTTPS and global CDN:

1. Create CloudFront distribution
2. Set origin to S3 bucket
3. Set default root object to `index.html`
4. Request SSL certificate

**Cost:** Very cheap for small sites (often free tier eligible)

## Render

1. Go to https://render.com
2. Click "New Static Site"
3. Connect repository
4. Configure:
   - Build command: (leave empty)
   - Publish directory: `docs`
5. Create site

**Features:**
- Free tier available
- Custom domains
- Automatic HTTPS

## Comparison

| Platform | Free Tier | Custom Domain | CDN | Build Time |
|----------|-----------|---------------|-----|------------|
| GitHub Pages | ✅ Yes | ✅ Yes | ✅ Yes | 1-2 min |
| Netlify | ✅ Yes (100GB) | ✅ Yes | ✅ Yes | < 1 min |
| Vercel | ✅ Yes | ✅ Yes | ✅ Yes | < 1 min |
| Cloudflare | ✅ Yes (unlimited) | ✅ Yes | ✅ Yes | 1-2 min |
| GitLab Pages | ✅ Yes | ✅ Yes | ✅ Yes | 2-5 min |
| Surge | ✅ Yes | ✅ Yes (paid) | ❌ No | < 30 sec |
| Firebase | ✅ Yes (10GB) | ✅ Yes | ✅ Yes | < 1 min |

## Recommendation by Use Case

### Personal Projects
**Best:** GitHub Pages or Netlify
- Free
- Simple setup
- Good enough performance

### Company Documentation
**Best:** Vercel or Cloudflare Pages
- Professional features
- Great performance
- Custom domains
- Analytics

### High Traffic Sites
**Best:** Cloudflare Pages or AWS S3+CloudFront
- Unlimited bandwidth (Cloudflare)
- Global CDN
- DDoS protection

### Quick Tests/Demos
**Best:** Surge or Netlify Drop
- Deploy in seconds
- No account needed (Surge)
- Temporary URLs

## General Deployment Steps

For any platform:

1. **Ensure .nojekyll exists** (if platform uses Jekyll)
2. **Use CDN links in index.html** (not relative paths)
3. **Set publish directory** to `docs` (or wherever your files are)
4. **No build command needed** (Docsify builds in browser)
5. **Configure SPA routing** (optional, for cleaner URLs)

## Next Steps

- [Read FAQ](faq.md) →
- [See examples](examples/sample1.md) →

---

Your docs deserve to be seen! Pick a platform and deploy today! 🚀
