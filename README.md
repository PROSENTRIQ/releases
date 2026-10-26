# Prosentriq releases

This repository holds no code. Its [Releases](https://github.com/PROSENTRIQ/releases/releases)
carry what you install, written by our release workflow:

- `install.sh`, the Linux installer, with its Sigstore bundle
- `.deb` and `.rpm` packages (x86_64 and ARM64), each with a Sigstore bundle
- SBOMs (SPDX) for the packages (images carry theirs as attestations)
- Release notes

Container images (`ghcr.io/prosentriq/agent` and others) and the Helm chart
(`oci://ghcr.io/prosentriq/charts/prosentriq-agent`) are published to GitHub
Container Registry with each release.

Each release also has a `SHA256SUMS` file covering every file in it.

Installing: see [PROSENTRIQ/docs](https://github.com/PROSENTRIQ/docs), starting
with [Linux hosts](https://github.com/PROSENTRIQ/docs/blob/main/install/linux.md).

## Verify before you install

Everything is signed keylessly with [Sigstore](https://www.sigstore.dev/): the
signature proves that an artifact was built by Prosentriq's release workflow
from a release tag in our repository. Install [cosign](https://docs.sigstore.dev/cosign/system_config/installation/),
then check [VERIFY.md](VERIFY.md).

## Security

Report vulnerabilities privately; see the
[security policy](SECURITY.md).
