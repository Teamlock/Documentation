---
title: Requirements
description: Prerequisites to install Teamlock
published: true
date: 2022-05-19T13:41:11.989Z
tags: requirements
editor: markdown
dateCreated: 2022-05-10T12:40:36.855Z
---

# Server Requirements

Teamlock runs on every system where Python, MongoDB and Redis are supported.

# Domain

Teamlock needs a dedicated sub-domain / domain *(e.g `teamlock.example.com`)*

# Database

Teamlock use MongoDB as database backend.

- MongoDB **4.4 or later**
{.grid-list}


![](https://upload.wikimedia.org/wikipedia/fr/thumb/4/45/MongoDB-Logo.svg/1280px-MongoDB-Logo.svg.png =250x)

> It's recommended you use the latest version of MongoDB when possible.
{.is-success}

# Sessions

Teamlock use Redis to store user session

![](https://upload.wikimedia.org/wikipedia/fr/6/6b/Redis_Logo.svg =250x)

# Python

Python 3.10 or later is required for Teamlock to run properly

![](https://openwhisk.apache.org/images/runtimes/icon-python-text-color-horz.png =250x)

# **Web Server**

Wiki.js doesn't need any actual web server (such as nginx or Apache). 
However, you might need to put a reverse proxy in front of your Teamlock instance if you require advanced network / DNS configuration.

Also, we recommand you to configure encrypted trafic in all communication.
Including Database communication.


# **Web Application Firewall**

Teamlock will store sensible data, we recommend you to route your trafic via a Web Application Firewall. 
Some are free like ModSecurity for Apache, Naxsi for Nginx.
Or you can create an account at Cloudflare for free.

[![](https://sitecorecdn.azureedge.net/-/media/sitecoresite/images/home/products/marketplace/cloudflare/cloudflare-logo.png =250x)](https://cloudflare.com/)

[![](https://www.kindpng.com/picc/m/123-1234584_modsecuritylogo-apache-mod-security-logo-hd-png-download.png =250x)](https://www.modsecurity.org/)

[![](https://raw.githubusercontent.com/nbs-system/naxsi/master/logo.png =250x)](https://github.com/nbs-system/naxsi)

# Supported Browsers

The following browsers are supported:

- Google Chrome
- Mozilla Firefox
- Microsoft Edge
- Apple Safari


# Next
- [Installation *Instruction to install Teamlock.*](/install/installation)
{.links-list}
