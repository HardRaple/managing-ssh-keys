# managing-ssh-keys
Make it easy to add new keys and remove old ones. These 3 python scripts will help delete old keys and add new ones using a QR code.

## Requirements
* Python 3 with python-qrcode module
* ssh-keygen utility
* at least one key without timestamp, preferably on phone to add ssh keys from QR code

## Installation
1. put scripts in /bin or ~/bin folder
2. configure your .bashrc or other shell initial file to execute cleanup-old-keys on shell startup
##### if you use ~/bin folder for scripts, add this folder to your PATH, for example, via .bashrc:
```
export PATH="~/bin:$PATH"
```

## Usage
* ssh-qrkey to generate new pair of keys and get a QR code of public key
* ssh-addkey <public key as provided by qr code scanner, without ""> to add key to authorized_keys
* cleanup-old-keys should be executed on every shell startup to seek for old keys in authorized_keys. Keys without timestamp will be ignored.