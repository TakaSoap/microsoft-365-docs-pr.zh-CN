---
title: 邮件加密（OME）版本比较
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 帮助解释邮件加密版本之间的差异。
ms.openlocfilehash: 89d145f19591ba59df6983bb8863a8e0cc28fcf3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626788"
---
# <a name="compare-versions-of-ome"></a><span data-ttu-id="3684f-103">比较 OME 的版本</span><span class="sxs-lookup"><span data-stu-id="3684f-103">Compare versions of OME</span></span>

<span data-ttu-id="3684f-104">本文将旧版 Office 365 邮件加密（OME）与新的 OME 功能和 Office 365 高级邮件加密进行比较。</span><span class="sxs-lookup"><span data-stu-id="3684f-104">This article compares legacy Office 365 Message Encryption (OME) to the new OME capabilities and Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="3684f-105">新功能是 OME 和信息权限管理（IRM）的合并和更新版本。</span><span class="sxs-lookup"><span data-stu-id="3684f-105">The new capabilities are a merger and newer version of both OME and Information Rights Management (IRM).</span></span> <span data-ttu-id="3684f-106">此外，还概述了将部署到 GCC 高的独特特征。</span><span class="sxs-lookup"><span data-stu-id="3684f-106">Unique characteristics of deploying into GCC High are also outlined.</span></span> <span data-ttu-id="3684f-107">这两个可以在您的组织中共存。</span><span class="sxs-lookup"><span data-stu-id="3684f-107">The two can coexist in your organization.</span></span> <span data-ttu-id="3684f-108">有关新功能的工作方式的信息，请参阅[Office 365 邮件加密（OME）](ome.md)。</span><span class="sxs-lookup"><span data-stu-id="3684f-108">For information on how the new capabilities work, see [Office 365 Message Encryption (OME)](ome.md).</span></span>

||
|:-----|
|<span data-ttu-id="3684f-109">本文是有关 Office 365 邮件加密的更多系列文章的一部分。</span><span class="sxs-lookup"><span data-stu-id="3684f-109">This article is part of a larger series of articles about Office 365 Message Encryption.</span></span> <span data-ttu-id="3684f-110">本文适用于管理员和 ITPros。</span><span class="sxs-lookup"><span data-stu-id="3684f-110">This article is intended for administrators and ITPros.</span></span> <span data-ttu-id="3684f-111">如果只是查找有关发送或接收加密邮件的信息，请参阅[Office 365 邮件加密（OME）](ome.md)中的文章列表，并找到最符合您的需求的文章。</span><span class="sxs-lookup"><span data-stu-id="3684f-111">If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

## <a name="side-by-side-comparison-of-features-and-capabilities"></a><span data-ttu-id="3684f-112">特性和功能的并排比较</span><span class="sxs-lookup"><span data-stu-id="3684f-112">Side-by-side comparison of features and capabilities</span></span>

