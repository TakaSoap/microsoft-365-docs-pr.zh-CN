---
title: 评估 Microsoft Defender for Office 365
description: 评估Office 365 Defender for Office 365创建 Defender for Office 365 记录裁定（如恶意软件）但不对邮件执行任何操作的电子邮件策略。
keywords: 评估 Office 365， Microsoft Defender for Office 365， office 365 评估， 试用 office 365， Microsoft Defender， Microsoft Defender for Endpoint
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 005c1f6ad7806c8d1ba1d38e4e82edd25034075d
ms.sourcegitcommit: 682ed2c4e2bc6979025cdb89094866cef6c8751a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51942989"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a><span data-ttu-id="f8e63-104">评估 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="f8e63-104">Evaluate Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="f8e63-105">Microsoft Defender for Office 365评估在公共预览版中。</span><span class="sxs-lookup"><span data-stu-id="f8e63-105">Microsoft Defender for Office 365 evaluation is in public preview.</span></span> <span data-ttu-id="f8e63-106">提供此预览版本时没有服务级别协议。</span><span class="sxs-lookup"><span data-stu-id="f8e63-106">This preview version is provided without a service level agreement.</span></span> <span data-ttu-id="f8e63-107">某些功能可能不受支持，或者可能具有受限功能。</span><span class="sxs-lookup"><span data-stu-id="f8e63-107">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="f8e63-108">执行全面的安全产品评估可帮助你做出有关升级和购买的明智决定。</span><span class="sxs-lookup"><span data-stu-id="f8e63-108">Conducting a thorough security product evaluation can help give you informed decisions on upgrades and purchases.</span></span> <span data-ttu-id="f8e63-109">这有助于试用安全产品的功能，以评估它如何有助于安全运营团队完成日常任务。</span><span class="sxs-lookup"><span data-stu-id="f8e63-109">It helps to try out the security product's capabilities to assess how it can help your security operations team in their daily tasks.</span></span>

<span data-ttu-id="f8e63-110">[Microsoft Defender for Office 365](defender-for-office-365.md)评估体验旨在消除设备和环境配置的复杂性，以便你可以专注于评估 Microsoft Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="f8e63-110">The [Microsoft Defender for Office 365](defender-for-office-365.md) evaluation experience is designed to eliminate the complexities of device and environment configuration so that you can focus on evaluating the capabilities of Microsoft Defender for Office 365.</span></span> <span data-ttu-id="f8e63-111">使用评估模式，可以评估发送到Exchange Online的所有邮件，而无需将 MX 记录指向 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="f8e63-111">With evaluation mode, all messages sent to Exchange Online mailboxes can be evaluated without pointing MX records to Microsoft.</span></span> <span data-ttu-id="f8e63-112">此功能仅适用于电子邮件保护，Office Word、SharePoint 或 Teams。</span><span class="sxs-lookup"><span data-stu-id="f8e63-112">The feature only applies to email protection and not to Office Clients like Word, SharePoint, or Teams.</span></span>

