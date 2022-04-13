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
description: 对于托管服务提供商 (使用Microsoft 365 Lighthouse) MSP，了解如何查看租户服务运行状况。
ms.openlocfilehash: 5c15e004108606ce00a90e0fa3d675d00806b430
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64822707"
---
# <a name="view-tenant-service-health"></a>查看租户服务运行状况

可以查看在Microsoft 365 Lighthouse中管理的租户的服务运行状况。 服务运行状况包括多个服务的事件和建议，包括Microsoft Intune、Azure Active Directory (Azure AD) 标识服务和移动设备管理 (MDM) 云服务。 还可以查看有多少托管租户受到事件的影响。 例如，如果其中一个租户遇到问题，则可以检查服务运行状况页，以确定这是正在解决的已知问题，或者最近的更改是否可能影响它们。 这可以节省故障排除和减少支持调用的时间。

如果无法登录 Lighthouse，可以使用[Microsoft 365服务运行状况页](https://status.office365.com/)检查阻止登录到合作伙伴租户的已知问题。 此外，注册以关注 Twitter 上的 [@MSFT365status](https://twitter.com/MSFT365Status) ，查看有关特定服务事件的信息。

## <a name="before-you-begin"></a>准备工作

若要查看服务运行状况，需要在具有以下属性集的合作伙伴租户中Azure AD角色：**microsoft.office365.serviceHealth/allEntities/allTasks**。 有关Azure AD角色的列表，请[参阅Azure AD内置角色](/azure/active-directory/roles/permissions-reference)。

## <a name="view-service-health-status-for-all-tenants"></a>查看所有租户的服务运行状况

1. 在 Lighthouse 的左侧导航窗格中，选择 **服务运行状况**。

2. 在 **服务运行状况** 页上，查看当前服务运行状况，包括：

   - 事件总数
   - 影响任何托管租户的顾问总数
   - 具有活动事件的服务数。

3. 在“ **所有服务** ”选项卡上，按服务查看问题。

4. 在“ **所有问题** ”选项卡上，查看所有当前问题。

## <a name="review-issue-details"></a>查看问题详细信息

1. 在 Lighthouse 的左侧导航窗格中，选择 **服务运行状况**。

2. 在 **服务运行状况** 页上，选择“**所有服务**”或 **“所有问题**”选项卡。

3. 从列表中选择问题。

4. 在“问题详细信息”窗格中，查看详细信息，包括问题类型、受影响的租户、用户影响和问题历史记录。

在 **受影响的租户** 选项卡上，可以将受影响的租户列表导出到逗号分隔值 (.csv) 文件，以便可以与支持团队共享。

## <a name="related-content"></a>相关内容

[如何检查Microsoft 365服务运行状况](/microsoft-365/enterprise/view-service-health) (文章) \
[Microsoft 365 Lighthouse (文章的已知问题](m365-lighthouse-known-issues.md)) 
