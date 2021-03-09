---
title: 数据丢失防护和 Microsoft Teams
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
description: 现在可以将 DLP 策略应用于 Microsoft Teams 聊天和频道。 阅读本文，详细了解其工作方式。
ms.openlocfilehash: 4b6f0c2e6915e7e96ba862fc6862b69aa0d827fd
ms.sourcegitcommit: d3c1b08b3a8af29ef19ffe77da063920f28fe290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50572658"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="dadb2-104">数据丢失防护和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dadb2-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="dadb2-105">数据丢失防护功能最近已添加到 Microsoft Teams 聊天和频道消息中，供授权使用 Office 365 E5/A5、Microsoft 365 E5/A5、Microsoft 365 信息保护和治理或 Office 365 高级合规性的用户使用。</span><span class="sxs-lookup"><span data-stu-id="dadb2-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance or Office 365 Advanced Compliance.</span></span> <span data-ttu-id="dadb2-106">Office 365 和 Microsoft 365 E3 包括针对 SharePoint Online、OneDrive 和 Exchange Online 的 DLP 保护。</span><span class="sxs-lookup"><span data-stu-id="dadb2-106">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="dadb2-107">这还包括通过 Teams 共享的文件，因为 Teams 使用 SharePoint Online 和 OneDrive 共享文件。</span><span class="sxs-lookup"><span data-stu-id="dadb2-107">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>
<span data-ttu-id="dadb2-108">支持 Teams 聊天中的 DLP 保护需要 E5。</span><span class="sxs-lookup"><span data-stu-id="dadb2-108">Support for DLP protection in Teams Chat requires E5.</span></span>
<span data-ttu-id="dadb2-109">要详细了解许可要求，请参阅 [Microsoft 365 租户级服务许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="dadb2-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="dadb2-110">适用于 Microsoft Teams 的 DLP 概述</span><span class="sxs-lookup"><span data-stu-id="dadb2-110">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="dadb2-111">最近 [，DLP (](data-loss-prevention-policies.md) 数据丢失) 功能进行了扩展，以包括 Microsoft Teams 聊天和频道消息， **包括私人频道消息**。</span><span class="sxs-lookup"><span data-stu-id="dadb2-111">Recently, [data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages**.</span></span>

<span data-ttu-id="dadb2-112">如果你的组织具有 DLP，你现在可以定义阻止用户在 Microsoft Teams 频道或聊天会话中共享敏感信息的策略。</span><span class="sxs-lookup"><span data-stu-id="dadb2-112">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="dadb2-113">下面是此保护的工作原理的一些示例：</span><span class="sxs-lookup"><span data-stu-id="dadb2-113">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="dadb2-114">**示例 1：保护邮件中的敏感信息**。</span><span class="sxs-lookup"><span data-stu-id="dadb2-114">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="dadb2-115">假设有人尝试与外部用户或外部用户共享 Teams 聊天或频道 (敏感信息) 。</span><span class="sxs-lookup"><span data-stu-id="dadb2-115">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="dadb2-116">如果已定义 DLP 策略以防止出现此情况，将删除包含发送给外部用户的敏感信息的邮件。</span><span class="sxs-lookup"><span data-stu-id="dadb2-116">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="dadb2-117">根据 DLP 策略的配置方式，这会自动发生，且在数秒钟内发生。</span><span class="sxs-lookup"><span data-stu-id="dadb2-117">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dadb2-118">与具有：</span><span class="sxs-lookup"><span data-stu-id="dadb2-118">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="dadb2-119">- [团队和](https://docs.microsoft.com/MicrosoftTeams/guest-access) 频道中的来宾访问;或</span><span class="sxs-lookup"><span data-stu-id="dadb2-119">- [guest access](https://docs.microsoft.com/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="dadb2-120">- [会议和](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) 聊天会话中的外部访问。</span><span class="sxs-lookup"><span data-stu-id="dadb2-120">- [external access](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="dadb2-121">外部聊天会话的 DLP 仅在发件人和接收方都采用"仅 Teams"模式并且使用 [Microsoft Teams 本机联盟时才能工作](https://docs.microsoft.com/microsoftteams/manage-external-access)。</span><span class="sxs-lookup"><span data-stu-id="dadb2-121">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](https://docs.microsoft.com/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="dadb2-122">适用于 Teams 的 DLP[](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business)不会阻止与 Skype for Business 或非本机联盟聊天会话互操作的消息。</span><span class="sxs-lookup"><span data-stu-id="dadb2-122">DLP for Teams does not block messages in [interop](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="dadb2-123">**示例 2：保护文档中的敏感信息**。</span><span class="sxs-lookup"><span data-stu-id="dadb2-123">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="dadb2-124">假设有人尝试在 Microsoft Teams 频道或聊天中与来宾共享文档，并且该文档包含敏感信息。</span><span class="sxs-lookup"><span data-stu-id="dadb2-124">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="dadb2-125">如果已定义 DLP 策略以防止出现此错误，则文档将不会为这些用户打开。</span><span class="sxs-lookup"><span data-stu-id="dadb2-125">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="dadb2-126">请注意，在这种情况下，DLP 策略必须包含 SharePoint 和 OneDrive，才能实施保护。</span><span class="sxs-lookup"><span data-stu-id="dadb2-126">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="dadb2-127"> (这是显示在 Microsoft Teams 中的适用于 SharePoint 的 DLP 示例，因此要求用户获得 Office 365 E3) 中包含的 Office 365 DLP (许可，但不要求用户获得 Office 365 高级合规性许可。) </span><span class="sxs-lookup"><span data-stu-id="dadb2-127">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="dadb2-128">策略提示有助于培训用户</span><span class="sxs-lookup"><span data-stu-id="dadb2-128">Policy tips help educate users</span></span>

<span data-ttu-id="dadb2-129">与 DLP 在 [Exchange、Outlook、Outlook 网页](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)版 [、SharePoint Online、OneDrive for Business](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)网站和 [Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)桌面客户端中的工作方式类似，当操作与 DLP 策略冲突时，会显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="dadb2-129">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="dadb2-130">下面是策略提示的示例：</span><span class="sxs-lookup"><span data-stu-id="dadb2-130">Here's an example of a policy tip:</span></span>

![Teams 中阻止的消息通知](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="dadb2-132">在这种情况下，发件人尝试在 Microsoft Teams 频道中共享社会保险号码。</span><span class="sxs-lookup"><span data-stu-id="dadb2-132">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="dadb2-133">" **我该怎么办？"** 链接将打开一个对话框，该对话框提供发件人解决问题的选项。</span><span class="sxs-lookup"><span data-stu-id="dadb2-133">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="dadb2-134">请注意，在这种情况下，发件人可以选择覆盖策略，或通知管理员查看并解决它。</span><span class="sxs-lookup"><span data-stu-id="dadb2-134">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![用于解决被阻止邮件的选项](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="dadb2-136">在组织中，可以选择允许用户覆盖 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="dadb2-136">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="dadb2-137">此外，配置 DLP 策略时，可以使用默认策略提示，或 [为](#to-customize-policy-tips) 组织自定义策略提示。</span><span class="sxs-lookup"><span data-stu-id="dadb2-137">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="dadb2-138">返回到我们的示例，其中发件人在 Teams 频道中共享了一个社会保险号码，以下是收件人看到的：</span><span class="sxs-lookup"><span data-stu-id="dadb2-138">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

![邮件被阻止](../media/dlp-teams-blockedmessage-notification-to-user.png)

<span data-ttu-id="dadb2-140">" **这是什么？"链接** 将打开 [一篇有关](data-loss-prevention-policies.md) DLP 策略的文章，帮助说明邮件被阻止的原因。</span><span class="sxs-lookup"><span data-stu-id="dadb2-140">The **What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="dadb2-141">自定义策略提示</span><span class="sxs-lookup"><span data-stu-id="dadb2-141">To customize policy tips</span></span>

<span data-ttu-id="dadb2-142">若要执行此任务，您必须获得一个有权编辑 DLP 策略的角色。</span><span class="sxs-lookup"><span data-stu-id="dadb2-142">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="dadb2-143">若要了解详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="dadb2-143">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="dadb2-144">转到安全与&中心 [https://protection.office.com](https://protection.office.com) () 登录。</span><span class="sxs-lookup"><span data-stu-id="dadb2-144">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="dadb2-145">选择 **数据丢失防护**  >  **策略**。</span><span class="sxs-lookup"><span data-stu-id="dadb2-145">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="dadb2-146">选择策略，在策略 **设置旁边** 选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="dadb2-146">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="dadb2-147">创建新规则，或编辑策略的现有规则。</span><span class="sxs-lookup"><span data-stu-id="dadb2-147">Either create a new rule, or edit an existing rule for the policy.</span></span><br/>![编辑策略的规则](../media/dlp-teams-editrule.png)<br/>

5. <span data-ttu-id="dadb2-149">在" **用户通知"** 选项卡上，选择 **"自定义电子邮件文本** "和/或" **自定义策略提示文本** 选项"。</span><span class="sxs-lookup"><span data-stu-id="dadb2-149">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span><br/><span data-ttu-id="dadb2-150">![自定义用户通知和策略提示](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="dadb2-150">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="dadb2-151">指定要用于电子邮件通知和/或策略提示的文本，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="dadb2-151">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="dadb2-152">在"**策略设置"** 选项卡上，选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="dadb2-152">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="dadb2-153">允许大约 1 小时更改通过数据中心运行并同步到用户帐户。</span><span class="sxs-lookup"><span data-stu-id="dadb2-153">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="dadb2-154">将 Microsoft Teams 添加为现有 DLP 策略的位置</span><span class="sxs-lookup"><span data-stu-id="dadb2-154">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="dadb2-155">若要执行此任务，您必须获得一个有权编辑 DLP 策略的角色。</span><span class="sxs-lookup"><span data-stu-id="dadb2-155">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="dadb2-156">若要了解详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="dadb2-156">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="dadb2-157">转到安全与&中心 [https://protection.office.com](https://protection.office.com) () 登录。</span><span class="sxs-lookup"><span data-stu-id="dadb2-157">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="dadb2-158">选择 **数据丢失防护**  >  **策略**。</span><span class="sxs-lookup"><span data-stu-id="dadb2-158">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="dadb2-159">选择一个策略，然后查看位置 **下的值**。</span><span class="sxs-lookup"><span data-stu-id="dadb2-159">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="dadb2-160">如果你看到 **Teams 聊天和频道消息**，则你已全部设置。</span><span class="sxs-lookup"><span data-stu-id="dadb2-160">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="dadb2-161">如果没有，请单击"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="dadb2-161">If you don't, click **Edit**.</span></span><br/><span data-ttu-id="dadb2-162">![现有策略的位置](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="dadb2-162">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span><br/>

4. <span data-ttu-id="dadb2-163">在 **"状态** "列中，打开 Teams **聊天和频道消息的策略**。</span><span class="sxs-lookup"><span data-stu-id="dadb2-163">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span><br/><span data-ttu-id="dadb2-164">![适用于 Teams 聊天和频道的 DLP](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="dadb2-164">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span><br/>

5. <span data-ttu-id="dadb2-165">在 **"选择位置"** 选项卡上，保留所有帐户的默认设置，或选择"**允许我选择特定位置"。**</span><span class="sxs-lookup"><span data-stu-id="dadb2-165">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="dadb2-166">可以指定：</span><span class="sxs-lookup"><span data-stu-id="dadb2-166">You can specify:</span></span>
    1. <span data-ttu-id="dadb2-167">最多包含或排除 1000 个个人帐户</span><span class="sxs-lookup"><span data-stu-id="dadb2-167">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="dadb2-168">要包含或排除的通讯组列表和安全组。</span><span class="sxs-lookup"><span data-stu-id="dadb2-168">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="dadb2-169">**这是公共预览功能。**</span><span class="sxs-lookup"><span data-stu-id="dadb2-169">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="dadb2-170">然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="dadb2-170">Then choose **Next**.</span></span>



6. <span data-ttu-id="dadb2-171">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="dadb2-171">Click **Save**.</span></span>

<span data-ttu-id="dadb2-172">允许大约 1 小时更改通过数据中心运行并同步到用户帐户。</span><span class="sxs-lookup"><span data-stu-id="dadb2-172">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="dadb2-173">为 Microsoft Teams 定义新的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="dadb2-173">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="dadb2-174">若要执行此任务，您必须获得一个有权编辑 DLP 策略的角色。</span><span class="sxs-lookup"><span data-stu-id="dadb2-174">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="dadb2-175">若要了解详细信息，请参阅[权限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="dadb2-175">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="dadb2-176">转到安全与&中心 [https://protection.office.com](https://protection.office.com) () 登录。</span><span class="sxs-lookup"><span data-stu-id="dadb2-176">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="dadb2-177">选择 **"数据丢失防护**  >  **策略**  >  **+ 创建策略"。**</span><span class="sxs-lookup"><span data-stu-id="dadb2-177">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="dadb2-178">选择 [模板，](data-loss-prevention-policies.md#dlp-policy-templates)然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="dadb2-178">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span><br/><span data-ttu-id="dadb2-179">在我们的示例中，我们选择了"美国个人身份信息数据"模板。</span><span class="sxs-lookup"><span data-stu-id="dadb2-179">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span><br/><span data-ttu-id="dadb2-180">![DLP 策略的隐私模板](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="dadb2-180">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="dadb2-181">在 **"命名策略"** 选项卡上，指定策略的名称和说明，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="dadb2-181">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="dadb2-182">在 **"选择位置"** 选项卡上，保留所有帐户的默认设置，或选择"**允许我选择特定位置"。**</span><span class="sxs-lookup"><span data-stu-id="dadb2-182">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="dadb2-183">可以指定：</span><span class="sxs-lookup"><span data-stu-id="dadb2-183">You can specify:</span></span>
    1. <span data-ttu-id="dadb2-184">最多包含或排除 1000 个个人帐户</span><span class="sxs-lookup"><span data-stu-id="dadb2-184">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="dadb2-185">要包含或排除的通讯组列表和安全组。</span><span class="sxs-lookup"><span data-stu-id="dadb2-185">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="dadb2-186">**这是公共预览功能。**</span><span class="sxs-lookup"><span data-stu-id="dadb2-186">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

![DLP 策略位置](../media/dlp-teams-selectlocationsnewpolicy.png)

> [!NOTE]
> <span data-ttu-id="dadb2-188">如果你想要确保包含敏感信息的文档在 Teams 中不会不当共享，请确保 **SharePoint** 网站和 **OneDrive** 帐户以及 Teams 聊天和频道消息已 **打开**。</span><span class="sxs-lookup"><span data-stu-id="dadb2-188">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>


6. <span data-ttu-id="dadb2-189">在"**策略设置**"选项卡上的"自定义要保护的内容类型"下，保留默认的简单设置，或选择"使用 **高级** 设置"，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="dadb2-189">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="dadb2-190">如果选择高级设置，可以创建或编辑策略的规则。</span><span class="sxs-lookup"><span data-stu-id="dadb2-190">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="dadb2-191"> (若要获取此帮助，请参阅"简单设置"与" [高级设置](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)") </span><span class="sxs-lookup"><span data-stu-id="dadb2-191">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="dadb2-192">在 **"策略设置** "选项卡上的"如果检测到敏感信息，要执行什么操作 **？"** 下，查看设置。</span><span class="sxs-lookup"><span data-stu-id="dadb2-192">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="dadb2-193"> (可以在此处选择保留默认策略提示和电子邮件通知，或自定义它们[](use-notifications-and-policy-tips.md)。) </span><span class="sxs-lookup"><span data-stu-id="dadb2-193">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span><br/><span data-ttu-id="dadb2-194">![带提示和通知的 DLP 策略设置](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="dadb2-194">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span><br/><span data-ttu-id="dadb2-195">完成查看或编辑设置后，选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="dadb2-195">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="dadb2-196">在"策略设置"选项卡上的"是否要先打开策略或先测试内容 **？"** 下，选择是打开策略，还是先测试策略，还是 [](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)将其保持关闭状态，然后选择"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="dadb2-196">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.</span></span><br/><span data-ttu-id="dadb2-197">![指定是否打开策略](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="dadb2-197">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span><br/>

9. <span data-ttu-id="dadb2-198">在 **"查看设置"** 选项卡上，查看新策略的设置。</span><span class="sxs-lookup"><span data-stu-id="dadb2-198">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="dadb2-199">选择 **"** 编辑"进行更改。</span><span class="sxs-lookup"><span data-stu-id="dadb2-199">Choose **Edit** to make changes.</span></span> <span data-ttu-id="dadb2-200">完成后，选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="dadb2-200">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="dadb2-201">允许新策略大约一小时通过数据中心工作并同步到用户帐户。</span><span class="sxs-lookup"><span data-stu-id="dadb2-201">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="dadb2-202">阻止外部访问敏感文档</span><span class="sxs-lookup"><span data-stu-id="dadb2-202">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="dadb2-203">若要确保外部来宾默认情况下无法从 SharePoint 或 Teams 访问包含敏感信息的 SharePoint 文档，请选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="dadb2-203">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="dadb2-204">通过默认将新文件标记为敏感，可以确保文档在 DLP 扫描并标记为可安全共享 [之前受到保护](https://docs.microsoft.com/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="dadb2-204">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](https://docs.microsoft.com/sharepoint/sensitive-by-default)</span></span>
- <span data-ttu-id="dadb2-205">建议的 DLP 策略结构</span><span class="sxs-lookup"><span data-stu-id="dadb2-205">Recommended DLP policy structure</span></span>
    - <span data-ttu-id="dadb2-206">**条件**</span><span class="sxs-lookup"><span data-stu-id="dadb2-206">**Conditions**</span></span>
        - <span data-ttu-id="dadb2-207">内容包含以下任何敏感信息类型：[选择所有适用内容]</span><span class="sxs-lookup"><span data-stu-id="dadb2-207">Content contains any of these sensitive information types: [Select all that applies]</span></span>
        - <span data-ttu-id="dadb2-208">内容从 Microsoft 365 与组织外部人员共享</span><span class="sxs-lookup"><span data-stu-id="dadb2-208">Content is shared from Microsoft 365 with people outside my organization</span></span>
        <br/><span data-ttu-id="dadb2-209">![用于检测敏感内容的外部共享的 DLP 条件](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="dadb2-209">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span><br/>


    - <span data-ttu-id="dadb2-210">**操作**</span><span class="sxs-lookup"><span data-stu-id="dadb2-210">**Actions**</span></span>
        - <span data-ttu-id="dadb2-211">限制外部用户访问内容</span><span class="sxs-lookup"><span data-stu-id="dadb2-211">Restrict access to the content for external users</span></span>
        - <span data-ttu-id="dadb2-212">使用电子邮件和策略提示通知用户</span><span class="sxs-lookup"><span data-stu-id="dadb2-212">Notify users with email and policy tips</span></span>
        - <span data-ttu-id="dadb2-213">向管理员发送事件报告</span><span class="sxs-lookup"><span data-stu-id="dadb2-213">Send incident reports to the Administrator</span></span>    
        <br/>![阻止外部共享敏感内容的 DLP 操作](../media/dlp-teams-external-sharing/external-action.png)<br/>

<span data-ttu-id="dadb2-215">DLP 策略在尝试在 SharePoint 中与外部来宾共享包含敏感信息的文档时正在操作：</span><span class="sxs-lookup"><span data-stu-id="dadb2-215">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>
<br/><span data-ttu-id="dadb2-216">![已阻止外部共享](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="dadb2-216">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span><br/>


<span data-ttu-id="dadb2-217">当来宾尝试在 Teams 中打开包含阻止外部阻止的文档时，DLP 策略在操作：</span><span class="sxs-lookup"><span data-stu-id="dadb2-217">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>
<br/><span data-ttu-id="dadb2-218">![外部访问被阻止](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="dadb2-218">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span><br/>

## <a name="related-articles"></a><span data-ttu-id="dadb2-219">相关文章</span><span class="sxs-lookup"><span data-stu-id="dadb2-219">Related articles</span></span>

[<span data-ttu-id="dadb2-220">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="dadb2-220">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="dadb2-221">发送电子邮件通知并显示 DLP 策略的策略提示</span><span class="sxs-lookup"><span data-stu-id="dadb2-221">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
