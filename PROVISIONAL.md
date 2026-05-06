# Experimental Federation and Trust Material

This document outlines provisional mechanisms for style federation and trust in the Citum ecosystem. These features are intended to support decentralized style distribution while maintaining security and integrity.

## Content Integrity (CIDs)

Citum supports pinning style dependencies to specific versions using CIDs (Content Identifiers).

Example pin for the thesis base:
```yaml
extends: https://raw.githubusercontent.com/example-org/citum-styles/main/styles/university-thesis.yaml
extends-pin: bafybeigdyrzt5sfp7udm7hu76uh7y26nf3efuylqabf3oclgtqy55fbzdi
```

## Registry Signatures (Future)

To prevent index tampering, registry files can be cryptographically signed.

```yaml
# citum-registry.yaml (Provisional)
version: "1"
signature: "eyAiYWxnIjogIlJTNTEyIiwgInR5cCI6ICJKV1QiIH0..." # RS512 signature of the styles list
styles:
  - id: university-thesis
    path: styles/university-thesis.yaml
```

## Discovery

Institutional registries can be discovered via RFC 8615 well-known URLs:
`https://example.edu/.well-known/citum-registry.yaml`
