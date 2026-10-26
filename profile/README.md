# bomwerk

**Build-accurate SBOMs and EU Cyber Resilience Act evidence, on your own machine.**

bomwerk is a command-line scanner for teams that ship software into the EU and have to say, on paper, what is inside it. It reads a repository, writes a CycloneDX or SPDX inventory, and for C and C++ it can check that inventory against what the build actually compiled and linked. It tells you plainly what it could not check.

It runs entirely on your machine. There is no account, no server and no telemetry, and your source is never uploaded.

## Community and Pro

- **Community** is Apache-2.0, unlimited and free. It is the whole scanner: `scan`, `observe`, `trim` and `binscan`. It lives in [bomwerk/bomwerk](https://github.com/bomwerk/bomwerk).
- **Pro** is in preview and adds registry, monitoring and reporting for compliance teams. It is available to design partners by agreement and is not something you can install yet. Write to [hello@bomwerk.com](mailto:hello@bomwerk.com) if that is you.

## Try it today

Release candidate `1.0.0-rc.2`. There are no prebuilt binaries yet, so build from source:

```bash
git clone --branch v1.0.0-rc.2 --recurse-submodules https://github.com/bomwerk/bomwerk.git
cd bomwerk
cmake -S . -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build --parallel
```

The first build compiles the pinned dependencies and takes a while. Then, from the directory you want to scan:

```bash
bomwerk scan .
bomwerk scan . --format spdx -o sbom.spdx.json
bomwerk scan . --html report.html
```

What works today, what is planned, and the test behind each claim are listed in the [capability ledger](https://github.com/bomwerk/bomwerk/blob/main/docs/capabilities.md).

## Test corpus

[bomwerk/nightmare](https://github.com/bomwerk/nightmare) is a small C project with a hand-checked answer key, built to find out which scanners see what is really inside a build.

## Where to go next

- Website: [bomwerk.com](https://bomwerk.com)
- Documentation: [bomwerk.com/docs](https://bomwerk.com/docs/)
- General questions: [hello@bomwerk.com](mailto:hello@bomwerk.com)
- Security reports: see our [security policy](https://github.com/bomwerk/.github/blob/main/SECURITY.md)
- LinkedIn: [bomwerk](https://www.linkedin.com/company/bomwerk/)
