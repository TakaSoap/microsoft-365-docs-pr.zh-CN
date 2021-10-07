---
title: 设置组Microsoft 365组之间的交互SharePoint
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: 了解组和组之间的Microsoft 365交互SharePoint
ms.openlocfilehash: 2978e2f0a450c72d7b4abf71edb208a5d9f364c6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208885"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>设置组Microsoft 365组之间的交互SharePoint

网站中Microsoft 365组SharePoint的Microsoft 365设置（尤其是与共享和组和团队网站创建相关）相互重叠。 本文提供了这些交互的说明，以及如何使用这些设置的最佳实践。

![维恩图SharePoint、Yammer和组功能。](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>设置对SharePoint组Microsoft 365效果

|SharePoint设置|说明|对组Microsoft 365影响|建议|
|:-----------------|:----------|:-----------------------------|:-------------|
|组织和网站的外部共享|确定是否可以与组织外部人员共享网站、文件和文件夹。|如果SharePoint和组设置不匹配，则可能会阻止该组中的来宾访问网站，或者外部访问可能在网站中可用，但组中不可用。|更改共享设置时，请检查组设置SharePoint组连接的团队网站的网站设置。<br><br>请参阅 [在网站中与来宾协作](./collaborate-in-site.md)。|
|域允许/阻止|允许或阻止与指定域共享内容。|组无法识别SharePoint列表或阻止列表。 域中的用户不允许SharePoint组SharePoint访问邮件。|管理 Azure AD 的域允许/阻止列表，SharePoint一起。 创建组织范围的管理流程以允许和阻止域。<br><br>请参阅[SharePoint域设置和](/sharepoint/restricted-domains-sharing)Azure [AD 域设置](/azure/active-directory/b2b/allow-deny-list)|
|仅允许特定安全组中的用户在外部共享|指定可在外部共享网站、文件夹和文件的安全组。|此设置不会影响组所有者在外部共享组。 组来宾有权访问关联的SharePoint网站。||
|SharePoint网站共享设置|确定谁可以直接在组成员身份之外共享网站。 这由组或网站所有者配置。|此设置不会直接影响组，但可以允许用户添加到网站，并且无法访问其他组资源|请考虑使用此设置来限制直接共享网站并通过组管理网站访问。|
|让用户从网站起始页SharePoint网站OneDrive|指定用户能否创建新的SharePoint网站。|如果关闭此设置，用户仍可通过创建组来创建与组连接的团队网站。||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>组设置Microsoft 365对组SharePoint

|Microsoft 365组设置|说明|对SharePoint|建议|
|:---------------------------|:----------|:-------------------|:-------------|
|命名策略|为组创建指定组名称前缀和后缀以及阻止的词语|为创建组连接的工作组网站的用户强制执行策略，但不强制应用通信网站或具有其他模板的网站。|根据需要为通信网站创建单独的命名指南。|
|组来宾访问|指定能否将组织外部人员添加到组。|如果SharePoint和组设置不匹配，则可能会阻止该组中的来宾访问网站，或者外部访问可能在网站中可用，但组中不可用。|更改共享设置时，请检查组设置SharePoint组连接的团队网站的网站设置。<br><br>请参阅 [在网站中与来宾协作](./collaborate-in-site.md)|
|按安全组创建组|组只能由特定安全组的成员创建。|不是安全组的成员的用户将无法创建与组连接的团队网站。|请确保请求组的过程包含有关请求网站的说明。|
|组过期策略|指定一个时间段，在此时间段之后，将自动删除未主动使用的组。|删除组时，还将删除SharePoint关联的网站。 保留受保留策略保护的内容。|使用过期策略以避免出现未使用的组和网站。|

## <a name="related-topics"></a>相关主题

[协作治理规划分步规划](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[创建协作管理计划](collaboration-governance-first.md)

[与组织外部人员进行协作](./collaborate-with-people-outside-your-organization.md)

[管理 SharePoint 中的网站创建](/sharepoint/manage-site-creation)