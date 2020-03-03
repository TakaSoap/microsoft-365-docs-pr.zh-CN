---
title: Office 365 组过期策略
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解 Office 365 组过期策略。
ms.openlocfilehash: c4c2f7b98247cc81b3fadc561f92084f9bd39c96
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352583"
---
# <a name="office-365-group-expiration-policy"></a>Office 365 组过期策略

随着 Office 365 组的使用提高，管理员和用户需要一种方法来清除未使用的组。 过期策略可帮助从系统中删除非活动组并使其更整洁。

当一个组过期时，它的所有关联服务（邮箱、Planner、SharePoint 网站等）也将被删除。

当组过期时，它会被 "软删除"，这意味着它仍可恢复最长30天。

管理员可以指定过期时间和任何非活动组，达到该时间段结束时间后，不会被更新。 过期时间是在创建组时开始，或在上次续订日期时开始。 在过期之前，将自动向组所有者发送一封电子邮件，以允许他们为其他过期间隔续订组。 团队用户将在团队中看到永久通知。

正在使用的组将自动续订。 以下任一操作将自动续订组：
- SharePoint-查看、编辑、下载、移动、共享或上传文件。
- Outlook-加入组、读取或写入组中的组邮件，以及类似于邮件（Outlook 网页网站）。
- 团队-访问团队频道。

> [!IMPORTANT]
> 当您更改过期策略时，服务将重新计算每个组的到期日期。 它始终从创建组的日期开始计数，然后应用新的过期策略。

请务必了解默认情况下禁用过期功能。 如果管理员想要使用它，则必须为其租户启用它。

> [!NOTE]
> 配置和使用 Office 365 组的过期策略要求您拥有（但不一定）为应用了过期策略的所有组的成员分配 Azure AD Premium 许可证。 有关详细信息，请参阅[Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)入门。

## <a name="who-can-configure-and-use-the-office-365-groups-expiration-policy"></a>哪些用户可以配置和使用 Office 365 组过期策略？

|Role|可以执行的操作|
|---------|---------|
|Office 365 全局管理员（在 Azure、公司管理员）、用户管理员|创建、读取、更新或删除 Office 365 组过期策略设置。|
|用户|续订或[还原](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)自己拥有的 Office 365 组|

## <a name="how-to-set-the-expiration-policy"></a>如何设置过期策略

如上所述，默认情况下过期功能处于关闭状态。 管理员必须启用过期策略并将其属性设置为生效。 若要启用它，请转到**Azure Active Directory （AAD）** > **组** > **过期**。 你可以在此处设置默认组生存期，并指定你希望第一个和第二个过期通知转到组所有者的提前程度。

组生存期以天为单位指定，可设置为180、365或指定的自定义值。 自定义值必须至少为30天。

如果组没有所有者，则过期电子邮件将转到指定管理员。

您可以设置所有组的策略、仅选定的组或通过选择 "**无**" 将其完全关闭。 请注意，对于不同的组，当前不能有不同的策略。

![Azure Active Directory 中的组过期设置的屏幕截图](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>到期日期如何与保留策略一起使用

如果您在组的安全性和合规性中心中设置了保留策略，则过期策略将与保留策略无缝运行。 当组过期时，组中的 "在邮箱中的对话" 框和组网站中的文件将保留在保留策略中定义的特定天数的保留容器中。 但是，用户在过期后将看不到该组或其内容。

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>组所有者在其组过期时的学习方式和时间

组所有者将仅通过电子邮件通知。 如果组是通过计划者、SharePoint 或任何其他应用程序创建的，则到期通知将始终通过电子邮件发送。 如果组是通过团队创建的，则组所有者将通过 "活动" 部分收到要续订的通知。 如果您的组所有者没有有效的电子邮件地址，则建议您在组中启用过期。

在组过期之前的30天内，组所有者（或为没有所有者的组指定的电子邮件地址）将会收到一封电子邮件，允许他们轻松地续订组。 如果不续订，他们将在到期前15天收到另一封续订电子邮件。 如果他们仍未续订，则会在过期前一天收到一封电子邮件通知。

如果由于某种原因，所有者或管理员在过期之前没有对组进行续订，则管理员仍可以在到期后的30天内还原组。 有关详细信息，请参阅：[还原已删除的 Office 365 组](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)。

## <a name="related-articles"></a>相关文章

[保留策略概述](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[向孤立组分配新的所有者](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[配置 Office 365 组过期](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
