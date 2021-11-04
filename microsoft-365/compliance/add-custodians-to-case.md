---
title: 将保管人添加到Advanced eDiscovery案例
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解如何在工作流中使用内置保管人Advanced eDiscovery协调工作流，并识别相关数据源。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d195690493e320407f7c9b1ca0d45da7c78955a7
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753546"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>将保管人添加到Advanced eDiscovery案例

使用托管服务中的内置保管人管理工具Advanced eDiscovery您的工作流，以管理保管人并确定与案例关联的相关、监管数据源。 当您添加保管人时，系统可自动识别并保留其邮箱Exchange帐户OneDrive for Business保留。 在调查的发现过程中，您还可以确定保管人访问或 (的其他数据源，如Teams) 访问或参与的邮箱、网站或网站。 在这种情况下，可以使用保管人管理工具将那些数据源关联为特定保管人。 将保管人添加到案例并将其他数据源与它们关联后，您可以快速保留数据并搜索监管数据。

可以在以下四个步骤中添加和管理Advanced eDiscovery保管人：

1. 确定保管人。

2. 选择保管人数据位置。

3. 配置保留设置。

4. 查看保管人并完成此过程。

   [!["源"选项卡Advanced eDiscovery大小写。 ](../media/AeD-Sources-Tab.png) ](../media/AeD-Sources-Tab.png#lightbox)

## <a name="make-sure-you-have-the-necessary-permissions"></a>确保您具有必要的权限

若要向案例添加保管人，您必须是电子数据展示管理员角色组的成员。 这为您提供了向案例添加保管人并保留现有数据源的必要权限。 有关详细信息，请参阅[分配电子数据展示权限](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions)。

## <a name="step-1-identify-custodians"></a>步骤 1：标识保管人

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然后使用已分配有相应电子数据展示权限的用户帐户登录。

2. 在邮件的左侧导航窗格中，Microsoft 365 合规中心"显示所有  >  **电子** 数据展示  >  Advanced eDiscovery，然后选择"事例 <a href="https://go.microsoft.com/fwlink/p/?linkid=2173764" target="_blank">**"** 选项卡</a>。

3. 选择要将保管人添加到的案例。

4. 选择"**数据源"** 选项卡，然后选择"**添加数据源**  >  **""添加新保管人"。**

5. 通过键入人员姓名或别名的第一部分，将组织中一个或多个用户作为保管人添加到案例。 找到正确的人员后，选择其姓名以将其添加到列表中。

## <a name="step-2-choose-custodian-data-locations"></a>步骤 2：选择保管人数据位置

选择保管人后，系统会自动尝试标识和验证这些用户及其数据源。 将保管人添加到列表中后，该工具将自动包含每个保管人的主OneDrive帐户。 在向案例添加保管人时，可以选择不包括这些数据源。

除了保管人邮箱和 OneDrive 帐户，您还可以将其他数据位置关联到保管人，例如 SharePoint 站点或保管人是其中一个成员的 Microsoft 团队。 这允许您保留、收集、分析和查看与案例保管人关联的其他数据源中的内容。

若要取消选择保管人的主OneDrive帐户，

1. 展开保管人以查看已自动与每个保管人关联的主数据位置。

2. 选择 **"****邮箱或** OneDrive"旁边的"清除"，将保管人邮箱或OneDrive帐户作为此保管人的数据位置相关联。

   ![配置要与保管人关联的位置。](../media/ConfigureCustodianLocations.png)

若要将其他邮箱、站点、Teams或Yammer组关联到特定保管人：

1. 展开保管人以显示以下服务以将数据位置与保管人关联。 单击 **服务** 旁边的"编辑"以添加数据位置。

   - **Exchange：** 用于将其他邮箱与保管人关联。 在搜索框中键入用户邮箱或 (的名称或别名) 至少包含三个字符。 选择要分配给保管人的邮箱，然后单击"添加 **"。**

   - **SharePoint：** 用于将SharePoint网站与保管人关联。 在列表中选择网站，或在搜索框中键入 URL 来搜索网站。 选择要分配给保管人的网站，然后单击"添加 **"。**

   - **Teams：** 用于分配Microsoft Teams保管人当前是其中成员的成员。 选择要分配给保管人的团队，然后单击"添加 **"。** 添加团队后，系统会自动标识并找到SharePoint关联的网站和组邮箱，并将其分配给保管人。

   - **Yammer：** 用于分配Yammer保管人当前是其中一个成员的组。 选择要分配给保管人的组，然后单击"添加 **"。** 添加团队后，系统会自动标识并找到SharePoint组关联的网站和组邮箱，并将其分配给保管人。

   > [!NOTE]
   > 可以使用Exchange和SharePoint位置选取器将保管人不是Yammer成员的其他团队或 Yammer (组) 保管人。 为此，您必须添加与每个团队或组关联的邮箱和Yammer网站。

2. 通过展开表中的每个保管人，可以查看分配给每个保管Teams的邮箱、站点、Yammer组总数。 在最终确定每个保管人分配的数据位置后，这些关联将在托管工作流中的收集、处理和审阅阶段Advanced eDiscovery使用。

3. 添加保管人并配置其数据位置后，单击"下一步"转到"**保留设置"** 页。  

## <a name="step-3-configure-hold-settings"></a>步骤 3：配置保留设置

 完成保管人及其数据位置后，可以将部分或所有保管人保留。 当您将保管人保留时，与保管人关联的所有内容位置中的内容将一直保留，直到您删除保留或将保管人从保留中解除。 在某些情况下，你可能希望向事例添加保管人，而不将其置于保留状态。

将保管人和数据源放在保留状态：

1. 在 **"保留设置** "页上，可以通过选中"保留"列下的复选框将保留应用于 **各个保管** 人。

   或者，可以通过选中列顶部的"保留"复选框来保留所有保管人。

2. 验证保管人保留选择，然后单击下一 **步**。

   > [!NOTE]
   > 如果未将保管人保留，则保管人及其关联的数据源将添加到案例，但与该案例关联的保留不会保留这些数据源中的内容。

## <a name="step-4-review-the-custodians-and-complete-the-process"></a>步骤 4：检查保管人并完成此过程

在将保管人实际添加到案例之前，你可以查看保管人列表、分配给保管人的数据位置以及保留设置。

1. 验证并查看与表中的每个保管人关联的所有数据源计数和保留设置。 如有必要，请返回到"识别 **保管人** "或" **保留设置"** 页以做出任何更改。

2. 单击 **"** 提交"将保管人及其数据位置添加到案例，并应用所有托管保留设置。

   新保管人将添加到案例，并显示在" **数据源"** 选项卡上。

   [!["数据源"选项卡上列出的保管人。 ](../media/DataSourcesTab.png) ](../media/DataSourcesTab.png#lightbox)
