---
title: 查看租户服务运行状况
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: 对于托管服务提供商 (使用) 托管服务提供商Microsoft 365 Lighthouse，了解如何查看租户服务运行状况。
ms.openlocfilehash: b7361865e0ad3f070e128207a92669f3515e9969
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2022
ms.locfileid: "62466143"
---
# <a name="view-tenant-service-health"></a>查看租户服务运行状况

> [!NOTE]
> 本文中所述的功能为预览版，可能会更改，并且仅对满足要求的合作伙伴 [可用](m365-lighthouse-requirements.md)。 如果你的组织没有此Microsoft 365 Lighthouse，请参阅[注册Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md)。

可以查看在租户中管理的租户的服务Microsoft 365 Lighthouse。 服务运行状况包括针对多种服务的事件和公告，包括 Microsoft Intune、Azure Active Directory (Azure AD) 标识服务和移动设备管理 (MDM) 云服务。 还可以查看受事件影响的托管租户数。 例如，如果其中一个租户遇到问题，可以检查"服务运行状况"页，以确定该问题是否是正在解决的已知问题，或者最近的更改是否可能会影响它们。 这可以节省故障排除时间并减少支持呼叫。

如果无法登录 Lighthouse，可以使用 Microsoft 365 [服务](https://status.office365.com/)运行状况页来检查阻止你登录到合作伙伴租户的已知问题。 此外，在 Twitter [上@MSFT365status](https://twitter.com/MSFT365Status) 关注事件，以查看有关特定服务事件的信息。

## <a name="before-you-begin"></a>准备工作

若要查看服务运行状况，您需要具有以下属性集的合作伙伴租户中的 Azure AD 角色：**microsoft.office365.serviceHealth/allEntities/allTasks**。 有关角色Azure AD，请参阅Azure AD[内置角色](/azure/active-directory/roles/permissions-reference)。

## <a name="view-service-health-status-for-all-tenants"></a>查看所有租户的服务运行状况

1. In the left navigation pane in Lighthouse， select **Service health**.

2. 在" **服务运行状况"** 页上，查看当前服务运行状况状态，包括：

   -   事件总数
   -   影响任何托管租户的公告总数
   -   活动事件的服务数量。

3. 在" **所有服务"** 选项卡上，按服务查看问题。

4. 在" **所有问题"** 选项卡上，查看所有当前问题。

## <a name="review-issue-details"></a>查看问题详细信息

1. In the left navigation pane in Lighthouse， select **Service health**.

2. 在"**服务运行状况"** 页上，选择"**所有服务或****所有问题"** 选项卡。

3. 从列表中选择问题。

4. 在问题详细信息窗格中，查看详细信息，包括问题类型、受影响的租户、用户影响和问题历史记录。

在 **"受影响的** 租户"选项卡上，可以将受影响的租户列表导出到通用分隔值 (.cvs) 文件，以便你可以与支持团队共享它。

## <a name="related-content"></a>相关内容
[How to check Microsoft 365 service health (](/microsoft-365/enterprise/view-service-health) article) 
