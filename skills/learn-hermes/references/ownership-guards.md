# Autonomous skill ownership guards

Hermes's background reviewer fails closed on autonomous skill writes. Preserve the same safety boundary in any host integration.

## Never autonomously mutate

- Bundled/protected skills shipped by the host.
- Hub/marketplace-installed skills when the host treats them as externally managed.
- Skills from external directories.
- Pinned skills.
- User-owned skills that were hand-written, URL-installed, or explicitly created by a foreground user action unless the host has an explicit adoption/curator mechanism.

A skill being loaded or relevant does not transfer ownership.

## Read before write

For an existing target, read the exact current skill before edit, patch, delete, support-file write, or support-file removal. This avoids stale autonomous mutation.

## Fail closed

If provenance/ownership cannot be established, do not mutate the skill. Report the blocked target and the reason instead.

Creating a new class-level skill is permitted when the host allows skill creation and there is no editable existing umbrella that fits.
