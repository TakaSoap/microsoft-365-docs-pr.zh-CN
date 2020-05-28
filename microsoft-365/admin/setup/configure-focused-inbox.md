---
title: 为组织中的每个人配置重点收件箱
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 613a845c-4b71-41de-b331-acdcf5b6625d
description: '了解如何为组织的所有或特定用户配置重点收件箱。 '
ms.openlocfilehash: 3d719208caf233ebcc4825ef04647bf06c68d93e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44398974"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a><span data-ttu-id="58ddd-103">为组织中的每个人配置重点收件箱</span><span class="sxs-lookup"><span data-stu-id="58ddd-103">Configure Focused Inbox for everyone in your organization</span></span>

  <span data-ttu-id="58ddd-104">如果你负责配置公司中每个人的电子邮件使用方式，则本文非常适合你！</span><span class="sxs-lookup"><span data-stu-id="58ddd-104">If you're responsible for configuring how email works for EVERYONE in a business this article is for you!</span></span> <span data-ttu-id="58ddd-105">其中说明如何根据业务来自定义或关闭电子邮件，还将解答[常见问题](#faq-for-focused-inbox)。</span><span class="sxs-lookup"><span data-stu-id="58ddd-105">It explains how to customize it or turn it off for your business, and answers [frequently asked questions](#faq-for-focused-inbox).</span></span>  <br/> <span data-ttu-id="58ddd-106">如果只想关闭重点收件箱，请参阅[关闭重点收件箱](https://support.office.com/article/f714d94d-9e63-4217-9ccb-6cb2986aa1b2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="58ddd-106">If you would like to turn off Focused Inbox for just yourself, please see [Turn off Focused Inbox](https://support.office.com/article/f714d94d-9e63-4217-9ccb-6cb2986aa1b2.aspx).</span></span>  
   
<span data-ttu-id="58ddd-p102">如果想确保用户收到特定业务的电子邮件（例如来自 HR 或薪酬专员），可配置重点收件箱，让这些邮件出现在“重点”视图中。还可控制组织内部用户的邮箱中是否显示重点收件箱。</span><span class="sxs-lookup"><span data-stu-id="58ddd-p102">If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view. You can also control whether users in your organization see the Focused Inbox in their mailbox.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a><span data-ttu-id="58ddd-109">在组织中打开或关闭重点收件箱</span><span class="sxs-lookup"><span data-stu-id="58ddd-109">Turn Focused Inbox On or Off in your organization</span></span>

