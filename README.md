# docker.debian-slim_radicale
Docker image for Radicale (CalDAV & CardDAV) server based on Debian Slim base. Source code at [Github](https://github.com/Mingala/docker.debian-slim_radicale).
* Components installed :
  * [LDAP client](https://wiki.debian.org/LDAP) for user authentication via NSS and PAM using [libnss-ldapd and libpam-ldapd libraries](https://arthurdejong.org/nss-pam-ldapd/).
  * [Radicale 3.0](https://radicale.org/3.0.html) (install from PyPi repository via Pip).
  * [Apache2](https://www.cyrusimap.org/sasl/) as a secured reverse proxy for Radicale Sasl authentification, only ldap component installed, modify Dockerfile for more
* Bind mounts on Docker :
  * /etc/prosody/certs/ folder to your certificates
  * /etc/prosody/prosody.cfg.lua to your Prosody config setup
  * /var/lib/prosody/ to make your Prosody data persistent (or other folder according to specific data-path in config file)
  * /var/lib/prosody-modules/ folder to install Prosody modules (need entry in Prosody config)
  * /var/log/prosody/ folder to make your Prosody log persistent
  * /etc/saslauthd.conf for your Sasl authentification config
* default Ports used on Docker (customizable in Prosody config) :
  * 5222 and 5269 for Prosody C2S and S2S exchange
  * 5000 if using Prosody Jingle Proxy ([mod-proxy65](https://prosody.im/doc/modules/mod_proxy65))
