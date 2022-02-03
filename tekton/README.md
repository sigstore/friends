# tekton

[tekton](https://tekton.dev/) is an open source cloud native CI/CD system. 

Tekton uses sigstore to:
- Sign releases with cosign
- Store provenance for release builds in Rekor

The [Tekton Chains](https://github.com/tektoncd/chains) project also depends on Sigstore under the hood.
* It uses cosign for signing images and blobs
* It enables keyless signing with cosign libraries and Fulcio
* Generates signed provenance for storage in Rekore
* Relies on the sigstore/sigstore library to provide users with various options for signing