|                                   |<span data-ttu-id="3684f-113">旧功能</span><span class="sxs-lookup"><span data-stu-id="3684f-113">Old features</span></span>       |                   |<span data-ttu-id="3684f-114">新增功能</span><span class="sxs-lookup"><span data-stu-id="3684f-114">New features</span></span>              |
|-----------------------------------|-------------------|-------------------|--------------------------|
|<span data-ttu-id="3684f-115">**功能**</span><span class="sxs-lookup"><span data-stu-id="3684f-115">**Capability**</span></span>                     | <span data-ttu-id="3684f-116">**旧 OME**</span><span class="sxs-lookup"><span data-stu-id="3684f-116">**Legacy OME**</span></span>    | <span data-ttu-id="3684f-117">**IRM**</span><span class="sxs-lookup"><span data-stu-id="3684f-117">**IRM**</span></span>           | <span data-ttu-id="3684f-118">**新的 OME 功能**</span><span class="sxs-lookup"><span data-stu-id="3684f-118">**New OME capabilities**</span></span> |
|<span data-ttu-id="3684f-119">*发送加密邮件*</span><span class="sxs-lookup"><span data-stu-id="3684f-119">*Sending an encrypted mail*</span></span>        |<span data-ttu-id="3684f-120">通过 Exchange 邮件流规则</span><span class="sxs-lookup"><span data-stu-id="3684f-120">Through Exchange mail flow rules</span></span>|<span data-ttu-id="3684f-121">最终用户是从 Outlook 桌面或 Web 上的 Outlook 启动的;或通过 Exchange 邮件流规则</span><span class="sxs-lookup"><span data-stu-id="3684f-121">End-user initiated from Outlook desktop or Outlook on the Web; or through Exchange mail flow rules</span></span>|<span data-ttu-id="3684f-122">最终用户从 Outlook 桌面、Outlook for Mac 或 Web 上的 Outlook 启动;通过 Exchange 邮件流规则（也称为传输规则）和数据丢失防护（DLP）</span><span class="sxs-lookup"><span data-stu-id="3684f-122">End-user initiated from Outlook desktop, Outlook for Mac, or Outlook on the Web; through Exchange mail flow rules (also known as transport rules) and Data Loss Prevention (DLP)</span></span>|
|<span data-ttu-id="3684f-123">*权限管理模板*</span><span class="sxs-lookup"><span data-stu-id="3684f-123">*Rights management template*</span></span>       |   <span data-ttu-id="3684f-124">不适用</span><span class="sxs-lookup"><span data-stu-id="3684f-124">N/A</span></span>      |<span data-ttu-id="3684f-125">"不要转发" 选项和自定义模板</span><span class="sxs-lookup"><span data-stu-id="3684f-125">Do Not Forward option and custom templates</span></span>|<span data-ttu-id="3684f-126">不转发选项、仅加密选项和自定义模板</span><span class="sxs-lookup"><span data-stu-id="3684f-126">Do Not Forward option, Encrypt-Only option, and custom templates</span></span>|
|<span data-ttu-id="3684f-127">*收件人类型*</span><span class="sxs-lookup"><span data-stu-id="3684f-127">*Recipient type*</span></span>                   |<span data-ttu-id="3684f-128">内部和外部收件人</span><span class="sxs-lookup"><span data-stu-id="3684f-128">Internal and external recipients</span></span>|<span data-ttu-id="3684f-129">仅限内部收件人</span><span class="sxs-lookup"><span data-stu-id="3684f-129">Internal recipients only</span></span>         |<span data-ttu-id="3684f-130">内部和外部收件人</span><span class="sxs-lookup"><span data-stu-id="3684f-130">Internal and external recipients</span></span>|
|<span data-ttu-id="3684f-131">*内部收件人的体验*</span><span class="sxs-lookup"><span data-stu-id="3684f-131">*Experience for internal recipient*</span></span>|<span data-ttu-id="3684f-132">收件人收到 HTML 邮件，并在 web 浏览器或移动应用程序中将其下载和打开</span><span class="sxs-lookup"><span data-stu-id="3684f-132">Recipients receive an HTML message, which they download and open in a web browser or mobile app</span></span>|<span data-ttu-id="3684f-133">Outlook 客户端中的本机内嵌体验</span><span class="sxs-lookup"><span data-stu-id="3684f-133">Native inline experience in Outlook clients</span></span>|<span data-ttu-id="3684f-134">使用 Outlook 客户端的相同组织中的收件人的本机内嵌体验。</span><span class="sxs-lookup"><span data-stu-id="3684f-134">Native inline experience for recipients in the same organization using Outlook clients.</span></span>  <span data-ttu-id="3684f-135">收件人可以使用除 Outlook 之外的客户端（无需下载或应用程序）从 OME 门户读取邮件。</span><span class="sxs-lookup"><span data-stu-id="3684f-135">Recipients can read message from OME portal using clients other than Outlook (no download or app required).</span></span>|
|<span data-ttu-id="3684f-136">*外部收件人的体验*</span><span class="sxs-lookup"><span data-stu-id="3684f-136">*Experience for external recipient*</span></span>|<span data-ttu-id="3684f-137">收件人收到 HTML 邮件，并在 web 浏览器或移动应用程序中将其下载和打开</span><span class="sxs-lookup"><span data-stu-id="3684f-137">Recipients receive an HTML message, which they download and open in a web browser or mobile app</span></span>|<span data-ttu-id="3684f-138">不适用</span><span class="sxs-lookup"><span data-stu-id="3684f-138">N/A</span></span>|<span data-ttu-id="3684f-139">Microsoft 365 收件人的本机内嵌体验。</span><span class="sxs-lookup"><span data-stu-id="3684f-139">Native inline experience for Microsoft 365 recipients.</span></span> <span data-ttu-id="3684f-140">所有其他收件人都可以从 OME 门户读取邮件（无需下载或应用程序）。</span><span class="sxs-lookup"><span data-stu-id="3684f-140">All other recipients can read message from OME portal (no download or app required).</span></span>|
|<span data-ttu-id="3684f-141">*附件权限*</span><span class="sxs-lookup"><span data-stu-id="3684f-141">*Attachment permissions*</span></span>           |<span data-ttu-id="3684f-142">对附件没有限制</span><span class="sxs-lookup"><span data-stu-id="3684f-142">No restrictions on attachments</span></span>|<span data-ttu-id="3684f-143">附件受到保护</span><span class="sxs-lookup"><span data-stu-id="3684f-143">Attachments are protected</span></span>|<span data-ttu-id="3684f-144">附件受到保护，可用于 "不转发" 选项和自定义模板。</span><span class="sxs-lookup"><span data-stu-id="3684f-144">Attachments are protected for the Do Not Forward option and custom templates.</span></span> <span data-ttu-id="3684f-145">管理员可以选择仅加密选项的附件是否受保护。</span><span class="sxs-lookup"><span data-stu-id="3684f-145">Admins can choose whether attachments for the Encrypt-Only option are protected or not.</span></span>|
|<span data-ttu-id="3684f-146">*引入你自己的密钥（BYOK）支持*</span><span class="sxs-lookup"><span data-stu-id="3684f-146">*Bring your own key (BYOK) support*</span></span>|<span data-ttu-id="3684f-147">无</span><span class="sxs-lookup"><span data-stu-id="3684f-147">None</span></span>                |<span data-ttu-id="3684f-148">无</span><span class="sxs-lookup"><span data-stu-id="3684f-148">None</span></span>               |<span data-ttu-id="3684f-149">支持的 BYOK</span><span class="sxs-lookup"><span data-stu-id="3684f-149">BYOK supported</span></span>          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a><span data-ttu-id="3684f-150">新的 OME 功能与旧版 OME 的优势</span><span class="sxs-lookup"><span data-stu-id="3684f-150">Advantages of the new OME capabilities over legacy OME</span></span>

