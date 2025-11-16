# Quick Start: GitHub Pages Setup

## For Repository Administrators

### Step 1: Enable GitHub Pages
1. Go to: `Settings` → `Pages`
2. Under "Source", select: `GitHub Actions`
3. Click `Save`

### Step 2: Deploy
After merging this PR to `main`:
- Deployment happens automatically
- Or manually trigger via: `Actions` → `Deploy to GitHub Pages` → `Run workflow`

### Site URL
Your site will be available at:
```
https://doka-nt.github.io/chatgpt-subtitle-translator/
```

### Documentation
- 📖 [Full English Guide](./GITHUB_PAGES_SETUP.md)
- 📖 [Полное руководство на русском](./GITHUB_PAGES_SETUP_RU.md)

## What Was Changed

### Workflow Updates (`.github/workflows/deploy.yml`)
- ✅ Modern GitHub Pages deployment with `actions/deploy-pages`
- ✅ Separate build and deploy jobs
- ✅ Proper permissions for Pages deployment
- ✅ Manual workflow trigger support
- ✅ npm caching for faster builds

### Benefits
- **Official GitHub Actions**: Uses GitHub's recommended approach
- **Better Security**: Fine-grained permissions with id-token
- **Improved Performance**: npm caching reduces build time
- **Manual Control**: Can trigger deployment on-demand
- **Environment Tracking**: Creates github-pages environment with deployment URL

## Troubleshooting

**Workflow not visible?**
→ Ensure this PR is merged to `main` branch

**Build fails?**
→ Check Actions tab for logs, verify dependencies

**404 errors?**
→ Verify GitHub Pages source is set to "GitHub Actions"

**Need help?**
→ See full documentation files in this directory
