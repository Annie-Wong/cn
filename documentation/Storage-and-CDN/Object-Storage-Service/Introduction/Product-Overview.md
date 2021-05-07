# OSS概述

## OSS简介

京东智联云对象存储（Object Storage Service，简称OSS）是利用京东在分布式存储领域多年的深厚技术积累，为用户提供安全、稳定、海量、便捷的对象存储服务。
京东智联云对象存储提供包括文件上传、存储、下载、分发、在线处理在内的全系列产品，从几字节到数TB的数据，都能够为您提供完整的存储方案。

同时，京东智联云对象存储还为您提供简单方便的Restful接口与方便易用的SDK，帮助您在任何应用、任何时间、任何地点都能管理和访问京东智联云对象存储上的数据。

目前京东智联云对象存储在京东内部已经承载了商城，金融、移动、物流、拍拍、京东智联云等近200个部门的关键数据，为京东业务高速增长提供了坚实的保障。

## OSS存储级别

标准型存储（STANDARD）：标准存储为用户提供了高可靠性、高可用性和高性能的对象存储服务。标准存储拥有低访问时延和较高的吞吐量，因而适用于吞吐量大，热点文件、需要频繁访问的业务场景，如：移动应用、 大型网站、 图片分享、热点音视频等。

低频存储（STANDARD-IA）：低频存储类型适合长期保存不经常访问的数据（平均每月访问频率1到2次）。存储单价低于标准类型，适合各类移动应用、智能设备、企业数据的长期备份，支持实时数据访问。存储时间短于30天的Object提前被删除会产生一定费用。

归档存储（GLACIER）：归档存储类型在存储类型中单价最低，适合需要长期保存（建议半年以上）的归档数据，在数据的存储周期内极少被访问；数据取回时，需要根据您选择的取回模式，等待几分钟到几小时。归档存储类型适合需要长期保存的档案数据、操作日志、影视素材等。存储时间短于60天的Object提前删除会产生一定费用。

低冗余型存储（REDUCED_REDUNDANCY）：低冗余型存储为用户提供了较低存储成本和较低访问时延的对象存储服务。与标准型存储相比，低冗余型存储大幅降低存储的价格，适用于读取频率较低、数据需在对象存储上做较长时间冷备的业务场景，最低存储时间为30天。

## 快速导航

[计费规则](../Pricing/Billing-Rules.md) 

[存储基本操作](../Operation-Guide/Sign-Up-Service-2.md)

[图片处理](../Operation-Guide/Image-Service-Guide/Introduction-1.md)

[兼容S3 API](../API-Reference-S3-Compatible/Introduction-2.md)

[JAVA SDK](https://docs.jdcloud.com/cn/object-storage-service/installation-s3)

[PHP SDK](../API-Reference-S3-Compatible/Compatibility-Tools/SDK-PHP.md)

[PYTHON SDK](../API-Reference-S3-Compatible/Compatibility-Tools/SDK-Python.md)

[迁移工具OSS Tranfer](../Best-Practices/Data-Migration-Tool.md)

[S3FS挂载工具](../Best-Practices/S3fs.md)
