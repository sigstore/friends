# Kyverno

[Kyverno](https://kyverno.io/) is a Kubernetes native policy engine that simplifies configuration security and automation for clusters and workloads. The Kyverno is an active user of the sigstore project:

## Kyverno policies for image verification with Cosign

Kyverno policies are applied within Kubernetes clusters at admission controls. They can be used to verify Cosign signatures for container images. Here is a sample:

```yaml
apiVersion: kyverno.io/v1
kind: ClusterPolicy
metadata:
  name: check-image
spec:
  validationFailureAction: enforce
  background: false
  webhookTimeoutSeconds: 30
  failurePolicy: Fail
  rules:
    - name: check-image
      match:
        resources:
          kinds:
            - Pod
      verifyImages:
      - image: "ghcr.io/kyverno/test-verify-image:*"
        key: |-
          -----BEGIN PUBLIC KEY-----
          MFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAE8nXRh950IZbRj8Ra/N9sbqOPZrfM
          5/KAQN0/KjHcorm/J5yctVd7iEcnessRQjU917hmKO6JWVGHpDguIyakZA==
          -----END PUBLIC KEY-----          
```

Kyverno policies can also verify [in-toto attestations](https://github.com/in-toto/attestation):

```yaml
apiVersion: kyverno.io/v1
kind: ClusterPolicy
metadata:
  name: attest-code-review
  annotations:
    pod-policies.kyverno.io/autogen-controllers: none
spec:
  validationFailureAction: enforce
  background: false
  webhookTimeoutSeconds: 30
  failurePolicy: Fail
  rules:
    - name: attest
      match:
        resources:
          kinds:
            - Pod
      verifyImages:
      - image: "registry.io/org/*"
        key: |-
          -----BEGIN PUBLIC KEY-----
          MFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAEHMmDjK65krAyDaGaeyWNzgvIu155
          JI50B2vezCw8+3CVeE0lJTL5dbL3OP98Za0oAEBJcOxky8Riy/XcmfKZbw==
          -----END PUBLIC KEY-----          
        attestations:
          - predicateType: https://example.com/CodeReview/v1
            conditions:
              - all:
                - key: "{{ repo.uri }}"
                  operator: Equals
                  value: "https://git-repo.com/org/app"            
                - key: "{{ repo.branch }}"
                  operator: Equals
                  value: "main"
                - key: "{{ reviewers }}"
                  operator: In
                  value: ["ana@example.com", "bob@example.com"]

```

More details at: https://kyverno.io/docs/writing-policies/verify-images/.

## Signed Kyverno container images and SBOMs

Kyverno container images are signed using Cosign with a [public key](https://github.com/kyverno/kyverno/blob/main/cosign.pub). Container image signatures and a signed SBOM are available at:

  * https://github.com/orgs/kyverno/packages/container/package/signatures

  * https://github.com/orgs/kyverno/packages/container/package/sbom

