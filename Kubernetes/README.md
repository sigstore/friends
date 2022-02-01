# Kubernetes
![Kubernetes Logo](1280px-Kubernetes_logo.svg.png  "Kubernetes")



The Kubernetes Release Engineering team is working on two KEPs
(Kubernetes Enhancement Proposals) which rely on the sigstore 
infrastructure.

## KEP-3031: [Signing Release Artifacts](https://github.com/kubernetes/enhancements/tree/master/keps/sig-release/3031-signing-release-artifacts)

Currently targeting the v1.24 release, this KEP describes the project
to sign all artifacts produced as part of a Kubernetes release:
container images, binaries, source tarballs, SBOMs. Sigstore code
is already in use in the release tooling and development is underway
to enable signing and verification in the release infrastructure in 
projects like [`krel` The Kubernetes Release Toolbox](https://github.com/kubernetes/release/tree/master/docs/krel), the [conatiner
and artifact promoter](https://github.com/kubernetes-sigs/promo-tools)
and the [Kubernetes SBOM tool](https://github.com/kubernetes-sigs/bom).

## KEP-3027 [SLSA Level 3 Compliance in the Kubernetes Release Process](https://github.com/kubernetes/enhancements/tree/master/keps/sig-release/3027-slsa-compliance)

In parallel, we are working on KEP-3027 which lays the road towards
SLSA ([Supply chain Levels for Software Artifacts](https://slsa.dev))
Level 3 compliance
in our release process. SLSA 3 requires non-falsifiable provenance 
metadata and the project leverages sigstore to sign attestations and
other internal processes.

