---
title: 评估 Microsoft Defender for Office 365
description: 评估模式下的 Defender for Office 365 创建 Defender for Office 365 电子邮件策略，用于记录裁定（如恶意软件）但不对邮件执行任何操作。
keywords: 评估 Office 365， Microsoft Defender for Office 365， office 365 评估， 试用 office 365， Microsoft Defender， Microsoft Defender for Endpoint
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
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
ms.openlocfilehash: 86433ef505cd1b9afca100dc731f1885e22c8401
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935133"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a><span data-ttu-id="7127a-104">评估 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="7127a-104">Evaluate Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="7127a-105">Microsoft Defender for Office 365 评估在公共预览版中。</span><span class="sxs-lookup"><span data-stu-id="7127a-105">Microsoft Defender for Office 365 evaluation is in public preview.</span></span> <span data-ttu-id="7127a-106">提供此预览版本时没有服务级别协议。</span><span class="sxs-lookup"><span data-stu-id="7127a-106">This preview version is provided without a service level agreement.</span></span> <span data-ttu-id="7127a-107">某些功能可能不受支持，或者可能具有受限功能。</span><span class="sxs-lookup"><span data-stu-id="7127a-107">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="7127a-108">执行全面的安全产品评估可帮助你做出有关升级和购买的明智决定。</span><span class="sxs-lookup"><span data-stu-id="7127a-108">Conducting a comprehensive security product evaluation can help give you informed decisions on upgrades and purchases.</span></span> <span data-ttu-id="7127a-109">这有助于试用安全产品的功能，以评估它如何有助于安全运营团队完成日常任务。</span><span class="sxs-lookup"><span data-stu-id="7127a-109">It helps to try out the security product's capabilities to assess how it can help your security operations team in their daily tasks.</span></span>

<span data-ttu-id="7127a-110">[Microsoft Defender for Office 365](defender-for-office-365.md)评估体验旨在消除设备和环境配置的复杂性，以便你可以专注于评估 Microsoft Defender for Office 365 的功能。</span><span class="sxs-lookup"><span data-stu-id="7127a-110">The [Microsoft Defender for Office 365](defender-for-office-365.md) evaluation experience is designed to eliminate the complexities of device and environment configuration so that you can focus on evaluating the capabilities of Microsoft Defender for Office 365.</span></span> <span data-ttu-id="7127a-111">使用评估模式，可以评估发送到 Exchange Online 邮箱的所有邮件，而无需将 MX 记录指向 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="7127a-111">With evaluation mode, all messages sent to Exchange Online mailboxes can be evaluated without pointing MX records to Microsoft.</span></span> <span data-ttu-id="7127a-112">此功能仅适用于电子邮件保护，而仅适用于 Word、SharePoint 或 Teams 等 Office 客户端。</span><span class="sxs-lookup"><span data-stu-id="7127a-112">The feature only applies to email protection and not to Office Clients like Word, SharePoint, or Teams.</span></span>

