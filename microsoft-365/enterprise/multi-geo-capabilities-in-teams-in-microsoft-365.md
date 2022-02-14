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
ms.localizationpriority: medium
description: 了解如何Teams多地理位置Microsoft 365功能。
ms.openlocfilehash: 0315a9ff0429c5e00c662bd7345a3b6a39a591c3
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2022
ms.locfileid: "62805864"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a>云中的多地理位置Microsoft Teams

多地理位置功能Teams允许Teams聊天数据以静止状态存储在指定地理位置。 聊天数据由聊天消息（包括私人消息、频道消息和聊天中使用的图像）组成。

Teams用户和组 (首选 (PDL) ，以确定存储数据的位置。 如果未设置 PDL 或 PDL 无效，则数据存储在租户的中心位置。

> [!NOTE]
> 2021 年 7 Teams推出多地理位置功能。 你的聊天和频道消息将会自动迁移到接下来几个季度的正确地理位置。 租户完成初始同步后，将处理所有新的 PDL 更改，超过该更改的新 PDL 更改将按照接收顺序排队和处理。

## <a name="user-chat"></a>用户聊天

用户聊天包括一对一、一对多和私人会议消息。

当创建一个新用户时，Teams读取用户的 PDL，并存储其所有聊天数据。

对于现有用户，如果管理员添加或修改用户的 PDL，该用户的聊天数据将添加到迁移队列中以移动到指定的地理位置。

一对一或一对多聊天的存储位置基于创建聊天的人的 PDL。 如果该用户的 PDL 发生更改，聊天将迁移到新的地理位置。 会议聊天的存储位置基于会议组织者的 PDL。

若要查找用户的数据的当前位置，Teams [PowerShell Teams并](/powershell/module/teams/connect-microsoftteams)运行以下命令：

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a>频道消息

每个Microsoft 365组都有一个首选数据 (PDL) 它表示要存储数据的地理位置。 Teams使用与每个团队关联的组的 PDL 来确定在何处存储该团队的频道消息数据。 这包括私人频道和频道会议内发生的聊天。

当用户创建新团队时，该用户的 PDL 将确定分配给该组Microsoft 365 PDL。 组 PDL 确定团队数据的存储位置。 如果该用户的 PDL 稍后发生更改，则组的 PDL 不会更改。

对于现有团队，如果管理员添加或修改支持团队的 Microsoft 365 组的 PDL，该团队的频道消息数据将添加到迁移队列中，以移动到指定地理位置。

更改组组的 PDL Microsoft 365队列，Teams数据迁移到所选位置。 但是，这不会迁移SharePoint组关联的网站或文件。 必须按照将网站移动到其他地理位置中SharePoint[移动网站。](/microsoft-365/enterprise/move-sharepoint-between-geo-locations) 请务必执行这两个步骤，以避免Teams位置SharePoint组的数据和数据。

若要查找团队数据的当前位置，请连接到 [Teams PowerShell](/powershell/module/teams/connect-microsoftteams) 并运行以下命令：

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a>用户体验

Teams多地理位置对最终用户是无缝的。 更改用户或组的 PDL 后，相应的数据将排入迁移队列，并且迁移将自动进行，不会影响用户或 Teams 客户端，即使它们在迁移发生时处于活动状态。

## <a name="see-also"></a>另请参阅

[Microsoft 365 多地理位置租户配置](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[管理多地理位置环境](administering-a-multi-geo-environment.md)

[在多地理位置环境中管理 Exchange Online 邮箱](administering-exchange-online-multi-geo.md)
