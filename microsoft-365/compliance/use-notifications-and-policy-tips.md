---
title: 发送电子邮件通知并显示 DLP 策略的策略提示
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleNotifyUser
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: 了解如何将策略提示添加到 DLP (策略) 数据丢失防护，以通知用户他们处理的内容与 DLP 策略冲突。
ms.openlocfilehash: 53a4db6cfc37f35422a1efffaeac052370cd5988
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228647"
---
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a><span data-ttu-id="4152f-103">发送电子邮件通知并显示 DLP 策略的策略提示</span><span class="sxs-lookup"><span data-stu-id="4152f-103">Send email notifications and show policy tips for DLP policies</span></span>

<span data-ttu-id="4152f-104">数据丢失防护 (DLP) 策略可用于跨 Office 365 识别、监视和保护敏感信息。</span><span class="sxs-lookup"><span data-stu-id="4152f-104">You can use a data loss prevention (DLP) policy to identify, monitor, and protect sensitive information across Office 365.</span></span> <span data-ttu-id="4152f-105">您希望组织中处理此敏感信息的人遵守 DLP 策略，但不希望不必要地阻止他们完成工作。</span><span class="sxs-lookup"><span data-stu-id="4152f-105">You want people in your organization who work with this sensitive information to stay compliant with your DLP policies, but you don't want to block them unnecessarily from getting their work done.</span></span> <span data-ttu-id="4152f-106">这是电子邮件通知和策略提示可以提供帮助的情况。</span><span class="sxs-lookup"><span data-stu-id="4152f-106">This is where email notifications and policy tips can help.</span></span>

![消息栏在 Excel 2016 中显示策略提示](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)

<span data-ttu-id="4152f-108">策略提示是某人使用与 DLP 策略冲突的内容（例如 OneDrive for Business 网站上包含个人身份信息 (PII) 且与外部用户共享的 Excel 工作簿等内容）时出现的通知或警告。</span><span class="sxs-lookup"><span data-stu-id="4152f-108">A policy tip is a notification or warning that appears when someone is working with content that conflicts with a DLP policy—for example, content like an Excel workbook on a OneDrive for Business site that contains personally identifiable information (PII) and is shared with an external user.</span></span>

<span data-ttu-id="4152f-109">可以使用电子邮件通知和策略提示提高意识，并帮助用户了解组织策略。</span><span class="sxs-lookup"><span data-stu-id="4152f-109">You can use email notifications and policy tips to increase awareness and help educate people about your organization's policies.</span></span> <span data-ttu-id="4152f-110">您还可以为用户提供覆盖策略的选项，以便他们在有有效的业务需求或策略检测到误报时不会被阻止。</span><span class="sxs-lookup"><span data-stu-id="4152f-110">You can also give people the option to override the policy, so that they're not blocked if they have a valid business need or if the policy is detecting a false positive.</span></span>

<span data-ttu-id="4152f-111">在合规中心内，创建 DLP 策略时，可以将用户通知配置为：</span><span class="sxs-lookup"><span data-stu-id="4152f-111">In the Compliance Center, when you create a DLP policy, you can configure the user notifications to:</span></span>

- <span data-ttu-id="4152f-112">向选择描述该问题的人发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="4152f-112">Send an email notification to the people you choose that describes the issue.</span></span>
> [!NOTE]
> <span data-ttu-id="4152f-113">通知电子邮件不受保护的发送。</span><span class="sxs-lookup"><span data-stu-id="4152f-113">Notification emails are sent unprotected.</span></span>

- <span data-ttu-id="4152f-114">显示与 DLP 策略冲突的内容的策略提示：</span><span class="sxs-lookup"><span data-stu-id="4152f-114">Display a policy tip for content that conflicts with the DLP policy:</span></span>

  - <span data-ttu-id="4152f-115">对于 Outlook 网页版 和 Outlook 2013 及更高版本中的电子邮件，策略提示显示在撰写邮件时收件人上方的邮件顶部。</span><span class="sxs-lookup"><span data-stu-id="4152f-115">For email in Outlook on the web and Outlook 2013 and later, the policy tip appears at the top of a message above the recipients while the message is being composed.</span></span>

  - <span data-ttu-id="4152f-116">对于 OneDrive for Business 或 SharePoint Online 网站中的文档，策略提示由项目上出现的警告图标指示。</span><span class="sxs-lookup"><span data-stu-id="4152f-116">For documents in a OneDrive for Business account or SharePoint Online site, the policy tip is indicated by a warning icon that appears on the item.</span></span> <span data-ttu-id="4152f-117">若要查看详细信息，您可以选择一个项目，然后选择页面右上角的信息信息窗格图标以 ![ ](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) 打开详细信息窗格。</span><span class="sxs-lookup"><span data-stu-id="4152f-117">To view more information, you can select an item and then choose **Information** ![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane.</span></span>

  - <span data-ttu-id="4152f-118&quot;>对于存储在 DLP 策略中包含的 OneDrive for Business 站点或 SharePoint Online 站点上的 Excel、PowerPoint 和 Word 文档，策略提示将显示在消息栏和 Backstage 视图 (文件菜单&quot;信息 \> ") 上。</span><span class="sxs-lookup"><span data-stu-id="4152f-118">For Excel, PowerPoint, and Word documents that are stored on a OneDrive for Business site or SharePoint Online site that's included in the DLP policy, the policy tip appears on the Message Bar and the Backstage view (**File** menu \> **Info**).</span></span>

## <a name="add-user-notifications-to-a-dlp-policy"></a><span data-ttu-id="4152f-119">向 DLP 策略添加用户通知</span><span class="sxs-lookup"><span data-stu-id="4152f-119">Add user notifications to a DLP policy</span></span>

<span data-ttu-id="4152f-120">创建 DLP 策略时，可以启用用户 **通知**。</span><span class="sxs-lookup"><span data-stu-id="4152f-120">When you create a DLP policy, you can enable **User notifications**.</span></span> <span data-ttu-id="4152f-121">启用用户通知后，Microsoft 365发送电子邮件通知和策略提示。</span><span class="sxs-lookup"><span data-stu-id="4152f-121">When user notifications are enabled, Microsoft 365 sends out both email notifications and policy tips.</span></span> <span data-ttu-id="4152f-122">你可以自定义向谁发送通知电子邮件、电子邮件文本和策略提示文本。</span><span class="sxs-lookup"><span data-stu-id="4152f-122">You can customize who notification emails are sent to, the email text and the policy tip text.</span></span>

