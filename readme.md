# Boilerplate

A stripped version of the [HTML5 Boilerplate](http://html5boilerplate.com). No license, but feel free to send me real baked cookies for the 5 minutes of work I did. It was exhausting.


## Components

* jQuery: MIT/GPL license
* Modernizr: MIT/BSD license
* Normalize.css: Public Domain

## Setup on Mac

This boilerplate assumes you're using a Mac and are willing to setup a virtual host. It's a tad bit complicated at first, but it becomes pretty easy after doing it one time.

I use [XAMPP](http://www.apachefriends.org/en/xampp.html) as my local server. Once you install XAMMP, open `/Applications/XAMPP/etc/httpd.conf`. Find the following lines in the file:

        # Virtual hosts
        #Include /Applications/XAMPP/etc/extra/httpd-vhosts.conf

Uncomment (remove the `#`) the `#Include /Applications/XAMPP/etc/extra/httpd-vhosts.conf` line.

Now open the `/Applications/XAMPP/etc/extra/httpd-vhosts.conf` file. Copy and paste this:

<pre>
#
# Virtual Hosts
#
# If you want to maintain multiple domains/hostnames on your
# machine you can setup VirtualHost containers for them. Most configurations
# use only name-based virtual hosts so the server doesn't need to worry about
# IP addresses. This is indicated by the asterisks in the directives below.
#
# Please see the documentation at 
# <URL:http://httpd.apache.org/docs/2.2/vhosts/>
# for further details before you try to setup virtual hosts.
#
# You may use the command line option '-S' to verify your virtual host
# configuration.

#
# Use name-based virtual hosting.
#
NameVirtualHost *

#
# VirtualHost example:
# Almost any Apache directive may go into a VirtualHost container.
# The first VirtualHost section is used for all requests that do not
# match a ServerName or ServerAlias in any <VirtualHost> block.
#
<VirtualHost *>
    DocumentRoot "/Applications/XAMPP/xamppfiles/htdocs"
    ServerName localhost
</VirtualHost>
</pre>

Now create a folder somewhere. For me, I keep my local sites in the `/Users/MyUserName/Sites` directory. Of course, you'll replace `MyUserName` with your username. For this, I'll create a folder named `test`. So my full directory location is `/Users/MyUserName/Sites/test`.

Once you do that open up the `/Applications/XAMPP/etc/extra/httpd-vhosts.conf` file again. Below the first `VirtualHost` section add another one using this:

<pre>
<VirtualHost *>
    DocumentRoot "/Users/MyUserName/Sites/"
    ServerName test.dev
</VirtualHost>
</pre>

Now either `mate /etc/hosts` in terminal to open it in TextMate or find it in finder and open with your text editor of choice. Add this line to the file:

        127.0.0.1 test.dev

You're all set now! Just start/restart XAMPP's Apache and put the boilerplate files in your `/Users/MyUserName/Sites/test` directory at [test.dev](http://test.dev).