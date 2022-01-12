---
title: 支持的文件类型Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 应用程序支持的文件类型Microsoft 365 Advanced eDiscovery，包括 OCR 功能支持的图像文件类型Advanced eDiscovery。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7462048816f8c5962453422506116e6e88d8a54c
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61938596"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>支持的文件类型Advanced eDiscovery

Advanced eDiscovery支持许多不同级别的许多文件类型。 支持文件类型在本文的下表中进行了介绍。 此列表尚未最终确定，我们将在继续验证测试时添加新的文件类型。 这些表指示文本提取 (以及图像文件) 的光学字符识别或 OCR 文本提取是否支持文件类型，在本机查看器中可查看，Advanced eDiscovery 中的注释查看器也支持此类型。

## <a name="archive--container"></a>存档/容器

<br>

****

|Mime 类型|文件标识|元数据提取|容器提取|可能的扩展|
|---|:---:|:---:|:---:|:---:|
|application/x-7z-compressed|是|是|是|.7z|
|application/x-rar-compressed|是|是|是|.rar|
|application/x-tar|是|是|是|.tar|
|application/zip|是|是|是|.zip|
|

## <a name="audio--video"></a>音频/视频

<br>

****

|Mime 类型|文件标识|元数据提取|文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/mp4|是|是|否|是|否|.f4v; .m4a; .m4v;.mp4;.mp4v;.mpeg; .mpeg4|
|audio/mpeg|是|是|否|是|否|.mpeg|
|video/3gpp|是|是|否|是|否|.3gp|
|video/3gpp2|是|是|否|是|否|.3g2; .3gp2|
|video/quicktime|是|是|否|是|否|.moov; .mov; .qt|
|video/x-m4v|是|是|否|是|否|.m4v|
|

## <a name="database"></a>Database

<br>

****

|Mime 类型|文件标识|元数据提取|文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/x-msaccess|是|是|是|否|否|.mdb|
|

## <a name="email"></a>电子邮件

<br>

****

|Mime 类型|文件标识|元数据提取|文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-outlook|是|是|是|是|是|.msg|
|message/rfc822|是|是|是|是|是|.eml|
|text/vcard-contact|是|是|是|是|是|.vcf|
|

## <a name="email-container"></a>电子邮件容器

<br>

****

|Mime 类型|文件标识|元数据提取|容器提取|可能的扩展|
|---|:---:|:---:|:---:|:---:|
|application/mbox|是|是|是|.mbox|
|application/vnd.ms-outlook-pst|是|是|是|.pst|
|

## <a name="html"></a>HTML

<br>

****

|Mime 类型|文件标识|元数据提取|文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/xhtml+xml|是|是|是|是|是|.xhtml|
|application/xml|是|是|是|是|是|.xml|
|text/html|是|是|是|是|是|.htm;.html;.shtml|
|

## <a name="image"></a>图像

<br>

****

|Mime 类型|文件标识|元数据提取|OCR 文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|image/bmp|是|是|是|是|是|.bmp|
|image/emf|是|是|是|是|是|.emf|
|image/gif|是|是|是|是|是|.gif|
|image/jpeg|是|是|是|是|是|.jpeg;.jpg|
|image/png|是|是|是|是|是|.png|
|image/svg+xml|是|是|是|是|否|.svg|
|image/tiff|是|是|是|是|是|.tif|
|image/vnd.dwg|是|是|是|是|是|.dwg; .dxf|
|image/wmf|是|是|是|是|是|.wmf|
|

## <a name="microsoft-excel"></a>Microsoft Excel

<br>

****

|Mime 类型|文件标识|元数据提取|文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-excel|是|是|是|是|是|.dat;.xls|
|application/vnd.ms-excel.sheet.binary.macroenabled.12|是|是|是|是|否|.xlsb|
|application/vnd.ms-excel.sheet.macroenabled.12|是|是|是|是|是|.xlsm|
|application/vnd.ms-excel.template.macroenabled.12|是|是|是|否|否|.xltm|
|application/vnd.openxmlformats-officedocument.spreadsheetml.sheet|是|是|是|是|是|.xlsx|
|application/vnd.openxmlformats-officedocument.spreadsheetml.template|是|是|是|是|是|.xltx|
|

