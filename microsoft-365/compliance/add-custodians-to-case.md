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
description: 了解如何在Advanced eDiscovery中使用内置的保管人管理工具来协调工作流并识别相关数据源。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bbd5bb1955fc0c8ee5917a6827b35a6688928571
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64759360"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>将保管人添加到Advanced eDiscovery案例

使用Advanced eDiscovery中的内置保管人管理工具协调工作流，以管理保管人并标识与事例关联的相关保管数据源。 添加保管人时，系统可以自动标识并保留其Exchange邮箱和OneDrive for Business帐户。 在调查发现过程中，还可以识别保管人访问或促成的其他数据源 (，例如邮箱、网站或Teams) 。 在这种情况下，可以使用保管人管理工具将这些数据源关联到特定的保管人。 将保管人添加到案例并将其他数据源与其关联后，可以快速保留数据并搜索保管数据。

可以在Advanced eDiscovery案例中按四个步骤添加和管理保管人：

1. 标识保管人。

2. 选择保管人数据位置。

3. 配置保留设置。

4. 查看保管人并完成此过程。

## <a name="make-sure-you-have-the-necessary-permissions"></a>确保拥有必要的权限

若要将保管人添加到案例中，必须是电子数据展示管理器角色组的成员。 这为你提供了向案例添加保管人并保留保管数据源所需的权限。 有关详细信息，请参阅[分配电子数据展示权限](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions)。

## <a name="step-1-identify-custodians"></a>步骤 1：标识保管人

1. 转到 [https://compliance.microsoft.com](https://compliance.microsoft.com) 并使用已分配了相应电子数据展示权限的用户帐户登录。

2. 在Microsoft 365 合规中心的左侧导航窗格中，选择 **电子数据展示** > **Advanced eDiscovery**，然后选择“[**事例**](https://go.microsoft.com/fwlink/p/?linkid=2173764)”选项卡。

3. 选择要向其添加保管人的情况。

4. 选择 **“数据源”** 选项卡，然后选择 **“添加数据源** > **”新保管人**。

5. 通过键入人员姓名或别名的第一部分，将组织中的一个或多个用户添加为事例的保管人。 找到正确的人员后，选择其姓名以将其添加到列表中。

## <a name="step-2-choose-custodian-data-locations"></a>步骤 2：选择保管人数据位置

选择保管人后，系统会自动尝试识别和验证这些用户及其数据源。 将保管人添加到列表后，该工具会自动包含每个保管人的主要邮箱和OneDrive帐户。 在将保管人添加到案例中时，可以选择不包含这些数据源。

除了保管人的邮箱和OneDrive帐户外，还可以将其他数据位置关联到保管人，例如托管人所属的SharePoint网站或 Microsoft 团队。 这样便可以保留、收集、分析和查看与案件保管人关联的其他数据源中的内容。

若要取消选择保管人的主要邮箱和OneDrive帐户，请执行以下操作：

1. 展开保管人以查看已自动关联到每个保管人的主要数据位置。

2. 选择 **“邮箱**”旁边的 **“清除****”或“OneDrive**”以删除保管人的邮箱或OneDrive帐户，将其关联为此保管人的数据位置。

   ![配置要关联到保管人的位置。](../media/ConfigureCustodianLocations.png)

若要将其他邮箱、网站、Teams或Yammer组关联到特定保管人：

1. 展开保管人以显示以下服务，以便将数据位置与保管人相关联。 单击服务旁边的 **“编辑** ”以添加数据位置。

   - **Exchange**：用于将其他邮箱关联到保管人。 在搜索框中键入名称或别名 (用户邮箱或通讯组) 至少三个字符。 选择要分配给保管人的邮箱，然后单击 **“添加**”。

   - **SharePoint**：用于将SharePoint站点关联到保管人。 在列表中选择网站或通过在搜索框中键入 URL 来搜索网站。 选择要分配给保管人的站点，然后单击 **“添加**”。

   - **Teams**：用于分配保管人当前所属的Microsoft Teams。 选择要分配给保管人的团队，然后单击 **“添加**”。 添加团队后，系统会自动标识并找到与该团队关联的SharePoint网站和组邮箱，并将其分配给保管人。

   - **Yammer**：用于分配保管人当前所属的Yammer组。 选择要分配给保管人的组，然后单击 **“添加**”。 添加团队后，系统会自动标识并找到与该组关联的SharePoint网站和组邮箱，并将其分配给保管人。

   > [!NOTE]
   > 可以使用 **Exchange** 和 **SharePoint** 位置选取器将组织中的任何邮箱或网站关联到保管人。 ，这包括关联托管人不是其成员的 Microsoft 团队或Yammer组的邮箱和网站。 为此，必须添加与每个团队或Yammer组关联的邮箱和网站。

2. 可以通过扩展表中的每个保管人来查看分配给每个保管人邮箱、网站、Teams和Yammer组的总数。 完成为每个保管人分配的数据位置后，这些关联将在Advanced eDiscovery工作流的收集、处理和审阅阶段内进行维护和使用。

3. 添加保管人并配置其数据位置后，单击 **“下一步** ”转到“ **保留设置”** 页。  

## <a name="step-3-configure-hold-settings"></a>步骤 3：配置保留设置

 完成保管人及其数据位置后，可以将部分或全部保管人置于保留状态。 将保管人置于保留状态时，将保留与保管人关联的所有内容位置中的所有内容，直到从保留中删除保管人或释放保管人。 在某些情况下，你可能希望将保管人添加到案例中，而不将其搁置。

将保管人和数据源置于保留状态：

1. 在 **“保留设置”** 页上，可以通过选中 **“保留** ”列下的复选框，对单个保管人应用保留。

   或者，可以通过选择列顶部的 **“保留** ”复选框，将所有保管人置于保留状态。

2. 验证保管人保存所选内容，然后单击 **“下一步**”。

   > [!NOTE]
   > 如果不保留保管人，保管人及其关联的数据源将添加到案例中，但这些数据源中的内容不会被与案件关联的保留保留保留。

## <a name="step-4-review-the-custodians-and-complete-the-process"></a>步骤 4：查看保管人并完成此过程

在实际将保管人添加到案例之前，可以查看保管人列表、分配给他们的数据位置以及保留设置。

1. 验证并查看与表中的每个保管人关联的所有数据源计数和保留设置。 如有必要，请返回到 **“标识保管人** ”或 **“保留设置”** 页进行任何更改。

2. 单击 **“提交** ”将保管人及其数据位置添加到案例中，并应用所有保管保留设置。

   新保管人将添加到事例中，并显示在 **“数据源** ”选项卡上。

   [![“数据源”选项卡上列出的保管人。](../media/DataSourcesTab.png) ](../media/DataSourcesTab.png#lightbox)
