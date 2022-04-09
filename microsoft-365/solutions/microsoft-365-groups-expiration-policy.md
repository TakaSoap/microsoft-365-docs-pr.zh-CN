---
title: Microsoft 365组过期策略
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
recommendations: false
description: 了解Microsoft 365组过期策略。
ms.openlocfilehash: 9287d61b95d635eccbbef64d307c0aa0e3d12357
ms.sourcegitcommit: 46e796c6b76a01516c48977335bbf5076ca74a06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2022
ms.locfileid: "64738568"
---
# <a name="microsoft-365-group-expiration-policy"></a>Microsoft 365组过期策略

随着 Microsoft 365 组和 Microsoft Teams 使用量的增加，管理员和用户需要一种方法来清理未使用的组和团队。 Microsoft 365 组过期策略可帮助从系统中删除非活动组，并使内容更简洁。

当组过期时，还会删除其所有关联的服务（邮箱、Planner、SharePoint 网站、团队等）。

当组过期时，它将“软删除”，这意味着它仍可恢复长达 30 天。

管理员可以指定过期期，任何到达该期限结束且未续订的非活动组都将被删除。  (这包括已存档的 teams.) 在创建组时或上次续订的日期开始过期时间。 组所有者将在过期前自动发送一封电子邮件，允许他们续订组以获得另一个到期间隔。 Teams 用户将在 Teams 中看到永久性通知。

主动使用的组将自动续订。 以下任何操作都将自动重新创建组：
- SharePoint - 查看、编辑、下载、移动、共享或上传文件。 （查看SharePoint页面不作为自动续订的操作。）
- Outlook - 加入或编辑组、从组读取或写入组消息，以及像消息 (Outlook 网页版) 一样。
- Teams - 访问团队频道。
- Yammer - 查看Yammer社区中的帖子或Outlook中的交互式电子邮件。
- 窗体 - 查看、创建或编辑表单，或提交对窗体的响应。 

请注意，将触发自动组续订的唯一Yammer活动是将文档上传到社区内SharePoint。

> [!IMPORTANT]
> 更改过期策略时，服务会重新计算每个组的过期日期。 它始终从创建组的日期开始计数，然后应用新的过期策略。

请务必知道，默认情况下会关闭过期。 如果管理员想要使用它，则必须为其组织启用它。

> [!NOTE]
> 为Microsoft 365组配置和使用过期策略需要你拥有但不一定为应用过期策略的所有组的成员分配Azure AD Premium许可证。 有关详细信息，请参阅[Azure Active Directory Premium入门](/azure/active-directory/active-directory-get-started-premium)。

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Who可以配置和使用Microsoft 365组过期策略？

|Role|可执行的操作|
|---------|---------|
|Office 365 Azure 中的全局管理员 (，公司管理员) 、用户管理员|创建、读取、更新或删除Microsoft 365组过期策略设置。|
|用户|续订或[还原](/azure/active-directory/users-groups-roles/groups-restore-deleted)他们拥有的Microsoft 365组|

## <a name="how-to-set-the-expiration-policy"></a>如何设置过期策略

如上所述，默认情况下会关闭过期。 管理员必须启用过期策略并设置要生效的属性。 若要启用它，请转到 **Azure Active Directory** >  **GroupsExpiration** > 。 可在此处设置默认组生存期，并指定希望第一个和第二个过期通知提前到组所有者的日期。

组生存期在几天内指定，可以设置为 180、365 或指定的自定义值。 自定义值必须至少为 30 天。

如果组没有所有者，则过期电子邮件将转到指定的管理员。

可以为所有组设置策略，仅选定组 (最多 500) ，或者通过选择 **“无**”完全关闭该策略。 请注意，目前不能为不同的组使用不同的策略。

![Azure Active Directory中组过期设置的屏幕截图。](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>到期日期如何与保留策略一起运行

如果在安全与合规中心为组设置了保留策略，则过期策略可与保留策略无缝协作。 当组过期时，该组的邮箱对话和组网站中的文件将在保留策略中定义的特定天数内保留在保留容器中。 但是，在过期后，用户将不会看到组或其内容。

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>组所有者如何以及何时了解其组是否即将过期

组所有者将仅通过电子邮件收到通知。 如果组是通过 Planner、SharePoint或任何其他应用创建的，过期通知将始终通过电子邮件发送。 如果组是通过 Teams 创建的，组所有者将收到通过活动部分续订的通知。 如果组所有者没有有效的电子邮件地址，则不建议在组上启用过期。

组过期前 30 天，组所有者 (或为没有所有者) 的组指定的电子邮件地址将收到一封电子邮件，允许他们轻松续订组。 如果他们未续订，则会在到期前 15 天收到另一封续订电子邮件。 如果他们仍未续订，则会在到期前一天再收到一封电子邮件通知。

如果出于某种原因，没有任何所有者或管理员在组过期前续订组，则管理员仍然可以在过期后最多 30 天内还原组。 有关详细信息，请参阅：[还原已删除的Microsoft 365组](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)。

## <a name="archiving-group-contents"></a>存档组内容

如果你有一个不再计划使用的组，但要保留其内容，请参阅[存档组、团队和Yammer](end-life-cycle-groups-teams-sites-yammer.md)，了解如何从不同的组服务导出信息。

## <a name="related-topics"></a>相关主题

[协作治理规划建议](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[创建协作治理计划](collaboration-governance-first.md)

[保留策略概述](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[向孤立组分配新的所有者](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[配置Microsoft 365组过期](/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
