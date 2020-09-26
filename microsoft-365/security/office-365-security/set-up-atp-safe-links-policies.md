---
title: 设置 Office 365 ATP 安全链接策略
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 设置安全链接策略以保护您的组织免受 Word、Excel、PowerPoint 和 Visio 文件以及电子邮件中的恶意链接。
ms.openlocfilehash: 76d0aba026b96251a64163ef7d7f518fe0b1e1b1
ms.sourcegitcommit: e9f32675061cd1cf4a3e2dada393e10d7c552efe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2020
ms.locfileid: "48279577"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a><span data-ttu-id="efb0c-103">设置 Office 365 ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="efb0c-103">Set up Office 365 ATP Safe Links policies</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="efb0c-104">本文适用于拥有 [Office 365 高级威胁防护](office-365-atp.md)的企业客户。</span><span class="sxs-lookup"><span data-stu-id="efb0c-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="efb0c-105">如果您是在 Outlook 中查找有关安全链接的信息的家庭用户，请参阅 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="efb0c-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="efb0c-106">[Atp 安全链接](atp-safe-links.md) 是 [Office 365 高级威胁防护](office-365-atp.md) 中的一项功能，可帮助保护您的组织免受网络钓鱼和其他攻击中使用的恶意链接的 (ATP) 。</span><span class="sxs-lookup"><span data-stu-id="efb0c-106">[ATP Safe Links](atp-safe-links.md) is a feature in [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) that can help protect your organization from malicious links used in phishing and other attacks.</span></span> <span data-ttu-id="efb0c-107">如果您具有 [安全 & 合规中心](permissions-in-the-security-and-compliance-center.md)的必要权限，则可以设置 ATP 安全链接策略，以帮助确保当用户单击 "web 地址 (url) 时，您的组织受到保护。</span><span class="sxs-lookup"><span data-stu-id="efb0c-107">If you have the necessary [permissions for the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md), you can set up ATP Safe Links policies to help ensure that when people click web addresses (URLs), your organization is protected.</span></span> <span data-ttu-id="efb0c-108">您的 ATP 安全链接策略可以配置为扫描 Office 文档中的电子邮件和 Url 中的 Url。</span><span class="sxs-lookup"><span data-stu-id="efb0c-108">Your ATP Safe Links policies can be configured to scan URLs in email and URLs in Office documents.</span></span> <span data-ttu-id="efb0c-109">ATP 安全链接扫描传入电子邮件的已知恶意超链接和包含恶意软件的附件。</span><span class="sxs-lookup"><span data-stu-id="efb0c-109">ATP Safe Links scans incoming email for known malicious hyperlinks and for attachments containing malware.</span></span> <span data-ttu-id="efb0c-110">此功能将扫描的 Url 重写为 Microsoft 的标准 URL 格式前缀 <https://nam01.safelinks.protection.outlook.com> 。</span><span class="sxs-lookup"><span data-stu-id="efb0c-110">This feature rewrites scanned URLs to Microsoft’s standard URL format prefix <https://nam01.safelinks.protection.outlook.com>.</span></span> <span data-ttu-id="efb0c-111">重写链接后，会对其进行分析以查找任何潜在的恶意内容。</span><span class="sxs-lookup"><span data-stu-id="efb0c-111">Once a link is rewritten, it is analyzed for any potential malicious content.</span></span> <span data-ttu-id="efb0c-112">启用 ATP 安全链接后，如果用户单击电子邮件中的链接，并且该 URL 已被组织的自定义 "阻止 URL" 列表阻止，或者如果该 URL 被确定为 "恶意"，则会打开 "警告" 页。</span><span class="sxs-lookup"><span data-stu-id="efb0c-112">With ATP Safe Links enabled, if a user clicks on a link in an email and the URL has been blocked by your organization's custom blocked URL list or if the URL is determined to be malicious, a warning page will open.</span></span>

<span data-ttu-id="efb0c-113">如果 ATP 安全链接重写了 URL，则在转发或答复邮件时，该 URL 仍将被重写。</span><span class="sxs-lookup"><span data-stu-id="efb0c-113">Once ATP Safe Links has rewritten a URL, if the message is forwarded or replied to, the URL will remain rewritten.</span></span> <span data-ttu-id="efb0c-114">将不会重写添加到要答复或转发的邮件中的其他链接。</span><span class="sxs-lookup"><span data-stu-id="efb0c-114">Additional links added to the message being replied to or forwarded will not be rewritten.</span></span>

