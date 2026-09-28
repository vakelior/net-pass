# net-pass

Unlock YouTube & Google on a social-only data plan (Maroc Telecom / Orange / inwi) using a free GitHub Actions runner as a SOCKS5 proxy tunnel.

## Quick start

1. Generate an SSH key locally: `ssh-keygen -t ed25519 -C "you@example.com"`
2. Copy `~/.ssh/id_ed25519.pub` content into a repo secret named `SSH_PUBKEY` (Settings → Secrets and variables → Actions).
3. Run the workflow manually (Actions → net-pass → Run workflow).
4. Get the runner IP from the workflow logs (it prints a public URL + IP).
5. Connect: `ssh -p 2222 -D 1080 -N runner@<RUNNER_IP>`
6. Set your browser/app to use SOCKS5 proxy `localhost:1080`.

## Important

- GitHub-hosted runners live max ~6 hours, then the tunnel dies. Re-run to renew.
- The public runner IP changes every run.
- This is for educational / personal use. Use responsibly.
