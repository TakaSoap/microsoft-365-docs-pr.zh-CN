---
title: Office 365 高级威胁防护
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Office 365 高级威胁防护包括安全附件、安全链接、高级反钓鱼工具、报告工具和威胁智能功能。
ms.openlocfilehash: 8acf38cc61f2789c407a80200b97269043bab95e
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600513"
---
# <a name="office-365-advanced-threat-protection-atp"></a><span data-ttu-id="2c532-103">Office 365 高级威胁防护 (ATP)</span><span class="sxs-lookup"><span data-stu-id="2c532-103">Office 365 Advanced Threat Protection (ATP)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> <span data-ttu-id="2c532-104">本文适用于拥有 [Office 365 高级威胁防护](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)的企业客户。</span><span class="sxs-lookup"><span data-stu-id="2c532-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="2c532-105">如果你使用的是 Outlook.com、Microsoft 365 家庭版或 Microsoft 365 个人版，并且正在查找有关 Outlook 中安全链接或安全附件的信息，请参阅[适用于 Microsoft 365 订阅者的高级 Outlook.com 安全机制](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="2c532-105">If you are using Outlook.com, Microsoft 365 Family, or Microsoft 365 Personal, and you're looking for information about Safe Links or Safe Attachments in Outlook, see [Advanced Outlook.com security for Microsoft 365 subscribers](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="2c532-106">Office 365 高级威胁防护 (ATP) 可保护你的组织免受电子邮件、链接 (URL) 和协作工具带来的恶意威胁。</span><span class="sxs-lookup"><span data-stu-id="2c532-106">Office 365 Advanced Threat Protection (ATP) safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> <span data-ttu-id="2c532-107">ATP 包括：</span><span class="sxs-lookup"><span data-stu-id="2c532-107">ATP includes:</span></span>

