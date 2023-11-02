# ComplyHub.dev sigstore public key

🔑 sigstore public key to verify provided data

This repository acts as the official source for getting the sigstore public key used
to verify artifact signatures published by [ComplyHub.dev](https://complyhub.dev/).

The public key provided by the `cosign.pub` file is signed using the [sigstore-python GitHub action](https://github.com/sigstore/gh-action-sigstore-python).
Verifying the signature requires installing the [sigstore-python](https://github.com/sigstore/sigstore-python) client.

To securely download the public key, run the following commands:

```
# Download the public key release artifact
wget https://github.com/ComplyHubDev/sigstore-pubkey/releases/cosign.pub

# Download the artifact Sigstore bundle containing the verification materials
wget https://github.com/ComplyHubDev/sigstore-pubkey/releases/cosign.pub.sigstore

# Verify the signature authenticity with sigstore-python
sigstore verify github \
--cert-identity https://github.com/sigstore/sigstore-python/.github/workflows/sign-pubkey.yaml \
--bundle cosign.pub.sigstore \
cosign.pub
```
