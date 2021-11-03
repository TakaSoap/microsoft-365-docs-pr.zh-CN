---
title: 通过电子邮件获取事件通知Microsoft 365 Defender
description: 了解如何创建规则，以在电子邮件中获取事件Microsoft 365 Defender
keywords: 事件， 电子邮件， 电子邮件通知， 配置， 用户， 邮箱， 电子邮件， 事件， 分析， 响应
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 600ff555762112222769fde0372716f4a89a12b9
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60717439"
---
# <a name="get-incident-notifications-by-email"></a>通过电子邮件获取事件通知

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

你可以设置Microsoft 365 Defender通知员工有关新事件或现有事件更新的电子邮件。 可以选择基于以下选项获取通知：

- 事件严重性。
- 设备组。
- 仅在每个事件的第一次更新时。

电子邮件通知包含有关事件的重要详细信息，如事件名称、严重性和类别等。 您还可以直接转到事件并立即开始分析。 有关详细信息，请参阅调查 [事件](investigate-incidents.md)。

可以在电子邮件通知中添加或删除收件人。 新收件人在添加事件后会收到通知。 

>[!NOTE]
>您需要"管理安全设置"权限才能配置电子邮件通知设置。 如果选择使用基本权限管理，则具有安全管理员或全局管理员角色的用户可以配置电子邮件通知。 <br> <br>
同样，如果组织使用的是基于角色的访问控制 (RBAC) ，则只能根据允许管理的设备组创建、编辑、删除和接收通知。

## <a name="create-a-rule-for-email-notifications"></a>为电子邮件通知创建规则

按照以下步骤创建新规则并自定义电子邮件通知设置。

1. 在导航窗格中，选择 **"设置 > Microsoft 365 Defender >事件电子邮件通知"。**
2. 选择 **"添加项目"。**
3. 在"**基本信息"** 页上，键入规则名称和说明，然后选择"下一步 **"。**
4. 在" **通知设置"** 页上，配置：
    - **警报严重程度** - 选择将触发事件通知的警报严重程度。 例如，如果你只想获得有关高严重性事件的通知，请选择"高 **"。**
    - **设备组范围** - 可以指定所有设备组或从租户中的设备组列表中进行选择。
    - **仅在每个事件第一次发生时进行通知** - 选择是否仅需要对与其他所选内容相匹配的第一个警报进行通知。 与事件相关的后续更新或警报不会发送额外通知。
    - **在电子邮件中包含组织名称** - 选择是否希望组织名称显示在电子邮件通知中。
    - **包括特定于租户的门户链接** - 选择是否要在电子邮件通知中添加包含租户 ID 的链接，以便访问特定的 Microsoft 365 租户。

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="事件电子邮件通知的通知设置。":::

5. 选择 **下一步**。 在 **"收件人"** 页上，添加将接收事件通知的电子邮件地址。 键入 **每个** 新电子邮件地址后，选择"添加"。 若要测试通知并确保收件人在收件箱中收到通知，请选择"**发送测试电子邮件"。** 
6. 选择 **下一步**。 在"**复查规则**"页上，查看规则的设置，然后选择"创建 **规则"。** 收件人将开始根据设置通过电子邮件接收事件通知。

若要编辑现有规则，请从规则列表中选择它。 在具有规则名称的窗格中，选择"编辑规则"，在"基本"、通知 **设置** 和"**收件人"页上进行更改**。 

若要删除规则，请从规则列表中选择它。 在具有规则名称的窗格中，选择"删除 **"。**

## <a name="see-also"></a>另请参阅
- [事件概述](incidents-overview.md)
- [确定事件优先级](incident-queue.md)
- [调查事件](investigate-incidents.md)
