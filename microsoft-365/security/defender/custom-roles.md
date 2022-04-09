---
title: 基于角色的访问控制的自定义角色
description: 了解如何在Microsoft 365 Defender门户中管理自定义角色
keywords: access， permissions， Microsoft 365 Defender， M365， 安全， MCAS， 云应用安全， Microsoft Defender for Endpoint， 范围， 范围， 范围， RBAC， 基于角色的访问， 基于角色的访问， 基于角色的身份验证， MDO 中的 RBAC， 角色， 角色组， 权限继承， 细化权限
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 94330e319eeb44618c1e11b27da7b3d63c08d203
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "64731342"
---
# <a name="custom-roles-in-role-based-access-control-for-microsoft-365-defender"></a>Microsoft 365 Defender的基于角色的访问控制中的自定义角色

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**适用于：**

- Microsoft 365 Defender
 
有两种类型的角色可用于访问Microsoft 365 Defender：
- **全局Azure Active Directory (AD) 角色**
- **自定义角色**

Azure Active Directory (AAD) [中使用全局角色](m365d-permissions.md)可以集体管理对Microsoft 365 Defender的访问

如果需要更大的灵活性和对特定产品数据访问权限的控制，也可以通过每个各自的安全门户创建自定义角色来管理Microsoft 365 Defender访问权限。  

例如，通过Microsoft Defender for Endpoint创建的自定义角色将允许访问相关的产品数据，包括Microsoft 365 Defender门户中的终结点数据。 同样，通过Microsoft Defender for Office 365创建的自定义角色将允许访问相关产品数据，包括Microsoft 365 Defender门户中的电子邮件&协作数据。

具有现有自定义角色的用户可以根据现有工作负荷权限访问Microsoft 365 Defender门户中的数据，无需其他配置。

## <a name="create-and-manage-custom-roles"></a>创建和管理自定义角色
可以通过以下每个安全门户创建和单独管理自定义角色和权限： 

- Microsoft Defender for Endpoint – [编辑Microsoft Defender for Endpoint中的角色](../defender-endpoint/user-roles.md)
- Microsoft Defender for Office 365 – [安全&合规中心中的权限](../office-365-security/permissions-in-the-security-and-compliance-center.md?preserve-view=true&view=o365-worldwide)
- Microsoft Defender for Cloud Apps – [管理管理员访问权限](/cloud-app-security/manage-admins)

通过单个门户创建的每个自定义角色都允许访问相关产品门户的数据。 例如，通过Microsoft Defender for Endpoint创建的自定义角色仅允许访问 Defender for Endpoint 数据。

> [!TIP]
> 还可以通过Microsoft 365 Defender门户从导航窗格中选择权限&角色来访问权限和角色。 对Microsoft Defender for Cloud Apps的访问通过Defender for Cloud应用门户进行管理，并控制对Microsoft Defender for Identity的访问。  请参阅[Microsoft Defender for Cloud Apps](/cloud-app-security/manage-admins)

> [!NOTE]
> 在Microsoft Defender for Cloud Apps中创建的自定义角色也有权访问Microsoft Defender for Identity数据。 具有用户组管理员或应用/实例管理员Microsoft Defender for Cloud Apps角色的用户无法通过Microsoft 365 Defender门户访问Microsoft Defender for Cloud Apps数据。

## <a name="manage-permissions-and-roles-in-the-microsoft-365-defender-portal"></a>在Microsoft 365 Defender门户中管理权限和角色
权限和角色也可以在Microsoft 365 Defender门户中进行管理：

1. 在 security.microsoft.com 登录到Microsoft 365 Defender门户。
2. 在导航窗格中，选择 **权限和角色**。
3. 在" **权限"** 标头下，选择 **"角色**"。

> [!NOTE]
> 这仅适用于 Defender for Office 365 和 Defender for Endpoint。 其他工作负载的访问必须在其相关门户中完成。


## <a name="required-roles-and-permissions"></a>所需角色和权限
下表概述了访问每个工作负荷中每个统一体验所需的角色和权限。 下表中定义的角色引用各个门户中的自定义角色，并且未连接到Azure AD中的全局角色，即使命名类似。

> [!NOTE]
> 事件管理需要对属于事件的所有产品进行权限管理。
 
| **Microsoft 365 Defender需要以下角色之一**  | **Defender for Endpoint 需要以下角色之一**  | **Defender for Office 365需要以下角色之一** | **Defender for Cloud应用需要以下角色之一** | 
|---------|---------|---------|---------|
| 查看调查数据： <ul><li>"警报"页</li> <li>警报队列</li> <li>事件</li>  <li>事件队列</li> <li>操作中心</li></ul>| 查看数据安全操作 | <ul><li>仅查看管理警报 </li> <li>组织配置</li><li>审核日志</li> <li>仅查看审核日志</li> <li>安全读者</li> <li>安全管理员</li><li>仅查看收件人</li></ul>  | <ul><li>全局管理员</li> <li>安全管理员</li> <li>合规性管理员</li> <li>安全操作员</li> <li>安全读者</li> <li>全局读取者</li></ul> |
| 查看搜寻数据 | 查看数据安全操作 | <ul><li>安全读者</li> <li>安全管理员</li> <li>仅查看收件人</li> | <ul><li>全局管理员</li> <li>安全管理员</li> <li>合规性管理员</li> <li>安全操作员</li> <li>安全读者</li> <li>全局读取者</li></ul> |
| 管理警报和事件 | 警报调查 | <ul><li>管理警报</li> <li>安全管理员</li> | <ul><li>全局管理员</li> <li>安全管理员</li> <li>合规性管理员</li> <li>安全操作员</li> <li>安全读者</li></ul> |
| 操作中心修正 | 主动修正操作 – 安全操作 | 搜索和清除 | |
| 设置自定义检测 | 管理安全设置 |<ul><li>管理警报</li> <li>安全管理员</li></ul> | <ul><li>全局管理员</li> <li>安全管理员</li> <li>合规性管理员</li> <li>安全操作员</li> <li>安全读者</li> <li>全局读取者</li></ul> |
| 威胁分析 | 警报和事件数据： <ul><li>查看数据安全操作</li></ul>TVM 缓解措施：<ul><li>查看数据 - 威胁和漏洞管理</li></ul> | 警报和事件数据：<ul> <li>仅查看管理警报</li> <li>管理警报</li> <li>组织配置</li><li>审核日志</li> <li>仅查看审核日志</li><li>安全读者</li> <li>安全管理员</li><li>仅查看收件人</li> </ul> 阻止了电子邮件尝试： <ul><li>安全读者</li> <li>安全管理员</li><li>仅查看收件人</li> | 不适用于Defender for Cloud应用或 MDI 用户 |

例如，若要查看Microsoft Defender for Endpoint中的搜寻数据，需要查看数据安全操作权限。  

同样，若要查看来自Microsoft Defender for Office 365的搜寻数据，用户需要以下角色之一：  

- 查看数据安全操作
- 安全读者
- 安全管理员
- 仅查看收件人

## <a name="related-topics"></a>相关主题
- [RBAC 角色](../office-365-security/migrate-to-defender-for-office-365-onboard.md#rbac-roles)
- [管理对 Microsoft 365 Defender 的访问权限](m365d-permissions.md)
- [管理Defender for Cloud应用的管理员访问权限](/cloud-app-security/manage-admins)