<span data-ttu-id="efb0c-115">[将新功能连续添加到 ATP](office-365-atp.md#new-features-in-office-365-atp)。</span><span class="sxs-lookup"><span data-stu-id="efb0c-115">[New features are continually being added to ATP](office-365-atp.md#new-features-in-office-365-atp).</span></span> <span data-ttu-id="efb0c-116">添加新功能时，您可能需要对现有的 ATP 安全链接策略进行调整。</span><span class="sxs-lookup"><span data-stu-id="efb0c-116">As new features are added, you may need to make adjustments to your existing ATP Safe Links policies.</span></span>

## <a name="what-to-do"></a><span data-ttu-id="efb0c-117">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="efb0c-117">What to do</span></span>

1. <span data-ttu-id="efb0c-118">查看先决条件。</span><span class="sxs-lookup"><span data-stu-id="efb0c-118">Review the prerequisites.</span></span>

2. <span data-ttu-id="efb0c-119">查看和编辑适用于每个人的默认 ATP 安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="efb0c-119">Review and edit the default ATP Safe Links policy that applies to everyone.</span></span> <span data-ttu-id="efb0c-120">例如，您可以 [为 ATP 安全链接设置自定义阻止的 url 列表](set-up-a-custom-blocked-urls-list-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="efb0c-120">For example, you can [set up your custom blocked URLs list for ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md).</span></span>

3. <span data-ttu-id="efb0c-121">为特定的电子邮件收件人添加或编辑策略，包括 [设置 ATP 安全链接的自定义 "不重写" url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="efb0c-121">Add or edit policies for specific email recipients, including [setting up your custom "Do not rewrite" URLs list for ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>

4. <span data-ttu-id="efb0c-122">了解本文中 (的 ATP 安全链接策略选项) ，包括最近更改的设置。</span><span class="sxs-lookup"><span data-stu-id="efb0c-122">Learn about ATP Safe Links policy options (in this article), including settings for recent changes.</span></span>

## <a name="step-1-review-the-prerequisites"></a><span data-ttu-id="efb0c-123">步骤1：查看先决条件</span><span class="sxs-lookup"><span data-stu-id="efb0c-123">Step 1: Review the prerequisites</span></span>

- <span data-ttu-id="efb0c-124">确保您的组织具有 [Office 365 高级威胁防护](office-365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="efb0c-124">Make sure that your organization has [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span>

- <span data-ttu-id="efb0c-125">请确保您具有必要的权限。</span><span class="sxs-lookup"><span data-stu-id="efb0c-125">Make sure that you have the necessary permissions.</span></span> <span data-ttu-id="efb0c-126">若要定义 (或编辑) ATP 策略，必须为您分配适当的角色。</span><span class="sxs-lookup"><span data-stu-id="efb0c-126">To define (or edit) ATP policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="efb0c-127">下表介绍了一些示例：</span><span class="sxs-lookup"><span data-stu-id="efb0c-127">Some examples are described in the following table:</span></span>

    |<span data-ttu-id="efb0c-128">角色</span><span class="sxs-lookup"><span data-stu-id="efb0c-128">Role</span></span>|<span data-ttu-id="efb0c-129">分配的位置/方式</span><span class="sxs-lookup"><span data-stu-id="efb0c-129">Where/how assigned</span></span>|
    |---|---|
    |<span data-ttu-id="efb0c-130">全局管理员</span><span class="sxs-lookup"><span data-stu-id="efb0c-130">global administrator</span></span>|<span data-ttu-id="efb0c-131">默认情况下，注册购买 Microsoft 365 的人是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="efb0c-131">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="efb0c-132"> (参阅 [关于 Microsoft 365 管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) ，了解详细信息。 ) </span><span class="sxs-lookup"><span data-stu-id="efb0c-132">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
    |<span data-ttu-id="efb0c-133">安全管理员</span><span class="sxs-lookup"><span data-stu-id="efb0c-133">Security Administrator</span></span>|<span data-ttu-id="efb0c-134">Azure Active Directory 管理员中心 (<https://aad.portal.azure.com>) </span><span class="sxs-lookup"><span data-stu-id="efb0c-134">Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>|
    |<span data-ttu-id="efb0c-135">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="efb0c-135">Exchange Online Organization Management</span></span>|<span data-ttu-id="efb0c-136">Exchange 管理中心 (<https://outlook.office365.com/ecp>) </span><span class="sxs-lookup"><span data-stu-id="efb0c-136">Exchange admin center (<https://outlook.office365.com/ecp>)</span></span> <br><span data-ttu-id="efb0c-137">或</span><span class="sxs-lookup"><span data-stu-id="efb0c-137">or</span></span> <br>  <span data-ttu-id="efb0c-138">PowerShell cmdlet (参阅 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)) </span><span class="sxs-lookup"><span data-stu-id="efb0c-138">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|

    <span data-ttu-id="efb0c-139">若要了解有关角色和权限的详细信息，请参阅 [Security & 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="efb0c-139">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="efb0c-140">请确保将 Office 客户端配置为使用 [新式验证](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016) (这适用于 office 文档中的 ATP 安全链接保护) 。</span><span class="sxs-lookup"><span data-stu-id="efb0c-140">Make sure that Office clients are configured to use [Modern Authentication](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016) (this is for ATP Safe Links protection in Office documents).</span></span>

- <span data-ttu-id="efb0c-141">了解本文中 (的[ATP 安全链接策略选项](#step-4-learn-about-atp-safe-links-policy-options)) 。</span><span class="sxs-lookup"><span data-stu-id="efb0c-141">[Learn about ATP Safe Links policy options](#step-4-learn-about-atp-safe-links-policy-options) (in this article).</span></span>

- <span data-ttu-id="efb0c-142">最长允许30分钟，新的或更新的策略将传播到所有 Microsoft 365 数据中心。</span><span class="sxs-lookup"><span data-stu-id="efb0c-142">Allow up to 30 minutes for your new or updated policy to spread to all Microsoft 365 datacenters.</span></span>

## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a><span data-ttu-id="efb0c-143">步骤2：定义 (或审阅) 适用于每个人的 ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="efb0c-143">Step 2: Define (or review) the ATP Safe Links policy that applies to everyone</span></span>

<span data-ttu-id="efb0c-144">当您拥有 [Office 365 高级威胁防护功能](office-365-atp.md)时，将拥有适用于组织中每个人的默认 ATP 安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="efb0c-144">When you have [Office 365 Advanced Threat Protection](office-365-atp.md), you will have a default ATP Safe Links policy that applies to everyone in your organization.</span></span> <span data-ttu-id="efb0c-145">请务必查看，如果需要，请编辑您的默认策略。</span><span class="sxs-lookup"><span data-stu-id="efb0c-145">Make sure to review, and if needed, edit your default policy.</span></span>

1. <span data-ttu-id="efb0c-146">转到 <https://protection.office.com> 并使用你的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="efb0c-146">Go to <https://protection.office.com> and sign in with your work or school account.</span></span>

2. <span data-ttu-id="efb0c-147">在左侧导航中的 "**威胁管理**" 下，选择 "\*\*策略 \> \*\* **安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="efb0c-147">In the left navigation, under **Threat management**, choose **Policy \>** **Safe Links**.</span></span>

3. <span data-ttu-id="efb0c-148">在 " **适用于整个组织的策略** " 部分中，选择 " **默认**"，然后选择 " **编辑** " (编辑按钮类似于铅笔) 。</span><span class="sxs-lookup"><span data-stu-id="efb0c-148">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span>

   ![单击 "编辑" 编辑安全链接保护的默认策略](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)

4. <span data-ttu-id="efb0c-150">在 " **阻止以下 url** " 部分中，指定要阻止组织中的用户访问的一个或多个 url。</span><span class="sxs-lookup"><span data-stu-id="efb0c-150">In the **Block the following URLs** section, specify one or more URLs that you want to prevent people in your organization from visiting.</span></span> <span data-ttu-id="efb0c-151"> (请参阅 [使用 ATP 安全链接设置自定义阻止的 url 列表](set-up-a-custom-blocked-urls-list-atp.md)。 ) </span><span class="sxs-lookup"><span data-stu-id="efb0c-151">(See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md).)</span></span>

5. <span data-ttu-id="efb0c-152">在 " **应用于内容（电子邮件除外** ）" 部分的 "设置" 中，选择 " (" 或 "清除) 您要使用的选项"。</span><span class="sxs-lookup"><span data-stu-id="efb0c-152">In the **Settings that apply to content except email** section, select (or clear) the options you want to use.</span></span> <span data-ttu-id="efb0c-153"> (建议您选择所有选项。 ) </span><span class="sxs-lookup"><span data-stu-id="efb0c-153">(We recommend that you select all the options.)</span></span>

6. <span data-ttu-id="efb0c-154">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="efb0c-154">Choose **Save**.</span></span>
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-all-or-specific-email-recipients"></a><span data-ttu-id="efb0c-155">步骤3：添加 (或编辑适用于所有或特定电子邮件收件人的) ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="efb0c-155">Step 3: Add (or edit) ATP Safe Links policies that apply to all or specific email recipients</span></span>

<span data-ttu-id="efb0c-156">在查看 (或编辑) 适用于每个人的默认 ATP 安全链接策略之后，下一步是定义将应用于所有或特定的电子邮件收件人的其他策略。</span><span class="sxs-lookup"><span data-stu-id="efb0c-156">After you have reviewed (or edited) the default ATP Safe Links policy that applies to everyone, your next step is to define additional policies that would apply to all or specific email recipients.</span></span> <span data-ttu-id="efb0c-157">例如，您可以通过定义其他策略或为所有员工创建更精确的限制来指定您的默认策略的例外。</span><span class="sxs-lookup"><span data-stu-id="efb0c-157">For example, you can specify exceptions to your default policy by defining an additional policy or create more granular restrictions for all employees.</span></span>
  
1. <span data-ttu-id="efb0c-158">转到 <https://protection.office.com> 并使用你的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="efb0c-158">Go to <https://protection.office.com> and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="efb0c-159">在左侧导航中的 " **威胁管理**" 下，选择 " **策略**"。</span><span class="sxs-lookup"><span data-stu-id="efb0c-159">In the left navigation, under **Threat management**, choose **Policy**.</span></span>

3. <span data-ttu-id="efb0c-160">选择 " **安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="efb0c-160">Choose **Safe Links**.</span></span>

4. <span data-ttu-id="efb0c-161">在 " **适用于特定收件人的策略** " 部分中，选择 " **新建** " (新按钮类似于加号 ( **+**) # A3。</span><span class="sxs-lookup"><span data-stu-id="efb0c-161">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)).</span></span>

   ![选择 "新建" 为特定的电子邮件收件人添加安全链接策略](../../media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)

5. <span data-ttu-id="efb0c-163">指定策略的名称、说明和设置。</span><span class="sxs-lookup"><span data-stu-id="efb0c-163">Specify the name, description, and settings for your policy.</span></span>

   <span data-ttu-id="efb0c-164">**示例：** 若要设置一个名为 "无直接单击" 的策略，且不允许组织中特定组中的用户在没有 ATP 安全链接保护的情况下单击特定网站，可以指定以下推荐设置：</span><span class="sxs-lookup"><span data-stu-id="efb0c-164">**Example:** To set up a policy called "no direct click through" that does not allow people in a certain group in your organization to click through to a specific website without ATP Safe Links protection, you might specify the following recommended settings:</span></span>

   - <span data-ttu-id="efb0c-165">在 " **名称** " 框中，键入 "无直接单击"。</span><span class="sxs-lookup"><span data-stu-id="efb0c-165">In the **Name** box, type no direct click through.</span></span>

   - <span data-ttu-id="efb0c-166">在 " **说明** " 框中，键入一个说明（如），以防止某些组中的用户在没有 ATP 安全链接验证的情况下单击到网站。</span><span class="sxs-lookup"><span data-stu-id="efb0c-166">In the **Description** box, type a description like, Prevents people in certain groups from clicking through to a website without ATP Safe Links verification.</span></span>

   - <span data-ttu-id="efb0c-167">在 " **选择操作** " 部分，选择 **"启用"**。</span><span class="sxs-lookup"><span data-stu-id="efb0c-167">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="efb0c-168">**对于可疑链接和指向文件的链接，请选择 "应用实时 url 扫描**"。如果您想要启用 URL 沙箱以查找可疑和文件指向的 url (建议的) 。</span><span class="sxs-lookup"><span data-stu-id="efb0c-168">Select **Apply real-time URL scanning for suspicious links and links that point to files** if you would like to enable URL detonation for suspicious and file-pointing URLs (recommended).</span></span> <span data-ttu-id="efb0c-169">如果您希望仅在完全扫描 Url 后用户收到邮件，则 **在传递邮件之前，请选择 "等待 URL 扫描完成"** 。</span><span class="sxs-lookup"><span data-stu-id="efb0c-169">And select **Wait for URL scanning to complete before delivering the message** if you wish to only have users receive messages after the URLs have been fully scanned.</span></span>

   - <span data-ttu-id="efb0c-170">如果要为组织内的用户之间发送的邮件启用安全链接，请选择 **"将安全链接应用于在组织内发送的邮件"** 。 (建议的) 。</span><span class="sxs-lookup"><span data-stu-id="efb0c-170">Select **Apply Safe Links to messages sent within the organization** if you would like to enable Safe Links for messages sent between users within your organization (recommended).</span></span>

   - <span data-ttu-id="efb0c-171">如果您不希望单个用户覆盖*正在进行的扫描*或*URL 阻止*的通知页面，请选择 **"不允许用户单击到原始 URL"** 。</span><span class="sxs-lookup"><span data-stu-id="efb0c-171">Select **Do not allow user to click through to original URL** if you do not wish the individual users to override a *scan in progress* or *URL blocked* notification pages.</span></span>

   - <span data-ttu-id="efb0c-172"> (这是可选的) 在 " **不重写以下 url"** 部分中，指定一个或多个被视为对您的组织而言是安全的 url。</span><span class="sxs-lookup"><span data-stu-id="efb0c-172">(This is optional) In the **Do not rewrite the following URLs** section, specify one or more URLs that are considered to be safe for your organization.</span></span> <span data-ttu-id="efb0c-173"> (参阅 [设置自定义 "不重写" 使用 ATP 安全链接的 url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)) </span><span class="sxs-lookup"><span data-stu-id="efb0c-173">(See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))</span></span>

   - <span data-ttu-id="efb0c-174">在 " **应用** 于" 部分中，选择 **"收件人是其成员**"，然后选择要在策略中包括的组 (s) 。</span><span class="sxs-lookup"><span data-stu-id="efb0c-174">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy.</span></span> <span data-ttu-id="efb0c-175">选择 " **添加**"，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="efb0c-175">Choose **Add**, and then choose **OK**.</span></span>

6. <span data-ttu-id="efb0c-176">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="efb0c-176">Choose **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="efb0c-177">优先级较高的 ATP 安全链接策略将优先。</span><span class="sxs-lookup"><span data-stu-id="efb0c-177">ATP Safe Links policies with higher priority will take precedence.</span></span> <span data-ttu-id="efb0c-178">如果用户接受两个或更多个策略，则只有较高优先级的策略才能生效。</span><span class="sxs-lookup"><span data-stu-id="efb0c-178">If a user is subject to two or more policies, only the higher priority policy will take effect.</span></span> <span data-ttu-id="efb0c-179">如果您希望客户策略优先执行，则需要提高策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="efb0c-179">If you want the customer policy to take precedence, you need to raise the priority of the policy.</span></span>

## <a name="step-4-learn-about-atp-safe-links-policy-options"></a><span data-ttu-id="efb0c-180">步骤4：了解 ATP 安全链接策略选项</span><span class="sxs-lookup"><span data-stu-id="efb0c-180">Step 4: Learn about ATP Safe Links policy options</span></span>

<span data-ttu-id="efb0c-181">在设置或编辑 ATP 安全链接策略时，将看到几个可用选项。</span><span class="sxs-lookup"><span data-stu-id="efb0c-181">As you set up or edit your ATP Safe Links policies, will see several options available.</span></span> <span data-ttu-id="efb0c-182">如果您想知道这些选项是什么，下表介绍了每一个选项及其效果。</span><span class="sxs-lookup"><span data-stu-id="efb0c-182">In case you are wondering what these options are, the following table describes each one and its effect.</span></span> <span data-ttu-id="efb0c-183">请注意，有两种主要的 ATP 安全链接策略可供定义或编辑：</span><span class="sxs-lookup"><span data-stu-id="efb0c-183">Remember that there are two main kinds of ATP Safe Links policies to define or edit:</span></span>

- <span data-ttu-id="efb0c-184">适用于每个人的 [默认策略](#default-policy-options) ;并</span><span class="sxs-lookup"><span data-stu-id="efb0c-184">a [default policy](#default-policy-options) that applies to everyone; and</span></span>
- <span data-ttu-id="efb0c-185">[针对特定收件人的其他策略](#policies-that-apply-to-specific-email-recipients)</span><span class="sxs-lookup"><span data-stu-id="efb0c-185">additional [policies for specific recipients](#policies-that-apply-to-specific-email-recipients)</span></span>

### <a name="default-policy-options"></a><span data-ttu-id="efb0c-186">默认策略选项</span><span class="sxs-lookup"><span data-stu-id="efb0c-186">Default policy options</span></span>

<span data-ttu-id="efb0c-187">默认策略选项适用于组织中的所有人。</span><span class="sxs-lookup"><span data-stu-id="efb0c-187">Default policy options apply to everyone in your organization.</span></span>

****

|<span data-ttu-id="efb0c-188">此选项</span><span class="sxs-lookup"><span data-stu-id="efb0c-188">This option</span></span>|<span data-ttu-id="efb0c-189">执行的操作</span><span class="sxs-lookup"><span data-stu-id="efb0c-189">Does this</span></span>|
|---|---|
|<span data-ttu-id="efb0c-190">**阻止以下 Url**</span><span class="sxs-lookup"><span data-stu-id="efb0c-190">**Block the following URLs**</span></span>|<span data-ttu-id="efb0c-191">允许您的组织具有自动阻止的自定义 Url 的自定义列表。</span><span class="sxs-lookup"><span data-stu-id="efb0c-191">Enables your organization to have a custom list of URLs that are automatically blocked.</span></span> <span data-ttu-id="efb0c-192">当用户单击此列表中的某个 URL 时，将会看到一个 [警告页面](atp-safe-links-warning-pages.md) ，说明为什么阻止了该 url。</span><span class="sxs-lookup"><span data-stu-id="efb0c-192">When users click a URL in this list, they'll be taken to a [warning page](atp-safe-links-warning-pages.md) that explains why the URL is blocked.</span></span> <span data-ttu-id="efb0c-193">若要了解详细信息，请参阅 [使用 Office 365 ATP 安全链接设置自定义阻止的 url 列表](set-up-a-custom-blocked-urls-list-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="efb0c-193">To learn more, see [Set up a custom blocked URLs list using Office 365 ATP Safe Links](set-up-a-custom-blocked-urls-list-atp.md).</span></span>|
|<span data-ttu-id="efb0c-194">**适用于企业的 Microsoft 365 应用、适用于 iOS 和 Android 的 Office**</span><span class="sxs-lookup"><span data-stu-id="efb0c-194">**Microsoft 365 Apps for enterprise, Office for iOS and Android**</span></span>| <span data-ttu-id="efb0c-195">选择此选项时，ATP 安全链接保护适用于 Windows 或 Mac OS 上的 Word、Excel 和 PowerPoint 文件中的 Url、Outlook 中的电子邮件、iOS 或 Android 设备上的 Office 文档、Windows 上的 Visio 2016 文件以及在 Office 应用程序的 web 版本中打开的文件 (Word、PowerPoint、Excel、Outlook 和 OneNote) ，前提是用户已登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="efb0c-195">When this option is selected, ATP Safe Links protection is applied to URLs in Word, Excel, and PowerPoint files on Windows or Mac OS, email messages in Outlook, Office documents on iOS or Android devices, Visio 2016 files on Windows, and files open in the web versions of Office apps (Word, PowerPoint, Excel, Outlook, and OneNote), provided the user has signed in to Office 365.</span></span>|
|<span data-ttu-id="efb0c-196">**在用户单击 ATP 安全链接时不进行跟踪**</span><span class="sxs-lookup"><span data-stu-id="efb0c-196">**Don't track when users click ATP Safe Links**</span></span>|<span data-ttu-id="efb0c-197">选择此选项后，将不存储在 Word、Excel、PowerPoint、Visio 文档和 Outlook 电子邮件中的 Url 的数据。</span><span class="sxs-lookup"><span data-stu-id="efb0c-197">When this option is selected, click data for URLs in Word, Excel, PowerPoint, Visio documents, and Outlook email messages is not stored.</span></span>|
|<span data-ttu-id="efb0c-198">**不要让用户点击到原始 URL 的 ATP 安全链接**</span><span class="sxs-lookup"><span data-stu-id="efb0c-198">**Don't let users click through ATP Safe Links to original URL**</span></span>|<span data-ttu-id="efb0c-199">选择此选项后，用户将无法继续处理被确定为恶意的 URL 之后的 [警告页](atp-safe-links-warning-pages.md) 。</span><span class="sxs-lookup"><span data-stu-id="efb0c-199">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>|
|

### <a name="policies-that-apply-to-specific-email-recipients"></a><span data-ttu-id="efb0c-200">适用于特定电子邮件收件人的策略</span><span class="sxs-lookup"><span data-stu-id="efb0c-200">Policies that apply to specific email recipients</span></span>

****

|<span data-ttu-id="efb0c-201">此选项</span><span class="sxs-lookup"><span data-stu-id="efb0c-201">This option</span></span>|<span data-ttu-id="efb0c-202">执行的操作</span><span class="sxs-lookup"><span data-stu-id="efb0c-202">Does this</span></span>|
|---|---|
|<span data-ttu-id="efb0c-203">**停**</span><span class="sxs-lookup"><span data-stu-id="efb0c-203">**Off**</span></span>|<span data-ttu-id="efb0c-204">不扫描电子邮件中的 Url。</span><span class="sxs-lookup"><span data-stu-id="efb0c-204">Does not scan URLs in email messages.</span></span>  <br/> <span data-ttu-id="efb0c-205">使您能够定义例外规则，如不扫描电子邮件中的 Url 的特定收件人组的 Url 的规则。</span><span class="sxs-lookup"><span data-stu-id="efb0c-205">Enables you to define an exception rule, such as a rule that does not scan URLs in email messages for a specific group of recipients.</span></span>|
|<span data-ttu-id="efb0c-206">**On**</span><span class="sxs-lookup"><span data-stu-id="efb0c-206">**On**</span></span>|<span data-ttu-id="efb0c-207">通过在用户单击电子邮件中的 Url 并启用 Outlook (C2R) 在 Windows 中的 ATP 安全链接，来重写 Url 以在 ATP 安全链接保护中路由用户。</span><span class="sxs-lookup"><span data-stu-id="efb0c-207">Rewrites URLs to route users through ATP Safe Links protection when the users click URLs in email messages and enables ATP Safe Links within Outlook (C2R) on Windows.</span></span>  <br/> <span data-ttu-id="efb0c-208">在对阻止或恶意 Url 列表单击时检查 URL，并在后台异步触发 URL 的沙箱，前提是该 URL 没有有效的信誉。</span><span class="sxs-lookup"><span data-stu-id="efb0c-208">Checks a URL when clicked against a list of blocked or malicious URLs and triggers a detonation of the URL in the background asynchronously if the URL does not have a valid reputation.</span></span>|
|<span data-ttu-id="efb0c-209">**对指向文件的可疑链接和链接应用实时 URL 扫描**</span><span class="sxs-lookup"><span data-stu-id="efb0c-209">**Apply real-time URL scanning for suspicious links and links that point to files**</span></span>|<span data-ttu-id="efb0c-210">如果选择此选项，则会扫描指向可下载内容的可疑 Url 和链接。</span><span class="sxs-lookup"><span data-stu-id="efb0c-210">When this option is selected, suspicious URLs and links that point to downloadable content are scanned.</span></span>|
|<span data-ttu-id="efb0c-211">**等待 URL 扫描完成后再传递邮件**</span><span class="sxs-lookup"><span data-stu-id="efb0c-211">**Wait for URL scanning to complete before delivering the message**</span></span>|<span data-ttu-id="efb0c-212">如果选择此选项，则将一直保留包含要扫描的 Url 的邮件，直到 Url 完成扫描并在传递邮件之前将其确认为安全。</span><span class="sxs-lookup"><span data-stu-id="efb0c-212">When this option is selected, messages that contain URLs to be scanned will be held until the URLs finish scanning and are confirmed to be safe before the messages are delivered.</span></span>|
|<span data-ttu-id="efb0c-213">**将安全链接应用于在组织内发送的邮件**</span><span class="sxs-lookup"><span data-stu-id="efb0c-213">**Apply Safe Links to messages sent within the organization**</span></span> <br/> | <span data-ttu-id="efb0c-214">当此选项可用并选中时，如果电子邮件帐户托管在 Office 365 中，则会将 ATP 安全链接保护应用于在组织中的人员之间发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="efb0c-214">When this option is available and selected, ATP Safe Links protection is applied to email messages sent between people in your organization, provided the email accounts are hosted in Office 365.</span></span>|
|<span data-ttu-id="efb0c-215">**不跟踪用户点击**</span><span class="sxs-lookup"><span data-stu-id="efb0c-215">**Do not track user clicks**</span></span>|<span data-ttu-id="efb0c-216">选择此选项后，请单击 "来自外部发件人的电子邮件中的 Url 数据未存储"。</span><span class="sxs-lookup"><span data-stu-id="efb0c-216">When this option is selected, click data for URLs in email from external senders is not stored.</span></span> <span data-ttu-id="efb0c-217">URL 单击 "跟踪" 以查找在组织内发送的电子邮件中的链接当前不受支持。</span><span class="sxs-lookup"><span data-stu-id="efb0c-217">URL click tracking for links within email messages sent within the organization is currently not supported.</span></span>|
|<span data-ttu-id="efb0c-218">**不允许用户单击到原始 URL**</span><span class="sxs-lookup"><span data-stu-id="efb0c-218">**Do not allow users to click through to original URL**</span></span>|<span data-ttu-id="efb0c-219">选择此选项后，用户将无法继续处理被确定为恶意的 URL 之后的 [警告页](atp-safe-links-warning-pages.md) 。</span><span class="sxs-lookup"><span data-stu-id="efb0c-219">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>|
|<span data-ttu-id="efb0c-220">**不重写以下 Url**</span><span class="sxs-lookup"><span data-stu-id="efb0c-220">**Do not rewrite the following URLs**</span></span>|<span data-ttu-id="efb0c-221">将 Url 保留为。</span><span class="sxs-lookup"><span data-stu-id="efb0c-221">Leaves URLs as they are.</span></span> <span data-ttu-id="efb0c-222">保留自定义不需要在组织中对特定电子邮件收件人组进行扫描的安全 Url 列表。</span><span class="sxs-lookup"><span data-stu-id="efb0c-222">Keeps a custom list of safe URLs that don't need scanning for a specific group of email recipients in your organization.</span></span> <span data-ttu-id="efb0c-223">有关更多详细信息，请参阅 [设置自定义 "不重写" url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) （包括对通配符星号 () 支持的最新更改） \* 。</span><span class="sxs-lookup"><span data-stu-id="efb0c-223">See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for more details, including recent changes to support for wildcard asterisks (\*).</span></span>|
|

## <a name="next-steps"></a><span data-ttu-id="efb0c-224">后续步骤</span><span class="sxs-lookup"><span data-stu-id="efb0c-224">Next steps</span></span>

<span data-ttu-id="efb0c-225">在 ATP 安全链接策略准备就绪后，您可以通过查看报告了解 ATP 是如何为您的组织工作的。</span><span class="sxs-lookup"><span data-stu-id="efb0c-225">Once your ATP Safe Links policies are in place, you can see how ATP is working for your organization by viewing reports.</span></span> <span data-ttu-id="efb0c-226">若要了解详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="efb0c-226">See the following resources to learn more:</span></span>

- [<span data-ttu-id="efb0c-227">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="efb0c-227">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

- [<span data-ttu-id="efb0c-228">使用安全与合规中心内的资源管理器</span><span class="sxs-lookup"><span data-stu-id="efb0c-228">Use Explorer in the Security & Compliance Center</span></span>](threat-explorer.md)

<span data-ttu-id="efb0c-229">继续在新功能的前面提供 ATP。</span><span class="sxs-lookup"><span data-stu-id="efb0c-229">Stay on top of new features coming to ATP.</span></span> <span data-ttu-id="efb0c-230">请访问 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)。</span><span class="sxs-lookup"><span data-stu-id="efb0c-230">visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).</span></span>
