---
title: 配置出站垃圾邮件策略
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: 如果您使用出站垃圾邮件筛选来发送出站电子邮件，那么将始终启用该服务，从而保护使用此服务的组织及其目标收件人。
ms.openlocfilehash: 0fa5ec23eee6144864f16b52d452d02f38b554d7
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957337"
---
# <a name="configure-the-outbound-spam-policy"></a><span data-ttu-id="0806e-103">配置出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="0806e-103">Configure the outbound spam policy</span></span>

<span data-ttu-id="0806e-104">如果您使用出站垃圾邮件筛选来发送出站电子邮件，那么将始终启用该服务，从而保护使用此服务的组织及其目标收件人。</span><span class="sxs-lookup"><span data-stu-id="0806e-104">Outbound spam filtering is always enabled if you use the service for sending outbound email, thereby protecting organizations using the service and their intended recipients.</span></span> <span data-ttu-id="0806e-105">与入站筛选类似，出站垃圾邮件筛选由连接筛选和内容筛选组成，并允许某些特定的控件处理出站邮件。</span><span class="sxs-lookup"><span data-stu-id="0806e-105">Similar to inbound filtering, outbound spam filtering is comprised of connection filtering and content filtering and allows some specific controls to handle outbound messages.</span></span> <span data-ttu-id="0806e-106">出站垃圾邮件筛选器策略设置类型：</span><span class="sxs-lookup"><span data-stu-id="0806e-106">Outbound spam filter policy settings types:</span></span>

- <span data-ttu-id="0806e-107">默认：使用默认出站垃圾邮件筛选器策略配置公司范围的出站垃圾邮件筛选器设置。</span><span class="sxs-lookup"><span data-stu-id="0806e-107">Default: The default outbound spam filter policy is used to configure company-wide outbound spam filter settings.</span></span> <span data-ttu-id="0806e-108">无法重命名此策略，并且其始终启用。</span><span class="sxs-lookup"><span data-stu-id="0806e-108">This policy can not be renamed and is always on.</span></span>

- <span data-ttu-id="0806e-109">自定义：自定义出站垃圾邮件筛选器策略可以精细并应用于组织中的特定用户、组或域。</span><span class="sxs-lookup"><span data-stu-id="0806e-109">Custom: Custom outbound spam filter policies can be granular and applied to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="0806e-110">自定义策略的优先级始终高于默认策略。</span><span class="sxs-lookup"><span data-stu-id="0806e-110">Custom policies always take precedence over the default policy.</span></span> <span data-ttu-id="0806e-111">您可以通过更改每个自定义策略的优先级来更改自定义策略的运行顺序;但是，如果用户匹配多个策略，则只有最高优先级（即最接近0的数字）策略适用。</span><span class="sxs-lookup"><span data-stu-id="0806e-111">You can change the order in which your custom policies run by changing the priority of each custom policy; however, only the highest priority (i.e. number closest to 0) policy will apply if the user matches multiple policies.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0806e-112">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="0806e-112">What do you need to know before you begin?</span></span>
<span data-ttu-id="0806e-113"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="0806e-113"><a name="sectionSection0"> </a></span></span>

- <span data-ttu-id="0806e-114">估计完成时间：5 分钟</span><span class="sxs-lookup"><span data-stu-id="0806e-114">Estimated time to complete: 5 minutes</span></span>

- <span data-ttu-id="0806e-115">您必须先获得权限，然后才能执行此过程或多个过程。</span><span class="sxs-lookup"><span data-stu-id="0806e-115">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="0806e-116">若要查看所需的权限，请参阅 [Exchange Online 中的功能权限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)主题中的“反垃圾邮件”条目。</span><span class="sxs-lookup"><span data-stu-id="0806e-116">To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) topic.</span></span>

- <span data-ttu-id="0806e-117">您还可以在远程 PowerShell 中执行本主题中的过程。</span><span class="sxs-lookup"><span data-stu-id="0806e-117">You can also do the procedures in this topic in remote PowerShell.</span></span> <span data-ttu-id="0806e-118">使用[HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy) cmdlet 可查看您的设置，以及用于编辑出站垃圾邮件策略设置的[HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy) 。</span><span class="sxs-lookup"><span data-stu-id="0806e-118">Use the [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy) cmdlet to review your settings, and the [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy) to edit your outbound spam policy settings.</span></span>

  <span data-ttu-id="0806e-119">若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0806e-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0806e-120">若要连接到 Exchange Online Protection PowerShell，请参阅[连接到 Exchange Online Protection powershell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0806e-120">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

