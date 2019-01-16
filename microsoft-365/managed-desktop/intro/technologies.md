---
title: Microsoft 托管桌面技术
description: 本主题列出的技术和 Microsoft 托管桌面中使用的应用程序。
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 4b26ec88e1f4ca95fee6f7c4c927fc06cab32135
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865604"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft 托管桌面技术

本主题列出的技术和 Microsoft 托管桌面中使用的应用程序。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 托管桌面服务需要安装 Microsoft 365 E5 许可证 （或等效身份）。以下是包含在此许可证和 Microsoft 托管桌面如何使用 Microsoft 托管桌面设备使用的每个组件中的所有组件。 整个 Microsoft 托管桌面主题详细介绍了每个区域的特定的角色和职责。 

Microsoft 365 E5 由 3 个组件组成： Office 365 E5、 Windows 10 Enterprise 和 E5、 企业移动 + 安全 E5。  

## <a name="office-365-e5"></a>Office 365 E5
 |
 --- | ---
Office 365 标准套件 （64 位） * | 标准的 Office 套件应用程序将附带设备： Word、 Excel、 PowerPoint、 Outlook、 Publisher、 Access、 业务，OneNote 的 Skype。<br><br>64 位单击以运行 Office 365 标准套件中不包含 (C2R) 完整版本的 Microsoft Project 和 Microsoft Visio。 但是，由于取决于标准的 Office 套件安装这些应用程序的安装，Microsoft 托管桌面已创建默认 Intune 部署和客户将用于部署到这些应用程序的安全组许可的最终用户。  
应用商店应用程序 |    Microsoft Sway、 Microsoft 工作组和 Power BI 桌面 （不专业人员） 都不附带了设备。这些应用程序可供下载 Microsoft 存储中。
Win32 应用程序 |    Power BI Pro、 Azure 信息保护客户端和 Microsoft 计划程序不附带设备，并可以由客户打包部署。 
Web 应用程序 |  Yammer，Office Online，Delve，流 StaffHub、 PowerApps 都不附带了该设备。用户可以访问这些浏览器中使用的应用程序的 web 版本。
业务在线云和 PBX 的 Skype | 可通过 Office 365 E5 获得此功能。Microsoft 托管桌面将不配置此服务的任何方面

## <a name="windows-10-enterprise-e5"></a>Windows 10 企业 E5

 |
 --- | ---
凭据 Guard |  Microsoft 托管桌面将所提供的指导和管理此功能的云方面
设备 Guard （Windows Defender 应用程序控制） | Microsoft 托管桌面将创建策略。客户将管理签名
AppLocker 管理 |  Microsoft 托管桌面将创建策略。客户将管理签名
Application Virtualization (APP-V) |    Microsoft 托管桌面不支持这种部署，如 Intune 上不支持。
用户体验虚拟化 (UE-V) | 未使用此属性与托管的 Microsoft 托管桌面设备
托管的用户体验  | 这不用于托管的 Microsoft 托管桌面设备。MDM 用作设备管理解决方案
Windows Defender 高级威胁防护 |   这用于通过 Microsoft 托管桌面管理设备安全策略。 

## <a name="enterprise-mobility--security"></a>企业移动性 + 安全性 

 |
 --- | ---
企业移动 + 安全 E3<br>Azure Active Directory Premium P2 |    企业移动 + 安全 E3 和 AADP 的所有方面可能都用于管理 MDM 设备
Microsoft Cloud App Security |  这是一项可选功能，客户可以使用与 Microsoft 托管桌面服务。
Azure 信息保护 P2  |这是一项可选功能，客户可以使用与 Microsoft 托管桌面服务。
