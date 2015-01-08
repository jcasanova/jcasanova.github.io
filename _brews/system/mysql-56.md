---
weight: 2
title: Installation de MySQL
version: 5.6
---

## Installation de MySQL

{% highlight text %}
MacBook-Pro-de-Julien:~ julien$ brew install mysql
==> Installing mysql dependency: openssl
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/openssl-1.0.1j_1.yosemite.bottle.tar.gz
######################################################################## 100,0%
==> Pouring openssl-1.0.1j_1.yosemite.bottle.tar.gz
==> Caveats
A CA file has been bootstrapped using certificates from the system
keychain. To add additional certificates, place .pem files in
  /usr/local/etc/openssl/certs

and run
  /usr/local/opt/openssl/bin/c_rehash

This formula is keg-only, which means it was not symlinked into /usr/local.

Mac OS X already provides this software and installing another version in
parallel can cause all kinds of trouble.

Apple has deprecated use of OpenSSL in favor of its own TLS and crypto libraries

Generally there are no consequences of this for you. If you build your
own software and it requires this formula, you'll need to add to your
build variables:

    LDFLAGS:  -L/usr/local/opt/openssl/lib
    CPPFLAGS: -I/usr/local/opt/openssl/include

==> Summary
🍺  /usr/local/Cellar/openssl/1.0.1j_1: 431 files, 15M
==> Installing mysql
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/mysql-5.6.22.yosemite.bottle.tar.gz
######################################################################## 100,0%
==> Pouring mysql-5.6.22.yosemite.bottle.tar.gz
==> Caveats
A "/etc/my.cnf" from another install may interfere with a Homebrew-built
server starting up correctly.

To connect:
    mysql -uroot

To have launchd start mysql at login:
    ln -sfv /usr/local/opt/mysql/*.plist ~/Library/LaunchAgents
Then to load mysql now:
    launchctl load ~/Library/LaunchAgents/homebrew.mxcl.mysql.plist
Or, if you don't want/need launchctl, you can just run:
    mysql.server start
==> /usr/local/Cellar/mysql/5.6.22/bin/mysql_install_db --verbose --user=julien --basedir=/usr/local/Cellar/mysql/5
==> Summary
🍺  /usr/local/Cellar/mysql/5.6.22: 9666 files, 339M
{% endhighlight %}

## Chargement du lanceur

{% highlight text %}
ln -sfv /usr/local/opt/mysql/*.plist ~/Library/LaunchAgents
launchctl load ~/Library/LaunchAgents/homebrew.mxcl.mysql.plist
{% endhighlight %}