## <a name="use-the-security--compliance-center-scc-to-edit-the-default-outbound-spam-policy"></a><span data-ttu-id="0806e-121">使用安全 & 合规性中心（SCC）编辑默认的出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="0806e-121">Use the Security & Compliance Center (SCC) to edit the default outbound spam policy</span></span>

<span data-ttu-id="0806e-122">使用以下步骤编辑默认出站垃圾邮件策略：</span><span class="sxs-lookup"><span data-stu-id="0806e-122">Use the following procedure to edit the default outbound spam policy:</span></span>

### <a name="to-configure-the-default-outbound-spam-policy"></a><span data-ttu-id="0806e-123">要配置默认出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="0806e-123">To configure the default outbound spam policy</span></span>

1. <span data-ttu-id="0806e-124">在 SCC 中，导航到 "**威胁管理** \> **策略** \> **反垃圾邮件**"</span><span class="sxs-lookup"><span data-stu-id="0806e-124">In the SCC, navigate to **Threat Management** \> **Policy** \> **Anti-spam**</span></span>

2. <span data-ttu-id="0806e-125">展开 "**出站垃圾邮件筛选器策略（永不打开）** " 部分，然后单击 "**编辑策略**"。</span><span class="sxs-lookup"><span data-stu-id="0806e-125">Expand the **Outbound spam filter policy (always ON)** section and click **Edit policy**.</span></span>

