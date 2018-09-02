---
ID: 17
post_title: >
  Install The latest version of PHP 7.2.9
  on Ubuntu 16.04 (Xenial)
author: Terry Lin
post_excerpt: ""
layout: post
permalink: >
  https://terryl.in/en/install-php-ubuntu-xenial/
published: true
post_date: 2018-09-03 03:49:21
---
<h2>Introduction</h2>

In this tutorial I'll show you how to install the latest version of PHP on Ubuntu 16.04. All the steps in this tutorial has been written as a bash shell script <a href="https://github.com/Proviscript/proviscript/blob/master/components/ubuntu_16.04/php-fpm.sh">php-fpm.sh</a> and is being a component of my project called <a href="https://proviscript.sh/" title="Proviscript.sh">Proviscript.sh</a>, basiclly I made it for myself, however, you can use it to save your time if you like.

<h3>Install via Proviscript</h3>

Proviscript php-fpm.sh is hosted on a stable storage provied by GitHub pages, just two line of command in this approach. Directly install PHP-FPM 7.2.9 on your Unbunto 16.04 server.

<pre><code class="">wget https://cdn.proviscript.sh/components/ubuntu_16.04/php-fpm.sh
./php-fpm.sh -v 7.2
</code></pre>

<h3>Install step by step</h3>

<pre><code class="">sudo apt-get install software-properties-common
</code></pre>

Not done yet. I go sleep... zzzz