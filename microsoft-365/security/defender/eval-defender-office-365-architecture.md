---
title: 查看 Microsoft Defender 的体系结构要求和规划Office 365、构建、构建和设计框架
description: Microsoft Defender for Office 365 for Microsoft 365 Defender 的技术图表将帮助你在构建试用实验室或Microsoft 365环境之前了解 microsoft Defender 中的身份。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 15c84921dcfb4644241cf83ce4ffb6403180b9d4
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457675"
---
# <a name="review-microsoft-defender-for-office-365-architecture-requirements-and-key-concepts"></a><span data-ttu-id="9e81a-103">查看 Microsoft Defender Office 365体系结构要求和关键概念</span><span class="sxs-lookup"><span data-stu-id="9e81a-103">Review Microsoft Defender for Office 365 architecture requirements and key concepts</span></span>


<span data-ttu-id="9e81a-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9e81a-104">**Applies to:**</span></span>
- <span data-ttu-id="9e81a-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e81a-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="9e81a-106">本文是设置 Microsoft Defender for Office 365 评估环境过程中的第 1 步（第[3](eval-defender-office-365-overview.md) Office 365）。</span><span class="sxs-lookup"><span data-stu-id="9e81a-106">This article is [Step 1 of 3](eval-defender-office-365-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="9e81a-107">有关此过程详细信息，请参阅 [概述文章](eval-defender-office-365-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="9e81a-107">For more information about this process, see the [overview article](eval-defender-office-365-overview.md).</span></span>

<span data-ttu-id="9e81a-108">在启用 Defender for Office 365，请确保你了解体系结构并满足要求。</span><span class="sxs-lookup"><span data-stu-id="9e81a-108">Before enabling Defender for Office 365, be sure you understand the architecture and can meet the requirements.</span></span> <span data-ttu-id="9e81a-109">本文介绍您的环境必须满足的体系结构、关键概念Exchange Online先决条件。</span><span class="sxs-lookup"><span data-stu-id="9e81a-109">This article describes the architecture, key concepts, and the prerequisites that your Exchange Online environment must meet.</span></span>

## <a name="understand-the-architecture"></a><span data-ttu-id="9e81a-110">了解体系结构</span><span class="sxs-lookup"><span data-stu-id="9e81a-110">Understand the architecture</span></span>

<span data-ttu-id="9e81a-111">下图说明了 Microsoft Defender for Office的基准体系结构，其中可以包含第三方 SMTP 网关或本地集成。</span><span class="sxs-lookup"><span data-stu-id="9e81a-111">The following diagram illustrates baseline architecture for Microsoft Defender for Office which can include a third-party SMTP gateway or on-premises integration.</span></span> <span data-ttu-id="9e81a-112">混合共存方案 (，即生产邮箱为内部部署和联机) 配置需要更复杂的配置，本文或评估指南中未介绍。</span><span class="sxs-lookup"><span data-stu-id="9e81a-112">Hybrid coexistence scenarios (i.e. production mailboxes are both on-premise and online) require more complex configurations and are not covered in this article or evaluation guidance.</span></span>

![Microsoft Defender for Office 365](../../media/defender/m365-defender-office-architecture.png)

<span data-ttu-id="9e81a-114">下表描述了此图。</span><span class="sxs-lookup"><span data-stu-id="9e81a-114">The following table describes this illustration.</span></span>

