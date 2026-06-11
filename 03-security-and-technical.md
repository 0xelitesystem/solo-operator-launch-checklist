# Security and technical

Before launch, confirm the security and technical foundations: no secrets in front-end code, HTTPS site-wide, basic security headers, working backups, and rate limits on anything that costs money. These are the items whose absence causes the worst, least visible problems.

## Secrets and keys

Make sure no API keys, tokens, or passwords are sitting in client-side code, public repositories, or anything that ships to the browser. Keys belong server-side or behind a proxy. A leaked key can be abused to run up costs or access data, and automated scanners find exposed keys quickly. Confirming that secrets are not exposed is one of the highest-value pre-launch checks a solo operator can run.

## HTTPS and headers

Serve the entire site over HTTPS, with HTTP redirecting to it, so traffic is encrypted. Add the straightforward security headers that tell browsers to behave more safely. Most hosts make HTTPS easy and ship basic headers, so this is often configuration rather than work. The result is a site that protects its visitors' traffic and avoids browser warnings, which is table stakes for a launch today.

## Backups

Confirm that backups run automatically, cover both files and data, are stored somewhere separate from the live site, and that you have actually tested a restore. For a solo operator, a working backup is what turns a disaster, a hack, a host failure, a mistake, into an inconvenience instead of the end of the project. If you confirm only one technical item before launch, make it that backups work and restore.

## Rate limits and cost ceilings

Anything public that costs money to run, such as calls to a paid API, needs rate limits and a spending ceiling, so that abuse or a bug cannot run up an unbounded bill. A public endpoint without limits is an open invitation to cost. Confirming caps and limits before launch means that even if something goes wrong or someone abuses the system, the financial damage stops at a known maximum rather than continuing unchecked.
