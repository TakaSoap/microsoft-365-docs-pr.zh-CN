---
title: 多地理位置功能Microsoft Teams
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
description: 了解如何Teams多地理位置Microsoft 365工作。
ms.openlocfilehash: 7da2032e1106d03178eccf3bcfb4f37fc63780d7
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59195739"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a>云中的多地理位置Microsoft Teams

多地理位置功能Teams Teams聊天数据可存储在指定地理位置中的静止状态。 聊天数据由聊天消息（包括私人消息、频道消息和聊天中使用的图像）组成。

Teams用户和组 (首选 (PDL) ，以确定存储数据的位置。 如果未设置 PDL 或 PDL 无效，则数据存储在租户的中心位置。

## <a name="user-chat"></a>用户聊天

用户聊天包括一对一、一对多和私人会议消息。

在新建用户时，Teams读取用户的 PDL，并存储其所有聊天数据。

对于现有用户，如果管理员添加或修改用户的 PDL，该用户的聊天数据将添加到迁移队列中以移动到指定的地理位置。

一对一或一对多聊天的存储位置基于创建聊天的人的 PDL。 如果该用户的 PDL 发生更改，聊天将迁移到新的地理位置。 会议聊天的存储位置基于会议组织者的 PDL。

若要查找用户的数据的当前位置，Teams [PowerShell](/powershell/module/teams/connect-microsoftteams) Teams并运行以下命令：

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a>频道消息

每个Microsoft 365组都有一个"首选数据 (PDL) ，该位置表示要存储数据的地理位置。 Teams与每个团队关联的组使用 PDL 来确定在何处存储该团队的频道消息数据。 这包括私人频道以及频道会议内发生的聊天。

当用户创建新团队时，该用户的 PDL 将确定分配给该组的 PDL Microsoft 365组。 组 PDL 确定团队数据的存储位置。 如果该用户的 PDL 稍后发生更改，则组的 PDL 不会更改。

对于现有团队，如果管理员为支持团队的 Microsoft 365 组添加或修改 PDL，该团队的频道消息数据将添加到迁移队列中，以移动到指定地理位置。

更改组组的 PDL Microsoft 365队列Teams数据以迁移到所选位置。 但是，这不会迁移SharePoint组关联的网站或文件。 必须按照将网站移动到其他地理位置中SharePoint[移动网站。](/microsoft-365/enterprise/move-sharepoint-between-geo-locations) 请务必执行这两个步骤，以避免Teams位置SharePoint组的数据和数据。

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
