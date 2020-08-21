---
title: 邮件流仪表板中的队列见解
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
description: 管理员可以了解如何使用安全 & 合规中心的邮件流仪表板中的"队列"小部件，以监视出站连接器上进入其内部部署组织或合作伙伴组织的不成功邮件流。
ms.openlocfilehash: 79523533306e847988fa0d4e2dd70eca22f7c76c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826901"
---
# <a name="queues-insight-in-the-security--compliance-center"></a>安全与合规中心的队列&

如果邮件无法使用连接器从您的组织发送到您的本地或合作伙伴电子邮件服务器，则邮件会在 Microsoft 365 中排队。 导致这种情况的常见示例为：

- 未正确配置连接器。
- 您的本地环境中已经存在网络或防火墙发生了变化。

Microsoft 365 将继续重试以投递 24 小时。 24 小时后，邮件将过期，并会在未送达报告 (也称为 NDR 或退回邮件的邮件时) 。

如果排队的电子邮件卷超过预定义的阈 (默认值为 200 封邮件) ，则信息在以下位置提供：

- **安全与**合规中心的[邮件流仪表板中的](mail-flow-insights-v2.md)队列&见解。 有关详细信息，请参阅 [本主题中"邮件流"仪表板一节中的"队列见](#queues-insight-in-the-mail-flow-dashboard) 解"。
  
- 在安全 & 合**规中心报告**或警报仪表板[的警报的](https://protection.office.com)**最新警报 (** \> **Dashboard**显示 <https://protection.office.com/alertsdashboard> 一) 。

  ![最近的警报安全与合规&警报](../../media/mfi-queued-messages-alert.png)

- 管理员将根据名为"邮件"的默认提醒策略的配置**收到一封电子邮件通知。** 若要配置此警报的通知设置，请参阅下一部分。

  有关警报策略的详细信息，请参阅 [安全与合规中心中的&策略](../../compliance/alert-policies.md)。

## <a name="customize-queue-alerts"></a>自定义队列警报

1. 在安全 [与与&中心](https://protection.office.com)内，转到 **提醒** \> **策略或** 打开 <https://protection.office.com/alertpolicies> 。

2. 在" **警报策略"** 页面上，找到并选择" **邮件已延迟"策略**。

3. 消息 **中已延迟打开** 的浮出控件，可以打开或关闭警报，并配置通知设置。

   ![邮件已延迟到警报策略详细信息，例如安全&中心](../../media/mfi-queued-messages-alert-policy.png)

   - **状态**：你可以打开或关闭警报。

   - **电子邮件收件人** 和 **每日通知限制：** 单击 **"编辑** "配置以下设置：

4. 若要配置通知设置，请单击"编辑 **"。** 在显示 **的"** 编辑策略"浮出控件中，配置以下设置：

   - **发送电子邮件通知**：默认值已启用。
   - **电子邮件收件人**：默认值为**TenantAdmins。**
   - **每日通知限制**：默认值为"无**限制"。**
   - **阈**值：默认值为 200。

   ![邮件中的通知设置已延迟安全中心&策略](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. 完成后，请单击"保存并**关闭****"。**

## <a name="queues-insight-in-the-mail-flow-dashboard"></a>邮件流仪表板中的队列见解

即使排队的邮件卷未超过阈值并生成警报，您仍可以使用 **邮件流** 仪表板中的队列见 [解来查看](mail-flow-insights-v2.md) 排队超过 1 小时的邮件，然后在排队邮件数量过大之前采取操作。

![安全与合规中心的"邮件流"仪表板中的&"小部件](../../media/mfi-queues-widget.png)

如果单击小部件上的邮件数量，则会 **显示"排队"** 浮出控件中的消息，并显示以下信息：

- **排队的邮件数**
- **连接器名称**：单击连接器名称，以便在 EAC 管理中心 () 连接器。
- **队列启动时间**
- **邮件过期**
- **目标服务器**
- **上一个 IP 地址**
- **上一错误**
- **修复方法**：常见问题和解决方案均可用。 如果"立即 **修复此"链接** 可用，请单击它来修复该问题。 否则，单击所有可用链接可获取有关错误和可能的解决方案的详细信息。

![在邮件流仪表板中单击队列见解后的详细信息](../../media/mfi-queues-details.png)

在单击邮件详细信息中的"查看队列" **是延迟警报** 后，将 **会显示相同的浮出** 控件。

![在安全与合规中心中，邮件&延迟详细信息](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a>另请参阅

有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。