- <span data-ttu-id="2c532-108">**[威胁防护策略](#configure-atp-policies)**：定义威胁防护策略，为组织设置适当级别的保护。</span><span class="sxs-lookup"><span data-stu-id="2c532-108">**[Threat protection policies](#configure-atp-policies)**: Define threat-protection policies to set the appropriate level of protection for your organization.</span></span>

- <span data-ttu-id="2c532-109">**[报告](#view-office-365-atp-reports)**：查看实时报告，监视组织中的 ATP 性能。</span><span class="sxs-lookup"><span data-stu-id="2c532-109">**[Reports](#view-office-365-atp-reports)**: View real-time reports to monitor ATP performance in your organization.</span></span>

- <span data-ttu-id="2c532-110">**[威胁调查和响应功能](#use-threat-investigation-and-response-capabilities)**：使用前沿工具调查、理解、模拟和阻止威胁。</span><span class="sxs-lookup"><span data-stu-id="2c532-110">**[Threat investigation and response capabilities](#use-threat-investigation-and-response-capabilities)**: Use leading-edge tools to investigate, understand, simulate, and prevent threats.</span></span>

- <span data-ttu-id="2c532-111">**[自动调查和响应功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)**：节省时间和精力来调查和缓解威胁。</span><span class="sxs-lookup"><span data-stu-id="2c532-111">**[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)**: Save time and effort investigating and mitigating threats.</span></span>

## <a name="getting-started"></a><span data-ttu-id="2c532-112">开始使用</span><span class="sxs-lookup"><span data-stu-id="2c532-112">Getting Started</span></span>

<span data-ttu-id="2c532-113">如果你没有使用过 Office 365 高级威胁防护或者“*做*中学”，则可将初始 ATP 配置分解为区块、调查以及使用此文章作为参考查看报告，从而获得最佳益处。</span><span class="sxs-lookup"><span data-stu-id="2c532-113">If you're new to Office 365 Advanced Threat Protection or learn best by *doing*, you may benefit from breaking initial ATP configuration into chunks, investigating, and viewing reports using this article as a reference.</span></span> <span data-ttu-id="2c532-114">下面是逻辑早期配置块：</span><span class="sxs-lookup"><span data-stu-id="2c532-114">Here are logical early configuration chunks:</span></span>

- <span data-ttu-id="2c532-115">为所有内容的名称配置“*anti*”。</span><span class="sxs-lookup"><span data-stu-id="2c532-115">Configure everything with '*anti*' in the name.</span></span>
    - <span data-ttu-id="2c532-116">反恶意软件</span><span class="sxs-lookup"><span data-stu-id="2c532-116">anti-malware</span></span>
    - <span data-ttu-id="2c532-117">防网络钓鱼</span><span class="sxs-lookup"><span data-stu-id="2c532-117">anti-phishing</span></span>
    - <span data-ttu-id="2c532-118">反垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="2c532-118">anti-spam</span></span>
- <span data-ttu-id="2c532-119">为所有内容的名称设置“*safe*”。</span><span class="sxs-lookup"><span data-stu-id="2c532-119">Set up everything with '*safe*' in the name.</span></span>
    - <span data-ttu-id="2c532-120">安全链接</span><span class="sxs-lookup"><span data-stu-id="2c532-120">safe links</span></span>
    - <span data-ttu-id="2c532-121">安全附件</span><span class="sxs-lookup"><span data-stu-id="2c532-121">safe attachments</span></span>
- <span data-ttu-id="2c532-122">保护工作负载（例如</span><span class="sxs-lookup"><span data-stu-id="2c532-122">Defend the workloads (ex.</span></span> <span data-ttu-id="2c532-123">SharePoint Online、OneDrive 和 Teams）</span><span class="sxs-lookup"><span data-stu-id="2c532-123">SharePoint Online, OneDrive, and Teams)</span></span> 
- <span data-ttu-id="2c532-124">通过零时差自动清除进行保护</span><span class="sxs-lookup"><span data-stu-id="2c532-124">Protect with Zero-Hour auto purge</span></span>

<span data-ttu-id="2c532-125">若要做中学，请[单击此链接](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="2c532-125">To learn by doing, [click this link](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide&preserve-view=true).</span></span> 

> [!NOTE]
> <span data-ttu-id="2c532-126">ATP 有两种不同的计划类型。</span><span class="sxs-lookup"><span data-stu-id="2c532-126">ATP comes in two different Plan types.</span></span> <span data-ttu-id="2c532-127">如果你具有“实时检测”功能，则可以判断你是否拥有**计划 1**；如果具有威胁资源管理器，则可以判断是否拥有**计划 2**。</span><span class="sxs-lookup"><span data-stu-id="2c532-127">You can tell if you have **Plan 1** if you have 'Real-time Detections', and **Plan 2**, if you have Threat Explorer.</span></span> <span data-ttu-id="2c532-128">你拥有的计划会影响你将看到的工具，因此请确保在学习过程中了解自己的计划。</span><span class="sxs-lookup"><span data-stu-id="2c532-128">The Plan you have influences the tools you will see, so be certain that you're aware of your Plan as you learn.</span></span>

## <a name="office-365-atp-plan-1-and-plan-2"></a><span data-ttu-id="2c532-129">Office 365 ATP 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="2c532-129">Office 365 ATP Plan 1 and Plan 2</span></span>

<span data-ttu-id="2c532-130">下表概括了每个计划中包含的内容。</span><span class="sxs-lookup"><span data-stu-id="2c532-130">The following table summarizes what's included in each plan.</span></span>

****

|<span data-ttu-id="2c532-131">Office 365 ATP 计划 1</span><span class="sxs-lookup"><span data-stu-id="2c532-131">Office 365 ATP Plan 1</span></span>|<span data-ttu-id="2c532-132">Office 365 ATP 计划 2</span><span class="sxs-lookup"><span data-stu-id="2c532-132">Office 365 ATP Plan 2</span></span>|
|---|---|
|<br/><span data-ttu-id="2c532-133">配置、保护和检测功能：</span><span class="sxs-lookup"><span data-stu-id="2c532-133">Configuration, protection, and detection capabilities:</span></span> <ul><li>[<span data-ttu-id="2c532-134">安全附件</span><span class="sxs-lookup"><span data-stu-id="2c532-134">Safe Attachments</span></span>](atp-safe-attachments.md)</li><li>[<span data-ttu-id="2c532-135">安全链接</span><span class="sxs-lookup"><span data-stu-id="2c532-135">Safe Links</span></span>](atp-safe-links.md)</li><li>[<span data-ttu-id="2c532-136">适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP</span><span class="sxs-lookup"><span data-stu-id="2c532-136">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)</li><li>[<span data-ttu-id="2c532-137">ATP 防钓鱼保护</span><span class="sxs-lookup"><span data-stu-id="2c532-137">ATP anti-phishing protection</span></span>](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)</li><li>[<span data-ttu-id="2c532-138">实时检测</span><span class="sxs-lookup"><span data-stu-id="2c532-138">Real-time detections</span></span>](threat-explorer.md)</li></ul>|<span data-ttu-id="2c532-139">Office 365 ATP 计划 1 功能</span><span class="sxs-lookup"><span data-stu-id="2c532-139">Office 365 ATP Plan 1 capabilities</span></span><br/><span data-ttu-id="2c532-140">--- + ---</span><span class="sxs-lookup"><span data-stu-id="2c532-140">--- plus ---</span></span><br/><span data-ttu-id="2c532-141">自动化、调查、补救措施和教育功能：</span><span class="sxs-lookup"><span data-stu-id="2c532-141">Automation, investigation, remediation, and education capabilities:</span></span></li><li>[<span data-ttu-id="2c532-142">威胁跟踪器</span><span class="sxs-lookup"><span data-stu-id="2c532-142">Threat Trackers</span></span>](threat-trackers.md)</li><li>[<span data-ttu-id="2c532-143">威胁资源管理器</span><span class="sxs-lookup"><span data-stu-id="2c532-143">Threat Explorer</span></span>](threat-explorer.md)</li><li>[<span data-ttu-id="2c532-144">自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="2c532-144">Automated investigation and response</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</li><li>[<span data-ttu-id="2c532-145">攻击模拟器</span><span class="sxs-lookup"><span data-stu-id="2c532-145">Attack Simulator</span></span>](attack-simulator.md)</li></ul>|
|

- <span data-ttu-id="2c532-146">Office 365 E5、Office 365 A5、Microsoft 365 E5 安全性和 Microsoft 365 E5 中包含 Office 365 ATP 计划 2。</span><span class="sxs-lookup"><span data-stu-id="2c532-146">Office 365 ATP Plan 2 is included in Office 365 E5, Office 365 A5, Microsoft 365 E5 Security, and Microsoft 365 E5.</span></span>

- <span data-ttu-id="2c532-147">Office 365 ATP 计划 1 包含在 Microsoft 365 商业高级版中。</span><span class="sxs-lookup"><span data-stu-id="2c532-147">Office 365 ATP Plan 1 is included in Microsoft 365 Business Premium.</span></span>

- <span data-ttu-id="2c532-148">Office 365 ATP 计划 1 和 Office 365 ATP 计划 2 可各自用作特定订阅的加载项。</span><span class="sxs-lookup"><span data-stu-id="2c532-148">Office 365 ATP Plan 1 and Office 365 ATP Plan 2 are each available as an add-on for certain subscriptions.</span></span> <span data-ttu-id="2c532-149">要了解详细信息，请参阅[跨高级威胁防护 (ATP) 计划的功能可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="2c532-149">To learn more, see [Feature availability across ATP plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

- <span data-ttu-id="2c532-150">只有拥有 Microsoft 365 E5 或 Microsoft 365 E5 安全版许可证（未包括在 Office 365 ATP 计划内）的用户才能使用[安全文档](safe-docs.md)功能。</span><span class="sxs-lookup"><span data-stu-id="2c532-150">The [Safe Documents](safe-docs.md) feature is only available to users with the Microsoft 365 E5 or Microsoft 365 E5 Security licenses (not included in Office 365 ATP plans).</span></span>

- <span data-ttu-id="2c532-151">如果你当前的订阅不包括 Office 365 ATP，请[与销售人员联系以开始试用](https://go.microsoft.com/fwlink/p/?LinkId=518644)，并查看 ATP 如何为你的组织所用。</span><span class="sxs-lookup"><span data-stu-id="2c532-151">If your current subscription does not include Office 365 ATP, [contact sales to start a trial](https://go.microsoft.com/fwlink/p/?LinkId=518644), and see how ATP can work for your organization.</span></span>

## <a name="configure-atp-policies"></a><span data-ttu-id="2c532-152">配置 ATP 策略</span><span class="sxs-lookup"><span data-stu-id="2c532-152">Configure ATP policies</span></span>

<span data-ttu-id="2c532-153">借助 Office 365 ATP，你组织的安全团队可以在安全与合规中心内定义策略（依次转到[https://protection.office.com](https://protection.office.com) > “威胁管理”\*\*\*\* > “策略”\*\*\*\*），从而配置保护。</span><span class="sxs-lookup"><span data-stu-id="2c532-153">With Office 365 ATP, your organization's security team can configure protection by defining policies in the Security & Compliance Center (Go to [https://protection.office.com](https://protection.office.com) > **Threat management** > **Policy**.)</span></span>

> [!TIP]
> <span data-ttu-id="2c532-154">有关可定义的策略的快速列表，请参阅[威胁防护](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="2c532-154">For a quick list of policies to define, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="advanced-threat-protection-policies"></a><span data-ttu-id="2c532-155">高级威胁防护策略</span><span class="sxs-lookup"><span data-stu-id="2c532-155">Advanced Threat Protection Policies</span></span>

<span data-ttu-id="2c532-156">为组织定义的策略将确定预定义威胁的行为和保护级别。</span><span class="sxs-lookup"><span data-stu-id="2c532-156">The policies that are defined for your organization determine the behavior and protection level for predefined threats.</span></span> <span data-ttu-id="2c532-157">策略选项非常灵活。</span><span class="sxs-lookup"><span data-stu-id="2c532-157">Policy options are extremely flexible.</span></span> <span data-ttu-id="2c532-158">例如，组织的安全团队可以在用户、组织、收件人和域级别设置细化的威胁防护。</span><span class="sxs-lookup"><span data-stu-id="2c532-158">For example, your organization's security team can set fine-grained threat protection at the user, organization, recipient, and domain level.</span></span> <span data-ttu-id="2c532-159">定期查看策略非常重要，因为每天都会出现新的威胁和挑战。</span><span class="sxs-lookup"><span data-stu-id="2c532-159">It is important to review your policies regularly because new threats and challenges emerge daily.</span></span>

- <span data-ttu-id="2c532-160">**[安全附件](atp-safe-attachments.md)**：提供可通过检查电子邮件附件查找恶意内容来保护邮件系统的零日防护。</span><span class="sxs-lookup"><span data-stu-id="2c532-160">**[Safe Attachments](atp-safe-attachments.md)**: Provides zero-day protection to safeguard your messaging system, by checking email attachments for malicious content.</span></span> <span data-ttu-id="2c532-161">它会将无病毒/恶意软件签名的所有邮件和附件路由到特殊环境，然后使用机器学习和分析技术检测恶意意向。</span><span class="sxs-lookup"><span data-stu-id="2c532-161">It routes all messages and attachments that do not have a virus/malware signature to a special environment, and then uses machine learning and analysis techniques to detect malicious intent.</span></span> <span data-ttu-id="2c532-162">如果未找到可疑活动，邮件将转发到邮箱。</span><span class="sxs-lookup"><span data-stu-id="2c532-162">If no suspicious activity is found, the message is forwarded to the mailbox.</span></span> <span data-ttu-id="2c532-163">若要了解详细信息，请参阅[设置“安全附件”策略](set-up-atp-safe-attachments-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2c532-163">To learn more, see [Set up Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

- <span data-ttu-id="2c532-164">**[安全链接](atp-safe-links.md)**：在诸如电子邮件和 Office 文件中提供 URL 的单击时验证。</span><span class="sxs-lookup"><span data-stu-id="2c532-164">**[Safe Links](atp-safe-links.md)**: Provides time-of-click verification of URLs, for example, in emails messages and Office files.</span></span> <span data-ttu-id="2c532-165">正在进行保护并适用于邮件和 Office 环境。</span><span class="sxs-lookup"><span data-stu-id="2c532-165">Protection is ongoing and applies across your messaging and Office environment.</span></span> <span data-ttu-id="2c532-166">每次单击时都扫描链接：安全链接仍然可访问，恶意链接被动态阻止。</span><span class="sxs-lookup"><span data-stu-id="2c532-166">Links are scanned for each click: safe links remain accessible and malicious links are dynamically blocked.</span></span> <span data-ttu-id="2c532-167">若要了解详细信息，请参阅[设置“安全链接”策略](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2c532-167">To learn more, see [Set up Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

- <span data-ttu-id="2c532-168">**[用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](atp-for-spo-odb-and-teams.md)**：当用户协作和共享文件时，可通过识别和阻止工作组网站和文档库中的恶意文件来保护你的组织。</span><span class="sxs-lookup"><span data-stu-id="2c532-168">**[ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md)**: Protects your organization when users collaborate and share files, by identifying and blocking malicious files in team sites and document libraries.</span></span> <span data-ttu-id="2c532-169">有关详细信息，请参阅[开启适用于 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="2c532-169">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

- <span data-ttu-id="2c532-170">**[ATP 防钓鱼防护](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)**：检测模拟用户和内部或自定义域的尝试。</span><span class="sxs-lookup"><span data-stu-id="2c532-170">**[ATP anti-phishing protection](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)**: Detects attempts to impersonate your users and internal or custom domains.</span></span> <span data-ttu-id="2c532-171">它应用机器学习模型和高级模仿检测算法，防止钓鱼攻击。</span><span class="sxs-lookup"><span data-stu-id="2c532-171">It applies machine learning models and advanced impersonation-detection algorithms to avert phishing attacks.</span></span> <span data-ttu-id="2c532-172">若要了解详细信息，请参阅[在 Office 365 中配置 ATP 防钓鱼策略](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2c532-172">To learn more, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="view-office-365-atp-reports"></a><span data-ttu-id="2c532-173">查看 Office 365 ATP 报告</span><span class="sxs-lookup"><span data-stu-id="2c532-173">View Office 365 ATP reports</span></span>

<span data-ttu-id="2c532-174">Office 365 ATP 包含用于监视 ATP 性能的高级[报告仪表板](view-reports-for-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="2c532-174">Office 365 ATP includes an advanced [reporting dashboard](view-reports-for-atp.md) to monitor your ATP performance.</span></span> <span data-ttu-id="2c532-175">可在安全与合规中心的“**报告**” > “**仪表板**”处访问该内容。</span><span class="sxs-lookup"><span data-stu-id="2c532-175">You can access it at **Reports** > **Dashboard** in the Security & Compliance Center.</span></span>

<span data-ttu-id="2c532-176">实时更新报告，为你提供最新见解。</span><span class="sxs-lookup"><span data-stu-id="2c532-176">Reports update in real-time, providing you with the latest insights.</span></span> <span data-ttu-id="2c532-177">这些报告还提供建议并向你提醒即将面临的威胁。</span><span class="sxs-lookup"><span data-stu-id="2c532-177">These reports also provide recommendations and alert you to imminent threats.</span></span> <span data-ttu-id="2c532-178">预定义的报告包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="2c532-178">Predefined reports include the following:</span></span>

- [<span data-ttu-id="2c532-179">威胁资源管理器（或实时检测）</span><span class="sxs-lookup"><span data-stu-id="2c532-179">Threat Explorer (or real-time detections)</span></span>](threat-explorer.md)

- [<span data-ttu-id="2c532-180">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="2c532-180">Threat protection status report</span></span>](view-reports-for-atp.md#threat-protection-status-report)

- [<span data-ttu-id="2c532-181">高级威胁防护文件类型报告</span><span class="sxs-lookup"><span data-stu-id="2c532-181">Advanced Threat Protection file types report</span></span>](view-reports-for-atp.md#advanced-threat-protection-file-types-report)

- [<span data-ttu-id="2c532-182">高级威胁防护邮件处置报告</span><span class="sxs-lookup"><span data-stu-id="2c532-182">Advanced Threat Protection message disposition report</span></span>](view-reports-for-atp.md#advanced-threat-protection-message-disposition-report)

- <span data-ttu-id="2c532-183">…及更多精彩内容。</span><span class="sxs-lookup"><span data-stu-id="2c532-183">... and several more.</span></span>

## <a name="use-threat-investigation-and-response-capabilities"></a><span data-ttu-id="2c532-184">使用威胁调查和响应功能</span><span class="sxs-lookup"><span data-stu-id="2c532-184">Use threat investigation and response capabilities</span></span>

<span data-ttu-id="2c532-185">Office 365 ATP 计划 2 包括同类最佳的[威胁调查和响应工具](office-365-ti.md)，可让组织的安全团队预测、理解和防范恶意攻击。</span><span class="sxs-lookup"><span data-stu-id="2c532-185">Office 365 ATP Plan 2 includes best-of-class [threat investigation and response tools](office-365-ti.md) that enable your organization's security team to anticipate, understand, and prevent malicious attacks.</span></span>

- <span data-ttu-id="2c532-186">**[威胁跟踪器](threat-trackers.md)** 提供有关主流网络安全问题的最新智能。</span><span class="sxs-lookup"><span data-stu-id="2c532-186">**[Threat trackers](threat-trackers.md)** provide the latest intelligence on prevailing cybersecurity issues.</span></span> <span data-ttu-id="2c532-187">例如，你可以查看有关最新恶意软件的信息，并采取措施，然后将其作为组织的实际威胁。</span><span class="sxs-lookup"><span data-stu-id="2c532-187">For example, you can view information about the latest malware, and take countermeasures before it becomes an actual threat to your organization.</span></span> <span data-ttu-id="2c532-188">可用的跟踪器包括[值得注意的跟踪器](threat-trackers.md#noteworthy-trackers)、[趋势跟踪器](threat-trackers.md#trending-trackers)、[跟踪的查询](threat-trackers.md#tracked-queries)和[已保存的查询](threat-trackers.md#saved-queries)。</span><span class="sxs-lookup"><span data-stu-id="2c532-188">Available trackers include [Noteworthy trackers](threat-trackers.md#noteworthy-trackers), [Trending trackers](threat-trackers.md#trending-trackers), [Tracked queries](threat-trackers.md#tracked-queries), and [Saved queries](threat-trackers.md#saved-queries).</span></span>

- <span data-ttu-id="2c532-189">**[威胁资源管理器（或实时检测）](threat-explorer.md)** 也称为“资源管理器”，它是一种实时报表，可用于识别和分析最近的威胁。</span><span class="sxs-lookup"><span data-stu-id="2c532-189">**[Threat Explorer (or real-time detections)](threat-explorer.md)** (also referred to as Explorer) is a real-time report that allows you to identify and analyze recent threats.</span></span> <span data-ttu-id="2c532-190">可配置资源管理器显示自定义期间的数据。</span><span class="sxs-lookup"><span data-stu-id="2c532-190">You can configure Explorer to show data for custom periods.</span></span>

- <span data-ttu-id="2c532-191">**[攻击仿真程序](attack-simulator.md)** 使你能够在组织中运行现实的攻击方案以确定漏洞。</span><span class="sxs-lookup"><span data-stu-id="2c532-191">**[Attack Simulator](attack-simulator.md)** allows you to run realistic attack scenarios in your organization to identify vulnerabilities.</span></span> <span data-ttu-id="2c532-192">可仿真当前类型的攻击，包括鱼叉式网络钓鱼凭据收集和附件攻击、密码喷射攻击和暴力密码攻击。</span><span class="sxs-lookup"><span data-stu-id="2c532-192">Simulations of current types of attacks are available, including spear phishing credential harvest and attachment attacks, and password spray and brute force password attacks.</span></span>

## <a name="save-time-with-automated-investigation-and-response"></a><span data-ttu-id="2c532-193">节省自动调查和响应的时间</span><span class="sxs-lookup"><span data-stu-id="2c532-193">Save time with automated investigation and response</span></span>

<span data-ttu-id="2c532-194">（**新增！**）调查可能的网络攻击时，时间至关重要。</span><span class="sxs-lookup"><span data-stu-id="2c532-194">(**NEW!**) When you are investigating a potential cyberattack, time is of the essence.</span></span> <span data-ttu-id="2c532-195">越快地识别和缓解威胁，贵公司的状况就越好。</span><span class="sxs-lookup"><span data-stu-id="2c532-195">The sooner you can identify and mitigate threats, the better off your organization will be.</span></span> <span data-ttu-id="2c532-196">[自动调查和响应](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) 功能包括一套可自动启动（例如触发预警时）或手动启动（例如从资源管理器中的视图启动）的安全手册。</span><span class="sxs-lookup"><span data-stu-id="2c532-196">[Automated investigation and response](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) capabilities include a set of security playbooks that can be launched automatically, such as when an alert is triggered, or manually, such as from a view in Explorer.</span></span> <span data-ttu-id="2c532-197">AIR 可以有效且高效地节省安全操作团队缓解威胁的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="2c532-197">AIR can save your security operations team time and effort in mitigating threats effectively and efficiently.</span></span> <span data-ttu-id="2c532-198">要了解详细信息，请参阅 [Office 365 中的 AIR](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。</span><span class="sxs-lookup"><span data-stu-id="2c532-198">To learn more, see [AIR in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span>

## <a name="permissions-required-to-use-atp-features"></a><span data-ttu-id="2c532-199">使用 ATP 功能所需的权限</span><span class="sxs-lookup"><span data-stu-id="2c532-199">Permissions required to use ATP features</span></span>

<span data-ttu-id="2c532-200">若要访问安全与合规中心中的 ATP 功能，你必须分配有相应的角色。</span><span class="sxs-lookup"><span data-stu-id="2c532-200">To access ATP features in the Security & Compliance Center, you must be assigned an appropriate role.</span></span> <span data-ttu-id="2c532-201">下表提供一些示例：</span><span class="sxs-lookup"><span data-stu-id="2c532-201">The following table includes some examples:</span></span>

|<span data-ttu-id="2c532-202">角色或角色组</span><span class="sxs-lookup"><span data-stu-id="2c532-202">Role or role group</span></span>|<span data-ttu-id="2c532-203">了解详细信息的资源</span><span class="sxs-lookup"><span data-stu-id="2c532-203">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="2c532-204">全局管理员（可以在 Azure Active Directory 或安全与合规中心内分配此权限）</span><span class="sxs-lookup"><span data-stu-id="2c532-204">global administrator (this can be assigned in either Azure Active Directory or in the Security & Compliance Center)</span></span>|[<span data-ttu-id="2c532-205">关于 Microsoft 365 管理员角色</span><span class="sxs-lookup"><span data-stu-id="2c532-205">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="2c532-206">安全管理员（可以在 Azure Active Directory 或安全与合规中心内分配此权限）</span><span class="sxs-lookup"><span data-stu-id="2c532-206">Security Administrator (this can be assigned in either Azure Active Directory or the Security & Compliance Center)</span></span>|[<span data-ttu-id="2c532-207">Azure Active Directory 中的管理员角色权限</span><span class="sxs-lookup"><span data-stu-id="2c532-207">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br><br/>[<span data-ttu-id="2c532-208">安全与合规中心内的权限</span><span class="sxs-lookup"><span data-stu-id="2c532-208">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)|
|<span data-ttu-id="2c532-209">Exchange Online 组织管理（在 Exchange Online 中分配此权限）</span><span class="sxs-lookup"><span data-stu-id="2c532-209">Exchange Online Organization Management (this is assigned in Exchange Online)</span></span>|[<span data-ttu-id="2c532-210">Exchange Online 中的权限</span><span class="sxs-lookup"><span data-stu-id="2c532-210">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)<br><br> [<span data-ttu-id="2c532-211">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c532-211">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|<span data-ttu-id="2c532-212">搜索和清除（仅在安全与合规中心内分配此权限）</span><span class="sxs-lookup"><span data-stu-id="2c532-212">Search and Purge (this is assigned only in the Security & Compliance Center)</span></span>|[<span data-ttu-id="2c532-213">安全与合规中心内的权限</span><span class="sxs-lookup"><span data-stu-id="2c532-213">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)|

<span data-ttu-id="2c532-214">有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2c532-214">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-office-365-atp"></a><span data-ttu-id="2c532-215">获取 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="2c532-215">Get Office 365 ATP</span></span>

<span data-ttu-id="2c532-216">Office 365 ATP 包含在特定订阅中，如 Microsoft 365 E5、Office 365 E5、Office 365 A5 和 Microsoft 365 商业高级版。</span><span class="sxs-lookup"><span data-stu-id="2c532-216">Office 365 ATP is included in certain subscriptions, such as Microsoft 365 E5, Office 365 E5, Office 365 A5, and Microsoft 365 Business Premium.</span></span> <span data-ttu-id="2c532-217">如果你的订阅未包括 Office 365 ATP，则可以将 ATP 计划 1 或 ATP 计划 2 作为加载项附加到特定订阅进行购买。</span><span class="sxs-lookup"><span data-stu-id="2c532-217">If your subscription does not include Office 365 ATP, you can purchase ATP Plan 1 or ATP Plan 2 as an add-on to certain subscriptions.</span></span> <span data-ttu-id="2c532-218">若要了解详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="2c532-218">To learn more, see the following resources:</span></span>

- <span data-ttu-id="2c532-219">有关包含 ATP 计划的订阅的列表，请参阅 [Office 365 高级威胁防护可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability)。</span><span class="sxs-lookup"><span data-stu-id="2c532-219">[Office 365 Advanced Threat Protection availability](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability) for a list of subscriptions that include ATP plans.</span></span>

- <span data-ttu-id="2c532-220">有关计划 1 和 2 中所含功能的列表，请参阅[高级威胁防护 (ATP) 计划中的功能可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="2c532-220">[Feature availability across Advanced Threat Protection (ATP) plans](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans) for a list of features included in Plan 1 and 2.</span></span>

- <span data-ttu-id="2c532-221">如需比较各个计划和购买 Office 365 ATP，请参阅[获得正确的 Office 365 高级威胁防护](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content)。</span><span class="sxs-lookup"><span data-stu-id="2c532-221">[Get the right Office 365 Advanced Threat Protection](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) to compare plans and purchase Office 365 ATP.</span></span>

- [<span data-ttu-id="2c532-222">启动免费试用版</span><span class="sxs-lookup"><span data-stu-id="2c532-222">Start a free trial</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-office-365-atp"></a><span data-ttu-id="2c532-223">Office 365 ATP 中的新功能</span><span class="sxs-lookup"><span data-stu-id="2c532-223">New features in Office 365 ATP</span></span>

<span data-ttu-id="2c532-224">向 Office 365 ATP 持续添加新功能。</span><span class="sxs-lookup"><span data-stu-id="2c532-224">New features are added to Office 365 ATP continually.</span></span> <span data-ttu-id="2c532-225">若要了解详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="2c532-225">To learn more, see the following resources:</span></span>

- <span data-ttu-id="2c532-226">[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)提供了正在开发和即将推出的新功能列表。</span><span class="sxs-lookup"><span data-stu-id="2c532-226">[Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) provides a list of new features in development and rolling out.</span></span>

- <span data-ttu-id="2c532-227">[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)介绍了 ATP 计划中的功能和可用性。</span><span class="sxs-lookup"><span data-stu-id="2c532-227">[Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp) describes features and availability across ATP plans.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c532-228">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c532-228">See also</span></span>

- [<span data-ttu-id="2c532-229">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="2c532-229">Microsoft Threat Protection</span></span>](../mtp/microsoft-threat-protection.md)

- [<span data-ttu-id="2c532-230">Microsoft 威胁防护中的自动调查和响应 (AIR)</span><span class="sxs-lookup"><span data-stu-id="2c532-230">Automated investigation and response (AIR) in Microsoft Threat Protection</span></span>](../mtp/mtp-autoir.md)
