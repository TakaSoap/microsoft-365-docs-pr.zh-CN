---
title: Microsoft 托管桌面应用程序要求
description: ''
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 71952a8b073f002890cc95883e717aeb04c0cd68
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865383"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Microsoft 托管桌面应用程序要求

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
您想要部署到 Microsoft 托管桌面设备上的业务线应用程序必须满足本主题中的要求。 

## <a name="application-condition"></a>应用程序条件

非常重要的应用程序不对 Microsoft 托管桌面环境产生不利影响。以下是应用程序必须满足 microsoft 将其部署顺序的要求。对于任何给定应用程序或驱动程序中，Microsoft 可能放弃根据此处提供的任何要求。Microsoft 可能决定删除任何应用程序或带来负面影响性能和可靠性 Microsoft 托管桌面设备的驱动程序。

## <a name="deployable-using-microsoft-technologies"></a>可使用 Microsoft 技术部署

Microsoft 托管桌面使用 Intune、 Microsoft 存储和 Microsoft Store for Business 部署应用程序。因此，必须能够通过这些服务的新版本部署方式打包应用程序。

## <a name="prohibited-app-classes"></a>禁止应用程序类

某些应用程序类型不是允许使用 Microsoft 托管桌面设备上：
- 第三方防病毒、 安全性或审核软件
- Office 365 Pro Plus 之前的 Microsoft Office 版本
- 安装或捆绑其他第三方软件应用程序

## <a name="restricted-app-behaviors"></a>受限制的应用程序行为

某些应用程序行为可能也会破坏用户体验或需要演示 Microsoft 托管桌面设备安全风险。应用程序应表现出以下行为或特征： 
- 安装后台服务或生成长时间运行背景进程
- 自动添加到 Windows 启动路径
- 呼叫未记录 Windows 或 Office Api 或承担内部 Windows 或 Office 数据结构依赖项
- 用作应用程序商店或内置扩展管理器
- 将最终用户的权限提升
- 具有已知安全漏洞
- 使用其不能上卷到受信任的根证书签名
- 加密或限制对最终用户数据访问
- 在运行时修改操作系统代码

## <a name="driver-deployment"></a>驱动程序部署

驱动程序 Windows Update 中可用，或者单独签名的 Windows 硬件质量实验室 (WHQL)，除非 Microsoft Microsoft 将部署到 Microsoft 托管桌面设备驱动程序之前必须批准驱动程序。