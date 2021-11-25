---
title: 管理 Microsoft Defender 终结点抑制规则
description: 你可能需要使用抑制规则阻止警报在门户中显示。 了解如何在 Microsoft Defender for Endpoint 中管理抑制规则。
keywords: 管理抑制， 规则， 规则名称， 范围， 操作， 警报， 打开， 关闭
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ee488256363cbb008f670bb8c88d3fb88d7c4090
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61166790"
---
# <a name="manage-suppression-rules"></a>管理点规则

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。


在某些情况下，可能需要禁止警报显示在门户中。 你可以为已知不安全的特定警报（如组织中已知的工具或流程）创建抑制规则。 若要详细了解如何抑制警报，请参阅 [抑制警报](manage-alerts.md)。

你可以查看所有抑制规则的列表，并可在一个地方管理它们。 还可以打开或关闭警报抑制规则。


1. 在导航窗格中，**选择"设置** \> **终结点** \> **规则** \> **警报抑制"。** 将显示组织中用户创建的抑制规则列表。

2. 通过单击规则名称旁边的复选框选择规则。

3. 单击 **"打开规则****"、"编辑** 规则"或"**删除规则"。** 更改规则时，可以选择释放已取消的警报，而无论这些警报是否匹配新条件。 


## <a name="view-details-of-a-suppression-rule"></a>查看抑制规则的详细信息

1. 在导航窗格中，**选择"设置** \> **终结点** \> **规则** \> **警报抑制"。** 将显示组织中用户创建的抑制规则列表。

2. 单击规则名称。 将显示规则的详细信息。 你将看到规则详细信息，如状态、范围、操作、匹配警报数、创建时间以及创建规则的日期。 您还可以查看关联的警报和规则条件。

## <a name="related-topics"></a>相关主题

- [管理警报](manage-alerts.md)
