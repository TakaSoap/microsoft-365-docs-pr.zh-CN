---
title: 通过 Microsoft 365 Defender 配置和管理 Microsoft 威胁专家功能
description: 通过 Microsoft 365 Defender 订阅 Microsoft 威胁专家，以在日常安全操作和安全管理工作中配置、管理和使用它。
keywords: Microsoft 威胁专家， 托管威胁搜寻服务， MTE， Microsoft 托管搜寻服务
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-maave
author: martyav
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.topic: article
ms.openlocfilehash: e1ccd4404eb94193695239def7f26ba64e70d51d
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476511"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities-through-microsoft-365-defender"></a><span data-ttu-id="9a24a-104">通过 Microsoft 365 Defender 配置和管理 Microsoft 威胁专家功能</span><span class="sxs-lookup"><span data-stu-id="9a24a-104">Configure and manage Microsoft Threat Experts capabilities through Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9a24a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9a24a-105">**Applies to:**</span></span>

- [<span data-ttu-id="9a24a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a24a-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="9a24a-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9a24a-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="9a24a-108">准备工作</span><span class="sxs-lookup"><span data-stu-id="9a24a-108">Before you begin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a24a-109">在应用之前，请务必与 Microsoft 技术服务提供商和帐户团队讨论 Microsoft 威胁专家 - 目标攻击通知托管威胁搜寻服务的资格要求。</span><span class="sxs-lookup"><span data-stu-id="9a24a-109">Before you apply, make sure to discuss the eligibility requirements for the Microsoft Threat Experts – Targeted Attack Notifications managed threat hunting service with your Microsoft Technical Service provider and account team.</span></span>

<span data-ttu-id="9a24a-110">若要接收目标攻击通知，你需要已注册设备并部署 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="9a24a-110">To receive targeted attack notifications, you'll need to have Microsoft 365 Defender deployed with devices enrolled.</span></span> <span data-ttu-id="9a24a-111">然后，通过 Microsoft 威胁专家 - 目标攻击通知的 M365 门户提交应用程序。</span><span class="sxs-lookup"><span data-stu-id="9a24a-111">Then, submit an application through the M365 portal for Microsoft Threat Experts - Targeted Attack Notifications.</span></span>

<span data-ttu-id="9a24a-112">联系你的帐户团队或 Microsoft 代表，订阅 Microsoft 威胁专家 - 专家按需订阅。</span><span class="sxs-lookup"><span data-stu-id="9a24a-112">Contact your account team or Microsoft representative to subscribe to Microsoft Threat Experts - Experts on Demand.</span></span> <span data-ttu-id="9a24a-113">按需专家让你可以咨询我们的威胁专家，了解如何保护你的组织免受相关检测和攻击。</span><span class="sxs-lookup"><span data-stu-id="9a24a-113">Experts on Demand lets you consult with our threat experts on how to protect your organization from relevant detections and adversaries.</span></span>

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a><span data-ttu-id="9a24a-114">适用于 Microsoft 威胁专家 - 目标攻击通知服务</span><span class="sxs-lookup"><span data-stu-id="9a24a-114">Apply for Microsoft Threat Experts - Targeted Attack Notifications service</span></span>

<span data-ttu-id="9a24a-115">如果你已拥有适用于终结点的 Microsoft Defender 和 Microsoft 365 Defender，可以通过 Microsoft 365 Defender 门户申请 Microsoft 威胁专家 - 目标攻击通知。</span><span class="sxs-lookup"><span data-stu-id="9a24a-115">If you already have Microsoft Defender for Endpoint and Microsoft 365 Defender, you can apply for Microsoft Threat Experts – Targeted Attack Notifications through their Microsoft 365 Defender portal.</span></span>  <span data-ttu-id="9a24a-116">目标攻击通知可让你获得特殊的见解和分析，以帮助确定对组织最重要的威胁，以便你可以快速响应它们。</span><span class="sxs-lookup"><span data-stu-id="9a24a-116">Targeted attack notifications grant you special insight and analysis to help identify the most critical threats to your organization, so you can respond to them quickly.</span></span>

1. <span data-ttu-id="9a24a-117">从导航窗格中，转到设置 > 终结点>常规>高级> Microsoft 威胁专家 **- 目标攻击通知**。</span><span class="sxs-lookup"><span data-stu-id="9a24a-117">From the navigation pane, go to **Settings > Endpoints > General > Advanced features > Microsoft Threat Experts - Targeted Attack Notifications**.</span></span>

2. <span data-ttu-id="9a24a-118">选择“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="9a24a-118">Select **Apply**.</span></span>

    ![Microsoft 威胁专家设置的图像](../../media/mte/mte-collaboratewithmte.png)

3. <span data-ttu-id="9a24a-120">输入你的姓名和电子邮件地址，以便 Microsoft 可以就你的应用程序联系你。</span><span class="sxs-lookup"><span data-stu-id="9a24a-120">Enter your name and email address so that Microsoft can contact you about your application.</span></span>

    ![Microsoft 威胁专家应用程序的图像](../../media/mte/mte-apply.png)

4. <span data-ttu-id="9a24a-122">阅读 [隐私声明，](https://privacy.microsoft.com/en-us/privacystatement)**然后在完成后选择** 提交。</span><span class="sxs-lookup"><span data-stu-id="9a24a-122">Read the [privacy statement](https://privacy.microsoft.com/en-us/privacystatement), then select **Submit** when you're done.</span></span> <span data-ttu-id="9a24a-123">应用程序获得批准后，您将收到欢迎电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9a24a-123">You'll receive a welcome email once your application is approved.</span></span>

    ![Microsoft 威胁专家应用程序确认图像](../../media/mte/mte-applicationconfirmation.png)

5. <span data-ttu-id="9a24a-125">收到欢迎电子邮件后，将自动开始接收目标攻击通知。</span><span class="sxs-lookup"><span data-stu-id="9a24a-125">After you receive your welcome email, you'll automatically start receiving targeted attack notifications.</span></span>

6. <span data-ttu-id="9a24a-126">可以通过访问"常规"和"高级"功能 **>"终结点>验证>状态**。</span><span class="sxs-lookup"><span data-stu-id="9a24a-126">You can verify your status by visiting **Settings > Endpoints > General > Advanced features**.</span></span> <span data-ttu-id="9a24a-127">获得批准后 **，Microsoft 威胁专家 - 目标攻击** 通知切换将可见并切换 **为打开**。</span><span class="sxs-lookup"><span data-stu-id="9a24a-127">Once approved, the **Microsoft Threat Experts - Targeted Attack Notification** toggle will be visible and switched **On**.</span></span>

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a><span data-ttu-id="9a24a-128">你将在哪里看到来自 Microsoft 威胁专家的定向攻击通知</span><span class="sxs-lookup"><span data-stu-id="9a24a-128">Where you'll see the targeted attack notifications from Microsoft Threat Experts</span></span>

<span data-ttu-id="9a24a-129">可以通过以下媒体从 Microsoft 威胁专家接收目标攻击通知：</span><span class="sxs-lookup"><span data-stu-id="9a24a-129">You can receive targeted attack notification from Microsoft Threat Experts through the following mediums:</span></span>

- <span data-ttu-id="9a24a-130">Microsoft 365 Defender 门户 **的事件** 页面</span><span class="sxs-lookup"><span data-stu-id="9a24a-130">The Microsoft 365 Defender portal's **Incidents** page</span></span>
- <span data-ttu-id="9a24a-131">Microsoft 365 Defender 门户 **的警报** 仪表板</span><span class="sxs-lookup"><span data-stu-id="9a24a-131">The Microsoft 365 Defender portal's **Alerts** dashboard</span></span>
- <span data-ttu-id="9a24a-132">OData 警报 [API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/get-alerts) 和 [REST API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span><span class="sxs-lookup"><span data-stu-id="9a24a-132">OData alerting [API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/get-alerts) and [REST API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span></span>
- <span data-ttu-id="9a24a-133">[高级搜寻中的 DeviceAlertEvents](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) 表</span><span class="sxs-lookup"><span data-stu-id="9a24a-133">[DeviceAlertEvents](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) table in Advanced hunting</span></span>
- <span data-ttu-id="9a24a-134">如果你选择通过电子邮件将目标攻击通知发送给你的收件箱。</span><span class="sxs-lookup"><span data-stu-id="9a24a-134">Your inbox, if you choose to have targeted attack notifications sent to you via email.</span></span> <span data-ttu-id="9a24a-135">请参阅 [下面的创建电子邮件通知](#create-an-email-notification-rule) 规则。</span><span class="sxs-lookup"><span data-stu-id="9a24a-135">See [Create an email notification rule](#create-an-email-notification-rule) below.</span></span>

### <a name="create-an-email-notification-rule"></a><span data-ttu-id="9a24a-136">创建电子邮件通知规则</span><span class="sxs-lookup"><span data-stu-id="9a24a-136">Create an email notification rule</span></span>

<span data-ttu-id="9a24a-137">可以创建规则来发送通知收件人的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="9a24a-137">You can create rules to send email notifications for notification recipients.</span></span> <span data-ttu-id="9a24a-138">有关完整详细信息，请参阅  [配置警报通知](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) 以创建、编辑、删除或解决电子邮件通知问题。</span><span class="sxs-lookup"><span data-stu-id="9a24a-138">For full details, see  [Configure alert notifications](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) to create, edit, delete, or troubleshoot email notification.</span></span>

## <a name="view-targeted-attack-notifications"></a><span data-ttu-id="9a24a-139">查看目标攻击通知</span><span class="sxs-lookup"><span data-stu-id="9a24a-139">View targeted attack notifications</span></span>

<span data-ttu-id="9a24a-140">在将系统配置为接收电子邮件通知后，你将开始在电子邮件中收到来自 Microsoft 威胁专家的定向攻击通知。</span><span class="sxs-lookup"><span data-stu-id="9a24a-140">You'll start receiving targeted attack notification from Microsoft Threat Experts in your email after you have configured your system to receive email notification.</span></span>

1. <span data-ttu-id="9a24a-141">选择电子邮件中的链接，转到使用威胁专家标记的仪表板中的相应 **警报上下文**。</span><span class="sxs-lookup"><span data-stu-id="9a24a-141">Select the link in the email to go to the corresponding alert context in the dashboard tagged with **Threat experts**.</span></span>

2. <span data-ttu-id="9a24a-142">从 **"警报"** 页面，选择与在电子邮件中收到的警报主题相同的警报主题，以查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="9a24a-142">From the **Alerts** page, select the same alert topic as the one you received in the email, to view further details.</span></span>

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="9a24a-143">订阅 Microsoft 威胁专家 - 专家按需</span><span class="sxs-lookup"><span data-stu-id="9a24a-143">Subscribe to Microsoft Threat Experts - Experts on Demand</span></span>

<span data-ttu-id="9a24a-144">如果你已经是适用于 Endpoint 的 Microsoft Defender 客户，你可以联系你的 Microsoft 代表来订阅 Microsoft 威胁专家 - 专家按需服务。</span><span class="sxs-lookup"><span data-stu-id="9a24a-144">If you're already a Microsoft Defender for Endpoint customer, you can contact your Microsoft representative to subscribe to Microsoft Threat Experts - Experts on Demand.</span></span>

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a><span data-ttu-id="9a24a-145">咨询 Microsoft 威胁专家，了解组织中可疑的网络安全活动</span><span class="sxs-lookup"><span data-stu-id="9a24a-145">Consult a Microsoft threat expert about suspicious cybersecurity activities in your organization</span></span>

<span data-ttu-id="9a24a-146">你可以从 Microsoft 365 Defender 门户内联系 Microsoft 威胁专家。</span><span class="sxs-lookup"><span data-stu-id="9a24a-146">You can contact Microsoft Threat Experts from inside the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="9a24a-147">专家可以帮助你了解复杂的威胁和目标攻击通知。</span><span class="sxs-lookup"><span data-stu-id="9a24a-147">Experts can help you understand complex threats and targeted attack notifications.</span></span> <span data-ttu-id="9a24a-148">与专家合作，进一步了解有关警报和事件的详细信息，或提供有关处理泄露的建议。</span><span class="sxs-lookup"><span data-stu-id="9a24a-148">Partner with experts for further details about alerts and incidents, or advice on handling compromise.</span></span> <span data-ttu-id="9a24a-149">深入了解门户仪表板描述的威胁情报上下文。</span><span class="sxs-lookup"><span data-stu-id="9a24a-149">Gain insight into the threat intelligence context described by your portal dashboard.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="9a24a-150">目前不支持与组织的自定义威胁情报数据相关的警报查询。</span><span class="sxs-lookup"><span data-stu-id="9a24a-150">Alert inquiries related to your organization's customized threat intelligence data are not currently supported.</span></span> <span data-ttu-id="9a24a-151">有关详细信息，请咨询安全运营或事件响应团队。</span><span class="sxs-lookup"><span data-stu-id="9a24a-151">Consult with your security operations or incident response team for details.</span></span>
> - <span data-ttu-id="9a24a-152">你需要拥有 Microsoft  365 Defender 门户中的"在安全中心中管理安全设置"权限，才能通过"咨询威胁专家"表单 **提交查询。**</span><span class="sxs-lookup"><span data-stu-id="9a24a-152">You need to have the **Manage security settings in Security Center** permission in the Microsoft 365 Defender portal to submit an inquiry through the **Consult a threat expert** form.</span></span>

1. <span data-ttu-id="9a24a-153">导航到与要调查的信息相关的门户页面：例如， **设备**、 **警报** 或 **事件**。</span><span class="sxs-lookup"><span data-stu-id="9a24a-153">Navigate to the portal page related to the information that you'd like to investigate: for example, **Device**, **Alert**, or **Incident**.</span></span> <span data-ttu-id="9a24a-154">发送调查请求之前，请确保已查看与查询相关的门户页面。</span><span class="sxs-lookup"><span data-stu-id="9a24a-154">Make sure that the portal page related to your inquiry is in view before you send an investigation request.</span></span>

2. <span data-ttu-id="9a24a-155">从顶部菜单中，选择 **？咨询威胁专家**。</span><span class="sxs-lookup"><span data-stu-id="9a24a-155">From the top menu, select **? Consult a threat expert**.</span></span>

    ![来自菜单的 Microsoft 威胁专家按需专家的图像](../../media/mte/incidents-action-mte-highlighted.png)

    <span data-ttu-id="9a24a-157">将打开一个飞出屏幕。</span><span class="sxs-lookup"><span data-stu-id="9a24a-157">A flyout screen will open.</span></span>

    <span data-ttu-id="9a24a-158">标头将指示你是在试用订阅，还是使用完整的 Microsoft 威胁专家 - 专家按需订阅。</span><span class="sxs-lookup"><span data-stu-id="9a24a-158">The header will indicate if you are on a trial subscription, or a full Microsoft Threat Experts - Experts on-Demand subscription.</span></span>

    ![Microsoft 威胁专家按需试用订阅屏幕的图像](../../media/mte/mte-trial.png)

    <span data-ttu-id="9a24a-160">" **调查** "主题字段已经填充了指向请求相关页面的链接。</span><span class="sxs-lookup"><span data-stu-id="9a24a-160">The **Investigation topic** field will already be populated with the link to the relevant page for your request.</span></span>

3. <span data-ttu-id="9a24a-161">In the next field， provide enough information to give the Microsoft Threat Experts enough context to start the investigation.</span><span class="sxs-lookup"><span data-stu-id="9a24a-161">In the next field, provide enough information to give the Microsoft Threat Experts enough context to start the investigation.</span></span>

4. <span data-ttu-id="9a24a-162">输入要用于与 Microsoft 威胁专家对应的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="9a24a-162">Enter the email address that you'd like to use to correspond with Microsoft Threat Experts.</span></span>

> [!NOTE]
> <span data-ttu-id="9a24a-163">如果要通过 Microsoft 服务中心跟踪专家按需案例的状态，请联系你的技术客户经理。</span><span class="sxs-lookup"><span data-stu-id="9a24a-163">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your technical account manager.</span></span>

<span data-ttu-id="9a24a-164">观看此视频，快速概览 Microsoft 服务中心。</span><span class="sxs-lookup"><span data-stu-id="9a24a-164">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics"></a><span data-ttu-id="9a24a-165">示例调查主题</span><span class="sxs-lookup"><span data-stu-id="9a24a-165">Sample investigation topics</span></span>

### <a name="alert-information"></a><span data-ttu-id="9a24a-166">警报信息</span><span class="sxs-lookup"><span data-stu-id="9a24a-166">Alert information</span></span>

- <span data-ttu-id="9a24a-167">我们看到了一种新型的针对非陆地二进制文件的警报。</span><span class="sxs-lookup"><span data-stu-id="9a24a-167">We saw a new type of alert for a living-off-the-land binary.</span></span> <span data-ttu-id="9a24a-168">我们可以提供警报 ID。</span><span class="sxs-lookup"><span data-stu-id="9a24a-168">We can provide the alert ID.</span></span> <span data-ttu-id="9a24a-169">能否告诉我们有关此警报以及如何进一步调查此警报的更多信息？</span><span class="sxs-lookup"><span data-stu-id="9a24a-169">Can you tell us more about this alert and how we can investigate it further?</span></span>
- <span data-ttu-id="9a24a-170">我们观察到两个类似的攻击，它们尝试执行恶意 PowerShell 脚本，但生成不同的警报。</span><span class="sxs-lookup"><span data-stu-id="9a24a-170">We've observed two similar attacks, which both try to execute malicious PowerShell scripts but generate different alerts.</span></span> <span data-ttu-id="9a24a-171">一种是"可疑 PowerShell 命令行"，另一种是"根据 O365 提供的指示检测到恶意文件"。</span><span class="sxs-lookup"><span data-stu-id="9a24a-171">One is "Suspicious PowerShell command line" and the other is "A malicious file was detected based on indication provided by O365".</span></span> <span data-ttu-id="9a24a-172">区别是什么？</span><span class="sxs-lookup"><span data-stu-id="9a24a-172">What is the difference?</span></span>
- <span data-ttu-id="9a24a-173">今天，我们收到一个有关高配置文件用户设备登录失败异常数量的奇数警报。</span><span class="sxs-lookup"><span data-stu-id="9a24a-173">We received an odd alert today about an abnormal number of failed logins from a high profile user’s device.</span></span> <span data-ttu-id="9a24a-174">我们找不到有关这些尝试的任何进一步证据。</span><span class="sxs-lookup"><span data-stu-id="9a24a-174">We can't find any further evidence for these attempts.</span></span> <span data-ttu-id="9a24a-175">Microsoft 365 Defender 如何查看这些尝试？</span><span class="sxs-lookup"><span data-stu-id="9a24a-175">How can Microsoft 365 Defender see these attempts?</span></span> <span data-ttu-id="9a24a-176">监视的登录类型是什么？</span><span class="sxs-lookup"><span data-stu-id="9a24a-176">What type of logins are being monitored?</span></span>
- <span data-ttu-id="9a24a-177">能否提供关于警报的更多上下文或见解，"已观察到系统实用工具的可疑行为"？</span><span class="sxs-lookup"><span data-stu-id="9a24a-177">Can you give more context or insight about the alert, "Suspicious behavior by a system utility was observed"?</span></span>
- <span data-ttu-id="9a24a-178">我观察到名为"创建转发/重定向规则"的警报。</span><span class="sxs-lookup"><span data-stu-id="9a24a-178">I observed an alert titled "Creation of forwarding/redirect rule".</span></span> <span data-ttu-id="9a24a-179">我认为活动是良好的。</span><span class="sxs-lookup"><span data-stu-id="9a24a-179">I believe the activity is benign.</span></span> <span data-ttu-id="9a24a-180">能否告诉我为什么收到警报？</span><span class="sxs-lookup"><span data-stu-id="9a24a-180">Can you tell me why I received an alert?</span></span>

### <a name="possible-machine-compromise"></a><span data-ttu-id="9a24a-181">可能的机器入侵</span><span class="sxs-lookup"><span data-stu-id="9a24a-181">Possible machine compromise</span></span>

- <span data-ttu-id="9a24a-182">你可以帮助解释我们为何在组织中很多设备上看到有关"观察到的未知进程"的消息或警报？</span><span class="sxs-lookup"><span data-stu-id="9a24a-182">Can you help explain why we see a message or alert for "Unknown process observed" on many devices in our organization?</span></span> <span data-ttu-id="9a24a-183">感谢你的任何输入来阐明此消息或警报是否与恶意活动相关。</span><span class="sxs-lookup"><span data-stu-id="9a24a-183">We appreciate any input to clarify whether this message or alert is related to malicious activity.</span></span>
- <span data-ttu-id="9a24a-184">你能否帮助验证从上周开始在下列系统上可能遭到入侵？</span><span class="sxs-lookup"><span data-stu-id="9a24a-184">Can you help validate a possible compromise on the following system, dating from last week?</span></span> <span data-ttu-id="9a24a-185">其行为类似于六个月之前对同一系统进行恶意软件检测的行为。</span><span class="sxs-lookup"><span data-stu-id="9a24a-185">It's behaving similarly as a previous malware detection on the same system six months ago.</span></span>

### <a name="threat-intelligence-details"></a><span data-ttu-id="9a24a-186">威胁情报详细信息</span><span class="sxs-lookup"><span data-stu-id="9a24a-186">Threat intelligence details</span></span>

- <span data-ttu-id="9a24a-187">我们检测到一封钓鱼电子邮件，该电子邮件向用户传递了恶意 Word 文档。</span><span class="sxs-lookup"><span data-stu-id="9a24a-187">We detected a phishing email that delivered a malicious Word document to a user.</span></span> <span data-ttu-id="9a24a-188">文档引发了一系列可疑事件，从而触发了针对特定恶意软件系列的多个警报。</span><span class="sxs-lookup"><span data-stu-id="9a24a-188">The document caused a series of suspicious events, which triggered multiple alerts for a particular malware family.</span></span> <span data-ttu-id="9a24a-189">你是否有关于此恶意软件的信息？</span><span class="sxs-lookup"><span data-stu-id="9a24a-189">Do you have any information on this malware?</span></span> <span data-ttu-id="9a24a-190">如果是，能否向我们发送链接？</span><span class="sxs-lookup"><span data-stu-id="9a24a-190">If yes, can you send us a link?</span></span>
- <span data-ttu-id="9a24a-191">我们最近看到一篇有关针对我们行业的威胁的博客文章。</span><span class="sxs-lookup"><span data-stu-id="9a24a-191">We recently saw a blog post about a threat that is targeting our industry.</span></span> <span data-ttu-id="9a24a-192">你可以帮助我们了解 Microsoft 365 Defender 针对此威胁参与者提供的保护吗？</span><span class="sxs-lookup"><span data-stu-id="9a24a-192">Can you help us understand what protection Microsoft 365 Defender provides against this threat actor?</span></span>
- <span data-ttu-id="9a24a-193">我们最近观察到了针对我们的组织进行的网络钓鱼活动。</span><span class="sxs-lookup"><span data-stu-id="9a24a-193">We recently observed a phishing campaign conducted against our organization.</span></span> <span data-ttu-id="9a24a-194">能否告诉我们这是专门针对我们的公司还是垂直市场？</span><span class="sxs-lookup"><span data-stu-id="9a24a-194">Can you tell us if this was targeted specifically to our company or vertical?</span></span>

### <a name="microsoft-threat-experts-alert-communications"></a><span data-ttu-id="9a24a-195">Microsoft 威胁专家的警报通信</span><span class="sxs-lookup"><span data-stu-id="9a24a-195">Microsoft Threat Experts’ alert communications</span></span>

- <span data-ttu-id="9a24a-196">事件响应团队能否帮助我们处理我们得到的目标攻击通知？</span><span class="sxs-lookup"><span data-stu-id="9a24a-196">Can your incident response team help us address the targeted attack notification that we got?</span></span>
- <span data-ttu-id="9a24a-197">我们收到了来自 Microsoft 威胁专家的此目标攻击通知。</span><span class="sxs-lookup"><span data-stu-id="9a24a-197">We received this targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="9a24a-198">我们还没有自己的事件响应团队。</span><span class="sxs-lookup"><span data-stu-id="9a24a-198">We don’t have our own incident response team.</span></span> <span data-ttu-id="9a24a-199">现在，我们可以做什么，如何包含事件？</span><span class="sxs-lookup"><span data-stu-id="9a24a-199">What can we do now, and how can we contain the incident?</span></span>
- <span data-ttu-id="9a24a-200">我们收到了来自 Microsoft 威胁专家的定向攻击通知。</span><span class="sxs-lookup"><span data-stu-id="9a24a-200">We received a targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="9a24a-201">您可以向我们提供哪些数据，我们可以将这些数据传递给事件响应团队？</span><span class="sxs-lookup"><span data-stu-id="9a24a-201">What data can you provide to us that we can pass on to our incident response team?</span></span>

> [!NOTE]
> <span data-ttu-id="9a24a-202">Microsoft 威胁专家是托管威胁搜寻服务，而不是事件响应服务。</span><span class="sxs-lookup"><span data-stu-id="9a24a-202">Microsoft Threat Experts is a managed threat hunting service and not an incident response service.</span></span> <span data-ttu-id="9a24a-203">但是，专家可以在必要时将调查无缝转换到 Microsoft 网络安全解决方案组 (CSG) 的检测和响应团队 () 服务。</span><span class="sxs-lookup"><span data-stu-id="9a24a-203">However, the experts can seamlessly transition the investigation to Microsoft Cybersecurity Solutions Group (CSG)'s Detection and Response Team (DART) services, when necessary.</span></span> <span data-ttu-id="9a24a-204">还可以选择与自己的事件响应团队合作，以解决需要事件响应的问题。</span><span class="sxs-lookup"><span data-stu-id="9a24a-204">You can also opt to engage with your own incident response team to address issues that requires an incident response.</span></span>

## <a name="scenario"></a><span data-ttu-id="9a24a-205">方案</span><span class="sxs-lookup"><span data-stu-id="9a24a-205">Scenario</span></span>

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a><span data-ttu-id="9a24a-206">接收有关托管搜寻查询的进度报告</span><span class="sxs-lookup"><span data-stu-id="9a24a-206">Receive a progress report about your managed hunting inquiry</span></span>

<span data-ttu-id="9a24a-207">Microsoft 威胁专家的响应因你的查询而异。</span><span class="sxs-lookup"><span data-stu-id="9a24a-207">The response from Microsoft Threat Experts will vary according to your inquiry.</span></span> <span data-ttu-id="9a24a-208">你通常会收到以下响应之一：</span><span class="sxs-lookup"><span data-stu-id="9a24a-208">You'll generally receive one of the following responses:</span></span>

- <span data-ttu-id="9a24a-209">需要更多信息才能继续执行调查</span><span class="sxs-lookup"><span data-stu-id="9a24a-209">More information is needed to continue with the investigation</span></span>
- <span data-ttu-id="9a24a-210">需要一个或多个文件示例来确定技术上下文</span><span class="sxs-lookup"><span data-stu-id="9a24a-210">A file or several file samples are needed to determine the technical context</span></span>
- <span data-ttu-id="9a24a-211">调查需要更多时间</span><span class="sxs-lookup"><span data-stu-id="9a24a-211">Investigation requires more time</span></span>
- <span data-ttu-id="9a24a-212">初始信息足以结束调查</span><span class="sxs-lookup"><span data-stu-id="9a24a-212">Initial information was enough to conclude the investigation</span></span>

<span data-ttu-id="9a24a-213">如果专家请求更多信息或文件示例，快速响应以保持调查的运行至关重要。</span><span class="sxs-lookup"><span data-stu-id="9a24a-213">If an expert requests more information or file samples, it's crucial to respond quickly to keep the investigation moving.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a24a-214">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a24a-214">See also</span></span>

- [<span data-ttu-id="9a24a-215">Microsoft 威胁专家概述</span><span class="sxs-lookup"><span data-stu-id="9a24a-215">Microsoft Threat Experts overview</span></span>](microsoft-threat-experts.md)
