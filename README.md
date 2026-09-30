# Mission OTA

Secure OTA Update Platform for Connected Vehicles

## Status

Mission OTA demonstrates Eclipse Leda, Ankaios, containerd, nerdctl, OTA update, rollback, SHA-256 integrity verification, Ed25519 signature verification, and tamper detection.
## OTA Demonstration

- nginx:1.27-alpine -> nginx:1.28-alpine: PASS
- nginx:1.28-alpine -> nginx:1.27-alpine rollback: PASS

## Security Verification

- SHA-256 verification: PASS
- Ed25519 signature verification: PASS
- Tampered package: REJECTED
- Private signing key is excluded from Git
## Ankaios

Ankaios agent tests: 559 passed, 0 failed, 0 ignored.

A nerdctl label parser fix was required because the Leda environment can return Labels: null.

Known limitation: Ankaios workload state handling reports Failed(Unknown) - Error getting state from Nerdctl, while direct containerd/nerdctl execution works successfully.
## Evidence

See evidence/ for runtime, Ankaios, OTA, rollback, and security verification records.

See docs/setup/upstream-commits.txt for upstream source traceability.

## Project Structure

- ankaios/ - Ankaios source and modifications
- leda/ - Eclipse Leda source
- leda-qemu/ - local QEMU environment
- evidence/ - verification evidence
- docs/ - project documentation
- ota-release-v2/ - OTA release metadata

## Security Notice

Do not commit private keys, credentials, tokens, VM images, firmware bundles, or other sensitive artifacts.
