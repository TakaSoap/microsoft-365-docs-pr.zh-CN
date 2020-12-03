---
title: 评估 Microsoft Defender for Office 365
description: 评估模式下的 Office 365 的 defender 为 Office 365 电子邮件策略创建了用于记录 verdicts 的 Defender，如恶意软件，但不对邮件执行操作。
keywords: 评估 Office 365、Microsoft Defender for Office 365、Office 365 评估、试用 Office 365、Microsoft Defender、ATP
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
ms.openlocfilehash: 12b6499822f8ed97ace8468054f219361d925332
ms.sourcegitcommit: a566ef236c85edfd566c8c3f859b80f9e5ce0473
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "49562984"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a><span data-ttu-id="13009-104">评估 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="13009-104">Evaluate Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

>[!IMPORTANT]
><span data-ttu-id="13009-105">评估 Microsoft Defender for Office 365 不久将在公共预览版中提供此预览版本，但不提供服务级别协议。</span><span class="sxs-lookup"><span data-stu-id="13009-105">Evaluate Microsoft Defender for Office 365 will soon be in public preview This preview version is provided without a service level agreement.</span></span> <span data-ttu-id="13009-106">某些功能可能不受支持或可能具有受约束的功能。</span><span class="sxs-lookup"><span data-stu-id="13009-106">Certain features might not be supported or might have constrained capabilities.</span></span>

<span data-ttu-id="13009-107">进行全面的安全产品评估有助于向您提供有关升级和购买的有根据的决策。</span><span class="sxs-lookup"><span data-stu-id="13009-107">Conducting a comprehensive security product evaluation can help give you informed decisions on upgrades and purchases.</span></span> <span data-ttu-id="13009-108">它有助于试用安全产品的功能，以评估如何帮助安全操作团队在日常任务中进行评估。</span><span class="sxs-lookup"><span data-stu-id="13009-108">It helps to try out the security product’s capabilities to assess how it can help your security operations team in their daily tasks.</span></span>

<span data-ttu-id="13009-109">[Microsoft Defender For Office 365](office-365-atp.md)评估体验旨在消除设备和环境配置的复杂性，这样您就可以专注于评估安全解决方案的功能。</span><span class="sxs-lookup"><span data-stu-id="13009-109">The [Microsoft Defender for Office 365](office-365-atp.md) evaluation experience is designed to eliminate the complexities of device and environment configuration so that you can focus on evaluating the capabilities of the security solution.</span></span> <span data-ttu-id="13009-110">它仅适用于电子邮件保护，而不适用于 SharePoint、Office 客户端或团队。</span><span class="sxs-lookup"><span data-stu-id="13009-110">It only applies to email protection and not SharePoint, Office Clients, or Teams.</span></span>

