---
title: 关于 Microsoft 365 管理中心中的 Intune 管理员角色
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
description: 管理员角色映射到业务功能，并授予在管理中心执行特定任务的权限。 例如，服务管理员可打开 Microsoft 的支持票证。
ms.openlocfilehash: 650a46c20acaf207f757ebbbe8f8b7179c29158f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60161794"
---
# <a name="intune-admin-roles-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理中心中的 Intune 管理员角色

你的 Microsoft 365 或 Office 365 订阅附带了一组管理员角色，可使用 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a> 将这些角色分配给组织中的用户。每个管理员角色都映射到常用的业务功能，并授予组织中的用户在管理中心执行特定任务的权限。

Microsoft 365 管理中心可用于管理一些 Microsoft Intune 角色。 然而，这些角色是 Intune 管理中心中可用角色的子集。 是否在查找 Microsoft Intune 的详细角色说明？ 查看 [Microsoft Intune 中的基于角色的访问控制 (RBAC)](/mem/intune/fundamentals/role-based-access-control)。

有关在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2097861" target="_blank">Microsoft 365 管理中心</a> 内分配角色的详细信息，请参阅 [分配管理员角色](assign-admin-roles.md)。

在 Microsoft 365 管理中心，你可以转到“**角色**”，然后选择任何角色以打开其详细信息窗格。 选择“**权限**”选项卡，以查看分配有该角色的管理员有权执行的操作的详细列表。 选择“**已分配**”或“**已分配管理员**”选项卡，以向角色添加用户。

## <a name="microsoft-intune-roles-available-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理中心提供的 Microsoft Intune 角色

|管理员角色     |应该为谁分配此角色？  |
|---------|---------|
|应用程序管理员     |   将应用程序管理员角色分配给管理移动应用的应用程序生命周期、配置策略管理的应用以及查看设备信息和配置文件的用户。  |
|技术支持操作员     |   将技术支持操作员角色分配给向用户和设备分配应用程序和策略的用户。 |
|Intune 角色管理员    |   将 Intune 角色管理员分配给可以向其他管理员分配 Intune 权限，并且可以管理自定义和内置 Intune 角色的用户。   |
|策略和个人资料管理员     |   将策略和个人资料管理员角色分配给用户管理合规性策略、配置文件和 Apple 注册的用户。   |
|只读操作员     |   将只读操作员角色分配给仅可查看用户、设备、注册详细信息和配置的用户。   |
|学校管理员     |   将学校管理员角色分配给用户，以获取在 Intune 教育版中管理 Windows 10 和 iOS 设备、应用和配置的完全访问权限。   |

## <a name="delegated-administration-for-microsoft-partners"></a>Microsoft 合作伙伴的委派管理

如果你正与 Microsoft 合作伙伴协作，可向其分配管理员角色。 他们又可以为你的公司（或其公司）内的用户分配管理员角色。 你可能希望他们执行此操作，例如，如果是由对方为你设置和管理联机组织的情况。
  
合作伙伴可以分配以下角色：
  
- 完全管理，其权限等同于全局管理员，但通过合作伙伴中心管理多重身份验证除外。

- 有限管理，其权限等同于支持管理员。

在合作伙伴将这些角色分配给用户之前，必须先将合作伙伴作为委派管理员添加到你的帐户中。 此过程由授权合作伙伴发起。 合作伙伴将向你发送一封电子邮件，询问你是否要授予其作为委派管理员的权限。有关说明，请参阅[授权或删除合作伙伴关系](../misc/add-partner.md)。
  
## <a name="related-content"></a>相关内容

[关于 Microsoft 365 管理员角色](about-admin-roles.md)（文章）\
[分配管理员角色](assign-admin-roles.md)（文章）\
[Microsoft 365 管理中心中的活动报告](../activity-reports/activity-reports.md)（文章）