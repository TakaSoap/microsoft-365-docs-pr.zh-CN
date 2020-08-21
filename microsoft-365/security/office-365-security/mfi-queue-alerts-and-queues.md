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
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="5a860-103">安全与合规中心的队列&</span><span class="sxs-lookup"><span data-stu-id="5a860-103">Queues insight in the Security & Compliance Center</span></span>

<span data-ttu-id="5a860-104">如果邮件无法使用连接器从您的组织发送到您的本地或合作伙伴电子邮件服务器，则邮件会在 Microsoft 365 中排队。</span><span class="sxs-lookup"><span data-stu-id="5a860-104">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="5a860-105">导致这种情况的常见示例为：</span><span class="sxs-lookup"><span data-stu-id="5a860-105">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="5a860-106">未正确配置连接器。</span><span class="sxs-lookup"><span data-stu-id="5a860-106">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="5a860-107">您的本地环境中已经存在网络或防火墙发生了变化。</span><span class="sxs-lookup"><span data-stu-id="5a860-107">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="5a860-108">Microsoft 365 将继续重试以投递 24 小时。</span><span class="sxs-lookup"><span data-stu-id="5a860-108">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="5a860-109">24 小时后，邮件将过期，并会在未送达报告 (也称为 NDR 或退回邮件的邮件时) 。</span><span class="sxs-lookup"><span data-stu-id="5a860-109">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="5a860-110">如果排队的电子邮件卷超过预定义的阈 (默认值为 200 封邮件) ，则信息在以下位置提供：</span><span class="sxs-lookup"><span data-stu-id="5a860-110">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="5a860-111">**安全与**合规中心的[邮件流仪表板中的](mail-flow-insights-v2.md)队列&见解。</span><span class="sxs-lookup"><span data-stu-id="5a860-111">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center.</span></span> <span data-ttu-id="5a860-112">有关详细信息，请参阅 [本主题中"邮件流"仪表板一节中的"队列见](#queues-insight-in-the-mail-flow-dashboard) 解"。</span><span class="sxs-lookup"><span data-stu-id="5a860-112">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this topic.</span></span>
  
- <span data-ttu-id="5a860-113">在安全 & 合**规中心报告**或警报仪表板[的警报的](https://protection.office.com)**最新警报 (** \> **Dashboard**显示 <https://protection.office.com/alertsdashboard> 一) 。</span><span class="sxs-lookup"><span data-stu-id="5a860-113">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![最近的警报安全与合规&警报](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="5a860-115">管理员将根据名为"邮件"的默认提醒策略的配置**收到一封电子邮件通知。**</span><span class="sxs-lookup"><span data-stu-id="5a860-115">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="5a860-116">若要配置此警报的通知设置，请参阅下一部分。</span><span class="sxs-lookup"><span data-stu-id="5a860-116">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="5a860-117">有关警报策略的详细信息，请参阅 [安全与合规中心中的&策略](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5a860-117">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="5a860-118">自定义队列警报</span><span class="sxs-lookup"><span data-stu-id="5a860-118">Customize queue alerts</span></span>

1. <span data-ttu-id="5a860-119">在安全 [与与&中心](https://protection.office.com)内，转到 **提醒** \> **策略或** 打开 <https://protection.office.com/alertpolicies> 。</span><span class="sxs-lookup"><span data-stu-id="5a860-119">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="5a860-120">在" **警报策略"** 页面上，找到并选择" **邮件已延迟"策略**。</span><span class="sxs-lookup"><span data-stu-id="5a860-120">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="5a860-121">消息 **中已延迟打开** 的浮出控件，可以打开或关闭警报，并配置通知设置。</span><span class="sxs-lookup"><span data-stu-id="5a860-121">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![邮件已延迟到警报策略详细信息，例如安全&中心](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="5a860-123">**状态**：你可以打开或关闭警报。</span><span class="sxs-lookup"><span data-stu-id="5a860-123">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="5a860-124">**电子邮件收件人** 和 **每日通知限制：** 单击 **"编辑** "配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="5a860-124">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="5a860-125">若要配置通知设置，请单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="5a860-125">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="5a860-126">在显示 **的"** 编辑策略"浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="5a860-126">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="5a860-127">**发送电子邮件通知**：默认值已启用。</span><span class="sxs-lookup"><span data-stu-id="5a860-127">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="5a860-128">**电子邮件收件人**：默认值为**TenantAdmins。**</span><span class="sxs-lookup"><span data-stu-id="5a860-128">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="5a860-129">**每日通知限制**：默认值为"无**限制"。**</span><span class="sxs-lookup"><span data-stu-id="5a860-129">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="5a860-130">**阈**值：默认值为 200。</span><span class="sxs-lookup"><span data-stu-id="5a860-130">**Threshold**: The default value is 200.</span></span>

   ![邮件中的通知设置已延迟安全中心&策略](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="5a860-132">完成后，请单击"保存并**关闭\*\*\*\*"。**</span><span class="sxs-lookup"><span data-stu-id="5a860-132">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="5a860-133">邮件流仪表板中的队列见解</span><span class="sxs-lookup"><span data-stu-id="5a860-133">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="5a860-134">即使排队的邮件卷未超过阈值并生成警报，您仍可以使用 **邮件流** 仪表板中的队列见 [解来查看](mail-flow-insights-v2.md) 排队超过 1 小时的邮件，然后在排队邮件数量过大之前采取操作。</span><span class="sxs-lookup"><span data-stu-id="5a860-134">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![安全与合规中心的"邮件流"仪表板中的&"小部件](../../media/mfi-queues-widget.png)

<span data-ttu-id="5a860-136">如果单击小部件上的邮件数量，则会 **显示"排队"** 浮出控件中的消息，并显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="5a860-136">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="5a860-137">**排队的邮件数**</span><span class="sxs-lookup"><span data-stu-id="5a860-137">**Number of queued messages**</span></span>
- <span data-ttu-id="5a860-138">**连接器名称**：单击连接器名称，以便在 EAC 管理中心 () 连接器。</span><span class="sxs-lookup"><span data-stu-id="5a860-138">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="5a860-139">**队列启动时间**</span><span class="sxs-lookup"><span data-stu-id="5a860-139">**Queue started time**</span></span>
- <span data-ttu-id="5a860-140">**邮件过期**</span><span class="sxs-lookup"><span data-stu-id="5a860-140">**Oldest messages expired**</span></span>
- <span data-ttu-id="5a860-141">**目标服务器**</span><span class="sxs-lookup"><span data-stu-id="5a860-141">**Destination server**</span></span>
- <span data-ttu-id="5a860-142">**上一个 IP 地址**</span><span class="sxs-lookup"><span data-stu-id="5a860-142">**Last IP address**</span></span>
- <span data-ttu-id="5a860-143">**上一错误**</span><span class="sxs-lookup"><span data-stu-id="5a860-143">**Last error**</span></span>
- <span data-ttu-id="5a860-144">**修复方法**：常见问题和解决方案均可用。</span><span class="sxs-lookup"><span data-stu-id="5a860-144">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="5a860-145">如果"立即 **修复此"链接** 可用，请单击它来修复该问题。</span><span class="sxs-lookup"><span data-stu-id="5a860-145">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="5a860-146">否则，单击所有可用链接可获取有关错误和可能的解决方案的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5a860-146">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![在邮件流仪表板中单击队列见解后的详细信息](../../media/mfi-queues-details.png)

<span data-ttu-id="5a860-148">在单击邮件详细信息中的"查看队列" **是延迟警报** 后，将 **会显示相同的浮出** 控件。</span><span class="sxs-lookup"><span data-stu-id="5a860-148">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![在安全与合规中心中，邮件&延迟详细信息](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="5a860-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a860-150">See also</span></span>

<span data-ttu-id="5a860-151">有关邮件流仪表板中的其他见解的信息，请参阅安全与合规中心 [中的&见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="5a860-151">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
