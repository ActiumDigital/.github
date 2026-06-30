# Power BI Project

## Overview
[Add project description and business purpose]

## Quick Start

### Prerequisites
- Power BI Desktop (version X.X or later)
- Access to data sources (see Data Access section)
- Optional: Python 3.8+ (if using custom scripts)

### Setup
1. Clone this repository
2. Copy `.env.example` to `.env` and configure your credentials
3. Open `reports/main-report.pbix` in Power BI Desktop
4. Refresh data sources
5. Save locally

### Important - DO NOT commit:
- Credentials or connection strings
- Personal `.pbix.user` files
- Local cache files (`.pbi/`, `cache.abf`)
- `.env` file (only commit `.env.example`)

## Project Structure
```
├── reports/          # Power BI reports (.pbix)
├── data/             # Data files and scripts
│   ├── raw/          # Source data (gitignored)
│   └── processed/    # Staging data
├── scripts/          # Python/SQL preparation scripts
├── docs/             # Documentation
├── config/           # Metadata and configurations
└── .github/          # CI/CD workflows
```

## Data Model
[Link to or description of dimensional model, key tables, relationships]

## Refresh Schedule
- **Frequency**: [Daily/Weekly/Monthly]
- **Time**: [UTC time]
- **Owner**: [Team/Person]

See `docs/refresh-guide.md` for detailed refresh procedures.

## Metrics Dictionary
Key measures and dimensions are documented in `docs/metrics-dictionary.md`

## Support
For issues or questions:
1. Check `docs/` for FAQs
2. Contact [Team/Owner]
3. Create an issue in this repository

## Security
See `SECURITY.md` for data protection and access control guidelines.