1. <span data-ttu-id="4152f-123">转到 [https://protection.office.com](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="4152f-123">Go to [https://protection.office.com](https://protection.office.com).</span></span>

2. <span data-ttu-id="4152f-124">使用工作或学校帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="4152f-124">Sign in using your work or school account.</span></span> <span data-ttu-id="4152f-125">现在，你已位于安全 &amp; 与合规中心。</span><span class="sxs-lookup"><span data-stu-id="4152f-125">You're now in the Security &amp; Compliance Center.</span></span>

3. <span data-ttu-id="4152f-126">在安全 &amp; 与合规中心 \> 左侧导航 \> **中，数据丢失防护** \> **策略** \> **+ 创建策略**。</span><span class="sxs-lookup"><span data-stu-id="4152f-126">In the Security &amp; Compliance Center \> left navigation \> **Data loss prevention** \> **Policy** \> **+ Create a policy**.</span></span>

    ![创建策略按钮](../media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)

4. <span data-ttu-id="4152f-128">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="4152f-128">Choose the DLP policy template that protects the types of sensitive information that you need \> **Next**.</span></span>

    <span data-ttu-id="4152f-129">若要从空模板开始，请选择"**自定义** \> **自定义策略""下一** \> **步"。**</span><span class="sxs-lookup"><span data-stu-id="4152f-129">To start with an empty template, choose **Custom** \> **Custom policy** \> **Next**.</span></span>

5. <span data-ttu-id="4152f-130">将策略名称为 \> **"下一步"。**</span><span class="sxs-lookup"><span data-stu-id="4152f-130">Name the policy \> **Next**.</span></span>

6. <span data-ttu-id="4152f-131">若要选择希望 DLP 策略保护的位置，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="4152f-131">To choose the locations that you want the DLP policy to protect, do one of the following:</span></span>

   - <span data-ttu-id="4152f-132">Choose **All locations in Office 365** \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="4152f-132">Choose **All locations in Office 365** \> **Next**.</span></span>

   - <span data-ttu-id="4152f-133">Choose **Let me choose specific locations** \> **Next**.</span><span class="sxs-lookup"><span data-stu-id="4152f-133">Choose **Let me choose specific locations** \> **Next**.</span></span>

   <span data-ttu-id="4152f-134">若要包含或排除整个位置（如所有Exchange或所有OneDrive帐户），请打开或关闭该位置的"状态"。</span><span class="sxs-lookup"><span data-stu-id="4152f-134">To include or exclude an entire location such as all Exchange email or all OneDrive accounts, switch the **Status** of that location on or off.</span></span>

   <span data-ttu-id="4152f-135">若要仅包含SharePoint或OneDrive帐户，请切换到"状态"打开，然后单击"包含"下的链接以选择特定网站或帐户。 </span><span class="sxs-lookup"><span data-stu-id="4152f-135">To include only specific SharePoint sites or OneDrive accounts, switch the **Status** to on, and then click the links under **Include** to choose specific sites or accounts.</span></span>

7. <span data-ttu-id="4152f-136">选择 **"使用高级设置""** \> **下一步"。**</span><span class="sxs-lookup"><span data-stu-id="4152f-136">Choose **Use advanced settings** \> **Next**.</span></span>

8. <span data-ttu-id="4152f-137">选择“**+ 新建规则**”。</span><span class="sxs-lookup"><span data-stu-id="4152f-137">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="4152f-138">在规则编辑器的"用户 **通知"下**，打开状态。</span><span class="sxs-lookup"><span data-stu-id="4152f-138">In the rule editor, under **User notifications**, switch the status on.</span></span>

    ![规则编辑器的用户通知部分](../media/47705927-c60b-4054-a072-ab914f33d15d.png)

> [!NOTE]
> <span data-ttu-id="4152f-140">DLP 策略应用于与策略匹配的所有文档，无论这些文档是新文档还是现有文档。</span><span class="sxs-lookup"><span data-stu-id="4152f-140">DLP policies apply to all documents that match the policy, whether those documents are new or existing.</span></span> <span data-ttu-id="4152f-141">但是，仅在新内容与现有 DLP 策略匹配时生成电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="4152f-141">However, an email notification is only generated when new content matches an existing DLP policy.</span></span> <span data-ttu-id="4152f-142">现有内容受保护，但不会通过电子邮件生成用户通知。</span><span class="sxs-lookup"><span data-stu-id="4152f-142">Existing content is protected, but will not generate a user notification via email.</span></span>

## <a name="options-for-configuring-email-notifications"></a><span data-ttu-id="4152f-143">用于配置电子邮件通知的选项</span><span class="sxs-lookup"><span data-stu-id="4152f-143">Options for configuring email notifications</span></span>

<span data-ttu-id="4152f-144">对于 DLP 策略中的每个规则，您可以：</span><span class="sxs-lookup"><span data-stu-id="4152f-144">For each rule in a DLP policy, you can:</span></span>

- <span data-ttu-id="4152f-p107">将通知发送给您选择的人员。这些人员可以包含内容的所有者、最后一次修改内容的人员、存储内容的网站所有者或特定用户。</span><span class="sxs-lookup"><span data-stu-id="4152f-p107">Send the notification to the people you choose. These people can include the owner of the content, the person who last modified the content, the owner of the site where the content is stored, or a specific user.</span></span>

- <span data-ttu-id="4152f-147">使用 HTML 或令牌自定义通知中包含的文本。</span><span class="sxs-lookup"><span data-stu-id="4152f-147">Customize the text that's included in the notification by using HTML or tokens.</span></span> <span data-ttu-id="4152f-148">有关详细信息，请参阅下面的部分。</span><span class="sxs-lookup"><span data-stu-id="4152f-148">See the section below for more information.</span></span>

> [!NOTE]
>  <span data-ttu-id="4152f-149">电子邮件通知只能发送给各个收件人，不能发送给组或通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="4152f-149">Email notifications can be sent only to individual recipients—not groups or distribution lists.</span></span> <span data-ttu-id="4152f-150">只有新内容才会触发电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="4152f-150">Only new content will trigger an email notification.</span></span> <span data-ttu-id="4152f-151">编辑现有内容将触发策略提示，但不能触发电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="4152f-151">Editing existing content will trigger policy tips, but not an email notification.</span></span>

![电子邮件通知选项](../media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)

### <a name="default-email-notification"></a><span data-ttu-id="4152f-153">默认电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="4152f-153">Default email notification</span></span>

<span data-ttu-id="4152f-154">通知的"主题"行以所采取操作开头，例如，电子邮件的"通知"、"邮件被阻止"或文档的"访问被阻止"。</span><span class="sxs-lookup"><span data-stu-id="4152f-154">Notifications have a Subject line that begins with the action taken, such as "Notification", "Message Blocked" for email, or "Access Blocked" for documents.</span></span> <span data-ttu-id="4152f-155">如果通知与文档有关，则通知邮件正文包含一个链接，该链接将你指向存储该文档的网站，并打开文档的策略提示，可在其中解决任何问题 (请参阅以下有关策略提示) 的部分。</span><span class="sxs-lookup"><span data-stu-id="4152f-155">If the notification is about a document, the notification message body includes a link that takes you to the site where the document's stored and opens the policy tip for the document, where you can resolve any issues (see the section below about policy tips).</span></span> <span data-ttu-id="4152f-156">如果通知与邮件有关，则通知会作为附件包含与 DLP 策略匹配的邮件。</span><span class="sxs-lookup"><span data-stu-id="4152f-156">If the notification is about a message, the notification includes as an attachment the message that matches a DLP policy.</span></span>

![消息通知](../media/35813d40-5fd8-425f-9624-55655e74fa6b.png)

<span data-ttu-id="4152f-p111">默认情况下，通知显示类似于网站上以下项的文本。通知文本针对每个规则单独配置，因此根据匹配的规则，显示的文本有所不同。</span><span class="sxs-lookup"><span data-stu-id="4152f-p111">By default, notifications display text similar to the following for an item on a site. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="4152f-160">**如果 DLP 策略规则也是如此...**</span><span class="sxs-lookup"><span data-stu-id="4152f-160">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="4152f-161">**然后，文档或SharePoint的默认OneDrive for Business显示...**</span><span class="sxs-lookup"><span data-stu-id="4152f-161">**Then the default notification for SharePoint or OneDrive for Business documents says this…**</span></span>|<span data-ttu-id="4152f-162">**然后，邮件的默认Outlook显示以下消息...**</span><span class="sxs-lookup"><span data-stu-id="4152f-162">**Then the default notification for Outlook messages says this…**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4152f-163">发送通知但不允许替代</span><span class="sxs-lookup"><span data-stu-id="4152f-163">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="4152f-164">此项与您的组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="4152f-164">This item conflicts with a policy in your organization.</span></span>  <br/> |<span data-ttu-id="4152f-165">您的电子邮件与贵组织的策略冲突。</span><span class="sxs-lookup"><span data-stu-id="4152f-165">Your email message conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="4152f-166">阻止访问，发送通知，并允许重写</span><span class="sxs-lookup"><span data-stu-id="4152f-166">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="4152f-167">此项与您的组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="4152f-167">This item conflicts with a policy in your organization.</span></span> <span data-ttu-id="4152f-168">如果不解决此冲突，则可能无法访问此文件。</span><span class="sxs-lookup"><span data-stu-id="4152f-168">If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |<span data-ttu-id="4152f-169">您的电子邮件与贵组织的策略冲突。</span><span class="sxs-lookup"><span data-stu-id="4152f-169">Your email message conflicts with a policy in your organization.</span></span> <span data-ttu-id="4152f-170">邮件未传递到所有收件人。</span><span class="sxs-lookup"><span data-stu-id="4152f-170">The message wasn't delivered to all recipients.</span></span>  <br/> |
|<span data-ttu-id="4152f-171">阻止访问，并向发送通知</span><span class="sxs-lookup"><span data-stu-id="4152f-171">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="4152f-p114">此项与您的组织中的策略相冲突。除非是项目的所有者、最后一次修改内容的用户以及网站集主管理员，否则其他人对此项目的访问将受到阻止。</span><span class="sxs-lookup"><span data-stu-id="4152f-p114">This item conflicts with a policy in your organization. Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |<span data-ttu-id="4152f-174">您的电子邮件与贵组织的策略冲突。</span><span class="sxs-lookup"><span data-stu-id="4152f-174">Your email message conflicts with a policy in your organization.</span></span> <span data-ttu-id="4152f-175">邮件未传递到所有收件人。</span><span class="sxs-lookup"><span data-stu-id="4152f-175">The message wasn't delivered to all recipients.</span></span>  <br/> |

### <a name="custom-email-notification"></a><span data-ttu-id="4152f-176">自定义电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="4152f-176">Custom email notification</span></span>

<span data-ttu-id="4152f-177">你可以创建自定义电子邮件通知，而不是向最终用户或管理员发送默认电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="4152f-177">You can create a custom email notification instead of sending the default email notification to your end users or admins.</span></span> <span data-ttu-id="4152f-178">自定义电子邮件通知支持 HTML，并且限制为 5，000 个字符。</span><span class="sxs-lookup"><span data-stu-id="4152f-178">The custom email notification supports HTML and has a 5,000-character limit.</span></span> <span data-ttu-id="4152f-179">可以使用 HTML 在通知中包括图像、格式和其他品牌。</span><span class="sxs-lookup"><span data-stu-id="4152f-179">You can use HTML to include images, formatting, and other branding in the notification.</span></span>

<span data-ttu-id="4152f-180">您还可以使用以下令牌来帮助自定义电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="4152f-180">You can also use the following tokens to help customize the email notification.</span></span> <span data-ttu-id="4152f-181">这些令牌是一些变量，由发送的通知中的特定信息取代。</span><span class="sxs-lookup"><span data-stu-id="4152f-181">These tokens are variables that are replaced by specific information in the notification that's sent.</span></span>

|<span data-ttu-id="4152f-182">**标记**</span><span class="sxs-lookup"><span data-stu-id="4152f-182">**Token**</span></span>|<span data-ttu-id="4152f-183">**说明**</span><span class="sxs-lookup"><span data-stu-id="4152f-183">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4152f-184">%%AppliedActions%%</span><span class="sxs-lookup"><span data-stu-id="4152f-184">%%AppliedActions%%</span></span>  <br/> |<span data-ttu-id="4152f-185">应用于内容的操作。</span><span class="sxs-lookup"><span data-stu-id="4152f-185">The actions applied to the content.</span></span>  <br/> |
|<span data-ttu-id="4152f-186">%%ContentURL%%</span><span class="sxs-lookup"><span data-stu-id="4152f-186">%%ContentURL%%</span></span>  <br/> |<span data-ttu-id="4152f-187">SharePoint Online 或 OneDrive for Business 上的文档的 URL。</span><span class="sxs-lookup"><span data-stu-id="4152f-187">The URL of the document on the SharePoint Online site or OneDrive for Business site.</span></span>  <br/> |
|<span data-ttu-id="4152f-188">%%MatchedConditions%%</span><span class="sxs-lookup"><span data-stu-id="4152f-188">%%MatchedConditions%%</span></span>  <br/> |<span data-ttu-id="4152f-189">与内容匹配的条件。</span><span class="sxs-lookup"><span data-stu-id="4152f-189">The conditions that were matched by the content.</span></span> <span data-ttu-id="4152f-190">使用此令牌向用户通知内容可能出现的问题。</span><span class="sxs-lookup"><span data-stu-id="4152f-190">Use this token to inform people of possible issues with the content.</span></span>  <br/> |

![显示标记显示位置的通知消息](../media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)

## <a name="options-for-configuring-policy-tips"></a><span data-ttu-id="4152f-192">用于配置策略提示的选项</span><span class="sxs-lookup"><span data-stu-id="4152f-192">Options for configuring policy tips</span></span>

<span data-ttu-id="4152f-193">对于 DLP 策略中的每个规则，您可以配置策略提示用于：</span><span class="sxs-lookup"><span data-stu-id="4152f-193">For each rule in a DLP policy, you can configure policy tips to:</span></span>

- <span data-ttu-id="4152f-194">简单地通知该用户此项内容与 DLP 策略相冲突，以便用户可以执行相应的操作来解决此冲突。</span><span class="sxs-lookup"><span data-stu-id="4152f-194">Simply notify the person that the content conflicts with a DLP policy, so that they can take action to resolve the conflict.</span></span> <span data-ttu-id="4152f-195">可以使用默认文本 (请参阅下表) 或输入有关组织特定策略的自定义文本。</span><span class="sxs-lookup"><span data-stu-id="4152f-195">You can use the default text (see the tables below) or enter custom text about your organization's specific policies.</span></span>

- <span data-ttu-id="4152f-p120">允许用户替换 DLP 策略。（可选） 您可以：</span><span class="sxs-lookup"><span data-stu-id="4152f-p120">Allow the person to override the DLP policy. Optionally, you can:</span></span>

  - <span data-ttu-id="4152f-198">要求用户输入替换该策略的业务理由。</span><span class="sxs-lookup"><span data-stu-id="4152f-198">Require the person to enter a business justification for overriding the policy.</span></span> <span data-ttu-id="4152f-199">将记录此信息，您可以在安全与合规中心的"报告"部分中的 DLP  &amp; 报告中查看此信息。</span><span class="sxs-lookup"><span data-stu-id="4152f-199">This information is logged and you can view it in the DLP reports in the **Reports** section of the Security &amp; Compliance Center.</span></span>

  - <span data-ttu-id="4152f-p122">允许用户报告误报并替换 DLP 策略。此信息还被记录下来用于报告，以便您可以使用误报来微调您的规则。</span><span class="sxs-lookup"><span data-stu-id="4152f-p122">Allow the person to report a false positive and override the DLP policy. This information is also logged for reporting, so that you can use false positives to fine tune your rules.</span></span>

![策略提示选项](../media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)

<span data-ttu-id="4152f-203">例如，您可能将 DLP 策略应用于检测到个人身份OneDrive for Business个人身份信息的网站 (PII) ，并且此策略有三个规则：</span><span class="sxs-lookup"><span data-stu-id="4152f-203">For example, you may have a DLP policy applied to OneDrive for Business sites that detects personally identifiable information (PII), and this policy has three rules:</span></span>

1. <span data-ttu-id="4152f-p123">第一个规则：如果在文档中检测到包含此敏感信息的实例少于五个，并且该文档与组织内部的人员共享，则“发送通知”操作将显示策略提示。对于策略提示，无需提供任何替换选项，因为此规则只是通知相关人员，但不会阻止访问。</span><span class="sxs-lookup"><span data-stu-id="4152f-p123">First rule: If fewer than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Send a notification** action displays a policy tip. For policy tips, no override options are necessary because this rule is simply notifying people and not blocking access.</span></span>

2. <span data-ttu-id="4152f-206">第二个规则：如果在文档中检测到包含此敏感信息的实例多于五个，并且该文档与组织内部的人员共享，则“阻止访问内容”操作将限制文件权限，并且“发送通知”操作会允许用户通过提供业务理由来替换该规则中的操作。</span><span class="sxs-lookup"><span data-stu-id="4152f-206">Second rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people inside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action allows people to override the actions in this rule by providing a business justification.</span></span> <span data-ttu-id="4152f-207">您的组织的业务有时要求内部人员共享 PII 数据，并且您不希望 DLP 策略阻止此操作。</span><span class="sxs-lookup"><span data-stu-id="4152f-207">Your organization's business sometimes requires internal people to share PII data, and you don't want your DLP policy to block this work.</span></span>

3. <span data-ttu-id="4152f-p125">第三个规则：如果在文档中检测到包含此敏感信息的实例多于五个，并且该文档与组织外部的人员共享，则“阻止访问内容”操作将限制文件权限，并且“发送通知”操作将不允许用户替换该规则中的操作，因为该信息是与外部共享的。决不允许您组织中的用户在组织外部共享 PII 数据。</span><span class="sxs-lookup"><span data-stu-id="4152f-p125">Third rule: If greater than five instances of this sensitive information are detected in a document, and the document is shared with people outside the organization, the **Block access to content** action restricts the permissions for the file, and the **Send a notification** action does not allow people to override the actions in this rule because the information is shared externally. Under no circumstances should people in your organization be allowed to share PII data outside the organization.</span></span>

<span data-ttu-id="4152f-210">以下几点有助于您对使用策略提示替换规则的理解：</span><span class="sxs-lookup"><span data-stu-id="4152f-210">Here are some fine points to understand about using a policy tip to override a rule:</span></span>

- <span data-ttu-id="4152f-211">覆盖选项是按规则进行，它将覆盖规则规则 (发送通知除外，通知在规则中) 。</span><span class="sxs-lookup"><span data-stu-id="4152f-211">The option to override is per rule, and it overrides all of the actions in the rule (except sending a notification, which can't be overridden).</span></span>

- <span data-ttu-id="4152f-212">内容可以匹配 DLP 策略中的多个规则，但只会显示限制最严格、优先级最高的规则中的策略提示。</span><span class="sxs-lookup"><span data-stu-id="4152f-212">It's possible for content to match several rules in a DLP policy, but only the policy tip from the most restrictive, highest-priority rule will be shown.</span></span> <span data-ttu-id="4152f-213">例如，阻止访问内容的规则所提供的策略提示比起只是发送通知的规则所提供的策略提示，前者的显示优先级高于后者。</span><span class="sxs-lookup"><span data-stu-id="4152f-213">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="4152f-214">这会让用户看不到策略提示的级联方式。</span><span class="sxs-lookup"><span data-stu-id="4152f-214">This prevents people from seeing a cascade of policy tips.</span></span>

- <span data-ttu-id="4152f-215">如果限制最严格的规则中的策略提示允许用户替换规则，那么替换此规则还会替换与此内容相匹配的所有其他规则。</span><span class="sxs-lookup"><span data-stu-id="4152f-215">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>

## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a><span data-ttu-id="4152f-216">OneDrive for Business 网站或 SharePoint Online 网站上的策略提示</span><span class="sxs-lookup"><span data-stu-id="4152f-216">Policy tips on OneDrive for Business sites and SharePoint Online sites</span></span>

<span data-ttu-id="4152f-217">当联机OneDrive for Business或 SharePoint 上的文档与 DLP 策略中的规则匹配，并且该规则使用策略提示时，策略提示在文档中显示特殊图标：</span><span class="sxs-lookup"><span data-stu-id="4152f-217">When a document on a OneDrive for Business site or SharePoint Online site matches a rule in a DLP policy, and that rule uses policy tips, the policy tips display special icons on the document:</span></span>

1. <span data-ttu-id="4152f-218">如果该规则发送有关该文件的通知，则会显示警告图标。</span><span class="sxs-lookup"><span data-stu-id="4152f-218">If the rule sends a notification about the file, the warning icon appears.</span></span>

2. <span data-ttu-id="4152f-219">如果该规则阻止访问该文档，则会显示阻止图标。</span><span class="sxs-lookup"><span data-stu-id="4152f-219">If the rule blocks access to the document, the blocked icon appears.</span></span>

   ![文档策略提示图标OneDrive帐户](../media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)

<span data-ttu-id="4152f-221">若要对文档采取措施，可以选择一个项目，选择页面右上角的信息信息窗格图标，以打开详细信息窗格 \>  ![ ](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **查看策略提示**。</span><span class="sxs-lookup"><span data-stu-id="4152f-221">To take action on a document, you can select an item \> choose **Information** ![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) in the upper-right corner of the page to open the details pane \> **View policy tip**.</span></span>

<span data-ttu-id="4152f-222">策略提示会列出问题及其内容，如果对策略提示配置了这些选项，则您可以选择“解决”，然后选择“替换”策略提示或“报告”误报。</span><span class="sxs-lookup"><span data-stu-id="4152f-222">The policy tip lists the issues with the content, and if the policy tips are configured with these options, you can choose **Resolve**, and then **Override** the policy tip or **Report** a false positive.</span></span>

![显示策略提示的信息窗格](../media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)

![具有重写选项的策略提示](../media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)

<span data-ttu-id="4152f-p127">将 DLP 策略同步到网站，并定期以异步方式根据这些策略对内容进行评估，因此，您创建 DLP 策略的时间与开始看到策略提示的时间之间可能出现短暂的延迟。类似延迟还有可能出现在从您解决或替换策略提示到网站的文档上的图标消失的这段时间里。</span><span class="sxs-lookup"><span data-stu-id="4152f-p127">DLP policies are synced to sites and contented is evaluated against them periodically and asynchronously, so there may be a short delay between the time you create the DLP policy and the time you begin to see policy tips. There may be a similar delay from when you resolve or override a policy tip to when the icon on the document on the site goes away.</span></span>

### <a name="default-text-for-policy-tips-on-sites"></a><span data-ttu-id="4152f-227">网站上的策略提示的默认文本</span><span class="sxs-lookup"><span data-stu-id="4152f-227">Default text for policy tips on sites</span></span>

<span data-ttu-id="4152f-p128">默认情况下，策略提示显示在网站上类似于以下项的文本。通知文本针对每个规则单独配置，因此根据匹配的规则，显示的文本有所不同。</span><span class="sxs-lookup"><span data-stu-id="4152f-p128">By default, policy tips display text similar to the following for an item on a site. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="4152f-230">**如果 DLP 策略规则也是如此...**</span><span class="sxs-lookup"><span data-stu-id="4152f-230">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="4152f-231">**然后默认策略提示的说明如下...**</span><span class="sxs-lookup"><span data-stu-id="4152f-231">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4152f-232">发送通知但不允许替代</span><span class="sxs-lookup"><span data-stu-id="4152f-232">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="4152f-233">此项与您的组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="4152f-233">This item conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="4152f-234">阻止访问，发送通知，并允许重写</span><span class="sxs-lookup"><span data-stu-id="4152f-234">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="4152f-235">此项与您的组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="4152f-235">This item conflicts with a policy in your organization.</span></span> <span data-ttu-id="4152f-236">如果不解决此冲突，则可能无法访问此文件。</span><span class="sxs-lookup"><span data-stu-id="4152f-236">If you don't resolve this conflict, access to this file might be blocked.</span></span>  <br/> |
|<span data-ttu-id="4152f-237">阻止访问，并向发送通知</span><span class="sxs-lookup"><span data-stu-id="4152f-237">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="4152f-p130">此项与您的组织中的策略相冲突。除非是项目的所有者、最后一次修改内容的用户以及网站集主管理员，否则其他人对此项目的访问将受到阻止。</span><span class="sxs-lookup"><span data-stu-id="4152f-p130">This item conflicts with a policy in your organization. Access to this item is blocked for everyone except its owner, last modifier, and the primary site collection administrator.</span></span>  <br/> |

### <a name="custom-text-for-policy-tips-on-sites"></a><span data-ttu-id="4152f-240">有关网站上策略提示的自定义文本</span><span class="sxs-lookup"><span data-stu-id="4152f-240">Custom text for policy tips on sites</span></span>

<span data-ttu-id="4152f-241">你可以将策略提示的文本与电子邮件通知分开自定义。</span><span class="sxs-lookup"><span data-stu-id="4152f-241">You can customize the text for policy tips separately from the email notification.</span></span> <span data-ttu-id="4152f-242">与上述部分 (电子邮件通知的自定义文本) ，策略提示的自定义文本不接受 HTML 或令牌。</span><span class="sxs-lookup"><span data-stu-id="4152f-242">Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens.</span></span> <span data-ttu-id="4152f-243">相反，策略提示的自定义文本是纯文本，只有 256 个字符的限制。</span><span class="sxs-lookup"><span data-stu-id="4152f-243">Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>

## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a><span data-ttu-id="4152f-244">Outlook 网页版 2013 Outlook及更高版本中的策略提示</span><span class="sxs-lookup"><span data-stu-id="4152f-244">Policy tips in Outlook on the web and Outlook 2013 and later</span></span>

<span data-ttu-id="4152f-245">在 Outlook 网页版 和 Outlook 2013 及更高版本中撰写新电子邮件时，如果添加的内容与 DLP 策略中的规则匹配，并且该规则使用策略提示，则会看到策略提示。</span><span class="sxs-lookup"><span data-stu-id="4152f-245">When you compose a new email in Outlook on the web and Outlook 2013 and later, you'll see a policy tip if you add content that matches a rule in a DLP policy, and that rule uses policy tips.</span></span> <span data-ttu-id="4152f-246">撰写邮件时，策略提示显示在邮件顶部的收件人上方。</span><span class="sxs-lookup"><span data-stu-id="4152f-246">The policy tip appears at the top of the message, above the recipients, while the message is being composed.</span></span>

![正在撰写的邮件顶部的策略提示](../media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)

<span data-ttu-id="4152f-248">无论敏感信息出现在邮件正文、主题行中，还是邮件附件中，策略提示都正常工作，如下所示。</span><span class="sxs-lookup"><span data-stu-id="4152f-248">Policy tips work whether the sensitive information appears in the message body, subject line, or even a message attachment as shown here.</span></span>

![显示附件与 DLP 策略冲突的策略提示](../media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)

<span data-ttu-id="4152f-250">如果策略提示配置为允许覆盖，可以选择"显示详细信息替代"输入业务理由 \>  \> 或报告误报 \> **替代**。</span><span class="sxs-lookup"><span data-stu-id="4152f-250">If the policy tips are configured to allow override, you can choose **Show Details** \> **Override** \> enter a business justification or report a false positive \> **Override**.</span></span>

![邮件中的策略提示展开以显示替代选项](../media/28bfb997-48a6-41f0-8682-d5e62488458a.png)

![策略提示对话框，可在其中覆盖策略提示](../media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)

<span data-ttu-id="4152f-253">请注意，向电子邮件添加敏感信息时，添加敏感信息和显示策略提示之间可能有延迟。</span><span class="sxs-lookup"><span data-stu-id="4152f-253">Note that when you add sensitive information to an email, there may be latency between when the sensitive information is added and when the policy tip appears.</span></span>

### <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions"></a><span data-ttu-id="4152f-254">Outlook 2013 及更高版本仅支持显示某些条件的策略提示</span><span class="sxs-lookup"><span data-stu-id="4152f-254">Outlook 2013 and later supports showing policy tips for only some conditions</span></span>

<span data-ttu-id="4152f-255">目前，Outlook 2013 及更高版本仅支持针对这些条件显示策略提示：</span><span class="sxs-lookup"><span data-stu-id="4152f-255">Currently, Outlook 2013 and later supports showing policy tips only for these conditions:</span></span>

- <span data-ttu-id="4152f-256">内容包含</span><span class="sxs-lookup"><span data-stu-id="4152f-256">Content contains</span></span>
- <span data-ttu-id="4152f-257">共享内容</span><span class="sxs-lookup"><span data-stu-id="4152f-257">Content is shared</span></span>

<span data-ttu-id="4152f-258">请注意，例外被视为条件，所有这些条件均在Outlook中工作，其中它们匹配内容，并强制对内容执行保护性操作。</span><span class="sxs-lookup"><span data-stu-id="4152f-258">Note that Exceptions are considered conditions and all of these conditions work in Outlook, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="4152f-259">但是，尚不支持向用户显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="4152f-259">But showing policy tips to users is not yet supported.</span></span>

### <a name="policy-tips-in-the-exchange-admin-center-vs-the-security-amp-compliance-center"></a><span data-ttu-id="4152f-260">安全Exchange中心与安全与合规中心 &amp; 中的策略提示</span><span class="sxs-lookup"><span data-stu-id="4152f-260">Policy tips in the Exchange admin center vs. the Security &amp; Compliance Center</span></span>

<span data-ttu-id="4152f-261">策略提示既可以与在管理中心中创建的 DLP 策略和邮件流规则一Exchange，也可以与在安全与合规中心中创建的 DLP 策略一起使用，但不能同时 &amp; 使用。</span><span class="sxs-lookup"><span data-stu-id="4152f-261">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security &amp; Compliance Center, but not both.</span></span> <span data-ttu-id="4152f-262">这是因为这些策略存储在不同位置，但策略提示只能从单个位置绘制。</span><span class="sxs-lookup"><span data-stu-id="4152f-262">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>

<span data-ttu-id="4152f-263">如果在 Exchange 管理中心中配置了策略提示，那么在 Outlook 网页版 和 Outlook 2013 及更高版本中，在 Exchange 管理中心中关闭这些提示之前，不会向 Outlook 网页版 和 Outlook 2013 中的用户显示任何策略提示。 &amp;</span><span class="sxs-lookup"><span data-stu-id="4152f-263">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security &amp; Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="4152f-264">这可确保当前Exchange邮件流规则 (传输规则) ，直到您选择切换到安全与合规 &amp; 中心。</span><span class="sxs-lookup"><span data-stu-id="4152f-264">This ensures that your current Exchange mail flow rules (also known as transport rules) will continue to work until you choose to switch over to the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="4152f-265">请注意，虽然策略提示只能从单个位置进行绘制，但始终会发送电子邮件通知，即使您同时在安全与合规中心和 Exchange使用 DLP &amp; 策略。</span><span class="sxs-lookup"><span data-stu-id="4152f-265">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security &amp; Compliance Center and the Exchange admin center.</span></span>

### <a name="default-text-for-policy-tips-in-email"></a><span data-ttu-id="4152f-266">电子邮件中的策略提示的默认文本</span><span class="sxs-lookup"><span data-stu-id="4152f-266">Default text for policy tips in email</span></span>

<span data-ttu-id="4152f-267">默认情况下，策略提示显示类似于以下内容的电子邮件文本。</span><span class="sxs-lookup"><span data-stu-id="4152f-267">By default, policy tips display text similar to the following for email.</span></span>

|<span data-ttu-id="4152f-268">**如果 DLP 策略规则也是如此...**</span><span class="sxs-lookup"><span data-stu-id="4152f-268">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="4152f-269">**然后默认策略提示的说明如下...**</span><span class="sxs-lookup"><span data-stu-id="4152f-269">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4152f-270">发送通知但不允许替代</span><span class="sxs-lookup"><span data-stu-id="4152f-270">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="4152f-271">您的电子邮件与贵组织的策略冲突。</span><span class="sxs-lookup"><span data-stu-id="4152f-271">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="4152f-272">阻止访问，发送通知，并允许重写</span><span class="sxs-lookup"><span data-stu-id="4152f-272">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="4152f-273">您的电子邮件与贵组织的策略冲突。</span><span class="sxs-lookup"><span data-stu-id="4152f-273">Your email conflicts with a policy in your organization.</span></span>  <br/> |
|<span data-ttu-id="4152f-274">阻止访问，并向发送通知</span><span class="sxs-lookup"><span data-stu-id="4152f-274">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="4152f-275">您的电子邮件与贵组织的策略冲突。</span><span class="sxs-lookup"><span data-stu-id="4152f-275">Your email conflicts with a policy in your organization.</span></span>  <br/> |

## <a name="policy-tips-in-excel-powerpoint-and-word"></a><span data-ttu-id="4152f-276">Excel、PowerPoint 和 Word 中的策略提示</span><span class="sxs-lookup"><span data-stu-id="4152f-276">Policy tips in Excel, PowerPoint, and Word</span></span>

<span data-ttu-id="4152f-277">当用户在桌面版本的 Excel、PowerPoint 和 Word 中处理敏感内容时，策略提示可以实时通知他们内容与 DLP 策略冲突。</span><span class="sxs-lookup"><span data-stu-id="4152f-277">When people work with sensitive content in the desktop versions of Excel, PowerPoint, and Word, policy tips can notify them in real time that the content conflicts with a DLP policy.</span></span> <span data-ttu-id="4152f-278">这要求：</span><span class="sxs-lookup"><span data-stu-id="4152f-278">This requires that:</span></span>

- <span data-ttu-id="4152f-279">Office 文档存储在 OneDrive for Business 网站或 SharePoint Online 网站上。</span><span class="sxs-lookup"><span data-stu-id="4152f-279">The Office document is stored on a OneDrive for Business site or SharePoint Online site.</span></span>

- <span data-ttu-id="4152f-280">该网站包含在配置为使用策略提示的 DLP 策略中。</span><span class="sxs-lookup"><span data-stu-id="4152f-280">The site is included in a DLP policy that's configured to use policy tips.</span></span>

<span data-ttu-id="4152f-281">Office桌面程序自动直接从 Office 365 同步 DLP 策略，然后扫描文档以确保它们不会与 DLP 策略发生冲突，并实时显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="4152f-281">Office desktop programs automatically sync DLP policies directly from Office 365, and then scan your documents to ensure that they don't conflict with your DLP policies and display policy tips in real time.</span></span>

> [!NOTE]
> <span data-ttu-id="4152f-282">Office桌面应用自行扫描文档，确定是否应显示 DLP 策略提示;它们不会显示联机SharePoint或OneDrive for Business确定应在文件上显示的策略提示。</span><span class="sxs-lookup"><span data-stu-id="4152f-282">Office desktop apps scan documents themselves to determine if DLP policy tips should be shown; they do not show policy tips that SharePoint Online sites or OneDrive for Business sites have already determined should be shown on a file.</span></span> <span data-ttu-id="4152f-283">因此，你可能并不总是在桌面应用中看到 DLP 策略提示，你将在 SharePoint Online 网站或OneDrive for Business看到该提示。</span><span class="sxs-lookup"><span data-stu-id="4152f-283">As a result, you may not always see a DLP policy tip in the desktop apps that you see in the SharePoint Online sites or OneDrive for Business sites.</span></span> <span data-ttu-id="4152f-284">相比之下，Office应用程序只显示 DLP 策略提示，SharePoint或OneDrive for Business确定应显示的 DLP 策略提示。</span><span class="sxs-lookup"><span data-stu-id="4152f-284">In contrast, the Office applications on the web only show DLP policy tips that SharePoint Online sites or OneDrive for Business sites have already determined should be shown.</span></span>

<span data-ttu-id="4152f-285">根据您在 DLP 策略中对策略提示的配置方式，用户可以选择忽略策略提示、使用或不使用业务理由替换策略或报告误报。</span><span class="sxs-lookup"><span data-stu-id="4152f-285">Depending on how you configure the policy tips in the DLP policy, people can choose to simply ignore the policy tip, override the policy with or without a business justification, or report a false positive.</span></span>

<span data-ttu-id="4152f-286">在消息栏上显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="4152f-286">Policy tips appear on the Message Bar.</span></span>

![消息栏在 Excel 2016 中显示策略提示](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)

<span data-ttu-id="4152f-288">策略提示也显示在 Backstage 视图（“文件”选项卡上）中。</span><span class="sxs-lookup"><span data-stu-id="4152f-288">And policy tips also appear in the Backstage view (on the **File** tab).</span></span>

![Backstage 在 Excel 2016 中显示策略提示](../media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)

<span data-ttu-id="4152f-290">如果对 DLP 策略中的策略提示配置了这些选项，您可以选择“解决”以“替换”策略提示或“报告”误报。</span><span class="sxs-lookup"><span data-stu-id="4152f-290">If policy tips in the DLP policy are configured with these options, you can choose **Resolve** to **Override** a policy tip or **Report** a false positive.</span></span>

![Excel 2016 Backstage 中的策略提示选项](../media/5b3857ba-907e-456e-ae43-888b594c049c.png)

<span data-ttu-id="4152f-292">在每个桌面Office中，用户可以选择关闭策略提示。</span><span class="sxs-lookup"><span data-stu-id="4152f-292">In each of these Office desktop programs, people can choose to turn off policy tips.</span></span> <span data-ttu-id="4152f-293">如果已关闭，则只是简单通知的策略提示将不会显示在消息栏或 Backstage 视图（“文件”选项卡上）上。</span><span class="sxs-lookup"><span data-stu-id="4152f-293">If turned off, policy tips that are simple notifications will not appear on the Message Bar or Backstage view (on the **File** tab).</span></span> <span data-ttu-id="4152f-294">但是，仍会显示有关阻止和替换的策略提示，并且仍将收到电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="4152f-294">However, policy tips about blocking and overriding will still appear, and they will still receive the email notification.</span></span> <span data-ttu-id="4152f-295">此外，关闭策略提示并不会将文档从任何已对其应用的 DLP 策略中予以免除。</span><span class="sxs-lookup"><span data-stu-id="4152f-295">In addition, turning off policy tips does not exempt the document from any DLP policies that have been applied to it.</span></span>

### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a><span data-ttu-id="4152f-296">Excel 2016、PowerPoint 2016 和 Word 2016 中的策略提示的默认文本</span><span class="sxs-lookup"><span data-stu-id="4152f-296">Default text for policy tips in Excel 2016, PowerPoint 2016, and Word 2016</span></span>

<span data-ttu-id="4152f-p139">默认情况下，策略提示将在打开文档的消息栏和 Backstage 视图中显示类似于以下的文本。通知文本针对每个规则单独配置，因此根据匹配的规则，显示的文本有所不同。</span><span class="sxs-lookup"><span data-stu-id="4152f-p139">By default, policy tips display text similar to the following on the Message Bar and Backstage view of an open document. The notification text is configured separately for each rule, so the text that's displayed differs depending on which rule is matched.</span></span>

|<span data-ttu-id="4152f-299">**如果 DLP 策略规则也是如此...**</span><span class="sxs-lookup"><span data-stu-id="4152f-299">**If the DLP policy rule does this…**</span></span>|<span data-ttu-id="4152f-300">**然后默认策略提示的说明如下...**</span><span class="sxs-lookup"><span data-stu-id="4152f-300">**Then the default policy tip says this…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4152f-301">发送通知但不允许替代</span><span class="sxs-lookup"><span data-stu-id="4152f-301">Sends a notification but doesn't allow override</span></span>  <br/> |<span data-ttu-id="4152f-302">此文件与您的组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="4152f-302">This file conflicts with a policy in your organization.</span></span> <span data-ttu-id="4152f-303">有关详细信息， **请转到"文件** "菜单。</span><span class="sxs-lookup"><span data-stu-id="4152f-303">Go to the **File** menu for more information.</span></span>  <br/> |
|<span data-ttu-id="4152f-304">阻止访问，发送通知，并允许重写</span><span class="sxs-lookup"><span data-stu-id="4152f-304">Blocks access, sends a notification, and allows override</span></span>  <br/> |<span data-ttu-id="4152f-305">此文件与您的组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="4152f-305">This file conflicts with a policy in your organization.</span></span> <span data-ttu-id="4152f-306">如果不解决此冲突，则可能无法访问此文件。</span><span class="sxs-lookup"><span data-stu-id="4152f-306">If you don't resolve this conflict, access to this file might be blocked.</span></span> <span data-ttu-id="4152f-307">有关详细信息， **请转到"文件** "菜单。</span><span class="sxs-lookup"><span data-stu-id="4152f-307">Go to the **File** menu for more information.</span></span>  <br/> |
|<span data-ttu-id="4152f-308">阻止访问，并向发送通知</span><span class="sxs-lookup"><span data-stu-id="4152f-308">Blocks access and sends a notification</span></span>  <br/> |<span data-ttu-id="4152f-309">此文件与您的组织中的策略相冲突。</span><span class="sxs-lookup"><span data-stu-id="4152f-309">This file conflicts with a policy in your organization.</span></span> <span data-ttu-id="4152f-310">如果不解决此冲突，则可能无法访问此文件。</span><span class="sxs-lookup"><span data-stu-id="4152f-310">If you don't resolve this conflict, access to this file might be blocked.</span></span> <span data-ttu-id="4152f-311">有关详细信息， **请转到"文件** "菜单。</span><span class="sxs-lookup"><span data-stu-id="4152f-311">Go to the **File** menu for more information.</span></span>  <br/> |

### <a name="custom-text-for-policy-tips-in-excel-powerpoint-and-word"></a><span data-ttu-id="4152f-312">自定义策略提示的文本，包括 Excel、PowerPoint 和 Word</span><span class="sxs-lookup"><span data-stu-id="4152f-312">Custom text for policy tips in Excel, PowerPoint, and Word</span></span>

<span data-ttu-id="4152f-313">你可以将策略提示的文本与电子邮件通知分开自定义。</span><span class="sxs-lookup"><span data-stu-id="4152f-313">You can customize the text for policy tips separately from the email notification.</span></span> <span data-ttu-id="4152f-314">与上述部分 (电子邮件通知的自定义文本) ，策略提示的自定义文本不接受 HTML 或令牌。</span><span class="sxs-lookup"><span data-stu-id="4152f-314">Unlike custom text for email notifications (see above section), custom text for policy tips does not accept HTML or tokens.</span></span> <span data-ttu-id="4152f-315">相反，策略提示的自定义文本是纯文本，只有 256 个字符的限制。</span><span class="sxs-lookup"><span data-stu-id="4152f-315">Instead, custom text for policy tips is plain text only with a 256-character limit.</span></span>

## <a name="more-information"></a><span data-ttu-id="4152f-316">更多信息</span><span class="sxs-lookup"><span data-stu-id="4152f-316">More information</span></span>

- [<span data-ttu-id="4152f-317">了解数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="4152f-317">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="4152f-318">根据模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="4152f-318">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
- [<span data-ttu-id="4152f-319">DLP 策略条件、例外和操作 (预览) </span><span class="sxs-lookup"><span data-stu-id="4152f-319">DLP policy conditions, exceptions, and actions (preview)</span></span>](./dlp-microsoft-teams.md)
- [<span data-ttu-id="4152f-320">创建 DLP 策略来保护具有 FCI 或其他属性的文档</span><span class="sxs-lookup"><span data-stu-id="4152f-320">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
- [<span data-ttu-id="4152f-321">DLP 策略模板包含的内容</span><span class="sxs-lookup"><span data-stu-id="4152f-321">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
- [<span data-ttu-id="4152f-322">敏感信息类型属性定义</span><span class="sxs-lookup"><span data-stu-id="4152f-322">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)