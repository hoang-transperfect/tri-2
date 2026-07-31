# Security Policy

## Supported versions

| Version | Supported |
| --- | --- |
| 0.x (latest) | ✅ |

## Reporting a vulnerability

**Please do not report security vulnerabilities through public GitHub issues.**

Instead, open a [GitHub Security Advisory](https://github.com/hoang-transperfect/tri-2/security/advisories/new) (private disclosure). Include:

- A description of the vulnerability and its potential impact
- Steps to reproduce or a proof-of-concept
- The affected version(s)

You will receive an acknowledgement within **72 hours** and a resolution timeline within **7 days**.

## Scope

This is a React UI component library. The attack surface is limited to:

- **XSS via props** — components should never render user-supplied strings as raw HTML. If you find a case where they do, that is in scope.
- **Malicious dependency** — if a dependency is compromised upstream, please report it here so we can issue a patch release quickly.

Client-side rendering bugs that require the consuming application to pass attacker-controlled data are generally out of scope but will be evaluated case by case.
