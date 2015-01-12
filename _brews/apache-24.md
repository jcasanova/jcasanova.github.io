---
weight: 3
title: Installation de Apache 2.4
version: 2.4
---

**Installation du serveur Apache 2.4**

{% highlight text %}
julien$ brew install httpd24 --with-privileged-ports
{% endhighlight %}

{% highlight text %}
==> Installing httpd24 from homebrew/homebrew-apache
==> Installing dependencies for httpd24: apr, apr-util, pcre
==> Installing httpd24 dependency: apr
==> Downloading https://bitbucket.org/alanthing/homebrew-apache/downloads/apr-1.5.1.yosemite.bottle.tar.gz
######################################################################## 100,0%
==> Pouring apr-1.5.1.yosemite.bottle.tar.gz
==> Caveats
This formula is keg-only, which means it was not symlinked into /usr/local.

Mac OS X already provides this software and installing another version in
parallel can cause all kinds of trouble.

Generally there are no consequences of this for you. If you build your
own software and it requires this formula, you'll need to add to your
build variables:

    LDFLAGS:  -L/usr/local/opt/apr/lib
    CPPFLAGS: -I/usr/local/opt/apr/include

==> Summary
🍺  /usr/local/Cellar/apr/1.5.1: 53 files, 1,3M
==> Installing httpd24 dependency: apr-util
==> Downloading https://bitbucket.org/alanthing/homebrew-apache/downloads/apr-util-1.5.4.yosemite.bottle.tar.gz
######################################################################## 100,0%
==> Pouring apr-util-1.5.4.yosemite.bottle.tar.gz
==> Caveats
This formula is keg-only, which means it was not symlinked into /usr/local.

Mac OS X already provides this software and installing another version in
parallel can cause all kinds of trouble.

Generally there are no consequences of this for you. If you build your
own software and it requires this formula, you'll need to add to your
build variables:

    LDFLAGS:  -L/usr/local/opt/apr-util/lib
    CPPFLAGS: -I/usr/local/opt/apr-util/include

==> Summary
🍺  /usr/local/Cellar/apr-util/1.5.4: 45 files, 808K
==> Installing httpd24 dependency: pcre
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/pcre-8.36.yosemite.bottle.tar.gz
######################################################################## 100,0%
==> Pouring pcre-8.36.yosemite.bottle.tar.gz
🍺  /usr/local/Cellar/pcre/8.36: 146 files, 5,9M
==> Installing httpd24
==> Downloading https://archive.apache.org/dist/httpd/httpd-2.4.10.tar.bz2
######################################################################## 100,0%
==> Patching
==> ./configure --enable-layout=Homebrew --enable-mods-shared=all --enable-unique-id --enable-ssl --enable-dav --en
==> make
==> make install
==> Caveats
To load httpd24 when --with-privileged-ports is used:
    sudo cp -v /usr/local/Cellar/httpd24/2.4.10/homebrew.mxcl.httpd24.plist /Library/LaunchDaemons
    sudo chown -v root:wheel /Library/LaunchDaemons/homebrew.mxcl.httpd24.plist
    sudo chmod -v 644 /Library/LaunchDaemons/homebrew.mxcl.httpd24.plist
    sudo launchctl load /Library/LaunchDaemons/homebrew.mxcl.httpd24.plist

To reload httpd24 after an upgrade when --with-privileged-ports is used:
    sudo launchctl unload /Library/LaunchDaemons/homebrew.mxcl.httpd24.plist
    sudo launchctl load /Library/LaunchDaemons/homebrew.mxcl.httpd24.plist

If not using --with-privileged-ports, use the instructions below.

To have launchd start httpd24 at login:
    ln -sfv /usr/local/opt/httpd24/*.plist ~/Library/LaunchAgents
Then to load httpd24 now:
    launchctl load ~/Library/LaunchAgents/homebrew.mxcl.httpd24.plist
==> Summary
🍺  /usr/local/Cellar/httpd24/2.4.10: 211 files, 4,5M, built in 62 seconds
{% endhighlight %}