## <a name="microsoft-onenote"></a>Microsoft OneNote

<br>

****

|Mime 类型|文件标识|元数据提取|文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/onenote|是|是|是|否|否|.one|
|

## <a name="microsoft-powerpoint"></a>Microsoft PowerPoint

<br>

****

|Mime 类型|文件标识|元数据提取|文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-powerpoint|是|是|是|是|是|.pot;.pps;.ppt|
|application/vnd.openxmlformats-officedocument.presentationml.presentation|是|是|是|是|是|.pptx|
|application/vnd.openxmlformats-officedocument.presentationml.幻灯片|是|是|是|是|是|.ppsx|
|application/vnd.openxmlformats-officedocument.presentationml.template|是|是|是|是|是|.potx|
|

## <a name="microsoft-project"></a>Microsoft Project

<br>

****

|Mime 类型|文件标识|元数据提取|文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-project|是|是|是|否|是|.mpp|
|

## <a name="microsoft-publisher"></a>Microsoft Publisher

<br>

****

|Mime 类型|文件标识|元数据提取|文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/x-mspublisher|是|是|是|是|是|.pub|
|

## <a name="microsoft-visio"></a>Microsoft Visio

<br>

****

|Mime 类型|文件标识|元数据提取|文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-visio.drawing|是|是|是|是|否||
|application/vnd.visio|是|是|是|是|是|.vsd|
|

## <a name="microsoft-word"></a>Microsoft Word

<br>

****

|Mime 类型|文件标识|元数据提取|文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/msword|是|是|是|是|是|.dat;.doc|
|application/rtf|是|是|是|是|是|.doc;.rtf|
|application/vnd.ms-word.document.macroenabled.12|是|是|是|是|是|.docm|
|application/vnd.ms-word.template.macroenabled.12|是|是|是|是|是|.dotm|
|application/vnd.openxmlformats-officedocument.wordprocessingml.document|是|是|是|是|是|.docx|
|application/vnd.openxmlformats-officedocument.wordprocessingml.template|是|是|是|是|是|.dotx|
|

## <a name="microsoft-works"></a>Microsoft Works

<br>

****

|Mime 类型|文件标识|元数据提取|文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.ms-works-ss|是|是|否|否|否|.wps|
|application/vnd.ms-works-wp|是|是|否|否|否|.wps|
|

## <a name="open-document-format"></a>打开文档格式

<br>

****

|Mime 类型|文件标识|元数据提取|文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.oasis.opendocument.text|是|是|是|是|是|.odt|
|

## <a name="other"></a>其他

<br>

****

|Mime 类型|文件标识|元数据提取|文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/json|是|是|是|是|是|不适用|
|application/vnd.ms-graph|是|是|否|否|否||
|application/winhlp|是|是|否|否|否|.hlp|
|application/x-tnef|是|是|否|否|否||
|

## <a name="plain-text"></a>纯文本

<br>

****

|Mime 类型|文件标识|元数据提取|文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|text/csv|是|是|是|是|是|.csv|
|text/plain|是|是|是|是|是|.con;.css;.csv; .dat; .pl;.txt|
|

## <a name="portable-document-format"></a>Portable Document Format

<br>

****

|Mime 类型|文件标识|元数据提取|文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/pdf|是|是|是|是|是|.pdf|
|

## <a name="word-perfect"></a>Word Perfect

<br>

****

|Mime 类型|文件标识|元数据提取|文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.wordperfect;version=5.0|是|是|是|否|否|.wpd|
|application/vnd.wordperfect;version=5.1|是|是|是|否|否|.wpd|
|application/vnd.wordperfect;version=6.x|是|是|是|否|否|.wpd|
|

## <a name="word-pro"></a>Word Pro

<br>

****

|Mime 类型|文件标识|元数据提取|文本提取|本机查看器|为查看器添加注释|可能的扩展|
|---|:---:|:---:|:---:|:---:|:---:|:---:|
|application/vnd.lotus-wordpro|是|是|否|否|否|.lwp|
|
