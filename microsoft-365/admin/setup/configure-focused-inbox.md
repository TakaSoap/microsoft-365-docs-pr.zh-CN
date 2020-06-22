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
ms.openlocfilehash: f56e85e79fcf17cde89ec3d6094ca757ccf0cc68
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779925"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a>为组织中的每个人配置重点收件箱

  如果你负责配置公司中每个人的电子邮件使用方式，则本文非常适合你！ 其中说明如何根据业务来自定义或关闭电子邮件，还将解答[常见问题](#faq-for-focused-inbox)。  <br/> 如果只想关闭重点收件箱，请参阅[关闭重点收件箱](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2)。  
   
If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view. You can also control whether users in your organization see the Focused Inbox in their mailbox.
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a>在组织中打开或关闭重点收件箱

使用 PowerShell 为组织中的每个人打开或关闭重点收件箱。 是否想在 Microsoft 365 管理中心执行此操作？ 请联系我们的工程团队。 **[请在此投票！](https://go.microsoft.com/fwlink/?linkid=862489)**
  
 **关闭重点收件箱：**
  
The following PowerShell example turns Focused Inbox **Off** in your organization. However, it doesn't block the availability of the feature for your users. If they want, they can still re-enable Focused Inbox again on each of their clients. 
  
1. [使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554)。
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).
    
3. 运行 **Get-OrganizationConfig** cmdlet。 
    
 ``` PowerShell
Get-OrganizationConfig
 ```

4. 查找 **FocusedInboxOn** 以查看其当前设置： 
    
    ![来自 PowerShell 的重点收件箱状态响应。](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. 运行以下 cmdlet 来关闭重点收件箱。
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $false
 ```

6. 再次运行 **Get-OrganizationConfig** cmdlet，可以看到 FocusedInboxOn 已设置为 $false，这表示重点收件箱已关闭。 
    
 **打开重点收件箱：**
  
- 在上述步骤 5 中，运行以下 cmdlet 来打开重点收件箱。
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $true
 ```

## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a>打开重点收件箱后，用户会看到什么？ 

Your users will see the Focused view only after they close and restart Outlook. When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.
  
![用户首次打开 Outlook 网页版时重点收件箱的外观图像。](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature. If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one. The tip looks like this:
  
![显示“重点收件箱”外观的图像，此时“重点收件箱”向你的用户推出且 Outlook 重新打开。](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
When a user decides to start using Focused Inbox, Clutter gets disabled automatically. The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a>为特定用户打开或关闭重点收件箱

This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization. However, it doesn't block the availability of the feature to him. If his wants, he can still re-enable Focused Inbox again on each of his clients. 
  
1. [使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554)。
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.
    
3. 运行 **Get-FocusedInbox** cmdlet，例如： 
    
 ``` PowerShell
 Get-FocusedInbox -Identity <tim@contoso.com>
 ```

4. 查找 FocusedInboxOn 以查看其当前设置：
    
    ![来自 PowerShell 的重点收件箱状态响应。](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. 运行以下 cmdlet 来关闭重点收件箱：
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
 ```

6. 或者，运行以下 cmdlet 将其打开：
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
 ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>利用 UI 创建传输规则，将电子邮件定向到所有用户的“重点”视图

1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。
    
2. 导航到**邮件流** \> **规则**。 选择“![EAC 添加图标](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif)”，然后选择“**新建规则...**”。 
    
3. 创建新规则完成后，选择 **“保存”** 启动该规则。 
    
    下图介绍了一个示例，其中来自"工资单管理部门"的所有邮件均被定向到了重点收件箱。
    
    ![Focusedinbox 工资单](../../media/focusedinbox-transport-rule.PNG)
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>使用 PowerShell 创建传输规则，将电子邮件定向到所有用户的“重点”视图

1. [使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554)。
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).

3. 例如，运行以下命令即可允许所有来自"工资单管理部门"的邮件定向到重点收件箱。
    
 ``` PowerShell
 New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
 ```

> [!IMPORTANT]
> 在本例中，"X-MS-Exchange-Organization-BypassFocusedInbox"和"true"都需区分大小写。
> 此外，重点收件箱将遵循绕过待筛选邮件的 X 标头，因此若在待筛选邮件中使用此设置，则此设置将用于重点收件箱。 有关语法和参数的详细信息，请参阅 [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194)。

### <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

可检查电子邮件标头，查看电子邮件是否通过重点收件箱的传输规则旁路发送到收件箱中。 从组织中应用了重点收件箱传输规则的邮箱中选择一封电子邮件。 查看邮件上标记的标头，应当可看到 **X-MS-Exchange-Organization-BypassFocusedInbox: true** 标头。 这意味着正在绕过。 有关如何查找邮件头的信息，请参阅 [查看电子邮件的 Internet 邮件头信息](https://go.microsoft.com/fwlink/p/?LinkId=822530)文章。 
 
## <a name="turn-onoff-clutter"></a>打开/关闭待筛选邮件
 
We've received reports that Clutter suddenly stopped working for some users. If this happens, you can enable it again for specific users. See [Configure Clutter for your organization](../email/configure-clutter.md).
 
## <a name="faq-for-focused-inbox"></a>重点收件箱的常见问题解答

下面是重点收件箱常见问题的答案。 

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a>我能否控制重点收件箱在组织中的推广方式？

Yes. You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users. See above.
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a>重点收件箱功能是否仅供 Office 2016 客户端使用？

可以，仅影响 Office 2016 的用户。 Outlook 2013 或更早版本不应用此功能。
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a>对重点收件箱所作的更改需多长时间才可在 Outlook 中生效？

在你打开或关闭重点收件箱后，用户一旦关闭再重启 Outlook，设置就会生效。
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a>启用重点收件箱后，待筛选邮件有什么变化？

After switching, you'll no longer receive less actionable email in the Clutter folder. Instead, email will be split between the Focused and Other tabs in your inbox. The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other. Any messages already in your Clutter folder will remain there until you decide to delete or move them.
  
请查看由 Microsoft 的 MVP [Tony Redmond](https://www.petri.com/author/tony-redmond) 撰写的该文章： [重点收件箱如何替换 Office 365 中的待筛选邮件](https://www.petri.com/focused-inbox-office-365)。
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a>能否让用户继续使用待筛选邮件？ 在使用待筛选邮件还是重点收件箱方面，Microsoft 有何建议？

Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now. To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a>如果要将每个人均移动到重点收件箱，则我是否应对最终用户禁用待筛选邮件？

No. It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet. However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox. It's therefore best not to disable Clutter until the upgraded clients are available.
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a>为何存在两个不同的 cmdlet 用于管理重点收件箱？

重点收件箱与两个状态关联。
  
- **组织级别**：重点收件箱状态，具有关联的最后更新时间戳。 
    
- **邮箱级别**：重点收件箱状态，具有关联的最后更新时间戳 
    
### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a>Outlook 决定如何呈现有这两种状态的重点收件箱体验？

Outlook decides to show the experience by choosing which cmdlet has the latest time stamp. By default, both time stamps are "null" and in this case, the feature is enabled.
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a>我已在组织中关闭重点收件箱，但为何 Get-FocusedInbox cmdlet 返回 “true”？

There are two cmdlets for controlling Focused Inbox. When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature. The experience in Outlook is chosen based on which cmdlet state was last modified.
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a>我能通过运行脚本来查看谁启用了重点收件箱吗？

No, and this is by design. Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience. It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.