<span data-ttu-id="13009-111">如果你还没有支持 Microsoft Defender for Office 365 的许可证，你可以开始 [30 天免费评估](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) ，并在 Office 365 安全性 & 合规性中心 (中测试功能 https://protection.office.com/homepage) 。</span><span class="sxs-lookup"><span data-stu-id="13009-111">If you don't already have a license that supports Microsoft Defender for Office 365, you can start a [free 30-day evaluation](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) and test the capabilities in the Office 365 Security & Compliance center (https://protection.office.com/homepage).</span></span> <span data-ttu-id="13009-112">你将喜欢快速设置，如果需要，你可以轻松地将其关闭。</span><span class="sxs-lookup"><span data-stu-id="13009-112">You'll enjoy the quick set-up and you can easily turn it off if necessary.</span></span>

## <a name="how-the-evaluation-works"></a><span data-ttu-id="13009-113">评估的工作方式</span><span class="sxs-lookup"><span data-stu-id="13009-113">How the evaluation works</span></span>

<span data-ttu-id="13009-114">评估模式下的 Office 365 的 defender 为 Office 365 电子邮件策略创建了用于记录 verdicts 的 Defender，如恶意软件，但不对邮件执行操作。</span><span class="sxs-lookup"><span data-stu-id="13009-114">Defender for Office 365 in evaluation mode creates Defender for Office 365 email policies that log verdicts, such as malware, but don’t act on messages.</span></span> <span data-ttu-id="13009-115">您无需更改 MX 记录配置。</span><span class="sxs-lookup"><span data-stu-id="13009-115">You are not required to change your MX record configuration.</span></span>

<span data-ttu-id="13009-116">使用评估模式时，将代表你设置 [安全附件](atp-safe-attachments.md)、 [安全链接](atp-safe-links.md)和 [反钓鱼网络模拟策略](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) 。</span><span class="sxs-lookup"><span data-stu-id="13009-116">With evaluation mode, [Safe Attachments](atp-safe-attachments.md), [Safe Links](atp-safe-links.md), and [anti-phishing impersonation policies](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) are setup on your behalf.</span></span> <span data-ttu-id="13009-117">所有适用于 Office 365 的 Defender 策略都是在后台非强制模式下创建的，对你不可见。</span><span class="sxs-lookup"><span data-stu-id="13009-117">All Defender for Office 365 policies are created in non-enforcement mode in the background and are not visible to you.</span></span>

<span data-ttu-id="13009-118">在设置过程中，评估模式还会为 [连接器配置增强的筛选](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="13009-118">As part of the setup, evaluation mode also configures [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span> <span data-ttu-id="13009-119">它通过保留 IP 地址和发件人信息来提高筛选准确性，当邮件通过电子邮件安全网关 (ESG) 在 Office 365 的前端中时，这些信息将会丢失。</span><span class="sxs-lookup"><span data-stu-id="13009-119">It improves filtering accuracy by preserving IP address and sender information, which are otherwise lost when mail passes through an email security gateway (ESG) in front of Defender for Office 365.</span></span> <span data-ttu-id="13009-120">这还提高了 Exchange Online Protection (EOP) 反垃圾邮件和反网络钓鱼策略的筛选准确性。</span><span class="sxs-lookup"><span data-stu-id="13009-120">This also improves the filtering accuracy for your Exchange Online Protection (EOP) anti-spam and anti-phishing policies.</span></span>

<span data-ttu-id="13009-121">若要最大限度地减少对某些不受支持的方案的潜在生产影响，可以通过创建传输规则来将垃圾邮件可信度 (SCL) 设置为-1，从而绕过所有 EOP 筛选。</span><span class="sxs-lookup"><span data-stu-id="13009-121">To minimize potential production impact on some unsupported scenarios, you can bypass all EOP filtering by creating a transport rule to set the Spam Confidence Level (SCL) to -1.</span></span> <span data-ttu-id="13009-122">有关详细信息，请参阅 [使用 EAC 创建邮件流规则，以设置邮件的 SCL](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)   。</span><span class="sxs-lookup"><span data-stu-id="13009-122">See [Use the EAC to create a mail flow rule that sets the SCL of a message](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) for details.</span></span>

<span data-ttu-id="13009-123">在设置评估模式时，将每日更新一次，最长可达90天的数据量化量化邮件已被阻止的邮件已被阻止，并已实施了策略 (例如，删除、发送到垃圾邮件、隔离) 。</span><span class="sxs-lookup"><span data-stu-id="13009-123">When the evaluation mode is set up, you will have a report updated daily with up to 90 days of data quantifying the messages that would have been blocked had the policies been made and implemented (for example, delete, send to junk, quarantine).</span></span> <span data-ttu-id="13009-124">为所有 Defender for Office 365 和 EOP 检测生成报告。</span><span class="sxs-lookup"><span data-stu-id="13009-124">Reports are generated for all Defender for Office 365 and EOP detections.</span></span> <span data-ttu-id="13009-125">它们按检测技术进行聚合 (例如，模拟) 并可按时间范围进行筛选。</span><span class="sxs-lookup"><span data-stu-id="13009-125">They are aggregated per detection technology (for example, impersonation) and can be filtered by time range.</span></span> <span data-ttu-id="13009-126">此外，还可以按需创建邮件报告，以使用威胁资源管理器创建自定义透视或深入研究邮件。</span><span class="sxs-lookup"><span data-stu-id="13009-126">Additionally, message reports can be created on-demand to create custom pivots or to deep dive messages using Threat Explorer.</span></span>

<span data-ttu-id="13009-127">使用简化的设置体验，您可以重点关注：</span><span class="sxs-lookup"><span data-stu-id="13009-127">With the simplified set-up experience, you can focus on:</span></span>

- <span data-ttu-id="13009-128">运行评估</span><span class="sxs-lookup"><span data-stu-id="13009-128">Running the evaluation</span></span>
- <span data-ttu-id="13009-129">获取详细报告</span><span class="sxs-lookup"><span data-stu-id="13009-129">Getting a detailed report</span></span>
- <span data-ttu-id="13009-130">分析报告的操作</span><span class="sxs-lookup"><span data-stu-id="13009-130">Analyzing the report for action</span></span>
- <span data-ttu-id="13009-131">展示评估结果</span><span class="sxs-lookup"><span data-stu-id="13009-131">Presenting the evaluation outcome</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="13009-132">准备工作</span><span class="sxs-lookup"><span data-stu-id="13009-132">Before you begin</span></span>

### <a name="licensing"></a><span data-ttu-id="13009-133">许可</span><span class="sxs-lookup"><span data-stu-id="13009-133">Licensing</span></span>

<span data-ttu-id="13009-134">若要访问评估版，你需要满足许可要求。</span><span class="sxs-lookup"><span data-stu-id="13009-134">To access the evaluation, you'll need to meet the licensing requirements.</span></span> <span data-ttu-id="13009-135">以下任何许可证都将生效：</span><span class="sxs-lookup"><span data-stu-id="13009-135">Any of the following licenses will work:</span></span>

- <span data-ttu-id="13009-136">Microsoft Defender for Office 365 计划1</span><span class="sxs-lookup"><span data-stu-id="13009-136">Microsoft Defender for Office 365 Plan 1</span></span>
- <span data-ttu-id="13009-137">Microsoft Defender for Office 365 计划2</span><span class="sxs-lookup"><span data-stu-id="13009-137">Microsoft Defender for Office 365 Plan 2</span></span>
- <span data-ttu-id="13009-138">Microsoft 365 E5，Microsoft 365 E5 安全</span><span class="sxs-lookup"><span data-stu-id="13009-138">Microsoft 365 E5, Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="13009-139">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="13009-139">Office 365 E5</span></span>

<span data-ttu-id="13009-140">如果你没有这些许可证中的任何一个，则需要获取试用许可证。</span><span class="sxs-lookup"><span data-stu-id="13009-140">If you don't have one of those licenses, then you'll need to obtain a trial license.</span></span>

#### <a name="trial"></a><span data-ttu-id="13009-141">试用</span><span class="sxs-lookup"><span data-stu-id="13009-141">Trial</span></span>

<span data-ttu-id="13009-142">若要获取 Microsoft Defender for Office 365 试用版许可证，您需要具有 " **记帐管理员" 角色** 或 " **全局管理员" 角色**。</span><span class="sxs-lookup"><span data-stu-id="13009-142">To obtain a trial license for Microsoft Defender for Office 365, you need to have the **Billing admin role** or **Global admin role**.</span></span> <span data-ttu-id="13009-143">向具有全局管理员角色的用户请求权限。</span><span class="sxs-lookup"><span data-stu-id="13009-143">Request permission from someone that has the Global admin role.</span></span> [<span data-ttu-id="13009-144">了解订阅和许可证</span><span class="sxs-lookup"><span data-stu-id="13009-144">Learn about subscriptions and licenses</span></span>](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

<span data-ttu-id="13009-145">拥有适当的角色后，推荐的路径是获取 Microsoft 365 管理中心内的 Microsoft Defender for Office 365 的试用许可证，方法是转到帐单 > 购买服务 (计划 2) 。</span><span class="sxs-lookup"><span data-stu-id="13009-145">Once you have the proper role, the recommended path is to obtain a trial license for Microsoft Defender for Office 365 (Plan 2) in the Microsoft 365 admin center by going to Billing > Purchase services.</span></span> <span data-ttu-id="13009-146">试用版包括30天免费试用版，25个许可证。</span><span class="sxs-lookup"><span data-stu-id="13009-146">The trial includes a 30-day free trial for 25 licenses.</span></span> <span data-ttu-id="13009-147">[获取 Microsoft Defender For Office 365 (Plan 2) 试用版 ](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)。</span><span class="sxs-lookup"><span data-stu-id="13009-147">[Get a trial for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span> 

<span data-ttu-id="13009-148">你将有一个为期30天的窗口，评估版将对高级威胁进行监控和报告。</span><span class="sxs-lookup"><span data-stu-id="13009-148">You'll have a 30-day window with the evaluation to monitor and report on advanced threats.</span></span> <span data-ttu-id="13009-149">如果你想要使用完整的 Defender for Office 365 功能，你也可以选择购买付费订阅。</span><span class="sxs-lookup"><span data-stu-id="13009-149">You'll also have the option to buy a paid subscription if you want the full Defender for Office 365 capabilities.</span></span>

### <a name="roles"></a><span data-ttu-id="13009-150">角色</span><span class="sxs-lookup"><span data-stu-id="13009-150">Roles</span></span>

<span data-ttu-id="13009-151">Exchange Online 角色是在评估模式下设置适用于 Office 365 的 Defender 所必需的。</span><span class="sxs-lookup"><span data-stu-id="13009-151">Exchange Online roles are required to set up Defender for Office 365 in evaluation mode.</span></span> <span data-ttu-id="13009-152">以下角色是必需的：</span><span class="sxs-lookup"><span data-stu-id="13009-152">The following roles are needed:</span></span>

|<span data-ttu-id="13009-153">任务</span><span class="sxs-lookup"><span data-stu-id="13009-153">Task</span></span> | <span data-ttu-id="13009-154">Role</span><span class="sxs-lookup"><span data-stu-id="13009-154">Role</span></span> |
|-----| -----|
| <span data-ttu-id="13009-155">获取免费试用版或购买 Microsoft Defender for Office 365 (Plan 2) </span><span class="sxs-lookup"><span data-stu-id="13009-155">Get a free trial or buy Microsoft Defender for Office 365 (Plan 2)</span></span>| <span data-ttu-id="13009-156">帐单管理员角色或全局管理员角色</span><span class="sxs-lookup"><span data-stu-id="13009-156">Billing admin role OR Global admin role</span></span>|
| <span data-ttu-id="13009-157">创建评估策略</span><span class="sxs-lookup"><span data-stu-id="13009-157">Create evaluation policy</span></span>| <span data-ttu-id="13009-158">远程和接受域角色;安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="13009-158">Remote and Accepted Domains role; Security admin role</span></span>|
| <span data-ttu-id="13009-159">编辑评估策略</span><span class="sxs-lookup"><span data-stu-id="13009-159">Edit evaluation policy</span></span> | <span data-ttu-id="13009-160">远程和接受域角色;安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="13009-160">Remote and Accepted Domains role; Security admin role</span></span> |
| <span data-ttu-id="13009-161">删除评估策略</span><span class="sxs-lookup"><span data-stu-id="13009-161">Delete evaluation policy</span></span> | <span data-ttu-id="13009-162">远程和接受域角色;安全管理员角色</span><span class="sxs-lookup"><span data-stu-id="13009-162">Remote and Accepted Domains role; Security admin role</span></span> |
|<span data-ttu-id="13009-163">查看评估报告</span><span class="sxs-lookup"><span data-stu-id="13009-163">View evaluation report</span></span> | <span data-ttu-id="13009-164">安全管理员角色或安全读者角色</span><span class="sxs-lookup"><span data-stu-id="13009-164">Security admin role OR Security reader role</span></span>|

### <a name="enhanced-filtering"></a><span data-ttu-id="13009-165">增强的筛选</span><span class="sxs-lookup"><span data-stu-id="13009-165">Enhanced filtering</span></span>

<span data-ttu-id="13009-166">您的 Exchange Online Protection 策略（如批量和垃圾邮件保护）将保持不变。</span><span class="sxs-lookup"><span data-stu-id="13009-166">Your Exchange Online Protection policies, such as bulk and spam protection, will remain the same.</span></span> <span data-ttu-id="13009-167">邮件传递也将保持不变。</span><span class="sxs-lookup"><span data-stu-id="13009-167">Message delivery will also remain the same.</span></span> <span data-ttu-id="13009-168">但是，此评估会对连接器启用增强型筛选，这将影响您的邮件流和 Exchange Online Protection 策略，除非被绕过。</span><span class="sxs-lookup"><span data-stu-id="13009-168">However, the evaluation turns on enhanced filtering for connectors, which will impact your mailflow and Exchange Online Protection policies unless bypassed.</span></span>

<span data-ttu-id="13009-169">连接器的增强型筛选功能将允许租户使用反欺骗保护。</span><span class="sxs-lookup"><span data-stu-id="13009-169">Enhanced filtering for connectors will allow tenants to use anti-spoofing protection.</span></span> <span data-ttu-id="13009-170">如果使用的是电子邮件安全网关 (ESG) 而无需启用对连接器的增强筛选，则不支持反欺骗。</span><span class="sxs-lookup"><span data-stu-id="13009-170">Anti-spoofing is not supported if you’re using an email security gateway (ESG) without having turned on Enhanced filtering for connectors.</span></span>

### <a name="urls"></a><span data-ttu-id="13009-171">URL</span><span class="sxs-lookup"><span data-stu-id="13009-171">URLs</span></span>

<span data-ttu-id="13009-172">在邮件流过程中，将触发 Url。</span><span class="sxs-lookup"><span data-stu-id="13009-172">URLs will be detonated during mail flow.</span></span> <span data-ttu-id="13009-173">如果不想让特定 Url 触发，请相应地管理允许的 Url 列表。</span><span class="sxs-lookup"><span data-stu-id="13009-173">If you don’t want specific URLs detonated, manage your list of allowed URLs appropriately.</span></span> <span data-ttu-id="13009-174">有关详细信息，请参阅 [管理租户允许/阻止列表中的 url](tenant-allow-block-list.md) 。</span><span class="sxs-lookup"><span data-stu-id="13009-174">See [Manage URLs in the Tenant Allow/Block List](tenant-allow-block-list.md) for details.</span></span>

<span data-ttu-id="13009-175">电子邮件正文中的 URL 链接不会换行，以减少客户影响。</span><span class="sxs-lookup"><span data-stu-id="13009-175">URL links in the email message bodies won't wrap, to lessen customer impact.</span></span>

### <a name="email-routing"></a><span data-ttu-id="13009-176">电子邮件路由</span><span class="sxs-lookup"><span data-stu-id="13009-176">Email routing</span></span>

<span data-ttu-id="13009-177">您需要准备设置您的电子邮件当前的路由方式所需的相应详细信息，包括路由邮件的入站连接器的名称。</span><span class="sxs-lookup"><span data-stu-id="13009-177">You need to prepare the corresponding details that you will need to set up how your email is currently routed, including the name of the inbound connector that routes your mail.</span></span> <span data-ttu-id="13009-178">如果只使用 Exchange Online Protection，则不会有连接器。 [了解有关邮件流和电子邮件路由的信息](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span><span class="sxs-lookup"><span data-stu-id="13009-178">If you are just using Exchange Online Protection, you won’t have a connector. [Learn about mail flow and email routing](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)</span></span>

<span data-ttu-id="13009-179">支持的电子邮件路由方案包括：</span><span class="sxs-lookup"><span data-stu-id="13009-179">Supported email routing scenarios include:</span></span>

- <span data-ttu-id="13009-180">**第三方合作伙伴和/或本地服务提供商**：要评估的入站连接器使用第三方提供程序，或使用的是本地电子邮件安全解决方案的解决方案。</span><span class="sxs-lookup"><span data-stu-id="13009-180">**Third-party partner and/or on-premises service provider**: The inbound connector that you want to evaluate uses a third-party provider and/or you’re using a solution for email security on-premises.</span></span>  
- <span data-ttu-id="13009-181">**仅 Microsoft Exchange Online Protection**：要评估的租户使用 Office 365 for email Security 和 Mail EXCHANGE (MX) 记录指向 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="13009-181">**Microsoft Exchange Online Protection only**: The tenant that you want to evaluate uses Office 365 for email security and the Mail Exchange (MX) record points to Microsoft.</span></span>

### <a name="email-security-gateway"></a><span data-ttu-id="13009-182">电子邮件安全网关</span><span class="sxs-lookup"><span data-stu-id="13009-182">Email security gateway</span></span>

<span data-ttu-id="13009-183">如果使用的是第三方电子邮件安全网关 (ESG) ，则需要知道提供商的名称。</span><span class="sxs-lookup"><span data-stu-id="13009-183">If you’re using a third-party email security gateway (ESG), you’ll need to know the provider’s name.</span></span> <span data-ttu-id="13009-184">如果您使用的是 ESG 内部部署或不受支持的供应商，您需要知道这些设备 (es) 的公用 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="13009-184">If you’re using an ESG on-premises or non-supported vendors, you’ll need to know the public IP address(es) for the devices.</span></span>

<span data-ttu-id="13009-185">支持的第三方合作伙伴包括：</span><span class="sxs-lookup"><span data-stu-id="13009-185">Supported third-party partners include:</span></span>

- <span data-ttu-id="13009-186">Barracuda</span><span class="sxs-lookup"><span data-stu-id="13009-186">Barracuda</span></span>
- <span data-ttu-id="13009-187">IronPort</span><span class="sxs-lookup"><span data-stu-id="13009-187">IronPort</span></span>
- <span data-ttu-id="13009-188">Mimecast</span><span class="sxs-lookup"><span data-stu-id="13009-188">Mimecast</span></span>
- <span data-ttu-id="13009-189">Proofpoint</span><span class="sxs-lookup"><span data-stu-id="13009-189">Proofpoint</span></span>
- <span data-ttu-id="13009-190">Sophos</span><span class="sxs-lookup"><span data-stu-id="13009-190">Sophos</span></span>
- <span data-ttu-id="13009-191">Symantec</span><span class="sxs-lookup"><span data-stu-id="13009-191">Symantec</span></span>
- <span data-ttu-id="13009-192">趋势微</span><span class="sxs-lookup"><span data-stu-id="13009-192">Trend Micro</span></span>

### <a name="scoping"></a><span data-ttu-id="13009-193">界定访问权限</span><span class="sxs-lookup"><span data-stu-id="13009-193">Scoping</span></span>

<span data-ttu-id="13009-194">您将能够将评估范围限定为入站连接器。</span><span class="sxs-lookup"><span data-stu-id="13009-194">You will be able to scope the evaluation to an inbound connector.</span></span> <span data-ttu-id="13009-195">如果未配置任何连接器，则评估范围将允许管理员从租户中的任何用户收集数据，以评估 Office 365 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="13009-195">If there's no connector configured, then the evaluation scope will allow admins to gather data from any user in your tenant to evaluate Defender for Office 365.</span></span>

## <a name="get-started-with-the-evaluation"></a><span data-ttu-id="13009-196">评估入门</span><span class="sxs-lookup"><span data-stu-id="13009-196">Get started with the evaluation</span></span>

<span data-ttu-id="13009-197">在 Office 365 安全性 & 合规性中心 (https://protection.office.com/homepage) 从三个接入点中查找 Microsoft Defender For office 365 评估设置卡：</span><span class="sxs-lookup"><span data-stu-id="13009-197">Find the Microsoft Defender for Office 365 evaluation set-up card in the Office 365 Security & Compliance center (https://protection.office.com/homepage) from three access points:</span></span>

- <span data-ttu-id="13009-198">> 仪表板的威胁管理</span><span class="sxs-lookup"><span data-stu-id="13009-198">Threat management > Dashboard</span></span>
- <span data-ttu-id="13009-199">威胁管理 > 策略</span><span class="sxs-lookup"><span data-stu-id="13009-199">Threat management > Policy</span></span>
- <span data-ttu-id="13009-200">报表 > 仪表板</span><span class="sxs-lookup"><span data-stu-id="13009-200">Reports > Dashboard</span></span>

## <a name="setting-up-the-evaluation"></a><span data-ttu-id="13009-201">设置评估</span><span class="sxs-lookup"><span data-stu-id="13009-201">Setting up the evaluation</span></span>

<span data-ttu-id="13009-202">启动评估的设置流程后，您将获得两个路由选项。</span><span class="sxs-lookup"><span data-stu-id="13009-202">Once you start the set-up flow for your evaluation, you'll be given two routing options.</span></span> <span data-ttu-id="13009-203">根据组织的邮件路由设置和评估需求，您可以选择使用的是第三方和/或本地服务提供商还是仅使用 Microsoft Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="13009-203">Depending on your organization’s mail routing setup and evaluation needs, you can select whether you are using a third-party and/or on-premises service provider or only Microsoft Exchange Online.</span></span>

- <span data-ttu-id="13009-204">如果使用的是第三方合作伙伴和/或本地服务提供商，则需要从下拉菜单中选择供应商的名称。</span><span class="sxs-lookup"><span data-stu-id="13009-204">If you are using a third-party partner and/or on-premises service provider, you'll need to select the name of the vendor from the drop-down menu.</span></span> <span data-ttu-id="13009-205">提供其他与连接器有关的详细信息。</span><span class="sxs-lookup"><span data-stu-id="13009-205">Provide the other connector-related details.</span></span>

- <span data-ttu-id="13009-206">如果 MX 记录指向 Microsoft 并拥有 Exchange Online 邮箱，请选择 "Microsoft Exchange Online"。</span><span class="sxs-lookup"><span data-stu-id="13009-206">Select Microsoft Exchange Online if the MX record points to Microsoft and you have an Exchange Online mailbox.</span></span>

<span data-ttu-id="13009-207">查看您的设置并根据需要进行编辑。</span><span class="sxs-lookup"><span data-stu-id="13009-207">Review your settings and edit them if necessary.</span></span> <span data-ttu-id="13009-208">然后，选择 " **创建评估**"。</span><span class="sxs-lookup"><span data-stu-id="13009-208">Then, select **Create evaluation**.</span></span> <span data-ttu-id="13009-209">您应该会收到一条确认消息，指示您的设置已完成。</span><span class="sxs-lookup"><span data-stu-id="13009-209">You should get a confirmation message to indicate that your set-up is complete.</span></span>

<span data-ttu-id="13009-210">Microsoft Defender for Office 365 评估报告每天生成一次。</span><span class="sxs-lookup"><span data-stu-id="13009-210">Your Microsoft Defender for Office 365 evaluation report is generated once per day.</span></span> <span data-ttu-id="13009-211">可能需要长达24小时才能填充数据。</span><span class="sxs-lookup"><span data-stu-id="13009-211">It may take up to 24 hours for the data to populate.</span></span>

### <a name="exchange-rules-optional"></a><span data-ttu-id="13009-212">Exchange 规则 (可选) </span><span class="sxs-lookup"><span data-stu-id="13009-212">Exchange rules (optional)</span></span>

<span data-ttu-id="13009-213">如果您有一个现有的网关，则可能需要绕过筛选，因为它将激活连接器的增强筛选并更改传入发件人的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="13009-213">If you have an existing gateway, you might want to bypass filtering because it will activate enhanced filtering for connectors and alter the incoming sender IP address.</span></span> <span data-ttu-id="13009-214">若要绕过，请导航到 Exchange 管理中心并创建 SCL-1 (的策略（如果尚没有) ）。</span><span class="sxs-lookup"><span data-stu-id="13009-214">To bypass, navigate to the Exchange admin center and create a policy of SCL -1 (if you don’t already have one).</span></span> <span data-ttu-id="13009-215">有关规则组件及其工作方式的详细信息，请参阅 Mail flow rules (transport rules) in Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="13009-215">For details on the rule components and how they work, see Mail flow rules (transport rules) in Exchange Online.</span></span>

## <a name="evaluate-capabilities"></a><span data-ttu-id="13009-216">评估功能</span><span class="sxs-lookup"><span data-stu-id="13009-216">Evaluate capabilities</span></span>

<span data-ttu-id="13009-217">生成评估报告后，请参阅组织中的电子邮件和协作工作区中确定了多少高级威胁链接、高级威胁附件和潜在 impersonations。</span><span class="sxs-lookup"><span data-stu-id="13009-217">After the evaluation report has been generated, see how many advanced threat links, advanced threat attachments, and potential impersonations were identified in the emails and collaboration workspaces in your organization.</span></span>  

<span data-ttu-id="13009-218">试用期到期后，你可以继续访问90天的报告。</span><span class="sxs-lookup"><span data-stu-id="13009-218">Once the trial has expired, you can continue to access the report for 90 days.</span></span> <span data-ttu-id="13009-219">但是，它不会收集任何详细信息。</span><span class="sxs-lookup"><span data-stu-id="13009-219">However, it won’t collect any more information.</span></span> <span data-ttu-id="13009-220">如果你想要在试用期过期后继续使用 Microsoft Defender for Office 365，请确保 [购买付费订阅 For Microsoft defender For office 365 (Plan 2) ](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)。</span><span class="sxs-lookup"><span data-stu-id="13009-220">If you want to continue using Microsoft Defender for Office 365 after your trial has expired, make sure you [buy a paid subscription for Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).</span></span>

<span data-ttu-id="13009-221">你可以转到 " **设置** " 以更新你的路由或在任何时候关闭评估。</span><span class="sxs-lookup"><span data-stu-id="13009-221">You can go to **Settings** to update your routing or turn off your evaluation at any time.</span></span> <span data-ttu-id="13009-222">但是，如果决定在关闭后继续进行评估，则需要再次执行相同的设置过程。</span><span class="sxs-lookup"><span data-stu-id="13009-222">However, you need to go through the same set-up process again should you decide to continue your evaluation after having turned it off.</span></span>

## <a name="provide-feedback"></a><span data-ttu-id="13009-223">提供反馈</span><span class="sxs-lookup"><span data-stu-id="13009-223">Provide feedback</span></span>

<span data-ttu-id="13009-224">你的反馈有助于我们更好地保护你的环境免受高级攻击。</span><span class="sxs-lookup"><span data-stu-id="13009-224">Your feedback helps us get better at protecting your environment from advanced attacks.</span></span> <span data-ttu-id="13009-225">分享产品功能和评估结果的体验和印象。</span><span class="sxs-lookup"><span data-stu-id="13009-225">Share your experience and impressions of product capabilities and evaluation results.</span></span>

<span data-ttu-id="13009-226">选择 " **提供反馈** "，让我们知道你的想法。</span><span class="sxs-lookup"><span data-stu-id="13009-226">Select **Give feedback** to let us know what you think.</span></span>
