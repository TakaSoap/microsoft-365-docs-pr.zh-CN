---
title: 云中的多地理位置Microsoft Teams
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
description: 了解Teams多地理位置Microsoft 365工作原理。
ms.openlocfilehash: 9fe9b289b0ffbef12327c4232b9deb6727b6d718
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362639"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a>多地理位置功能Microsoft Teams

多地理位置功能Teams允许Teams聊天数据以静止状态存储在指定地理位置。 聊天数据由聊天消息（包括私人消息、频道消息和聊天中使用的图像）组成。

Teams用户和组 (PDL) 首选数据位置，以确定存储数据的位置。 如果未设置 PDL 或 PDL 无效，则数据存储在租户的中心位置。

## <a name="user-chat"></a>用户聊天

用户聊天包括一对一、一对多和私人会议消息。

当创建一个新用户时，Teams读取用户的 PDL，并存储其所有聊天数据。

对于现有用户，如果管理员添加或修改用户的 PDL，该用户的聊天数据将添加到迁移队列中以移动到指定的地理位置。

一对一或一对多聊天的存储位置基于创建聊天的人的 PDL。 如果该用户的 PDL 发生更改，聊天将迁移到新的地理位置。 会议聊天的存储位置基于会议组织者的 PDL。

若要查找用户当前存储数据Teams，请连接到[Teams PowerShell 并](/powershell/module/teams/connect-microsoftteams)运行以下命令：

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a>频道消息

每个Microsoft 365组都有一 (PDL) 首选数据位置，该位置表示要存储数据的地理位置。 Teams使用与每个团队关联的组的 PDL 来确定在何处存储该团队的频道消息数据。 这包括频道会议内发生的聊天。

当用户创建新团队时，该用户的 PDL 将确定分配给该组Microsoft 365 PDL。 组 PDL 确定团队数据的存储位置。 如果该用户的 PDL 稍后发生更改，则组的 PDL 不会更改。

对于现有团队，如果管理员添加或修改支持团队的 Microsoft 365 组的 PDL，该团队的频道消息数据将添加到迁移队列中，以移动到指定地理位置。

更改组组的 PDL Microsoft 365将Teams数据排入队列，以迁移到所选位置。 但是，这不会迁移SharePoint组关联的网站或文件。 必须按照将网站移动到其他地理位置中SharePoint[移动网站](/microsoft-365/enterprise/move-sharepoint-between-geo-locations)。 请务必执行这两个步骤，以避免Teams组的数据SharePoint访问数据。

若要查找团队数据的当前位置，请连接到 Teams [PowerShell](/powershell/module/teams/connect-microsoftteams)并运行以下命令：

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a>用户体验

Teams多地理位置对最终用户是无缝的。 更改用户或组的 PDL 后，相应的数据将排入迁移队列，并且迁移将自动进行，不会影响用户或 Teams 客户端，即使它们在迁移发生时处于活动状态。

## <a name="see-also"></a>另请参阅

[Microsoft 365 多地理位置租户配置](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[管理多地理位置环境](administering-a-multi-geo-environment.md)

[在多地理位置环境中管理 Exchange Online 邮箱](administering-exchange-online-multi-geo.md)
