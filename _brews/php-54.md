---
weight: 1
title: Installation de PHP 5.4
---

# Installation de PHP 5.4

{% highlight text linenos %}
MacBook-Pro-de-Julien:~ julien$ brew install php54
==> Installing php54 from homebrew/homebrew-php
==> Installing dependencies for php54: libpng, freetype, gettext, icu4c, jpeg, unixodbc, homebrew/dupes/zlib
==> Installing php54 dependency: libpng
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/libpng-1.6.16.yosemite.bottle.tar.gz
######################################################################## 100,0%
==> Pouring libpng-1.6.16.yosemite.bottle.tar.gz
🍺  /usr/local/Cellar/libpng/1.6.16: 17 files, 1,3M
==> Installing php54 dependency: freetype
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/freetype-2.5.5.yosemite.bottle.tar.gz
######################################################################## 100,0%
==> Pouring freetype-2.5.5.yosemite.bottle.tar.gz
🍺  /usr/local/Cellar/freetype/2.5.5: 60 files, 2,6M
==> Installing php54 dependency: gettext
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/gettext-0.19.4.yosemite.bottle.tar.gz
######################################################################## 100,0%
==> Pouring gettext-0.19.4.yosemite.bottle.tar.gz
==> Caveats
This formula is keg-only, which means it was not symlinked into /usr/local.

Mac OS X provides similar software, and installing this software in
parallel can cause all kinds of trouble.

OS X provides the BSD gettext library and some software gets confused if both are in the library path.

Generally there are no consequences of this for you. If you build your
own software and it requires this formula, you'll need to add to your
build variables:

    LDFLAGS:  -L/usr/local/opt/gettext/lib
    CPPFLAGS: -I/usr/local/opt/gettext/include

==> Summary
🍺  /usr/local/Cellar/gettext/0.19.4: 1920 files, 21M
==> Installing php54 dependency: icu4c
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/icu4c-54.1.yosemite.bottle.1.tar.gz
######################################################################## 100,0%
==> Pouring icu4c-54.1.yosemite.bottle.1.tar.gz
==> Caveats
This formula is keg-only, which means it was not symlinked into /usr/local.

Mac OS X already provides this software and installing another version in
parallel can cause all kinds of trouble.

OS X provides libicucore.dylib (but nothing else).

Generally there are no consequences of this for you. If you build your
own software and it requires this formula, you'll need to add to your
build variables:

    LDFLAGS:  -L/usr/local/opt/icu4c/lib
    CPPFLAGS: -I/usr/local/opt/icu4c/include

==> Summary
🍺  /usr/local/Cellar/icu4c/54.1: 242 files, 65M
==> Installing php54 dependency: jpeg
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/jpeg-8d.yosemite.bottle.2.tar.gz
######################################################################## 100,0%
==> Pouring jpeg-8d.yosemite.bottle.2.tar.gz
🍺  /usr/local/Cellar/jpeg/8d: 18 files, 776K
==> Installing php54 dependency: unixodbc
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/unixodbc-2.3.2_1.yosemite.bottle.1.tar.gz
######################################################################## 100,0%
==> Pouring unixodbc-2.3.2_1.yosemite.bottle.1.tar.gz
🍺  /usr/local/Cellar/unixodbc/2.3.2_1: 31 files, 1,0M
==> Installing php54 dependency: homebrew/dupes/zlib
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/dupes/zlib-1.2.8.yosemite.bottle.tar.gz
######################################################################## 100,0%
==> Pouring zlib-1.2.8.yosemite.bottle.tar.gz
==> Caveats
This formula is keg-only, which means it was not symlinked into /usr/local.

Mac OS X already provides this software and installing another version in
parallel can cause all kinds of trouble.

Generally there are no consequences of this for you. If you build your
own software and it requires this formula, you'll need to add to your
build variables:

    LDFLAGS:  -L/usr/local/opt/zlib/lib
    CPPFLAGS: -I/usr/local/opt/zlib/include

==> Summary
🍺  /usr/local/Cellar/zlib/1.2.8: 9 files, 392K
==> Installing php54 dependency: libtool
==> Downloading https://downloads.sf.net/project/machomebrew/Bottles/libtool-2.4.4.yosemite.bottle.tar.gz
######################################################################## 100,0%
==> Pouring libtool-2.4.4.yosemite.bottle.tar.gz
==> Caveats
In order to prevent conflicts with Apple's own libtool we have prepended a "g"
so, you have instead: glibtool and glibtoolize.
==> Summary
🍺  /usr/local/Cellar/libtool/2.4.4: 69 files, 3,8M
==> Installing php54
==> Downloading https://www.php.net/get/php-5.4.36.tar.bz2/from/this/mirror
######################################################################## 100,0%
==> Patching
==> ./configure --prefix=/usr/local/Cellar/php54/5.4.36 --localstatedir=/usr/local/var --sysconfdir=/usr/local/etc/
==> make
==> make install
==> /usr/local/Cellar/php54/5.4.36/bin/pear config-set php_ini /usr/local/etc/php/5.4/php.ini
==> Caveats
To enable PHP in Apache add the following to httpd.conf and restart Apache:
    LoadModule php5_module    /usr/local/opt/php54/libexec/apache2/libphp5.so

The php.ini file can be found in:
    /usr/local/etc/php/5.4/php.ini

✩✩✩✩ PEAR ✩✩✩✩

If PEAR complains about permissions, 'fix' the default PEAR permissions and config:
    chmod -R ug+w /usr/local/Cellar/php54/5.4.36/lib/php
    pear config-set php_ini /usr/local/etc/php/5.4/php.ini

✩✩✩✩ Extensions ✩✩✩✩

If you are having issues with custom extension compiling, ensure that
you are using the brew version, by placing /usr/local/bin before /usr/sbin in your PATH:

      PATH="/usr/local/bin:$PATH"

PHP54 Extensions will always be compiled against this PHP. Please install them
using --without-homebrew-php to enable compiling against system PHP.

✩✩✩✩ PHP CLI ✩✩✩✩

If you wish to swap the PHP you use on the command line, you should add the following to ~/.bashrc,
~/.zshrc, ~/.profile or your shell's equivalent configuration file:

      export PATH="$(brew --prefix homebrew/php/php54)/bin:$PATH"

To have launchd start php54 at login:
    ln -sfv /usr/local/opt/php54/*.plist ~/Library/LaunchAgents
Then to load php54 now:
    launchctl load ~/Library/LaunchAgents/homebrew.mxcl.php54.plist
==> Summary
🍺  /usr/local/Cellar/php54/5.4.36: 489 files, 38M, built in 4.5 minutes
{% endhighlight %}
