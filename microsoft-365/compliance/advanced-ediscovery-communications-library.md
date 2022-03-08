---
title: 在 Advanced eDiscovery 中的通信库中管理保管人Advanced eDiscovery
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
description: 你可以添加保管人通信模板 (如 Advanced eDiscovery 中的保留通知) 模板，以便在任何情况下都可以在组织中使用。
ms.openlocfilehash: 1b5be4a4a923050b43943e81ac64265e16749899
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330759"
---
# <a name="manage-custodian-communications-templates-in-advanced-ediscovery"></a>在托管服务中管理保管人Advanced eDiscovery

当您或其他用户创建保留通知或其他类型的保管人通信时，您必须使用"通信"选项卡上的通信编辑器从头开始创建通信文档，Advanced eDiscovery情况。 现在，我们发布了一项新功能，允许你创建可用于在组织中在任何情况下创建通信的通信模板。 创建通信模板后，可以在一种情况下使用这些模板。 这意味着创建保管人通信的律师或其他用户不必从头开始生成通知。 相反，他们可以选择模板来生成发送给保管人的通知。

本文介绍如何创建组织范围内的通信模板，以及如何在为特定案例创建新的保管人通知时选择Advanced eDiscovery模板。

## <a name="before-you-create-templates-in-the-communications-library"></a>在通信库中创建模板之前

- 您必须是您的组织中的电子数据展示管理员，才能在 Advanced eDiscovery 中的通信库中添加或删除Advanced eDiscovery。 有关详细信息，请参阅分配[电子数据展示](assign-ediscovery-permissions.md)Microsoft 365 合规中心  

- 你的组织在通信库中最多可以有 50 个模板。

## <a name="create-a-communications-template"></a>创建通信模板

1. In the Microsoft 365 合规中心， go to [Advanced eDiscovery](https://go.microsoft.com/fwlink/p/?linkid=2173764)， and then click **Advanced eDiscovery settings**.

   ![选择Advanced eDiscovery设置](..\media\HistoricalVersions1.png)

2. 在"**设置**"页上，选择"**通信库"** 选项卡。

3. 在" **通信库"页上** ，单击"创建 **"**。

4. 按照过程创建保管人通信。 有关分步说明，请参阅 [创建合法保留通知](create-hold-notification.md)。

   > [!NOTE]
   > 创建通信模板的步骤与在案例内创建通知的工作流相同。 唯一的区别是，创建模板时，不指定颁发者，也不需要分配保管人。 使用通信模板为案例创建保管人通知时，将指定颁发官和分配保管人。

5. 创建模板后，该模板将显示在"通信库 **"** 页上。

   ![通信库中显示的模板](..\media\AeDCommunicationsLibrary1.png)

您或其他电子数据展示管理员可以编辑通信模板。 对模板进行的任何更改都不会影响或修改之前使用该模板创建的任何通知。 这些更改将仅适用于使用更新的模板创建的新通知。

## <a name="use-a-communications-template-to-create-a-custodian-notification"></a>使用通信模板创建保管人通知

在通信库中创建一个或多个通信模板后，可以选择这些模板，在一种情况下创建保管人通知。

若要选择模板，请进行以下操作：

1. 在Microsoft 365 合规中心中，转到"**>"**"高级"以显示组织中事例的列表。

2. 选择一个案例，单击" **通信"** 选项卡，然后单击"新建 **通信"**。

3. 在" **名称通信** "页上，使用" **选择** 通信模板"下拉列表选择要用于创建保管人通知的通信模板。

   组织的通信库中的模板列表显示在下拉列表中。

   ![下拉列表中显示的通信库中的模板。](..\media\AeDCommunicationsTemplates1.png)