|<span data-ttu-id="9e81a-115">呼叫</span><span class="sxs-lookup"><span data-stu-id="9e81a-115">Call-out</span></span>  |<span data-ttu-id="9e81a-116">说明</span><span class="sxs-lookup"><span data-stu-id="9e81a-116">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="9e81a-117">1</span><span class="sxs-lookup"><span data-stu-id="9e81a-117">1</span></span>     | <span data-ttu-id="9e81a-118">外部发件人的主机服务器通常会对 MX 记录执行公共 DNS 查找，该记录为目标服务器提供中继邮件的目标服务器。</span><span class="sxs-lookup"><span data-stu-id="9e81a-118">The host server for the external sender typically performs a public DNS lookup for an MX record which provides the target server to relay the message.</span></span>  <span data-ttu-id="9e81a-119">此引用可以是直接Exchange Online (EXO) 或已配置为针对 EXO 中继的 SMTP 网关。</span><span class="sxs-lookup"><span data-stu-id="9e81a-119">This referral can either be Exchange Online (EXO) directly or an SMTP gateway that has been configured to relay against EXO.</span></span>  |
|<span data-ttu-id="9e81a-120">2</span><span class="sxs-lookup"><span data-stu-id="9e81a-120">2</span></span>     | <span data-ttu-id="9e81a-121">Exchange Online Protection协商并验证入站连接，并检查邮件头和内容以确定需要其他哪些策略、标记或处理。</span><span class="sxs-lookup"><span data-stu-id="9e81a-121">Exchange Online Protection negotiates and validates the inbound connection and inspects the message headers and content to determine what additional policies, tagging, or processing is required.</span></span>  |
|<span data-ttu-id="9e81a-122">3</span><span class="sxs-lookup"><span data-stu-id="9e81a-122">3</span></span>     | <span data-ttu-id="9e81a-123">Exchange Online与 Microsoft Defender for Office 365集成，以提供更高级的威胁防护、缓解和修正。</span><span class="sxs-lookup"><span data-stu-id="9e81a-123">Exchange Online integrates with Microsoft Defender for Office 365 to offer more advanced threat protection, mitigation, and remediation.</span></span> |
|<span data-ttu-id="9e81a-124">4 </span><span class="sxs-lookup"><span data-stu-id="9e81a-124">4</span></span>     | <span data-ttu-id="9e81a-125">非恶意邮件、阻止邮件或隔离邮件将在 EXO 中处理并传递到收件人，其中评估并触发了与垃圾邮件、邮箱规则或其他设置相关的用户首选项。</span><span class="sxs-lookup"><span data-stu-id="9e81a-125">A message that is not malicious, blocked, or quarantined is processed and delivered to the recipient in EXO where user preferences related to junk mail, mailbox rules, or other settings are evaluated and triggered.</span></span> |
|<span data-ttu-id="9e81a-126">5 </span><span class="sxs-lookup"><span data-stu-id="9e81a-126">5</span></span>     | <span data-ttu-id="9e81a-127">可以使用 Azure AD 连接启用与本地 Active Directory 的集成，以同步和预配启用邮件的对象和帐户，Azure Active Directory并最终Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="9e81a-127">Integration with on-premises Active Directory can be enabled using Azure AD Connect to synchronize and provision mail-enabled objects and accounts to Azure Active Directory and ultimately Exchange Online.</span></span> |
|<span data-ttu-id="9e81a-128">6 </span><span class="sxs-lookup"><span data-stu-id="9e81a-128">6</span></span>     | <span data-ttu-id="9e81a-129">在集成本地环境时，强烈建议使用 Exchange 服务器对与邮件相关的属性、设置和配置进行受支持的管理</span><span class="sxs-lookup"><span data-stu-id="9e81a-129">When integrating an on-premises environment, it is strongly encouraged to use an Exchange server for supported management and administration of mail related attributes, settings, and configurations</span></span> |
|<span data-ttu-id="9e81a-130">7 </span><span class="sxs-lookup"><span data-stu-id="9e81a-130">7</span></span>     | <span data-ttu-id="9e81a-131">Microsoft Defender for Office 365 XDR Microsoft 365 Defender共享信号，以扩展 XDR (响应) 。</span><span class="sxs-lookup"><span data-stu-id="9e81a-131">Microsoft Defender for Office 365 shares signals to Microsoft 365 Defender for extended detection and response (XDR).</span></span>|

