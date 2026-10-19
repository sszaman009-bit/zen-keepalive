# zen-keepalive

Pings https://zenporcelainbd.com every 5 minutes so the Hostinger Node app never falls asleep. Without it, the first visitor after a
quiet spell or a deploy can wait about 20 seconds for the first page.

- Workflow: `.github/workflows/keepalive.yml` (GitHub Actions, free because this repository is public).
- It only requests three public pages: `/api/health`, `/` and `/products/sea-green`. No code or secrets live here.
- A weekly job re-enables the schedule so GitHub does not pause it after 60 days without commits.
- To stop it: Actions tab -> "Keep zenporcelainbd.com awake" -> "..." -> Disable workflow (or delete this repository).