<span data-ttu-id="7127a-113">如果还没有支持 Microsoft Defender for Office 365 的许可证，可以启动为期[30](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)天的免费评估，并测试 Office 36 & 5 安全与合规中心 (中的功能。 https://protection.office.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="7127a-113">If you don't already have a license that supports Microsoft Defender for Office 365, you can start a [free 30-day evaluation](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) and test the capabilities in the Office 365 Security & Compliance center (https://protection.office.com/homepage).</span></span> <span data-ttu-id="7127a-114">你可以轻松完成快速设置，并在必要时轻松将其关闭。</span><span class="sxs-lookup"><span data-stu-id="7127a-114">You'll enjoy the quick set-up and you can easily turn it off if necessary.</span></span>

## <a name="how-the-evaluation-works"></a><span data-ttu-id="7127a-115">评估的工作原理</span><span class="sxs-lookup"><span data-stu-id="7127a-115">How the evaluation works</span></span>

<span data-ttu-id="7127a-116">评估模式下的 Defender for Office 365 创建 Defender for Office 365 电子邮件策略，用于记录裁定（如恶意软件）但不对邮件执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="7127a-116">Defender for Office 365 in evaluation mode creates Defender for Office 365 email policies that log verdicts, such as malware, but don't act on messages.</span></span> <span data-ttu-id="7127a-117">无需更改 MX 记录配置。</span><span class="sxs-lookup"><span data-stu-id="7127a-117">You are not required to change your MX record configuration.</span></span>

<span data-ttu-id="7127a-118">使用评估 [模式，](safe-attachments.md) [将](safe-links.md)代表您设置安全附件、 [](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)安全链接和基于邮箱智能的模拟策略。</span><span class="sxs-lookup"><span data-stu-id="7127a-118">With evaluation mode, [Safe Attachments](safe-attachments.md), [Safe Links](safe-links.md), and [mailbox intelligence based impersonation policies](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) are set up on your behalf.</span></span> <span data-ttu-id="7127a-119">所有 Defender for Office 365 策略均在后台的非强制模式下创建，并且对不可见。</span><span class="sxs-lookup"><span data-stu-id="7127a-119">All Defender for Office 365 policies are created in non-enforcement mode in the background and are not visible to you.</span></span>

<span data-ttu-id="7127a-120">作为设置的一部分，评估模式还配置 [连接器的增强筛选](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="7127a-120">As part of the setup, evaluation mode also configures [Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span> <span data-ttu-id="7127a-121">它通过保留 IP 地址和发件人信息来提高筛选准确度，否则当邮件通过 Office 365 Defender 前面的电子邮件安全网关 (ESG) 时，这些信息会丢失。</span><span class="sxs-lookup"><span data-stu-id="7127a-121">It improves filtering accuracy by preserving IP address and sender information, which are otherwise lost when mail passes through an email security gateway (ESG) in front of Defender for Office 365.</span></span> <span data-ttu-id="7127a-122">增强的连接器筛选功能还提高了 EOP 中的现有 Exchange Online Protection () 反垃圾邮件和防钓鱼策略的筛选准确度。</span><span class="sxs-lookup"><span data-stu-id="7127a-122">Enhanced Filtering for Connectors also improves the filtering accuracy for your existing Exchange Online Protection (EOP) anti-spam and anti-phishing policies.</span></span>

<span data-ttu-id="7127a-123">对连接器启用的增强筛选可提高筛选准确度，但如果在 Defender for Office 365 前面有 ESG，并且当前未绕过 EOP 筛选，则某些邮件可能会改变可传递性。</span><span class="sxs-lookup"><span data-stu-id="7127a-123">Enabled Enhanced Filtering for Connectors improves filtering accuracy but may alter deliverability for certain messages if you have an ESG in front of Defender for Office 365, and currently do not bypass EOP filtering.</span></span> <span data-ttu-id="7127a-124">影响仅限于 EOP 策略;作为评估的一部分的 MDO 策略设置是在非强制模式下创建的。</span><span class="sxs-lookup"><span data-stu-id="7127a-124">The impact is limited to EOP policies; MDO policies setup as part of the evaluation are created in non-enforcement mode.</span></span> <span data-ttu-id="7127a-125">为了最大限度地减少潜在的生产影响，您可以通过创建传输规则来绕过所有 EOP 筛选，将"垃圾邮件可信度" (SCL) 设置为 -1。</span><span class="sxs-lookup"><span data-stu-id="7127a-125">To minimize potential production impact, you can bypass all EOP filtering by creating a transport rule to set the Spam Confidence Level (SCL) to -1.</span></span> <span data-ttu-id="7127a-126">有关详细信息，请参阅使用 [EAC 创建设置邮件 SCL 的邮件](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)   流规则。</span><span class="sxs-lookup"><span data-stu-id="7127a-126">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) for details.</span></span>

<span data-ttu-id="7127a-127">设置评估模式后，你每天将更新一个报告，其中最多包含 90 天的数据，用于量化实施策略时可能阻止的邮件 (例如删除、发送到垃圾邮件、隔离) 。</span><span class="sxs-lookup"><span data-stu-id="7127a-127">When the evaluation mode is set up, you will have a report updated daily with up to 90 days of data quantifying the messages that would have been blocked if the policies were implemented (for example, delete, send to junk, quarantine).</span></span> <span data-ttu-id="7127a-128">针对所有 Defender for Office 365 和 EOP 检测生成报告。</span><span class="sxs-lookup"><span data-stu-id="7127a-128">Reports are generated for all Defender for Office 365 and EOP detections.</span></span> <span data-ttu-id="7127a-129">它们根据检测技术聚合 (例如，模拟) 并可以按时间范围进行筛选。</span><span class="sxs-lookup"><span data-stu-id="7127a-129">They are aggregated per detection technology (for example, impersonation) and can be filtered by time range.</span></span> <span data-ttu-id="7127a-130">此外，还可以按需创建邮件报告，以创建自定义透视表，或者使用威胁资源管理器深入探究邮件。</span><span class="sxs-lookup"><span data-stu-id="7127a-130">Additionally, message reports can be created on-demand to create custom pivots or to deep dive messages using Threat Explorer.</span></span>

<span data-ttu-id="7127a-131">借助简化的设置体验，你可以专注于：</span><span class="sxs-lookup"><span data-stu-id="7127a-131">With the simplified set-up experience, you can focus on:</span></span>

- <span data-ttu-id="7127a-132">运行评估</span><span class="sxs-lookup"><span data-stu-id="7127a-132">Running the evaluation</span></span>
- <span data-ttu-id="7127a-133">获取详细报告</span><span class="sxs-lookup"><span data-stu-id="7127a-133">Getting a detailed report</span></span>
- <span data-ttu-id="7127a-134">分析要操作的报告</span><span class="sxs-lookup"><span data-stu-id="7127a-134">Analyzing the report for action</span></span>
- <span data-ttu-id="7127a-135">显示评估结果</span><span class="sxs-lookup"><span data-stu-id="7127a-135">Presenting the evaluation outcome</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7127a-136">准备工作</span><span class="sxs-lookup"><span data-stu-id="7127a-136">Before you begin</span></span>

### <a name="licensing"></a><span data-ttu-id="7127a-137">授权</span><span class="sxs-lookup"><span data-stu-id="7127a-137">Licensing</span></span>

<span data-ttu-id="7127a-138">若要访问评估，你将需要满足许可要求。</span><span class="sxs-lookup"><span data-stu-id="7127a-138">To access the evaluation, you'll need to meet the licensing requirements.</span></span> <span data-ttu-id="7127a-139">以下任一许可证都可用：</span><span class="sxs-lookup"><span data-stu-id="7127a-139">Any of the following licenses will work:</span></span>

- <span data-ttu-id="7127a-140">Microsoft Defender for Office 365 计划 1</span><span class="sxs-lookup"><span data-stu-id="7127a-140">Microsoft Defender for Office 365 Plan 1</span></span>
- <span data-ttu-id="7127a-141">Microsoft Defender for Office 365 计划 2</span><span class="sxs-lookup"><span data-stu-id="7127a-141">Microsoft Defender for Office 365 Plan 2</span></span>
- <span data-ttu-id="7127a-142">Microsoft 365 E5、Microsoft 365 E5 安全</span><span class="sxs-lookup"><span data-stu-id="7127a-142">Microsoft 365 E5, Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="7127a-143">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="7127a-143">Office 365 E5</span></span>

<span data-ttu-id="7127a-144">如果你没有这些许可证之一，则需要获取试用许可证。</span><span class="sxs-lookup"><span data-stu-id="7127a-144">If you don't have one of those licenses, then you'll need to obtain a trial license.</span></span>

#### <a name="trial"></a><span data-ttu-id="7127a-145">试用</span><span class="sxs-lookup"><span data-stu-id="7127a-145">Trial</span></span>

<span data-ttu-id="7127a-146">若要获取适用于 Office 365 的 Microsoft Defender 的试用许可证，你需要具有帐单管理员 **角色或\*\*\*\*全局管理员角色**。</span><span class="sxs-lookup"><span data-stu-id="7127a-146">To obtain a trial license for Microsoft Defender for Office 365, you need to have the **Billing admin role** or **Global admin role**.</span></span> <span data-ttu-id="7127a-147">向具有全局管理员角色的人请求权限。</span><span class="sxs-lookup"><span data-stu-id="7127a-147">Request permission from someone that has the Global admin role.</span></span> [<span data-ttu-id="7127a-148">了解订阅和许可证</span><span class="sxs-lookup"><span data-stu-id="7127a-148">Learn about subscriptions and licenses</span></span>](../../commerce/licenses/subscriptions-and-licenses.md)

<span data-ttu-id="7127a-149">获得适当角色后，建议的路径是，通过进入"帐单"> 购买服务，在 Microsoft 365 管理中心获取适用于 Office 365 (计划 2) 的 Microsoft Defender 试用许可证。</span><span class="sxs-lookup"><span data-stu-id="7127a-149">Once you have the proper role, the recommended path is to obtain a trial license for Microsoft Defender for Office 365 (Plan 2) in the Microsoft 365 admin center by going to Billing > Purchase services.</span></span> <span data-ttu-id="7127a-150">试用版包含 25 个许可证的 30 天免费试用版。</span><span class="sxs-lookup"><span data-stu-id="7127a-150">The trial includes a 30-day free trial for 25 licenses.</span></span> <span data-ttu-id="7127a-151">[获取 Microsoft Defender for Office 365 (计划 2 ](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)) 。</span><span class="sxs-lookup"><span data-stu-id="7127a-151">[Get a trial for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="7127a-152">你将有一个 30 天窗口，其评估用于监视并报告高级威胁。</span><span class="sxs-lookup"><span data-stu-id="7127a-152">You'll have a 30-day window with the evaluation to monitor and report on advanced threats.</span></span> <span data-ttu-id="7127a-153">如果需要完整的 Defender for Office 365 功能，还可以选择购买付费订阅。</span><span class="sxs-lookup"><span data-stu-id="7127a-153">You'll also have the option to buy a paid subscription if you want the full Defender for Office 365 capabilities.</span></span>

### <a name="roles"></a><span data-ttu-id="7127a-154">角色</span><span class="sxs-lookup"><span data-stu-id="7127a-154">Roles</span></span>

<span data-ttu-id="7127a-155">**在评估模式下设置** Defender for Office 365 需要 Exchange Online 角色。</span><span class="sxs-lookup"><span data-stu-id="7127a-155">**Exchange Online roles are required** to set up Defender for Office 365 in evaluation mode.</span></span> <span data-ttu-id="7127a-156">分配 Microsoft 365 合规性或安全管理员角色不起作用。</span><span class="sxs-lookup"><span data-stu-id="7127a-156">Assigning a Microsoft 365 compliance or security admin role won't work.</span></span>

- [<span data-ttu-id="7127a-157">了解 Exchange Online 中的权限</span><span class="sxs-lookup"><span data-stu-id="7127a-157">Learn about permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
- [<span data-ttu-id="7127a-158">了解如何分配管理员角色</span><span class="sxs-lookup"><span data-stu-id="7127a-158">Learn about assigning admin roles</span></span>](../../admin/add-users/assign-admin-roles.md)

<span data-ttu-id="7127a-159">需要以下角色：</span><span class="sxs-lookup"><span data-stu-id="7127a-159">The following roles are needed:</span></span>

|<span data-ttu-id="7127a-160">任务</span><span class="sxs-lookup"><span data-stu-id="7127a-160">Task</span></span>|<span data-ttu-id="7127a-161">Exchange Online (中的角色) </span><span class="sxs-lookup"><span data-stu-id="7127a-161">Role (in Exchange Online)</span></span>|
|---|---|
|<span data-ttu-id="7127a-162">获取免费试用版或购买 Microsoft Defender for Office 365 (计划 2) </span><span class="sxs-lookup"><span data-stu-id="7127a-162">Get a free trial or buy Microsoft Defender for Office 365 (Plan 2)</span></span>|<span data-ttu-id="7127a-163">帐单管理员角色或全局管理员角色</span><span class="sxs-lookup"><span data-stu-id="7127a-163">Billing admin role OR Global admin role</span></span>|
|<span data-ttu-id="7127a-164">创建评估策略</span><span class="sxs-lookup"><span data-stu-id="7127a-164">Create evaluation policy</span></span>|<span data-ttu-id="7127a-165">远程域和接受域角色;安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="7127a-165">Remote and Accepted Domains role; Security admin role</span></span>|
|<span data-ttu-id="7127a-166">编辑评估策略</span><span class="sxs-lookup"><span data-stu-id="7127a-166">Edit evaluation policy</span></span>|<span data-ttu-id="7127a-167">远程域和接受域角色;安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="7127a-167">Remote and Accepted Domains role; Security admin role</span></span>|
|<span data-ttu-id="7127a-168">删除评估策略</span><span class="sxs-lookup"><span data-stu-id="7127a-168">Delete evaluation policy</span></span>|<span data-ttu-id="7127a-169">远程域和接受域角色;安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="7127a-169">Remote and Accepted Domains role; Security admin role</span></span> |
|<span data-ttu-id="7127a-170">查看评估报告</span><span class="sxs-lookup"><span data-stu-id="7127a-170">View evaluation report</span></span>|<span data-ttu-id="7127a-171">安全管理员角色或安全读取者角色</span><span class="sxs-lookup"><span data-stu-id="7127a-171">Security admin role OR Security reader role</span></span>|
|

### <a name="enhanced-filtering"></a><span data-ttu-id="7127a-172">增强的筛选</span><span class="sxs-lookup"><span data-stu-id="7127a-172">Enhanced filtering</span></span>

<span data-ttu-id="7127a-173">Exchange Online Protection 策略（如批量和垃圾邮件保护）将保持不变。</span><span class="sxs-lookup"><span data-stu-id="7127a-173">Your Exchange Online Protection policies, such as bulk and spam protection, will remain the same.</span></span> <span data-ttu-id="7127a-174">但是，评估将对连接器启用增强的筛选功能，这可能会影响邮件流和 Exchange Online Protection 策略，除非绕过。</span><span class="sxs-lookup"><span data-stu-id="7127a-174">However, the evaluation turns on enhanced filtering for connectors, which may impact your mail flow and Exchange Online Protection policies unless bypassed.</span></span>

<span data-ttu-id="7127a-175">连接器的增强筛选允许租户使用反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="7127a-175">Enhanced filtering for connectors allows tenants to use anti-spoofing protection.</span></span> <span data-ttu-id="7127a-176">如果在未打开连接器的增强筛选 (ESG) 电子邮件安全网关，则不支持反欺骗。</span><span class="sxs-lookup"><span data-stu-id="7127a-176">Anti-spoofing is not supported if you're using an email security gateway (ESG) without having turned on Enhanced filtering for connectors.</span></span>

### <a name="urls"></a><span data-ttu-id="7127a-177">URL</span><span class="sxs-lookup"><span data-stu-id="7127a-177">URLs</span></span>

<span data-ttu-id="7127a-178">URL 将在邮件流期间触发。</span><span class="sxs-lookup"><span data-stu-id="7127a-178">URLs will be detonated during mail flow.</span></span> <span data-ttu-id="7127a-179">如果不希望触发特定 URL，请适当地管理允许的 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="7127a-179">If you don't want specific URLs detonated, manage your list of allowed URLs appropriately.</span></span> <span data-ttu-id="7127a-180">有关详细信息 [，请参阅管理租户允许/](tenant-allow-block-list.md) 阻止列表。</span><span class="sxs-lookup"><span data-stu-id="7127a-180">See [Manage the Tenant Allow/Block List](tenant-allow-block-list.md) for details.</span></span>

<span data-ttu-id="7127a-181">电子邮件正文中的 URL 链接不会换行，以减少客户影响。</span><span class="sxs-lookup"><span data-stu-id="7127a-181">URL links in the email message bodies won't wrap, to lessen customer impact.</span></span>

### <a name="email-routing"></a><span data-ttu-id="7127a-182">电子邮件路由</span><span class="sxs-lookup"><span data-stu-id="7127a-182">Email routing</span></span>

<span data-ttu-id="7127a-183">准备设置电子邮件当前路由方式所需的相应详细信息，包括路由邮件的入站连接器的名称。</span><span class="sxs-lookup"><span data-stu-id="7127a-183">Prepare the corresponding details that you will need to set up how your email is currently routed, including the name of the inbound connector that routes your mail.</span></span> <span data-ttu-id="7127a-184">如果您只是使用 Exchange Online Protection，则没有连接器。 [了解邮件流和电子邮件路由](/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span><span class="sxs-lookup"><span data-stu-id="7127a-184">If you are just using Exchange Online Protection, you won't have a connector. [Learn about mail flow and email routing](/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span></span>

<span data-ttu-id="7127a-185">支持的电子邮件路由方案包括：</span><span class="sxs-lookup"><span data-stu-id="7127a-185">Supported email routing scenarios include:</span></span>

- <span data-ttu-id="7127a-186">**第三方合作伙伴和/** 或本地服务提供商：要评估的入站连接器使用第三方提供商和/或你正在使用用于本地电子邮件安全的解决方案。</span><span class="sxs-lookup"><span data-stu-id="7127a-186">**Third-party partner and/or on-premises service provider**: The inbound connector that you want to evaluate uses a third-party provider and/or you're using a solution for email security on-premises.</span></span>
- <span data-ttu-id="7127a-187">**Microsoft Exchange Online保护**：要评估的租户使用 Office 365 进行电子邮件安全保护，而邮件 Exchange (MX) 记录指向 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="7127a-187">**Microsoft Exchange Online Protection only**: The tenant that you want to evaluate uses Office 365 for email security and the Mail Exchange (MX) record points to Microsoft.</span></span>

### <a name="email-security-gateway"></a><span data-ttu-id="7127a-188">电子邮件安全网关</span><span class="sxs-lookup"><span data-stu-id="7127a-188">Email security gateway</span></span>

<span data-ttu-id="7127a-189">如果使用第三方电子邮件安全网关 (ESG) ，则需要知道提供商的名称。</span><span class="sxs-lookup"><span data-stu-id="7127a-189">If you're using a third-party email security gateway (ESG), you'll need to know the provider's name.</span></span> <span data-ttu-id="7127a-190">如果你使用的是本地或不支持的 ESG 供应商，你需要知道设备的公用 IP 地址 () 地址。</span><span class="sxs-lookup"><span data-stu-id="7127a-190">If you're using an ESG on-premises or non-supported vendors, you'll need to know the public IP address(es) for the devices.</span></span>

<span data-ttu-id="7127a-191">受支持的第三方合作伙伴包括：</span><span class="sxs-lookup"><span data-stu-id="7127a-191">Supported third-party partners include:</span></span>

- <span data-ttu-id="7127a-192">Barracuda</span><span class="sxs-lookup"><span data-stu-id="7127a-192">Barracuda</span></span>
- <span data-ttu-id="7127a-193">IronPort</span><span class="sxs-lookup"><span data-stu-id="7127a-193">IronPort</span></span>
- <span data-ttu-id="7127a-194">Mimecast</span><span class="sxs-lookup"><span data-stu-id="7127a-194">Mimecast</span></span>
- <span data-ttu-id="7127a-195">Proofpoint</span><span class="sxs-lookup"><span data-stu-id="7127a-195">Proofpoint</span></span>
- <span data-ttu-id="7127a-196">S一os</span><span class="sxs-lookup"><span data-stu-id="7127a-196">Sophos</span></span>
- <span data-ttu-id="7127a-197">Symantec</span><span class="sxs-lookup"><span data-stu-id="7127a-197">Symantec</span></span>
- <span data-ttu-id="7127a-198">Trend Micro</span><span class="sxs-lookup"><span data-stu-id="7127a-198">Trend Micro</span></span>

### <a name="scoping"></a><span data-ttu-id="7127a-199">界定访问权限</span><span class="sxs-lookup"><span data-stu-id="7127a-199">Scoping</span></span>

<span data-ttu-id="7127a-200">你将能够将评估范围确定为入站连接器。</span><span class="sxs-lookup"><span data-stu-id="7127a-200">You will be able to scope the evaluation to an inbound connector.</span></span> <span data-ttu-id="7127a-201">如果未配置连接器，则评估范围将允许管理员收集租户中任何用户的数据，以评估 Office 365 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="7127a-201">If there's no connector configured, then the evaluation scope will allow admins to gather data from any user in your tenant to evaluate Defender for Office 365.</span></span>

## <a name="get-started-with-the-evaluation"></a><span data-ttu-id="7127a-202">评估入门</span><span class="sxs-lookup"><span data-stu-id="7127a-202">Get started with the evaluation</span></span>

<span data-ttu-id="7127a-203">在 Office 365 安全与合规中心内从三个访问点& Microsoft Defender for Office 365 (https://protection.office.com/homepage) 设置卡：</span><span class="sxs-lookup"><span data-stu-id="7127a-203">Find the Microsoft Defender for Office 365 evaluation set-up card in the Office 365 Security & Compliance center (https://protection.office.com/homepage) from three access points:</span></span>

- <span data-ttu-id="7127a-204">威胁管理>仪表板</span><span class="sxs-lookup"><span data-stu-id="7127a-204">Threat management > Dashboard</span></span>
- <span data-ttu-id="7127a-205">威胁管理>策略</span><span class="sxs-lookup"><span data-stu-id="7127a-205">Threat management > Policy</span></span>
- <span data-ttu-id="7127a-206">仪表板>报表</span><span class="sxs-lookup"><span data-stu-id="7127a-206">Reports > Dashboard</span></span>

## <a name="setting-up-the-evaluation"></a><span data-ttu-id="7127a-207">设置评估</span><span class="sxs-lookup"><span data-stu-id="7127a-207">Setting up the evaluation</span></span>

<span data-ttu-id="7127a-208">启动评估设置流后，您将获得两个路由选项。</span><span class="sxs-lookup"><span data-stu-id="7127a-208">Once you start the set-up flow for your evaluation, you'll be given two routing options.</span></span> <span data-ttu-id="7127a-209">根据组织的邮件路由设置和评估需求，您可以选择是使用第三方和/或本地服务提供商，还是仅 Microsoft Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="7127a-209">Depending on your organization's mail routing setup and evaluation needs, you can select whether you are using a third-party and/or on-premises service provider or only Microsoft Exchange Online.</span></span>

- <span data-ttu-id="7127a-210">如果你使用的是第三方合作伙伴和/或本地服务提供商，则需要从下拉菜单中选择供应商的名称。</span><span class="sxs-lookup"><span data-stu-id="7127a-210">If you are using a third-party partner and/or on-premises service provider, you'll need to select the name of the vendor from the drop-down menu.</span></span> <span data-ttu-id="7127a-211">提供其他与连接器相关的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7127a-211">Provide the other connector-related details.</span></span>

- <span data-ttu-id="7127a-212">Select Microsoft Exchange Online if the MX record points to Microsoft and you have an Exchange Online mailbox.</span><span class="sxs-lookup"><span data-stu-id="7127a-212">Select Microsoft Exchange Online if the MX record points to Microsoft and you have an Exchange Online mailbox.</span></span>

<span data-ttu-id="7127a-213">查看设置并在必要时编辑它们。</span><span class="sxs-lookup"><span data-stu-id="7127a-213">Review your settings and edit them if necessary.</span></span> <span data-ttu-id="7127a-214">然后，选择创建 **评估**。</span><span class="sxs-lookup"><span data-stu-id="7127a-214">Then, select **Create evaluation**.</span></span> <span data-ttu-id="7127a-215">应该会收到一条确认消息，指示设置已完成。</span><span class="sxs-lookup"><span data-stu-id="7127a-215">You should get a confirmation message to indicate that your set-up is complete.</span></span>

<span data-ttu-id="7127a-216">你的 Microsoft Defender for Office 365 评估报告每天生成一次。</span><span class="sxs-lookup"><span data-stu-id="7127a-216">Your Microsoft Defender for Office 365 evaluation report is generated once per day.</span></span> <span data-ttu-id="7127a-217">可能需要 24 小时才能填充数据。</span><span class="sxs-lookup"><span data-stu-id="7127a-217">It may take up to 24 hours for the data to populate.</span></span>

### <a name="exchange-rules-optional"></a><span data-ttu-id="7127a-218">Exchange 规则 (可选) </span><span class="sxs-lookup"><span data-stu-id="7127a-218">Exchange rules (optional)</span></span>

<span data-ttu-id="7127a-219">如果您已有网关，启用评估模式将激活连接器的增强筛选。</span><span class="sxs-lookup"><span data-stu-id="7127a-219">If you have an existing gateway, enabling evaluation mode will activate enhanced filtering for connectors.</span></span> <span data-ttu-id="7127a-220">这将通过更改传入发件人 IP 地址提高筛选准确度。</span><span class="sxs-lookup"><span data-stu-id="7127a-220">This improves filtering accuracy by altering the incoming sender IP address.</span></span> <span data-ttu-id="7127a-221">这可能会更改筛选裁定，如果不绕过 Exchange Online Protection，这可能会改变某些邮件的可传递性。</span><span class="sxs-lookup"><span data-stu-id="7127a-221">This may change the filter verdicts and if you are not bypassing Exchange Online Protection this may alter deliverability for certain messages.</span></span> <span data-ttu-id="7127a-222">在这种情况下，您可能需要暂时绕过筛选来分析影响。</span><span class="sxs-lookup"><span data-stu-id="7127a-222">In this case you might want to temporarily bypass filtering to analyze impact.</span></span> <span data-ttu-id="7127a-223">若要绕过，请导航到 Exchange 管理中心，并创建 SCL -1 策略 (如果还没有 SCL -1) 。</span><span class="sxs-lookup"><span data-stu-id="7127a-223">To bypass, navigate to the Exchange admin center and create a policy of SCL -1 (if you don't already have one).</span></span> <span data-ttu-id="7127a-224">有关规则组件及其工作方式的详细信息，请参阅 Mail flow rules (transport rules) in Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="7127a-224">For details on the rule components and how they work, see Mail flow rules (transport rules) in Exchange Online.</span></span>

## <a name="evaluate-capabilities"></a><span data-ttu-id="7127a-225">评估功能</span><span class="sxs-lookup"><span data-stu-id="7127a-225">Evaluate capabilities</span></span>

<span data-ttu-id="7127a-226">生成评估报告后，查看组织中电子邮件和协作工作区中标识了多少高级威胁链接、高级威胁附件和潜在模拟。</span><span class="sxs-lookup"><span data-stu-id="7127a-226">After the evaluation report has been generated, see how many advanced threat links, advanced threat attachments, and potential impersonations were identified in the emails and collaboration workspaces in your organization.</span></span>

<span data-ttu-id="7127a-227">试用版过期后，可以在 90 天内继续访问报告。</span><span class="sxs-lookup"><span data-stu-id="7127a-227">Once the trial has expired, you can continue to access the report for 90 days.</span></span> <span data-ttu-id="7127a-228">但是，它不会收集更多信息。</span><span class="sxs-lookup"><span data-stu-id="7127a-228">However, it won't collect any more information.</span></span> <span data-ttu-id="7127a-229">如果你希望在你的试用版过期后继续使用 Microsoft Defender for Office 365，请确保你购买了 [Microsoft Defender for Office 365 ](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) (计划 2) 。</span><span class="sxs-lookup"><span data-stu-id="7127a-229">If you want to continue using Microsoft Defender for Office 365 after your trial has expired, make sure you [buy a paid subscription for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="7127a-230">你随时都可以转到 **设置** 以更新路由或关闭评估。</span><span class="sxs-lookup"><span data-stu-id="7127a-230">You can go to **Settings** to update your routing or turn off your evaluation at any time.</span></span> <span data-ttu-id="7127a-231">但是，如果你决定在关闭评估后继续评估，则需要再次完成相同的设置过程。</span><span class="sxs-lookup"><span data-stu-id="7127a-231">However, you need to go through the same set-up process again should you decide to continue your evaluation after having turned it off.</span></span>

## <a name="provide-feedback"></a><span data-ttu-id="7127a-232">提供反馈</span><span class="sxs-lookup"><span data-stu-id="7127a-232">Provide feedback</span></span>

<span data-ttu-id="7127a-233">你的反馈可帮助我们更好地保护你的环境免受高级攻击。</span><span class="sxs-lookup"><span data-stu-id="7127a-233">Your feedback helps us get better at protecting your environment from advanced attacks.</span></span> <span data-ttu-id="7127a-234">分享产品功能和评估结果的体验和印象。</span><span class="sxs-lookup"><span data-stu-id="7127a-234">Share your experience and impressions of product capabilities and evaluation results.</span></span>

<span data-ttu-id="7127a-235">选择 **"提供** 反馈"，告诉我们您的想法。</span><span class="sxs-lookup"><span data-stu-id="7127a-235">Select **Give feedback** to let us know what you think.</span></span>