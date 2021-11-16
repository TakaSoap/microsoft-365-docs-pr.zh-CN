---
title: 如何确定数据治理建议的内容
f1.keywords:
- NOCSH
ms.author: brendonb
author: cabailey
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection:
- SPO_Content
ms.custom: admindeeplinkDEFENDER
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 安全中心与 Microsoft 365 合规中心根据你组织的当前设置提供数据管理建议，并让你可以通过几次单击进行设置。其中一些建议会检测组织中的特定内容，然后提供管理该内容的建议步骤。例如，建议可能会检测包含业务关键内容的项目（如律师-客户特权或 NDA 信息），然后让你自动为这些项目应用保留标签，以确保根据需要对它们进行分类和保留。本主题列出了你可能会看到的数据管理建议，并介绍了为触发每条建议而检测的内容。
ms.openlocfilehash: f6343ab8856393f1928edfdb917e26fe9d72cc97
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2021
ms.locfileid: "60963343"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a>如何确定数据治理建议的内容

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 安全中心</a> 和 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心</a> 根据组织的当前设置提供有关数据治理的建议，并允许你只需单击几下即可进行设置。 其中一些建议检测组织中的特定内容，然后提供用于管理该内容的建议步骤。 例如，建议可能会检测包含业务关键内容的项目（如律师-客户特权或 NDA 信息），然后允许你自动将保留标签应用于这些项目，以确保根据需要对其进行分类和保留。

本主题列出了你可能会看到的数据治理建议，并介绍了为触发每条建议而检测的内容。

## <a name="clean-up-voicemail"></a>清理语音邮件

在用户邮箱中检测到标识为“语音邮件”邮件类型的电子邮件时，将显示此建议。详细了解 [Exchange 中的邮件属性](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators#searchable-properties-in-exchange)。

## <a name="label-attorney-client-privilege-content"></a>标记律师-客户特权内容

当满足以下任一条件时，将显示此建议。

- 在电子邮件正文中检测到以下关键字的任何组合：
  - ACP
  - 律师客户特权
  - 律师-客户特权
  - 律师-客户特权的

- 在 SharePoint 或 OneDrive 文件中检测到以下关键字的任意组合：
  - ACP
  - 律师客户特权*
  - AC 特权

## <a name="retain-audio-files"></a>保留音频文件

在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。

- .MP3
- .WMA
- .WAV
- .RA
- .RAM
- .RM
- .MID
- .OGG
- .AIFF
- .PCM
- .AAC
- .FLAC
- .ALAC

## <a name="retain-cad-files"></a>保留 CAD 文件

在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。

- .3DXML
- .ACIS
- .ARC
- .ASM
- .CAT*
- .CGR
- .DW*
- .DX*
- .EDRW
- .IAM
- .IGES
- .IGS
- .IPT
- .JT
- .MF1
- .NEU
- .PAR
- .PKG
- .PRC
- .PRT
- .PSM
- .PWD
- .SLD*
- .STEP
- .STL
- .STP
- .U3D
- .UNV
- .VRML
- .WRL
- .X_*
- .XAS
- .XMT*
- .XPR

## <a name="retain-image-files"></a>保留图像文件

在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。

- .JPEG
- .GIF
- .TIF*
- .BMP
- .PNG
- .RAW
- .PSD
- .PSP
- .JPG
- .EXIF
- .PPM
- .PGM
- .PBM
- .PNM
- .WEBP

## <a name="retain-nda-content"></a>保留 NDA 内容

当满足以下任一条件时，将显示此建议。

- 在电子邮件正文中检测到以下关键字的任何组合：
  - NDA
  - “保密协议”
  - “保密协议”

- 在 SharePoint 或 OneDrive 中的 .PDF 或 .DOC 文件中检测到以下关键字的任意组合：
  - NDA
  - 保密协议

## <a name="retain-software-development-files"></a>保留软件开发文件

在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。

- .ASAX
- .ASM
- .ASP*
- .BAT
- .CONFIG
- .CS
- .CSS
- .DISCO
- .HTM*
- .INC
- .JAD
- .JAVA
- .JS*
- .LIB
- .O
- .PHP
- .RC
- .RESX
- .RPT
- .RSS
- .SCPT
- .SRC
- .VB*
- .WSF
- .XCODEPROJ
- .XML
- .XSD
- .XSL*

## <a name="retain-video-files"></a>保留视频文件

在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。

- .AVCHD
- .AVI
- .FLV
- .MOV
- .MP2V
- .MP4
- .MP4V
- .MPE
- .MPEG
- .MPEG1
- .MPEG2
- .MPEG4
- .MPG
- .MPG2
- .MPG4
- .WMV
- .XMV
