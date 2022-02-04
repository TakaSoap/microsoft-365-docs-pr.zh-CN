---
title: Microsoft 365仅云标识
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
  - CSH
ms.custom:
  - Adm_O365
  - O365p_AddUsersWithDirSync
  - O365M_AddUsersWithDirSync
  - O365E_HRCSetupAADConnectAboutLM617031
  - O365E_AddUsersWithDirSync
ms.collection:
  - Ent_O365
  - M365-identity-device-management
search.appverid:
  - MET150
  - MOP150
  - MOE150
  - MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: 介绍如何在订阅使用仅云标识Microsoft 365创建用户和组。
---

# <a name="microsoft-365-cloud-only-identity"></a>Microsoft 365仅云标识

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

如果你已选择仅云标识模型，则对于 Microsoft 365 订阅，你已经拥有一个 Azure Active Directory (Azure AD) 租户来存储所有用户、组和联系人。 在解决方案步骤 [2](protect-your-global-administrator-accounts.md) 和此解决方案的步骤 [3](microsoft-365-secure-sign-in.md) 中为管理员帐户设置保护后，现在可以开始创建组织所需的新帐户和组。

以下是仅云标识的基本组件。
 
![仅云标识的基本组件。](../media/about-microsoft-365-identity/cloud-only-identity.png)

可以通过多种方式对组织中用户及其用户帐户进行分类。 例如，有些是员工，并且具有永久状态。 一些是具有临时状态的供应商、承包商或合作伙伴。 有些用户没有用户帐户，但仍必须被授予访问特定服务和资源的权限以支持交互和协作。 例如：

- 租户帐户表示组织中许可访问云服务的用户。

- 企业到企业 (B2B) 帐户表示组织外部邀请加入协作的用户。

盘点组织中用户的类型。 什么是分组？ 例如，您可以按组织的高级别职能或用途对用户进行分组。

此外，可以将某些云服务与组织外部没有任何用户帐户的用户共享，而且你还需要标识这些用户组。

可以将 Azure AD 中的组用于多个目的，以简化云环境的管理。 例如，使用Azure AD组，您可以：

- 使用基于组的许可，一旦添加为Microsoft 365，就会将用户的许可证自动分配给用户帐户。
- 根据用户帐户属性（如部门名称）将用户帐户动态添加到特定组。
- 自动为用户预配软件即服务 (SaaS) 应用程序，并保护使用多重身份验证 (MFA) 和其他条件访问策略访问这些应用程序。
- 为团队和联机团队网站SharePoint权限和访问权限级别。

## <a name="next-steps-for-cloud-only-identity"></a>仅云标识的以下步骤

- [管理用户帐户](manage-microsoft-365-accounts.md)
- [向用户帐户分配许可证](assign-licenses-to-user-accounts.md)
- [管理组和组成员身份](manage-microsoft-365-groups.md)
- [管理用户帐户密码](manage-microsoft-365-passwords.md)
