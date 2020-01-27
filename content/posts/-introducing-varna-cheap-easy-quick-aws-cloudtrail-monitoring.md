---
title: '# Introducing Varna: Cheap, Easy & Quick AWS CloudTrail Monitoring'
date: '2020-01-26T18:33:39-06:00'
tags:
  - Varna Tools
---
Varna is a tool that is meant to monitor AWS CloudTrail logs with support for custom rules while remaining easy to deploy and cheap to run. Varna uses Event Query Language (EQL) as its query language of choice for writing rules in. EQL has some nice advantages over existing languages in the support for sequences of events which can be invaluable for security rules which may have preconditions. In addition, EQL has a rich library of functions that make it well suited for complex rules. 

Varna is an AWS Lambda and a DynamoDB table that are meant to be quick to deploy and minimally invasive. The code is actually small enough that it can be reviewed by hand in a couple of hours. Varna uses [Zappa](https://github.com/Miserlou/Zappa) to handle the bundling and deployment of Varna. This means that Varna can be deployed in under 5 minutes with very little changes to an existing AWS account.  

Varna uses the CloudTrail logs that are written to an S3 bucket as the primary source of events. This means the only state that Varna maintains is a DynamoDB table of alerts that have been raised from triggering the rules. This means that Varna is cheap to run because it has minimal fixed costs. 

Varna has several features that make it attractive for usage as an AWS account security tool. Varna uses signals from the S3 bucket where CloudTrail log files are being dropped to process log files as quickly as possible. This allows Varna to quickly process rules over new events as they happen and then deliver notifications to the administrator. Varna sends alerts via two methods, email or slack. In addition, Varna will deliver a periodic alert at a user defined interval to remind them about alerts they may have missed. 

Varna also includes past search. This can frequently be used to shed light on what was happening around an event. Both the web interface and the command line script allow the administrator to run EQL queries over previous time windows. In the latest release, Varna can also be protected to only allow access by specific users via authentication. 

Varna comes with a small suite of preexisting EQL analytics. These are meant to be tuned to an individual account and may not be suitable for any individual account. All of these are meant to be high signal alerts that indicate potentially dangerous actions that can be undertaken in an AWS account. Combined with the built in notification methods, this can be a quick means of detecting suspicious behavior for a cheap monthly cost while maintain rich customization. 
