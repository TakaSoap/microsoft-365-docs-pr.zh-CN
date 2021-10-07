---
title: 在 Microsoft Defender for Endpoint 中配置警报通知
description: 可以使用 Microsoft Defender for Endpoint 根据严重性和其他条件配置安全警报的电子邮件通知设置。
keywords: 电子邮件通知， 配置警报通知， 适用于终结点的 Microsoft Defender， 适用于终结点的 Microsoft Defender 通知， 适用于终结点的 Microsoft Defender 警报， windows 企业版， windows 教育版
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
ms.openlocfilehash: d598687edbb4268bc02a4f0bd8c752405cf22dee
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192963"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中配置警报通知

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-emailconfig-abovefoldlink)。

你可以将 Defender for Endpoint 配置为向指定收件人发送电子邮件通知，以接收新警报。 此功能使你能够识别将立即获得通知的一组个人，并可以基于其严重性对警报采取行动。

> [!NOTE]
> 只有具有"管理安全设置"权限的用户才能配置电子邮件通知。 如果选择使用基本权限管理，则具有安全管理员或全局管理员角色的用户可以配置电子邮件通知。

你可以设置触发通知的警报严重性级别。 您还可以添加或删除电子邮件通知的收件人。 新收件人收到有关在添加后触发的警报的通知。 有关警报详细信息，请参阅 [查看和组织警报队列](alerts-queue.md)。

如果使用基于角色的访问控制 (RBAC) ，则收件人将仅根据通知规则中配置的设备组接收通知。
具有适当权限的用户只能创建、编辑或删除仅限于其设备组管理作用域的通知。
只有分配到全局管理员角色的用户才能管理所有设备组配置的通知规则。

电子邮件通知包括有关警报的基本信息和指向门户的链接，可在其中执行进一步调查。

## <a name="create-rules-for-alert-notifications"></a>创建通知通知规则
可以创建规则，以确定要发送电子邮件通知的设备以及通知收件人的警报严重性。


1. 在导航窗格中，**选择"设置** \>  \> **终结点""** \> **常规电子邮件通知"。**

2. 单击 **"添加项目"。**

3. 指定常规信息：
    - **规则名称** - 指定通知规则的名称。
    - **包含组织** 名称 - 指定电子邮件通知上显示的客户名称。
    - **包含特定于租户的门户链接** - 添加包含租户 ID 的链接，以允许访问特定租户。
    - **包括设备信息** - 在电子邮件警报正文中包含设备名称。

        > [!NOTE]
        > 此信息可能由不在你为 Defender for Endpoint 数据选择的地理位置中的收件人邮件服务器进行处理。

    - **设备** - 选择是通知收件人有关所有设备上警报 (全局管理员角色) 或所选设备组。 有关详细信息，请参阅创建 [和管理设备组](machine-groups.md)。
    - **警报严重性** - 选择警报严重性级别。

4. 单击“下一步”。

5. 输入收件人的电子邮件地址，然后单击"**添加收件人"。** 可添加多个电子邮件地址。

6. 选中"发送测试电子邮件"，检查电子邮件收件人是否 **可接收电子邮件通知**。

7. 单击 **"保存通知规则"。**

## <a name="edit-a-notification-rule"></a>编辑通知规则

1. 选择要编辑的通知规则。

2. 更新"常规"和"收件人"选项卡信息。

3. 单击 **"保存通知规则"。**

## <a name="delete-notification-rule"></a>删除通知规则

1. 选择要删除的通知规则。

2. 单击“删除”。

## <a name="troubleshoot-email-notifications-for-alerts"></a>警报电子邮件通知疑难解答

本节列出了在使用电子邮件通知发出警报时可能遇到的各种问题。

**问题：** 目标收件人报告他们未收到通知。

**解决方案：** 确保电子邮件筛选器不会阻止通知：

1. 检查 Defender for Endpoint 电子邮件通知是否未发送到垃圾邮件文件夹。 将其标记为"非垃圾邮件"。
2. 检查你的电子邮件安全产品是否未阻止来自 Defender for Endpoint 的电子邮件通知。
3. 检查可能捕获和移动 Defender for Endpoint 电子邮件通知的电子邮件应用程序规则。

## <a name="related-topics"></a>相关主题

- [更新数据保留设置](data-retention-settings.md)
- [配置高级功能](advanced-features.md)
- [在 Microsoft Defender for Endpoint 中配置漏洞电子邮件通知](/microsoft-365/security/defender-endpoint/configure-vulnerability-email-notifications)
