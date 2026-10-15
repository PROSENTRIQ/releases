# Verifying Prosentriq artifacts

Every artifact and image is signed by the release workflow
`PROSENTRIQ/prosentriq-core/.github/workflows/release.yml` running on a `v*`
tag. The signatures are recorded in the public Rekor transparency log. Each
command below checks that identity; if it fails, don't install.

## Container images

Verify by digest, not by tag:

```bash
cosign verify ghcr.io/prosentriq/agent@sha256:… \
  --certificate-identity-regexp '^https://github.com/PROSENTRIQ/prosentriq-core/\.github/workflows/release\.yml@refs/tags/v' \
  --certificate-oidc-issuer https://token.actions.githubusercontent.com
```

## The installer and packages

Download the file and its `.sigstore.json` bundle from the release, then:

```bash
cosign verify-blob install.sh --bundle install.sh.sigstore.json \
  --certificate-identity-regexp '^https://github.com/PROSENTRIQ/prosentriq-core/\.github/workflows/release\.yml@refs/tags/v' \
  --certificate-oidc-issuer https://token.actions.githubusercontent.com
```

The same command works for each `.deb`, `.rpm` and SBOM with its own bundle.

The apt and dnf repositories that `install.sh` configures are signed with our
repository key, and `install.sh` pins that key's fingerprint, so packages
installed through them are checked by your package manager as well.
