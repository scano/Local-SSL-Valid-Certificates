# Local-SSL-Valid-Certificates
Generate local SSL valid certificates to develop on Docker or other platforms

## Install mkcert

Install Brew if you have it

`$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

Install mkcert:

`$ brew install mkcert`

Install NSS for FireFox

`$ brew install nss`

Run mkcert to install in system. The systems request the user password.

`$ mkcert -install`

## Generating SSL

All the paths and data is for example. Personalize with your requeriments.

Navigate to the folder that you want to save the certificates.

`$ cd /Volumes/Data/Works-Web/_docker/nginx/ssl`

Generate certificate. You can issue a wildcart or individual certificate.

`$ mkcert "*.mydomain.devs"`

Set the certificate to the apropiate server. In our case Nginx config file server

```
ssl_certificate /etc/nginx/ssl/_wildcard.domain.devs.pem;
ssl_certificate_key /etc/nginx/ssl/_wildcard.domain.devs-key.pem;
```

Restart the Nginx

⚠️ IMPORTANT ⚠️

These certs are valid for the current machine.
If you replatform or change the machine you need reissue the certs


Enjoy!

.s.
