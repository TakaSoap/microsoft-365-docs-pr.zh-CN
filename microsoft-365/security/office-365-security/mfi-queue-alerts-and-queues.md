---
title: 邮件流仪表板中的队列见解
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 管理员可以 &了解如何使用安全与合规中心内邮件流仪表板中的"队列"小组件监视通过出站连接器发送到其内部部署组织或合作伙伴组织的不成功邮件流。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 94e8a1f3b54c3738c21e94ba85ae4f1d3f953498
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150167"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>安全与合规中心&队列见解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用于**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 计划 1 和计划 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

当无法将邮件从组织发送到使用连接器本地或合作伙伴电子邮件服务器时，这些邮件将在 Microsoft 365 中排队。 导致这种情况的常见示例包括：

- 连接器配置不正确。
- 本地环境中发生了网络或防火墙更改。

Microsoft 365 将继续重试传递 24 小时。 24 小时后，这些邮件将过期，并返回到未送达报告中的发件人 (也称为 NDDR 或退回邮件) 。

如果排队的电子邮件卷超过预定义的阈值 (默认值为 200 封邮件) ，则信息可在以下位置获取：

- 安全 **与** 合规中心 [的邮件流仪表板](mail-flow-insights-v2.md) 中的& [见解](https://protection.office.com)。 有关详细信息，请参阅本文"邮件 [流仪表板"](#queues-insight-in-the-mail-flow-dashboard) 部分中的"队列见解"。

- 警报显示在 **安全与合规** 中心内"警报"仪表板中的"最近 [](https://protection.office.com)&警报 ( \> **仪表板** 或 <https://protection.office.com/alertsdashboard>) 。

  ![安全与合规中心的警报仪表板中的&警报](../../media/mfi-queued-messages-alert.png)

- 管理员将收到一封电子邮件通知，该通知基于名为"邮件" **的默认警报策略的配置已延迟**。 若要为此警报配置通知设置，请参阅下一节。

  有关警报策略详细信息，请参阅安全与合规中心& [策略](../../compliance/alert-policies.md)。

## <a name="customize-queue-alerts"></a>自定义队列警报

1. 在 [安全&中心](https://protection.office.com)，转到 **警报** \> **警报策略或** 打开 <https://protection.office.com/alertpolicies> 。

2. 在 **"警报策略"** 页上，查找并选择名为 **"已延迟的邮件"的策略**。

3. 在 **打开的"消息"** 已延迟的飞出中，你可以打开或关闭警报并配置通知设置。

   ![邮件已延迟警报策略详细信息 安全&合规中心](../../media/mfi-queued-messages-alert-policy.png)

   - **状态**：你可以打开或关闭警报。

   - **电子邮件收件人** 和 **每日通知限制**：单击 **"编辑** "配置以下设置：

4. 若要配置通知设置，请单击"编辑 **"。** 在 **出现的"编辑策略** "飞出中，配置以下设置：

   - **发送电子邮件通知**：默认值为打开状态。
   - **电子邮件收件人**：默认值为 **TenantAdmins。**
   - **每日通知限制**：默认值为 **无限制**。
   - **阈值**：默认值为 200。

   !["邮件"中的通知设置已延迟警报策略详细信息 安全&合规中心](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. 完成后，单击"**保存并****关闭"。**

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>邮件流仪表板中的队列见解

即使排队的邮件卷未超出阈值并生成警报，您仍可以使用邮件流仪表板中的 **"** 队列见解"查看已排队超过 [](mail-flow-insights-v2.md)1 小时的邮件，在排队邮件数量过大之前采取措施。

![安全与合规中心的邮件流仪表板中的&小组件](../../media/mfi-queues-widget.png)

If you click the number of messages on the widget， a **Messages queued** flyout appears with the following information：

- **排队邮件数**
- **连接器名称**：单击连接器名称以在 Exchange 管理中心或 EAC (管理) 。
- **队列启动时间**
- **最旧邮件已过期**
- **目标服务器**
- **最后一个 IP 地址**
- **上一个错误**
- **如何修复**：常见问题和解决方案可用。 If is a **Fix it now** link is available， click it to fix the problem. 否则，请单击任何可用链接，了解有关错误和可能的解决方案的详细信息。

![单击邮件流仪表板中的"队列"见解后的详细信息](../../media/mfi-queues-details.png)

单击"邮件已延迟警报的详细信息 **"中的"** 查看队列"后，将显示 **相同的飞** 出。

![安全与合规中心内的邮件&警报详细信息](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。