<span data-ttu-id="9e81a-132">本地集成很常见，但是可选的。</span><span class="sxs-lookup"><span data-stu-id="9e81a-132">On-premises integration is common but optional.</span></span> <span data-ttu-id="9e81a-133">如果你的环境是仅云环境，本指南也将适合你。</span><span class="sxs-lookup"><span data-stu-id="9e81a-133">If your environment is cloud-only this guidance will also work for you.</span></span>

## <a name="understand-key-concepts"></a><span data-ttu-id="9e81a-134">了解关键概念</span><span class="sxs-lookup"><span data-stu-id="9e81a-134">Understand key concepts</span></span>

<span data-ttu-id="9e81a-135">下表确定了在评估、配置和部署 MDO 时必须了解的重要概念。</span><span class="sxs-lookup"><span data-stu-id="9e81a-135">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying MDO.</span></span>


|<span data-ttu-id="9e81a-136">概念</span><span class="sxs-lookup"><span data-stu-id="9e81a-136">Concept</span></span>  |<span data-ttu-id="9e81a-137">说明</span><span class="sxs-lookup"><span data-stu-id="9e81a-137">Description</span></span> |<span data-ttu-id="9e81a-138">详细信息</span><span class="sxs-lookup"><span data-stu-id="9e81a-138">More information</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="9e81a-139">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9e81a-139">Exchange Online Protection</span></span>      |    <span data-ttu-id="9e81a-140">Exchange Online Protection (EOP) 是基于云的筛选服务，可帮助保护组织免受垃圾邮件和恶意软件电子邮件的攻击。</span><span class="sxs-lookup"><span data-stu-id="9e81a-140">Exchange Online Protection (EOP) is the cloud-based filtering service that helps protect your organization against spam and malware emails.</span></span> <span data-ttu-id="9e81a-141">EOP 包含在所有Microsoft 365许可证中，其中包括Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="9e81a-141">EOP is included in all Microsoft 365 licenses which include Exchange Online.</span></span>     |   [<span data-ttu-id="9e81a-142">Exchange Online Protection 概述</span><span class="sxs-lookup"><span data-stu-id="9e81a-142">Exchange Online Protection overview</span></span>](../office-365-security/exchange-online-protection-overview.md)      |
|<span data-ttu-id="9e81a-143">反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="9e81a-143">Anti-malware protection</span></span>     |    <span data-ttu-id="9e81a-144">在 EXO 中拥有邮箱的组织将自动受到恶意软件的攻击。</span><span class="sxs-lookup"><span data-stu-id="9e81a-144">Organizations with mailboxes in EXO are automatically protected against malware.</span></span>     |  [<span data-ttu-id="9e81a-145">EOP 中的反恶意软件保护</span><span class="sxs-lookup"><span data-stu-id="9e81a-145">Anti-malware protection in EOP</span></span>](../office-365-security/anti-malware-protection.md)       |
|<span data-ttu-id="9e81a-146">反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="9e81a-146">Anti-spam protection</span></span>     |   <span data-ttu-id="9e81a-147">在 EXO 中拥有邮箱的组织会自动受到垃圾邮件和垃圾邮件策略的保护。</span><span class="sxs-lookup"><span data-stu-id="9e81a-147">Organizations with mailboxes in EXO are automatically protected against junk mail and spam policies.</span></span>      |  [<span data-ttu-id="9e81a-148">EOP 中的反垃圾邮件保护</span><span class="sxs-lookup"><span data-stu-id="9e81a-148">Anti-spam protection in EOP</span></span>](../office-365-security/anti-spam-protection.md)       |
|<span data-ttu-id="9e81a-149">防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="9e81a-149">Anti-phishing protection</span></span> |  <span data-ttu-id="9e81a-150">MDO 提供与网络钓鱼、网络钓鱼、勒索软件和其他恶意活动相关的更高级防钓鱼保护。</span><span class="sxs-lookup"><span data-stu-id="9e81a-150">MDO offers more advanced anti-phishing  protection related to spear phishing, whaling, ransomware, and other malicious activities.</span></span>   | [<span data-ttu-id="9e81a-151">Microsoft Defender for Office 365 中的其他反网络钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="9e81a-151">Additional anti-phishing protection in Microsoft Defender for Office 365</span></span>](../office-365-security/anti-phishing-protection.md)   |
|<span data-ttu-id="9e81a-152">防欺骗保护</span><span class="sxs-lookup"><span data-stu-id="9e81a-152">Anti-spoofing protection</span></span>     |   <span data-ttu-id="9e81a-153">EOP 包括可帮助保护组织免受欺骗 (伪造) 攻击的功能。</span><span class="sxs-lookup"><span data-stu-id="9e81a-153">EOP includes features to help protect your organization from spoofed (forged) senders.</span></span>      |   [<span data-ttu-id="9e81a-154">EOP 中的防欺骗防护</span><span class="sxs-lookup"><span data-stu-id="9e81a-154">Anti-spoofing protection in EOP</span></span>](../office-365-security/anti-spoofing-protection.md)      |
|<span data-ttu-id="9e81a-155">安全附件</span><span class="sxs-lookup"><span data-stu-id="9e81a-155">Safe attachments</span></span>     |   <span data-ttu-id="9e81a-156">保险箱附件通过使用虚拟环境在电子邮件中检查和"触发"附件，然后再传递，提供一层额外的保护。</span><span class="sxs-lookup"><span data-stu-id="9e81a-156">Safe Attachments provides an additional layer of protection by using a virtual environment to check and "detonate" attachments in email messages before they are delivered.</span></span>      |   [<span data-ttu-id="9e81a-157">保险箱Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="9e81a-157">Safe Attachments in Microsoft Defender for Office 365</span></span>](../office-365-security/safe-attachments.md)      |
|<span data-ttu-id="9e81a-158">保险箱、SharePoint、OneDrive和Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9e81a-158">Safe attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>     |    <span data-ttu-id="9e81a-159">此外，保险箱、SharePoint、OneDrive 和 Microsoft Teams 的附件为已上载到云存储存储库的文件提供额外的保护层。</span><span class="sxs-lookup"><span data-stu-id="9e81a-159">In addition, Safe Attachments for SharePoint, OneDrive, and Microsoft Teams offers an additional layer of protection for files that have been uploaded to cloud storage repositories.</span></span>     |  [<span data-ttu-id="9e81a-160">用于 SharePoint、OneDrive 和 Microsoft Teams 的安全附件</span><span class="sxs-lookup"><span data-stu-id="9e81a-160">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](../office-365-security/mdo-for-spo-odb-and-teams.md)       |
|<span data-ttu-id="9e81a-161">安全链接</span><span class="sxs-lookup"><span data-stu-id="9e81a-161">Safe Links</span></span>     | <span data-ttu-id="9e81a-162">保险箱链接是一项功能，在入站电子邮件中提供 URL 扫描和重写，并提供在传递或单击链接之前验证这些链接的功能。</span><span class="sxs-lookup"><span data-stu-id="9e81a-162">Safe Links is a feature that provides URL scanning and rewriting within inbound email messages and offers verification of those links before they are delivered or clicked.</span></span>        |   [<span data-ttu-id="9e81a-163">保险箱Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="9e81a-163">Safe Links in Microsoft Defender for Office 365</span></span>](../office-365-security/safe-links.md)      |
|    |         |         |