<span data-ttu-id="58ddd-110">使用 PowerShell 为组织中的每个人打开或关闭重点收件箱。</span><span class="sxs-lookup"><span data-stu-id="58ddd-110">You use PowerShell to turn Focused Inbox on or off for everyone in your organization.</span></span> <span data-ttu-id="58ddd-111">是否想在 Microsoft 365 管理中心执行此操作？</span><span class="sxs-lookup"><span data-stu-id="58ddd-111">Do you want to do this in the Microsoft 365 admin center?</span></span> <span data-ttu-id="58ddd-112">请联系我们的工程团队。</span><span class="sxs-lookup"><span data-stu-id="58ddd-112">Let our Engineering team know.</span></span> <span data-ttu-id="58ddd-113">**[请在此投票！](https://go.microsoft.com/fwlink/?linkid=862489)**</span><span class="sxs-lookup"><span data-stu-id="58ddd-113">**[Vote here!](https://go.microsoft.com/fwlink/?linkid=862489)**</span></span>
  
 <span data-ttu-id="58ddd-114">**关闭重点收件箱：**</span><span class="sxs-lookup"><span data-stu-id="58ddd-114">**To turn off Focused Inbox:**</span></span>
  
<span data-ttu-id="58ddd-p104">以下 PowerShell 示例演示如何在组织中**关闭**重点收件箱。但是，它不会阻止用户使用此功能。如果用户想使用，仍可在其每个客户端上重新启用重点收件箱。</span><span class="sxs-lookup"><span data-stu-id="58ddd-p104">The following PowerShell example turns Focused Inbox **Off** in your organization. However, it doesn't block the availability of the feature for your users. If they want, they can still re-enable Focused Inbox again on each of their clients.</span></span> 
  
1. <span data-ttu-id="58ddd-118">[使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="58ddd-118">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="58ddd-p105">需要分配有权限，然后才可执行此程序。要查看需要哪些权限，请参阅[邮件策略和符合性权限](https://go.microsoft.com/fwlink/p/?LinkId=829796)中的"传输规则"条目。</span><span class="sxs-lookup"><span data-stu-id="58ddd-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span></span>
    
3. <span data-ttu-id="58ddd-121">运行 **Get-OrganizationConfig** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="58ddd-121">Run the **Get-OrganizationConfig** cmdlet.</span></span> 
    
 ``` PowerShell
Get-OrganizationConfig
 ```

4. <span data-ttu-id="58ddd-122">查找 **FocusedInboxOn** 以查看其当前设置：</span><span class="sxs-lookup"><span data-stu-id="58ddd-122">Look for **FocusedInboxOn** to view its current setting:</span></span> 
    
    ![来自 PowerShell 的重点收件箱状态响应。](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="58ddd-124">运行以下 cmdlet 来关闭重点收件箱。</span><span class="sxs-lookup"><span data-stu-id="58ddd-124">Run the following cmdlet to turn Focused Inbox off.</span></span>
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $false
 ```

6. <span data-ttu-id="58ddd-125">再次运行 **Get-OrganizationConfig** cmdlet，可以看到 FocusedInboxOn 已设置为 $false，这表示重点收件箱已关闭。</span><span class="sxs-lookup"><span data-stu-id="58ddd-125">Run the **Get-OrganizationConfig** cmdlet again and you'll see that FocusedInboxOn is set to $false, which means it's been turned off.</span></span> 
    
 <span data-ttu-id="58ddd-126">**打开重点收件箱：**</span><span class="sxs-lookup"><span data-stu-id="58ddd-126">**To turn on Focused Inbox:**</span></span>
  
- <span data-ttu-id="58ddd-127">在上述步骤 5 中，运行以下 cmdlet 来打开重点收件箱。</span><span class="sxs-lookup"><span data-stu-id="58ddd-127">In Step 5 above, run the following cmdlet to turn Focused Inbox on.</span></span>
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $true
 ```

## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a><span data-ttu-id="58ddd-128">打开重点收件箱后，用户会看到什么？ </span><span class="sxs-lookup"><span data-stu-id="58ddd-128">What do users see after I turn on Focused Inbox?</span></span>

<span data-ttu-id="58ddd-p106">用户关闭并重启 Outlook​​ 后才可看到“重点”视图。重启 Outlook​​ 后，用户会在 Outlook​​ 用户界面中看到一条提示，其中含有使用新“重点收件箱”的选项。</span><span class="sxs-lookup"><span data-stu-id="58ddd-p106">Your users will see the Focused view only after they close and restart Outlook. When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.</span></span>
  
![用户首次打开 Outlook 网页版时重点收件箱的外观图像。](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
<span data-ttu-id="58ddd-p107">如果从待筛选邮件切换到重点收件箱，用户可决定启用（"试用"）或关闭该功能。如果用户拥有多个（受支持的）客户端，可在每个客户端上单独启用/禁用重点收件箱。将出现如下所示的提示：</span><span class="sxs-lookup"><span data-stu-id="58ddd-p107">If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature. If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one. The tip looks like this:</span></span>
  
![显示“重点收件箱”外观的图像，此时“重点收件箱”向你的用户推出且 Outlook 重新打开。](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
<span data-ttu-id="58ddd-p108">用户决定开始使用重点收件箱后，将自动禁用待筛选邮件。“待筛选邮件”文件夹转换成标准文件夹，用户可以重命名或将其删除。</span><span class="sxs-lookup"><span data-stu-id="58ddd-p108">When a user decides to start using Focused Inbox, Clutter gets disabled automatically. The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a><span data-ttu-id="58ddd-138">为特定用户打开或关闭重点收件箱</span><span class="sxs-lookup"><span data-stu-id="58ddd-138">Turn Focused Inbox On or Off for specific users</span></span>

<span data-ttu-id="58ddd-p109">本示例会为 Contoso 组织中的 Tim Matthews **关闭**重点收件箱。但是，它并不禁止他使用此功能。如果他想使用，仍可在其每个客户端上重新启用重点收件箱。</span><span class="sxs-lookup"><span data-stu-id="58ddd-p109">This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization. However, it doesn't block the availability of the feature to him. If his wants, he can still re-enable Focused Inbox again on each of his clients.</span></span> 
  
1. <span data-ttu-id="58ddd-142">[使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="58ddd-142">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="58ddd-p110">需要分配有权限，然后才可执行此程序。要查看需要哪些权限，请参阅邮件策略和合规性权限主题中的“传输规则”条目。</span><span class="sxs-lookup"><span data-stu-id="58ddd-p110">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.</span></span>
    
3. <span data-ttu-id="58ddd-145">运行 **Get-FocusedInbox** cmdlet，例如：</span><span class="sxs-lookup"><span data-stu-id="58ddd-145">Run the **Get-FocusedInbox** cmdlet, for example:</span></span> 
    
 ``` PowerShell
 Get-FocusedInbox -Identity <tim@contoso.com>
 ```

4. <span data-ttu-id="58ddd-146">查找 FocusedInboxOn 以查看其当前设置：</span><span class="sxs-lookup"><span data-stu-id="58ddd-146">Look for FocusedInboxOn to view its current setting:</span></span>
    
    ![来自 PowerShell 的重点收件箱状态响应。](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="58ddd-148">运行以下 cmdlet 来关闭重点收件箱：</span><span class="sxs-lookup"><span data-stu-id="58ddd-148">Run the following cmdlet to turn Focused Inbox off:</span></span>
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
 ```

6. <span data-ttu-id="58ddd-149">或者，运行以下 cmdlet 将其打开：</span><span class="sxs-lookup"><span data-stu-id="58ddd-149">OR, run the following cmdlet to turn it on:</span></span>
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
 ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="58ddd-150">利用 UI 创建传输规则，将电子邮件定向到所有用户的“重点”视图</span><span class="sxs-lookup"><span data-stu-id="58ddd-150">Use the UI to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="58ddd-151">转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="58ddd-151">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
    
2. <span data-ttu-id="58ddd-152">导航到**邮件流** \> **规则**。</span><span class="sxs-lookup"><span data-stu-id="58ddd-152">Navigate to **mail flow** \> **Rules**.</span></span> <span data-ttu-id="58ddd-153">选择“![EAC 添加图标](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif)”，然后选择“**新建规则...**”。</span><span class="sxs-lookup"><span data-stu-id="58ddd-153">Select ![EAC Add icon](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) and then select **Create a new rule...**.</span></span> 
    
3. <span data-ttu-id="58ddd-154">创建新规则完成后，选择 **“保存”** 启动该规则。</span><span class="sxs-lookup"><span data-stu-id="58ddd-154">After you're done creating the new rule, select **Save** to start the rule.</span></span> 
    
    <span data-ttu-id="58ddd-155">下图介绍了一个示例，其中来自"工资单管理部门"的所有邮件均被定向到了重点收件箱。</span><span class="sxs-lookup"><span data-stu-id="58ddd-155">The following image shows an example where all messages From "Payroll Department" are to be delivered to the Focused Inbox.</span></span>
    
    ![Focusedinbox 工资单](../../media/focusedinbox-transport-rule.PNG)
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="58ddd-157">使用 PowerShell 创建传输规则，将电子邮件定向到所有用户的“重点”视图</span><span class="sxs-lookup"><span data-stu-id="58ddd-157">Use PowerShell to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="58ddd-158">[使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554)。</span><span class="sxs-lookup"><span data-stu-id="58ddd-158">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="58ddd-p112">需要分配有权限，然后才可执行此程序。要查看需要哪些权限，请参阅[邮件策略和符合性权限](https://go.microsoft.com/fwlink/p/?LinkId=829796)中的"传输规则"条目。</span><span class="sxs-lookup"><span data-stu-id="58ddd-p112">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span></span>

3. <span data-ttu-id="58ddd-161">例如，运行以下命令即可允许所有来自"工资单管理部门"的邮件定向到重点收件箱。</span><span class="sxs-lookup"><span data-stu-id="58ddd-161">Run the following command to allow all messages from "Payroll Department," for example, to be delivered to the Focused Inbox.</span></span>
    
 ``` PowerShell
 New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
 ```

> [!IMPORTANT]
> <span data-ttu-id="58ddd-162">在本例中，"X-MS-Exchange-Organization-BypassFocusedInbox"和"true"都需区分大小写。</span><span class="sxs-lookup"><span data-stu-id="58ddd-162">In this example, both "X-MS-Exchange-Organization-BypassFocusedInbox" and "true" are case sensitive.</span></span>
> <span data-ttu-id="58ddd-163">此外，重点收件箱将遵循绕过待筛选邮件的 X 标头，因此若在待筛选邮件中使用此设置，则此设置将用于重点收件箱。</span><span class="sxs-lookup"><span data-stu-id="58ddd-163">Also, Focused Inbox will honor the X-header that bypasses Clutter, so if you use this setting in Clutter, it will be used in Focused Inbox.</span></span> <span data-ttu-id="58ddd-164">有关语法和参数的详细信息，请参阅 [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194)。</span><span class="sxs-lookup"><span data-stu-id="58ddd-164">For detailed syntax and parameter information, see [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="58ddd-165">如何判断是否生效？</span><span class="sxs-lookup"><span data-stu-id="58ddd-165">How do you know this worked?</span></span>

<span data-ttu-id="58ddd-166">可检查电子邮件标头，查看电子邮件是否通过重点收件箱的传输规则旁路发送到收件箱中。</span><span class="sxs-lookup"><span data-stu-id="58ddd-166">You can check email message headers to see if the email messages are landing in the Inbox due to the Focused Inbox transport rule bypass.</span></span> <span data-ttu-id="58ddd-167">从组织中应用了重点收件箱传输规则的邮箱中选择一封电子邮件。</span><span class="sxs-lookup"><span data-stu-id="58ddd-167">Pick an email message from a mailbox in your organization that has the Focused Inbox transport rule applied.</span></span> <span data-ttu-id="58ddd-168">查看邮件上标记的标头，应当可看到 **X-MS-Exchange-Organization-BypassFocusedInbox: true** 标头。</span><span class="sxs-lookup"><span data-stu-id="58ddd-168">Look at the headers stamped on the message, and you should see the **X-MS-Exchange-Organization-BypassFocusedInbox: true** header.</span></span> <span data-ttu-id="58ddd-169">这意味着正在绕过。</span><span class="sxs-lookup"><span data-stu-id="58ddd-169">This means the bypass is working.</span></span> <span data-ttu-id="58ddd-170">有关如何查找邮件头的信息，请参阅 [查看电子邮件的 Internet 邮件头信息](https://go.microsoft.com/fwlink/p/?LinkId=822530)文章。</span><span class="sxs-lookup"><span data-stu-id="58ddd-170">Check out the [View the Internet header information for an email message](https://go.microsoft.com/fwlink/p/?LinkId=822530) article for info on how to find the header information.</span></span> 
 
## <a name="turn-onoff-clutter"></a><span data-ttu-id="58ddd-171">打开/关闭待筛选邮件</span><span class="sxs-lookup"><span data-stu-id="58ddd-171">Turn on/off Clutter</span></span>
 
<span data-ttu-id="58ddd-p115">我们已收到一些报告，了解到某些用户的待筛选邮件会突然停止工作。如果发生此情况，可为特定用户再次启用待筛选邮件。请参阅[为组织配置待筛选邮件](../email/configure-clutter.md)。</span><span class="sxs-lookup"><span data-stu-id="58ddd-p115">We've received reports that Clutter suddenly stopped working for some users. If this happens, you can enable it again for specific users. See [Configure Clutter for your organization](../email/configure-clutter.md).</span></span>
 
## <a name="faq-for-focused-inbox"></a><span data-ttu-id="58ddd-175">重点收件箱的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="58ddd-175">FAQ for Focused Inbox</span></span>

<span data-ttu-id="58ddd-176">下面是重点收件箱常见问题的答案。</span><span class="sxs-lookup"><span data-stu-id="58ddd-176">Here are answers to Frequently Asked Questions about Focused Inbox.</span></span> 

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a><span data-ttu-id="58ddd-177">我能否控制重点收件箱在组织中的推广方式？</span><span class="sxs-lookup"><span data-stu-id="58ddd-177">Can I control how I roll out Focused Inbox in my organization?</span></span>

<span data-ttu-id="58ddd-p116">可以。可为整个组织打开或关闭重点收件箱，也可为特定用户执行此操作。具体步骤请见上文。</span><span class="sxs-lookup"><span data-stu-id="58ddd-p116">Yes. You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users. See above.</span></span>
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a><span data-ttu-id="58ddd-181">重点收件箱功能是否仅供 Office 2016 客户端使用？</span><span class="sxs-lookup"><span data-stu-id="58ddd-181">Is the Focused Inbox feature ONLY available for Office 2016 clients?</span></span>

<span data-ttu-id="58ddd-182">可以，仅影响 Office 2016 的用户。</span><span class="sxs-lookup"><span data-stu-id="58ddd-182">Yes, only users with Office 2016 are affected.</span></span> <span data-ttu-id="58ddd-183">Outlook 2013 或更早版本不应用此功能。</span><span class="sxs-lookup"><span data-stu-id="58ddd-183">The feature is not going to be backported to Outlook 2013 or earlier.</span></span>
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a><span data-ttu-id="58ddd-184">对重点收件箱所作的更改需多长时间才可在 Outlook 中生效？</span><span class="sxs-lookup"><span data-stu-id="58ddd-184">How long does it take for Focused Inbox changes to take place in Outlook?</span></span>

<span data-ttu-id="58ddd-185">在你打开或关闭重点收件箱后，用户一旦关闭再重启 Outlook，设置就会生效。</span><span class="sxs-lookup"><span data-stu-id="58ddd-185">Once you turn on or turn off Focused Inbox, the settings will take effect once your users close and restart Outlook.</span></span>
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a><span data-ttu-id="58ddd-186">启用重点收件箱后，待筛选邮件有什么变化？</span><span class="sxs-lookup"><span data-stu-id="58ddd-186">What happens to Clutter once I turn on Focused Inbox?</span></span>

<span data-ttu-id="58ddd-p118">切换后，待筛选邮件文件夹中将不再接收可操作性较低的电子邮件。相反，电子邮件将分散位于收件箱的“重点”和“其他”选项卡上。将项目移动到待筛选邮件文件夹时所用的同一算法现支持重点收件箱，这意味着设置为“移至待筛选邮件”的任何电子邮件现都将移动到“其他”。在你决定删除或移动之前，待筛选邮件文件夹中已存的任何邮件都将保留在此处。</span><span class="sxs-lookup"><span data-stu-id="58ddd-p118">After switching, you'll no longer receive less actionable email in the Clutter folder. Instead, email will be split between the Focused and Other tabs in your inbox. The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other. Any messages already in your Clutter folder will remain there until you decide to delete or move them.</span></span>
  
<span data-ttu-id="58ddd-191">请查看由 Microsoft 的 MVP [Tony Redmond](https://www.petri.com/author/tony-redmond) 撰写的该文章： [重点收件箱如何替换 Office 365 中的待筛选邮件](https://www.petri.com/focused-inbox-office-365)。</span><span class="sxs-lookup"><span data-stu-id="58ddd-191">Check out this post by [Tony Redmond](https://www.petri.com/author/tony-redmond), Microsoft MVP: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365).</span></span>
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a><span data-ttu-id="58ddd-192">能否让用户继续使用待筛选邮件？</span><span class="sxs-lookup"><span data-stu-id="58ddd-192">Can I keep users on Clutter?</span></span> <span data-ttu-id="58ddd-193">在使用待筛选邮件还是重点收件箱方面，Microsoft 有何建议？</span><span class="sxs-lookup"><span data-stu-id="58ddd-193">What is Microsoft's recommendation when it comes to using Clutter vs Focused Inbox?</span></span>

<span data-ttu-id="58ddd-p120">可以，可让用户继续使用待筛选邮件并禁用重点收件箱，但重点收件箱最终将完全替换待筛选邮件，因此 Microsoft 建议立即移到重点收件箱。若要详细了解何时在 Exchange Online 中使用待筛选邮件，请参阅以下博客文章：[Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448)（重点收件箱上的更新及针对待筛选邮件的计划）。</span><span class="sxs-lookup"><span data-stu-id="58ddd-p120">Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now. To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).</span></span>
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a><span data-ttu-id="58ddd-196">如果要将每个人均移动到重点收件箱，则我是否应对最终用户禁用待筛选邮件？</span><span class="sxs-lookup"><span data-stu-id="58ddd-196">Should I disable Clutter for my end users if we are going to move everyone to Focused Inbox?</span></span>

<span data-ttu-id="58ddd-p121">不。可运行 Set-Clutter cmdlet，以显式禁用邮箱的待筛选邮件。但是，如果执行此操作，邮箱所有者将发现曾经重定向到待筛选邮件文件夹的邮件保留在收件箱中，而他们需要处理这些邮件，直到其客户端升级到支持重点收件箱的版本。因此最好在升级的客户端可用之后，再禁用待筛选邮件。</span><span class="sxs-lookup"><span data-stu-id="58ddd-p121">No. It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet. However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox. It's therefore best not to disable Clutter until the upgraded clients are available.</span></span>
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a><span data-ttu-id="58ddd-201">为何存在两个不同的 cmdlet 用于管理重点收件箱？</span><span class="sxs-lookup"><span data-stu-id="58ddd-201">Why are there two different cmdlets for managing Focused Inbox?</span></span>

<span data-ttu-id="58ddd-202">重点收件箱与两个状态关联。</span><span class="sxs-lookup"><span data-stu-id="58ddd-202">There are two states associated with Focused Inbox.</span></span>
  
- <span data-ttu-id="58ddd-203">**组织级别**：重点收件箱状态，具有关联的最后更新时间戳。</span><span class="sxs-lookup"><span data-stu-id="58ddd-203">**Organization Level**: Focused Inbox state, and an associated last update time-stamp.</span></span> 
    
- <span data-ttu-id="58ddd-204">**邮箱级别**：重点收件箱状态，具有关联的最后更新时间戳</span><span class="sxs-lookup"><span data-stu-id="58ddd-204">**Mailbox Level**: Focused Inbox state, and an associated last update time-stamp</span></span> 
    
### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a><span data-ttu-id="58ddd-205">Outlook 决定如何呈现有这两种状态的重点收件箱体验？</span><span class="sxs-lookup"><span data-stu-id="58ddd-205">How does Outlook decide to show the Focused Inbox experience with these two states?</span></span>

<span data-ttu-id="58ddd-p122">Outlook​​ 通过选择具有最新时间戳的 cmdlet 来决定显示相应的体验。两个时间戳均默认为“null”，且本例启用了此功能。</span><span class="sxs-lookup"><span data-stu-id="58ddd-p122">Outlook decides to show the experience by choosing which cmdlet has the latest time stamp. By default, both time stamps are "null" and in this case, the feature is enabled.</span></span>
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a><span data-ttu-id="58ddd-208">我已在组织中关闭重点收件箱，但为何 Get-FocusedInbox cmdlet 返回 “true”？</span><span class="sxs-lookup"><span data-stu-id="58ddd-208">Why does the Get-FocusedInbox cmdlet return "true", when I've turned Focused Inbox off in my organization?</span></span>

<span data-ttu-id="58ddd-p123">存在两个 cmdlet 来控制重点收件箱。对邮箱运行 Get-FocusedInbox 时，将返回此功能的邮箱级别状态。根据 cmdlet 状态修改时间的先后，在 Outlook​​ 中选择相应的体验。</span><span class="sxs-lookup"><span data-stu-id="58ddd-p123">There are two cmdlets for controlling Focused Inbox. When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature. The experience in Outlook is chosen based on which cmdlet state was last modified.</span></span>
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a><span data-ttu-id="58ddd-212">我能通过运行脚本来查看谁启用了重点收件箱吗？</span><span class="sxs-lookup"><span data-stu-id="58ddd-212">Can I run a script to see who has turned on Focused Inbox?</span></span>

<span data-ttu-id="58ddd-p124">不能，这是由设计决定的。启用重点收件箱是客户端设置，cmdlet 仅能告知你用户的邮箱是否符合客户端体验的条件。可在一些客户端中启用它，同时在另一些客户端中禁用它，例如，在 Outlook 应用和 Outlook Mobile 中启用，但在 Outlook 网页版中禁用。</span><span class="sxs-lookup"><span data-stu-id="58ddd-p124">No, and this is by design. Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience. It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.</span></span>
