---
title : "Prepare"
weight : 1 
chapter : false
pre : " <b> 1. </b> "
---
We will begin by setting up the necessary resources for this workshop. We will create S3 buckets for file storage and appropriate IAM roles for the services we will use. These resources have been defined in a CloudFormation template.



- Go to [CloudFormation in the AWS Console](https://ap-southeast-1.console.aws.amazon.com/cloudformation/home?region=ap-southeast-1#/stacks?filteringText=&filteringStatus=active&viewNested=true).
- In the navigation menu on the right, click **Create stack** and select **With new resources (standard)**.
- Download this file: [CFN Template](https://drive.google.com/uc?export=download&id=1SRDkQrSHtpAknpcRDSyAc2TIMxHqU63h).
- Select **Upload a template file**, and upload the file you just downloaded.
- Click **Next**. 
- Name the stack `sdlj-workshop`
- Click **Next** until you reach the Review page.
- Check the box **I Acknowledge that AWS CloudFormation might create IAM resources with custom names**.
- Click **Submit**.
- Wait for the resources to be provisioned.
![](../images/1.prepare/001-prepare.png)
![](../images/1.prepare/002-prepare.png)