# Security policy

This is the default policy for repositories in the bomwerk organisation. A repository that has its own `SECURITY.md` follows that one instead.

## Reporting a vulnerability

Report privately through **GitHub's private vulnerability reporting** on the repository concerned: the *Security* tab, then *Report a vulnerability*. Please do not open a public issue for a suspected vulnerability.

If the repository does not offer that form, or you cannot use it, write to **info@bomwerk.com** and say up front that the message concerns a vulnerability. Use hello@bomwerk.com for everything else.

Useful in a report: what you ran, what happened, what you expected, the version (`bomwerk --version`) and the platform. A repository or file that reproduces the behaviour is the fastest path to a fix. If it cannot be shared, a description of its shape usually gets us there too.

You will get an acknowledgement within three working days and an assessment, with a fix or a plan, within ten. We will tell you when a fix ships and credit you in the release notes unless you would rather we did not.

## What is in scope

bomwerk reads repositories that it treats as hostile by design. The following are vulnerabilities, not expected behaviour:

- a crafted manifest, lockfile, archive or binary that crashes the scanner, hangs it, or makes it read or write outside the paths it was given;
- anything that causes the scanner to execute code from the repository it is scanning, including through a build tool or a repository-local configuration;
- a network request to a host that is not in the allowlist printed by `bomwerk --endpoints`, or any transmission of scanned source;
- output that misrepresents what was checked, for example a component reported as clean when its data was never fetched.

## What is not a vulnerability

- A missed component, a wrong version, or an unmatched advisory. Those are accuracy bugs. Please open a normal issue, they are just as welcome.
- The absence of an SBOM for an ecosystem bomwerk does not parse yet.
- Findings produced by scanning a deliberately malicious repository, when the scanner reported them and stayed within its own process and output paths.
- Problems in third-party components that a repository vendors on purpose, such as the test corpus in [bomwerk/nightmare](https://github.com/bomwerk/nightmare). Report those to the upstream project.

## Supported versions

Until 1.0, only the latest release receives fixes.
