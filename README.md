# Termux-services
<!DOCTYPE html>
<html class="client-nojs" lang="en" dir="ltr">
<head>
<meta charset="UTF-8"/>
				<div id="mw-content-text" class="mw-body-content mw-content-ltr" lang="en" dir="ltr"><div class="mw-parser-output"><p><a rel="nofollow" class="external text" href="https://github.com/termux/termux-services">termux-services</a> contains a set of scripts for controlling services.
Instead of putting commands in ~/.bashrc or ~/.bash_profile, they can be started and stopped with termux-services.
</p>
<table class="wikitable">
<caption>Supported services
</caption>
<tbody><tr>
<th>Package</th>
<th>Daemon</th>
<th>Port</th>
<th>Description
</th></tr>
<tr>
<td>apache2</td>
<td>httpd</td>
<td>8080</td>
<td>Apache Web Server <a rel="nofollow" class="external text" href="https://en.wikipedia.org/wiki/Web_server">HTTP Web Server</a>
</td></tr>
<tr>
<td>at</td>
<td>atd</td>
<td></td>
<td>AT and batch delayed command scheduling utility and daemon <a rel="nofollow" class="external text" href="https://en.wikipedia.org/wiki/At_(command)">at</a>
</td></tr>
<tr>
<td>bitcoin</td>
<td>bitcoind</td>
<td></td>
<td>Bitcoin Core
</td></tr>
<tr>
<td>busybox</td>
<td>telnetd</td>
<td>8023</td>
<td>Remote terminal service <a rel="nofollow" class="external text" href="https://en.wikipedia.org/wiki/Telnet">Telnet</a>
</td></tr>
<tr>
<td>busybox</td>
<td>ftpd</td>
<td>8021</td>
<td>FTP (File Transfer Protocol) <a rel="nofollow" class="external text" href="https://en.wikipedia.org/wiki/File_Transfer_Protocol">FTP</a>
</td></tr>
<tr>
<td>cronie</td>
<td>crond</td>
<td></td>
<td>Daemon that runs specified programs at scheduled times <a rel="nofollow" class="external text" href="https://en.wikipedia.org/wiki/Cron">cron</a>
</td></tr>
<tr>
<td>emacs</td>
<td>emacsd</td>
<td></td>
<td>Extensible, customizable text editor-and more <a rel="nofollow" class="external text" href="https://www.emacswiki.org/emacs/EmacsAsDaemon">EMACS</a>
</td></tr>
<tr>
<td>ipfs</td>
<td>ipfs</td>
<td></td>
<td>A peer-to-peer hypermedia distribution protocol <a rel="nofollow" class="external text" href="https://en.wikipedia.org/wiki/InterPlanetary_File_System">IPFS</a>
</td></tr>
<tr>
<td>libmosquitto</td>
<td>mosquitto</td>
<td>1883</td>
<td>MQTT is a lightweight, publish-subscribe network protocol <a rel="nofollow" class="external text" href="https://en.wikipedia.org/wiki/MQTT">MQTT</a>
</td></tr>
<tr>
<td>lighttpd</td>
<td>lighttpd</td>
<td>8080</td>
<td>Lighttpd Small webserver HTTP Web Server
</td></tr>

<tr>
<td>lnd</td>
<td>lnd</td>
<td></td>
<td>Lightning Network Daemon
</td></tr>
<tr>
<td>mariadb</td>
<td>mysqld</td>
<td>3306</td>
<td><a rel="nofollow" class="external text" href="https://en.wikipedia.org/wiki/MariaDB">MariaDB</a> Community-developed fork of the MySQL from its original authors
</td></tr>
<tr>
<td>mpd</td>
<td>mpd</td>
<td></td>
<td><a rel="nofollow" class="external text" href="https://en.wikipedia.org/wiki/Music_Player_Daemon">Music Player Daemon (MPD)</a>
</td></tr>
<tr>
<td>mpdscribble</td>
<td>mpdscribble</td>
<td></td>
<td>MPD client which submits tracks being played
</td></tr>
<tr>
<td>nginx</td>
<td>nginx</td>
<td>8080</td>
<td>NGINX Web server HTTP Web Server
</td></tr>
<tr>
<td>openssh</td>
<td>sshd</td>
<td>8022</td>
<td>OpenSSH <a rel="nofollow" class="external text" href="https://en.wikipedia.org/wiki/Secure_Shell_Protocol">SSH</a>
</td></tr>
<tr>
<td>postgresql</td>
<td>postgres</td>
<td>5432</td>
<td>PostgreSQL database <a rel="nofollow" class="external text" href="https://en.wikipedia.org/wiki/PostgreSQL">PostgreSQL</a>
</td></tr>
<tr>
<td>privoxy</td>
<td>privoxy</td>
<td></td>
<td>Privoxy is non-caching web proxy with advanced filtering capabilities <a rel="nofollow" class="external text" href="https://en.wikipedia.org/wiki/Proxy_server">HTTP Proxy</a>
</td></tr>
<tr>
<td>tor</td>
<td>tor</td>
<td></td>
<td>The Onion Router anonymizing overlay network <a rel="nofollow" class="external text" href="https://en.wikipedia.org/wiki/Tor_(network)">Tor</a>
</td></tr>
<tr>
<td>transmission</td>
<td>transmission</td>
<td></td>
<td>BitTorrent client <a rel="nofollow" class="external text" href="https://en.wikipedia.org/wiki/BitTorrent">BitTorrent</a>
</td></tr></tbody></table>
<p><br />
To install termux-services, run
</p>
<pre>pkg install termux-services
</pre>
<p>and then restart termux so that the service-daemon is started.
</p><p>To then enable and run a service, run
</p>
<pre>sv-enable &lt;service&gt;
</pre>
<p>If you only want to run it once, run
</p>
<pre>sv up &lt;service&gt;
</pre>
<p>To later stop a service, run:
</p>
<pre>sv down &lt;service&gt;
</pre>
<p>Or to disable it
</p>
<pre>sv-disable &lt;service&gt;
</pre>
<p>A service is disabled if `$PREFIX/var/service/&lt;service&gt;/down` exists, so the `sv-enable` and `sv-disable` scripts touches, or removes, this file.
</p><p>termux-services uses the programs from <a rel="nofollow" class="external text" href="http://smarden.org/runit/">runit</a> to control the services. A bunch of example scripts are available from the <a rel="nofollow" class="external text" href="http://smarden.org/runit/runscripts.html">same site</a>.
If you find a script you want to use, or if you write your own, you can use set it up by running:
</p>
<pre>mkdir -p $PREFIX/var/service/&lt;PKG&gt;/log
ln -sf $PREFIX/share/termux-services/svlogger $PREFIX/var/service/&lt;PKG&gt;/log/run
</pre>
<p>and then put your run script for the package at $PREFIX/var/service/&lt;PKG&gt;/run and make sure that it is runnable.
</p><p>You can then run
</p>
<pre>sv up &lt;PKG&gt;
</pre>
<p>to start it.
</p><p>Log files for services are situated in $PREFIX/var/log/sv/&lt;PKG&gt;/ with the active log file named "current".
</p>
<h3><span class="mw-headline" id="Starting_termux-services_on_boot">Starting termux-services on boot</span></h3>
<p>If you want your services to start on device boot, see the example in <a href="/wiki/Termux:Boot" title="Termux:Boot">Termux:Boot</a>
</p>
				</div>
</html>
