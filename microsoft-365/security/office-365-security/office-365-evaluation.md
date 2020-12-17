---
title: 评估 Microsoft Defender for Office 365
description: 评估模式下的 Defender for Office 365 创建 Office 365 电子邮件策略的 Defender，用于记录裁定（如恶意软件）但不对邮件执行任何操作。
keywords: 评估 Office 365， Microsoft Defender for Office 365， office 365 评估， 试用 office 365， Microsoft Defender， ATP
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: abb33b85717e63cb78a2b1edfd86584fd165a71f
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701011"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a><span data-ttu-id="28d75-104">评估 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="28d75-104">Evaluate Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> <span data-ttu-id="28d75-105">评估 Microsoft Defender for Office 365 将很快公开预览版。</span><span class="sxs-lookup"><span data-stu-id="28d75-105">Evaluate Microsoft Defender for Office 365 will soon be in public preview.</span></span> <span data-ttu-id="28d75-106">提供此预览版本时没有服务级别协议。</span><span class="sxs-lookup"><span data-stu-id="28d75-106">This preview version is provided without a service level agreement.</span></span> <span data-ttu-id="28d75-107">某些功能可能不受支持，或者可能具有受限功能。</span><span class="sxs-lookup"><span data-stu-id="28d75-107">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="28d75-108">执行全面的安全产品评估可帮助你做出有关升级和购买的明智决定。</span><span class="sxs-lookup"><span data-stu-id="28d75-108">Conducting a comprehensive security product evaluation can help give you informed decisions on upgrades and purchases.</span></span> <span data-ttu-id="28d75-109">它有助于试用安全产品的功能，以评估它如何有助于安全运营团队完成日常任务。</span><span class="sxs-lookup"><span data-stu-id="28d75-109">It helps to try out the security product's capabilities to assess how it can help your security operations team in their daily tasks.</span></span>

<span data-ttu-id="28d75-110">[Microsoft Defender for Office 365](office-365-atp.md)评估体验旨在消除设备和环境配置的复杂性，以便你可以专注于评估安全解决方案的功能。</span><span class="sxs-lookup"><span data-stu-id="28d75-110">The [Microsoft Defender for Office 365](office-365-atp.md) evaluation experience is designed to eliminate the complexities of device and environment configuration so that you can focus on evaluating the capabilities of the security solution.</span></span> <span data-ttu-id="28d75-111">它仅适用于电子邮件保护，不应用于 SharePoint、Office 客户端或 Teams。</span><span class="sxs-lookup"><span data-stu-id="28d75-111">It only applies to email protection and not SharePoint, Office Clients, or Teams.</span></span>

<span data-ttu-id="28d75-112">如果还没有支持 Microsoft Defender for Office 365 的许可证，可以开始为期 [30](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) 天的免费评估，并测试 Office 365 安全与合规中心&功能 https://protection.office.com/homepage) (。</span><span class="sxs-lookup"><span data-stu-id="28d75-112">If you don't already have a license that supports Microsoft Defender for Office 365, you can start a [free 30-day evaluation](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) and test the capabilities in the Office 365 Security & Compliance center (https://protection.office.com/homepage).</span></span> <span data-ttu-id="28d75-113">您将享受快速设置，并在必要时轻松关闭它。</span><span class="sxs-lookup"><span data-stu-id="28d75-113">You'll enjoy the quick set-up and you can easily turn it off if necessary.</span></span>

## <a name="how-the-evaluation-works"></a><span data-ttu-id="28d75-114">评估的工作原理</span><span class="sxs-lookup"><span data-stu-id="28d75-114">How the evaluation works</span></span>

<span data-ttu-id="28d75-115">评估模式下的 Defender for Office 365 创建 Office 365 电子邮件策略的 Defender，用于记录裁定（如恶意软件）但不对邮件执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="28d75-115">Defender for Office 365 in evaluation mode creates Defender for Office 365 email policies that log verdicts, such as malware, but don't act on messages.</span></span> <span data-ttu-id="28d75-116">无需更改 MX 记录配置。</span><span class="sxs-lookup"><span data-stu-id="28d75-116">You are not required to change your MX record configuration.</span></span>

