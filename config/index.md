---
title: Teamlock Configuration
description: Guide to configure Teamlock
published: true
date: 2022-05-19T13:41:02.396Z
tags: 
editor: markdown
dateCreated: 2022-05-11T12:34:08.525Z
---

Now that your Teamlock instance is up and ready you can finish the installation with your Browser.

Go to: **http://\<ip\>:8000/#/install**

![capture_d’écran_2022-05-11_à_14.32.24.png](/captures/capture_d’écran_2022-05-11_à_14.32.24.png =500x)

- **Size of User's RSA Keys** : RSA Size for User's Private and Public Keys
- **Enforce MFA** : Force users to enable Multi Factor Authentication
- **Allow self registration** : Allow users to self register on Teamlock
- **Allowed email addresses** : This input will be visible only if self registration is enabled. This input will allow you to authorize only users with your enterprise email address
{.grid-list}

![capture_d’écran_2022-05-11_à_14.34.20.png](/captures/capture_d’écran_2022-05-11_à_14.34.20.png =500x)

- **User's password duration** : Delay between user's password change
- **Password minimum length** : User's password minimum length
- **Minimum uppercase letter(s)** : Define minimum uppercase letter
- **Minimum number(s)** : Define minimum number
- **Minimum special character(s)** : Define minimum special characters
{.grid-list}

![capture_d’écran_2022-05-11_à_14.36.25.png](/captures/capture_d’écran_2022-05-11_à_14.36.25.png =500x)

- **Email** : Administrateur email address. We recommand you to set a service account in this step.
{.grid-list}

Once finished, you will receive an email to configure the administrator account

You can show the logs of Teamlock to check if everything is ok:

```bash
docker logs teamlock_teamlock_1
```

- [User configuration *Instruction to configure User account.*](/usage/user/configuration)
{.links-list}