<span data-ttu-id="9e81a-164">有关 Microsoft Defender for Office 中包含的功能的更多详细信息，请参阅[Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="9e81a-164">For more detailed information about the capabilities included with Microsoft Defender for Office, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

## <a name="review-architecture-requirements"></a><span data-ttu-id="9e81a-165">查看体系结构要求</span><span class="sxs-lookup"><span data-stu-id="9e81a-165">Review architecture requirements</span></span>
<span data-ttu-id="9e81a-166">成功的 MDO 评估或生产试点需要满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="9e81a-166">A successful MDO evaluation or production pilot assumes the following pre-requisites:</span></span>
- <span data-ttu-id="9e81a-167">所有收件人邮箱当前都处于Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="9e81a-167">All your recipient mailboxes are currently in Exchange Online.</span></span>
- <span data-ttu-id="9e81a-168">公共 MX 记录直接解析为 EOP 或第三方 SMTP 网关，然后直接将入站外部电子邮件中继到 EOP。</span><span class="sxs-lookup"><span data-stu-id="9e81a-168">Your public MX record resolves directly to EOP or a third-party SMTP gateway that then relays inbound external email directly to EOP.</span></span>
- <span data-ttu-id="9e81a-169">主要电子邮件域在 *电子邮件中配置为* Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="9e81a-169">Your primary email domain is configured as *authoritative* in Exchange Online.</span></span>
- <span data-ttu-id="9e81a-170">您已成功部署和配置基于目录的边缘阻止 (DBEB *) 进行* 配置。</span><span class="sxs-lookup"><span data-stu-id="9e81a-170">You successfully deployed and configured *Directory Based Edge Blocking* (DBEB) as appropriate.</span></span> <span data-ttu-id="9e81a-171">有关详细信息，请参阅[使用基于目录的Edge 阻止拒绝向无效收件人的发送邮件](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。</span><span class="sxs-lookup"><span data-stu-id="9e81a-171">For more information, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e81a-172">如果这些要求不适用或你仍在混合共存方案中，则 Microsoft Defender for Office 365 评估可能需要更复杂的或高级配置，而本指南未完全涵盖这些配置。</span><span class="sxs-lookup"><span data-stu-id="9e81a-172">If these requirements are not applicable or you are still in a hybrid coexistence scenario, then a Microsoft Defender for Office 365 evaluation can require more complex or advanced configurations which are not fully covered in this guidance.</span></span>

## <a name="siem-integration"></a><span data-ttu-id="9e81a-173">SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="9e81a-173">SIEM integration</span></span>

<span data-ttu-id="9e81a-174">你可以将 Microsoft Defender for Office 365与 Azure Sentinel 集成，以更全面的分析整个组织的安全事件，并生成有效且即时响应的手册。</span><span class="sxs-lookup"><span data-stu-id="9e81a-174">You can integrate Microsoft Defender for Office 365 with Azure Sentinel to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span> <span data-ttu-id="9e81a-175">有关详细信息，请参阅连接[Microsoft Defender for Office 365 警报](/azure/sentinel/connect-office-365-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="9e81a-175">For more information, see [Connect alerts from Microsoft Defender for Office 365](/azure/sentinel/connect-office-365-advanced-threat-protection).</span></span>

<span data-ttu-id="9e81a-176">Microsoft Defender for Office 365 还可以集成到其他安全信息和事件管理 (SIEM) 解决方案（使用 Office 365[活动管理 API）。](/office/office-365-management-api/office-365-management-activity-api-reference)</span><span class="sxs-lookup"><span data-stu-id="9e81a-176">Microsoft Defender for Office 365 can also be integrated into other Security Information and Event Management (SIEM) solutions using the [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9e81a-177">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9e81a-177">Next steps</span></span>

<span data-ttu-id="9e81a-178">步骤 2/3：[启用评估](eval-defender-office-365-enable-eval.md)环境 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="9e81a-178">Step 2 of 3: [Enable the evaluation environment Microsoft Defender for Office 365](eval-defender-office-365-enable-eval.md)</span></span>

<span data-ttu-id="9e81a-179">返回到评估 Microsoft [Defender](eval-defender-office-365-overview.md) for Office 365</span><span class="sxs-lookup"><span data-stu-id="9e81a-179">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="9e81a-180">返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9e81a-180">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span> 

