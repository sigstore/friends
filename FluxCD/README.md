# Flux

The [Flux project](https://fluxcd.io/) is the vendor-neutral home for GitOps in a Cloud Native world.

- The Flux team is an active user of the sigstore project. 
- We use cosign to sign the container images of [Flagger](https://flagger.app) 
  (the progressive delivery operator for Kubernetes) and soon we'll be rolling
  cosign signing across all Flux controllers.
- Flux protects your GitOps delivery pipeline from identity theft with GPG signature verification, 
  we look forward to collaborating with the Sigstore team on enabling cosign signature verification for
  Kubernetes manifests stored as OCI artifacts.
