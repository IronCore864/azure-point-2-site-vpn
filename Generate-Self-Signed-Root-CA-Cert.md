# Generate a Self-Signed Root CA Cert

Note: This part is already done; just documenting how to do it.

## Create Root Key

Attention: this is the key used to sign the certificate requests, anyone holding this can sign certificates on your behalf. So keep it in a safe place!

```
openssl genrsa -des3 -out rootCA.key 4096
```

If you want a non password protected key just remove the -des3 option (in the key in this repo, there isn't a password for simpler usage).

## Create and self sign the Root Certificate

```
openssl req -x509 -new -nodes -key rootCA.key -sha256 -days 1024 -out rootCA.crt
```
