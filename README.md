# docker.debian-slim_radicale
Docker image for Radicale (CalDAV & CardDAV) server based on Debian Slim base. Source code at [Github](https://github.com/Mingala/docker.debian-slim_radicale).
* Components installed :
  * [LDAP client](https://wiki.debian.org/LDAP) for user authentication via NSS and PAM using [libnss-ldapd and libpam-ldapd libraries](https://arthurdejong.org/nss-pam-ldapd/).
  * [Radicale 3.0](https://radicale.org/3.0.html) (install from PyPi repository via Pip).
  * [Apache2](https://www.cyrusimap.org/sasl/) as a secured reverse proxy for Radicale Sasl authentification, only ldap component installed, modify Dockerfile for more
* Bind mounts on Docker :
  * /etc/radicale/ folder to your Radicale config setup
  * /etc/apache2/sites-available/radicale_ldap.conf file to your Apache Radicale proxy setup
  * /var/lib/radicale/collections/collection-root/ folder to make your Radicale data persistent containing the calendars files and contact files
  * /var/log/radicale/ folder to make your Radicale log persistent
  * /var/log/apache2/ folder to make your Apache log persistent
  * /etc/ssl/certs/cert_int.crt file to your ssl intermediate certificate (customizable in apache radicale_ldap.conf)
  * /etc/ssl/certs/cert.crt file to your ssl certificate (customizable in apache radicale_ldap.conf)
  * /etc/ssl/private/cert.key file to your ssl certificate key (customizable in apache radicale_ldap.conf)
  * /etc/prosody/prosody.cfg.lua to your Prosody config setup
  * /usr/local/bin/start.sh file to start apache proxy and radicale service
* Default Ports used on Docker :
  * 9008 (tcp) (customizable in apache radicale_ldap.conf)
