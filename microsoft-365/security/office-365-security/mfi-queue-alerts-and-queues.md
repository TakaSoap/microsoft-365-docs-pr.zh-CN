---
title: 邮件流仪表板中的队列洞察力
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 管理员可以了解如何在安全 & 合规性中心中使用邮件流仪表板中的 "队列" 小部件，以通过出站连接器监视到其内部部署或合作伙伴组织的未成功邮件流。
ms.openlocfilehash: bcd78a50f017aae65e82185bf167ea7a227656fa
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357384"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>队列在安全 & 合规中心中的洞察力

当无法使用连接器从组织向内部部署或合作伙伴电子邮件服务器发送邮件时，邮件将在 Microsoft 365 中排队。 导致出现此情况的常见示例为：

- 连接器配置不正确。
- 本地环境中的网络或防火墙发生变化。

Microsoft 365 将继续重试传递24小时。 24小时后，邮件将会过期，并将返回到未送达报告中的发件人 (也称为 "Ndr" 或 "退回邮件") 。

如果排队的电子邮件量超过预定义的阈值 (默认值为 200) 的邮件，则可在以下位置获取这些信息：

- [安全 & 合规性中心](https://protection.office.com)中的[邮件流仪表板](mail-flow-insights-v2.md)中的**队列**洞察力。 有关详细信息，请参阅本主题中的 [邮件流仪表板](#queues-insight-in-the-mail-flow-dashboard) 部分中的队列洞察力。
  
- 在 "[安全 & 合规中心](https://protection.office.com) ("**通知**" **Recent alerts** \> **仪表板**或") 中，"最近" 警报显示在 "警报" 仪表板中 <https://protection.office.com/alertsdashboard> 。

  ![安全 & 合规中心中的 "警报" 仪表板中的最近通知](../../media/mfi-queued-messages-alert.png)

- 管理员将根据名为 " **邮件**" 的默认警报策略的配置收到电子邮件通知。 若要配置此通知的通知设置，请参阅下一节。

  有关通知策略的详细信息，请参阅 [Security & 合规性中心中的警报策略](../../compliance/alert-policies.md)。

## <a name="customize-queue-alerts"></a>自定义队列通知

1. 在 [安全 & 合规性中心](https://protection.office.com)中，转到 " **通知**" "通知 \> **策略** " 或 "打开" <https://protection.office.com/alertpolicies> 。

2. 在 " **通知策略** " 页上，查找并选择名为 "邮件" 的策略已 **延迟**。

3. 在邮件中打开了 **延迟** 的浮出浮出控件时，您可以打开或关闭通知并配置通知设置。

   ![邮件已延迟通知策略详细信息安全 & 合规性中心](../../media/mfi-queued-messages-alert-policy.png)

   - **状态**：您可以打开或关闭通知。

   - **电子邮件收件人** 和 **每日通知限制**：单击 " **编辑** " 配置以下设置：

4. 若要配置通知设置，请单击 " **编辑**"。 在出现的 " **编辑策略** " 浮出控件中，配置以下设置：

   - **发送电子邮件通知**：默认值为 "开"。
   - **电子邮件收件人**：默认值为 **TenantAdmins**。
   - **每日通知限制**：默认值为 **无限制**。
   - **阈值**：默认值为200。

   ![邮件中的通知设置已延迟警报策略详细信息安全 & 合规性中心](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. 完成后，单击 " **保存** 并 **关闭**"。

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>邮件流仪表板中的队列洞察力

即使排队邮件卷未超过阈值并生成警报，仍可以使用[邮件流仪表板](mail-flow-insights-v2.md)中的**队列**洞察力查看已排入一小时以上的邮件，并在队列中的邮件数变得过大之前采取措施。

![安全 & 合规性中心的邮件流仪表板中的 "队列" 小部件](../../media/mfi-queues-widget.png)

如果单击小组件上的邮件数，将显示一条包含以下信息的已 **排队邮件** ：

- **排队邮件数**
- **连接器名称**：单击连接器名称以管理 Exchange 管理中心内的连接器 (EAC) 。
- **队列启动时间**
- **最旧邮件已过期**
- **目标服务器**
- **最后一个 IP 地址**
- **上一个错误**
- **如何修复**：共有问题和解决方案可用。 如果 "是" **立即修复** 链接可用，请单击它以解决问题。 否则，请单击任何可用的链接，以获取有关错误和可能的解决方案的详细信息。

![单击邮件流仪表板中的队列洞察力后的详细信息](../../media/mfi-queues-details.png)

在邮件的详细信息 "**延迟**" 警报中单击 "**查看队列**" 后，将显示相同的浮出控件。

![邮件已在安全 & 合规中心中延迟警报详细信息](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。
