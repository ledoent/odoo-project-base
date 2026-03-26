# odoo-project-base

Odoo project template with automated browser QA testing via [odoo-qa](https://github.com/ledoent/odoo-qa).

## Quick start

```bash
# 1. Initialize Odoo with demo data (first time only)
docker compose run --rm odoo-init

# 2. Start Odoo
docker compose up -d odoo

# 3. Run QA tests
docker compose run --rm qa

# 4. View results
open test-results/report/index.html
```

## Capture baseline screenshots

```bash
docker compose run --rm qa-baseline
# Screenshots saved to baseline/checkpoints/
# Manifest saved to baseline/baseline-manifest.json
```

## CI

PRs automatically run QA tests via GitHub Actions. See `.github/workflows/qa-on-pr.yml`.

## Configuration

| Variable | Default | Description |
|----------|---------|-------------|
| `ODOO_VERSION` | `19.0` | Odoo Docker image version |
| `ODOO_PORT` | `8069` | Host port for Odoo |
| `ODOO_DB` | `odoo` | Database name |

## Adding custom addons

Place OCA or custom addons in `addons/`. They'll be available to Odoo at `/mnt/extra-addons`.
