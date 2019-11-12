---
title: Presigner - Moving files using presigned s3 urls.
date: '2019-11-12T08:55:03-06:00'
categories:
  - tools
tags:
  - tools presigner
---
Server administrators frequently have a hard problem with regards to moving files. As much as people like to discuss the future of DevOps and how all servers will be provisioned from code, some people still have servers that are pets. It can frequently be difficult to transfer files from one system to another when those systems are on different networks or different data centers. Presigner aims to solve this problem by using presigned links for downloading and uploading files with curl. 

```> presigner s3://bucket_here/file_here.tar
https://bucket_here.s3.amazonaws.com/file_here.tar?X-Amz-Signature=18424ca80001a1b88cfe402cbe2395c47cf24a36ca121d11f53d04d4186e1369&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIRPW5JGRSXEQSOQQ/20191112/us-east-1/s3/aws4_request&X-Amz-Date=20191112T150506Z&X-Amz-Expires=21600&X-Amz-SignedHeaders=host```

These urls include all the authentication needed to GET/PUT files from AWS S3 so that they can safely be made on one system and then transferred via ssh or shortlinks to a remote system. As long as the systems can access S3 over the network, this works for file transfers. 

Quick tip, we have a bucket called `***-dropbox` which is set to expire everything in seven days. We use this for a lot of one off transfers.

