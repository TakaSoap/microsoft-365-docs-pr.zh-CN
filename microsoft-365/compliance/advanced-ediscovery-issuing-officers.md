---
title: 管理证书颁发Advanced eDiscovery
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
description: 您可以在组织中添加组织范围内的颁发Advanced eDiscovery以便他们可添加到组织中在任何情况下的任何计划性通信。
ms.openlocfilehash: 21c5a3db9cb0cfefb26bc75537f298c7e8a5c09a
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319059"
---
# <a name="manage-issuing-officers-in-advanced-ediscovery"></a>管理证书颁发Advanced eDiscovery

当您或其他人创建一个保留通知或发送给作为保管人的用户的其他通信类型时，您必须指定颁发者。 通知将代表指定的颁发机构发送给保管人。 例如，您的组织中的律师可能负责创建保留通知，并针对案例向保管人发送保留通知。 在此方案中，律师可以在组织中将律师指定为颁发者。 Who是否可指定为颁发者？ 有两种类型的用户可以选作保管人通信的颁发官：

- 代表发送通信的特定案例的任何成员。

- 添加到组织范围内的颁发官员列表的任何用户。 可以将此列表的用户添加到您组织的任何案例的颁发官。

本文介绍如何向组织范围内的颁发机构列表中添加和删除用户。

## <a name="before-you-add-an-issuing-officer"></a>添加颁发官之前

- 您必须是您的组织中的电子数据展示管理员才能添加或删除颁发官员。 有关详细信息，请参阅分配[电子数据展示](assign-ediscovery-permissions.md)Microsoft 365 合规中心  

- 被添加为颁发机构的用户必须在您的组织中拥有Microsoft 365邮箱。

- 你的组织最多可有 15 个颁发官员。 可以指定为颁发机构的成员不计入此限制。 此限制仅适用于可添加到证书颁发机构页面中的用户Advanced eDiscovery。

## <a name="add-an-issuing-officer"></a>添加颁发官

1. In the Microsoft 365 合规中心， go to [Advanced eDiscovery](https://go.microsoft.com/fwlink/p/?linkid=2173764)， and then click **Advanced eDiscovery settings**.

   ![选择Advanced eDiscovery设置](..\media\HistoricalVersions1.png)

2. 在"**设置**"页上，选择"颁发者 **"选项卡以显示**"**管理颁发官员"** 页。

   ![颁发官员设置页。](..\media\AeDIssuingOfficers1.png)

3. 单击 **"** 添加"，然后搜索一个或多个用户并将其添加到颁发官员列表中。

在将用户添加为颁发官员后，您或其他用户将能够指定这些用户为组织中任何案例的保管人通信的颁发官。 有关创建保管人通信的信息，请参阅 [创建法定保留通知](create-hold-notification.md)。

## <a name="remove-an-issuing-officer"></a>删除发证人员

1. In the Microsoft 365 合规中心， go to [Advanced eDiscovery](https://go.microsoft.com/fwlink/p/?linkid=2173764)， and then click **Advanced eDiscovery settings**.

2. 在"**设置**"页上，选择 **"颁发官员"** 选项卡。

3. 在颁发者列表中选择一个或多个用户，然后单击"删除 **"**。

从颁发机构列表中删除用户后，这些用户不再可以在新的保管人通信中指定为颁发者，除非该用户是发出通信的特定案例的成员。 此外，删除发证人员不会影响在将用户删除为颁发官员之前发送的任何通信。
