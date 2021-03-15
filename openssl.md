# `openssl`

## Convert an ssh pub key to rsa pub key
```sh
	ssh-keygen -f ~/.ssh/id_rsa.pub -e -m PKCS8 > ~/.ssh/id_rsa.pem.pub
```
(Found Here)[https://superuser.com/a/576558]

## Encrypt/Decrypt Files with Public Key
```sh
# Encrypt Passphrase
openssl rsautl -encrypt -inkey ~/.ssh/id_rsa.pem.pub -pubin -in pass.txt -out pass.txt.enc

# Decrypt Passphrase
openssl rsautl -decrypt -inkey ~/.ssh/id_rsa -in pass.txt.enc -out pass.txt
```
(Found Here)[https://kulkarniamit.github.io/whatwhyhow/howto/encrypt-decrypt-file-using-rsa-public-private-keys.html]

## Encrypt/Decrypt Files with Passphrase

> Security Warning: AES-256-CBC does not provide authenticated encryption and is vulnerable to padding oracle attacks. You should use something like age instead.
```sh
# Encrypt:
openssl aes-256-cbc -salt -in secrets.txt -out secrets.txt.enc

# Decrypt:
openssl aes-256-cbc -d -in secrets.txt.enc -out secrets.txt.new
```
(Found Here)[https://stackoverflow.com/a/16056298/11891816]
