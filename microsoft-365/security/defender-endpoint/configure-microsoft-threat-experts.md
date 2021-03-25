---
title: 配置和管理 Microsoft 威胁专家功能
ms.reviewer: ''
description: 注册到 Microsoft 威胁专家，以在日常安全操作和安全管理工作中配置、管理和使用它。
keywords: Microsoft 威胁专家， 托管威胁搜寻服务， MTE， Microsoft 托管搜寻服务
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b578436522998ba88cb58f29c5e303ebe0b1ce45
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166097"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities"></a><span data-ttu-id="1a39f-104">配置和管理 Microsoft 威胁专家功能</span><span class="sxs-lookup"><span data-stu-id="1a39f-104">Configure and manage Microsoft Threat Experts capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1a39f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1a39f-105">**Applies to:**</span></span>
- [<span data-ttu-id="1a39f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1a39f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1a39f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1a39f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1a39f-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="1a39f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1a39f-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="1a39f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="before-you-begin"></a><span data-ttu-id="1a39f-110">准备工作</span><span class="sxs-lookup"><span data-stu-id="1a39f-110">Before you begin</span></span> 
> [!NOTE]
> <span data-ttu-id="1a39f-111">在适用于 Microsoft 威胁专家 - 目标攻击通知托管威胁搜寻服务之前，与 Microsoft 技术服务提供商和帐户团队讨论资格要求。</span><span class="sxs-lookup"><span data-stu-id="1a39f-111">Discuss the eligibility requirements with your Microsoft Technical Service provider and account team before you apply to Microsoft Threat Experts - Targeted Attack Notification managed threat hunting service.</span></span>

<span data-ttu-id="1a39f-112">确保在你的环境中部署了 Defender for Endpoint 并注册了设备，而不只是在实验室设置上。</span><span class="sxs-lookup"><span data-stu-id="1a39f-112">Ensure that you have Defender for Endpoint deployed in your environment with devices enrolled, and not just on a laboratory set-up.</span></span>

<span data-ttu-id="1a39f-113">如果你是适用于终结点的 Defender 客户，你需要申请 **Microsoft 威胁** 专家 - 目标攻击通知，获取特殊的见解和分析，以帮助识别最重要的威胁，以便你可以快速响应它们。</span><span class="sxs-lookup"><span data-stu-id="1a39f-113">If you're a Defender for Endpoint customer, you need to apply for **Microsoft Threat Experts - Targeted Attack Notifications** to get special insights and analysis to help identify the most critical threats, so you can respond to them quickly.</span></span> <span data-ttu-id="1a39f-114">联系你的客户团队或 Microsoft 代表，订阅 **Microsoft 威胁** 专家 - 专家按需咨询我们的威胁专家，了解相关检测和对手。</span><span class="sxs-lookup"><span data-stu-id="1a39f-114">Contact your account team or Microsoft representative to subscribe to **Microsoft Threat Experts - Experts on Demand** to consult with our threat experts on relevant detections and adversaries.</span></span>

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a><span data-ttu-id="1a39f-115">适用于 Microsoft 威胁专家 - 目标攻击通知服务</span><span class="sxs-lookup"><span data-stu-id="1a39f-115">Apply for Microsoft Threat Experts - Targeted Attack Notifications service</span></span> 
<span data-ttu-id="1a39f-116">如果你已经是适用于终结点的 Defender 客户，可以通过 Microsoft Defender 安全中心申请。</span><span class="sxs-lookup"><span data-stu-id="1a39f-116">If you're already a Defender for Endpoint customer, you can apply through the Microsoft Defender Security Center.</span></span> 

1. <span data-ttu-id="1a39f-117">在导航窗格中，转到"设置">"常规> Microsoft 威胁专家 - >攻击通知"中的 **"高级功能"。**</span><span class="sxs-lookup"><span data-stu-id="1a39f-117">From the navigation pane, go to **Settings > General > Advanced features > Microsoft Threat Experts - Targeted Attack Notifications**.</span></span>

2. <span data-ttu-id="1a39f-118">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="1a39f-118">Click **Apply**.</span></span>

    ![Microsoft 威胁专家设置的图像](images/mte-collaboratewithmte.png)

3. <span data-ttu-id="1a39f-120">输入你的姓名和电子邮件地址，以便 Microsoft 可以在你的应用程序上返回给你。</span><span class="sxs-lookup"><span data-stu-id="1a39f-120">Enter your name and email address so that Microsoft can get back to you on your application.</span></span>

    ![Microsoft 威胁专家应用程序的图像](images/mte-apply.png)

4. <span data-ttu-id="1a39f-122">阅读 [隐私声明，](https://privacy.microsoft.com/en-us/privacystatement)**完成后单击提交**。</span><span class="sxs-lookup"><span data-stu-id="1a39f-122">Read the [privacy statement](https://privacy.microsoft.com/en-us/privacystatement), then click **Submit** when you're done.</span></span> <span data-ttu-id="1a39f-123">应用程序获得批准后，您将收到欢迎电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1a39f-123">You will receive a welcome email once your application is approved.</span></span>

    ![Microsoft 威胁专家应用程序确认图像](images/mte-applicationconfirmation.png)

<span data-ttu-id="1a39f-125">接受后，你将收到欢迎电子邮件，并且你将看到"应用"按钮更改为"打开"的切换。</span><span class="sxs-lookup"><span data-stu-id="1a39f-125">When accepted, you will receive a welcome email and you will see the **Apply** button change to a toggle that is “on”.</span></span> <span data-ttu-id="1a39f-126">如果你希望将自己从目标攻击通知服务中退出，请滑动切换"关闭"，然后单击页面底部的"保存首选项"。</span><span class="sxs-lookup"><span data-stu-id="1a39f-126">In case you want to take yourself out of the Targeted Attack Notifications service, slide the toggle “off” and click **Save preferences** at the bottom of the page.</span></span> 

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a><span data-ttu-id="1a39f-127">你将在哪里看到来自 Microsoft 威胁专家的定向攻击通知</span><span class="sxs-lookup"><span data-stu-id="1a39f-127">Where you'll see the targeted attack notifications from Microsoft Threat Experts</span></span> 
<span data-ttu-id="1a39f-128">可以通过以下媒体从 Microsoft 威胁专家接收目标攻击通知：</span><span class="sxs-lookup"><span data-stu-id="1a39f-128">You can receive targeted attack notification from Microsoft Threat Experts through the following medium:</span></span>  
- <span data-ttu-id="1a39f-129">终结点门户的 Defender **事件** 页面</span><span class="sxs-lookup"><span data-stu-id="1a39f-129">The Defender for Endpoint portal's **Incidents** page</span></span> 
- <span data-ttu-id="1a39f-130">Defender for Endpoint 门户 **的警报** 仪表板</span><span class="sxs-lookup"><span data-stu-id="1a39f-130">The Defender for Endpoint portal's **Alerts** dashboard</span></span>  
- <span data-ttu-id="1a39f-131">OData 警报 [API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/get-alerts) 和 [REST API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span><span class="sxs-lookup"><span data-stu-id="1a39f-131">OData alerting [API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/get-alerts) and [REST API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span></span>
- <span data-ttu-id="1a39f-132">[高级搜寻中的 DeviceAlertEvents](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) 表</span><span class="sxs-lookup"><span data-stu-id="1a39f-132">[DeviceAlertEvents](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) table in Advanced hunting</span></span>
- <span data-ttu-id="1a39f-133">您的电子邮件（如果选择进行配置）</span><span class="sxs-lookup"><span data-stu-id="1a39f-133">Your email, if you choose to configure it</span></span> 

<span data-ttu-id="1a39f-134">若要通过电子邮件接收目标攻击通知，请创建电子邮件通知规则。</span><span class="sxs-lookup"><span data-stu-id="1a39f-134">To receive targeted attack notifications through email, create an email notification rule.</span></span>

### <a name="create-an-email-notification-rule"></a><span data-ttu-id="1a39f-135">创建电子邮件通知规则</span><span class="sxs-lookup"><span data-stu-id="1a39f-135">Create an email notification rule</span></span> 
<span data-ttu-id="1a39f-136">可以创建规则来发送通知收件人的电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="1a39f-136">You can create rules to send email notifications for notification recipients.</span></span> <span data-ttu-id="1a39f-137">有关详细信息  [，请参阅配置警报](configure-email-notifications.md) 通知以创建、编辑、删除或解决电子邮件通知问题。</span><span class="sxs-lookup"><span data-stu-id="1a39f-137">See  [Configure alert notifications](configure-email-notifications.md) to create, edit, delete, or troubleshoot email notification, for details.</span></span>

## <a name="view-the-targeted-attack-notification"></a><span data-ttu-id="1a39f-138">查看目标攻击通知</span><span class="sxs-lookup"><span data-stu-id="1a39f-138">View the targeted attack notification</span></span>  
<span data-ttu-id="1a39f-139">在将系统配置为接收电子邮件通知后，你将开始在电子邮件中收到来自 Microsoft 威胁专家的定向攻击通知。</span><span class="sxs-lookup"><span data-stu-id="1a39f-139">You'll start receiving targeted attack notification from Microsoft Threat Experts in your email after you have configured your system to receive email notification.</span></span>  

1. <span data-ttu-id="1a39f-140">单击电子邮件中的链接，转到使用威胁专家标记的仪表板中的相应 **警报上下文**。</span><span class="sxs-lookup"><span data-stu-id="1a39f-140">Click the link in the email to go to the corresponding alert context in the dashboard tagged with **Threat experts**.</span></span> 

2. <span data-ttu-id="1a39f-141">从仪表板中，选择与从电子邮件获得相同的警报主题，以查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="1a39f-141">From the dashboard, select the same alert topic that you got from the email, to view the details.</span></span>  

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="1a39f-142">订阅 Microsoft 威胁专家 - 专家按需</span><span class="sxs-lookup"><span data-stu-id="1a39f-142">Subscribe to Microsoft Threat Experts - Experts on Demand</span></span>
<span data-ttu-id="1a39f-143">这作为订阅服务提供。</span><span class="sxs-lookup"><span data-stu-id="1a39f-143">This is available as a subscription service.</span></span> <span data-ttu-id="1a39f-144">如果你已经是适用于 Endpoint 的 Defender 客户，你可以联系你的 Microsoft 代表，订阅 Microsoft 威胁专家 - 专家按需订阅。</span><span class="sxs-lookup"><span data-stu-id="1a39f-144">If you're already a Defender for Endpoint customer, you can contact your Microsoft representative to subscribe to Microsoft Threat Experts - Experts on Demand.</span></span> 

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a><span data-ttu-id="1a39f-145">咨询 Microsoft 威胁专家，了解组织中可疑的网络安全活动</span><span class="sxs-lookup"><span data-stu-id="1a39f-145">Consult a Microsoft threat expert about suspicious cybersecurity activities in your organization</span></span> 
<span data-ttu-id="1a39f-146">你可以与可直接在 Microsoft Defender 安全中心内参与的 Microsoft 威胁专家合作，以及时准确地做出响应。</span><span class="sxs-lookup"><span data-stu-id="1a39f-146">You can partner with Microsoft Threat Experts who can be engaged directly from within the Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="1a39f-147">专家提供见解，以更好地了解复杂的威胁、你收到的定向攻击通知，或者如果你需要有关警报、可能受到威胁的设备或你在门户仪表板上看到的威胁智能上下文详细信息。</span><span class="sxs-lookup"><span data-stu-id="1a39f-147">Experts provide insights to better understand complex threats, targeted attack notifications that you get, or if you need more information about the alerts, a potentially compromised device, or a threat intelligence context that you see on your portal dashboard.</span></span> 

> [!NOTE]
> - <span data-ttu-id="1a39f-148">目前不支持与组织的自定义威胁情报数据相关的警报查询。</span><span class="sxs-lookup"><span data-stu-id="1a39f-148">Alert inquiries related to your organization's customized threat intelligence data are currently not supported.</span></span> <span data-ttu-id="1a39f-149">有关详细信息，请咨询安全运营或事件响应团队。</span><span class="sxs-lookup"><span data-stu-id="1a39f-149">Consult your security operations or incident response team for details.</span></span>
> - <span data-ttu-id="1a39f-150">你需要在安全中心门户中拥有"管理安全设置"权限，才能提交"咨询威胁专家"查询。</span><span class="sxs-lookup"><span data-stu-id="1a39f-150">You need to have the **Manage security settings** permission in the Security Center portal to be able to submit a "Consult a threat expert" inquiry.</span></span>

1. <span data-ttu-id="1a39f-151">导航到包含要调查的相关信息的门户页面，例如"事件 **"** 页面。</span><span class="sxs-lookup"><span data-stu-id="1a39f-151">Navigate to the portal page with the relevant information that you'd like to investigate, for example, the **Incident** page.</span></span> <span data-ttu-id="1a39f-152">发送调查请求之前，请确保相关警报或设备的页面已查看。</span><span class="sxs-lookup"><span data-stu-id="1a39f-152">Ensure that the page for the relevant alert or device is in view before you send an investigation request.</span></span> 

2. <span data-ttu-id="1a39f-153">从右上角的菜单中，单击" **？"**</span><span class="sxs-lookup"><span data-stu-id="1a39f-153">From the upper right-hand menu, click the **?**</span></span> <span data-ttu-id="1a39f-154">图标。</span><span class="sxs-lookup"><span data-stu-id="1a39f-154">icon.</span></span> <span data-ttu-id="1a39f-155">然后，选择 **"咨询威胁专家"。**</span><span class="sxs-lookup"><span data-stu-id="1a39f-155">Then, select **Consult a threat expert**.</span></span> 

    ![来自菜单的 Microsoft 威胁专家按需专家的图像](images/mte-eod-menu.png)

    <span data-ttu-id="1a39f-157">将打开一个飞出屏幕。</span><span class="sxs-lookup"><span data-stu-id="1a39f-157">A flyout screen opens.</span></span> <span data-ttu-id="1a39f-158">以下屏幕显示你何时使用试用版订阅。</span><span class="sxs-lookup"><span data-stu-id="1a39f-158">The following screen shows when you are on a trial subscription.</span></span>

    ![Microsoft 威胁专家按需屏幕的图像](images/mte-eod.png)

    <span data-ttu-id="1a39f-160">以下屏幕显示你何时使用完整的 Microsoft 威胁专家 - 专家按需订阅。</span><span class="sxs-lookup"><span data-stu-id="1a39f-160">The following screen shows when you are on a full Microsoft Threat Experts - Experts on-Demand subscription.</span></span>

    ![Microsoft 威胁专家按需专家完整订阅屏幕的图像](images/mte-eod-fullsubscription.png)

    <span data-ttu-id="1a39f-162">" **查询"** 主题字段预填充了指向调查请求的相关页面的链接。</span><span class="sxs-lookup"><span data-stu-id="1a39f-162">The **Inquiry topic** field is pre-populated with the link to the relevant page for your investigation request.</span></span> <span data-ttu-id="1a39f-163">例如，指向发出请求时所访问的事件、警报或设备详细信息页面的链接。</span><span class="sxs-lookup"><span data-stu-id="1a39f-163">For example, a link to the incident, alert, or device details page that you were at when you made the request.</span></span>

3.  <span data-ttu-id="1a39f-164">In the next field， provide enough information to give the Microsoft Threat Experts enough context to start the investigation.</span><span class="sxs-lookup"><span data-stu-id="1a39f-164">In the next field, provide enough information to give the Microsoft Threat Experts enough context to start the investigation.</span></span>
  
4. <span data-ttu-id="1a39f-165">输入要用于与 Microsoft 威胁专家对应的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="1a39f-165">Enter the email address that you'd like to use to correspond with Microsoft Threat Experts.</span></span>

> [!NOTE]
> <span data-ttu-id="1a39f-166">如果要通过 Microsoft 服务中心跟踪专家按需案例的状态，请联系你的技术客户经理。</span><span class="sxs-lookup"><span data-stu-id="1a39f-166">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your Technical Account Manager.</span></span> 

<span data-ttu-id="1a39f-167">观看此视频，快速概览 Microsoft 服务中心。</span><span class="sxs-lookup"><span data-stu-id="1a39f-167">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f] 


   
## <a name="sample-investigation-topics-that-you-can-consult-with-microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="1a39f-168">可以咨询 Microsoft 威胁专家 - 按需专家的示例调查主题</span><span class="sxs-lookup"><span data-stu-id="1a39f-168">Sample investigation topics that you can consult with Microsoft Threat Experts - Experts on Demand</span></span> 

<span data-ttu-id="1a39f-169">**警报信息**</span><span class="sxs-lookup"><span data-stu-id="1a39f-169">**Alert information**</span></span>
- <span data-ttu-id="1a39f-170">我们会看到一种针对陆地外活动二进制文件的新警报类型：[AlertID]。</span><span class="sxs-lookup"><span data-stu-id="1a39f-170">We see a new type of alert for a living-off-the-land binary: [AlertID].</span></span> <span data-ttu-id="1a39f-171">能否告诉我们有关此警报以及我们可以如何进一步调查的更多信息？</span><span class="sxs-lookup"><span data-stu-id="1a39f-171">Can you tell us something more about this alert and how we can investigate further?</span></span>
- <span data-ttu-id="1a39f-172">我们观察到两个类似的攻击，它们尝试执行恶意 PowerShell 脚本，但生成不同的警报。</span><span class="sxs-lookup"><span data-stu-id="1a39f-172">We’ve observed two similar attacks, which try to execute malicious PowerShell scripts but generate different alerts.</span></span> <span data-ttu-id="1a39f-173">一种是"可疑 PowerShell 命令行"，另一种是"根据 O365 提供的指示检测到恶意文件"。</span><span class="sxs-lookup"><span data-stu-id="1a39f-173">One is "Suspicious PowerShell command line" and the other is "A malicious file was detected based on indication provided by O365".</span></span> <span data-ttu-id="1a39f-174">区别是什么？</span><span class="sxs-lookup"><span data-stu-id="1a39f-174">What is the difference?</span></span>
- <span data-ttu-id="1a39f-175">今天，我收到一个有关高配置文件用户设备登录失败异常数量的奇数警报。</span><span class="sxs-lookup"><span data-stu-id="1a39f-175">I receive an odd alert today for abnormal number of failed logins from a high profile user’s device.</span></span> <span data-ttu-id="1a39f-176">我找不到有关这些登录尝试的任何进一步证据。</span><span class="sxs-lookup"><span data-stu-id="1a39f-176">I cannot find any further evidence around these sign-in attempts.</span></span> <span data-ttu-id="1a39f-177">Defender for Endpoint 如何查看这些尝试？</span><span class="sxs-lookup"><span data-stu-id="1a39f-177">How can Defender for Endpoint see these attempts?</span></span> <span data-ttu-id="1a39f-178">正在监视哪种类型的登录？</span><span class="sxs-lookup"><span data-stu-id="1a39f-178">What type of sign-ins are being monitored?</span></span>
- <span data-ttu-id="1a39f-179">能否提供关于此警报的更多上下文或见解："已观察到系统实用工具的可疑行为"。</span><span class="sxs-lookup"><span data-stu-id="1a39f-179">Can you give more context or insights about this alert: “Suspicious behavior by a system utility was observed”.</span></span> 

<span data-ttu-id="1a39f-180">**可能的机器入侵**</span><span class="sxs-lookup"><span data-stu-id="1a39f-180">**Possible machine compromise**</span></span>
- <span data-ttu-id="1a39f-181">能否帮助回答我们为何看到"观察到的未知进程？"</span><span class="sxs-lookup"><span data-stu-id="1a39f-181">Can you help answer why we see “Unknown process observed?”</span></span> <span data-ttu-id="1a39f-182">此消息或警报在许多设备上经常看到。</span><span class="sxs-lookup"><span data-stu-id="1a39f-182">This message or alert is seen frequently on many devices.</span></span> <span data-ttu-id="1a39f-183">感谢你的任何输入来阐明此消息或警报是否与恶意活动相关。</span><span class="sxs-lookup"><span data-stu-id="1a39f-183">We appreciate any input to clarify whether this message or alert is related to malicious activity.</span></span>
- <span data-ttu-id="1a39f-184">是否有助于验证以下系统在 [date] 上可能遭到入侵，其行为与 [month] 中的同一系统上之前的 [恶意软件名称] 恶意软件检测行为类似？</span><span class="sxs-lookup"><span data-stu-id="1a39f-184">Can you help validate a possible compromise on the following system on [date] with similar behaviors as the previous [malware name] malware detection on the same system in [month]?</span></span>

<span data-ttu-id="1a39f-185">**威胁情报详细信息**</span><span class="sxs-lookup"><span data-stu-id="1a39f-185">**Threat intelligence details**</span></span>
- <span data-ttu-id="1a39f-186">我们检测到一封钓鱼电子邮件，该电子邮件向用户传递了恶意 Word 文档。</span><span class="sxs-lookup"><span data-stu-id="1a39f-186">We detected a phishing email that delivered a malicious Word document to a user.</span></span> <span data-ttu-id="1a39f-187">恶意 Word 文档引发了一系列可疑事件，触发了针对 [恶意软件名称] 恶意软件的多个 Microsoft Defender 警报。</span><span class="sxs-lookup"><span data-stu-id="1a39f-187">The malicious Word document caused a series of suspicious events, which triggered multiple Microsoft Defender alerts for [malware name] malware.</span></span> <span data-ttu-id="1a39f-188">你是否有关于此恶意软件的信息？</span><span class="sxs-lookup"><span data-stu-id="1a39f-188">Do you have any information on this malware?</span></span> <span data-ttu-id="1a39f-189">如果是，可以向我发送链接吗？</span><span class="sxs-lookup"><span data-stu-id="1a39f-189">If yes, can you send me a link?</span></span>
- <span data-ttu-id="1a39f-190">我最近看到[社交媒体参考，例如 Twitter 或博客]文章，关于面向我的行业的威胁。</span><span class="sxs-lookup"><span data-stu-id="1a39f-190">I recently saw a [social media reference, for example, Twitter or blog] post about a threat that is targeting my industry.</span></span> <span data-ttu-id="1a39f-191">你可以帮助我了解针对此威胁参与者的 Defender 提供什么保护？</span><span class="sxs-lookup"><span data-stu-id="1a39f-191">Can you help me understand what protection Defender for Endpoint provides against this threat actor?</span></span> 

<span data-ttu-id="1a39f-192">**Microsoft 威胁专家的警报通信**</span><span class="sxs-lookup"><span data-stu-id="1a39f-192">**Microsoft Threat Experts’ alert communications**</span></span> 
- <span data-ttu-id="1a39f-193">事件响应团队能否帮助我们处理我们得到的目标攻击通知？</span><span class="sxs-lookup"><span data-stu-id="1a39f-193">Can your incident response team help us address the targeted attack notification that we got?</span></span>
- <span data-ttu-id="1a39f-194">我收到了来自 Microsoft 威胁专家的此目标攻击通知。</span><span class="sxs-lookup"><span data-stu-id="1a39f-194">I received this targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="1a39f-195">我们还没有自己的事件响应团队。</span><span class="sxs-lookup"><span data-stu-id="1a39f-195">We don’t have our own incident response team.</span></span> <span data-ttu-id="1a39f-196">现在，我们可以做什么，如何包含事件？</span><span class="sxs-lookup"><span data-stu-id="1a39f-196">What can we do now, and how can we contain the incident?</span></span>
- <span data-ttu-id="1a39f-197">我收到了来自 Microsoft 威胁专家的定向攻击通知。</span><span class="sxs-lookup"><span data-stu-id="1a39f-197">I received a targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="1a39f-198">您可以向我们提供哪些数据，我们可以将这些数据传递给事件响应团队？</span><span class="sxs-lookup"><span data-stu-id="1a39f-198">What data can you provide to us that we can pass on to our incident response team?</span></span>

  >[!NOTE]
  ><span data-ttu-id="1a39f-199">Microsoft 威胁专家是一项托管网络安全搜寻服务，而不是事件响应服务。</span><span class="sxs-lookup"><span data-stu-id="1a39f-199">Microsoft Threat Experts is a managed cybersecurity hunting service and not an incident response service.</span></span> <span data-ttu-id="1a39f-200">但是，专家可以在必要时将调查无缝转换到 Microsoft 网络安全解决方案组 (CSG) 的检测和响应团队 () 服务。</span><span class="sxs-lookup"><span data-stu-id="1a39f-200">However, the experts can seamlessly transition the investigation to Microsoft Cybersecurity Solutions Group (CSG)'s  Detection and Response Team (DART) services, when necessary.</span></span> <span data-ttu-id="1a39f-201">还可以选择与自己的事件响应团队合作，以解决需要事件响应的问题。</span><span class="sxs-lookup"><span data-stu-id="1a39f-201">You can also opt to engage with your own incident response team to address issues that requires an incident response.</span></span> 

## <a name="scenario"></a><span data-ttu-id="1a39f-202">方案</span><span class="sxs-lookup"><span data-stu-id="1a39f-202">Scenario</span></span>

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a><span data-ttu-id="1a39f-203">接收有关托管搜寻查询的进度报告</span><span class="sxs-lookup"><span data-stu-id="1a39f-203">Receive a progress report about your managed hunting inquiry</span></span> 
<span data-ttu-id="1a39f-204">Microsoft 威胁专家的响应因你的查询而异。</span><span class="sxs-lookup"><span data-stu-id="1a39f-204">Response from Microsoft Threat Experts varies according to your inquiry.</span></span> <span data-ttu-id="1a39f-205">他们将在两天内通过电子邮件向你发送关于咨询威胁专家查询的进度报告，以传达以下类别的调查状态：</span><span class="sxs-lookup"><span data-stu-id="1a39f-205">They will email a progress report to you about your **Consult a threat expert** inquiry within two days, to communicate the investigation status from the following categories:</span></span> 
- <span data-ttu-id="1a39f-206">需要更多信息才能继续执行调查</span><span class="sxs-lookup"><span data-stu-id="1a39f-206">More information is needed to continue with the investigation</span></span> 
- <span data-ttu-id="1a39f-207">需要一个或多个文件示例来确定技术上下文</span><span class="sxs-lookup"><span data-stu-id="1a39f-207">A file or several file samples are needed to determine the technical context</span></span> 
- <span data-ttu-id="1a39f-208">调查需要更多时间</span><span class="sxs-lookup"><span data-stu-id="1a39f-208">Investigation requires more time</span></span>   
- <span data-ttu-id="1a39f-209">初始信息足以结束调查</span><span class="sxs-lookup"><span data-stu-id="1a39f-209">Initial information was enough to conclude the investigation</span></span> 

<span data-ttu-id="1a39f-210">快速响应以保持调查的运行至关重要。</span><span class="sxs-lookup"><span data-stu-id="1a39f-210">It is crucial to respond in quickly to keep the investigation moving.</span></span> 

## <a name="related-topic"></a><span data-ttu-id="1a39f-211">相关主题</span><span class="sxs-lookup"><span data-stu-id="1a39f-211">Related topic</span></span>
- [<span data-ttu-id="1a39f-212">Microsoft 威胁专家概述</span><span class="sxs-lookup"><span data-stu-id="1a39f-212">Microsoft Threat Experts overview</span></span>](microsoft-threat-experts.md)