<span data-ttu-id="3684f-151">新功能具有以下优点：</span><span class="sxs-lookup"><span data-stu-id="3684f-151">The new capabilities provide the following advantages:</span></span>

- <span data-ttu-id="3684f-152">能够使用仅加密（启用安全协作）、不转发和自定义限制。</span><span class="sxs-lookup"><span data-stu-id="3684f-152">Ability to use Encrypt-Only (which enables secure collaboration), Do Not Forward, and custom restrictions.</span></span>
- <span data-ttu-id="3684f-153">发件人可以使用新功能从 Outlook Desktop、Outlook for Mac 和 web 客户端上的 Outlook 手动发送已加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="3684f-153">Senders can send mail encrypted with the new capabilities manually from Outlook Desktop, Outlook for Mac and Outlook on the web clients.</span></span>
- <span data-ttu-id="3684f-154">Microsoft 365 收件人在受支持的 Outlook 客户端中使用内嵌体验。</span><span class="sxs-lookup"><span data-stu-id="3684f-154">Microsoft 365 recipients get to use an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="3684f-155">此外，管理员还可以选择向 Microsoft 365 收件人显示品牌丰富的体验。</span><span class="sxs-lookup"><span data-stu-id="3684f-155">Alternatively, admins can choose to show Microsoft 365 recipients a branded experience.</span></span>
- <span data-ttu-id="3684f-156">Microsoft 365 之外的帐户（如 Gmail、Yahoo 和 Microsoft 帐户）与 OME 门户联合在一起，从而为这些收件人提供了更好的用户体验。</span><span class="sxs-lookup"><span data-stu-id="3684f-156">Accounts outside of Microsoft 365, such as Gmail, Yahoo, and Microsoft accounts, are federated with the OME portal, which provides a better user experience for these recipients.</span></span> <span data-ttu-id="3684f-157">所有其他标识都使用一次性传递代码来访问加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="3684f-157">All other identities use a one-time pass code to access encrypted messages.</span></span>
- <span data-ttu-id="3684f-158">管理员可以自定义品牌打造和创建多个品牌打造模板。</span><span class="sxs-lookup"><span data-stu-id="3684f-158">Admins can customize branding, and create multiple branding templates.</span></span>
- <span data-ttu-id="3684f-159">管理员可以使用新功能撤消加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3684f-159">Admins can revoke emails encrypted with the new capabilities.</span></span>
- <span data-ttu-id="3684f-160">新功能通过安全&amp;合规性中心提供详细的使用情况报告。</span><span class="sxs-lookup"><span data-stu-id="3684f-160">The new capabilities provide detailed usage reports through the Security &amp; Compliance Center.</span></span>

