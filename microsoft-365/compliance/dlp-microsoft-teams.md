---
title: 数据丢失保护和 Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft Teams聊天和频道支持数据丢失防护 (DLP) 策略。
ms.openlocfilehash: fa7e0967e24d8fa5e64b84fbccf54ff8cf45d1d6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843538"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="1d327-103">数据丢失保护和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1d327-103">Data loss prevention and Microsoft Teams</span></span>

<span data-ttu-id="1d327-104">如果您的组织具有 DLP (数据丢失) ，您可以定义防止用户共享 Microsoft Teams 频道或聊天会话中敏感信息的策略。</span><span class="sxs-lookup"><span data-stu-id="1d327-104">If your organization has data loss prevention (DLP), you can define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="1d327-105">下面是此保护的工作原理的一些示例：</span><span class="sxs-lookup"><span data-stu-id="1d327-105">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="1d327-106">**示例 1：保护邮件中的敏感信息**。</span><span class="sxs-lookup"><span data-stu-id="1d327-106">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="1d327-107">假设有人尝试在来宾聊天或频道中Teams与外部用户 (敏感信息) 。</span><span class="sxs-lookup"><span data-stu-id="1d327-107">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="1d327-108">如果已定义 DLP 策略以防止出现此情况，则包含发送给外部用户的敏感信息的邮件将被删除。</span><span class="sxs-lookup"><span data-stu-id="1d327-108">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="1d327-109">根据 DLP 策略的配置方式，这会自动发生，且在数秒钟内发生。</span><span class="sxs-lookup"><span data-stu-id="1d327-109">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1d327-110">与具有Microsoft Teams的用户共享时，用于Microsoft Teams DLP 会阻止敏感内容：</span><span class="sxs-lookup"><span data-stu-id="1d327-110">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="1d327-111">- [团队和](/MicrosoftTeams/guest-access) 频道中的来宾访问;或</span><span class="sxs-lookup"><span data-stu-id="1d327-111">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="1d327-112">- [会议和](/MicrosoftTeams/manage-external-access) 聊天会话中的外部访问。</span><span class="sxs-lookup"><span data-stu-id="1d327-112">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="1d327-113">外部聊天会话的 DLP 仅在发送方和接收方均在"仅Teams且使用本地联盟Microsoft Teams[才能工作](/microsoftteams/manage-external-access)。</span><span class="sxs-lookup"><span data-stu-id="1d327-113">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="1d327-114">DLP for Teams 不会阻止与本地[](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business)或非Skype for Business联盟聊天会话进行互操作的消息。</span><span class="sxs-lookup"><span data-stu-id="1d327-114">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="1d327-115">**示例 2：保护文档中的敏感信息**。</span><span class="sxs-lookup"><span data-stu-id="1d327-115">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="1d327-116">假设有人尝试在频道或聊天中与来宾共享Microsoft Teams，并且该文档包含敏感信息。</span><span class="sxs-lookup"><span data-stu-id="1d327-116">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="1d327-117">如果已定义 DLP 策略以防止出现此状态，文档将不会为这些用户打开。</span><span class="sxs-lookup"><span data-stu-id="1d327-117">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="1d327-118">DLP 策略必须包含 SharePoint 和 OneDrive，才能实施保护。</span><span class="sxs-lookup"><span data-stu-id="1d327-118">Your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="1d327-119">这是 SharePoint DLP 的一个示例，显示在 Microsoft Teams 中，因此要求用户获得 Office 365 E3) 中包含的 Office 365 Office 365 DLP (的许可，但不要求用户获得 Office 365 高级合规版.) 的许可。</span><span class="sxs-lookup"><span data-stu-id="1d327-119">This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="dlp-licensing-for-microsoft-teams"></a><span data-ttu-id="1d327-120">DLP 许可Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1d327-120">DLP Licensing for Microsoft Teams</span></span>

