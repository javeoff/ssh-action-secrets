# 🚀 SSH for GitHub Actions (With Secrets Integration)

Referenced: https://github.com/appleboy/ssh-action/

## Usage

```yml
  - name: My SSH Script
	uses: javeoff/ssh-action-secrets@main
	with:
	  secrets: ${{ toJson(secrets) }}
	  script: |
		git pull
```

## Input variables
See action.yml for more detailed information.
* `script` - execute commands
* `envs` - environments collection
* `secrets` - secrets collection (may be inherited from github secrets)

## Secrets Variables
See action.yml for more detailed information.

* `SSH_HOST` - ssh host
* `SSH_PORT` - ssh port, default is `22`
* `SSH_USERNAME` - ssh username
* `SSH_PASSWORD` - ssh password
* `SSH_PASSPHRASE` - the passphrase is usually to encrypt the private key
* `SSH_SYNC` - synchronous execution if multiple hosts, default is false
* `SSH_TIMEOUT` - timeout for ssh to remote host, default is `30s`
* `SSH_COMMAND_TIMEOUT` - timeout for ssh command, default is `10m`
* `SSH_PRIVATE_KEY` - content of ssh private key. ex raw content of ~/.ssh/id_rsa, rembemer include the BEGIN and END lines
* `SSH_KEY_PATH` - path of ssh private key
* `SSH_FINGERPRINT` - fingerprint SHA256 of the host public key, default is to skip verification
* `SSH_SCRIPT_STOP` - stop script after first failure
* `SSH_DEBUG` - enable debug mode
* `SSH_USE_INSECURE_CIPHER` - include more ciphers with use_insecure_cipher (see [#56](https://github.com/appleboy/ssh-action/issues/56))
* `SSH_CIPHER` - the allowed cipher algorithms. If unspecified then a sensible

SSH Proxy Setting:

* `SSH_PROXY_HOST` - proxy host
* `SSH_PROXY_PORT` - proxy port, default is `22`
* `SSH_PROXY_USERNAME` - proxy username
* `SSH_PROXY_PASSWORD` - proxy password
* `SSH_PROXY_PASSPHRASE` - the passphrase is usually to encrypt the private key
* `SSH_PROXY_TIMEOUT` - timeout for ssh to proxy host, default is `30s`
* `SSH_PROXY_KEY` - content of ssh proxy private key.
* `SSH_PROXY_KEY_PATH` - path of ssh proxy private key
* `SSH_PROXY_FINGERPRINT` - fingerprint SHA256 of the proxy host public key, default is to skip verification
* `SSH_PROXY_USE_INSECURE_CIPHER` - include more ciphers with use_insecure_cipher (see [#56](https://github.com/appleboy/ssh-action/issues/56))
* `SSH_PROXY_CIPHER` - the allowed cipher algorithms. If unspecified then a sensible
