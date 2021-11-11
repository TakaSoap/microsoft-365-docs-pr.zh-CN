---
title: 基于角色的访问控制的自定义角色
description: 了解如何在自定义门户中管理Microsoft 365 Defender角色
keywords: access， 权限， Microsoft 365 Defender， M365， 安全， MCAS， 云应用安全， Microsoft Defender for Endpoint， 作用域， RBAC， 基于角色的访问， 基于角色的自定义访问， 基于角色的身份验证， MDO 中的 RBAC， 角色， 角色组， 权限继承， 细粒度权限
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
ms.openlocfilehash: a5ce8d049402fc0f1acdd1f47885c29bb4eba0cb
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914256"
---
# <a name="custom-roles-in-role-based-access-control-for-microsoft-365-defender"></a>基于角色的访问控制中的自定义角色Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**适用于：**

- Microsoft 365 Defender
 
有两种类型的角色可用于访问Microsoft 365 Defender：
- **全局Azure Active Directory (AD) 角色**
- **自定义角色**

可通过Microsoft 365 Defender全局角色集中管理对[Azure Active Directory (AAD) ](m365d-permissions.md)

如果您需要更大的灵活性和对特定产品数据的访问权限的控制，Microsoft 365 Defender每个安全门户通过创建自定义角色管理自定义访问。  

例如，通过 Microsoft Defender for Endpoint 创建的自定义角色将允许访问相关的产品数据，包括 Microsoft 365 Defender 数据。 同样，通过 Microsoft Defender for Office 365创建的自定义角色将允许访问相关产品数据，包括电子邮件&门户中的Microsoft 365 Defender数据。

具有现有自定义角色的用户可根据现有工作负载权限Microsoft 365 Defender门户中访问数据，无需其他配置。

## <a name="create-and-manage-custom-roles"></a>创建和管理自定义角色
可以通过以下每个安全门户创建并单独管理自定义角色和权限： 

- Microsoft Defender for Endpoint – [编辑 Microsoft Defender for Endpoint 中的角色](../defender-endpoint/user-roles.md)
- Microsoft Defender for Office 365 – 安全与[合规&中的权限](../office-365-security/permissions-in-the-security-and-compliance-center.md?preserve-view=true&view=o365-worldwide)
- Microsoft Cloud App Security –[管理管理员访问权限](/cloud-app-security/manage-admins)

通过单个门户创建的每个自定义角色都允许访问相关产品门户的数据。 例如，通过 Microsoft Defender for Endpoint 创建的自定义角色将仅允许访问 Defender for Endpoint 数据。

> [!TIP]
> 通过从导航窗格中选择"权限"Microsoft 365 Defender角色&访问权限和角色。 对 MCAS Microsoft Cloud App Security (的访问权限) MCAS 门户进行管理，并控制对 Microsoft Defender for Identity 的访问。  请参阅[Microsoft Cloud App Security](/cloud-app-security/manage-admins)

> [!NOTE]
> 在 Microsoft Microsoft Cloud App Security创建的自定义角色也有权访问 Microsoft Defender for Identity 数据。 具有用户组管理员或应用/实例管理员Microsoft Cloud App Security用户无法通过 Microsoft Cloud App Security 门户访问Microsoft 365 Defender数据。

## <a name="manage-permissions-and-roles-in-the-microsoft-365-defender-portal"></a>管理应用程序门户中的权限Microsoft 365 Defender角色
还可以在管理门户中管理Microsoft 365 Defender和角色：

1. 登录到 Microsoft 365 Defender 门户，security.microsoft.com。
2. 在导航窗格中，选择 **权限和角色**。
3. 在"**权限"标头** 下，选择"**角色"。**

> [!NOTE]
> 这仅适用于 Defender for Office 365 Defender for Endpoint。 必须在其相关门户中访问其他工作负载。


## <a name="required-roles-and-permissions"></a>所需角色和权限
下表概述了访问每个工作负载中每个统一体验所需的角色和权限。 下表中定义的角色是指各个门户中的自定义角色，并且未连接到 Azure AD 中的全局角色，即使名称类似。

> [!NOTE]
> 事件管理需要对属于事件的所有产品进行权限管理。
 
| **用户需要以下角色之一Microsoft 365 Defender**  | **Defender for Endpoint 需要以下角色之一**  | **Defender for Office 365** | **需要以下角色之一才能云应用安全** | 
|---------|---------|---------|---------|
| 查看调查数据： <ul><li>警报页面</li> <li>警报队列</li> <li>事件</li>  <li>事件队列</li> <li>操作中心</li></ul>| 查看数据 - 安全操作 | <ul><li>仅查看管理警报 </li> <li>组织配置</li><li>审核日志</li> <li>仅查看审核日志</li> <li>安全读者</li> <li>安全管理员</li><li>仅查看收件人</li></ul>  | <ul><li>全局管理员</li> <li>安全管理员</li> <li>合规性管理员</li> <li>安全操作员</li> <li>安全读者</li> <li>全局读取者</li></ul> |
| 查看搜寻数据 | 查看数据 - 安全操作 | <ul><li>安全读者</li> <li>安全管理员</li> <li>仅查看收件人</li> | <ul><li>全局管理员</li> <li>安全管理员</li> <li>合规性管理员</li> <li>安全操作员</li> <li>安全读者</li> <li>全局读取者</li></ul> |
| 管理警报和事件 | 警报调查 | <ul><li>管理警报</li> <li>安全管理员</li> | <ul><li>全局管理员</li> <li>安全管理员</li> <li>合规性管理员</li> <li>安全操作员</li> <li>安全读者</li></ul> |
| 操作中心修正 | 活动修正操作 – 安全操作 | 搜索和清除 | |
| 设置自定义检测 | 管理安全设置 |<ul><li>管理警报</li> <li>安全管理员</li></ul> | <ul><li>全局管理员</li> <li>安全管理员</li> <li>合规性管理员</li> <li>安全操作员</li> <li>安全读者</li> <li>全局读取者</li></ul> |
| 威胁分析 | 警报和事件数据： <ul><li>查看数据 - 安全操作</li></ul>TVM 缓解：<ul><li>查看数据 - 威胁和漏洞管理</li></ul> | 警报和事件数据：<ul> <li>仅查看管理警报</li> <li>管理警报</li> <li>组织配置</li><li>审核日志</li> <li>仅查看审核日志</li><li>安全读者</li> <li>安全管理员</li><li>仅查看收件人</li> </ul> 阻止的电子邮件尝试： <ul><li>安全读者</li> <li>安全管理员</li><li>仅查看收件人</li> | 不适用于 MCAS 或 MDI 用户 |

例如，若要查看 Microsoft Defender for Endpoint 中的搜寻数据，需要查看数据安全操作权限。  

同样，若要查看来自 Microsoft Defender for Office 365的搜寻数据，用户将需要以下角色之一：  

- 查看数据安全操作
- 安全读者
- 安全管理员
- 仅查看收件人

## <a name="related-topics"></a>相关主题
- [RBAC 角色](../office-365-security/migrate-to-defender-for-office-365-onboard.md#rbac-roles)
- [管理对 Microsoft 365 Defender 的访问权限](m365d-permissions.md)
- [管理 MCAS 的管理员访问权限](/cloud-app-security/manage-admins)