<span data-ttu-id="f8e63-113">如果你还没有支持 Microsoft Defender for Office 365 的许可证，你可以启动为期[30](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)天的免费评估，并测试 Office 365 安全&合规中心 (中的功能 https://protection.office.com/homepage) 。</span><span class="sxs-lookup"><span data-stu-id="f8e63-113">If you don't already have a license that supports Microsoft Defender for Office 365, you can start a [free 30-day evaluation](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) and test the capabilities in the Office 365 Security & Compliance center (https://protection.office.com/homepage).</span></span> <span data-ttu-id="f8e63-114">你可以轻松完成快速设置，并在必要时轻松将其关闭。</span><span class="sxs-lookup"><span data-stu-id="f8e63-114">You'll enjoy the quick set-up and you can easily turn it off if necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="f8e63-115">如果你在统一的 Microsoft 365 安全门户 (security.microsoft.com) 可以在此处启动 Defender for Office 365 评估：Email & Collaboration > Policies & Rules > Threat Policies > Additional Policies。</span><span class="sxs-lookup"><span data-stu-id="f8e63-115">If you're in the unified Microsoft 365 security portal (security.microsoft.com) you can start a Defender for Office 365 evaluation here: Email & Collaboration > Policies & Rules > Threat Policies > Additional Policies.</span></span>

## <a name="how-the-evaluation-works"></a><span data-ttu-id="f8e63-116">评估的工作原理</span><span class="sxs-lookup"><span data-stu-id="f8e63-116">How the evaluation works</span></span>

<span data-ttu-id="f8e63-117">评估Office 365 Defender for Office 365创建 Defender for Office 365 记录裁定（如恶意软件）但不对邮件执行任何操作的电子邮件策略。</span><span class="sxs-lookup"><span data-stu-id="f8e63-117">Defender for Office 365 in evaluation mode creates Defender for Office 365 email policies that log verdicts, such as malware, but don't act on messages.</span></span> <span data-ttu-id="f8e63-118">无需更改 MX 记录配置。</span><span class="sxs-lookup"><span data-stu-id="f8e63-118">You are not required to change your MX record configuration.</span></span>

<span data-ttu-id="f8e63-119">使用评估模式 [保险箱，保险箱"](safe-attachments.md)附件"、"链接"和基于邮箱 [](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)智能的模拟策略将代表您设置。 [](safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="f8e63-119">With evaluation mode, [Safe Attachments](safe-attachments.md), [Safe Links](safe-links.md), and [mailbox intelligence based impersonation policies](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) are set up on your behalf.</span></span> <span data-ttu-id="f8e63-120">所有 Defender for Office 365 策略均在后台的非强制模式下创建，并且不可见。</span><span class="sxs-lookup"><span data-stu-id="f8e63-120">All Defender for Office 365 policies are created in non-enforcement mode in the background and are not visible to you.</span></span>

<span data-ttu-id="f8e63-121">作为设置的一部分，评估模式还配置 [连接器的增强筛选](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="f8e63-121">As part of the setup, evaluation mode also configures [Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span> <span data-ttu-id="f8e63-122">它通过保留 IP 地址和发件人信息来提高筛选准确度，否则当邮件通过 Defender for Office 365 前面的电子邮件安全网关 (ESG) 时，这些信息会丢失。</span><span class="sxs-lookup"><span data-stu-id="f8e63-122">It improves filtering accuracy by preserving IP address and sender information, which are otherwise lost when mail passes through an email security gateway (ESG) in front of Defender for Office 365.</span></span> <span data-ttu-id="f8e63-123">增强的连接器筛选功能还可以提高 EOP 策略Exchange Online Protection (EOP) 反垃圾邮件和防钓鱼策略的筛选准确度。</span><span class="sxs-lookup"><span data-stu-id="f8e63-123">Enhanced Filtering for Connectors also improves the filtering accuracy for your existing Exchange Online Protection (EOP) anti-spam and anti-phishing policies.</span></span>

<span data-ttu-id="f8e63-124">为连接器启用的增强筛选可提高筛选准确度，但如果在 Defender for Office 365 前面有 ESG，并且当前未绕过 EOP 筛选，则某些邮件可能会改变可传递性。</span><span class="sxs-lookup"><span data-stu-id="f8e63-124">Enabled Enhanced Filtering for Connectors improves filtering accuracy but may alter deliverability for certain messages if you have an ESG in front of Defender for Office 365, and currently do not bypass EOP filtering.</span></span> <span data-ttu-id="f8e63-125">影响仅限于 EOP 策略;作为评估的一部分的 MDO 策略设置是在非强制模式下创建的。</span><span class="sxs-lookup"><span data-stu-id="f8e63-125">The impact is limited to EOP policies; MDO policies setup as part of the evaluation are created in non-enforcement mode.</span></span> <span data-ttu-id="f8e63-126">为了最大限度地减少潜在的生产影响，您可以通过创建传输规则来绕过所有 EOP 筛选，将"垃圾邮件可信度" (SCL) 设置为 -1。</span><span class="sxs-lookup"><span data-stu-id="f8e63-126">To minimize potential production impact, you can bypass all EOP filtering by creating a transport rule to set the Spam Confidence Level (SCL) to -1.</span></span> <span data-ttu-id="f8e63-127">有关详细信息，请参阅使用 [EAC 创建设置邮件 SCL 的邮件](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)   流规则。</span><span class="sxs-lookup"><span data-stu-id="f8e63-127">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) for details.</span></span>

<span data-ttu-id="f8e63-128">设置评估模式后，你每天将更新一个报告，其中最多包含 90 天的数据，用于量化实施策略时可能阻止的邮件 (例如删除、发送到垃圾邮件、隔离) 。</span><span class="sxs-lookup"><span data-stu-id="f8e63-128">When the evaluation mode is set up, you will have a report updated daily with up to 90 days of data quantifying the messages that would have been blocked if the policies were implemented (for example, delete, send to junk, quarantine).</span></span> <span data-ttu-id="f8e63-129">针对所有 Defender 生成针对 Office 365 和 EOP 检测的报告。</span><span class="sxs-lookup"><span data-stu-id="f8e63-129">Reports are generated for all Defender for Office 365 and EOP detections.</span></span> <span data-ttu-id="f8e63-130">它们根据检测技术聚合 (例如，模拟) 并可以按时间范围进行筛选。</span><span class="sxs-lookup"><span data-stu-id="f8e63-130">They are aggregated per detection technology (for example, impersonation) and can be filtered by time range.</span></span> <span data-ttu-id="f8e63-131">此外，还可以按需创建邮件报告，以创建自定义透视表，或者使用威胁资源管理器深入探究邮件。</span><span class="sxs-lookup"><span data-stu-id="f8e63-131">Additionally, message reports can be created on-demand to create custom pivots or to deep dive messages using Threat Explorer.</span></span>

<span data-ttu-id="f8e63-132">借助简化的设置体验，你可以专注于：</span><span class="sxs-lookup"><span data-stu-id="f8e63-132">With the simplified set-up experience, you can focus on:</span></span>

- <span data-ttu-id="f8e63-133">运行评估</span><span class="sxs-lookup"><span data-stu-id="f8e63-133">Running the evaluation</span></span>
- <span data-ttu-id="f8e63-134">获取详细报告</span><span class="sxs-lookup"><span data-stu-id="f8e63-134">Getting a detailed report</span></span>
- <span data-ttu-id="f8e63-135">分析要操作的报告</span><span class="sxs-lookup"><span data-stu-id="f8e63-135">Analyzing the report for action</span></span>
- <span data-ttu-id="f8e63-136">显示评估结果</span><span class="sxs-lookup"><span data-stu-id="f8e63-136">Presenting the evaluation outcome</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f8e63-137">开始之前</span><span class="sxs-lookup"><span data-stu-id="f8e63-137">Before you begin</span></span>

### <a name="licensing"></a><span data-ttu-id="f8e63-138">授权</span><span class="sxs-lookup"><span data-stu-id="f8e63-138">Licensing</span></span>

<span data-ttu-id="f8e63-139">若要访问评估，你将需要满足许可要求。</span><span class="sxs-lookup"><span data-stu-id="f8e63-139">To access the evaluation, you'll need to meet the licensing requirements.</span></span> <span data-ttu-id="f8e63-140">以下任一许可证都可用：</span><span class="sxs-lookup"><span data-stu-id="f8e63-140">Any of the following licenses will work:</span></span>

- <span data-ttu-id="f8e63-141">Microsoft Defender for Office 365 计划 1</span><span class="sxs-lookup"><span data-stu-id="f8e63-141">Microsoft Defender for Office 365 Plan 1</span></span>
- <span data-ttu-id="f8e63-142">Microsoft Defender for Office 365 计划 2</span><span class="sxs-lookup"><span data-stu-id="f8e63-142">Microsoft Defender for Office 365 Plan 2</span></span>
- <span data-ttu-id="f8e63-143">Microsoft 365 E5、Microsoft 365 E5 安全性</span><span class="sxs-lookup"><span data-stu-id="f8e63-143">Microsoft 365 E5, Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="f8e63-144">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="f8e63-144">Office 365 E5</span></span>

<span data-ttu-id="f8e63-145">如果你没有这些许可证之一，则需要获取试用许可证。</span><span class="sxs-lookup"><span data-stu-id="f8e63-145">If you don't have one of those licenses, then you'll need to obtain a trial license.</span></span>

#### <a name="trial"></a><span data-ttu-id="f8e63-146">试用</span><span class="sxs-lookup"><span data-stu-id="f8e63-146">Trial</span></span>

<span data-ttu-id="f8e63-147">若要获取 Microsoft Defender for Office 365 试用版许可证，你需要具有帐单管理员角色 **或\*\*\*\*全局管理员角色**。</span><span class="sxs-lookup"><span data-stu-id="f8e63-147">To obtain a trial license for Microsoft Defender for Office 365, you need to have the **Billing admin role** or **Global admin role**.</span></span> <span data-ttu-id="f8e63-148">向具有全局管理员角色的人请求权限。</span><span class="sxs-lookup"><span data-stu-id="f8e63-148">Request permission from someone that has the Global admin role.</span></span> [<span data-ttu-id="f8e63-149">了解订阅和许可证</span><span class="sxs-lookup"><span data-stu-id="f8e63-149">Learn about subscriptions and licenses</span></span>](../../commerce/licenses/subscriptions-and-licenses.md)

<span data-ttu-id="f8e63-150">获得适当角色后，建议的路径是，通过进入"帐单""购买服务"，在 Microsoft 365 管理中心获取适用于 Office 365 (计划 2) 的 Microsoft Defender > 试用许可证。</span><span class="sxs-lookup"><span data-stu-id="f8e63-150">Once you have the proper role, the recommended path is to obtain a trial license for Microsoft Defender for Office 365 (Plan 2) in the Microsoft 365 admin center by going to Billing > Purchase services.</span></span> <span data-ttu-id="f8e63-151">试用版包含 25 个许可证的 30 天免费试用版。</span><span class="sxs-lookup"><span data-stu-id="f8e63-151">The trial includes a 30-day free trial for 25 licenses.</span></span> <span data-ttu-id="f8e63-152">[获取 Microsoft Defender for Office 365 (计划 2) ](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)试用版。</span><span class="sxs-lookup"><span data-stu-id="f8e63-152">[Get a trial for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="f8e63-153">你将有一个 30 天窗口，其评估用于监视并报告高级威胁。</span><span class="sxs-lookup"><span data-stu-id="f8e63-153">You'll have a 30-day window with the evaluation to monitor and report on advanced threats.</span></span> <span data-ttu-id="f8e63-154">如果你想要完整的 Defender for Office 365功能，还可以选择购买付费订阅。</span><span class="sxs-lookup"><span data-stu-id="f8e63-154">You'll also have the option to buy a paid subscription if you want the full Defender for Office 365 capabilities.</span></span>

### <a name="roles"></a><span data-ttu-id="f8e63-155">角色</span><span class="sxs-lookup"><span data-stu-id="f8e63-155">Roles</span></span>

<span data-ttu-id="f8e63-156">**Exchange Online评估模式下设置** Defender Office 365需要角色。</span><span class="sxs-lookup"><span data-stu-id="f8e63-156">**Exchange Online roles are required** to set up Defender for Office 365 in evaluation mode.</span></span> <span data-ttu-id="f8e63-157">分配Microsoft 365或安全管理员角色不起作用。</span><span class="sxs-lookup"><span data-stu-id="f8e63-157">Assigning a Microsoft 365 compliance or security admin role won't work.</span></span>

- [<span data-ttu-id="f8e63-158">了解 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f8e63-158">Learn about permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
- [<span data-ttu-id="f8e63-159">了解如何分配管理员角色</span><span class="sxs-lookup"><span data-stu-id="f8e63-159">Learn about assigning admin roles</span></span>](../../admin/add-users/assign-admin-roles.md)

<span data-ttu-id="f8e63-160">需要以下角色：</span><span class="sxs-lookup"><span data-stu-id="f8e63-160">The following roles are needed:</span></span>

|<span data-ttu-id="f8e63-161">任务</span><span class="sxs-lookup"><span data-stu-id="f8e63-161">Task</span></span>|<span data-ttu-id="f8e63-162">角色 (角色Exchange Online) </span><span class="sxs-lookup"><span data-stu-id="f8e63-162">Role (in Exchange Online)</span></span>|
|---|---|
|<span data-ttu-id="f8e63-163">获取免费试用版或购买 Microsoft Defender for Office 365 (计划 2) </span><span class="sxs-lookup"><span data-stu-id="f8e63-163">Get a free trial or buy Microsoft Defender for Office 365 (Plan 2)</span></span>|<span data-ttu-id="f8e63-164">帐单管理员角色或全局管理员角色</span><span class="sxs-lookup"><span data-stu-id="f8e63-164">Billing admin role OR Global admin role</span></span>|
|<span data-ttu-id="f8e63-165">创建评估策略</span><span class="sxs-lookup"><span data-stu-id="f8e63-165">Create evaluation policy</span></span>|<span data-ttu-id="f8e63-166">远程域和接受域角色;安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="f8e63-166">Remote and Accepted Domains role; Security admin role</span></span>|
|<span data-ttu-id="f8e63-167">编辑评估策略</span><span class="sxs-lookup"><span data-stu-id="f8e63-167">Edit evaluation policy</span></span>|<span data-ttu-id="f8e63-168">远程域和接受域角色;安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="f8e63-168">Remote and Accepted Domains role; Security admin role</span></span>|
|<span data-ttu-id="f8e63-169">删除评估策略</span><span class="sxs-lookup"><span data-stu-id="f8e63-169">Delete evaluation policy</span></span>|<span data-ttu-id="f8e63-170">远程域和接受域角色;安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="f8e63-170">Remote and Accepted Domains role; Security admin role</span></span> |
|<span data-ttu-id="f8e63-171">查看评估报告</span><span class="sxs-lookup"><span data-stu-id="f8e63-171">View evaluation report</span></span>|<span data-ttu-id="f8e63-172">安全管理员角色或安全读取者角色</span><span class="sxs-lookup"><span data-stu-id="f8e63-172">Security admin role OR Security reader role</span></span>|
|

### <a name="enhanced-filtering"></a><span data-ttu-id="f8e63-173">增强的筛选</span><span class="sxs-lookup"><span data-stu-id="f8e63-173">Enhanced filtering</span></span>

<span data-ttu-id="f8e63-174">你的Exchange Online Protection策略（如批量和垃圾邮件保护）将保持不变。</span><span class="sxs-lookup"><span data-stu-id="f8e63-174">Your Exchange Online Protection policies, such as bulk and spam protection, will remain the same.</span></span> <span data-ttu-id="f8e63-175">但是，评估会启用对连接器的增强筛选，这可能会影响邮件流Exchange Online Protection策略，除非绕过。</span><span class="sxs-lookup"><span data-stu-id="f8e63-175">However, the evaluation turns on enhanced filtering for connectors, which may impact your mail flow and Exchange Online Protection policies unless bypassed.</span></span>

<span data-ttu-id="f8e63-176">连接器的增强筛选允许租户使用反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="f8e63-176">Enhanced filtering for connectors allows tenants to use anti-spoofing protection.</span></span> <span data-ttu-id="f8e63-177">如果在未打开连接器的增强筛选 (ESG) 电子邮件安全网关，则不支持反欺骗。</span><span class="sxs-lookup"><span data-stu-id="f8e63-177">Anti-spoofing is not supported if you're using an email security gateway (ESG) without having turned on Enhanced filtering for connectors.</span></span>

### <a name="urls"></a><span data-ttu-id="f8e63-178">URL</span><span class="sxs-lookup"><span data-stu-id="f8e63-178">URLs</span></span>

<span data-ttu-id="f8e63-179">URL 将在邮件流期间触发。</span><span class="sxs-lookup"><span data-stu-id="f8e63-179">URLs will be detonated during mail flow.</span></span> <span data-ttu-id="f8e63-180">如果不希望触发特定 URL，请适当地管理允许的 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="f8e63-180">If you don't want specific URLs detonated, manage your list of allowed URLs appropriately.</span></span> <span data-ttu-id="f8e63-181">有关详细信息 [，请参阅管理租户允许/](tenant-allow-block-list.md) 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="f8e63-181">See [Manage the Tenant Allow/Block List](tenant-allow-block-list.md) for details.</span></span>

<span data-ttu-id="f8e63-182">电子邮件正文中的 URL 链接不会换行，以减少客户影响。</span><span class="sxs-lookup"><span data-stu-id="f8e63-182">URL links in the email message bodies won't wrap, to lessen customer impact.</span></span>

### <a name="email-routing"></a><span data-ttu-id="f8e63-183">电子邮件路由</span><span class="sxs-lookup"><span data-stu-id="f8e63-183">Email routing</span></span>

<span data-ttu-id="f8e63-184">准备设置电子邮件当前路由方式所需的相应详细信息，包括路由邮件的入站连接器的名称。</span><span class="sxs-lookup"><span data-stu-id="f8e63-184">Prepare the corresponding details that you will need to set up how your email is currently routed, including the name of the inbound connector that routes your mail.</span></span> <span data-ttu-id="f8e63-185">如果您只是使用 Exchange Online Protection，则没有连接器。 [了解邮件流和电子邮件路由](/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span><span class="sxs-lookup"><span data-stu-id="f8e63-185">If you are just using Exchange Online Protection, you won't have a connector. [Learn about mail flow and email routing](/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span></span>

<span data-ttu-id="f8e63-186">支持的电子邮件路由方案包括：</span><span class="sxs-lookup"><span data-stu-id="f8e63-186">Supported email routing scenarios include:</span></span>

- <span data-ttu-id="f8e63-187">**第三方合作伙伴和/** 或本地服务提供商：要评估的入站连接器使用第三方提供商和/或你正在使用用于本地电子邮件安全的解决方案。</span><span class="sxs-lookup"><span data-stu-id="f8e63-187">**Third-party partner and/or on-premises service provider**: The inbound connector that you want to evaluate uses a third-party provider and/or you're using a solution for email security on-premises.</span></span>
- <span data-ttu-id="f8e63-188">**Microsoft Exchange Online保护**：要评估的租户使用 Office 365 用于电子邮件安全，而 Mail Exchange (MX) 记录指向 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="f8e63-188">**Microsoft Exchange Online Protection only**: The tenant that you want to evaluate uses Office 365 for email security and the Mail Exchange (MX) record points to Microsoft.</span></span>

### <a name="email-security-gateway"></a><span data-ttu-id="f8e63-189">电子邮件安全网关</span><span class="sxs-lookup"><span data-stu-id="f8e63-189">Email security gateway</span></span>

<span data-ttu-id="f8e63-190">如果使用第三方电子邮件安全网关 (ESG) ，则需要知道提供商的名称。</span><span class="sxs-lookup"><span data-stu-id="f8e63-190">If you're using a third-party email security gateway (ESG), you'll need to know the provider's name.</span></span> <span data-ttu-id="f8e63-191">如果你使用的是本地或不支持的 ESG 供应商，你需要知道设备的公用 IP 地址 () 地址。</span><span class="sxs-lookup"><span data-stu-id="f8e63-191">If you're using an ESG on-premises or non-supported vendors, you'll need to know the public IP address(es) for the devices.</span></span>

<span data-ttu-id="f8e63-192">受支持的第三方合作伙伴包括：</span><span class="sxs-lookup"><span data-stu-id="f8e63-192">Supported third-party partners include:</span></span>

- <span data-ttu-id="f8e63-193">Barracuda</span><span class="sxs-lookup"><span data-stu-id="f8e63-193">Barracuda</span></span>
- <span data-ttu-id="f8e63-194">IronPort</span><span class="sxs-lookup"><span data-stu-id="f8e63-194">IronPort</span></span>
- <span data-ttu-id="f8e63-195">Mimecast</span><span class="sxs-lookup"><span data-stu-id="f8e63-195">Mimecast</span></span>
- <span data-ttu-id="f8e63-196">Proofpoint</span><span class="sxs-lookup"><span data-stu-id="f8e63-196">Proofpoint</span></span>
- <span data-ttu-id="f8e63-197">S一os</span><span class="sxs-lookup"><span data-stu-id="f8e63-197">Sophos</span></span>
- <span data-ttu-id="f8e63-198">Symantec</span><span class="sxs-lookup"><span data-stu-id="f8e63-198">Symantec</span></span>
- <span data-ttu-id="f8e63-199">Trend Micro</span><span class="sxs-lookup"><span data-stu-id="f8e63-199">Trend Micro</span></span>

### <a name="scoping"></a><span data-ttu-id="f8e63-200">界定访问权限</span><span class="sxs-lookup"><span data-stu-id="f8e63-200">Scoping</span></span>

<span data-ttu-id="f8e63-201">你将能够将评估范围确定为入站连接器。</span><span class="sxs-lookup"><span data-stu-id="f8e63-201">You will be able to scope the evaluation to an inbound connector.</span></span> <span data-ttu-id="f8e63-202">如果未配置连接器，则评估范围将允许管理员收集租户中任何用户的数据，以评估 Defender Office 365。</span><span class="sxs-lookup"><span data-stu-id="f8e63-202">If there's no connector configured, then the evaluation scope will allow admins to gather data from any user in your tenant to evaluate Defender for Office 365.</span></span>

## <a name="get-started-with-the-evaluation"></a><span data-ttu-id="f8e63-203">评估入门</span><span class="sxs-lookup"><span data-stu-id="f8e63-203">Get started with the evaluation</span></span>

<span data-ttu-id="f8e63-204">从三个访问Office 365安全与合规Office 365中心& Microsoft Defender (https://protection.office.com/homepage) 评估设置卡：</span><span class="sxs-lookup"><span data-stu-id="f8e63-204">Find the Microsoft Defender for Office 365 evaluation set-up card in the Office 365 Security & Compliance center (https://protection.office.com/homepage) from three access points:</span></span>

- <span data-ttu-id="f8e63-205">威胁管理>仪表板</span><span class="sxs-lookup"><span data-stu-id="f8e63-205">Threat management > Dashboard</span></span>
- <span data-ttu-id="f8e63-206">威胁管理>策略</span><span class="sxs-lookup"><span data-stu-id="f8e63-206">Threat management > Policy</span></span>
- <span data-ttu-id="f8e63-207">仪表板>报表</span><span class="sxs-lookup"><span data-stu-id="f8e63-207">Reports > Dashboard</span></span>

## <a name="setting-up-the-evaluation"></a><span data-ttu-id="f8e63-208">设置评估</span><span class="sxs-lookup"><span data-stu-id="f8e63-208">Setting up the evaluation</span></span>

<span data-ttu-id="f8e63-209">启动评估设置流后，您将获得两个路由选项。</span><span class="sxs-lookup"><span data-stu-id="f8e63-209">Once you start the set-up flow for your evaluation, you'll be given two routing options.</span></span> <span data-ttu-id="f8e63-210">根据组织的邮件路由设置和评估需求，您可以选择是使用第三方和/或本地服务提供商，还是仅 Microsoft Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="f8e63-210">Depending on your organization's mail routing setup and evaluation needs, you can select whether you are using a third-party and/or on-premises service provider or only Microsoft Exchange Online.</span></span>

- <span data-ttu-id="f8e63-211">如果你使用的是第三方合作伙伴和/或本地服务提供商，则需要从下拉菜单中选择供应商的名称。</span><span class="sxs-lookup"><span data-stu-id="f8e63-211">If you are using a third-party partner and/or on-premises service provider, you'll need to select the name of the vendor from the drop-down menu.</span></span> <span data-ttu-id="f8e63-212">提供其他与连接器相关的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f8e63-212">Provide the other connector-related details.</span></span>

- <span data-ttu-id="f8e63-213">如果Microsoft Exchange Online MX 记录指向 Microsoft，并且你有一个邮箱，请选择"Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="f8e63-213">Select Microsoft Exchange Online if the MX record points to Microsoft and you have an Exchange Online mailbox.</span></span>

<span data-ttu-id="f8e63-214">查看设置并在必要时编辑它们。</span><span class="sxs-lookup"><span data-stu-id="f8e63-214">Review your settings and edit them if necessary.</span></span> <span data-ttu-id="f8e63-215">然后，选择创建 **评估**。</span><span class="sxs-lookup"><span data-stu-id="f8e63-215">Then, select **Create evaluation**.</span></span> <span data-ttu-id="f8e63-216">应该会收到一条确认消息，指示设置已完成。</span><span class="sxs-lookup"><span data-stu-id="f8e63-216">You should get a confirmation message to indicate that your set-up is complete.</span></span>

<span data-ttu-id="f8e63-217">你的 Microsoft Defender for Office 365评估报告每天生成一次。</span><span class="sxs-lookup"><span data-stu-id="f8e63-217">Your Microsoft Defender for Office 365 evaluation report is generated once per day.</span></span> <span data-ttu-id="f8e63-218">可能需要 24 小时才能填充数据。</span><span class="sxs-lookup"><span data-stu-id="f8e63-218">It may take up to 24 hours for the data to populate.</span></span>

### <a name="exchange-rules-optional"></a><span data-ttu-id="f8e63-219">Exchange规则 (可选) </span><span class="sxs-lookup"><span data-stu-id="f8e63-219">Exchange rules (optional)</span></span>

<span data-ttu-id="f8e63-220">如果您已有网关，启用评估模式将激活连接器的增强筛选。</span><span class="sxs-lookup"><span data-stu-id="f8e63-220">If you have an existing gateway, enabling evaluation mode will activate enhanced filtering for connectors.</span></span> <span data-ttu-id="f8e63-221">这将通过更改传入发件人 IP 地址提高筛选准确度。</span><span class="sxs-lookup"><span data-stu-id="f8e63-221">This improves filtering accuracy by altering the incoming sender IP address.</span></span> <span data-ttu-id="f8e63-222">这可能会更改筛选裁定，如果不绕过筛选Exchange Online Protection可能会改变某些邮件的可传递性。</span><span class="sxs-lookup"><span data-stu-id="f8e63-222">This may change the filter verdicts and if you are not bypassing Exchange Online Protection this may alter deliverability for certain messages.</span></span> <span data-ttu-id="f8e63-223">在这种情况下，您可能需要暂时绕过筛选来分析影响。</span><span class="sxs-lookup"><span data-stu-id="f8e63-223">In this case you might want to temporarily bypass filtering to analyze impact.</span></span> <span data-ttu-id="f8e63-224">若要绕过，请导航到 Exchange 管理中心，并创建 SCL -1 策略 (如果你还没有 SCL -1) 。</span><span class="sxs-lookup"><span data-stu-id="f8e63-224">To bypass, navigate to the Exchange admin center and create a policy of SCL -1 (if you don't already have one).</span></span> <span data-ttu-id="f8e63-225">有关规则组件及其工作方式的详细信息，请参阅 mail flow rules (transport rules) in Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="f8e63-225">For details on the rule components and how they work, see Mail flow rules (transport rules) in Exchange Online.</span></span>

## <a name="evaluate-capabilities"></a><span data-ttu-id="f8e63-226">评估功能</span><span class="sxs-lookup"><span data-stu-id="f8e63-226">Evaluate capabilities</span></span>

<span data-ttu-id="f8e63-227">生成评估报告后，查看组织中电子邮件和协作工作区中标识了多少高级威胁链接、高级威胁附件和潜在模拟。</span><span class="sxs-lookup"><span data-stu-id="f8e63-227">After the evaluation report has been generated, see how many advanced threat links, advanced threat attachments, and potential impersonations were identified in the emails and collaboration workspaces in your organization.</span></span>

<span data-ttu-id="f8e63-228">试用版过期后，可以在 90 天内继续访问报告。</span><span class="sxs-lookup"><span data-stu-id="f8e63-228">Once the trial has expired, you can continue to access the report for 90 days.</span></span> <span data-ttu-id="f8e63-229">但是，它不会收集更多信息。</span><span class="sxs-lookup"><span data-stu-id="f8e63-229">However, it won't collect any more information.</span></span> <span data-ttu-id="f8e63-230">如果你希望在你的试用版过期后继续使用 Microsoft Defender for Office 365，请确保你购买了[Microsoft Defender for Office 365 (计划 2](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)的付费) 。</span><span class="sxs-lookup"><span data-stu-id="f8e63-230">If you want to continue using Microsoft Defender for Office 365 after your trial has expired, make sure you [buy a paid subscription for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="f8e63-231">你可以 **转到设置更新** 路由或随时关闭评估。</span><span class="sxs-lookup"><span data-stu-id="f8e63-231">You can go to **Settings** to update your routing or turn off your evaluation at any time.</span></span> <span data-ttu-id="f8e63-232">但是，如果你决定在关闭评估后继续评估，则需要再次完成相同的设置过程。</span><span class="sxs-lookup"><span data-stu-id="f8e63-232">However, you need to go through the same set-up process again should you decide to continue your evaluation after having turned it off.</span></span>

## <a name="provide-feedback"></a><span data-ttu-id="f8e63-233">提供反馈</span><span class="sxs-lookup"><span data-stu-id="f8e63-233">Provide feedback</span></span>

<span data-ttu-id="f8e63-234">你的反馈可帮助我们更好地保护你的环境免受高级攻击。</span><span class="sxs-lookup"><span data-stu-id="f8e63-234">Your feedback helps us get better at protecting your environment from advanced attacks.</span></span> <span data-ttu-id="f8e63-235">分享产品功能和评估结果的体验和印象。</span><span class="sxs-lookup"><span data-stu-id="f8e63-235">Share your experience and impressions of product capabilities and evaluation results.</span></span>

<span data-ttu-id="f8e63-236">选择 **"提供** 反馈"，告诉我们您的想法。</span><span class="sxs-lookup"><span data-stu-id="f8e63-236">Select **Give feedback** to let us know what you think.</span></span>