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
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="feced-103">安全与合规中心&队列见解</span><span class="sxs-lookup"><span data-stu-id="feced-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="feced-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="feced-104">**Applies to**</span></span>
- [<span data-ttu-id="feced-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="feced-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="feced-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="feced-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="feced-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="feced-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="feced-108">当无法将邮件从组织发送到使用连接器本地或合作伙伴电子邮件服务器时，这些邮件将在 Microsoft 365 中排队。</span><span class="sxs-lookup"><span data-stu-id="feced-108">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="feced-109">导致这种情况的常见示例包括：</span><span class="sxs-lookup"><span data-stu-id="feced-109">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="feced-110">连接器配置不正确。</span><span class="sxs-lookup"><span data-stu-id="feced-110">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="feced-111">本地环境中发生了网络或防火墙更改。</span><span class="sxs-lookup"><span data-stu-id="feced-111">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="feced-112">Microsoft 365 将继续重试传递 24 小时。</span><span class="sxs-lookup"><span data-stu-id="feced-112">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="feced-113">24 小时后，这些邮件将过期，并返回到未送达报告中的发件人 (也称为 NDDR 或退回邮件) 。</span><span class="sxs-lookup"><span data-stu-id="feced-113">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="feced-114">如果排队的电子邮件卷超过预定义的阈值 (默认值为 200 封邮件) ，则信息可在以下位置获取：</span><span class="sxs-lookup"><span data-stu-id="feced-114">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="feced-115">安全 **与** 合规中心 [的邮件流仪表板](mail-flow-insights-v2.md) 中的& [见解](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="feced-115">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="feced-116">有关详细信息，请参阅本文"邮件 [流仪表板"](#queues-insight-in-the-mail-flow-dashboard) 部分中的"队列见解"。</span><span class="sxs-lookup"><span data-stu-id="feced-116">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this article.</span></span>

- <span data-ttu-id="feced-117">警报显示在 **安全与合规** 中心内"警报"仪表板中的"最近 [](https://protection.office.com)&警报 ( \> **仪表板** 或 <https://protection.office.com/alertsdashboard>) 。</span><span class="sxs-lookup"><span data-stu-id="feced-117">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![安全与合规中心的警报仪表板中的&警报](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="feced-119">管理员将收到一封电子邮件通知，该通知基于名为"邮件" **的默认警报策略的配置已延迟**。</span><span class="sxs-lookup"><span data-stu-id="feced-119">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="feced-120">若要为此警报配置通知设置，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="feced-120">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="feced-121">有关警报策略详细信息，请参阅安全与合规中心& [策略](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="feced-121">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="feced-122">自定义队列警报</span><span class="sxs-lookup"><span data-stu-id="feced-122">Customize queue alerts</span></span>

1. <span data-ttu-id="feced-123">在 [安全&中心](https://protection.office.com)，转到 **警报** \> **警报策略或** 打开 <https://protection.office.com/alertpolicies> 。</span><span class="sxs-lookup"><span data-stu-id="feced-123">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="feced-124">在 **"警报策略"** 页上，查找并选择名为 **"已延迟的邮件"的策略**。</span><span class="sxs-lookup"><span data-stu-id="feced-124">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="feced-125">在 **打开的"消息"** 已延迟的飞出中，你可以打开或关闭警报并配置通知设置。</span><span class="sxs-lookup"><span data-stu-id="feced-125">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![邮件已延迟警报策略详细信息 安全&合规中心](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="feced-127">**状态**：你可以打开或关闭警报。</span><span class="sxs-lookup"><span data-stu-id="feced-127">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="feced-128">**电子邮件收件人** 和 **每日通知限制**：单击 **"编辑** "配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="feced-128">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="feced-129">若要配置通知设置，请单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="feced-129">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="feced-130">在 **出现的"编辑策略** "飞出中，配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="feced-130">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="feced-131">**发送电子邮件通知**：默认值为打开状态。</span><span class="sxs-lookup"><span data-stu-id="feced-131">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="feced-132">**电子邮件收件人**：默认值为 **TenantAdmins。**</span><span class="sxs-lookup"><span data-stu-id="feced-132">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="feced-133">**每日通知限制**：默认值为 **无限制**。</span><span class="sxs-lookup"><span data-stu-id="feced-133">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="feced-134">**阈值**：默认值为 200。</span><span class="sxs-lookup"><span data-stu-id="feced-134">**Threshold**: The default value is 200.</span></span>

   !["邮件"中的通知设置已延迟警报策略详细信息 安全&合规中心](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="feced-136">完成后，单击"**保存并\*\*\*\*关闭"。**</span><span class="sxs-lookup"><span data-stu-id="feced-136">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="feced-137">邮件流仪表板中的队列见解</span><span class="sxs-lookup"><span data-stu-id="feced-137">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="feced-138">即使排队的邮件卷未超出阈值并生成警报，您仍可以使用邮件流仪表板中的 **"** 队列见解"查看已排队超过 [](mail-flow-insights-v2.md)1 小时的邮件，在排队邮件数量过大之前采取措施。</span><span class="sxs-lookup"><span data-stu-id="feced-138">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![安全与合规中心的邮件流仪表板中的&小组件](../../media/mfi-queues-widget.png)

<span data-ttu-id="feced-140">If you click the number of messages on the widget， a **Messages queued** flyout appears with the following information：</span><span class="sxs-lookup"><span data-stu-id="feced-140">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="feced-141">**排队邮件数**</span><span class="sxs-lookup"><span data-stu-id="feced-141">**Number of queued messages**</span></span>
- <span data-ttu-id="feced-142">**连接器名称**：单击连接器名称以在 Exchange 管理中心或 EAC (管理) 。</span><span class="sxs-lookup"><span data-stu-id="feced-142">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="feced-143">**队列启动时间**</span><span class="sxs-lookup"><span data-stu-id="feced-143">**Queue started time**</span></span>
- <span data-ttu-id="feced-144">**最旧邮件已过期**</span><span class="sxs-lookup"><span data-stu-id="feced-144">**Oldest messages expired**</span></span>
- <span data-ttu-id="feced-145">**目标服务器**</span><span class="sxs-lookup"><span data-stu-id="feced-145">**Destination server**</span></span>
- <span data-ttu-id="feced-146">**最后一个 IP 地址**</span><span class="sxs-lookup"><span data-stu-id="feced-146">**Last IP address**</span></span>
- <span data-ttu-id="feced-147">**上一个错误**</span><span class="sxs-lookup"><span data-stu-id="feced-147">**Last error**</span></span>
- <span data-ttu-id="feced-148">**如何修复**：常见问题和解决方案可用。</span><span class="sxs-lookup"><span data-stu-id="feced-148">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="feced-149">If is a **Fix it now** link is available， click it to fix the problem.</span><span class="sxs-lookup"><span data-stu-id="feced-149">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="feced-150">否则，请单击任何可用链接，了解有关错误和可能的解决方案的详细信息。</span><span class="sxs-lookup"><span data-stu-id="feced-150">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![单击邮件流仪表板中的"队列"见解后的详细信息](../../media/mfi-queues-details.png)

<span data-ttu-id="feced-152">单击"邮件已延迟警报的详细信息 **"中的"** 查看队列"后，将显示 **相同的飞** 出。</span><span class="sxs-lookup"><span data-stu-id="feced-152">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![安全与合规中心内的邮件&警报详细信息](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="feced-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="feced-154">See also</span></span>

<span data-ttu-id="feced-155">有关邮件流仪表板中其他见解的信息，请参阅安全与合规中心& [见解](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="feced-155">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
