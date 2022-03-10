# SUSE

- [SUSE](https://www.suse.com) is implementing sigstore methods in its Container and Product deliveries.
- The [SUSE Container Registry](https://registry.suse.com/) is now also signing the SUSE containers using Cosign (additionally to Notary and Atomic methods) and also uploading signatures to the Linux Foundation Transparency Rekor log.
- Our SUSE Linux Enterprise update repositories signatures are also being uploaded to the Linux Foundation Transparency Rekor log.
- SUSE Linux Enterprise 15 SP4 will contain, and openSUSE Tumbleweed already contains Cosign and Rekor tooling.
- [Kubewarden](https://kubewarden.io/) uses sigstore in the following contexts:
  * Signature and verification of its WebAssembly policies
  * Allow policy authors to leverage sigstore verification capabilities inside of their policies. That allows the creation of policies that can validate OCI artifacts using sigstore
