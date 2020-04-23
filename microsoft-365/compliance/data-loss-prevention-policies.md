---
title: 数据丢失防护概述
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/12/2019
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: 通过安全 &amp; 合规中心的数据丢失防护 (DLP) 策略，可在 Office 365 内识别、监视和自动保护敏感数据。
ms.openlocfilehash: 68e81a83242ef4a1a099760044b5ccaec5bd91b7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630599"
---
# <a name="overview-of-data-loss-prevention"></a><span data-ttu-id="00248-103">数据丢失防护概述</span><span class="sxs-lookup"><span data-stu-id="00248-103">Overview of data loss prevention</span></span>
<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
<!-- move this note to a more appropriate place, no topic should start with a note -->
> [!NOTE]
> <span data-ttu-id="00248-104">对于具有 Office 365 高级合规版许可证的用户，最近为 Microsoft Teams 聊天和频道消息添加了数据丢失防护功能。它是一种独立选项，包含在 Office 365 E5 和 Microsoft 365 E5 合规版中。</span><span class="sxs-lookup"><span data-stu-id="00248-104">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 Advanced Compliance, which is available as a standalone option and is included in Office 365 E5 and Microsoft 365 E5 Compliance.</span></span> <span data-ttu-id="00248-105">要详细了解许可要求，请参阅 [Microsoft 365 租户级服务许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="00248-105">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

<span data-ttu-id="00248-106">为了符合业务标准和行业法规，组织必须保护敏感信息，防止由于疏忽而泄露。</span><span class="sxs-lookup"><span data-stu-id="00248-106">To comply with business standards and industry regulations, organizations must protect sensitive information and prevent its inadvertent disclosure.</span></span> <span data-ttu-id="00248-107">敏感信息包括财务数据或个人身份信息 (PII)，如信用卡号、社会保险号或健康记录。</span><span class="sxs-lookup"><span data-stu-id="00248-107">Sensitive information can include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records.</span></span> <span data-ttu-id="00248-108">通过 Office 365 安全 &amp; 合规中心的数据丢失防护 (DLP) 策略，可在 Office 365 内识别、监视和自动保护敏感数据。</span><span class="sxs-lookup"><span data-stu-id="00248-108">With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.</span></span>
  
<span data-ttu-id="00248-109">你可以使用 DLP 策略实现以下功能：</span><span class="sxs-lookup"><span data-stu-id="00248-109">With a DLP policy, you can:</span></span>
  
- <span data-ttu-id="00248-110">**跨 Exchange Online、SharePoint Online、OneDrive for Business 和 Microsoft Teams 等多个位置标识敏感信息。**</span><span class="sxs-lookup"><span data-stu-id="00248-110">**Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.**</span></span>
    
    <span data-ttu-id="00248-111">例如，可以识别存储在任何 OneDrive for Business 站点中的包含信用卡号的任何文档，也可以仅监视特定人员的 OneDrive 站点。</span><span class="sxs-lookup"><span data-stu-id="00248-111">For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.</span></span>
    
- <span data-ttu-id="00248-112">**防止意外共享敏感信息**。</span><span class="sxs-lookup"><span data-stu-id="00248-112">**Prevent the accidental sharing of sensitive information**.</span></span> 
    
    <span data-ttu-id="00248-113">例如，可识别出与组织外人员共享的文档或电子邮件是否包含医疗记录，然后自动阻止对该文档的访问或阻止发送该电子邮件。</span><span class="sxs-lookup"><span data-stu-id="00248-113">For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.</span></span>
    
- <span data-ttu-id="00248-114">**监视和保护 Excel、PowerPoint 和 Word 桌面版中的敏感信息。**</span><span class="sxs-lookup"><span data-stu-id="00248-114">**Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.**</span></span>
    
    <span data-ttu-id="00248-115">就像在 Exchange Online、SharePoint Online 和 OneDrive for Business 中一样，这些 Office 桌面程序都包含相同的功能以识别敏感信息和应用 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="00248-115">Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office desktop programs include the same capabilities to identify sensitive information and apply DLP policies.</span></span> <span data-ttu-id="00248-116">当用户在这些 Office 程序中共享内容时，DLP 进行持续监视。</span><span class="sxs-lookup"><span data-stu-id="00248-116">DLP provides continuous monitoring when people share content in these Office programs.</span></span>
    
- <span data-ttu-id="00248-117">**帮助用户了解如何保持兼容性，同时不会中断工作流。**</span><span class="sxs-lookup"><span data-stu-id="00248-117">**Help users learn how to stay compliant without interrupting their workflow.**</span></span>
    
    <span data-ttu-id="00248-118">您可以向用户介绍 DLP 策略，并帮助他们保持兼容性，同时不会中断工作。</span><span class="sxs-lookup"><span data-stu-id="00248-118">You can educate your users about DLP policies and help them remain compliant without blocking their work.</span></span> <span data-ttu-id="00248-119">例如，如果用户尝试共享包含敏感信息的文档，DLP 策略可以向他们发送电子邮件通知，同时在文档库的上下文中向其显示一个策略提示，以允许他们在具有业务理由的情况下替代策略。</span><span class="sxs-lookup"><span data-stu-id="00248-119">For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span> <span data-ttu-id="00248-120">Outlook 网页版、Outlook、Excel、PowerPoint 和 Word 中显示了相同的策略提示。</span><span class="sxs-lookup"><span data-stu-id="00248-120">The same policy tips also appear in Outlook on the web, Outlook, Excel, PowerPoint, and Word.</span></span>
    
- <span data-ttu-id="00248-121">**查看 DLP 报告，了解符合组织的 DLP 策略的内容。**</span><span class="sxs-lookup"><span data-stu-id="00248-121">**View DLP reports showing content that matches your organization's DLP policies.**</span></span>
    
    <span data-ttu-id="00248-122">要评估组织遵守 DLP 策略的情况，可查看每个策略和每条规则拥有的匹配数随时间变化的情况。</span><span class="sxs-lookup"><span data-stu-id="00248-122">To assess how your organization is complying with a DLP policy, you can see how many matches each policy and rule has over time.</span></span> <span data-ttu-id="00248-123">如果 DLP 策略允许用户覆盖策略提示和发出误报，则还可查看用户报告的内容。</span><span class="sxs-lookup"><span data-stu-id="00248-123">If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported.</span></span>
    
<span data-ttu-id="00248-124">你可在 Office 365 安全 &amp; 合规中心的“数据丢失防护”页上创建和管理 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="00248-124">You create and manage DLP policies on the Data loss prevention page in the Office 365 Security &amp; Compliance Center.</span></span>
  
![Office 365 安全 &amp; 合规中心的数据丢失防护页](../media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
## <a name="what-a-dlp-policy-contains"></a><span data-ttu-id="00248-126">DLP 策略包含的内容</span><span class="sxs-lookup"><span data-stu-id="00248-126">What a DLP policy contains</span></span>

<span data-ttu-id="00248-127">DLP 策略包含以下基本内容：</span><span class="sxs-lookup"><span data-stu-id="00248-127">A DLP policy contains a few basic things:</span></span>
  
- <span data-ttu-id="00248-128">在何处保护内容：Exchange Online、SharePoint Online 和 OneDrive for Business 网站等**位置**，还包括 Microsoft Teams 聊天和频道消息。</span><span class="sxs-lookup"><span data-stu-id="00248-128">Where to protect the content: **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chat and channel messages.</span></span> 
    
- <span data-ttu-id="00248-129">何时以及如何通过强制执行由以下部分组成的**规则**来保护此内容：</span><span class="sxs-lookup"><span data-stu-id="00248-129">When and how to protect the content by enforcing **rules** comprised of:</span></span> 
    
  - <span data-ttu-id="00248-130">在强制执行规则之前内容必须满足的**条件**。</span><span class="sxs-lookup"><span data-stu-id="00248-130">**Conditions** the content must match before the rule is enforced.</span></span> <span data-ttu-id="00248-131">例如，可将规则配置为只查找包含与组织外部人员共享的社会保险号的内容。</span><span class="sxs-lookup"><span data-stu-id="00248-131">For example, a rule might be configured to look only for content containing Social Security numbers that's been shared with people outside your organization.</span></span> 
    
  - <span data-ttu-id="00248-132">找到满足条件的内容时你希望规则自动执行的**操作**。</span><span class="sxs-lookup"><span data-stu-id="00248-132">**Actions** that you want the rule to take automatically when content matching the conditions is found.</span></span> <span data-ttu-id="00248-133">例如，可将规则配置为阻止访问文档，以及向用户和合规部主管发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="00248-133">For example, a rule might be configured to block access to a document and send both the user and compliance officer an email notification.</span></span> 
    
<span data-ttu-id="00248-134">可使用规则来满足特定保护要求，然后使用 DLP 策略将常见保护要求组合在一起，例如符合特定规则所需的所有规则。</span><span class="sxs-lookup"><span data-stu-id="00248-134">You can use a rule to meet a specific protection requirement, and then use a DLP policy to group together common protection requirements, such as all of the rules needed to comply with a specific regulation.</span></span>
  
<span data-ttu-id="00248-135">例如，DLP 策略可能会帮助您检测是否存在受健康保险可携性与责任法案 (HIPAA) 约束的信息。</span><span class="sxs-lookup"><span data-stu-id="00248-135">For example, you might have a DLP policy that helps you detect the presence of information subject to the Health Insurance Portability and Accountability Act (HIPAA).</span></span> <span data-ttu-id="00248-136">此 DLP 策略可以通过查找与你的组织外部人员共享的包含此敏感信息（条件）的任何文档，来帮助保护所有 SharePoint Online 站点和所有 OneDrive for Business 站点（位置）的 HIPAA 数据（对象），然后阻止对该文档的访问并发送通知（操作）。</span><span class="sxs-lookup"><span data-stu-id="00248-136">This DLP policy could help protect HIPAA data (the what) across all SharePoint Online sites and all OneDrive for Business sites (the where) by finding any document containing this sensitive information that's shared with people outside your organization (the conditions) and then blocking access to the document and sending a notification (the actions).</span></span> <span data-ttu-id="00248-137">这些要求存储为单个规则，并作为一项 DLP 策略组合在一起以简化管理和报告。</span><span class="sxs-lookup"><span data-stu-id="00248-137">These requirements are stored as individual rules and grouped together as a DLP policy to simplify management and reporting.</span></span>
  
![图表显示了 DLP 策略包含位置和规则](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
### <a name="locations"></a><span data-ttu-id="00248-139">位置</span><span class="sxs-lookup"><span data-stu-id="00248-139">Locations</span></span>

<span data-ttu-id="00248-140">无论信息位于 Exchange Online、SharePoint Online、OneDrive for Business 还是 Microsoft Teams 中，DLP 策略均可查找和保护 Microsoft 365 中的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="00248-140">A DLP policy can find and protect sensitive information across Microsoft 365, whether that information is located in Exchange Online, SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="00248-141">你可以选择保护 Exchange 电子邮件、Microsoft Teams 聊天和频道消息以及所有 SharePoint 或 OneDrive 库中的内容，或为策略选择特定位置。</span><span class="sxs-lookup"><span data-stu-id="00248-141">You can choose to protect content in Exchange email, Microsoft Teams chats and channel messages, and all SharePoint or OneDrive libraries, or select specific locations for a policy.</span></span>
  
![DLP 策略可以在其中应用的位置选项](../media/ee50a61a-e867-4571-a150-3eec8d83650f.png)

 <span data-ttu-id="00248-143">如果选择将特定通讯组包含在 Exchange 中，则 DLP 策略的影响范围将仅限于该组的成员。</span><span class="sxs-lookup"><span data-stu-id="00248-143">If you choose to include specific distribution groups in Exchange, the DLP policy will be scoped only to the members of that group.</span></span> <span data-ttu-id="00248-144">同样，排除通讯组将把该通讯组的所有成员从策略评估中排除。</span><span class="sxs-lookup"><span data-stu-id="00248-144">Similarly excluding a distribution group will exclude all the members of that distribution group from policy evaluation.</span></span> <span data-ttu-id="00248-145">可选择将策略的影响范围限定为通讯组列表、动态通讯组和安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="00248-145">You can choose to scope a policy to the members of distribution lists, dynamic distribution groups, and security groups.</span></span> <span data-ttu-id="00248-146">一条 DLP 策略可包含不超过 50 个这种包含和排除。</span><span class="sxs-lookup"><span data-stu-id="00248-146">A DLP policy can contain no more than 50 such inclusions and exclusions.</span></span>

<span data-ttu-id="00248-147">如果你选择包含或排除特定的 SharePoint 网站或 OneDrive 帐户，则 DLP 策略可包含不超过 100 个此类包含和排除项。</span><span class="sxs-lookup"><span data-stu-id="00248-147">If you choose to include or exclude specific SharePoint sites or OneDrive accounts, a DLP policy can contain no more than 100 such inclusions and exclusions.</span></span> <span data-ttu-id="00248-148">尽管存在此限制，你可应用组织范围策略或位置整体策略来超出此限制。</span><span class="sxs-lookup"><span data-stu-id="00248-148">Although this limit exists, you can exceed this limit by applying either an org-wide policy or a policy that applies to entire locations.</span></span>
  
### <a name="rules"></a><span data-ttu-id="00248-149">Rules</span><span class="sxs-lookup"><span data-stu-id="00248-149">Rules</span></span>

> [!NOTE]
> <span data-ttu-id="00248-150">当未配置警报时，DLP 策略的默认行为是，不发出警报或不触发事件。</span><span class="sxs-lookup"><span data-stu-id="00248-150">The default behavior of a DLP policy, when there is no alert configured, is not to alert or trigger.</span></span> <span data-ttu-id="00248-151">这仅适用于默认信息类型。</span><span class="sxs-lookup"><span data-stu-id="00248-151">This applies only to default information types.</span></span> <span data-ttu-id="00248-152">对于自定义信息类型，即使策略中未定义任何操作，系统也会发出警报。</span><span class="sxs-lookup"><span data-stu-id="00248-152">For custom information types, the system will alert even if there is no action defined in the policy.</span></span>

<span data-ttu-id="00248-153">规则用于对组织的内容强制执行业务要求。</span><span class="sxs-lookup"><span data-stu-id="00248-153">Rules are what enforce your business requirements on your organization's content.</span></span> <span data-ttu-id="00248-154">策略包含一条或多条规则，每条规则由多个条件和操作组成。</span><span class="sxs-lookup"><span data-stu-id="00248-154">A policy contains one or more rules, and each rule consists of conditions and actions.</span></span> <span data-ttu-id="00248-155">对于每条规则，只要满足了条件，就会自动执行操作。</span><span class="sxs-lookup"><span data-stu-id="00248-155">For each rule, when the conditions are met, the actions are taken automatically.</span></span> <span data-ttu-id="00248-156">规则按顺序执行，从每个策略中优先级最高的规则开始。</span><span class="sxs-lookup"><span data-stu-id="00248-156">Rules are executed sequentially, starting with the highest-priority rule in each policy.</span></span>
  
<span data-ttu-id="00248-157">规则还提供一些选项，用于通知用户（使用策略提示和电子邮件通知）和管理员（使用电子邮件事件报告）内容与规则相匹配。</span><span class="sxs-lookup"><span data-stu-id="00248-157">A rule also provides options to notify users (with policy tips and email notifications) and admins (with email incident reports) that content has matched the rule.</span></span>
  
<span data-ttu-id="00248-158">以下是规则的各组成部分，并提供了相应说明。</span><span class="sxs-lookup"><span data-stu-id="00248-158">Here are the components of a rule, each explained below.</span></span>
  
![DLP 规则编辑器的各部分](../media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a><span data-ttu-id="00248-160">条件</span><span class="sxs-lookup"><span data-stu-id="00248-160">Conditions</span></span>

<span data-ttu-id="00248-161">条件非常重要，因为它们确定要查找的信息类型以及执行操作的时间。</span><span class="sxs-lookup"><span data-stu-id="00248-161">Conditions are important because they determine what types of information you're looking for, and when to take an action.</span></span> <span data-ttu-id="00248-162">例如，你可能会选择忽略包含护照号的内容，除非内容包含 10 个以上此类数字并与组织外部的人员进行了共享。</span><span class="sxs-lookup"><span data-stu-id="00248-162">For example, you might choose to ignore content containing passport numbers unless the content contains more than 10 such numbers and is shared with people outside your organization.</span></span>
  
<span data-ttu-id="00248-163">条件侧重于**内容**，例如要查找的敏感信息类型，还侧重于**上下文**，例如共享文档的人员。</span><span class="sxs-lookup"><span data-stu-id="00248-163">Conditions focus on the **content**, such as what types of sensitive information you're looking for, and also on the **context**, such as who the document is shared with.</span></span> <span data-ttu-id="00248-164">你可以使用条件向不同的风险级别分配不同操作。</span><span class="sxs-lookup"><span data-stu-id="00248-164">You can use conditions to assign different actions to different risk levels.</span></span> <span data-ttu-id="00248-165">例如，相较与组织外部人员共享的敏感信息，可在内部共享的敏感内容的风险更低、需要执行的操作更少。</span><span class="sxs-lookup"><span data-stu-id="00248-165">For example, sensitive content shared internally might be lower risk and require fewer actions than sensitive content shared with people outside the organization.</span></span> 
  
![显示可用的 DLP 条件的列表](../media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
<span data-ttu-id="00248-167">现在的可用条件可以确定以下内容：</span><span class="sxs-lookup"><span data-stu-id="00248-167">The conditions now available can determine if:</span></span>
  
- <span data-ttu-id="00248-168">包含某种敏感信息的内容。</span><span class="sxs-lookup"><span data-stu-id="00248-168">Content contains a type of sensitive information.</span></span>
    
- <span data-ttu-id="00248-169">包含标签的内容。</span><span class="sxs-lookup"><span data-stu-id="00248-169">Content contains a label.</span></span> <span data-ttu-id="00248-170">有关详细信息，请参阅下方的[将保留标签用作 DLP 策略中的条件](#using-a-retention-label-as-a-condition-in-a-dlp-policy)部分。</span><span class="sxs-lookup"><span data-stu-id="00248-170">For more information, see the below section [Using a retention label as a condition in a DLP policy](#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>
    
- <span data-ttu-id="00248-171">内容是与贵组织的外部还是内部人员共享。</span><span class="sxs-lookup"><span data-stu-id="00248-171">Content is shared with people outside or inside your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="00248-172">在主体组织的 Active Directory 或 Azure Active Directory 租户中具有非来宾帐户的用户是否被视为该组织内部人员。</span><span class="sxs-lookup"><span data-stu-id="00248-172">Users who have non-guest accounts in a host organization's Active Directory or Azure Active Directory tenant are considered as people inside the organization.</span></span>
    
#### <a name="types-of-sensitive-information"></a><span data-ttu-id="00248-173">敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="00248-173">Types of sensitive information</span></span>

<span data-ttu-id="00248-174">DLP 策略可帮助保护定义为**敏感信息类型**的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="00248-174">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="00248-175">Microsoft 365 包含对多个不同地区供你使用的众多常见敏感信息类型的定义，例如信用卡号、银行账号、国民身份证号及护照号等。</span><span class="sxs-lookup"><span data-stu-id="00248-175">Microsoft 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> 
  
![可用敏感信息类型列表](../media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
<span data-ttu-id="00248-177">当 DLP 策略查找信用卡号之类的敏感信息类型时，它不只是在查找 16 位数字。</span><span class="sxs-lookup"><span data-stu-id="00248-177">When a DLP policy looks for a sensitive information type such as a credit card number, it doesn't simply look for a 16-digit number.</span></span> <span data-ttu-id="00248-178">通过以下组合对每种敏感信息类型进行定义和检测：</span><span class="sxs-lookup"><span data-stu-id="00248-178">Each sensitive information type is defined and detected by using a combination of:</span></span>
  
- <span data-ttu-id="00248-179">关键字</span><span class="sxs-lookup"><span data-stu-id="00248-179">Keywords</span></span>
    
- <span data-ttu-id="00248-180">用于验证校验和或撰写的内部函数</span><span class="sxs-lookup"><span data-stu-id="00248-180">Internal functions to validate checksums or composition</span></span>
    
- <span data-ttu-id="00248-181">用于查找模式匹配的正则表达式评估</span><span class="sxs-lookup"><span data-stu-id="00248-181">Evaluation of regular expressions to find pattern matches</span></span>
    
- <span data-ttu-id="00248-182">其他内容检查</span><span class="sxs-lookup"><span data-stu-id="00248-182">Other content examination</span></span>
    
<span data-ttu-id="00248-183">这将有助于实现高度准确的 DLP 检测，同时减少导致用户工作中断的误报数。</span><span class="sxs-lookup"><span data-stu-id="00248-183">This helps DLP detection achieve a high degree of accuracy while reducing the number of false positives that can interrupt peoples' work.</span></span>
  
#### <a name="actions"></a><span data-ttu-id="00248-184">操作</span><span class="sxs-lookup"><span data-stu-id="00248-184">Actions</span></span>

<span data-ttu-id="00248-185">当内容与规则中的条件匹配时，可应用操作以自动保护内容。</span><span class="sxs-lookup"><span data-stu-id="00248-185">When content matches a condition in a rule, you can apply actions to automatically protect the content.</span></span>
  
![可用 DLP 操作列表](../media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
<span data-ttu-id="00248-187">借助可用操作，能够：</span><span class="sxs-lookup"><span data-stu-id="00248-187">With the actions now available, you can:</span></span>
  
- <span data-ttu-id="00248-188">**限制对内容的访问** 对于网站内容，这就意味着，除主要网站集管理员、文档所有者和上次修改文档的人员外，所有人访问该文档均受限。</span><span class="sxs-lookup"><span data-stu-id="00248-188">**Restrict access to the content** For site content, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> <span data-ttu-id="00248-189">这些用户可从文档中删除敏感信息或执行其他补救操作。</span><span class="sxs-lookup"><span data-stu-id="00248-189">These people can remove the sensitive information from the document or take other remedial action.</span></span> <span data-ttu-id="00248-190">如果文档符合规则，则会自动恢复原始权限。</span><span class="sxs-lookup"><span data-stu-id="00248-190">When the document is in compliance, the original permissions are automatically restored.</span></span> <span data-ttu-id="00248-191">访问文档受阻时，文档将在网站的库中显示一个特殊策略提示图标。</span><span class="sxs-lookup"><span data-stu-id="00248-191">When access to a document is blocked, the document appears with a special policy tip icon in the library on the site.</span></span> 
    
    ![显示文档访问被拦截的策略提示](../media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
    <span data-ttu-id="00248-193">对于电子邮件内容，此操作阻止发送该邮件。</span><span class="sxs-lookup"><span data-stu-id="00248-193">For email content, this action blocks the message from being sent.</span></span> <span data-ttu-id="00248-194">根据 DLP 规则的配置方式，发件人将看到 NDR 或（如果规则使用通知）策略提示和/或电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="00248-194">Depending on how the DLP rule is configured, the sender sees an NDR or (if the rule uses a notification) a policy tip and/or email notification.</span></span>
    
    ![警告：必须从邮件中删除未经授权的收件人](../media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a><span data-ttu-id="00248-196">用户通知和用户覆盖</span><span class="sxs-lookup"><span data-stu-id="00248-196">User notifications and user overrides</span></span>

<span data-ttu-id="00248-197">你可以使用通知和覆盖向用户介绍 DLP 策略，并帮助他们保持兼容性，同时不会中断工作。</span><span class="sxs-lookup"><span data-stu-id="00248-197">You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work.</span></span> <span data-ttu-id="00248-198">例如，如果用户尝试共享包含敏感信息的文档，DLP 策略可以向他们发送电子邮件通知，同时在文档库的上下文中向其显示一个策略提示，以允许他们在具有业务理由的情况下替代策略。</span><span class="sxs-lookup"><span data-stu-id="00248-198">For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span>
  
![DLP 规则编辑器的用户通知和用户覆盖部分](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
<span data-ttu-id="00248-200">电子邮件可向发送、共享或最后修改内容的人员发送通知，对于网站内容，则可通知主要网站集管理员和文档所有者。</span><span class="sxs-lookup"><span data-stu-id="00248-200">The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner.</span></span> <span data-ttu-id="00248-201">此外，还可向电子邮件通知中添加人员或删除所选人员。</span><span class="sxs-lookup"><span data-stu-id="00248-201">In addition, you can add or remove whomever you choose from the email notification.</span></span>
  
<span data-ttu-id="00248-202">除发送电子邮件通知外，用户通知还会显示一条策略提示：</span><span class="sxs-lookup"><span data-stu-id="00248-202">In addition to sending an email notification, a user notification displays a policy tip:</span></span>
  
- <span data-ttu-id="00248-203">在 Outlook 和 Outlook 网页版中。</span><span class="sxs-lookup"><span data-stu-id="00248-203">In Outlook and Outlook on the web.</span></span>
    
- <span data-ttu-id="00248-204">对于 SharePoint Online 或 OneDrive for Business 网站上的文档。</span><span class="sxs-lookup"><span data-stu-id="00248-204">For the document on a SharePoint Online or OneDrive for Business site.</span></span>
    
- <span data-ttu-id="00248-205">在 Excel、PowerPoint 和 Word 中（如果文档存储在 DLP 策略中包含的网站上）。</span><span class="sxs-lookup"><span data-stu-id="00248-205">In Excel, PowerPoint, and Word, when the document is stored on a site included in a DLP policy.</span></span>
    
<span data-ttu-id="00248-206">电子邮件通知和策略提示解释内容与 DLP 策略相冲突的原因。</span><span class="sxs-lookup"><span data-stu-id="00248-206">The email notification and policy tip explain why content conflicts with a DLP policy.</span></span> <span data-ttu-id="00248-207">如果您选择，电子邮件通知和策略提示可以允许用户通过报告误报或提供业务理由来替代规则。</span><span class="sxs-lookup"><span data-stu-id="00248-207">If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification.</span></span> <span data-ttu-id="00248-208">这可以帮助您让用户了解您的 DLP 策略和强制执行它们，而不会阻止用户完成其工作。</span><span class="sxs-lookup"><span data-stu-id="00248-208">This can help you educate users about your DLP policies and enforce them without preventing people from doing their work.</span></span> <span data-ttu-id="00248-209">有关替代和误报的信息还记录报告（请参阅下文提供的 DLP 报告）并且包含在事件报告（下一节）中，以便合规部主管可以定期查看此信息。</span><span class="sxs-lookup"><span data-stu-id="00248-209">Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.</span></span>
  
<span data-ttu-id="00248-210">以下是 OneDrive for Business 帐户中的策略提示。</span><span class="sxs-lookup"><span data-stu-id="00248-210">Here's what a policy tip looks like in a OneDrive for Business account.</span></span>
  
![针对 OneDrive 帐户中文档的策略提示](../media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 <span data-ttu-id="00248-212">若要了解有关 DLP 策略中的用户通知和策略提示的详细信息，请参阅[使用通知和策略提示](use-notifications-and-policy-tips.md)。</span><span class="sxs-lookup"><span data-stu-id="00248-212">To learn more about user notifications and policy tips in DLP policies, see [Use notifications and policy tips](use-notifications-and-policy-tips.md).</span></span>

#### <a name="incident-reports"></a><span data-ttu-id="00248-213">事件报告</span><span class="sxs-lookup"><span data-stu-id="00248-213">Incident reports</span></span>

<span data-ttu-id="00248-214">当项目与规则相匹配时，可向合规负责人（或所选的任何人员）发送包含事件详情的事件报告。</span><span class="sxs-lookup"><span data-stu-id="00248-214">When a rule is matched, you can send an incident report to your compliance officer (or any people you choose) with details of the event.</span></span> <span data-ttu-id="00248-215">此报告中的信息包括，匹配的项目的信息、与规则匹配的实际内容以及上次修改内容的人员的姓名。</span><span class="sxs-lookup"><span data-stu-id="00248-215">This report includes information about the item that was matched, the actual content that matched the rule, and the name of the person who last modified the content.</span></span> <span data-ttu-id="00248-216">对于电子邮件，报告还将与 DLP 策略匹配的原始邮件包含为附件。</span><span class="sxs-lookup"><span data-stu-id="00248-216">For email messages, the report also includes as an attachment the original message that matches a DLP policy.</span></span>
  
![用于配置事件报告的页面](../media/31c6da0e-981c-415e-91bf-d94ca391a893.png)

<span data-ttu-id="00248-218">DLP 扫描电子邮件的方式与 SharePoint Online 或 OneDrive for Business 中的项目不同。</span><span class="sxs-lookup"><span data-stu-id="00248-218">DLP scans email differently from items in SharePoint Online or OneDrive for Business.</span></span> <span data-ttu-id="00248-219">在 SharePoint Online 和 OneDrive for business 中，DLP 可扫描现有项目以及新项目，并在找到匹配项时生成事件报告。</span><span class="sxs-lookup"><span data-stu-id="00248-219">In SharePoint Online and OneDrive for Business, DLP scans existing items as well as new ones and generates an incident report whenever a match is found.</span></span> <span data-ttu-id="00248-220">在 Exchange Online 中，DLP 仅扫描新电子邮件，并在存在策略匹配项时生成报告。</span><span class="sxs-lookup"><span data-stu-id="00248-220">In Exchange Online, DLP only scans new email messages and generates a report if there is a policy match.</span></span> <span data-ttu-id="00248-221">DLP ***不会***扫描或匹配邮箱或存档中存储的先前存在的电子邮件项目。</span><span class="sxs-lookup"><span data-stu-id="00248-221">DLP ***does not*** scan or match previously existing email items that are stored in a mailbox or archive.</span></span>
  
## <a name="grouping-and-logical-operators"></a><span data-ttu-id="00248-222">分组和逻辑运算符</span><span class="sxs-lookup"><span data-stu-id="00248-222">Grouping and logical operators</span></span>

<span data-ttu-id="00248-223">DLP 策略的要求通常比较简单，例如标识包含美国社会安全号码的所有内容。</span><span class="sxs-lookup"><span data-stu-id="00248-223">Often your DLP policy has a straightforward requirement, such as to identify all content that contains a U.S. Social Security Number.</span></span> <span data-ttu-id="00248-224">但在其他情况下，DLP 策略可能需要标识定义更松散的数据。</span><span class="sxs-lookup"><span data-stu-id="00248-224">However, in other scenarios, your DLP policy might need to identify more loosely defined data.</span></span>
  
<span data-ttu-id="00248-225">例如，若要标识应遵循美国健康保险法案 (HIPAA) 的内容，需要查找：</span><span class="sxs-lookup"><span data-stu-id="00248-225">For example, to identify content subject to the U.S. Health Insurance Act (HIPAA), you need to look for:</span></span>
  
- <span data-ttu-id="00248-226">包含特定类型敏感信息的内容，例如美国。社会安全号码或毒品管制局 (DEA) 号码。</span><span class="sxs-lookup"><span data-stu-id="00248-226">Content that contains specific types of sensitive information, such as a U.S. Social Security Number or Drug Enforcement Agency (DEA) Number.</span></span>
    
    <span data-ttu-id="00248-227">AND</span><span class="sxs-lookup"><span data-stu-id="00248-227">AND</span></span>
    
- <span data-ttu-id="00248-228">更难以标识的内容，例如有关患者护理的通信，或者提供的医疗服务说明。</span><span class="sxs-lookup"><span data-stu-id="00248-228">Content that's more difficult to identify, such as communications about a patient's care or descriptions of medical services provided.</span></span> <span data-ttu-id="00248-229">识别此内容需要匹配极庞大的关键字列表中的关键字，如国际疾病分类（ICD-9-CM 或 ICD-10-CM）。</span><span class="sxs-lookup"><span data-stu-id="00248-229">Identifying this content requires matching keywords from very large keyword lists, such as the International Classification of Diseases (ICD-9-CM or ICD-10-CM).</span></span>
    
<span data-ttu-id="00248-230">使用分组和逻辑运算符（AND、OR），可轻松标识此类定义松散的数据。</span><span class="sxs-lookup"><span data-stu-id="00248-230">You can easily identify such loosely defined data by using grouping and logical operators (AND, OR).</span></span> <span data-ttu-id="00248-231">创建 DLP 策略时，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="00248-231">When you create a DLP policy, you can:</span></span>
  
- <span data-ttu-id="00248-232">对敏感信息类型进行分组。</span><span class="sxs-lookup"><span data-stu-id="00248-232">Group sensitive information types.</span></span>
    
- <span data-ttu-id="00248-233">选择组内敏感信息类型之间以及组与组之间的逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="00248-233">Choose the logical operator between the sensitive information types within a group and between the groups themselves.</span></span>
    
### <a name="choosing-the-operator-within-a-group"></a><span data-ttu-id="00248-234">选择组内的运算符</span><span class="sxs-lookup"><span data-stu-id="00248-234">Choosing the operator within a group</span></span>

<span data-ttu-id="00248-235">在组中，可选择要将内容视为与规则匹配，是只需满足该组中的任一条件，还是必须满足所有条件。</span><span class="sxs-lookup"><span data-stu-id="00248-235">Within a group, you can choose whether any or all of the conditions in that group must be satisfied for the content to match the rule.</span></span>
  
![显示组内运算符的组](../media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a><span data-ttu-id="00248-237">添加组</span><span class="sxs-lookup"><span data-stu-id="00248-237">Adding a group</span></span>

<span data-ttu-id="00248-238">可以快速添加组，该组内可包含自己的条件和运算符。</span><span class="sxs-lookup"><span data-stu-id="00248-238">You can quickly add a group, which can have its own conditions and operator within that group.</span></span>
  
![添加组按钮](../media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a><span data-ttu-id="00248-240">选择组之间的运算符</span><span class="sxs-lookup"><span data-stu-id="00248-240">Choosing the operator between groups</span></span>

<span data-ttu-id="00248-241">在组之间，为使内容与规则匹配，可选择只需满足一个组中的条件，还是必须满足所有组的条件。</span><span class="sxs-lookup"><span data-stu-id="00248-241">Between groups, you can choose whether the conditions in just one group or all of the groups must be satisfied for the content to match the rule.</span></span>
  
<span data-ttu-id="00248-242">例如，内置“**美国 HIPAA**”政策有一项规则，规定在组之间使用 **AND** 运算符，因此它标识的内容将包括：</span><span class="sxs-lookup"><span data-stu-id="00248-242">For example, the built-in **U.S. HIPAA** policy has a rule that uses an **AND** operator between the groups so that it identifies content that contains:</span></span> 
  
- <span data-ttu-id="00248-243">从组“**PII 标识符**”（至少一个 SSN 数字 **OR** DEA 数字）</span><span class="sxs-lookup"><span data-stu-id="00248-243">from the group **PII Identifiers** (at least one SSN number **OR** DEA number)</span></span> 
    
    <span data-ttu-id="00248-244">AND\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="00248-244">**AND**</span></span>
    
- <span data-ttu-id="00248-245">从组“**医疗条件**”（至少一个 ICD-9-CM 关键字 **OR** 一个 ICD-10-CM 关键字）</span><span class="sxs-lookup"><span data-stu-id="00248-245">from the group **Medical Terms** (at least one ICD-9-CM keyword **OR** ICD-10-CM keyword)</span></span> 
    
![显示组之间运算符的组](../media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a><span data-ttu-id="00248-247">处理规则的优先级</span><span class="sxs-lookup"><span data-stu-id="00248-247">The priority by which rules are processed</span></span>

<span data-ttu-id="00248-248">在策略中创建规则时，每条规则都按创建顺序分配了优先级 — 这意味着，首先创建的规则具有第一优先级，创建的第二条规则具有第二优先级，以此类推。</span><span class="sxs-lookup"><span data-stu-id="00248-248">When you create rules in a policy, each rule is assigned a priority in the order in which it's created — meaning, the rule created first has first priority, the rule created second has second priority, and so on.</span></span> 
  
![按优先级顺序排列的规则](../media/dlp-rules-in-priority-order.png)
  
<span data-ttu-id="00248-250">设置多个 DLP 策略后，可以更改一个或多个策略的优先级。</span><span class="sxs-lookup"><span data-stu-id="00248-250">After you have set up more than one DLP policy, you can change the priority of one or more policies.</span></span> <span data-ttu-id="00248-251">若要执行此操作，请选择一个策略，选择“**编辑策略**”，然后使用“**优先级**”列表指定其优先级。</span><span class="sxs-lookup"><span data-stu-id="00248-251">To do that, select a policy, choose **Edit policy**, and use the **Priority** list to specify its priority.</span></span>

![设置策略的优先级](../media/dlp-set-policy-priority.png)

<span data-ttu-id="00248-253">对照规则评估内容时，按优先级顺序处理规则。</span><span class="sxs-lookup"><span data-stu-id="00248-253">When content is evaluated against rules, the rules are processed in priority order.</span></span> <span data-ttu-id="00248-254">如果内容符合多个规则，按优先级顺序处理规则，并强制实施最严格的操作。</span><span class="sxs-lookup"><span data-stu-id="00248-254">If content matches multiple rules, the rules are processed in priority order and the most restrictive action is enforced.</span></span> <span data-ttu-id="00248-255">例如，如果内容符合以下所有规则，将实施规则 3，因为它具有最高优先级且最严格：</span><span class="sxs-lookup"><span data-stu-id="00248-255">For example, if content matches all of the following rules, Rule 3 is enforced because it's the highest priority, most restrictive rule:</span></span>
  
- <span data-ttu-id="00248-256">规则 1：仅通知用户</span><span class="sxs-lookup"><span data-stu-id="00248-256">Rule 1: only notifies users</span></span>
    
- <span data-ttu-id="00248-257">规则 2：通知用户、限制访问并允许用户替代</span><span class="sxs-lookup"><span data-stu-id="00248-257">Rule 2: notifies users, restricts access, and allows user overrides</span></span>
    
- <span data-ttu-id="00248-258">规则 3：通知用户、限制访问且不允许用户替代</span><span class="sxs-lookup"><span data-stu-id="00248-258">Rule 3: notifies users, restricts access, and does not allow user overrides</span></span>
    
- <span data-ttu-id="00248-259">规则 4：仅通知用户</span><span class="sxs-lookup"><span data-stu-id="00248-259">Rule 4: only notifies users</span></span>
    
- <span data-ttu-id="00248-260">规则 5：限制访问</span><span class="sxs-lookup"><span data-stu-id="00248-260">Rule 5: restricts access</span></span>
    
- <span data-ttu-id="00248-261">规则 6：通知用户、限制访问且不允许用户替代</span><span class="sxs-lookup"><span data-stu-id="00248-261">Rule 6: notifies users, restricts access, and does not allow user overrides</span></span>
    
<span data-ttu-id="00248-262">在此示例中，要注意的是尽管只实施最严格的规则，仍会将所有匹配的规则记录在审核日志中，并显示在 DLP 报表中。</span><span class="sxs-lookup"><span data-stu-id="00248-262">In this example, note that matches for all of the rules are recorded in the audit logs and shown in the DLP reports, even though only the most restrictive rule is enforced.</span></span>
  
<span data-ttu-id="00248-263">对于策略提示，请注意:</span><span class="sxs-lookup"><span data-stu-id="00248-263">Regarding policy tips, note that:</span></span>
  
- <span data-ttu-id="00248-264">仅显示来自最高优先级、最具限制性的规则的策略提示。</span><span class="sxs-lookup"><span data-stu-id="00248-264">Only the policy tip from the highest priority, most restrictive rule will be shown.</span></span> <span data-ttu-id="00248-265">例如，阻止访问内容的规则所提供的策略提示比起只是发送通知的规则所提供的策略提示，前者的显示优先级高于后者。</span><span class="sxs-lookup"><span data-stu-id="00248-265">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="00248-266">这会让用户看不到策略提示的级联方式。</span><span class="sxs-lookup"><span data-stu-id="00248-266">This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="00248-267">如果限制最严格的规则中的策略提示允许用户替换规则，那么替换此规则还会替换与此内容相匹配的所有其他规则。</span><span class="sxs-lookup"><span data-stu-id="00248-267">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a><span data-ttu-id="00248-268">调整规则，使它们更易或更难匹配</span><span class="sxs-lookup"><span data-stu-id="00248-268">Tuning rules to make them easier or harder to match</span></span>

<span data-ttu-id="00248-269">用户创建并启用 DLP 策略后，他们有时会遇到以下问题：</span><span class="sxs-lookup"><span data-stu-id="00248-269">After people create and turn on their DLP policies, they sometimes run into these issues:</span></span>
  
- <span data-ttu-id="00248-270">太多**不是**敏感信息的内容与规则匹配 — 也就是说，太多误报。</span><span class="sxs-lookup"><span data-stu-id="00248-270">Too much content that **is not** sensitive information matches the rules — in other words, too many false positives.</span></span> 
    
- <span data-ttu-id="00248-271">太少**是**敏感信息的内容与规则匹配。</span><span class="sxs-lookup"><span data-stu-id="00248-271">Too little content that **is** sensitive information matches the rules.</span></span> <span data-ttu-id="00248-272">也就是说，未对敏感信息强制执行保护操作。</span><span class="sxs-lookup"><span data-stu-id="00248-272">In other words, the protective actions aren't being enforced on the sensitive information.</span></span> 
    
<span data-ttu-id="00248-273">若要解决这些问题，可以通过调整实例计数和匹配准确度来调整规则，使内容更难或更易匹配规则。</span><span class="sxs-lookup"><span data-stu-id="00248-273">To address these issues, you can tune your rules by adjusting the instance count and match accuracy to make it harder or easier for content to match the rules.</span></span> <span data-ttu-id="00248-274">规则中使用的每一类敏感信息都有实例计数和匹配准确度。</span><span class="sxs-lookup"><span data-stu-id="00248-274">Each sensitive information type used in a rule has both an instance count and match accuracy.</span></span>
  
### <a name="instance-count"></a><span data-ttu-id="00248-275">实例计数</span><span class="sxs-lookup"><span data-stu-id="00248-275">Instance count</span></span>

<span data-ttu-id="00248-276">实例计数是指若要使内容与规则匹配，某类敏感信息必须出现的次数。</span><span class="sxs-lookup"><span data-stu-id="00248-276">Instance count means simply how many occurrences of a specific type of sensitive information must be present for content to match the rule.</span></span> <span data-ttu-id="00248-277">例如，如果将美国或英国护照号码标识为 1 到 9，</span><span class="sxs-lookup"><span data-stu-id="00248-277">For example, content matches the rule shown below if between 1 and 9 unique U.S. or U.K.</span></span> <span data-ttu-id="00248-278">则内容将与如下所示的规则匹配。</span><span class="sxs-lookup"><span data-stu-id="00248-278">passport numbers are identified.</span></span>
  
<span data-ttu-id="00248-279">请注意，实例计数仅包括敏感信息类型和关键字的**唯一**匹配项。</span><span class="sxs-lookup"><span data-stu-id="00248-279">Note that the instance count includes only **unique** matches for sensitive information types and keywords.</span></span> <span data-ttu-id="00248-280">例如，如果一个电子邮件中相同的信用卡号码出现了 10 次，则这 10 次计为信用卡号码的单个实例。</span><span class="sxs-lookup"><span data-stu-id="00248-280">For example, if an email contains 10 occurrences of the same credit card number, those 10 occurrences count as a single instance of a credit card number.</span></span> 
  
<span data-ttu-id="00248-281">若要使用实例计数来调整规则，则指南非常简单：</span><span class="sxs-lookup"><span data-stu-id="00248-281">To use instance count to tune rules, the guidance is straightforward:</span></span>
  
- <span data-ttu-id="00248-282">若要使规则更易匹配，减少“**最小**”计数和/或增加“**最大**”计数。</span><span class="sxs-lookup"><span data-stu-id="00248-282">To make the rule easier to match, decrease the **min** count and/or increase the **max** count.</span></span> <span data-ttu-id="00248-283">也可以通过删除数值，将“**最大**”设置为“**任意**”。</span><span class="sxs-lookup"><span data-stu-id="00248-283">You can also set **max** to **any** by deleting the numerical value.</span></span> 
    
- <span data-ttu-id="00248-284">若要使规则更难匹配，增加“**最小**”计数。</span><span class="sxs-lookup"><span data-stu-id="00248-284">To make the rule harder to match, increase the **min** count.</span></span> 
    
<span data-ttu-id="00248-285">在实例计数较低（例如，1-9）的规则中，通常会使用较为宽松的操作，如发送用户通知。</span><span class="sxs-lookup"><span data-stu-id="00248-285">Typically, you use less restrictive actions, such as sending user notifications, in a rule with a lower instance count (for example, 1-9).</span></span> <span data-ttu-id="00248-286">在实例计数较高（例如，10–任意）的规则中，使用更严格的操作，如限制访问内容且不允许用户替代。</span><span class="sxs-lookup"><span data-stu-id="00248-286">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with a higher instance count (for example, 10-any).</span></span>
  
![规则编辑器中的实例计数](../media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a><span data-ttu-id="00248-288">匹配准确度</span><span class="sxs-lookup"><span data-stu-id="00248-288">Match accuracy</span></span>

<span data-ttu-id="00248-289">如上文所述，使用不同类型的证据组合定义并检测敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="00248-289">As described above, a sensitive information type is defined and detected by using a combination of different types of evidence.</span></span> <span data-ttu-id="00248-290">敏感信息类型通常由多个此类组合（称为模式）定义。</span><span class="sxs-lookup"><span data-stu-id="00248-290">Commonly, a sensitive information type is defined by multiple such combinations, called patterns.</span></span> <span data-ttu-id="00248-291">需要越少证据的模式匹配准确度（即置信水平）越低，而需要越多证据的模式匹配准确度（即置信水平）更高。</span><span class="sxs-lookup"><span data-stu-id="00248-291">A pattern that requires less evidence has a lower match accuracy (or confidence level), while a pattern that requires more evidence has a higher match accuracy (or confidence level).</span></span> <span data-ttu-id="00248-292">若要了解每种敏感信息类型使用的实际模式和置信水平，请参阅[使用敏感信息类型查找什么](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="00248-292">To learn more about the actual patterns and confidence levels used by every sensitive information type, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
<span data-ttu-id="00248-293">例如，名为“信用卡号”的敏感信息类型由两种模式定义：</span><span class="sxs-lookup"><span data-stu-id="00248-293">For example, the sensitive information type named Credit Card Number is defined by two patterns:</span></span>
  
- <span data-ttu-id="00248-294">置信度为 65% 的模式需要：</span><span class="sxs-lookup"><span data-stu-id="00248-294">A pattern with 65% confidence that requires:</span></span>
    
  - <span data-ttu-id="00248-295">信用卡号格式的数字。</span><span class="sxs-lookup"><span data-stu-id="00248-295">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="00248-296">传递校验和的数字。</span><span class="sxs-lookup"><span data-stu-id="00248-296">A number that passes the checksum.</span></span>
    
- <span data-ttu-id="00248-297">置信度为 85% 的模式需要：</span><span class="sxs-lookup"><span data-stu-id="00248-297">A pattern with 85% confidence that requires:</span></span>
    
  - <span data-ttu-id="00248-298">信用卡号格式的数字。</span><span class="sxs-lookup"><span data-stu-id="00248-298">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="00248-299">传递校验和的数字。</span><span class="sxs-lookup"><span data-stu-id="00248-299">A number that passes the checksum.</span></span>
    
  - <span data-ttu-id="00248-300">格式正确的关键字或到期日期。</span><span class="sxs-lookup"><span data-stu-id="00248-300">A keyword or an expiration date in the right format.</span></span>
    
<span data-ttu-id="00248-301">可在规则中使用这些置信水平（或匹配准确度）。</span><span class="sxs-lookup"><span data-stu-id="00248-301">You can use these confidence levels (or match accuracy) in your rules.</span></span> <span data-ttu-id="00248-302">在匹配准确度较低的规则中通常使用较为宽松的操作，如发送用户通知。</span><span class="sxs-lookup"><span data-stu-id="00248-302">Typically, you use less restrictive actions, such as sending user notifications, in a rule with lower match accuracy.</span></span> <span data-ttu-id="00248-303">在匹配准确度较高的规则中使用更严格的操作，如限制访问内容且不允许用户替代。</span><span class="sxs-lookup"><span data-stu-id="00248-303">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with higher match accuracy.</span></span>
  
<span data-ttu-id="00248-304">务必了解在内容中标识特定类型的敏感信息（如信用卡号）时，只会返回单个置信水平：</span><span class="sxs-lookup"><span data-stu-id="00248-304">It's important to understand that when a specific type of sensitive information, such as a credit card number, is identified in content, only a single confidence level is returned:</span></span>
  
- <span data-ttu-id="00248-305">如果所有匹配项适用于单个模式，则返回该模式的置信水平。</span><span class="sxs-lookup"><span data-stu-id="00248-305">If all of the matches are for a single pattern, the confidence level for that pattern is returned.</span></span>
    
- <span data-ttu-id="00248-306">如果存在多个模式的匹配项（即，存在具有两种不同置信水平的匹配项），则返回高于任一单个模式的置信水平。</span><span class="sxs-lookup"><span data-stu-id="00248-306">If there are matches for more than one pattern (that is, there are matches with two different confidence levels), a confidence level higher than any of the single patterns alone is returned.</span></span> <span data-ttu-id="00248-307">这就是难点。</span><span class="sxs-lookup"><span data-stu-id="00248-307">This is the tricky part.</span></span> <span data-ttu-id="00248-308">例如，对于信用卡号，如果同时匹配 65% 和 85% 模式，则该敏感信息类型返回的置信水平超过 90%，因为证据越多，置信度越高。</span><span class="sxs-lookup"><span data-stu-id="00248-308">For example, for a credit card, if both the 65% and 85% patterns are matched, the confidence level returned for that sensitive information type is greater than 90% because more evidence means more confidence.</span></span>
    
<span data-ttu-id="00248-309">因此，如果要为信用卡创建两条互斥的规则，一条用于 65% 的匹配准确度，另一条用于 85% 的匹配准确度，匹配准确度的范围将如下所示。</span><span class="sxs-lookup"><span data-stu-id="00248-309">So if you want to create two mutually exclusive rules for credit cards, one for the 65% match accuracy and one for the 85% match accuracy, the ranges for match accuracy would look like this.</span></span> <span data-ttu-id="00248-310">第一条规则仅选取 65% 模式的匹配项。</span><span class="sxs-lookup"><span data-stu-id="00248-310">The first rule picks up only matches of the 65% pattern.</span></span> <span data-ttu-id="00248-311">第二条规则选取**至少一个** 85% 匹配项，并且**可能具有**其他置信度较低的匹配项。</span><span class="sxs-lookup"><span data-stu-id="00248-311">The second rule picks up matches with **at least one** 85% match and **can potentially have** other lower-confidence matches.</span></span> 
  
![两条具有不同匹配准确度范围的规则](../media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
<span data-ttu-id="00248-313">由于以上原因，使用不同的匹配准确性创建规则的指南为：</span><span class="sxs-lookup"><span data-stu-id="00248-313">For these reasons, the guidance for creating rules with different match accuracies is:</span></span>
  
- <span data-ttu-id="00248-314">最低置信水平通常使用相同的“**最小**”和“**最大**”值（而不是范围）。</span><span class="sxs-lookup"><span data-stu-id="00248-314">The lowest confidence level typically uses the same value for **min** and **max** (not a range).</span></span> 
    
- <span data-ttu-id="00248-315">最高置信水平通常是一个范围，该范围为略高于置信水平下限到 100。</span><span class="sxs-lookup"><span data-stu-id="00248-315">The highest confidence level is typically a range from just above the lower confidence level to 100.</span></span>
    
- <span data-ttu-id="00248-316">任何中间置信水平范围通常为略高于置信水平下限，略低于置信水平上限。</span><span class="sxs-lookup"><span data-stu-id="00248-316">Any in-between confidence levels typically range from just above the lower confidence level to just below the higher confidence level.</span></span>
    
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="00248-317">将保留标签用作 DLP 策略中的条件</span><span class="sxs-lookup"><span data-stu-id="00248-317">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="00248-318">将以前创建和发布的[保留标签](labels.md)用作 DLP 策略中的条件时，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="00248-318">When you use a previously created and published [retention label](labels.md) as a condition in a DLP policy, there are some things to be aware of:</span></span>

- <span data-ttu-id="00248-319">在尝试将保留标签用作 DLP 策略中的条件之前，你以前必须已创建、发布和应用了该标签。</span><span class="sxs-lookup"><span data-stu-id="00248-319">You have to have previously created, published and applied the retention label before you attempt to use it as a condition in a DLP policy.</span></span>
- <span data-ttu-id="00248-320">创建并发布保留标签后，它们可能需要长达一天的时间来同步，并且最多需要 7 天来自动应用。</span><span class="sxs-lookup"><span data-stu-id="00248-320">Retention labels can take up to a day to sync and up to seven days to auto-apply after they have been created and published.</span></span> <span data-ttu-id="00248-321">有关详细信息，请参阅[保留标签需要多长时间才能生效](labels.md#how-long-it-takes-for-retention-labels-to-take-effect)。</span><span class="sxs-lookup"><span data-stu-id="00248-321">See, [How long it takes for retention labels to take effect](labels.md#how-long-it-takes-for-retention-labels-to-take-effect) for detailed information.</span></span>
- <span data-ttu-id="00248-322">***仅支持 SharePoint Online 和 OneDrive for Business 中的项目***在策略中使用保留标签。</span><span class="sxs-lookup"><span data-stu-id="00248-322">Using a retention label in a policy ***is only supported for items in SharePoint Online and OneDrive for Business***.</span></span>


![用作条件的标签](../media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

<span data-ttu-id="00248-324">如果你有项目处于保留和处置状态，并且还希望为其应用其他控件，则可能需要在 DLP 策略中使用保留标签，例如：</span><span class="sxs-lookup"><span data-stu-id="00248-324">You might want to use a retention label in a DLP policy if you have items that are under retention and disposition, and you also want to apply other controls to them, for example:</span></span>

- <span data-ttu-id="00248-325">你发布了一个名为“**2018 纳税年度**”的保留标签，当它应用于存储在 SharePoint 中的 2018 年税务文档后，系统会将其保留 10 年，并在此期限后处置它们。</span><span class="sxs-lookup"><span data-stu-id="00248-325">You published a retention label named **tax year 2018**, which when applied to tax documents from 2018 that are stored in SharePoint retains them for 10 years then disposes of them.</span></span> <span data-ttu-id="00248-326">你也不希望在组织外部共享这些项目，你可以使用 DLP 策略来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="00248-326">You also don't want those items being shared outside your organization, which you can do with a DLP policy.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00248-327">如果在 DLP 策略中将保留标签指定为条件，而且你还包含 Exchange 和/或 Teams 作为位置，则你将收到以下错误：**“不支持保护电子邮件和团队消息中带标签的内容。请删除下述标签或取消将 Exchange 和 Teams 设为位置。”**</span><span class="sxs-lookup"><span data-stu-id="00248-327">You'll get this error if you specify a retention label as a condition in a DLP policy and you also include Exchange and/or Teams as a location: **"Protecting labeled content in email and teams messages isn't supported. Either remove the label below or turn off Exchange and Teams as a location."**</span></span> <span data-ttu-id="00248-328">这是因为 Exchange 传输在消息提交和传递过程中不会评估标签元数据。</span><span class="sxs-lookup"><span data-stu-id="00248-328">This is because Exchange transport does not evaluate the label metadata during message submission and delivery.</span></span> 

### <a name="support-for-sensitivity-labels-is-coming"></a><span data-ttu-id="00248-329">即将推出对敏感度标签的支持</span><span class="sxs-lookup"><span data-stu-id="00248-329">Support for sensitivity labels is coming</span></span>

<span data-ttu-id="00248-330">目前，你只能将保留标签用作条件，而不能将[敏感度标签](sensitivity-labels.md)用作条件。</span><span class="sxs-lookup"><span data-stu-id="00248-330">You can currently use only a retention label as a condition, not a [sensitivity label](sensitivity-labels.md).</span></span> <span data-ttu-id="00248-331">目前，我们正致力于支持在此条件中使用敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="00248-331">We're currently working on support for using a sensitivity label in this condition.</span></span>
  
### <a name="how-this-feature-relates-to-other-features"></a><span data-ttu-id="00248-332">此功能与其他功能的联系</span><span class="sxs-lookup"><span data-stu-id="00248-332">How this feature relates to other features</span></span>

<span data-ttu-id="00248-333">可对包含敏感信息的内容应用多个功能：</span><span class="sxs-lookup"><span data-stu-id="00248-333">Several features can be applied to content containing sensitive information:</span></span>
  
- <span data-ttu-id="00248-334">[保留标签](labels.md#applying-a-retention-label-automatically-based-on-conditions)和[保留策略](retention-policies.md)均可对此内容执行**保留**操作。</span><span class="sxs-lookup"><span data-stu-id="00248-334">A [retention label](labels.md#applying-a-retention-label-automatically-based-on-conditions) and a [retention policy](retention-policies.md) can both enforce **retention** actions on this content.</span></span> 
    
- <span data-ttu-id="00248-335">DLP 策略可对此内容执行**保护**操作。</span><span class="sxs-lookup"><span data-stu-id="00248-335">A DLP policy can enforce **protection** actions on this content.</span></span> <span data-ttu-id="00248-336">执行这些操作之前，DLP 策略可要求内容除包含标签之外还需满足其他条件。</span><span class="sxs-lookup"><span data-stu-id="00248-336">And before enforcing these actions, a DLP policy can require other conditions to be met in addition to the content containing a label.</span></span> 
    
![可应用于敏感信息的功能图表](../media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
<span data-ttu-id="00248-338">请注意，相较于对敏感信息应用的标签或保留策略，DLP 策略的检测功能更强。</span><span class="sxs-lookup"><span data-stu-id="00248-338">Note that a DLP policy has a richer detection capability than a label or retention policy applied to sensitive information.</span></span> <span data-ttu-id="00248-339">DLP 策略可以对包含敏感信息的内容执行保护操作；从内容中删除敏感信息之后，这些保护操作会在下一次扫描内容时撤消。</span><span class="sxs-lookup"><span data-stu-id="00248-339">A DLP policy can enforce protective actions on content containing sensitive information, and if the sensitive information is removed from the content, those protective actions are undone the next time the content's scanned.</span></span> <span data-ttu-id="00248-340">但如果对包含敏感信息的内容应用了保留策略或标签，则该操作是一次性操作，即使删除了敏感信息也不会撤消该操作。</span><span class="sxs-lookup"><span data-stu-id="00248-340">But if a retention policy or label is applied to content containing sensitive information, that's a one-time action that won't be undone even if the sensitive information is removed.</span></span>
  
<span data-ttu-id="00248-341">在 DLP 策略中使用标签作为条件之后，可对包含该标签的内容执行保留和保护操作。</span><span class="sxs-lookup"><span data-stu-id="00248-341">By using a label as a condition in a DLP policy, you can enforce both retention and protection actions on content with that label.</span></span> <span data-ttu-id="00248-342">可将带标签的内容完全视为包含敏感信息的内容；标签和敏感信息类型都是用于对内容进行分类的属性，以便对该内容执行操作。</span><span class="sxs-lookup"><span data-stu-id="00248-342">You can think of content containing a label exactly like content containing sensitive information - both a label and a sensitive information type are properties used to classify content, so that you can enforce actions on that content.</span></span>
  
![使用标签作为条件的 DLP 策略图表](../media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a><span data-ttu-id="00248-344">简单设置与高级设置</span><span class="sxs-lookup"><span data-stu-id="00248-344">Simple settings vs. advanced settings</span></span>

<span data-ttu-id="00248-345">创建 DLP 策略时，将在简单或高级设置中进行选择：</span><span class="sxs-lookup"><span data-stu-id="00248-345">When you create a DLP policy, you'll choose between simple or advanced settings:</span></span>
  
- <span data-ttu-id="00248-346">**简单设置**，可轻松创建最常见类型的 DLP 策略，无需使用规则编辑器创建或修改规则。</span><span class="sxs-lookup"><span data-stu-id="00248-346">**Simple settings** make it easy to create the most common type of DLP policy without using the rule editor to create or modify rules.</span></span> 
    
- <span data-ttu-id="00248-347">**高级设置**，使用规则编辑器，让使用者可完全控制 DLP 策略的每个设置。</span><span class="sxs-lookup"><span data-stu-id="00248-347">**Advanced settings** use the rule editor to give you complete control over every setting for your DLP policy.</span></span> 
    
<span data-ttu-id="00248-348">不要担心，实际上简单设置和高级设置的工作方式完全相同，都是强制执行由条件和操作组成的规则，只是使用简单设置时，看不到规则编辑器。</span><span class="sxs-lookup"><span data-stu-id="00248-348">Don't worry, under the covers, simple settings and advanced settings work exactly the same, by enforcing rules comprised of conditions and actions -- only with simple settings, you don't see the rule editor.</span></span> <span data-ttu-id="00248-349">这是快速创建 DLP 策略的方法。</span><span class="sxs-lookup"><span data-stu-id="00248-349">It's a quick way to create a DLP policy.</span></span>
  
### <a name="simple-settings"></a><span data-ttu-id="00248-350">简单设置</span><span class="sxs-lookup"><span data-stu-id="00248-350">Simple settings</span></span>

<span data-ttu-id="00248-351">到目前为止，最常见的 DLP 方案是创建策略，帮助保护含敏感信息的内容，防止与组织外人员共享该内容，并采取自动补救措施，例如限制可访问内容的人员、向最终用户或管理员发送通知、对事件进行审核以备后续调查。</span><span class="sxs-lookup"><span data-stu-id="00248-351">By far, the most common DLP scenario is creating a policy to help protect content containing sensitive information from being shared with people outside your organization, and taking an automatic remediating action such as restricting who can access the content, sending end-user or admin notifications, and auditing the event for later investigation.</span></span> <span data-ttu-id="00248-352">人们使用 DLP 防止意外泄露敏感信息。</span><span class="sxs-lookup"><span data-stu-id="00248-352">People use DLP to help prevent the inadvertent disclosure of sensitive information.</span></span>
  
<span data-ttu-id="00248-353">为轻松实现这一目标，创建 DLP 策略时，可选择**使用简单设置**。</span><span class="sxs-lookup"><span data-stu-id="00248-353">To simplify achieving this goal, when you create a DLP policy, you can choose **Use simple settings**.</span></span> <span data-ttu-id="00248-354">这些设置可提供实现最常见 DLP 策略所需的一切，无需使用规则编辑器。</span><span class="sxs-lookup"><span data-stu-id="00248-354">These settings provide everything you need to implement the most common DLP policy, without having to go into the rule editor.</span></span>
  
![DLP 简单和高级设置选项](../media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a><span data-ttu-id="00248-356">高级设置</span><span class="sxs-lookup"><span data-stu-id="00248-356">Advanced settings</span></span>

<span data-ttu-id="00248-357">如需创建自定义程度更高的 DLP 策略，可选择**使用高级设置**。</span><span class="sxs-lookup"><span data-stu-id="00248-357">If you need to create more customized DLP policies, you can choose **Use advanced settings**.</span></span>
  
<span data-ttu-id="00248-358">高级设置会显示规则编辑器，可通过它完全控制每个可能的选项，包括每个规则的实例计数和匹配准确度（可信度级别）。</span><span class="sxs-lookup"><span data-stu-id="00248-358">The advanced settings present you with the rule editor, where you have full control over every possible option, including the instance count and match accuracy (confidence level) for each rule.</span></span>
  
<span data-ttu-id="00248-359">若要快速跳转到某一部分，请单击规则编辑器顶部导航中的项，转到下面的部分。</span><span class="sxs-lookup"><span data-stu-id="00248-359">To jump to a section quickly, click an item in the top navigation of the rule editor to go to that section below.</span></span>
  
![DLP 规则编辑器的顶部导航菜单](../media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a><span data-ttu-id="00248-361">DLP 策略模板</span><span class="sxs-lookup"><span data-stu-id="00248-361">DLP policy templates</span></span>

<span data-ttu-id="00248-362">创建 DLP 策略的第一步是选择要保护的内容。</span><span class="sxs-lookup"><span data-stu-id="00248-362">The first step in creating a DLP policy is choosing what information to protect.</span></span> <span data-ttu-id="00248-363">从 DLP 模板开始创建，无需从头构建一组新规则，无需指出默认应包含哪些信息类型。</span><span class="sxs-lookup"><span data-stu-id="00248-363">By starting with a DLP template, you save the work of building a new set of rules from scratch, and figuring out which types of information should be included by default.</span></span> <span data-ttu-id="00248-364">然后即可添加或修改这些要求，微调规则以满足组织的特定要求。</span><span class="sxs-lookup"><span data-stu-id="00248-364">You can then add to or modify these requirements to fine tune the rule to meet your organization's specific requirements.</span></span>
  
<span data-ttu-id="00248-365">预配置的 DLP 策略模板可帮助你检测特定类型的敏感信息，如 HIPAA 数据、PCI-DSS 数据、格雷姆-里奇-比利雷法案数据，甚至是特定区域设置的个人身份信息 (P.I.)。</span><span class="sxs-lookup"><span data-stu-id="00248-365">A preconfigured DLP policy template can help you detect specific types of sensitive information, such as HIPAA data, PCI-DSS data, Gramm-Leach-Bliley Act data, or even locale-specific personally identifiable information (P.I.).</span></span> <span data-ttu-id="00248-366">要使你能够轻松地查找和保护常见类型的敏感信息，包含在 Microsoft 365 中的策略模板已包含你要开始构建策略所需的最常见的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="00248-366">To make it easy for you to find and protect common types of sensitive information, the policy templates included in Microsoft 365 already contain the most common sensitive information types necessary for you to get started.</span></span>
  
![数据丢失防护策略模板列表，重点放在美国爱国者法案模板上](../media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
<span data-ttu-id="00248-368">组织可能还有自己特定的要求，在这种情况下可通过选择“**自定义策略**”选项从头创建 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="00248-368">Your organization may also have its own specific requirements, in which case you can create a DLP policy from scratch by choosing the **Custom policy** option.</span></span> <span data-ttu-id="00248-369">自定义策略为空，且不包含任何预制定的规则。</span><span class="sxs-lookup"><span data-stu-id="00248-369">A custom policy is empty and contains no premade rules.</span></span> 
  
## <a name="roll-out-dlp-policies-gradually-with-test-mode"></a><span data-ttu-id="00248-370">在测试模式下逐步部署 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="00248-370">Roll out DLP policies gradually with test mode</span></span>

<span data-ttu-id="00248-371">创建 DLP 策略时，您应考虑逐步部署策略，在完全强制执行策略之前评估其影响，并测试其有效性。</span><span class="sxs-lookup"><span data-stu-id="00248-371">When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them.</span></span> <span data-ttu-id="00248-372">例如，你不希望新的 DLP 策略在无意中阻止用户访问需要进行访问才能完成工作所需的上千个文档。</span><span class="sxs-lookup"><span data-stu-id="00248-372">For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.</span></span>
  
<span data-ttu-id="00248-373">如果你创建的 DLP 策略具有较大的潜在影响，建议你按以下顺序执行操作：</span><span class="sxs-lookup"><span data-stu-id="00248-373">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
  
1. <span data-ttu-id="00248-374">**在不使用策略提示的情况下启动测试模式**，然后使用 DLP 报告和任何事件报告评估影响。</span><span class="sxs-lookup"><span data-stu-id="00248-374">**Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact.</span></span> <span data-ttu-id="00248-375">您可以使用 DLP 报告查看匹配策略的次数、位置、类型和严重性。</span><span class="sxs-lookup"><span data-stu-id="00248-375">You can use DLP reports to view the number, location, type, and severity of policy matches.</span></span> <span data-ttu-id="00248-376">根据结果，您可以在需要时微调规则。</span><span class="sxs-lookup"><span data-stu-id="00248-376">Based on the results, you can fine tune the rules as needed.</span></span> <span data-ttu-id="00248-377">在测试模式下，DLP 策略不会影响您组织内的工作人员的工作效率。</span><span class="sxs-lookup"><span data-stu-id="00248-377">In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> 
    
2. <span data-ttu-id="00248-p157">**移动到使用通知和策略提示的测试模式**，以便您可以开始向用户介绍合规性策略，让用户对将要应用的规则做好准备。在这一阶段，您还可以要求用户报告误报，便于您进一步优化规则。</span><span class="sxs-lookup"><span data-stu-id="00248-p157">**Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules.</span></span> 
    
3. <span data-ttu-id="00248-380">**开始完全强制执行策略**，以便应用规则中的操作，并保护内容。</span><span class="sxs-lookup"><span data-stu-id="00248-380">**Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected.</span></span> <span data-ttu-id="00248-381">继续监视 DLP 报告及任何事件报告或通知，确保结果是你所期望的。</span><span class="sxs-lookup"><span data-stu-id="00248-381">Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 

    ![使用测试模式和启用策略的选项](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    <span data-ttu-id="00248-383">你可以随时关闭 DLP 策略，这将影响此策略中的所有规则。</span><span class="sxs-lookup"><span data-stu-id="00248-383">You can turn off a DLP policy at any time, which affects all rules in the policy.</span></span> <span data-ttu-id="00248-384">但是，也可以通过在规则编辑器中切换其状态来单独关闭每个规则。</span><span class="sxs-lookup"><span data-stu-id="00248-384">However, each rule can also be turned off individually by toggling its status in the rule editor.</span></span>

    ![关闭策略中的规则的选项](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    <span data-ttu-id="00248-386">你还可以更改策略中的多个规则的优先级。</span><span class="sxs-lookup"><span data-stu-id="00248-386">You can also change the priority of multiple rules in a policy.</span></span> <span data-ttu-id="00248-387">若要执行此操作，请打开要编辑的策略。</span><span class="sxs-lookup"><span data-stu-id="00248-387">To do that, open a policy for editing.</span></span> <span data-ttu-id="00248-388">在规则行中，选择省略号 (**...**)，然后选择一个选项，例如“**下移**”或“**移到最后**”。</span><span class="sxs-lookup"><span data-stu-id="00248-388">In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.</span></span>

    ![设置规则优先级](../media/dlp-set-rule-priority.png)
  
## <a name="dlp-reports"></a><span data-ttu-id="00248-390">DLP 报告</span><span class="sxs-lookup"><span data-stu-id="00248-390">DLP reports</span></span>

<span data-ttu-id="00248-391">创建并启用 DLP 策略后，你会希望验证这些策略是否按预期工作，以及是否有助于保持合规性。</span><span class="sxs-lookup"><span data-stu-id="00248-391">After you create and turn on your DLP policies, you'll want to verify that they're working as you intended and helping you stay compliant.</span></span> <span data-ttu-id="00248-392">使用 DLP 报告，您可以快速查看随着时间的推移 DLP 策略和规则匹配的次数，以及误报和替代数。</span><span class="sxs-lookup"><span data-stu-id="00248-392">With DLP reports, you can quickly view the number of DLP policy and rule matches over time, and the number of false positives and overrides.</span></span> <span data-ttu-id="00248-393">对于每个报告，您都可以按位置、时间范围，甚至缩小为特定的策略、规则或操作来筛选这些匹配项。</span><span class="sxs-lookup"><span data-stu-id="00248-393">For each report, you can filter those matches by location, time frame, and even narrow it down to a specific policy, rule, or action.</span></span>
  
<span data-ttu-id="00248-394">使用 DLP 报告，您可以获取业务见解并了解以下内容：</span><span class="sxs-lookup"><span data-stu-id="00248-394">With the DLP reports, you can get business insights and:</span></span>
  
- <span data-ttu-id="00248-395">重点关注特定的时间段，并了解峰值和发展趋势的原因。</span><span class="sxs-lookup"><span data-stu-id="00248-395">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
- <span data-ttu-id="00248-396">发现违反贵组织的合规性策略的业务流程。</span><span class="sxs-lookup"><span data-stu-id="00248-396">Discover business processes that violate your organization's compliance policies.</span></span>
    
- <span data-ttu-id="00248-397">了解 DLP 策略的任何业务影响。</span><span class="sxs-lookup"><span data-stu-id="00248-397">Understand any business impact of the DLP policies.</span></span>
    
<span data-ttu-id="00248-398">此外，您可以使用 DLP 报告在运行时微调您的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="00248-398">In addition, you can use the DLP reports to fine tune your DLP policies as you run them.</span></span>
  
![安全与合规中心的报表仪表板](../media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a><span data-ttu-id="00248-400">DLP 策略的工作原理</span><span class="sxs-lookup"><span data-stu-id="00248-400">How DLP policies work</span></span>

<span data-ttu-id="00248-p162">DLP 使用深入内容分析（而不仅仅是简单的文本扫描）来检测敏感信息。这种深入内容分析使用关键字匹配、字典匹配、正则表达式评估、内部函数以及其他方法来检测匹配 DLP 策略的内容。您的数据中可能只有一小部分数据被视为敏感数据。DLP 策略可以只识别、监视和自动保护那些敏感数据，而不会妨碍或影响处理您的内容的其余部分的人员。</span><span class="sxs-lookup"><span data-stu-id="00248-p162">DLP detects sensitive information by using deep content analysis (not just a simple text scan). This deep content analysis uses keyword matches, dictionary matches, the evaluation of regular expressions, internal functions, and other methods to detect content that matches your DLP policies. Potentially only a small percentage of your data is considered sensitive. A DLP policy can identify, monitor, and automatically protect just that data, without impeding or affecting people who work with the rest of your content.</span></span>
  
### <a name="policies-are-synced"></a><span data-ttu-id="00248-405">策略会进行同步</span><span class="sxs-lookup"><span data-stu-id="00248-405">Policies are synced</span></span>

<span data-ttu-id="00248-406">在安全 &amp; 合规中心创建 DLP 策略后，它将存储在中心策略存储中，然后同步到各种内容源，其中包括：</span><span class="sxs-lookup"><span data-stu-id="00248-406">After you create a DLP policy in the Security &amp; Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="00248-407">Exchange Online，并从它同步到 Outlook 网页版和 Outlook</span><span class="sxs-lookup"><span data-stu-id="00248-407">Exchange Online, and from there to Outlook on the web and Outlook</span></span>
    
- <span data-ttu-id="00248-408">OneDrive for Business 站点</span><span class="sxs-lookup"><span data-stu-id="00248-408">OneDrive for Business sites</span></span>
    
- <span data-ttu-id="00248-409">SharePoint Online 站点</span><span class="sxs-lookup"><span data-stu-id="00248-409">SharePoint Online sites</span></span>
    
- <span data-ttu-id="00248-410">Office 桌面程序（Excel、PowerPoint 和 Word）</span><span class="sxs-lookup"><span data-stu-id="00248-410">Office desktop programs (Excel, PowerPoint, and Word)</span></span>

- <span data-ttu-id="00248-411">Microsoft Teams 频道和聊天消息</span><span class="sxs-lookup"><span data-stu-id="00248-411">Microsoft Teams channels and chat messages</span></span>
    
<span data-ttu-id="00248-412">该策略同步到正确的位置后，它将开始评估内容并强制执行操作。</span><span class="sxs-lookup"><span data-stu-id="00248-412">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a><span data-ttu-id="00248-413">OneDrive for Business 和 SharePoint Online 站点中的策略评估</span><span class="sxs-lookup"><span data-stu-id="00248-413">Policy evaluation in OneDrive for Business and SharePoint Online sites</span></span>

<span data-ttu-id="00248-414">文档在你的所有 SharePoint Online 站点和 OneDrive for Business 站点中会不断更改，用户会持续对文档执行创建、编辑、共享等操作。</span><span class="sxs-lookup"><span data-stu-id="00248-414">Across all of your SharePoint Online sites and OneDrive for Business sites, documents are constantly changing — they're continually being created, edited, shared, and so on.</span></span> <span data-ttu-id="00248-415">这意味着文档可能随时会与 DLP 策略发生冲突，或变为合规状态。</span><span class="sxs-lookup"><span data-stu-id="00248-415">This means documents can conflict or become compliant with a DLP policy at any time.</span></span> <span data-ttu-id="00248-416">例如，一个用户上载的文档可能不包含与团队站点相关的敏感信息，但之后，另一个客户可能会编辑同一文档，并向文档添加了敏感信息。</span><span class="sxs-lookup"><span data-stu-id="00248-416">For example, a person can upload a document that contains no sensitive information to their team site, but later, a different person can edit the same document and add sensitive information to it.</span></span>
  
<span data-ttu-id="00248-417">为此，DLP 策略经常检查后台中是否包含与策略相符的文档。</span><span class="sxs-lookup"><span data-stu-id="00248-417">For this reason, DLP policies check documents for policy matches frequently in the background.</span></span> <span data-ttu-id="00248-418">您可以将这视为异步策略评估。</span><span class="sxs-lookup"><span data-stu-id="00248-418">You can think of this as asynchronous policy evaluation.</span></span>
<!-- what is the frequency? looks like it is tied to the search crawl schedule -->
  
#### <a name="how-it-works"></a><span data-ttu-id="00248-419">运作方式</span><span class="sxs-lookup"><span data-stu-id="00248-419">How it works</span></span>
 
<span data-ttu-id="00248-420">在用户添加或更改其站点中的文档时，搜索引擎会扫描内容，以便你稍后对其进行搜索。</span><span class="sxs-lookup"><span data-stu-id="00248-420">As people add or change documents in their sites, the search engine scans the content, so that you can search for it later.</span></span> <span data-ttu-id="00248-421">同时，还对此内容进行敏感信息扫描，以检查是否进行过共享。</span><span class="sxs-lookup"><span data-stu-id="00248-421">While this is happening, the content's also scanned for sensitive information and to check if it's shared.</span></span> <span data-ttu-id="00248-422">找到的任何敏感信息都安全地存储在搜索索引中，以便仅供合规性团队而不是典型用户进行访问。</span><span class="sxs-lookup"><span data-stu-id="00248-422">Any sensitive information that's found is stored securely in the search index, so that only the compliance team can access it, but not typical users.</span></span> <span data-ttu-id="00248-423">已启用的每个 DLP 策略在后台（异步）运行，它会经常检查搜索中是否包含与某个策略相符的内容，并应用操作以防止由于疏忽而导致泄漏。</span><span class="sxs-lookup"><span data-stu-id="00248-423">Each DLP policy that you've turned on runs in the background (asynchronously), checking search frequently for any content that matches a policy, and applying actions to protect it from inadvertent leaks.</span></span>
  
![显示 DLP 策略如何异步计算内容的图表](../media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<!-- conflict with a DLP policy is bad wording --><span data-ttu-id="00248-p166"> 最后，文档可能与 DLP 策略相冲突，但也可能符合 DLP 策略。例如，如果用户将信用卡号添加到文档，可能会导致 DLP 策略自动阻止对该文档的访问。但是，如果该用户稍后删除此敏感信息，则下一次根据此策略对此文档进行评估时，该操作（在这种情况下，阻止操作）将自动撤消。</span><span class="sxs-lookup"><span data-stu-id="00248-p166"> Finally, documents can conflict with a DLP policy, but they can also become compliant with a DLP policy. For example, if a person adds credit card numbers to a document, it might cause a DLP policy to block access to the document automatically. But if the person later removes the sensitive information, the action (in this case, blocking) is automatically undone the next time the document is evaluated against the policy.</span></span>
  
<span data-ttu-id="00248-428">DLP 评估可编制索引的任何内容。</span><span class="sxs-lookup"><span data-stu-id="00248-428">DLP evaluates any content that can be indexed.</span></span> <span data-ttu-id="00248-429">有关默认的爬网文件类型的详细信息，请参阅 [SharePoint Server 中的默认爬网文件扩展名和分析文件类型](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)。</span><span class="sxs-lookup"><span data-stu-id="00248-429">For more information on what file types are crawled by default, see [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).</span></span>
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a><span data-ttu-id="00248-430">Exchange Online、Outlook 和 Outlook 网页版中的策略评估</span><span class="sxs-lookup"><span data-stu-id="00248-430">Policy evaluation in Exchange Online, Outlook, and Outlook on the web</span></span>

<span data-ttu-id="00248-431">当创建一个将 Exchange Online 包含为位置的 DLP 策略时，系统会将策略从 Office 365 安全 &amp; 合规中心同步到 Exchange Online，然后从 Exchange Online 同步到 Outlook 网页版和 Outlook。</span><span class="sxs-lookup"><span data-stu-id="00248-431">When you create a DLP policy that includes Exchange Online as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to Exchange Online, and then from Exchange Online to Outlook on the web and Outlook.</span></span>
  
<span data-ttu-id="00248-432">在 Outlook 中撰写消息时，会显示策略提示，因为会根据 DLP 策略对创建的内容进行评估。</span><span class="sxs-lookup"><span data-stu-id="00248-432">When a message is being composed in Outlook, the user can see policy tips as the content being created is evaluated against DLP policies.</span></span> <span data-ttu-id="00248-433">邮件发送后，会根据 DLP 策略对其进行评估，作为邮件流程的正常部分，还会使用 Exchange 管理中心中创建的 Exchange 邮件流规则（也称为传输规则）和 DLP 策略进行评估。</span><span class="sxs-lookup"><span data-stu-id="00248-433">And after a message is sent, it's evaluated against DLP policies as a normal part of mail flow, along with Exchange mail flow rules (also known as transport rules) and DLP policies created in the Exchange admin center.</span></span> <span data-ttu-id="00248-434">DLP 策略会扫描邮件及其所有附件。</span><span class="sxs-lookup"><span data-stu-id="00248-434">DLP policies scan both the message and any attachments.</span></span>
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a><span data-ttu-id="00248-435">Office 桌面程序中的策略评估</span><span class="sxs-lookup"><span data-stu-id="00248-435">Policy evaluation in the Office desktop programs</span></span>

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
<span data-ttu-id="00248-436">Excel、PowerPoint 和 Word 包含相同的功能，可像 SharePoint Online 和 OneDrive for Business 一样识别敏感信息和应用 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="00248-436">Excel, PowerPoint, and Word include the same capability to identify sensitive information and apply DLP policies as SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="00248-437">这些 Office 程序直接从中心策略存储同步其 DLP 策略，然后在用户处理从包含在 DLP 策略中的网站打开的文档时，不断根据 DLP 策略对内容进行评估。</span><span class="sxs-lookup"><span data-stu-id="00248-437">These Office programs sync their DLP policies directly from the central policy store, and then continuously evaluate the content against the DLP policies when people work with documents opened from a site that's included in a DLP policy.</span></span>
  
<span data-ttu-id="00248-438">Office 中的 DLP 策略评估旨在不对程序的性能或处理内容的用户的工作效率产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="00248-438">DLP policy evaluation in Office is designed not to affect the performance of the programs or the productivity of people working on content.</span></span> <span data-ttu-id="00248-439">如果他们正在处理大型文档，或用户的计算机正忙，可能需要几秒钟才能显示策略提示。</span><span class="sxs-lookup"><span data-stu-id="00248-439">If they're working on a large document, or the user's computer is busy, it might take a few seconds for a policy tip to appear.</span></span>

### <a name="policy-evaluation-in-microsoft-teams"></a><span data-ttu-id="00248-440">Microsoft Teams 中的策略评估</span><span class="sxs-lookup"><span data-stu-id="00248-440">Policy evaluation in Microsoft Teams</span></span>
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

<span data-ttu-id="00248-441">当创建一个将 Microsoft Teams 包含为位置的 DLP 策略时，系统会将策略从 Office 365 安全 &amp; 合规中心同步到用户帐户和 Microsoft Teams 频道和聊天消息。</span><span class="sxs-lookup"><span data-stu-id="00248-441">When you create a DLP policy that includes Microsoft Teams as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to user accounts and Microsoft Teams channels and chat messages.</span></span> <span data-ttu-id="00248-442">根据 DLP 策略的配置方式，当某人尝试在 Microsoft Teams 聊天或频道消息中共享敏感信息时，可以阻止或撤消该消息。</span><span class="sxs-lookup"><span data-stu-id="00248-442">Depending on how DLP policies are configured, when someone attempts to share sensitive information in a Microsoft Teams chat or channel message, the message can be blocked or revoked.</span></span> <span data-ttu-id="00248-443">并且，这些用户将无法打开包含敏感信息以及与来宾（外部用户）共享的文档。</span><span class="sxs-lookup"><span data-stu-id="00248-443">And, documents that contain sensitive information and that are shared with guests (external users) won't open for those users.</span></span> <span data-ttu-id="00248-444">若要了解详细信息，请参阅[数据丢失防护和 Microsoft Teams](dlp-microsoft-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="00248-444">To learn more, see [Data loss prevention and Microsoft Teams](dlp-microsoft-teams.md).</span></span>
 
## <a name="permissions"></a><span data-ttu-id="00248-445">权限</span><span class="sxs-lookup"><span data-stu-id="00248-445">Permissions</span></span>

<span data-ttu-id="00248-446">创建 DLP 策略的合规性团队成员需要具有对安全 &amp; 合规中心的访问权限。</span><span class="sxs-lookup"><span data-stu-id="00248-446">Members of your compliance team who will create DLP policies need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="00248-447">默认情况下，租户管理员将有权访问此位置，并可授予合规部主管和其他人访问安全 &amp; 合规中心的权限，而不为其提供租户管理员的所有权限。为此，我们建议你：</span><span class="sxs-lookup"><span data-stu-id="00248-447">By default, your tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you:</span></span>
  
1. <span data-ttu-id="00248-448">在 Microsoft 365 中创建组并向其添加合规部主管。</span><span class="sxs-lookup"><span data-stu-id="00248-448">Create a group in Microsoft 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="00248-449">在安全 &amp; 合规中心的“**权限**”页面上创建一个角色组。</span><span class="sxs-lookup"><span data-stu-id="00248-449">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 
    
3. <span data-ttu-id="00248-450">将 Microsoft 365 组添加到角色组。</span><span class="sxs-lookup"><span data-stu-id="00248-450">Add the Microsoft 365 group to the role group.</span></span>
    
<span data-ttu-id="00248-451">有关详细信息，请访问[向用户授予对 Office 365 合规中心的访问权限](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="00248-451">For more information, see [Give users access to the Office 365 Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="00248-452">只有在创建和应用 DLP 策略时才需要这些权限。</span><span class="sxs-lookup"><span data-stu-id="00248-452">These permissions are required only to create and apply a DLP policy.</span></span> <span data-ttu-id="00248-453">策略执行不需要访问此内容。</span><span class="sxs-lookup"><span data-stu-id="00248-453">Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-dlp-cmdlets"></a><span data-ttu-id="00248-454">查找 DLP cmdlet</span><span class="sxs-lookup"><span data-stu-id="00248-454">Find the DLP cmdlets</span></span>

<span data-ttu-id="00248-455">若要使用安全 &amp; 合规中心的大多数 cmdlet，你需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="00248-455">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="00248-456">使用远程 PowerShell 连接到 Office 365 安全 &amp; 合规中心</span><span class="sxs-lookup"><span data-stu-id="00248-456">Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)
    
2. <span data-ttu-id="00248-457">使用任何[策略和合规性 dlp cmdlet](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/export-dlppolicycollection?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="00248-457">Use any of these [policy-and-compliance-dlp cmdlets](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/export-dlppolicycollection?view=exchange-ps)</span></span>
    
<span data-ttu-id="00248-458">但是，DLP 报告需要从 Microsoft 365（包括 Exchange Online）提取数据。</span><span class="sxs-lookup"><span data-stu-id="00248-458">However, DLP reports need pull data from across Microsoft 365, including Exchange Online.</span></span> <span data-ttu-id="00248-459">因此，**可以在 Exchange Online Powershell 中使用 DLP 报告的 cmdlet，而不能在安全 &amp; 合规中心 Powershell 中使用**。</span><span class="sxs-lookup"><span data-stu-id="00248-459">For this reason, **the cmdlets for the DLP reports are available in Exchange Online Powershell -- not in Security &amp; Compliance Center Powershell**.</span></span> <span data-ttu-id="00248-460">因此，若要使用适用于 DLP 报告的 cmdlet，你需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="00248-460">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="00248-461">使用远程 PowerShell 连接到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="00248-461">Connect to Exchange Online using remote PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)
    
2. <span data-ttu-id="00248-462">对 DLP 报告使用以下任意 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="00248-462">Use any of these cmdlets for the DLP reports:</span></span>
    
    - [<span data-ttu-id="00248-463">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="00248-463">Get-DlpDetectionsReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetectionsReport?view=exchange-ps)

    - [<span data-ttu-id="00248-464">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="00248-464">Get-DlpDetailReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpDetailReport?view=exchange-ps)
    
## <a name="more-information"></a><span data-ttu-id="00248-465">更多信息</span><span class="sxs-lookup"><span data-stu-id="00248-465">More information</span></span>

- [<span data-ttu-id="00248-466">从模板创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="00248-466">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="00248-467">发送通知，并显示 DLP 策略的策略提示</span><span class="sxs-lookup"><span data-stu-id="00248-467">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="00248-468">创建 DLP 策略来保护具有 FCI 或其他属性的文档</span><span class="sxs-lookup"><span data-stu-id="00248-468">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="00248-469">DLP 策略模板包含的内容</span><span class="sxs-lookup"><span data-stu-id="00248-469">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="00248-470">使用敏感信息类型查找什么</span><span class="sxs-lookup"><span data-stu-id="00248-470">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
    
- [<span data-ttu-id="00248-471">DLP 函数查找的内容</span><span class="sxs-lookup"><span data-stu-id="00248-471">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
    
- [<span data-ttu-id="00248-472">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="00248-472">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)