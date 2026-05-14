# GitHub Actions Setup Guide

## How It Works

1. **GitHub Actions Workflow** (`.github/workflows/fetch-news.yml`) runs every hour
2. Fetches latest news from NewsData.io API using a **secret API key** (not exposed in code)
3. Saves results to `news.json` 
4. Commits and pushes changes to the repository
5. Your website reads from the local `news.json` file instead of calling the API directly

## Setup Steps

### 1. Add Your API Key as a Secret

1. Go to your GitHub repository
2. Navigate to **Settings → Secrets and variables → Actions**
3. Click **New repository secret**
4. Name: `NEWSDATA_API_KEY`
5. Value: Your NewsData.io API key (e.g., `pub_xxxxx...`)
6. Click **Add secret**

### 2. Enable Workflow Permissions

1. Go to **Settings → Actions → General**
2. Under "Workflow permissions", select **Read and write permissions**
3. Check **Allow GitHub Actions to create and approve pull requests**
4. Save

### 3. Trigger the First Fetch (Optional)

The workflow will run automatically on the next hour. To test immediately:

1. Go to **Actions** tab
2. Select **Fetch News Hourly**
3. Click **Run workflow**
4. Select **Run workflow**

## Files

- `.github/workflows/fetch-news.yml` - The GitHub Actions workflow
- `news.json` - Cached news data (auto-updated hourly)
- `index.html` - Updated to read from `news.json` instead of API

## Benefits

✅ API key stays private (stored as GitHub secret)
✅ No quota burned by website visitors
✅ Faster page loads (serving cached JSON)
✅ News updates predictably every hour
✅ Git history tracks all news updates
