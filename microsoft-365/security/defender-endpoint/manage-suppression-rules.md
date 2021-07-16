---
title: 管理 Microsoft Defender 终结点抑制规则
description: 你可能需要使用抑制规则阻止警报在门户中显示。 了解如何在 Microsoft Defender for Endpoint 中管理抑制规则。
keywords: 管理抑制， 规则， 规则名称， 范围， 操作， 警报， 打开， 关闭
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 74b89d86b770cb47a0855b45d457ea8ce5fb9802
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454753"
---
# <a name="manage-suppression-rules"></a>管理点规则

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


在某些情况下，可能需要禁止警报显示在门户中。 你可以为已知不安全的特定警报（如组织中已知的工具或流程）创建抑制规则。 若要详细了解如何抑制警报，请参阅 [抑制警报](manage-alerts.md)。

可以查看所有抑制规则的列表，并可在一个地方管理它们。 还可以打开或关闭警报抑制规则。


1. 在导航窗格中，**选择"设置**  >  **终结点**  >  **规则**  >  **警报抑制"。** 将显示组织中用户创建的抑制规则列表。

2. 通过单击规则名称旁边的复选框选择规则。

3. 单击 **"打开规则****"、"编辑** 规则"或"**删除规则"。** 更改规则时，可以选择释放已取消的警报，而无论这些警报是否匹配新条件。 


## <a name="view-details-of-a-suppression-rule"></a>查看抑制规则的详细信息

1. 在导航窗格中，**选择"设置**  >  **终结点**  >  **规则**  >  **警报抑制"。** 将显示组织中用户创建的抑制规则列表。

2. 单击规则名称。 将显示规则的详细信息。 你将看到规则详细信息，如状态、范围、操作、匹配警报数、创建时间以及创建规则的日期。 您还可以查看关联的警报和规则条件。

## <a name="related-topics"></a>相关主题

- [管理警报](manage-alerts.md)
