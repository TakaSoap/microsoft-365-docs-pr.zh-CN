---
title: Microsoft 365 组、团队和 SharePoint 之间的设置交互
ms.reviewer: ''
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
description: 了解 Microsoft 365 组、团队和 SharePoint 之间的设置交互
ms.openlocfilehash: 3a6d4e057f88410a8808ea133bf7e579d0041228
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377541"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Microsoft 365 组、团队和 SharePoint 之间的设置交互

Microsoft 365 中的 Microsoft 365 组、Microsoft 团队和 SharePoint 的一些设置，尤其与共享和组/团队以及 SharePoint 网站创建相关，彼此重叠。 本文提供了这些交互的说明以及有关如何使用这些设置的最佳实践。

![SharePoint、团队和组功能的维恩图](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>SharePoint 设置对组和团队的影响

|SharePoint 设置|说明|对 Microsoft 365 组和团队的影响|建议|
|:-----------------|:----------|:---------------------------------------|:-------------|
|组织和网站的外部共享|确定是否可以与组织外部的人员共享网站、文件和文件夹。|如果 SharePoint、组和团队设置不匹配，可能会阻止团队中的来宾访问网站，或可能会发生意外的外部访问。|更改共享设置时，请选中组连接的团队网站的 "组设置"、"团队设置" 和 "SharePoint 网站设置"。<br><br> 请参阅 [在团队中与来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)|
|域允许/阻止|允许或禁止与指定域共享内容。|组和团队不识别 SharePoint 允许或阻止列表。 来自 SharePoint 中不允许的域的用户可以通过团队获取对 SharePoint 网站或内容的访问权限。|同时管理 Azure AD 和 SharePoint 的域允许/阻止列表。 创建用于允许和阻止域的组织范围内管理流程。<br><br>请参阅 [SharePoint 域设置](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) 和 [Azure AD 域设置](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
|仅允许特定安全组中的用户在外部共享|指定可在外部共享 SharePoint 网站、文件夹和文件的安全组。|此设置不会阻止团队所有者在外部共享团队。 团队来宾有权访问关联的 SharePoint 网站。||
|SharePoint 网站共享设置|确定可以直接在团队成员资格之外共享网站的人员。 这由团队或网站所有者配置。|此设置不会直接影响团队，但可以允许将用户添加到网站，而不能访问团队本身或其他团队资源|请考虑使用此设置来直接限制网站共享，并通过团队管理网站访问权限。|
|允许用户从 SharePoint 起始页和 OneDrive 创建网站|指定用户是否可以创建新的 SharePoint 网站。|如果关闭此设置，则用户仍可以通过创建团队来创建连接到组的团队网站。||

## <a name="the-effects-of-groups-settings-on-teams"></a>组设置对团队的影响

|Microsoft 365 组设置|说明|对团队的影响|建议|
|:---------------------------|:----------|:--------------|:-------------|
|命名策略|指定组名称前缀和后缀以及阻止的组创建的词|为创建团队的用户强制实施策略。||
|组来宾访问|指定是否可以将组织外部的人员添加到组中。|如果 "组" 或 "团队" 来宾共享设置处于关闭状态，则无法与来宾共享团队。|更改来宾共享设置时，请检查团队、组和与团队关联的 SharePoint 网站的设置。<br><br> 请参阅 [在团队中与来宾协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)|
|组创建（按安全组）|组仅可由特定安全组的成员创建。|不是安全组成员的用户将不能创建团队。|请确保请求组的过程包含有关请求团队或 SharePoint 网站的说明。|
|组过期策略|指定将自动删除未主动使用的组的时间段。|删除组后，团队和关联的 SharePoint 网站也将被删除。 保留策略保护的内容将保留。|使用过期策略以避免未使用的团队、组和网站的数量剧增。|

## <a name="related-topics"></a>相关主题

[与组织外部的人员进行协作](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[管理 SharePoint 中的网站创建](https://docs.microsoft.com/sharepoint/manage-site-creation)
