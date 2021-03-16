---
title: '了解 Microsoft Teams (预览版中的默认数据丢失) '
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 了解 Microsoft Teams 中的默认数据丢失防护策略
ms.openlocfilehash: 3992daf9431dbd87ed5e947a1e5a2b0acd20edce
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826223"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>了解 Microsoft Teams (预览版中的默认数据丢失) 

[数据丢失防护](data-loss-prevention-policies.md) (DLP) 功能已扩展为包括 Microsoft Teams 聊天和频道消息，包括私人频道消息。 作为此版本的一部分，我们为首次使用合规性中心的客户创建了默认 DLP 策略。

## <a name="applies-to"></a>适用于

通过以下一个或多个许可证获得许可并拥有活动 Teams 用户的任何租户
 
- ME5、 
- MA5、 
- E5/A5 合规性、 
- IP+G、 
- OE5、 
- O365 高级合规性 
- EMS E5


## <a name="what-does-the-default-policy-do"></a>默认策略有什么功能？

默认 DLP 策略跟踪在组织内部和外部共享的所有信用卡号。 默认情况下，租户的所有用户都启用此策略。 它不会为最终用户生成任何策略提示，但会生成警报事件，还会触发低严重性电子邮件给管理员 (添加到策略策略) 。 管理员可以通过登录到合规中心查看活动并编辑策略详细信息。

管理员可以在合规中心查看此策略>[](https://compliance.microsoft.com/compliancesettings)数据丢失防护策略"页面。


> [!div class="mx-imgBorder"]
> ![默认 Teams DLP 策略](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>编辑或删除默认策略

若要 [编辑默认策略以提高性能或将其删除](create-test-tune-dlp-policy.md#tune-a-dlp-policy)，只需使用具有 **DLP 合规性管理权限** 的帐户。 有关详细信息，请参阅权限[。](create-test-tune-dlp-policy.md#permissions)

