---
title: 基于角色的访问控制的自定义角色
description: 了解如何在 Microsoft 365 安全中心管理自定义角色
keywords: access， 权限， MTP， Microsoft 威胁防护， M365， 安全性， MCAS， MDATP， Cloud App Security， Microsoft Defender 高级威胁防护， 范围， 作用域， RBAC， 基于角色的访问， 基于角色的访问， 基于角色的身份验证， MDO 中的 RBAC， 角色， 角色组， 权限继承， 精细的权限
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
ms.openlocfilehash: 35ac4e26406fe6fde1385008b527dc4865e0392b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928924"
---
# <a name="custom-roles-in-role-based-access-control-for-microsoft-365-defender"></a>Microsoft 365 Defender 基于角色的访问控制中的自定义角色

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**适用于：**

- Microsoft 365 Defender
 
有两种类型的角色可用于访问 Microsoft 365 Defender：
- **全局 Azure Active Directory (AD) 角色**
- **自定义角色**

使用[Azure Active Directory](mtp-permissions.md)中的全局角色和 AAD 角色，可以共同 (Microsoft 365 Defender) 

如果需要更大的灵活性并控制对特定产品数据的访问，还可以通过每个安全门户创建自定义角色管理 Microsoft 365 Defender 访问。  

例如，通过 Microsoft Defender for Endpoint 创建的自定义角色将允许访问相关产品数据，包括 Microsoft 365 安全中心内的终结点数据。 同样，通过 Microsoft Defender for Office 365 创建的自定义角色将允许访问相关产品数据，包括 Microsoft 365 安全中心&电子邮件和协作数据。

具有现有自定义角色的用户可根据其现有工作负载权限访问 Microsoft 365 安全中心的数据，无需其他配置。

## <a name="create-and-manage-custom-roles"></a>创建和管理自定义角色
可以通过以下每个安全门户创建并单独管理自定义角色和权限： 

- Microsoft Defender for Endpoint – [编辑 Microsoft Defender for Endpoint 中的角色](/windows/security/threat-protection/microsoft-defender-atp/user-roles)
- Microsoft Defender for Office 365 – 安全与 [合规&中的权限](../office-365-security/permissions-in-the-security-and-compliance-center.md?preserve-view=true&view=o365-worldwide)
- Microsoft Cloud App Security – [管理管理员访问权限](/cloud-app-security/manage-admins)

通过单个门户创建的每个自定义角色都允许访问相关产品门户的数据。 例如，通过 Microsoft Defender for Endpoint 创建的自定义角色将仅允许访问 Defender for Endpoint 数据。

> [!TIP]
> 权限和角色也可通过 Microsoft 365 安全中心访问，方法为从导航窗格中选择"&角色"。 Microsoft Cloud App Security (MCAS) 通过 MCAS 门户进行管理，并控制对 Microsoft Defender 标识的访问。  请参阅 [Microsoft Cloud App Security](/cloud-app-security/manage-admins)

> [!NOTE]
> 在 Microsoft Cloud App Security 中创建的自定义角色也有权访问 Microsoft Defender for Identity 数据。 具有用户组管理员或应用/实例管理员 Microsoft Cloud App Security 角色的用户无法通过 Microsoft 365 安全中心访问 Microsoft Cloud App Security 数据。

## <a name="manage-permissions-and-roles-in-the-microsoft-365-security-center"></a>在 Microsoft 365 安全中心管理权限和角色
还可以在 Microsoft 365 安全中心管理权限和角色：

1. 登录到 Microsoft 365 安全中心，security.microsoft.com。
2. 在导航窗格中，选择 **"权限&角色"。**
3. 在"**权限"标头** 下，选择"**角色"。**

> [!NOTE]
> 这仅适用于 Defender for Office 365 和 Defender for Endpoint。 必须在其相关门户中访问其他工作负载。


## <a name="required-roles-and-permissions"></a>所需角色和权限
下表概述了访问每个工作负载中每个统一体验所需的角色和权限。 下表中定义的角色是指各个门户中的自定义角色，并且未连接到 Azure AD 中的全局角色，即使名称类似。

> [!NOTE]
> 事件管理需要对属于事件的所有产品的管理权限。
 
| **Microsoft 365 Defender 需要以下角色之一**  | **Defender for Endpoint 需要以下角色之一**  | **Defender for Office 365 需要以下角色之一** | **Cloud App Security 需要以下角色之一** | 
|---------|---------|---------|---------|
| 查看调查数据： <ul><li>警报页面</li> <li>警报队列</li> <li>事件</li>  <li>事件队列</li> <li>操作中心</li></ul>| 查看数据 - 安全操作 | <ul><li>仅查看管理警报 </li> <li>组织配置</li><li>审核日志</li> <li>仅查看审核日志</li> <li>安全读者</li> <li>安全管理员</li><li>仅查看收件人</li></ul>  | <ul><li>全局管理员</li> <li>安全管理员</li> <li>合规性管理员</li> <li>安全操作员</li> <li>安全读者</li> <li>全局读取者</li></ul> |
| 查看搜寻数据 | 查看数据 - 安全操作 | <ul><li>安全读者</li> <li>安全管理员</li> <li>仅查看收件人</li> | <ul><li>全局管理员</li> <li>安全管理员</li> <li>合规性管理员</li> <li>安全操作员</li> <li>安全读者</li> <li>全局读取者</li></ul> |
| 管理警报和事件 | 警报调查 | <ul><li>管理警报</li> <li>安全管理员</li> | <ul><li>全局管理员</li> <li>安全管理员</li> <li>合规性管理员</li> <li>安全操作员</li> <li>安全读者</li></ul> |
| 操作中心修正 | 活动修正操作 – 安全操作 | 搜索和清除 | |
| 设置自定义检测 | 管理安全设置 |<ul><li>管理警报</li> <li>安全管理员</li></ul> | <ul><li>全局管理员</li> <li>安全管理员</li> <li>合规性管理员</li> <li>安全操作员</li> <li>安全读者</li> <li>全局读取者</li></ul> |
| 威胁分析 | 警报和事件数据： <ul><li>查看数据 - 安全操作</li></ul>TVM 缓解：<ul><li>查看数据 - 威胁和漏洞管理</li></ul> | 警报和事件数据：<ul> <li>仅查看管理警报</li> <li>管理警报</li> <li>组织配置</li><li>审核日志</li> <li>仅查看审核日志</li><li>安全读者</li> <li>安全管理员</li><li>仅查看收件人</li> </ul> 阻止的电子邮件尝试： <ul><li>安全读者</li> <li>安全管理员</li><li>仅查看收件人</li> | 不适用于 MCAS 或 MDI 用户 |

例如，若要查看 Microsoft Defender for Endpoint 中的搜寻数据，需要查看数据安全操作权限。  

同样，若要查看来自 Microsoft Defender for Office 365 的搜寻数据，用户需要以下角色之一：  

- 查看数据安全操作
- 安全读者
- 安全管理员
- 仅查看收件人

## <a name="related-topics"></a>相关主题
- [管理对 Microsoft 365 Defender 的访问权限](mtp-permissions.md)
- [管理 MCAS 的管理员访问权限](/cloud-app-security/manage-admins)