# Operational-readiness checklist

The Infrastructure Operations Toolkit demonstrates monitoring, evidence capture, incident escalation, backup creation, and SHA-256 backup verification in a small lab. This checklist defines the controls needed before adapting the workflow to a real hosting environment.

## Monitoring

- Define service owners, expected ports/endpoints, timeout budgets, and escalation thresholds.
- Separate transient degradation from confirmed outage states and avoid alerting on a single noisy sample where inappropriate.
- Time-stamp evidence consistently and preserve enough context to reproduce an incident timeline.
- Protect monitoring configuration from unauthorized changes.

## Incident operations

- Assign severity criteria, on-call ownership, communication paths, and escalation deadlines.
- Record actions taken, evidence collected, recovery steps, and verification results.
- Keep recovery commands and credentials out of public logs or tickets.
- Require post-recovery validation instead of treating process restart as proof of restoration.

## Backup and recovery

- Verify backups with integrity checks, but also perform periodic restore tests.
- Define retention, rotation, encryption, off-site/independent copy, and access-control requirements.
- Alert on failed, stale, or unexpectedly small backups.
- Record backup source, destination, timestamp, hash, and restore-test outcome.

## Security and reliability

- Run monitoring and backup jobs with least privilege.
- Store secrets outside source control and rotate them when access changes.
- Add structured log retention, clock synchronization, dependency monitoring, and host hardening for production use.
- Test failure cases such as unreachable hosts, permission errors, corrupt backups, partial writes, and disk exhaustion.

The current repository remains a portfolio lab; production availability, backup durability, and recovery-time claims should only be made after deployment-specific testing and measurement.
