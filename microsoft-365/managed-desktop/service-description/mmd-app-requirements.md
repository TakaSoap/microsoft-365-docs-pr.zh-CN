---
title: Microsoft 托管桌面应用程序要求
description: ''
keywords: microsoft 托管桌面, microsoft 365, 服务, 文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: de6cc7d77e023a9d41961e5fbcce060f1bb659ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278332"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Microsoft 托管桌面应用程序要求

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
要部署到 Microsoft 托管桌面设备的业务线应用程序必须满足本主题中的要求。 

## <a name="application-condition"></a>应用程序条件

应用程序不会对 Microsoft 托管桌面环境产生负面影响, 这一点非常重要。 以下是应用程序必须满足以让 Microsoft 部署它的要求。 对于任何给定的应用程序或驱动程序, Microsoft 可能会停征此处提供的任何要求。 microsoft 可能会决定删除对 Microsoft 托管桌面设备的性能和可靠性产生负面影响的任何应用程序或驱动程序。

## <a name="deployable-using-microsoft-technologies"></a>可使用 Microsoft 技术部署

Microsoft 托管桌面使用 Intune、microsoft store 和 microsoft store for Business 来部署应用程序。 因此, 应用程序必须以可由这些服务的当前版本部署的方式进行打包。

## <a name="prohibited-app-classes"></a>禁止的应用程序类

Microsoft 托管桌面设备上不允许某些应用程序类型:
- 第三方反病毒、安全性或审核软件
- 第三方 web 浏览器
- office 365 Pro Plus 之前的 Microsoft Office 版本
- 安装或捆绑其他第三方软件的应用程序

## <a name="restricted-app-behaviors"></a>受限制的应用程序行为

某些应用程序行为可能会对用户体验造成损害或向 Microsoft 托管桌面设备带来安全风险。 应用程序不应表现出以下行为或特征: 

用户体验:
- 安装后台服务或生成长时间运行的后台进程
- 将自身添加到 Windows 启动路径

安全性：
- 调用未记录的 windows 或 office api 或对内部 Windows 或 office 数据结构进行依赖关系
- 充当应用商店或具有内置扩展管理器
- 提升最终用户的权限
- 存在已知的安全漏洞
- 使用不会汇总到受信任的根的证书进行签名
- 加密或限制对最终用户数据的访问
- 在运行时修改操作系统代码

## <a name="driver-deployment"></a>驱动程序部署

除非驱动程序在 windows 更新中可用或由 windows 硬件质量实验室 (WHQL) 单独签名, 否则 microsoft 必须先批准驱动程序, 然后才能将驱动程序部署到 microsoft 托管桌面设备。
