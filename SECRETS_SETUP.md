# GitHub Actions Secrets Setup

This document outlines the required secrets for the GitHub Follower Bot automation workflow.

## Required Secrets

The following secrets must be configured in your repository settings under **Settings > Secrets and variables > Actions**:

### 1. `PERSONAL_GITHUB_TOKEN`
- **Description**: Your GitHub Personal Access Token for API access
- **Required Scopes**: 
  - `user:follow` (to follow users)
  - `read:user` (to read user data) 
  - `public_repo` (if working with public repositories)
- **How to create**: Go to GitHub Settings > Developer settings > Personal access tokens > Tokens (classic)

### 2. `GITHUB_USER`
- **Description**: Your GitHub username
- **Example**: `yourusername`
- **Usage**: Used by the bot to fetch your followers list

### 3. `GIT_USER_NAME`
- **Description**: The name to use for automated git commits
- **Example**: `Your Full Name` or `GitHub Bot`
- **Usage**: Sets the git user.name for automated commits

### 4. `GIT_USER_EMAIL`
- **Description**: The email to use for automated git commits  
- **Example**: `your.email@example.com` or `noreply@github.com`
- **Usage**: Sets the git user.email for automated commits

## How to Add Secrets

1. Go to your repository on GitHub
2. Click on **Settings** in the repository menu
3. In the left sidebar, click **Secrets and variables** > **Actions**
4. Click **New repository secret**
5. Add the secret name and value, then click **Add secret**
6. Repeat for all required secrets

## Security Notes

- Never commit these values to your repository
- Personal Access Tokens should be treated like passwords
- Use minimal required scopes for the Personal Access Token
- Consider using a dedicated GitHub account for automation if needed

## Verification

After adding all secrets, the workflow should run automatically according to the schedule or can be triggered manually from the Actions tab.