3. <span data-ttu-id="0806e-126">展开 "**通知**" 部分，选择以下与出站邮件相关的复选框，然后选择 "**添加人员**"，在附带的对话框中添加关联的电子邮件地址或地址。</span><span class="sxs-lookup"><span data-stu-id="0806e-126">Expand the **Notifications** section and select the following check boxes pertaining to outbound messages, then select **Add people** to add an associated email address or addresses in the accompanying dialog box.</span></span> <span data-ttu-id="0806e-127">（如果它们解析为有效的 SMTP 目标，它们可以是通讯组列表）：</span><span class="sxs-lookup"><span data-stu-id="0806e-127">(these can be distribution lists if they resolve as valid SMTP destinations):</span></span>

   - <span data-ttu-id="0806e-128">将**所有可疑的出站电子邮件的副本发送到以下电子邮件地址或地址**：这些邮件被筛选器标记为垃圾邮件（无论 SCL 分级如何）。</span><span class="sxs-lookup"><span data-stu-id="0806e-128">**Send a copy of all suspicious outbound email messages to the following email address or addresses**: These are messages that are marked as spam by the filter (regardless of the SCL rating).</span></span> <span data-ttu-id="0806e-129">它们未被筛选器拒绝，但是将通过高风险传输工具路由。</span><span class="sxs-lookup"><span data-stu-id="0806e-129">They are not rejected by the filter but are routed through the higher risk delivery pool.</span></span> <span data-ttu-id="0806e-130">用分号分隔多个地址。</span><span class="sxs-lookup"><span data-stu-id="0806e-130">Separate multiple addresses with a semicolon.</span></span> <span data-ttu-id="0806e-131">请注意，指定的收件人将作为密件抄送 (Bcc) 地址接收邮件（"发件人"和"收件人"字段是原始的发件人和收件人）。</span><span class="sxs-lookup"><span data-stu-id="0806e-131">Note that the recipients specified will receive the messages as a Blind carbon copy (Bcc) address (the From and To fields are the original sender and recipient).</span></span>

   - <span data-ttu-id="0806e-132">**当发件人被阻止发送出站垃圾邮件时，向以下电子邮件地址发送通知**：使用分号分隔多个地址。</span><span class="sxs-lookup"><span data-stu-id="0806e-132">**Send a notification to the following email address when a sender is blocked sending outbound spam**: Separate multiple addresses with a semicolon.</span></span>

   <span data-ttu-id="0806e-133">当从特定用户检测到大量垃圾邮件或其他发送异常时，将限制该用户发送电子邮件，并将通知发送到指定的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="0806e-133">When a significant amount of spam or other sending anomalies are detected from a particular user, the user is restricted from sending email messages and a notification is sent to the email addresses specified.</span></span>

   <span data-ttu-id="0806e-134">使用该设置指定的域管理员将收到该用户的出站邮件被阻止的通知。</span><span class="sxs-lookup"><span data-stu-id="0806e-134">The administrator for the domain, who is specified using this setting, will be informed that outbound messages are blocked for this user.</span></span>  <span data-ttu-id="0806e-135">若要查看此通知的样式，请参阅[发件人被阻止发送出站垃圾邮件时的示例通知](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="0806e-135">To see what this notification looks like, see [Sample notification when a sender is blocked sending outbound spam](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="0806e-136">还会生成一个系统警报，指示用户已受到限制。</span><span class="sxs-lookup"><span data-stu-id="0806e-136">A system alert is also generated indicating the user has been restricted.</span></span> <span data-ttu-id="0806e-137">若要了解有关警报以及如何恢复用户的详细信息，请参阅[发送垃圾电子邮件后，从受限用户门户中删除用户](removing-user-from-restricted-users-portal-after-spam.md)。</span><span class="sxs-lookup"><span data-stu-id="0806e-137">To learn more about the alert and how to recover the user, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

4. <span data-ttu-id="0806e-138">展开 "**收件人限制**" 部分，指定用户可以向其发送的最大收件人数、内部和外部收件人的每小时收件人数以及每天的最大数量。</span><span class="sxs-lookup"><span data-stu-id="0806e-138">Expand the **Recipient limits** section to specify the maximum number of recipients that a user can send to, per hour for internal and external recipients together with the maximum number per day.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0806e-139">任何输入的最大数量为10000。</span><span class="sxs-lookup"><span data-stu-id="0806e-139">The maximum number for any input is 10000.</span></span> <span data-ttu-id="0806e-140">有关详细信息，请参阅[Exchange online 中的接收和发送限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)</span><span class="sxs-lookup"><span data-stu-id="0806e-140">For more information see [receiving and sending limits within Exchange online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)</span></span>

7. <span data-ttu-id="0806e-141">指定当用户超过指定限制时要执行的**操作**。</span><span class="sxs-lookup"><span data-stu-id="0806e-141">Specify the **action** to take when a user exceeds the specified limits.</span></span>  <span data-ttu-id="0806e-142">可能的操作如下所示：</span><span class="sxs-lookup"><span data-stu-id="0806e-142">The actions that are possible are as follows:</span></span>

   - <span data-ttu-id="0806e-143">**限制用户在以下日期之前发送邮件**。</span><span class="sxs-lookup"><span data-stu-id="0806e-143">**Restrict the user from sending mail till the following day**.</span></span>  <span data-ttu-id="0806e-144">一旦超出任何发送限制（内部、外部或每日），将为管理员生成一个警报，并且用户将无法在下一天（基于 UTC 时间）发送任何后续电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0806e-144">Once any sending limit has been exceeded (internal, external or daily) an alert will be generated for the admin and the user will be unable to send any further email until the following day, based on UTC time.</span></span> <span data-ttu-id="0806e-145">管理员无法替代此块。</span><span class="sxs-lookup"><span data-stu-id="0806e-145">There is no way for the administrator to override this block.</span></span>

   - <span data-ttu-id="0806e-146">**限制用户发送邮件**。</span><span class="sxs-lookup"><span data-stu-id="0806e-146">**Restrict the user from sending mail**.</span></span>  <span data-ttu-id="0806e-147">一旦超出任何发送限制（内部、外部或每日），将为管理员生成一个警报，并且在管理员删除此限制之前，用户将无法再发送任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0806e-147">Once any sending limit has been exceeded (internal, external or daily) an alert will be generated for the admin and the user will be unable to send any further email until the administrator removes the restriction.</span></span>  <span data-ttu-id="0806e-148">在这些情况下，将在 "[受限用户" 页](removing-user-from-restricted-users-portal-after-spam.md)上列出用户。</span><span class="sxs-lookup"><span data-stu-id="0806e-148">In these cases the user will be listed on the [Restricted Users page](removing-user-from-restricted-users-portal-after-spam.md).</span></span>  <span data-ttu-id="0806e-149">从列表中删除后，将不会在那天再次限制用户。</span><span class="sxs-lookup"><span data-stu-id="0806e-149">Once removed from the list the user will not be restricted again for that day.</span></span>

   - <span data-ttu-id="0806e-150">**不执行任何操作/警报**。</span><span class="sxs-lookup"><span data-stu-id="0806e-150">**No Action/Alert only**.</span></span> <span data-ttu-id="0806e-151">一旦超出任何发送限制（内部、外部或每日），将为管理员生成警报，但不会执行任何操作来限制用户。</span><span class="sxs-lookup"><span data-stu-id="0806e-151">Once any sending limit has been exceeded (internal, external or daily) an alert will be generated for the admin but no action will be taken to restrict the user.</span></span>

6. <span data-ttu-id="0806e-152">展开 "**应用**于" 部分，然后创建基于条件的规则，以指定要向其应用此策略的用户、组和域。</span><span class="sxs-lookup"><span data-stu-id="0806e-152">Expand the **Applies to** section and then create a condition-based rule to specify the users, groups, and domains to which to apply this policy.</span></span> <span data-ttu-id="0806e-153">可以创建多个唯一性条件。</span><span class="sxs-lookup"><span data-stu-id="0806e-153">You can create multiple conditions, if they are unique.</span></span>  <span data-ttu-id="0806e-154">注意：如果指定了多个条件，则用户必须满足所有条件。</span><span class="sxs-lookup"><span data-stu-id="0806e-154">Note: that users must meet all the conditions when multiple conditions are specified.</span></span>  

   - <span data-ttu-id="0806e-155">若要选择用户，请选择 **"发件人为"**。</span><span class="sxs-lookup"><span data-stu-id="0806e-155">To select users, select **The sender is**.</span></span> <span data-ttu-id="0806e-156">在随后的对话框中，从用户选取器列表中选择一个或多个公司的发件人，然后单击“添加”。</span><span class="sxs-lookup"><span data-stu-id="0806e-156">In the subsequent dialog box, select one or more senders from your company from the user picker list, and then click add.</span></span> <span data-ttu-id="0806e-157">若要添加列表中没有的发件人，请键入他们的电子邮件地址，并单击“检查姓名”。</span><span class="sxs-lookup"><span data-stu-id="0806e-157">To add senders who aren't on the list, type their email addresses, and then click Check names.</span></span> <span data-ttu-id="0806e-158">完成选择后，单击“确定”返回主屏幕。</span><span class="sxs-lookup"><span data-stu-id="0806e-158">When you are done making your selections, click ok to return to the main screen.</span></span>

   - <span data-ttu-id="0806e-159">若要选择组，请选择 **"发件人是" 的成员**。</span><span class="sxs-lookup"><span data-stu-id="0806e-159">To select groups, select **The sender is a member of**.</span></span> <span data-ttu-id="0806e-160">然后，在随后出现的对话框中选择或指定组。</span><span class="sxs-lookup"><span data-stu-id="0806e-160">Then, in the subsequent dialog box, select or specify the groups.</span></span> <span data-ttu-id="0806e-161">单击"确定"返回到主屏幕。</span><span class="sxs-lookup"><span data-stu-id="0806e-161">Click ok to return to the main screen.</span></span>

   - <span data-ttu-id="0806e-162">若要选择域，请选择 **"发件人域为"**。</span><span class="sxs-lookup"><span data-stu-id="0806e-162">To select domains, select **The sender domain is**.</span></span> <span data-ttu-id="0806e-163">然后，在随后出现的对话框中添加域。</span><span class="sxs-lookup"><span data-stu-id="0806e-163">Then, in the subsequent dialog box, add the domains.</span></span> <span data-ttu-id="0806e-164">单击"确定"返回到主屏幕。</span><span class="sxs-lookup"><span data-stu-id="0806e-164">Click ok to return to the main screen.</span></span>

   <span data-ttu-id="0806e-165">可以在规则中创建例外。</span><span class="sxs-lookup"><span data-stu-id="0806e-165">You can create exceptions within the rule.</span></span> <span data-ttu-id="0806e-166">例如，可以筛选来自除某个域之外的所有域的邮件。</span><span class="sxs-lookup"><span data-stu-id="0806e-166">For example, you can filter messages from all domains except for a certain domain.</span></span> <span data-ttu-id="0806e-167">单击“添加例外”，然后创建例外条件，此过程与创建其他条件的方法类似。</span><span class="sxs-lookup"><span data-stu-id="0806e-167">Click add exception, and then create your exception conditions similar to the way that you created the other conditions.</span></span>

   <span data-ttu-id="0806e-168">仅支持启用邮件的安全组将出站垃圾邮件策略应用于组。</span><span class="sxs-lookup"><span data-stu-id="0806e-168">Applying an outbound spam policy to a group is supported only for Mail Enabled Security Groups.</span></span>

7. <span data-ttu-id="0806e-169">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0806e-169">Click **save**.</span></span>

## <a name="to-create-a-custom-policy-for-a-specific-set-of-users"></a><span data-ttu-id="0806e-170">为一组特定用户创建自定义策略</span><span class="sxs-lookup"><span data-stu-id="0806e-170">To create a custom policy for a specific set of users</span></span>

1. <span data-ttu-id="0806e-171">在 SCC 中，导航到 "**威胁管理** \> **策略** \> **反垃圾邮件**"</span><span class="sxs-lookup"><span data-stu-id="0806e-171">In the SCC, navigate to **Threat Management** \> **Policy** \> **Anti-spam**</span></span>

2. <span data-ttu-id="0806e-172">单击 "**创建出站策略**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="0806e-172">Click on the **Create an outbound policy** button.</span></span>

3. <span data-ttu-id="0806e-173">展开 "**通知**" 部分，选择以下与出站邮件相关的复选框，然后选择 "**添加人员**"，在附带的对话框中添加关联的电子邮件地址或地址。</span><span class="sxs-lookup"><span data-stu-id="0806e-173">Expand the **Notifications** section and select the following check boxes pertaining to outbound messages, then select **Add people** to add an associated email address or addresses in the accompanying dialog box.</span></span>

4. <span data-ttu-id="0806e-174">展开 "**收件人限制**" 部分，指定用户可以向其发送的收件人的最大数量、内部和外部收件人的每小时以及每日最大数量。</span><span class="sxs-lookup"><span data-stu-id="0806e-174">Expand the **Recipient limits** section to specify the maximum number of recipients that a user can send to, per hour for internal and external recipients and maximum number per day.</span></span>

7. <span data-ttu-id="0806e-175">指定当用户超过指定限制时要执行的**操作**。</span><span class="sxs-lookup"><span data-stu-id="0806e-175">Specify the **action** to take when a user exceeds the specified limits.</span></span>

6. <span data-ttu-id="0806e-176">展开 "**应用**于" 部分并创建基于条件的规则，以指定要向其应用此策略的用户、组和域。</span><span class="sxs-lookup"><span data-stu-id="0806e-176">Expand the **Applies to** section and create a condition-based rule to specify the users, groups, and domains to which to apply this policy.</span></span> <span data-ttu-id="0806e-177">可以创建多个唯一性条件。</span><span class="sxs-lookup"><span data-stu-id="0806e-177">You can create multiple conditions, if they are unique.</span></span>  

8. <span data-ttu-id="0806e-178">单击 "**保存**"</span><span class="sxs-lookup"><span data-stu-id="0806e-178">Click **save**</span></span>

## <a name="for-more-information"></a><span data-ttu-id="0806e-179">更多信息</span><span class="sxs-lookup"><span data-stu-id="0806e-179">For more information</span></span>

[<span data-ttu-id="0806e-180">发送垃圾电子邮件后，从受限用户门户删除用户</span><span class="sxs-lookup"><span data-stu-id="0806e-180">Removing a user from the Restricted Users portal after sending spam email</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)

[<span data-ttu-id="0806e-181">出站邮件的高风险传递池</span><span class="sxs-lookup"><span data-stu-id="0806e-181">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="0806e-182">反垃圾邮件保护常见问题</span><span class="sxs-lookup"><span data-stu-id="0806e-182">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
