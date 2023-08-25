# Venafi, Inc.

[Venafi](https://www.venafi.com) is the leader in machine identity management.

[Venafi CodeSign Protect](https://venafi.com/codesign-protect/) integrates with sigstore/cosign via PKCS#11 to provide strong controls over the enterprise code signing keys and certificates, used to sign container images and other artifacts such as SBOMs.

Venafi also uses sigstore/cosign to sign its internally developed container images.

[Jetstack](https://jetstack.io), a Venafi company, helps businesses to build and operate modern cloud native infrastructure with Kubernetes.

Jetstack also designed and maintains the CNCF [cert-manager](https://github.com/cert-manager/cert-manager) project – the de facto cloud native solution for developers to automate TLS and mTLS certificate issuance and renewal.

* Jetstack is an active user of the sigstore project
* We use sigstore/cosign to sign our open source container images along with [SLSA provenance](https://slsa.dev/provenance/v0.2) and a [CycloneDX SBOM](https://cyclonedx.org/).
