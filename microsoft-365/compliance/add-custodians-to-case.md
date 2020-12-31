---
title: 向高级电子数据展示案例添加保管人
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解如何使用高级电子数据展示中的内置保管人管理工具来协调工作流，并识别案例的相关数据源。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740339"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>向高级电子数据展示案例添加保管人

使用高级电子数据展示中的内置保管人管理工具，协调工作流，以管理保管人并识别与案例关联的相关、监管数据源。 添加保管人时，系统可自动识别并保留其 Exchange 邮箱和 OneDrive for Business 帐户。 在调查的发现过程中，您还可以确定保管人访问或参与 (的其他数据源，例如) 邮箱、网站或 Teams 网站。 在这种情况下，可以使用保管人管理工具将这些数据源关联为特定保管人。 将保管人添加到案例并将其他数据源与案例关联后，您可以快速保留数据并搜索监管数据。

可以通过四个步骤在高级电子数据展示事例中添加和管理保管人：

1. 确定保管人。

2. 选择保管人数据位置。

3. 配置保留设置。

4. 查看保管人并完成该过程。

   [![高级电子数据展示案例中的"源"选项卡 ](../media/AeD-Sources-Tab.png)](../media/AeD-Sources-Tab.png#lightbox)

## <a name="make-sure-you-have-the-necessary-permissions"></a>确保你拥有必要的权限

若要向案例添加保管人，您必须是电子数据展示管理员角色组的成员。 这为您提供了向案例添加保管人并保留监管数据源的必要权限。 有关详细信息，请参阅[分配电子数据展示权限](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions)。

## <a name="step-1-identify-custodians"></a>步骤 1：确定保管人

1. 转到已分配有相应电子数据展示权限的用户帐户 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并登录。

2. 在 Microsoft 365 合规中心的左侧导航窗格中，单击"全部显示"，然后单击"电子数据展示>**高级"**。

3. 在 **"高级电子数据** 展示"页上，单击"事例"选项卡，然后选择要添加保管人的情况。

4. 单击 **"数据源"** 选项卡，然后单击 **"添加数据源**  >  **添加新保管人"。**

5. 通过键入人员姓名或别名的第一部分，将组织中一个或多个用户添加为案例保管人。 找到正确的人员后，选择他们的姓名以将其添加到列表中。

## <a name="step-2-choose-custodian-data-locations"></a>步骤 2：选择保管人数据位置

选择保管人后，系统将自动尝试标识和验证这些用户及其数据源。 将保管人添加到列表中后，该工具将自动包含每个保管人的主邮箱和 OneDrive 帐户。 在向案例添加保管人时，可以选择不包括这些数据源。

除了保管人邮箱和 OneDrive 帐户之外，还可以将其他数据位置关联到保管人，如保管人是保管人所参与的 SharePoint 网站或 Microsoft 团队。 这允许您保留、收集、分析和查看与案例保管人关联的其他数据源中的内容。

若要取消选择保管人的主邮箱和 OneDrive 帐户：

1. 展开保管人以查看已自动与每个保管人关联的主数据位置。

2. Select **Clear** next to **Mailbox** or **OneDrive** to remove a custodian's mailbox or OneDrive account from being associated as a data location for this custodian.

   ![将位置配置为与保管人关联](../media/ConfigureCustodianLocations.png)

若要将其他邮箱、网站、Teams 或 Yammer 组关联到特定保管人：

1. 展开保管人以显示以下服务，以将数据位置与保管人关联。 单击 **服务** 旁边的"编辑"可添加数据位置。

   - **Exchange：** 用于将其他邮箱与保管人关联。 在搜索框中键入用户邮箱或 (组) 至少包含三个字符的名称或别名。 选择要分配给保管人的邮箱，然后单击"添加 **"。**

   - **SharePoint：** 用于将 SharePoint 网站与保管人关联。 在列表中选择网站，或在搜索框中键入 URL 来搜索网站。 选择要分配给保管人的网站，然后单击"添加 **"。**

   - **Teams：** 用于分配保管人当前是 Microsoft Teams 的成员。 选择要分配给保管人的团队，然后单击"添加 **"。** 添加团队后，系统会自动标识并找到与该团队关联的 SharePoint 网站和组邮箱，并将其分配给保管人。

   - **Yammer：** 用于分配保管人当前是其中一个成员的 Yammer 组。 选择要分配给保管人组，然后单击"添加 **"。** 添加团队后，系统会自动标识并找到与该组关联的 SharePoint 网站和组邮箱，并将其分配给保管人。

   > [!NOTE]
   > 您可以使用 **Exchange** 和 **SharePoint** 位置选取器将其他团队或 Yammer 组 (保管人不是保管人) 保管人。 为此，您必须添加与每个团队或 Yammer 组关联的邮箱和网站。

2. 通过展开表中的每个保管人，可以查看分配给每个保管人的邮箱、网站、Teams 和 Yammer 组总数。 完成为每个保管人分配的数据位置后，将在高级电子数据展示工作流中的收集、处理和审阅阶段维护和使用这些关联。

3. 添加保管人并配置其数据位置后，单击" **下** 一步"转到 **"保留设置"** 页。  

## <a name="step-3-configure-hold-settings"></a>步骤 3：配置保留设置

 完成保管人及其数据位置后，可以将部分或所有保管人放在保留状态。 当您将保管人保留时，与保管人关联的所有内容位置中的内容将一直保留，直到您删除保留或解除保管人。 在某些情况下，你可能希望向事例添加保管人，而不将其置于保留状态。

将保管人和数据源放在保留状态：

1. 在 **"保留设置** "页上，可以通过选中"保留"列下的复选框将保留应用于 **各个保管** 人。

   或者，可以通过选中列顶部的"保留"复选框来保留所有保管人。

2. 验证保管人保留选择，然后单击"下 **一步"。**

   > [!NOTE]
   > 如果未对保管人进行保留，则保管人及其关联的数据源将添加到案例，但这些数据源中的内容不会由与案例关联的保留保留。

## <a name="step-4-review-the-custodians-and-complete-the-process"></a>步骤 4：查看保管人并完成此过程

在将保管人实际添加到案例之前，你可以查看保管人列表、分配给保管人的数据位置以及保留设置。

1. 验证并查看与表中每个保管人关联的所有数据源计数和保留设置。 如有必要，请返回到" **标识保管人** "或" **保留** 设置"页进行任何更改。

2. 单击 **"** 提交"将保管人及其数据位置添加到案例，并应用所有监管保留设置。

   新保管人将添加到案例，并显示在"数据源 **"** 选项卡上。

   [!["数据源"选项卡上列出的保管人 ](../media/DataSourcesTab.png)](../media/DataSourcesTab.png#lightbox)
