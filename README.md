# Contentful Actions

GitHub Actions workflows for managing Contentful spaces across environments.

## Quick Start

### Prerequisites
- Contentful Management Token (`CONTENTFUL_MANAGEMENT_TOKEN`)
- Contentful Space ID (`CONTENTFUL_SPACE_ID`)

Add these as GitHub Secrets in your repository.

## Workflows

### 1. Content Migration
Generate and apply migration scripts between environments.

**How to use:**
1. Go to Actions → Contentful Migration
2. Select source and target environments
3. Choose preview or apply mode
4. Run workflow

### 2. Export & Import
Export content from one environment and import to another.

**How to use:**
1. Go to Actions → Contentful Space Export and Import
2. Configure options (drafts, assets, etc.)
3. Run workflow

## Environments Supported
- master
- development  
- qa
- stage

## Security
- Use GitHub Secrets for tokens
- Preview migrations before applying
- Test in non-production first

## Artifacts
- Migration scripts and export files are kept for 7 days
- Available in Actions → Artifacts

## Contributing
1. Fork → Branch → Commit → Push → PR 