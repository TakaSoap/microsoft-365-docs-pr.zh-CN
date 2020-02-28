---
title: Microsoft 托管桌面应用程序要求
description: ''
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 01c580cd671a84ef68c18b114e133f046a3e5b3b
ms.sourcegitcommit: 7930fb8327bbd3594fde52f2dbf91e0f5d92f684
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "42328064"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Microsoft 托管桌面应用程序要求

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
为了保证 Microsoft 托管桌面设备的性能、可靠性和可维护性，客户的业务线应用程序不一定会严重影响最终用户体验，也不能修改安全的态度。 因此，要部署到 Microsoft 托管桌面设备的业务线应用程序必须满足本主题中的要求。

## <a name="application-condition"></a>应用程序条件

应用程序不会对 Microsoft 托管桌面环境产生负面影响，这一点非常重要。 以下是应用程序必须满足部署应用程序的要求。 对于任何给定的应用程序或驱动程序，Microsoft 可能会停征此处提供的任何要求。 Microsoft 可能会决定删除对 Microsoft 托管桌面设备的性能和可靠性产生负面影响的任何应用程序或驱动程序。

## <a name="centrally-managed-apps"></a>集中管理的应用程序

所有安装在 Microsoft 托管设备上的应用程序和驱动程序都必须通过 Microsoft Intune、Microsoft Store 或 Microsoft Store for Business 进行部署;如果可用，还将通过 Windows Update 服务部署驱动程序。 

## <a name="prohibited-app-classes"></a>禁止的应用程序类

Microsoft 托管桌面设备上不允许某些应用程序类型：
- 第三方反病毒、安全性或审核软件
- Office 365 专业增强版之前的 Microsoft Office 版本
- 安装或捆绑其他第三方软件的应用程序

## <a name="restricted-app-behaviors"></a>受限制的应用程序行为

某些应用程序行为可能会对用户体验产生负面影响，也可能对 Microsoft 托管桌面设备带来安全风险。 在 Microsoft 托管桌面环境中，不允许运行具有以下行为的应用程序，而无需从 Microsoft 进行指定。

用户体验：
- 安装后台服务
- 将自身添加到 Windows 启动路径
- 依赖驱动程序的应用程序
- 第三方 web 浏览器

安全性：
- 提升最终用户的权限
- 充当应用商店或具有内置扩展管理器
- 存在已知的安全漏洞
- 加密或限制对最终用户数据的访问
- 未签名或使用不会汇总到受信任的根的证书进行签名


## <a name="driver-deployment"></a>驱动程序部署

Microsoft 托管桌面仅支持通过 Microsoft 托管设备在 Windows 更新或已安装的收件箱中提供的设备驱动程序。 

如果应用程序需要特定驱动程序来运行它，则会将其视为受限制的应用程序，并在将其部署到 Microsoft 托管桌面之前需要异常。 