<span data-ttu-id="1d327-121">[数据丢失防护](dlp-learn-about-dlp.md)功能已扩展为包括Microsoft Teams消息，包括用于以下功能的 **专用频道** 消息：</span><span class="sxs-lookup"><span data-stu-id="1d327-121">[Data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages** for:</span></span>

- <span data-ttu-id="1d327-122">Office 365E5/A5</span><span class="sxs-lookup"><span data-stu-id="1d327-122">Office 365 E5/A5</span></span>
- <span data-ttu-id="1d327-123">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="1d327-123">Microsoft 365 E5/A5</span></span>
- <span data-ttu-id="1d327-124">Microsoft 365 信息保护和治理</span><span class="sxs-lookup"><span data-stu-id="1d327-124">Microsoft 365 Information Protection and Governance</span></span>
- <span data-ttu-id="1d327-125">Office 365 高级合规版</span><span class="sxs-lookup"><span data-stu-id="1d327-125">Office 365 Advanced Compliance</span></span>

<span data-ttu-id="1d327-126">Office 365和Microsoft 365 E3包括适用于 SharePoint Online、OneDrive 和 Exchange Online 的 DLP 保护。</span><span class="sxs-lookup"><span data-stu-id="1d327-126">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="1d327-127">这还包括通过 Teams 共享Teams使用 SharePoint Online 和 OneDrive 共享文件。</span><span class="sxs-lookup"><span data-stu-id="1d327-127">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>

<span data-ttu-id="1d327-128">在聊天中支持 DLP Teams需要 E5。</span><span class="sxs-lookup"><span data-stu-id="1d327-128">Support for DLP protection in Teams Chat requires E5.</span></span>

<span data-ttu-id="1d327-129">要详细了解许可要求，请参阅 [Microsoft 365 租户级服务许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="1d327-129">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1d327-130">DLP 仅适用于聊天或频道线程中的实际消息。</span><span class="sxs-lookup"><span data-stu-id="1d327-130">DLP applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="1d327-131">活动通知（包括短消息预览并基于用户的通知设置显示）不包含在 DLP Teams中。</span><span class="sxs-lookup"><span data-stu-id="1d327-131">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP.</span></span> <span data-ttu-id="1d327-132">即使已应用 DLP 策略并删除了邮件本身的敏感信息，预览中显示的邮件部分的任何敏感信息仍将在通知中可见。</span><span class="sxs-lookup"><span data-stu-id="1d327-132">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

## <a name="scope-of-dlp-protection"></a><span data-ttu-id="1d327-133">DLP 保护的范围</span><span class="sxs-lookup"><span data-stu-id="1d327-133">Scope of DLP protection</span></span>

<span data-ttu-id="1d327-134">DLP 保护以不同方式应用于Teams实体。</span><span class="sxs-lookup"><span data-stu-id="1d327-134">DLP protection are applied differently to Teams entities.</span></span>

|<span data-ttu-id="1d327-135">用户帐户/组/列表</span><span class="sxs-lookup"><span data-stu-id="1d327-135">User Accounts/Groups/List</span></span>  |<span data-ttu-id="1d327-136">Teams实体</span><span class="sxs-lookup"><span data-stu-id="1d327-136">Teams Entity</span></span> |<span data-ttu-id="1d327-137">可用的 DLP 保护</span><span class="sxs-lookup"><span data-stu-id="1d327-137">DLP protection available</span></span>|
|---------|---------|---------|
|<span data-ttu-id="1d327-138">单个用户帐户</span><span class="sxs-lookup"><span data-stu-id="1d327-138">individual user accounts</span></span>     |<span data-ttu-id="1d327-139">1：1/n 聊天</span><span class="sxs-lookup"><span data-stu-id="1d327-139">1:1/n chats</span></span>         |<span data-ttu-id="1d327-140">是</span><span class="sxs-lookup"><span data-stu-id="1d327-140">yes</span></span>         |
|     |<span data-ttu-id="1d327-141">常规聊天</span><span class="sxs-lookup"><span data-stu-id="1d327-141">general chats</span></span>         |<span data-ttu-id="1d327-142">否</span><span class="sxs-lookup"><span data-stu-id="1d327-142">no</span></span>         |
|     |<span data-ttu-id="1d327-143">私人频道</span><span class="sxs-lookup"><span data-stu-id="1d327-143">private channels</span></span>         |<span data-ttu-id="1d327-144">是</span><span class="sxs-lookup"><span data-stu-id="1d327-144">yes</span></span>         |
|<span data-ttu-id="1d327-145">安全组/通讯组列表</span><span class="sxs-lookup"><span data-stu-id="1d327-145">security groups/distribution lists</span></span>  | <span data-ttu-id="1d327-146">1：1/n 聊天</span><span class="sxs-lookup"><span data-stu-id="1d327-146">1:1/n chats</span></span>         |<span data-ttu-id="1d327-147">是</span><span class="sxs-lookup"><span data-stu-id="1d327-147">yes</span></span>         |
|     |<span data-ttu-id="1d327-148">常规聊天</span><span class="sxs-lookup"><span data-stu-id="1d327-148">general chats</span></span>         |<span data-ttu-id="1d327-149">否</span><span class="sxs-lookup"><span data-stu-id="1d327-149">no</span></span>         |
|     |<span data-ttu-id="1d327-150">私人频道</span><span class="sxs-lookup"><span data-stu-id="1d327-150">private channels</span></span>         |<span data-ttu-id="1d327-151">是</span><span class="sxs-lookup"><span data-stu-id="1d327-151">yes</span></span>        |
|<span data-ttu-id="1d327-152">Microsoft 365组</span><span class="sxs-lookup"><span data-stu-id="1d327-152">Microsoft 365 group</span></span>    |<span data-ttu-id="1d327-153">1：1/n 聊天</span><span class="sxs-lookup"><span data-stu-id="1d327-153">1:1/n chats</span></span>          |<span data-ttu-id="1d327-154">否</span><span class="sxs-lookup"><span data-stu-id="1d327-154">no</span></span>         |
|     |<span data-ttu-id="1d327-155">常规聊天</span><span class="sxs-lookup"><span data-stu-id="1d327-155">general chats</span></span>          |<span data-ttu-id="1d327-156">是</span><span class="sxs-lookup"><span data-stu-id="1d327-156">yes</span></span>        |
|     |<span data-ttu-id="1d327-157">私人频道</span><span class="sxs-lookup"><span data-stu-id="1d327-157">private channels</span></span>|<span data-ttu-id="1d327-158">否</span><span class="sxs-lookup"><span data-stu-id="1d327-158">no</span></span>| 


## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="1d327-159">策略提示有助于培训用户</span><span class="sxs-lookup"><span data-stu-id="1d327-159">Policy tips help educate users</span></span>

<span data-ttu-id="1d327-160">与 DLP 在[Exchange、Outlook、Outlook 网页](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)版[、SharePoint Online、OneDrive for Business 网站](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)和[Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)桌面客户端中的工作方式类似，当使用 DLP 策略触发操作时，会显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="1d327-160">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action triggers with a DLP policy.</span></span> <span data-ttu-id="1d327-161">下面是策略提示的示例：</span><span class="sxs-lookup"><span data-stu-id="1d327-161">Here's an example of a policy tip:</span></span>

![阻止的邮件通知Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="1d327-163">在此，发件人尝试在一个安全通道中共享Microsoft Teams号码。</span><span class="sxs-lookup"><span data-stu-id="1d327-163">Here, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="1d327-164">The **What can I do？** link opens a dialog box that provides options for the sender to resolve the issue.</span><span class="sxs-lookup"><span data-stu-id="1d327-164">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="1d327-165">请注意，发件人可以选择覆盖策略，或通知管理员查看并解析策略。</span><span class="sxs-lookup"><span data-stu-id="1d327-165">Notice that, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![用于解决阻止的邮件的选项](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="1d327-167">在组织中，可以选择允许用户覆盖 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="1d327-167">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="1d327-168">配置 DLP 策略时，可以使用默认策略提示，或 [为](#to-customize-policy-tips) 组织自定义策略提示。</span><span class="sxs-lookup"><span data-stu-id="1d327-168">When you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="1d327-169">返回到我们的示例，其中发件人在 Teams 频道中共享了社会保险号码，以下是收件人看到的信息：</span><span class="sxs-lookup"><span data-stu-id="1d327-169">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1d327-170">![邮件被阻止](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="1d327-170">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="1d327-171">自定义策略提示</span><span class="sxs-lookup"><span data-stu-id="1d327-171">To customize policy tips</span></span>

<span data-ttu-id="1d327-172">若要执行该任务，须被分配具有编辑 DLP 策略权限的角色。</span><span class="sxs-lookup"><span data-stu-id="1d327-172">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="1d327-173">若要了解详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="1d327-173">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="1d327-174">转到合规中心 [https://compliance.microsoft.com](https://compliance.microsoft.com) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="1d327-174">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="1d327-175">选择“**数据丢失保护**” > “**策略**”。</span><span class="sxs-lookup"><span data-stu-id="1d327-175">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="1d327-176">选择策略，在"策略设置 **"旁边**，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="1d327-176">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="1d327-177">创建新规则，或编辑策略的现有规则。</span><span class="sxs-lookup"><span data-stu-id="1d327-177">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1d327-178">![编辑策略的规则](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="1d327-178">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="1d327-179">在" **用户通知"** 选项卡上，选择"自定义 **电子邮件文本"和** /或 **"自定义策略提示文本选项** "。</span><span class="sxs-lookup"><span data-stu-id="1d327-179">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1d327-180">![自定义用户通知和策略提示](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="1d327-180">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="1d327-181">指定要用于电子邮件通知和/或策略提示的文本，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="1d327-181">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="1d327-182">在"**策略设置"选项卡上**，选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="1d327-182">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="1d327-183">允许大约 1 小时更改通过数据中心运行并同步到用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1d327-183">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="1d327-184">将 Microsoft Teams 作为位置添加到现有 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="1d327-184">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="1d327-185">若要执行该任务，须被分配具有编辑 DLP 策略权限的角色。</span><span class="sxs-lookup"><span data-stu-id="1d327-185">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="1d327-186">若要了解详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="1d327-186">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="1d327-187">转到合规中心 [https://compliance.microsoft.com](https://compliance.microsoft.com) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="1d327-187">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="1d327-188">选择“**数据丢失保护**” > “**策略**”。</span><span class="sxs-lookup"><span data-stu-id="1d327-188">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="1d327-189">选择一个策略，然后查看"位置 **"下的值**。</span><span class="sxs-lookup"><span data-stu-id="1d327-189">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="1d327-190">如果你看到 **Teams和频道消息，** 则你已全部设置。</span><span class="sxs-lookup"><span data-stu-id="1d327-190">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="1d327-191">如果不单击，请单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="1d327-191">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1d327-192">![现有策略的位置](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="1d327-192">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="1d327-193">在"**状态**"列中，打开聊天Teams **消息的策略**。</span><span class="sxs-lookup"><span data-stu-id="1d327-193">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1d327-194">![用于Teams和频道的 DLP](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="1d327-194">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="1d327-195">在"**选择位置"** 选项卡上，保留所有帐户的默认设置，或选择"**允许我选择特定位置"。**</span><span class="sxs-lookup"><span data-stu-id="1d327-195">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="1d327-196">可以指定：</span><span class="sxs-lookup"><span data-stu-id="1d327-196">You can specify:</span></span>

    1. <span data-ttu-id="1d327-197">最多包含或排除 1000 个个人帐户</span><span class="sxs-lookup"><span data-stu-id="1d327-197">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="1d327-198">要包含或排除的通讯组列表和安全组。</span><span class="sxs-lookup"><span data-stu-id="1d327-198">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="1d327-199">然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="1d327-199">Then choose **Next**.</span></span>

7. <span data-ttu-id="1d327-200">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1d327-200">Click **Save**.</span></span>

<span data-ttu-id="1d327-201">允许大约 1 小时更改通过数据中心运行并同步到用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1d327-201">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="1d327-202">为 Microsoft Teams 定义新的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="1d327-202">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="1d327-203">若要执行该任务，须被分配具有编辑 DLP 策略权限的角色。</span><span class="sxs-lookup"><span data-stu-id="1d327-203">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="1d327-204">若要了解详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="1d327-204">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="1d327-205">转到合规中心 [https://compliance.microsoft.com](https://compliance.microsoft.com) () 并登录。</span><span class="sxs-lookup"><span data-stu-id="1d327-205">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="1d327-206">选择 **“数据丢失保护”** > **“策略”** > **“创建策略”**。</span><span class="sxs-lookup"><span data-stu-id="1d327-206">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="1d327-207">选择模板 [，](data-loss-prevention-policies.md#dlp-policy-templates)然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="1d327-207">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="1d327-208">在我们的示例中，我们选择了"美国个人身份信息数据"模板。</span><span class="sxs-lookup"><span data-stu-id="1d327-208">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1d327-209">![DLP 策略的隐私模板](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="1d327-209">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="1d327-210">在"**命名策略"** 选项卡上，指定策略的名称和说明，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="1d327-210">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="1d327-211">在"**选择位置"** 选项卡上，保留所有帐户的默认设置，或选择"**允许我选择特定位置"。**</span><span class="sxs-lookup"><span data-stu-id="1d327-211">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="1d327-212">可以指定：</span><span class="sxs-lookup"><span data-stu-id="1d327-212">You can specify:</span></span>

    1. <span data-ttu-id="1d327-213">最多包含或排除 1000 个个人帐户</span><span class="sxs-lookup"><span data-stu-id="1d327-213">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="1d327-214">要包含或排除的通讯组列表和安全组。</span><span class="sxs-lookup"><span data-stu-id="1d327-214">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="1d327-215">**这是公共预览功能。**</span><span class="sxs-lookup"><span data-stu-id="1d327-215">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![DLP 策略位置](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="1d327-217">如果您希望确保包含敏感信息的文档未在 Teams 中以不当方式共享，请确保 **SharePoint 网站** 和 **OneDrive** 帐户以及 Teams 聊天和频道消息 **已** 打开。</span><span class="sxs-lookup"><span data-stu-id="1d327-217">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="1d327-218">在"**策略设置**"选项卡上的"自定义要保护的内容类型"下，保留默认的简单设置，或选择"**使用** 高级设置"，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="1d327-218">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="1d327-219">如果选择高级设置，你可以为策略创建或编辑规则。</span><span class="sxs-lookup"><span data-stu-id="1d327-219">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="1d327-220">若要获取有关此的帮助，请参阅 [简单设置与高级设置](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)。</span><span class="sxs-lookup"><span data-stu-id="1d327-220">To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).</span></span>

7.  <span data-ttu-id="1d327-221">在" **策略设置"** 选项卡上的 **"** 如果检测到敏感信息，想要做什么？"下，查看设置。</span><span class="sxs-lookup"><span data-stu-id="1d327-221">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="1d327-222">你可以在此处选择保留默认 [策略](use-notifications-and-policy-tips.md)提示和电子邮件通知，或自定义它们。</span><span class="sxs-lookup"><span data-stu-id="1d327-222">Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1d327-223">![具有提示和通知的 DLP 策略设置](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="1d327-223">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="1d327-224">完成查看或编辑设置后，选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="1d327-224">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="1d327-225">在"策略设置"选项卡上的"是希望先打开策略还是先测试内容 **？"** 下，选择是打开策略，还是先测试策略，[](dlp-overview-plan-for-dlp.md#policy-deployment)还是将其保持为"现在关闭"，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="1d327-225">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](dlp-overview-plan-for-dlp.md#policy-deployment), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1d327-226">![指定是否打开策略](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="1d327-226">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="1d327-227">在 **"查看设置"** 选项卡上，查看新策略的设置。</span><span class="sxs-lookup"><span data-stu-id="1d327-227">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="1d327-228">选择 **"** 编辑"进行更改。</span><span class="sxs-lookup"><span data-stu-id="1d327-228">Choose **Edit** to make changes.</span></span> <span data-ttu-id="1d327-229">完成后，选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="1d327-229">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="1d327-230">允许新策略大约一小时通过数据中心运行并同步到用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1d327-230">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="1d327-231">阻止对敏感文档的外部访问</span><span class="sxs-lookup"><span data-stu-id="1d327-231">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="1d327-232">若要确保SharePoint外部来宾在默认情况下不能从 SharePoint 或 Teams访问包含敏感信息的文档，请选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="1d327-232">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="1d327-233">通过默认将新文件标记为敏感，可以确保文档在 DLP 扫描之前受到保护，并标记为可 [安全共享](/sharepoint/sensitive-by-default)。</span><span class="sxs-lookup"><span data-stu-id="1d327-233">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="1d327-234">建议的 DLP 策略结构</span><span class="sxs-lookup"><span data-stu-id="1d327-234">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="1d327-235">**条件**</span><span class="sxs-lookup"><span data-stu-id="1d327-235">**Conditions**</span></span>
        - <span data-ttu-id="1d327-236">内容包含以下任何敏感信息类型：[选择所有适用]</span><span class="sxs-lookup"><span data-stu-id="1d327-236">Content contains any of these sensitive information types: [Select all that apply]</span></span>
        
        - <span data-ttu-id="1d327-237">与组织Microsoft 365人员共享内容</span><span class="sxs-lookup"><span data-stu-id="1d327-237">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="1d327-238">![用于检测敏感内容的外部共享的 DLP 条件](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="1d327-238">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="1d327-239">**Actions**</span><span class="sxs-lookup"><span data-stu-id="1d327-239">**Actions**</span></span>
        - <span data-ttu-id="1d327-240">限制外部用户对内容的访问</span><span class="sxs-lookup"><span data-stu-id="1d327-240">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="1d327-241">使用电子邮件和策略提示通知用户</span><span class="sxs-lookup"><span data-stu-id="1d327-241">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="1d327-242">向管理员发送事件报告</span><span class="sxs-lookup"><span data-stu-id="1d327-242">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="1d327-243">![阻止外部共享敏感内容的 DLP 操作](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="1d327-243">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="1d327-244">DLP 策略在尝试与外部来宾共享包含SharePoint敏感信息的文档时正在操作：</span><span class="sxs-lookup"><span data-stu-id="1d327-244">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1d327-245">![外部共享被阻止](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="1d327-245">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="1d327-246">当来宾尝试在包含阻止外部阻止的文档中打开文档时Teams DLP 策略：</span><span class="sxs-lookup"><span data-stu-id="1d327-246">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1d327-247">![外部访问被阻止](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="1d327-247">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="1d327-248">相关文章</span><span class="sxs-lookup"><span data-stu-id="1d327-248">Related articles</span></span>

- [<span data-ttu-id="1d327-249">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="1d327-249">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="1d327-250">发送电子邮件通知并显示 DLP 策略的策略提示</span><span class="sxs-lookup"><span data-stu-id="1d327-250">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
