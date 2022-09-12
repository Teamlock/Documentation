---
title: S3 Recovery Configuration
description: 
published: true
date: 2022-09-12T12:47:42.111Z
tags: 
editor: markdown
dateCreated: 2022-09-12T09:42:48.003Z
---

S3 is an object storage developped by Amazon.
In this tutorial, we will be using the **Object Storage on OVHCloud**.

First, you'll need to create a **Public Cloud Project** on your OVH Account.
After the project is created go to the **Object Storage** section:

![capture_d’écran_2022-09-12_à_11.30.38.png](/captures/capture_d’écran_2022-09-12_à_11.30.38.png =400x)

Then create a new **Object Container**:
![capture_d’écran_2022-09-12_à_11.32.26.png](/captures/capture_d’écran_2022-09-12_à_11.32.26.png =1000x)

Select **High Performance**

Then choose any **Region**:

![capture_d’écran_2022-09-12_à_11.33.22.png](/captures/capture_d’écran_2022-09-12_à_11.33.22.png =1000x)

Define a name for your container and click on **Create the container**

![capture_d’écran_2022-09-12_à_11.34.26.png](/captures/capture_d’écran_2022-09-12_à_11.34.26.png =1000x)

![capture_d’écran_2022-09-12_à_11.39.50.png](/captures/capture_d’écran_2022-09-12_à_11.39.50.png =1000x)

Click on the button on the right of the line, then select **Add a user to a container**

If you have no users available, follow the OVH Documentation to create one:

[OVH Documentation](https://docs.ovh.com/fr/storage/s3/debuter-avec-s3/)


Then, in the Teamlock form, you can define the following data:

- S3 Endpoint URL
- S3 Access Key
- S3 Secret Key
- S3 Region Name (lowercase)
- S3 Bucket name (Name of the Object Storage)