## <a name="office-365-advanced-message-encryption-capabilities"></a><span data-ttu-id="3684f-161">Office 365 高级邮件加密功能</span><span class="sxs-lookup"><span data-stu-id="3684f-161">Office 365 Advanced Message Encryption capabilities</span></span>

<span data-ttu-id="3684f-162">Office 365 高级邮件加密功能提供了新 OME 功能的其他功能。</span><span class="sxs-lookup"><span data-stu-id="3684f-162">Office 365 Advanced Message Encryption offers additional capabilities on top of the new OME capabilities.</span></span> <span data-ttu-id="3684f-163">您必须在您的组织中设置新的 Office 365 邮件加密功能，才能使用高级邮件加密功能。</span><span class="sxs-lookup"><span data-stu-id="3684f-163">You must have the new Office 365 Message Encryption capabilities set up in your organization in order to use the Advanced Message Encryption capabilities.</span></span> <span data-ttu-id="3684f-164">此外，为了使用这些功能，收件人必须通过 OME 门户查看并回复安全邮件。</span><span class="sxs-lookup"><span data-stu-id="3684f-164">Also, in order to use these capabilities, recipients must view and reply to secure mail through the OME Portal.</span></span> <span data-ttu-id="3684f-165">高级功能包括：</span><span class="sxs-lookup"><span data-stu-id="3684f-165">The advanced capabilities  include:</span></span>

- <span data-ttu-id="3684f-166">邮件吊销</span><span class="sxs-lookup"><span data-stu-id="3684f-166">Message revocation</span></span>

- <span data-ttu-id="3684f-167">邮件过期</span><span class="sxs-lookup"><span data-stu-id="3684f-167">Message expiration</span></span>

- <span data-ttu-id="3684f-168">多品牌模板</span><span class="sxs-lookup"><span data-stu-id="3684f-168">Multiple branding templates</span></span>

<span data-ttu-id="3684f-169">在 GCC High 中不支持对 Office 365 高级邮件加密。</span><span class="sxs-lookup"><span data-stu-id="3684f-169">Office 365 Advanced Message Encryption is not supported in GCC High.</span></span>

