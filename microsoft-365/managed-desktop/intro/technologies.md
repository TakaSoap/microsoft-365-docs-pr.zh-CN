---
title: Microsoft 托管桌面技术
description: 本主题列出了 Microsoft 托管桌面中使用的技术和应用。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 914a90b4267132c9cb942740ceb974b084bcdf82
ms.sourcegitcommit: 2f4a61f02ea90102ded8e5d71c9b78a1f7f6b789
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2019
ms.locfileid: "35778087"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft 托管桌面技术

本主题列出了 Microsoft 托管桌面中使用的技术和应用。

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

所有 Microsoft 托管桌面用户都需要 microsoft 365 企业版许可。 有关服务的许可要求的详细信息, 请参阅[Microsoft 托管桌面的先决条件](../get-ready/prerequisites.md)。

以下是所需企业版许可证中包含的所有组件, 以及服务如何将每个组件与 Microsoft 托管桌面设备一起使用。 在整个 Microsoft 托管桌面主题中详细介绍了每个领域的特定角色和职责。 

## <a name="office-365-e3"></a>Office 365 E3
 |
 --- | ---
Office 365 Standard Suite (64 位) * | 标准 Office 套件应用程序将随设备一起附带: Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business、OneNote。<br><br>64位单击可运行 (C2R) 完整版本的 Microsoft Project 和 Microsoft Visio 不包含在 Office 365 Standard Suite 中。  但是, 由于安装这些应用程序依赖于标准 Office 套件安装, Microsoft 托管桌面已创建默认的 Intune 部署和安全组, 客户将使用这些部署和安全组将这些应用程序部署到许可的最终用户。  
应用商店应用 |    Microsoft Sway, Power BI Desktop 不随设备附带。 这些应用程序可从 Microsoft Store 下载。
Win32 应用程序 |    Power BI Pro、Azure 信息保护客户端和 Microsoft Planner 不随设备一起提供, 可以打包以供客户部署。 
Web 应用程序 |  Yammer、Office 在浏览器、Delve、流、StaffHub、PowerApps 不随设备一起附带。 用户可以通过浏览器访问这些应用程序的 web 版本。
Skype for Business Online 云 PBX | 可通过 Office 365 获取此功能。 Microsoft 托管桌面不会配置此服务的任何方面

## <a name="windows-10-enterprise-e5"></a>Windows 10 企业版 E5

 |
 --- | ---
Credential Guard |  Microsoft 将提供指导并管理此功能的云方面。
Application Virtualization (app-v) |    Microsoft 托管桌面不支持此类型的部署, 因为 Intune 不支持此类型的部署。
用户体验虚拟化 (UE-V) | 这不与 Microsoft 托管桌面托管设备一起使用。
托管用户体验  | 这不与 Microsoft 托管桌面托管设备一起使用。 MDM 用作设备管理解决方案。
Microsoft Defender 高级威胁防护 | Microsoft 托管桌面使用它来管理设备安全策略。 

## <a name="enterprise-mobility--security-e5"></a>企业移动性 + 安全性 E5

 |
 --- | ---
企业移动性 + 安全 E3<br>Azure Active Directory 高级 P2 |    企业移动性 + 安全 E3 和 AADP 的各个方面均可用于管理 MDM 设备。
Microsoft Cloud App Security |  这是客户可用于 Microsoft 托管桌面服务的一项可选功能。
Azure 信息保护 P2  |这是客户可用于 Microsoft 托管桌面服务的一项可选功能。
