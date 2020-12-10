---
title: 邮件流仪表板中的队列洞察力
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 管理员可以了解如何在安全 & 合规性中心中使用邮件流仪表板中的 "队列" 小部件，以通过出站连接器监视到其内部部署或合作伙伴组织的未成功邮件流。
ms.openlocfilehash: c582a7f459d89fa1515713c4f55dea14b619a6ec
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616388"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="ac8ec-103">队列在安全 & 合规中心中的洞察力</span><span class="sxs-lookup"><span data-stu-id="ac8ec-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ac8ec-104">当无法使用连接器从组织向内部部署或合作伙伴电子邮件服务器发送邮件时，邮件将在 Microsoft 365 中排队。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-104">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="ac8ec-105">导致出现此情况的常见示例为：</span><span class="sxs-lookup"><span data-stu-id="ac8ec-105">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="ac8ec-106">连接器配置不正确。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-106">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="ac8ec-107">本地环境中的网络或防火墙发生变化。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-107">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="ac8ec-108">Microsoft 365 将继续重试传递24小时。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-108">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="ac8ec-109">24小时后，邮件将会过期，并将返回到未送达报告中的发件人 (也称为 "Ndr" 或 "退回邮件") 。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-109">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="ac8ec-110">如果排队的电子邮件量超过预定义的阈值 (默认值为 200) 的邮件，则可在以下位置获取这些信息：</span><span class="sxs-lookup"><span data-stu-id="ac8ec-110">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="ac8ec-111">[安全 & 合规性中心](https://protection.office.com)中的 [邮件流仪表板](mail-flow-insights-v2.md)中的 **队列** 洞察力。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-111">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="ac8ec-112">有关详细信息，请参阅本主题中的 [邮件流仪表板](#queues-insight-in-the-mail-flow-dashboard) 部分中的队列洞察力。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-112">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this topic.</span></span>

- <span data-ttu-id="ac8ec-113">在 "[安全 & 合规中心](https://protection.office.com) ("**通知**"  \> **仪表板** 或") 中，"最近" 警报显示在 "警报" 仪表板中 <https://protection.office.com/alertsdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-113">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![安全 & 合规中心中的 "警报" 仪表板中的最近通知](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="ac8ec-115">管理员将根据名为 " **邮件**" 的默认警报策略的配置收到电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-115">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="ac8ec-116">若要配置此通知的通知设置，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-116">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="ac8ec-117">有关通知策略的详细信息，请参阅 [Security & 合规性中心中的警报策略](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-117">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="ac8ec-118">自定义队列通知</span><span class="sxs-lookup"><span data-stu-id="ac8ec-118">Customize queue alerts</span></span>

1. <span data-ttu-id="ac8ec-119">在 [安全 & 合规性中心](https://protection.office.com)中，转到 " **通知**" "通知 \> **策略** " 或 "打开" <https://protection.office.com/alertpolicies> 。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-119">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="ac8ec-120">在 " **通知策略** " 页上，查找并选择名为 "邮件" 的策略已 **延迟**。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-120">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="ac8ec-121">在邮件中打开了 **延迟** 的浮出浮出控件时，您可以打开或关闭通知并配置通知设置。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-121">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![邮件已延迟通知策略详细信息安全 & 合规性中心](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="ac8ec-123">**状态**：您可以打开或关闭通知。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-123">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="ac8ec-124">**电子邮件收件人** 和 **每日通知限制**：单击 " **编辑** " 配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="ac8ec-124">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="ac8ec-125">若要配置通知设置，请单击 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-125">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="ac8ec-126">在出现的 " **编辑策略** " 浮出控件中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="ac8ec-126">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="ac8ec-127">**发送电子邮件通知**：默认值为 "开"。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-127">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="ac8ec-128">**电子邮件收件人**：默认值为 **TenantAdmins**。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-128">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="ac8ec-129">**每日通知限制**：默认值为 **无限制**。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-129">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="ac8ec-130">**阈值**：默认值为200。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-130">**Threshold**: The default value is 200.</span></span>

   ![邮件中的通知设置已延迟警报策略详细信息安全 & 合规性中心](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="ac8ec-132">完成后，单击 " **保存** 并 **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-132">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="ac8ec-133">邮件流仪表板中的队列洞察力</span><span class="sxs-lookup"><span data-stu-id="ac8ec-133">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="ac8ec-134">即使排队邮件卷未超过阈值并生成警报，仍可以使用 [邮件流仪表板](mail-flow-insights-v2.md)中的 **队列** 洞察力查看已排入一小时以上的邮件，并在队列中的邮件数变得过大之前采取措施。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-134">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![安全 & 合规性中心的邮件流仪表板中的 "队列" 小部件](../../media/mfi-queues-widget.png)

<span data-ttu-id="ac8ec-136">如果单击小组件上的邮件数，将显示一条包含以下信息的已 **排队邮件** ：</span><span class="sxs-lookup"><span data-stu-id="ac8ec-136">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="ac8ec-137">**排队邮件数**</span><span class="sxs-lookup"><span data-stu-id="ac8ec-137">**Number of queued messages**</span></span>
- <span data-ttu-id="ac8ec-138">**连接器名称**：单击连接器名称以管理 Exchange 管理中心内的连接器 (EAC) 。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-138">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="ac8ec-139">**队列启动时间**</span><span class="sxs-lookup"><span data-stu-id="ac8ec-139">**Queue started time**</span></span>
- <span data-ttu-id="ac8ec-140">**最旧邮件已过期**</span><span class="sxs-lookup"><span data-stu-id="ac8ec-140">**Oldest messages expired**</span></span>
- <span data-ttu-id="ac8ec-141">**目标服务器**</span><span class="sxs-lookup"><span data-stu-id="ac8ec-141">**Destination server**</span></span>
- <span data-ttu-id="ac8ec-142">**最后一个 IP 地址**</span><span class="sxs-lookup"><span data-stu-id="ac8ec-142">**Last IP address**</span></span>
- <span data-ttu-id="ac8ec-143">**上一个错误**</span><span class="sxs-lookup"><span data-stu-id="ac8ec-143">**Last error**</span></span>
- <span data-ttu-id="ac8ec-144">**如何修复**：共有问题和解决方案可用。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-144">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="ac8ec-145">如果 "是" **立即修复** 链接可用，请单击它以解决问题。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-145">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="ac8ec-146">否则，请单击任何可用的链接，以获取有关错误和可能的解决方案的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-146">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![单击邮件流仪表板中的队列洞察力后的详细信息](../../media/mfi-queues-details.png)

<span data-ttu-id="ac8ec-148">在邮件的详细信息 "**延迟**" 警报中单击 "**查看队列**" 后，将显示相同的浮出控件。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-148">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![邮件已在安全 & 合规中心中延迟警报详细信息](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="ac8ec-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac8ec-150">See also</span></span>

<span data-ttu-id="ac8ec-151">有关邮件流仪表板中的其他见解的信息，请参阅 [Security & 合规性中心中的邮件流见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="ac8ec-151">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
