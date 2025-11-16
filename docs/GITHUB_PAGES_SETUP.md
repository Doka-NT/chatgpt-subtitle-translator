# GitHub Pages Setup Guide

This document explains how to enable and configure GitHub Pages for this repository.

## Overview

The repository includes a GitHub Actions workflow (`.github/workflows/deploy.yml`) that automatically builds and deploys the web interface to GitHub Pages whenever code is pushed to the `main` branch.

## Prerequisites

- Repository admin access to configure GitHub Pages settings
- The workflow file must be present in the `main` branch

## Enabling GitHub Pages

Follow these steps to enable GitHub Pages for this repository:

### 1. Navigate to Repository Settings

1. Go to your repository on GitHub
2. Click on the **Settings** tab
3. In the left sidebar, click on **Pages** (under "Code and automation")

### 2. Configure GitHub Pages Source

1. Under **Build and deployment**, find the **Source** section
2. Select **GitHub Actions** from the dropdown menu
3. Click **Save** (if the button appears)

### 3. Trigger the Workflow

The workflow will automatically run when:
- Code is pushed to the `main` branch
- You manually trigger it via the Actions tab

To manually trigger the workflow:
1. Go to the **Actions** tab
2. Click on **Deploy to GitHub Pages** workflow
3. Click **Run workflow** button
4. Select the `main` branch
5. Click **Run workflow**

## Verifying the Deployment

After the workflow runs successfully:

1. Go to the **Actions** tab to see the workflow status
2. Once the deployment is complete, your site will be available at:
   ```
   https://<username>.github.io/chatgpt-subtitle-translator/
   ```
   Replace `<username>` with your GitHub username or organization name

3. You can also find the URL in:
   - Repository Settings → Pages (under "Your site is live at...")
   - The workflow run details (click on a completed workflow run)

## Workflow Details

The workflow consists of two jobs:

### Build Job
- Checks out the repository
- Sets up Node.js 22
- Installs dependencies with npm caching
- Builds the Next.js application in static export mode
- Uploads the build artifacts

### Deploy Job
- Deploys the artifacts to GitHub Pages
- Creates a deployment environment called `github-pages`
- Provides the deployment URL

## Troubleshooting

### Workflow Not Appearing
- Ensure the workflow file is in the `main` branch
- Check that the file is located at `.github/workflows/deploy.yml`

### Build Failures
- Check the workflow logs in the Actions tab
- Ensure all dependencies are correctly specified in `web/package.json`
- Verify that the Next.js configuration in `web/next.config.js` is correct

### Deployment Failures
- Verify that GitHub Pages is enabled in repository settings
- Check that the workflow has the correct permissions
- Ensure the source is set to "GitHub Actions" (not "Deploy from a branch")

### 404 Errors After Deployment
- Verify the `basePath` in `web/next.config.js` matches your repository name
- Check that all internal links use the correct base path

## Configuration Files

Key files for GitHub Pages deployment:

- `.github/workflows/deploy.yml` - GitHub Actions workflow
- `web/next.config.js` - Next.js configuration with basePath
- `web/package.json` - Dependencies and build scripts

## Additional Resources

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [GitHub Actions for Pages](https://github.com/actions/deploy-pages)
- [Next.js Static Exports](https://nextjs.org/docs/app/building-your-application/deploying/static-exports)
