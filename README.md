# Renovate Bot Configuration

Central Renovate configuration and scheduled runner for AmadeusITGroup repositories.

## Configuration presets

| File | Purpose |
| --- | --- |
| `default.json` | Organization-wide dependency-update policy, labels, dashboards, release cooldowns, and dependency grouping. |
| `node.json` | Node.js-specific rules for lock-file maintenance, lint tooling, and Node/pnpm runtime updates. |
| `renovate.json` | Base Renovate configuration using Renovate's recommended preset. |

Repositories can extend a preset from their `renovate.json`:

```json
{
  "extends": ["github>AmadeusITGroup/renovate-config"]
}
```

For Node.js repositories, also extend the Node preset:

```json
{
  "extends": [
    "github>AmadeusITGroup/renovate-config",
    "github>AmadeusITGroup/renovate-config:node"
  ]
}
```

## Scheduled runner

The [Renovate workflow](.github/workflows/renovate-bot-cron.yml) runs on the first day of each month at 00:00 UTC. It can also be started manually from the Actions tab:

- Leave `repository` empty to scan repositories owned by the current organization.
- Set `repository` to `repository-name` or `owner/repository-name` to scan one repository.
- Select the desired `log_level` when troubleshooting.