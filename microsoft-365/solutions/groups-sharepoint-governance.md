---
title: Microsoft 365 组和 SharePoint 之间的设置交互
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 了解 Microsoft 365 组和 SharePoint 之间的设置交互
ms.openlocfilehash: a00e863fead8e74cf0f169471ebb36f9539ed103
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613486"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Microsoft 365 组和 SharePoint 之间的设置交互

Microsoft 365 中的 Microsoft 365 组和 SharePoint 的一些设置，尤其与共享和组以及工作组网站创建相关，相互重叠。 本文提供了这些交互的说明以及有关如何使用这些设置的最佳实践。

![SharePoint、Yammer 和组功能的维恩图](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>SharePoint 设置对 Microsoft 365 组的影响

|SharePoint 设置|说明|对 Microsoft 365 组的影响|建议|
|:-----------------|:----------|:-----------------------------|:-------------|
|组织和网站的外部共享|确定是否可以与组织外部的人员共享网站、文件和文件夹。|如果 SharePoint 和组设置不匹配，可能会阻止组中的来宾访问网站，或外部访问可能在网站（而不是组）中可用。|更改共享设置时，请检查组连接的团队网站的组设置和 SharePoint 网站设置。<br><br>请参阅 [在网站中与来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site)。|
|域允许/阻止|允许或禁止与指定域共享内容。|组不识别 SharePoint 允许或阻止列表。 来自 SharePoint 中不允许的域的用户可以通过组获取对 SharePoint 的访问权限。|同时管理 Azure AD 和 SharePoint 的域允许/阻止列表。 创建用于允许和阻止域的组织范围内管理流程。<br><br>请参阅 [SharePoint 域设置](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) 和 [Azure AD 域设置](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
|仅允许特定安全组中的用户在外部共享|指定可在外部共享网站、文件夹和文件的安全组。|此设置不会影响在外部共享组的组所有者。 组来宾有权访问关联的 SharePoint 网站。||
|SharePoint 网站共享设置|确定谁可以直接在组成员身份之外共享网站。 这是由组或网站所有者配置的。|此设置不会直接影响组，但可以允许将用户添加到网站，而无法访问其他组资源|请考虑使用此设置来直接限制网站共享，并通过组管理网站访问权限。|
|允许用户从 SharePoint 起始页和 OneDrive 创建网站|指定用户是否可以创建新的 SharePoint 网站。|如果关闭此设置，则用户仍可以通过创建组来创建连接到组的团队网站。||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>SharePoint 上的 Microsoft 365 组设置的影响

|Microsoft 365 组设置|说明|对 SharePoint 的影响|建议|
|:---------------------------|:----------|:-------------------|:-------------|
|命名策略|指定组名称前缀和后缀以及阻止的组创建的词|为用户创建与组连接的团队网站，但不使用与其他模板的通信网站或网站来强制执行策略。|如果需要，请为通信网站创建单独的命名指南。|
|组来宾访问|指定是否可以将组织外部的人员添加到组中。|如果 SharePoint 和组设置不匹配，可能会阻止组中的来宾访问网站，或外部访问可能在网站（而不是组）中可用。|更改共享设置时，请检查组连接的团队网站的组设置和 SharePoint 网站设置。<br><br>请参阅 [在网站中与来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site)|
|组创建（按安全组）|组仅可由特定安全组的成员创建。|不是安全组成员的用户将不能创建与组连接的团队网站。|请确保请求组的过程包含有关请求网站的说明。|
|组过期策略|指定将自动删除未主动使用的组的时间段。|删除组后，相关联的 SharePoint 网站也会被删除。 保留策略保护的内容将保留。|使用过期策略以避免未使用的组和站点的数量剧增。|

## <a name="related-topics"></a>相关主题

[协作治理规划分步](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[创建协作管理计划](collaboration-governance-first.md)

[与组织外部的人员进行协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[在 SharePoint 中管理网站创建](https://docs.microsoft.com/sharepoint/manage-site-creation)