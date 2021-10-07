---
title: 管理案例Advanced eDiscovery保管人
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
description: 了解如何查看详细信息、编辑和批量编辑案例的保管人Advanced eDiscovery列表。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e5616b74fd8fb3a5667244d3fa5c97b5a4fbd57f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201837"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a>管理案例Advanced eDiscovery保管人

案例的"源"选项卡上的"保管人"Advanced eDiscovery包含已添加到案例的所有保管人的列表。 向案例添加保管人后，会自动从保管人中收集每个保管人Azure Active Directory，并可查看Advanced eDiscovery。

![管理保管人。](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a>查看保管人详细信息

若要查看保管人的详细信息，请单击"保管人"选项卡上的列表中的 **保管** 人。将显示一个飞出页，其中包含有关保管人的以下信息：

- 联系信息

  - **显示名称** - 在通讯簿中显示的保管人名称。 这通常是保管人名字、中间名首字母和姓氏的组合。
  
   - **邮件/SMTP** - 保管人的主 SMTP 地址，例如 brianj@contoso.onmicrosoft.com。 还将列出保管人的用户主体名称 (UPN) UPN。

  - **职务** - 保管人职务。

  - **Department** - 保管人工作部门的名称。

  - **经理** - 保管人经理。 指定的经理将收到此保管人的任何上报通信。
  
- 位置信息

  - **City** - 保管人所在的城市。

  - **State** - 保管人地址中的省/市/县。

  - **国家/地区** - 保管人所在的国家/地区。

  - **Office** - 保管人业务地点中的办公地点。

- 案例信息

  - **保留状态** - 指示保管人是否已被置于保留状态。 

  - **通信状态**：指示是否向保管人发出保留通知。 如果保管人已发出通知，则此属性的值为 **Published**。 如果保管人尚未发出通知，则状态为 **"未发布"。** 

  - **Status** - 案例内保管人的状态。 Active **状态** 指示保管人是案例的一部分。 如果保管人从案例释放，则状态更改为 **"已发布"。** 

- 数据源和索引信息

    - **数据源**- 显示与保管人关联的 (邮箱、网站和Teams) 的数据源计数和类型。

    - **索引更新** 时间 - 指示上次触发高级索引作业的时间和日期。 此属性还将指示当前正在进行高级索引编制过程。


## <a name="edit-a-custodian"></a>编辑保管人

随着你的案例的进展，你可能会发现可能有与特定保管人相关的其他数据源&您的案例。 在其他方案中，您可能需要删除已审阅并被视为不相关的某些数据源。

更新与保管人关联的数据源：

1. 转到 **电子数据展示> Advanced eDiscovery** 并打开案例。
  
2. 单击" **源"** 选项卡。
  
3. 在"**保管人"** 页上，从列表中选择保管人，然后单击飞出页上的"编辑"。

    ![编辑数据源。](../media/EditCustodianDataSource.PNG)
  
4. 单击 **"选择数据源**"选项卡更改保管人邮箱和Exchange帐户OneDrive设置，然后单击"**选择数据源"。**
  
5. 单击"**选择其他数据源**"选项卡，添加或删除Teams、SharePoint或Exchange保管人关联的邮箱。 

    有关与保管人关联的数据源详细信息，请参阅向案例 [添加保管人](add-custodians-to-case.md)。 
  
6. 单击 **"设置托管保留** "以启用或禁用保管人保留。

## <a name="re-index-custodian-data"></a>重新索引保管人数据

在大多数法律调查电子数据展示工作流中，在将保管人添加到法律案件之后，将搜索保管人数据的子集。 由于文件大小很大或数据可能损坏，与保管人关联的数据源中的某些项可能会部分编制索引。 通过使用[索引功能中的](indexing-custodian-data.md)高级Advanced eDiscovery，大多数部分索引项都可以按需重新编制索引，以自动修正这些项。

向案例添加保管人时，由高级索引过程自动对位于与保管人关联的数据源 (重新编制) 。 这意味着你可以保留就地数据，而无需下载并修正数据，然后脱机搜索) 。 但是，在法律案件生命周期内，新的数据源可能会与保管人关联。 在这种情况下，可以通过重新运行高级索引过程来重新编制保管人数据的索引，以修正任何部分索引项并更新保管人数据的索引。

若要触发重新编制索引的过程以解决部分索引项，需要执行以下操作：

1. 转到 **电子数据展示> Advanced eDiscovery** 并打开案例。

2. 单击" **源"** 选项卡。

3. 在" **保管人** "页上，选择其数据必须重新索引的保管人。

4. 在飞出页面上，单击"更新 **索引"。**

   将显示一个对话框，指出已创建索引作业。

重新索引保管人数据是一个长期运行的过程;所创建的相应作业名为 **"重新索引保管人数据"。** 您可以通过监视"索引作业状态"列中的状态来跟踪"作业"选项卡或"**保管** 人"**选项卡上** 的进度。

有关详细信息，请参阅：

- [解决处理错误](processing-data-for-case.md)

- [管理作业](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a>从案例释放保管人

在案例关闭、保管人不再承担保留案例内容的义务或认为保管人不再与案例相关时，将释放保管人。 

如果在发布保留通知后释放保管人，则向保管人发送释放通知。 此外，将删除对与保管人关联的数据源的任何保留。 如果保管人被置于静默保留状态，而其中未发出任何合法保留通知，将不会发送释放通知，但会删除与该保管人关联的数据源上的任何保留。

释放保管人： 

1. 转到 **电子数据展示> Advanced eDiscovery** 并打开案例。

2. 单击" **源"** 选项卡。

3. 在" **保管人** "页上，然后选择从案例释放的保管人。

4. 在飞出页面上，单击释放 **保管人**。

   将显示一个警告页面，说明如果对与保管人关联的数据源设置保留，则保留将被删除，并且与另一个 Advanced eDiscovery 案例关联的任何其他保留仍将适用。 这包括其他类型的保留和保留功能 (如Microsoft 365保留策略) 。

5. 单击 **"** 是"确认要释放保管人。 

    "保管人"选项卡上此用户的状态设置为"已释放"，并且飞出页面上的"保留状态"将更改为 **False**。  

> [!NOTE]
> 保管人可能同时涉及多个法律案件。 当保管人从案例释放时，其他事项中的保留和通知不会受到影响。

## <a name="bulk-edit-custodians"></a>批量编辑保管人

可以使用批量编辑器同时编辑多个保管人。 为此，只需在"保管人"选项卡上选择两个或多个保管人即可显示批量编辑器，然后单击其中一个任务。

![用于编辑多个保管人设置的 Flyout 页。](../media/AeDBulkEditCustodians.png)
