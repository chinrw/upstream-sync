# Upstream synchronization

This repository keeps `chinrw/asterinas`'s `main` branch synchronized with
`asterinas/asterinas` without adding configuration commits to the fork.
GitHub Actions checks every hour at minute 23. Scheduled runs may be delayed.

To run a check immediately, open **Actions → Sync Asterinas upstream → Run workflow**.
Only fast-forward updates are allowed. If the fork's `main` contains commits
absent from upstream, the job fails and preserves those commits. Keep development
work on separate branches.

The `ASTERINAS_SYNC_SSH_KEY` Actions secret holds a dedicated SSH deploy key
with write access to `chinrw/asterinas`. To stop synchronization, disable the
workflow. To revoke its access, delete the `upstream-sync` deploy key from the
fork's **Settings → Deploy keys**.
