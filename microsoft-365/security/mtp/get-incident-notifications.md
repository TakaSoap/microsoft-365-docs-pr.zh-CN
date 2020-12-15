---
title: 在 Microsoft 365 Defender 中获取事件通知
description: 了解如何创建规则，以在 Microsoft 365 Defender 中获取事件的电子邮件通知
keywords: 事件， 电子邮件， 电子邮件通知， 配置， 用户， 邮箱， 电子邮件， 事件
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
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
ms.openlocfilehash: 3af1dcfec165c88a18cbc0d8cbf6866bb6398adc
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668139"
---
# <a name="get-incident-notifications-by-email"></a>通过电子邮件获取事件通知

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!IMPORTANT]
> 事件功能电子邮件通知目前处于公共预览阶段。 有关此功能的一些信息在商业可用性之前可能会更改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

**适用于：**
- Microsoft 365 Defender

你可以设置 Microsoft 365 Defender，以在有新事件或现有事件的新更新时通过电子邮件通知你。 

你可以选择根据事件严重性或设备组获取通知。 还可以选择仅在每个事件的第一次更新时收到通知。

可以在电子邮件通知中添加或删除收件人。 新添加的收件人在添加事件后收到事件通知。 

电子邮件通知包含有关事件的重要详细信息，如事件名称、严重性和类别等。 还可以直接转到事件，以便立即开始调查。 有关调查事件 More on investigatings， see [Investigate incidents in Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

>[!NOTE]
>您需要"管理安全设置"权限来配置电子邮件通知设置。 如果选择使用基本权限管理，具有安全管理员或全局管理员角色的用户可以配置电子邮件通知。 <br> <br>
同样，如果组织使用基于角色的访问控制 (RBAC) ，则只能基于允许管理的设备组创建、编辑、删除和接收通知。

## <a name="create-rules-for-incident-notifications"></a>创建事件通知规则

若要为事件设置第一个电子邮件通知，请创建一个新规则并自定义电子邮件通知设置。

1. 在导航窗格中，选择 **"设置**  >  **事件电子邮件通知"。**
2. 选择 **"添加项目"。**
3. 在"名称"**中为规则** 命名，并提供 **"说明"。**

    ![为事件电子邮件创建规则窗口](../../media/incidentemailnotif1.png) 
4. 选择 **"下** 一步"转到 **"通知设置"。** 你可以在此处指定：
    - **警报严重性** - 选择将触发事件通知的警报严重性。 例如，如果您只想获得有关高严重性事件的通知，请选择"高"。
    - **设备组** 作用域 - 此下拉列表显示用户可以访问的所有设备组。 选择要为哪些设备组创建事件通知规则。
    - **仅在每个事件首次出现** 时通知 - 选择此选项将仅在第一个匹配其他选择的警报上发送电子邮件通知。 以后与事件相关的更新或警报不会触发通知。
    - **包含组织名称** - 指示是否在电子邮件通知上显示客户名称。
    - **包含特定于租户的门户链接** - 添加包含租户 ID 的链接，以允许访问特定租户。
    
    ![事件电子邮件的 Notif 设置窗口](../../media/incidentemailnotif2.png)
5. 选择 **"下** 一步"转到 **"收件人"** 部分。 你可以在此处指定将接收事件电子邮件通知的电子邮件地址。 键入 **每个电子邮件地址后** ，选择"添加收件人"。

    ![事件电子邮件的"添加收件人"窗口](../../media/incidentemailnotif3.png) 

6. 最后， **选择"下一** 步 **"转到"** 查看规则"，以便你可以看到与新规则关联的所有设置。 收件人将开始根据设置通过电子邮件接收事件通知。

## <a name="see-also"></a>另请参阅
- [Microsoft 365 Defender 中的事件概述](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [确定 Microsoft 365 Defender 中事件的优先级](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [调查 Microsoft 365 Defender 中的事件](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

