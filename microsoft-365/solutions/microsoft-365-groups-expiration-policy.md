---
title: Microsoft 365 组过期策略
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
description: 了解 Microsoft 365 组过期策略。
ms.openlocfilehash: 65a746751cd523a5dadce3eca573e6a9bfce0166
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052298"
---
# <a name="microsoft-365-group-expiration-policy"></a>Microsoft 365 组过期策略

随着 Microsoft 365 组和 Microsoft Teams 的使用不断增加，管理员和用户需要一种方法来清理未使用的组和团队。 Microsoft 365 组过期策略可帮助从系统中删除非活动组，使情况更简洁。

当组过期时，还将删除 (、Planner、SharePoint 网站、团队等) 服务。

当组过期时，它将"软删除"，这意味着它仍然可以恢复最多 30 天。

管理员可以指定过期期限，达到该期限末尾且未续订的任何非活动组都将被删除。  (包括存档的 teams.) 到期日期从组创建时开始，或自上次续订日期开始。 组所有者将在过期前自动收到一封电子邮件，允许他们续订组的另一个过期间隔。 Teams 用户将在 Teams 中看到永久性通知。

主动使用的组将自动续订。 以下任一操作将自动续订组：
- SharePoint - 查看、编辑、下载、移动、共享或上载文件。  (查看 SharePoint 页面不作为自动续订的操作。) 
- Outlook - 加入组、从组读取或写入组邮件，就像 Outlook 网页 (邮件) 。
- Teams - 访问团队频道。

请注意，将触发自动组续订的唯一 Yammer 活动是，将文档上传到社区内的 SharePoint。

> [!IMPORTANT]
> 更改过期策略时，该服务将重新计算每个组的到期日期。 它始终从组创建日期开始计数，然后应用新的过期策略。

了解默认情况下关闭过期很重要。 如果想使用，管理员必须针对其组织启用它。

> [!NOTE]
> 配置和使用 Microsoft 365 组的过期策略需要你拥有（但不一定）为应用过期策略的所有组的成员分配 Azure AD Premium 许可证。 有关详细信息，请参阅 [Azure Active Directory Premium 入门](/azure/active-directory/active-directory-get-started-premium)。

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>谁可以配置和使用 Microsoft 365 组过期策略？

|Role|他们可以执行哪些功能|
|---------|---------|
|Azure 中的 Office 365 全局管理员 (，公司管理员) 用户管理员|创建、读取、更新或删除 Microsoft 365 组过期策略设置。|
|User|续订或 [还原](/azure/active-directory/users-groups-roles/groups-restore-deleted) 他们拥有的 Microsoft 365 组|

## <a name="how-to-set-the-expiration-policy"></a>如何设置过期策略

如上所述，过期默认为关闭状态。 管理员必须启用过期策略并设置其属性才能生效。 若要启用它，请转到 **Azure Active Directory**  >  **组**  >  **过期**。 你可以在此处设置默认组生存期，并指定希望第一个和第二个过期通知提前多远转到组所有者。

组生存期以天指定，可以设置为 180，365 或您指定的自定义值。 自定义值必须至少为 30 天。

如果组没有所有者，过期电子邮件将转到指定的管理员。

你可以为所有组（仅选定组）设置策略，或者通过选择"无"将其完全 **关闭**。 请注意，目前不能为不同的组设置不同的策略。

![Azure Active Directory 中的组过期设置的屏幕截图](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>到期日期如何与保留策略一起运行

如果在安全与合规中心为组设置了保留策略，则过期策略可与保留策略无缝协作。 当组过期时，该组的邮箱对话和组网站中的文件将在保留策略中定义的特定天数内保留在保留容器中。 但是，在过期后，用户将不会看到组或其内容。

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>组所有者如何以及何时了解其组是否即将过期

组所有者将仅通过电子邮件收到通知。 如果组是通过 Planner、SharePoint 或其他任何应用创建的，过期通知将始终通过电子邮件发送。 如果组是通过 Teams 创建的，组所有者将收到通过活动部分续订的通知。 如果你的组所有者没有有效的电子邮件地址，建议不要对组启用过期。

在组过期前 30 天， (或你为没有所有者) 的组指定的电子邮件地址将收到一封电子邮件，允许他们轻松续订组。 如果他们没有续订，将在过期前 15 天收到另一封续订电子邮件。 如果他们仍未续订，将在过期前一天收到一封多封电子邮件通知。

如果出于某种原因，没有任何所有者或管理员在组过期前续订组，则管理员仍然可以在过期后最多 30 天内还原组。 有关详细信息，请参阅： [还原已删除的 Microsoft 365 组](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)。

## <a name="archiving-group-contents"></a>存档组内容

如果您有一个不再计划使用的组，但希望保留其内容，请参阅存档组、团队和 [Yammer，](end-life-cycle-groups-teams-sites-yammer.md) 了解如何从不同组服务导出信息。

## <a name="related-topics"></a>相关主题

[协作治理规划分步规划](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[创建协作管理计划](collaboration-governance-first.md)

[保留策略概述](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[向孤立组分配新的所有者](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[配置 Microsoft 365 组过期](/azure/active-directory/active-directory-groups-lifecycle-azure-portal)