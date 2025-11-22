# GitHub App: GitFlows App

Purpose:
This GitHub App scaffold supports automated PR creation, automated approvals, and auto-merges for repo workflows. Use this repo as the code + runbook for the App, plus example Actions that use a bot identity.

Quick steps:
1. Register the App in GitHub (Settings → Developer settings → GitHub Apps) or use the manifest.yml included.
2. Set the App webhook URL to your handler (or use a placeholder during initial setup).
3. Grant the App the minimal permissions described below and install it on target repos.
4. Add secrets to repo/org secrets as described in docs/secret-setup-example.md.
5. Use the provided workflows as examples; adapt to your security posture (machine user PAT vs GitHub App installation tokens).

Recommended permissions (least privilege):
- Pull requests: read & write
- Contents: read
- Checks: read & write
- Issues: read & write (if creating issues for failures)
- Metadata: read

Events to subscribe to (webhooks):
- pull_request
- pull_request_review
- workflow_run

Security notes:
- Prefer GitHub App installation tokens over machine PATs for production.
- Store private key / PAT in org secrets, not in plaintext.
- Limit App installation to only the repositories that require automation.

Files in this folder:
- manifest.yml — App manifest for registration
- runbook.md — runbook for token generation and rotation

