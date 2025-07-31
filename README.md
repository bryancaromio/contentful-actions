# Contentful CLI Workflows

This repository contains GitHub Actions workflows for managing Contentful spaces, including content migration, export, and import operations between different environments.

## Features

- Content Migration between environments
- Space Export/Import with configurable options
- Support for multiple environments (master, development, qa, stage)
- Asset handling
- Draft and archived content management

## Available Workflows

### 1. Contentful Migration

This workflow generates and applies migration scripts between Contentful environments.

**Inputs:**
- `source-environment-id`: Source environment (master, development, qa, stage)
- `target-environment-id`: Target environment (master, development, qa, stage)
- `preview-only`: Generate migration script without applying changes (default: true)

**Usage:**
1. Go to Actions → Contentful Migration
2. Click "Run workflow"
3. Select source and target environments
4. Choose whether to preview or apply the migration
5. Run the workflow

### 2. Contentful Space Export and Import

This workflow exports content from a source environment and imports it into a target environment.

**Inputs:**
- `source-environment-id`: Source environment
- `target-environment-id`: Target environment
- `include-drafts`: Include draft entries (optional)
- `include-archived`: Include archived entries (optional)
- `download-assets`: Download and re-upload assets (default: true)
- `skip-content-publishing`: Create content without publishing (optional)
- `content-model-only`: Import only content types (optional)
- `skip-content-model`: Skip importing content types and locales (optional)

**Usage:**
1. Go to Actions → Contentful Space Export and Import
2. Click "Run workflow"
3. Configure the desired options
4. Run the workflow

## Prerequisites

- Contentful Management Token (stored as `CONTENTFUL_MANAGEMENT_TOKEN` secret)
- Contentful Space ID (stored as `CONTENTFUL_SPACE_ID` secret)
- GitHub repository with Actions enabled

## Directory Structure

```
.
├── .github/workflows/
│   ├── contentful-migration.yml
│   └── contentful-export-import.yml
├── exports/            # Directory for export files
├── migrations/         # Directory for migration scripts
└── README.md
```

## Security Notes

- Never commit your Contentful tokens or sensitive data
- Always use GitHub Secrets for storing credentials
- Review migration scripts before applying them to production environments

## Artifacts

Both workflows generate artifacts that are stored in GitHub Actions:
- Migration scripts are retained for 7 days
- Export files are retained for 7 days

## Best Practices

1. Always preview migrations before applying them
2. Test changes in development/qa environments first
3. Schedule major migrations during off-peak hours
4. Keep backup exports before performing large migrations
5. Review logs and artifacts after each workflow run

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

[Add your license here] 