<span data-ttu-id="28d75-117">使用评估 [模式，将](atp-safe-attachments.md)代表你 [](atp-safe-links.md)设置安全附件、 [](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)安全链接和防钓鱼模拟策略。</span><span class="sxs-lookup"><span data-stu-id="28d75-117">With evaluation mode, [Safe Attachments](atp-safe-attachments.md), [Safe Links](atp-safe-links.md), and [anti-phishing impersonation policies](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) are set up on your behalf.</span></span> <span data-ttu-id="28d75-118">所有 Defender for Office 365 策略都是在后台的非强制模式下创建的，并且对不可见。</span><span class="sxs-lookup"><span data-stu-id="28d75-118">All Defender for Office 365 policies are created in non-enforcement mode in the background and are not visible to you.</span></span>

<span data-ttu-id="28d75-119">作为设置的一部分，评估模式还配置 [连接器的增强筛选](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="28d75-119">As part of the setup, evaluation mode also configures [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span> <span data-ttu-id="28d75-120">它通过保留 IP 地址和发件人信息提高了筛选准确度，否则当邮件通过 Office 365 的 Defender (ESG) 电子邮件安全网关时，这些邮件会丢失。</span><span class="sxs-lookup"><span data-stu-id="28d75-120">It improves filtering accuracy by preserving IP address and sender information, which are otherwise lost when mail passes through an email security gateway (ESG) in front of Defender for Office 365.</span></span> <span data-ttu-id="28d75-121">增强的筛选功能还可提高 Exchange Online Protection (EOP) 反垃圾邮件和防钓鱼策略的筛选准确度。</span><span class="sxs-lookup"><span data-stu-id="28d75-121">Enhanced Filtering also improves the filtering accuracy for your Exchange Online Protection (EOP) anti-spam and anti-phishing policies.</span></span>

<span data-ttu-id="28d75-122">为了最大限度地减少对一些不受支持的方案的潜在生产影响，您可以通过创建传输规则将垃圾邮件可信度 (SCL) 设置为 -1 来绕过所有 EOP 筛选。</span><span class="sxs-lookup"><span data-stu-id="28d75-122">To minimize potential production impact on some unsupported scenarios, you can bypass all EOP filtering by creating a transport rule to set the Spam Confidence Level (SCL) to -1.</span></span> <span data-ttu-id="28d75-123"> [有关详细信息，请参阅"使用 EAC 创建设置邮件 SCL 的邮件流](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)   规则"。</span><span class="sxs-lookup"><span data-stu-id="28d75-123">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) for details.</span></span>

<span data-ttu-id="28d75-124">设置评估模式后，你每天将更新一个报告，其中最多包含 90 天的数据，用于量化实施策略时可能阻止的邮件 (例如删除、发送到垃圾邮件、隔离邮件) 。</span><span class="sxs-lookup"><span data-stu-id="28d75-124">When the evaluation mode is set up, you will have a report updated daily with up to 90 days of data quantifying the messages that would have been blocked if the policies were implemented (for example, delete, send to junk, quarantine).</span></span> <span data-ttu-id="28d75-125">针对所有 Defender for Office 365 和 EOP 检测生成报告。</span><span class="sxs-lookup"><span data-stu-id="28d75-125">Reports are generated for all Defender for Office 365 and EOP detections.</span></span> <span data-ttu-id="28d75-126">它们根据检测技术聚合 (例如，模拟) ，并可以按时间范围进行筛选。</span><span class="sxs-lookup"><span data-stu-id="28d75-126">They are aggregated per detection technology (for example, impersonation) and can be filtered by time range.</span></span> <span data-ttu-id="28d75-127">此外，还可以按需创建邮件报告以创建自定义透视表，或者使用威胁资源管理器深入探究邮件。</span><span class="sxs-lookup"><span data-stu-id="28d75-127">Additionally, message reports can be created on-demand to create custom pivots or to deep dive messages using Threat Explorer.</span></span>

<span data-ttu-id="28d75-128">借助简化的设置体验，你可以专注于：</span><span class="sxs-lookup"><span data-stu-id="28d75-128">With the simplified set-up experience, you can focus on:</span></span>

- <span data-ttu-id="28d75-129">运行评估</span><span class="sxs-lookup"><span data-stu-id="28d75-129">Running the evaluation</span></span>
- <span data-ttu-id="28d75-130">获取详细报告</span><span class="sxs-lookup"><span data-stu-id="28d75-130">Getting a detailed report</span></span>
- <span data-ttu-id="28d75-131">分析报告的操作</span><span class="sxs-lookup"><span data-stu-id="28d75-131">Analyzing the report for action</span></span>
- <span data-ttu-id="28d75-132">显示评估结果</span><span class="sxs-lookup"><span data-stu-id="28d75-132">Presenting the evaluation outcome</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="28d75-133">准备工作</span><span class="sxs-lookup"><span data-stu-id="28d75-133">Before you begin</span></span>

### <a name="licensing"></a><span data-ttu-id="28d75-134">许可</span><span class="sxs-lookup"><span data-stu-id="28d75-134">Licensing</span></span>

<span data-ttu-id="28d75-135">若要访问评估，你将需要满足许可要求。</span><span class="sxs-lookup"><span data-stu-id="28d75-135">To access the evaluation, you'll need to meet the licensing requirements.</span></span> <span data-ttu-id="28d75-136">以下任一许可证都可用：</span><span class="sxs-lookup"><span data-stu-id="28d75-136">Any of the following licenses will work:</span></span>

- <span data-ttu-id="28d75-137">Microsoft Defender for Office 365 计划 1</span><span class="sxs-lookup"><span data-stu-id="28d75-137">Microsoft Defender for Office 365 Plan 1</span></span>
- <span data-ttu-id="28d75-138">Microsoft Defender for Office 365 计划 2</span><span class="sxs-lookup"><span data-stu-id="28d75-138">Microsoft Defender for Office 365 Plan 2</span></span>
- <span data-ttu-id="28d75-139">Microsoft 365 E5、Microsoft 365 E5 安全</span><span class="sxs-lookup"><span data-stu-id="28d75-139">Microsoft 365 E5, Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="28d75-140">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="28d75-140">Office 365 E5</span></span>

<span data-ttu-id="28d75-141">如果你没有这些许可证之一，则需要获取试用许可证。</span><span class="sxs-lookup"><span data-stu-id="28d75-141">If you don't have one of those licenses, then you'll need to obtain a trial license.</span></span>

#### <a name="trial"></a><span data-ttu-id="28d75-142">试用</span><span class="sxs-lookup"><span data-stu-id="28d75-142">Trial</span></span>

<span data-ttu-id="28d75-143">若要获取适用于 Office 365 的 Microsoft Defender 的试用许可证，你需要具有帐单管理员 **角色** 或 **全局管理员角色**。</span><span class="sxs-lookup"><span data-stu-id="28d75-143">To obtain a trial license for Microsoft Defender for Office 365, you need to have the **Billing admin role** or **Global admin role**.</span></span> <span data-ttu-id="28d75-144">向具有全局管理员角色的人请求权限。</span><span class="sxs-lookup"><span data-stu-id="28d75-144">Request permission from someone that has the Global admin role.</span></span> [<span data-ttu-id="28d75-145">了解订阅和许可证</span><span class="sxs-lookup"><span data-stu-id="28d75-145">Learn about subscriptions and licenses</span></span>](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

<span data-ttu-id="28d75-146">获得适当角色后，建议的路径是，通过进入"帐单 > 购买服务"，在 Microsoft 365 管理中心获取适用于 Office 365 (计划 2) 的 Microsoft Defender 试用许可证。</span><span class="sxs-lookup"><span data-stu-id="28d75-146">Once you have the proper role, the recommended path is to obtain a trial license for Microsoft Defender for Office 365 (Plan 2) in the Microsoft 365 admin center by going to Billing > Purchase services.</span></span> <span data-ttu-id="28d75-147">试用版包含 25 个许可证的 30 天免费试用版。</span><span class="sxs-lookup"><span data-stu-id="28d75-147">The trial includes a 30-day free trial for 25 licenses.</span></span> <span data-ttu-id="28d75-148">[获取 Microsoft Defender for Office 365 (计划 2) 。 ](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)</span><span class="sxs-lookup"><span data-stu-id="28d75-148">[Get a trial for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="28d75-149">你将有一个 30 天的窗口，其评估用于监视并报告高级威胁。</span><span class="sxs-lookup"><span data-stu-id="28d75-149">You'll have a 30-day window with the evaluation to monitor and report on advanced threats.</span></span> <span data-ttu-id="28d75-150">如果需要完整的 Defender for Office 365 功能，还可以选择购买付费订阅。</span><span class="sxs-lookup"><span data-stu-id="28d75-150">You'll also have the option to buy a paid subscription if you want the full Defender for Office 365 capabilities.</span></span>

### <a name="roles"></a><span data-ttu-id="28d75-151">角色</span><span class="sxs-lookup"><span data-stu-id="28d75-151">Roles</span></span>

<span data-ttu-id="28d75-152">在评估模式下设置适用于 Office 365 的 Defender 时，需要 Exchange Online 角色。</span><span class="sxs-lookup"><span data-stu-id="28d75-152">Exchange Online roles are required to set up Defender for Office 365 in evaluation mode.</span></span>

- [<span data-ttu-id="28d75-153">了解 Exchange Online 中的权限</span><span class="sxs-lookup"><span data-stu-id="28d75-153">Learn about permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
- [<span data-ttu-id="28d75-154">了解如何分配管理员角色</span><span class="sxs-lookup"><span data-stu-id="28d75-154">Learn about assigning admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)

<span data-ttu-id="28d75-155">需要以下角色：</span><span class="sxs-lookup"><span data-stu-id="28d75-155">The following roles are needed:</span></span>

|<span data-ttu-id="28d75-156">任务</span><span class="sxs-lookup"><span data-stu-id="28d75-156">Task</span></span>|<span data-ttu-id="28d75-157">Role</span><span class="sxs-lookup"><span data-stu-id="28d75-157">Role</span></span>|
|---|---|
|<span data-ttu-id="28d75-158">获取免费试用版或购买 Microsoft Defender for Office 365 (计划 2) </span><span class="sxs-lookup"><span data-stu-id="28d75-158">Get a free trial or buy Microsoft Defender for Office 365 (Plan 2)</span></span>|<span data-ttu-id="28d75-159">计费管理员角色或全局管理员角色</span><span class="sxs-lookup"><span data-stu-id="28d75-159">Billing admin role OR Global admin role</span></span>|
|<span data-ttu-id="28d75-160">创建评估策略</span><span class="sxs-lookup"><span data-stu-id="28d75-160">Create evaluation policy</span></span>|<span data-ttu-id="28d75-161">远程域和接受域角色;安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="28d75-161">Remote and Accepted Domains role; Security admin role</span></span>|
|<span data-ttu-id="28d75-162">编辑评估策略</span><span class="sxs-lookup"><span data-stu-id="28d75-162">Edit evaluation policy</span></span>|<span data-ttu-id="28d75-163">远程域和接受域角色;安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="28d75-163">Remote and Accepted Domains role; Security admin role</span></span>|
|<span data-ttu-id="28d75-164">删除评估策略</span><span class="sxs-lookup"><span data-stu-id="28d75-164">Delete evaluation policy</span></span>|<span data-ttu-id="28d75-165">远程域和接受域角色;安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="28d75-165">Remote and Accepted Domains role; Security admin role</span></span> |
|<span data-ttu-id="28d75-166">查看评估报告</span><span class="sxs-lookup"><span data-stu-id="28d75-166">View evaluation report</span></span>|<span data-ttu-id="28d75-167">安全管理员角色或安全读者角色</span><span class="sxs-lookup"><span data-stu-id="28d75-167">Security admin role OR Security reader role</span></span>|
|


### <a name="enhanced-filtering"></a><span data-ttu-id="28d75-168">增强的筛选</span><span class="sxs-lookup"><span data-stu-id="28d75-168">Enhanced filtering</span></span>

<span data-ttu-id="28d75-169">Exchange Online Protection 策略（如批量和垃圾邮件保护）将保持不变。</span><span class="sxs-lookup"><span data-stu-id="28d75-169">Your Exchange Online Protection policies, such as bulk and spam protection, will remain the same.</span></span> <span data-ttu-id="28d75-170">邮件传递也保持不变。</span><span class="sxs-lookup"><span data-stu-id="28d75-170">Message delivery will also remain the same.</span></span> <span data-ttu-id="28d75-171">但是，该评估将对连接器启用增强的筛选，这将影响邮件流和 Exchange Online Protection 策略，除非绕过。</span><span class="sxs-lookup"><span data-stu-id="28d75-171">However, the evaluation turns on enhanced filtering for connectors, which will impact your mail flow and Exchange Online Protection policies unless bypassed.</span></span>

<span data-ttu-id="28d75-172">连接器的增强筛选将允许租户使用反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="28d75-172">Enhanced filtering for connectors will allow tenants to use anti-spoofing protection.</span></span> <span data-ttu-id="28d75-173">如果使用电子邮件安全网关 (ESG) 未启用连接器的增强筛选，则不支持反欺骗。</span><span class="sxs-lookup"><span data-stu-id="28d75-173">Anti-spoofing is not supported if you're using an email security gateway (ESG) without having turned on Enhanced filtering for connectors.</span></span>

### <a name="urls"></a><span data-ttu-id="28d75-174">URL</span><span class="sxs-lookup"><span data-stu-id="28d75-174">URLs</span></span>

<span data-ttu-id="28d75-175">URL 将在邮件流期间触发。</span><span class="sxs-lookup"><span data-stu-id="28d75-175">URLs will be detonated during mail flow.</span></span> <span data-ttu-id="28d75-176">如果不希望触发特定 URL，请适当地管理允许的 URL 列表。</span><span class="sxs-lookup"><span data-stu-id="28d75-176">If you don't want specific URLs detonated, manage your list of allowed URLs appropriately.</span></span> <span data-ttu-id="28d75-177">有关详细信息 [，请参阅"管理租户允许/阻止列表"](tenant-allow-block-list.md) 中的 URL。</span><span class="sxs-lookup"><span data-stu-id="28d75-177">See [Manage URLs in the Tenant Allow/Block List](tenant-allow-block-list.md) for details.</span></span>

<span data-ttu-id="28d75-178">电子邮件正文中的 URL 链接不会换行，以减少客户影响。</span><span class="sxs-lookup"><span data-stu-id="28d75-178">URL links in the email message bodies won't wrap, to lessen customer impact.</span></span>

### <a name="email-routing"></a><span data-ttu-id="28d75-179">电子邮件路由</span><span class="sxs-lookup"><span data-stu-id="28d75-179">Email routing</span></span>

<span data-ttu-id="28d75-180">准备设置电子邮件当前路由方式所需的相应详细信息，包括路由邮件的入站连接器的名称。</span><span class="sxs-lookup"><span data-stu-id="28d75-180">Prepare the corresponding details that you will need to set up how your email is currently routed, including the name of the inbound connector that routes your mail.</span></span> <span data-ttu-id="28d75-181">如果您只是使用 Exchange Online Protection，则没有连接器。 [了解邮件流和电子邮件路由](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span><span class="sxs-lookup"><span data-stu-id="28d75-181">If you are just using Exchange Online Protection, you won’t have a connector. [Learn about mail flow and email routing](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span></span>

<span data-ttu-id="28d75-182">支持的电子邮件路由方案包括：</span><span class="sxs-lookup"><span data-stu-id="28d75-182">Supported email routing scenarios include:</span></span>

- <span data-ttu-id="28d75-183">**第三方合作伙伴和/或** 本地服务提供商：要评估的入站连接器使用第三方提供商和/或正在使用本地电子邮件安全解决方案。</span><span class="sxs-lookup"><span data-stu-id="28d75-183">**Third-party partner and/or on-premises service provider**: The inbound connector that you want to evaluate uses a third-party provider and/or you're using a solution for email security on-premises.</span></span>
- <span data-ttu-id="28d75-184">**Microsoft Exchange Online保护**：要评估的租户使用 Office 365 进行电子邮件安全保护，邮件 Exchange (MX) 记录指向 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="28d75-184">**Microsoft Exchange Online Protection only**: The tenant that you want to evaluate uses Office 365 for email security and the Mail Exchange (MX) record points to Microsoft.</span></span>

### <a name="email-security-gateway"></a><span data-ttu-id="28d75-185">电子邮件安全网关</span><span class="sxs-lookup"><span data-stu-id="28d75-185">Email security gateway</span></span>

<span data-ttu-id="28d75-186">如果使用第三方电子邮件安全网关 (ESG) ，则需要知道提供商的名称。</span><span class="sxs-lookup"><span data-stu-id="28d75-186">If you're using a third-party email security gateway (ESG), you'll need to know the provider's name.</span></span> <span data-ttu-id="28d75-187">如果你使用的是本地或不支持的 ESG 供应商，你需要知道设备的公用 IP 地址 () 地址。</span><span class="sxs-lookup"><span data-stu-id="28d75-187">If you're using an ESG on-premises or non-supported vendors, you'll need to know the public IP address(es) for the devices.</span></span>

<span data-ttu-id="28d75-188">受支持的第三方合作伙伴包括：</span><span class="sxs-lookup"><span data-stu-id="28d75-188">Supported third-party partners include:</span></span>

- <span data-ttu-id="28d75-189">Barracuda</span><span class="sxs-lookup"><span data-stu-id="28d75-189">Barracuda</span></span>
- <span data-ttu-id="28d75-190">IronPort</span><span class="sxs-lookup"><span data-stu-id="28d75-190">IronPort</span></span>
- <span data-ttu-id="28d75-191">Mimecast</span><span class="sxs-lookup"><span data-stu-id="28d75-191">Mimecast</span></span>
- <span data-ttu-id="28d75-192">Proofpoint</span><span class="sxs-lookup"><span data-stu-id="28d75-192">Proofpoint</span></span>
- <span data-ttu-id="28d75-193">斯拉多斯</span><span class="sxs-lookup"><span data-stu-id="28d75-193">Sophos</span></span>
- <span data-ttu-id="28d75-194">Symantec</span><span class="sxs-lookup"><span data-stu-id="28d75-194">Symantec</span></span>
- <span data-ttu-id="28d75-195">Trend Micro</span><span class="sxs-lookup"><span data-stu-id="28d75-195">Trend Micro</span></span>

### <a name="scoping"></a><span data-ttu-id="28d75-196">界定访问权限</span><span class="sxs-lookup"><span data-stu-id="28d75-196">Scoping</span></span>

<span data-ttu-id="28d75-197">您将能够将评估范围确定为入站连接器。</span><span class="sxs-lookup"><span data-stu-id="28d75-197">You will be able to scope the evaluation to an inbound connector.</span></span> <span data-ttu-id="28d75-198">如果未配置连接器，则评估范围将允许管理员从租户中任何用户收集数据，以评估 Defender for Office 365。</span><span class="sxs-lookup"><span data-stu-id="28d75-198">If there's no connector configured, then the evaluation scope will allow admins to gather data from any user in your tenant to evaluate Defender for Office 365.</span></span>

## <a name="get-started-with-the-evaluation"></a><span data-ttu-id="28d75-199">评估入门</span><span class="sxs-lookup"><span data-stu-id="28d75-199">Get started with the evaluation</span></span>

<span data-ttu-id="28d75-200">在 Office 365 安全与合规中心内查找 Microsoft Defender for Office 365 &设置 (https://protection.office.com/homepage) 访问点：</span><span class="sxs-lookup"><span data-stu-id="28d75-200">Find the Microsoft Defender for Office 365 evaluation set-up card in the Office 365 Security & Compliance center (https://protection.office.com/homepage) from three access points:</span></span>

- <span data-ttu-id="28d75-201">威胁管理>仪表板</span><span class="sxs-lookup"><span data-stu-id="28d75-201">Threat management > Dashboard</span></span>
- <span data-ttu-id="28d75-202">威胁管理>策略</span><span class="sxs-lookup"><span data-stu-id="28d75-202">Threat management > Policy</span></span>
- <span data-ttu-id="28d75-203">报表>仪表板</span><span class="sxs-lookup"><span data-stu-id="28d75-203">Reports > Dashboard</span></span>

## <a name="setting-up-the-evaluation"></a><span data-ttu-id="28d75-204">设置评估</span><span class="sxs-lookup"><span data-stu-id="28d75-204">Setting up the evaluation</span></span>

<span data-ttu-id="28d75-205">启动评估的设置流后，您将获得两个路由选项。</span><span class="sxs-lookup"><span data-stu-id="28d75-205">Once you start the set-up flow for your evaluation, you'll be given two routing options.</span></span> <span data-ttu-id="28d75-206">根据组织的邮件路由设置和评估需求，您可以选择是使用第三方和/或本地服务提供商，还是仅使用Microsoft Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="28d75-206">Depending on your organization's mail routing setup and evaluation needs, you can select whether you are using a third-party and/or on-premises service provider or only Microsoft Exchange Online.</span></span>

- <span data-ttu-id="28d75-207">如果使用的是第三方合作伙伴和/或本地服务提供商，则需要从下拉菜单中选择供应商的名称。</span><span class="sxs-lookup"><span data-stu-id="28d75-207">If you are using a third-party partner and/or on-premises service provider, you'll need to select the name of the vendor from the drop-down menu.</span></span> <span data-ttu-id="28d75-208">提供其他与连接器相关的详细信息。</span><span class="sxs-lookup"><span data-stu-id="28d75-208">Provide the other connector-related details.</span></span>

- <span data-ttu-id="28d75-209">如果Microsoft Exchange Online MX 记录指向 Microsoft 并且您拥有 Exchange Online 邮箱，请选择"自动删除"。</span><span class="sxs-lookup"><span data-stu-id="28d75-209">Select Microsoft Exchange Online if the MX record points to Microsoft and you have an Exchange Online mailbox.</span></span>

<span data-ttu-id="28d75-210">查看你的设置并在必要时编辑它们。</span><span class="sxs-lookup"><span data-stu-id="28d75-210">Review your settings and edit them if necessary.</span></span> <span data-ttu-id="28d75-211">然后，选择 **"创建评估"。**</span><span class="sxs-lookup"><span data-stu-id="28d75-211">Then, select **Create evaluation**.</span></span> <span data-ttu-id="28d75-212">应收到确认消息，指示设置已完成。</span><span class="sxs-lookup"><span data-stu-id="28d75-212">You should get a confirmation message to indicate that your set-up is complete.</span></span>

<span data-ttu-id="28d75-213">Microsoft Defender for Office 365 评估报告每天生成一次。</span><span class="sxs-lookup"><span data-stu-id="28d75-213">Your Microsoft Defender for Office 365 evaluation report is generated once per day.</span></span> <span data-ttu-id="28d75-214">可能需要 24 小时才能填充数据。</span><span class="sxs-lookup"><span data-stu-id="28d75-214">It may take up to 24 hours for the data to populate.</span></span>

### <a name="exchange-rules-optional"></a><span data-ttu-id="28d75-215">Exchange 规则 (可选) </span><span class="sxs-lookup"><span data-stu-id="28d75-215">Exchange rules (optional)</span></span>

<span data-ttu-id="28d75-216">如果您具有现有网关，您可能需要绕过筛选，因为它将激活连接器的增强筛选并更改传入发件人 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="28d75-216">If you have an existing gateway, you might want to bypass filtering because it will activate enhanced filtering for connectors and alter the incoming sender IP address.</span></span> <span data-ttu-id="28d75-217">若要绕过，请导航到 Exchange 管理中心，并创建 SCL -1 策略 (如果还没有 SCL -1) 。</span><span class="sxs-lookup"><span data-stu-id="28d75-217">To bypass, navigate to the Exchange admin center and create a policy of SCL -1 (if you don't already have one).</span></span> <span data-ttu-id="28d75-218">有关规则组件及其工作方式的详细信息，请参阅 Exchange Online (传输规则) 规则。</span><span class="sxs-lookup"><span data-stu-id="28d75-218">For details on the rule components and how they work, see Mail flow rules (transport rules) in Exchange Online.</span></span>

## <a name="evaluate-capabilities"></a><span data-ttu-id="28d75-219">评估功能</span><span class="sxs-lookup"><span data-stu-id="28d75-219">Evaluate capabilities</span></span>

<span data-ttu-id="28d75-220">生成评估报告后，查看组织中电子邮件和协作工作区中标识了多少高级威胁链接、高级威胁附件和潜在模拟。</span><span class="sxs-lookup"><span data-stu-id="28d75-220">After the evaluation report has been generated, see how many advanced threat links, advanced threat attachments, and potential impersonations were identified in the emails and collaboration workspaces in your organization.</span></span>

<span data-ttu-id="28d75-221">试用版过期后，您可以在 90 天内继续访问报告。</span><span class="sxs-lookup"><span data-stu-id="28d75-221">Once the trial has expired, you can continue to access the report for 90 days.</span></span> <span data-ttu-id="28d75-222">但是，它不会收集更多信息。</span><span class="sxs-lookup"><span data-stu-id="28d75-222">However, it won't collect any more information.</span></span> <span data-ttu-id="28d75-223">如果你想要在试用到期后继续使用适用于 Office 365 的 Microsoft Defender，请确保为 [Microsoft Defender for Office 365 ](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) (计划 2) 。</span><span class="sxs-lookup"><span data-stu-id="28d75-223">If you want to continue using Microsoft Defender for Office 365 after your trial has expired, make sure you [buy a paid subscription for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="28d75-224">你可以 **转到"设置** "以随时更新路由或关闭评估。</span><span class="sxs-lookup"><span data-stu-id="28d75-224">You can go to **Settings** to update your routing or turn off your evaluation at any time.</span></span> <span data-ttu-id="28d75-225">但是，如果你决定在关闭评估后继续评估，则需要再次执行相同的设置过程。</span><span class="sxs-lookup"><span data-stu-id="28d75-225">However, you need to go through the same set-up process again should you decide to continue your evaluation after having turned it off.</span></span>

## <a name="provide-feedback"></a><span data-ttu-id="28d75-226">提供反馈</span><span class="sxs-lookup"><span data-stu-id="28d75-226">Provide feedback</span></span>

<span data-ttu-id="28d75-227">你的反馈可帮助我们更好地保护你的环境免受高级攻击。</span><span class="sxs-lookup"><span data-stu-id="28d75-227">Your feedback helps us get better at protecting your environment from advanced attacks.</span></span> <span data-ttu-id="28d75-228">分享产品功能和评估结果的体验和印象。</span><span class="sxs-lookup"><span data-stu-id="28d75-228">Share your experience and impressions of product capabilities and evaluation results.</span></span>

<span data-ttu-id="28d75-229">选择 **"提供** 反馈"，告诉我们您的想法。</span><span class="sxs-lookup"><span data-stu-id="28d75-229">Select **Give feedback** to let us know what you think.</span></span>
