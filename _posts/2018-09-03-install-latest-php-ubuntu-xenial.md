---
ID: 17
post_title: >
  Install The latest version of PHP
  (7.2.9) on Ubuntu 16.04 Xenial
author: Terry Lin
post_excerpt: ""
layout: post
permalink: >
  https://terryl.in/en/install-latest-php-ubuntu-xenial/
published: true
post_date: 2018-09-03 03:49:21
---
<h2>Introduction</h2>

In this tutorial I'll show you how to install the latest version of PHP on Ubuntu 16.04. All the steps in this tutorial has been written as a bash shell script <a href="https://github.com/Proviscript/proviscript/blob/master/components/ubuntu_16.04/php-fpm.sh">php-fpm.sh</a> and is being a component of my project called <a href="https://proviscript.sh/" title="Proviscript.sh">proviscript</a>, basiclly I made it for myself. However, you might as well use it to save time if you like.

<h3>Shortcut</h3>

Proviscript <code>php-fpm.sh</code> is hosted on a stable storage provied by GitHub pages, just two line of command in this approach. Directly install PHP-FPM 7.2.9 on your Unbuntu 16.04 server.

<pre><code class="">wget https://cdn.proviscript.sh/components/ubuntu_16.04/php-fpm.sh
./php-fpm.sh -v 7.2
</code></pre>

By default <code>php-fpm.sh</code> will install all available modules automatically.

That's it.

<h3>Install PHP 7.0</h3>

PHP 7.0 is available in the official repository of Ubuntu 16.04 and can be installed by simply using the command:

<pre><code class="">apt-get install php7
</code></pre>

List packages associated with PHP7

<pre><code class="">apt-cache pkgnames php7
</code></pre>

Result:

<pre><code class="">root@ubuntu-xenial:/home/vagrant# apt-cache pkgnames php7
php7.0-xmlrpc
php7.0-bz2
php7.0-cgi
php7.0-cli
php7.0-dba
php7.0-dev
php7.0-fpm
php7.0-gd
php7.0-gmp
php7.0-opcache
php7.0
php7.0-pspell
php7.0-recode
php7.0-common
php7.0-bcmath
php7.0-sqlite3
php7.0-tidy
php7.0-json
php7.0-mbstring
php7.0-readline
php7.0-xml
php7.0-xsl
php7.0-curl
php7.0-zip
php7.0-ldap
php7.0-pgsql
php7.0-mcrypt
php7.0-imap
php7.0-intl
php7.0-enchant
php7.0-odbc
php7.0-snmp
php7.0-soap
php7.0-sybase
php7.0-phpdbg
php7.0-mysql
php7.0-interbase
</code></pre>

You can check the modules that are available for PHP 7.0 and install them if needed.

<h2>Install PHP 7.2.9</h2>

In previous post section, you probably already know that official repository of Ubuntu 16.04 provides PHP 7.0, not the lastest version. To install the lastest stable version of PHP we can use the well-known third-party PPA (Personal Package Archives) by <a href="https://launchpad.net/~ondrej" title="  Ondřej Surý">  Ondřej Surý</a>.

You have to first install <code>software-properties-common</code>, which is a software written in Python. It provides an abstraction of the used apt repositories, allows you to easily manage your distribution and independent software vendor software sources.

In other words, <code>software-properties-common</code> provides some useful scripts for adding and removing PPAs.

<pre><code class="">sudo apt-get install software-properties-common
</code></pre>

Add repository which provides the latest PHP version 7.2.9

<pre><code class="">add-apt-repository ppa:ondrej/php
</code></pre>

Update repository.

<pre><code class="">apt-get update
</code></pre>

Install PHP 7.2.9

<pre><code class="">apt-get install -y php7.2-fpm
</code></pre>

Install PHP Pear.

<pre><code class="">apt-get install -y php-pear
</code></pre>

Install PHP 7.2 modules.

<pre><code class="">apt-get install -y php7.2-pgsql php7.2-curl php7.2-json php7.2-mbstring php7.2-gd php7.2-intl php7.2-xml php7.2-imagick php7.2-redis php7.2-zip
</code></pre>

To enable PHP FPM in boot.

<pre><code class="">systemctl enable php7.2-fpm
</code></pre>

Restart PHP FPM service.

<pre><code class="">service php7.2-fpm restart
</code></pre>

To check if PHP 7.2 is installed on your server.

<pre><code class="">php -v
</code></pre>