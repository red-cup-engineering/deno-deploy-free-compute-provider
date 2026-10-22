# Deno Deploy Free Compute Provider

<!-- 561-group-standards:badges:start -->
[![Red Cup Engineering](https://img.shields.io/badge/561%20Group-Red%20Cup%20Engineering-c0392b)](https://github.com/red-cup-engineering)
[![License: MIT](https://img.shields.io/badge/license-MIT-c0392b)](LICENSE)
[![Indigenous data: CARE](https://img.shields.io/badge/Indigenous%20data-CARE-4b6f44)](https://github.com/red-cup-engineering/.github/blob/main/GOVERNANCE.md)
[![Tips welcome](https://img.shields.io/badge/tips-welcome-d4a017)](https://github.com/561-group/.github/blob/main/TIPS.md)
<!-- 561-group-standards:badges:end -->

This provider supplies authenticated, low-latency, restart-safe deterministic
edge computation. Deployment and invocation are admitted only while Deno's live
organization record says `free_verified`; Deno pauses Free applications on
allowance exhaustion instead of charging overage.

The cloud app holds only an Ed25519 public key. The settlement-owned private key
signs requests locally and is never uploaded. Direct requests expire
after 15 minutes so the same authorization can survive bounded hosted-runner
admission without becoming a durable credential. The app exposes public
`GET /health` plus signed `POST /v1/sha256` and `POST /v1/pbkdf2`. It has no
outbound fetch, upload, shell, dependency, environment secret, database, queue,
cron, model, or persistent state.
