---
title: AWS Cloud Costs Every Programmer Should Know
date: '2019-07-04T09:47:55-05:00'
tags:
  - '#aws  #devops'
---
I was recently reading an article that preported to discuss the costs that that every programmer using Amazon Web Services (AWS) should know. Imagine my suprise when they started talking about how much a CPU core or gigabyte of memory costs. I would actually argue that this is the wrong manner to approach thinking about costs in the cloud. One of the largest benifts of moving the cloud is that you get a large number of services along with your virtual machines. Given the choice between trying to setup an object store and using s3, you would be crazy to not use s3. Running a large object storage system that scales gracefully is incredible challenging and AWS is already running one and letting it's customers use it for just pennies a day.

Knowing gut heuristics for AWS costs by the service is incredible helpful. One of the first ways that I was taught the benefit of knowing heuristics was actually by old story about Grace Hopper. Grace Hopper was struggling to understand the what a nanosecond was and how long that really was so she acquired a length of wire that was 11.6 inches long. The reason that
