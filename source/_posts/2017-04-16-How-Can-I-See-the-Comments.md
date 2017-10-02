---
title: How Can I See the Comments
date: 2017-04-16 07:38:00
categories:
- World view
- China
tags:
- GFW
- Discuss
toc: true
---

It seems that the blog comment service Disqus is blocked by GFW, so if you want to see some blogs' comments without **climbling the wall**, you may need to edit system `hosts` file.

# How can I see the comments?

## Step 1

Open `hosts` file (`notepad` is OK). The `hosts` file should be there[^1]:

| Operating System              | Version(s)                               | Location                                 |
| :---------------------------- | :--------------------------------------- | :--------------------------------------- |
| Unix, Unix-like, POSIX        |                                          | `/etc/hosts`                             |
| Microsoft Windows             | 3.1                                      | `%WinDir%\HOSTS`                         |
| Microsoft Windows             | 95, 98, ME                               | `%WinDir%\hosts`                         |
| Microsoft Windows             | NT, 2000, XP, 2003, Vista, 2008, 7, 2012, 8, 10 | `%SystemRoot%\System32\drivers\etc\hosts` |
| Windows Mobile, Windows Phone |                                          | Registry key under `HKEY_LOCAL_MACHINE\Comm\Tcpip\Hosts` |
| Apple Macintosh               | 9 and earlier                            | `Preferences` or `System` folder         |
| Apple Macintosh               | Mac OS X 10.0–10.1.5                     | (Added through NetInfo or niload)        |
| Apple Macintosh               | Mac OS X 10.2 and newer                  | `/etc/hosts` (a symbolic link to `/private/etc/hosts`) |
| Android                       |                                          | `/etc/hosts` (a symbolic link to `/system/etc/hosts`) |
| iOS                           | iOS 2.0 and newer                        | `/etc/hosts` (a symbolic link to `/private/etc/hosts`) |

## Step 2

Edit the hosts file (some require `root`) and add the following lines below:

```
# Disqus Start
151.101.100.134 disqus.com
151.101.100.134 www.disqus.com
151.101.100.134 content.disqus.com
151.101.100.134 referrer.disqus.com
151.101.100.134 docs.disqus.com
151.101.100.134 dropbox.disqus.com
151.101.100.134 apkpure.disqus.com
151.101.100.64 glitter.services.disqus.com
151.101.100.64 links.services.disqus.com
173.192.82.196 realtime.services.disqus.com
50.18.249.249 help.disqus.com
23.65.183.218 about.disqus.com
23.65.183.218 blog.disqus.com
23.65.183.218 publishers.disqus.com
# Disqus End
```

## Step 3

Then you maybe can see my comments (?!!)

If not, press `Windows + R` and run `ipconfig /flushdns`. (for Windows)

[^1]: Source [Wikipedia](https://en.wikipedia.org/wiki/Hosts_(file)).