<span data-ttu-id="3684f-170">有关使用高级邮件加密的信息，请参阅[Office 365 高级邮件加密](ome-advanced-message-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="3684f-170">For information on using Advanced Message Encryption, see [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md).</span></span>

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a><span data-ttu-id="3684f-171">GCC 高部署中的 Office 365 邮件加密的独特特征</span><span class="sxs-lookup"><span data-stu-id="3684f-171">Unique characteristics of Office 365 Message Encryption in a GCC High deployment</span></span>

<span data-ttu-id="3684f-172">Office 365 高级消息加密在 GCC 高环境中不可用。</span><span class="sxs-lookup"><span data-stu-id="3684f-172">Office 365 Advanced Message Encryption is not available in a GCC High environment.</span></span> <span data-ttu-id="3684f-173">您仍可以在 GCC 高环境中使用和自定义单个品牌模板。</span><span class="sxs-lookup"><span data-stu-id="3684f-173">You can still use and customize a single brand template in a GCC High environment.</span></span>

<span data-ttu-id="3684f-174">此外，如果您计划在 GCC 高环境中使用 Office 365 邮件加密，则有一些关于收件人体验的独特特征。</span><span class="sxs-lookup"><span data-stu-id="3684f-174">In addition, if you plan to use Office 365 Message Encryption in a GCC High environment, there are some unique characteristics about the recipient experience.</span></span>

### <a name="encrypted-email-from-gcc-high-to-gcc-high-recipients"></a><span data-ttu-id="3684f-175">来自 GCC 高到 GCC 的加密电子邮件高收件人</span><span class="sxs-lookup"><span data-stu-id="3684f-175">Encrypted email from GCC High to GCC High recipients</span></span>

<span data-ttu-id="3684f-176">发件人可以在 Outlook 中为电脑和 Mac 和 Outlook 网页版手动加密电子邮件，或者组织可以设置策略以使用 Exchange 邮件流规则对电子邮件进行加密。</span><span class="sxs-lookup"><span data-stu-id="3684f-176">Senders can manually encrypt emails in Outlook for PC and Mac and Outlook on the web, or organizations can set up a policy to encrypt emails using Exchange mail flow rules.</span></span>

<span data-ttu-id="3684f-177">GCC 内的收件人在 Outlook 中对电脑和 Mac 和 Outlook 网页版中的所有其他用户都具有相同的内嵌阅读体验。</span><span class="sxs-lookup"><span data-stu-id="3684f-177">Recipients inside GCC High receive the same inline reading experience in Outlook for PC and Mac and Outlook on the web as all other users.</span></span>

### <a name="encrypted-email-from-gcc-high-to-non-gcc-high-recipients"></a><span data-ttu-id="3684f-178">来自 GCC 高到非 GCC 高收件人的加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="3684f-178">Encrypted email from GCC High to Non-GCC High recipients</span></span>

<span data-ttu-id="3684f-179">GCC High 中的发件人可以在 GCC 的高边界之外发送加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3684f-179">Senders inside GCC High can send encrypted email outside of the GCC High boundary.</span></span>

<span data-ttu-id="3684f-180">所有超过 GCC 的收件人（包括商业 Microsoft 365 用户、Outlook.com 用户和其他电子邮件提供商（如 Gmail 和 Yahoo）的其他用户）都会收到包装邮件。</span><span class="sxs-lookup"><span data-stu-id="3684f-180">All recipients outside GCC High, including commercial Microsoft 365 users, Outlook.com users, and other users of other email providers such as Gmail and Yahoo, receive a wrapper mail.</span></span> <span data-ttu-id="3684f-181">此包装邮件将收件人重定向到 OME 门户，收件人可在其中读取和回复邮件。</span><span class="sxs-lookup"><span data-stu-id="3684f-181">This wrapper mail redirects the recipient to the OME Portal where the recipient can read and reply to message.</span></span>

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a><span data-ttu-id="3684f-182">旧版 OME 的共存和同一租户中的新功能</span><span class="sxs-lookup"><span data-stu-id="3684f-182">Coexistence of legacy OME and the new capabilities in the same tenant</span></span>

<span data-ttu-id="3684f-183">您可以在同一个租户中使用这两个旧的 OME 和新功能。</span><span class="sxs-lookup"><span data-stu-id="3684f-183">You can use both legacy OME and the new capabilities in the same tenant.</span></span> <span data-ttu-id="3684f-184">作为管理员，您可以通过在创建邮件流规则时选择要使用的 OME 版本来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="3684f-184">As an administrator, you do this by choosing which version of OME you want to use when you create your mail flow rules.</span></span>

- <span data-ttu-id="3684f-185">若要指定旧版本的 OME，请使用 Exchange 邮件流规则操作 "**应用以前版本的 OME"**。</span><span class="sxs-lookup"><span data-stu-id="3684f-185">To specify the legacy version of OME, use the Exchange mail flow rule action **Apply the previous version of OME**.</span></span>

- <span data-ttu-id="3684f-186">若要指定新的功能，请使用 Exchange 邮件流规则操作 "**应用 Office 365 邮件加密" 和 "权限保护**"。</span><span class="sxs-lookup"><span data-stu-id="3684f-186">To specify the new capabilities, use the Exchange mail flow rule action **Apply Office 365 Message Encryption and rights protection**.</span></span>

<span data-ttu-id="3684f-187">用户可以使用 Outlook Desktop 中的新功能、Outlook for Mac 和 web 上的 Outlook 手动发送已加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="3684f-187">Users can manually send mail that is encrypted with the new capabilities from Outlook Desktop, Outlook for Mac, and Outlook on the web.</span></span>

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a><span data-ttu-id="3684f-188">从旧 OME 迁移到新功能</span><span class="sxs-lookup"><span data-stu-id="3684f-188">Migrate from legacy OME to the new capabilities</span></span>

<span data-ttu-id="3684f-189">尽管这两个版本的 OME 都可以共存，但我们强烈建议您编辑旧的邮件流规则，这些规则使用规则操作 "**应用以前版本的 OME** " 以使用新功能。</span><span class="sxs-lookup"><span data-stu-id="3684f-189">Even though both versions of OME can coexist, we highly recommend that you edit your old mail flow rules that use the rule action **Apply the previous version of OME** to use the new capabilities.</span></span> <span data-ttu-id="3684f-190">更新这些规则以使用邮件流规则操作 "**应用 Office 365 邮件加密" 和 "权限保护**"。</span><span class="sxs-lookup"><span data-stu-id="3684f-190">Update these rules to use the mail flow rule action **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="3684f-191">有关说明，请参阅[在 Office 365 中定义用于加密电子邮件的邮件流规则](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="3684f-191">For instructions, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

## <a name="get-started-with-ome"></a><span data-ttu-id="3684f-192">开始使用 OME</span><span class="sxs-lookup"><span data-stu-id="3684f-192">Get started with OME</span></span>

<span data-ttu-id="3684f-193">通常情况下，系统会自动为您的组织启用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="3684f-193">Typically, the new OME capabilities are automatically enabled for your organization.</span></span> <span data-ttu-id="3684f-194">有关贵组织内的新 OME 功能的详细信息，请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="3684f-194">For more information about the new OME capabilities within your organization, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span>

<span data-ttu-id="3684f-195">如果已启用 Azure 信息保护，则会自动为你的组织启用旧版本的 OME。</span><span class="sxs-lookup"><span data-stu-id="3684f-195">The legacy version of OME is automatically enabled for your organization if you have enabled Azure Information Protection.</span></span> <span data-ttu-id="3684f-196">以前，即使未启用 Azure 信息保护，旧版 OME 也能正常工作。</span><span class="sxs-lookup"><span data-stu-id="3684f-196">In the past, legacy OME worked even if Azure Information Protection wasn't enabled.</span></span> <span data-ttu-id="3684f-197">但现在不再如此。</span><span class="sxs-lookup"><span data-stu-id="3684f-197">This is no longer the case.</span></span>

<span data-ttu-id="3684f-198">若要开始使用旧版 OME，如果已启用 Azure 信息保护，请配置使用规则操作的邮件流规则 "**应用以前版本的 OME**"。</span><span class="sxs-lookup"><span data-stu-id="3684f-198">To start using legacy OME, if you have enabled Azure Information Protection, configure mail flow rules that use the rule action **Apply the previous version of OME**.</span></span> <span data-ttu-id="3684f-199">有关说明，请参阅[定义邮件流规则以加密电子邮件](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="3684f-199">For instructions, see [Define mail flow rules to encrypt email messages](define-mail-flow-rules-to-encrypt-email.md).</span></span>
