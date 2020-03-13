---
title: 信息保护基础结构退出条件
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 检查基于信息保护的服务和基础结构的条件，确保你的配置满足 Microsoft 365 企业版的要求。
ms.openlocfilehash: 28eff02ea870dcfca7e2e32580ed6a3a9e8a9484
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544161"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="cacc4-103">信息保护基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="cacc4-103">Information protection infrastructure exit criteria</span></span>

![第 6 阶段：信息保护](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="cacc4-105">确保你的信息保护基础结构符合以下必需条件，以及你认为可选的那些条件。</span><span class="sxs-lookup"><span data-stu-id="cacc4-105">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="cacc4-106">必需：为你的组织定义安全和信息保护级别。</span><span class="sxs-lookup"><span data-stu-id="cacc4-106">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="cacc4-p101">已计划并确定组织需要的安全级别。这些级别定义了最低安全级别，以及对敏感信息及其所需数据安全性提升保护的额外安全级别。</span><span class="sxs-lookup"><span data-stu-id="cacc4-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="cacc4-109">至少，当前需要使用三种安全级别：</span><span class="sxs-lookup"><span data-stu-id="cacc4-109">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="cacc4-110">基线</span><span class="sxs-lookup"><span data-stu-id="cacc4-110">Baseline</span></span>
- <span data-ttu-id="cacc4-111">敏感</span><span class="sxs-lookup"><span data-stu-id="cacc4-111">Sensitive</span></span>
- <span data-ttu-id="cacc4-112">高度管控</span><span class="sxs-lookup"><span data-stu-id="cacc4-112">Highly regulated</span></span>

<span data-ttu-id="cacc4-113">如果需要，可在[步骤 1](infoprotect-define-sec-infoprotect-levels.md) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="cacc4-113">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="cacc4-114">必需：已配置增强的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="cacc4-114">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="cacc4-115">你已配置 [Office 365 增强安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)的以下设置：</span><span class="sxs-lookup"><span data-stu-id="cacc4-115">You've configured the following settings for [Office 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="cacc4-116">Microsoft 365 安全中心中的威胁管理策略</span><span class="sxs-lookup"><span data-stu-id="cacc4-116">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="cacc4-117">其他 Exchange Online 租户范围内设置</span><span class="sxs-lookup"><span data-stu-id="cacc4-117">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="cacc4-118">SharePoint Online 管理中心中的租户范围内共享策略</span><span class="sxs-lookup"><span data-stu-id="cacc4-118">Tenant-wide sharing policies in SharePoint Online admin center</span></span>
- <span data-ttu-id="cacc4-119">Azure Active Directory 中的设置 (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="cacc4-119">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="cacc4-120">你还已[启用 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 高级威胁防护 (ATP)](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams)。</span><span class="sxs-lookup"><span data-stu-id="cacc4-120">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="cacc4-121">如果需要，请执行[第 3 步](infoprotect-configure-increased-security-office-365.md)，这样做有助于满足此要求。</span><span class="sxs-lookup"><span data-stu-id="cacc4-121">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="cacc4-122">可选：已在整个环境中配置分类</span><span class="sxs-lookup"><span data-stu-id="cacc4-122">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="cacc4-123">你已与法律和合规性团队合作，为组织数据管理和安全策略制定了适当的分类和标签方案。</span><span class="sxs-lookup"><span data-stu-id="cacc4-123">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data governance and security policies.</span></span> 

<span data-ttu-id="cacc4-124">这些策略对应于以下项的配置和部署：</span><span class="sxs-lookup"><span data-stu-id="cacc4-124">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="cacc4-125">敏感数据类型</span><span class="sxs-lookup"><span data-stu-id="cacc4-125">Sensitive data types</span></span>
- <span data-ttu-id="cacc4-126">保留标签</span><span class="sxs-lookup"><span data-stu-id="cacc4-126">Retention labels</span></span>
- <span data-ttu-id="cacc4-127">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="cacc4-127">Sensitivity labels</span></span>
- <span data-ttu-id="cacc4-128">Azure 信息保护标签</span><span class="sxs-lookup"><span data-stu-id="cacc4-128">Azure Information Protection labels</span></span>

<span data-ttu-id="cacc4-129">如果需要，请执行[第 2 步](infoprotect-configure-classification.md)，这样做有助于满足此要求。</span><span class="sxs-lookup"><span data-stu-id="cacc4-129">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="cacc4-130">可选：在整个环境中部署 Windows 信息保护</span><span class="sxs-lookup"><span data-stu-id="cacc4-130">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="cacc4-131">你已注册 Windows 10 企业版设备，它们部署且应用了定义下列内容的 Intune 策略：</span><span class="sxs-lookup"><span data-stu-id="cacc4-131">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="cacc4-132">要保护的应用。</span><span class="sxs-lookup"><span data-stu-id="cacc4-132">Which apps to protect.</span></span>
- <span data-ttu-id="cacc4-133">保护级别。</span><span class="sxs-lookup"><span data-stu-id="cacc4-133">The level of protection.</span></span>
- <span data-ttu-id="cacc4-134">保护涵盖的范围。</span><span class="sxs-lookup"><span data-stu-id="cacc4-134">Where the protection extends.</span></span>

<span data-ttu-id="cacc4-135">必要时请执行[第 4 步](infoprotect-deploy-windows-information-protection.md)，这样做有助于满足此要求。</span><span class="sxs-lookup"><span data-stu-id="cacc4-135">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="cacc4-136">可选：部署 Office 365 数据丢失防护 (DLP)</span><span class="sxs-lookup"><span data-stu-id="cacc4-136">Optional: Office 365 Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="cacc4-137">你分析、测试并随后推广了 DLP 策略集；该集中注明了位置和条件及操作规则，而且你的组织需要它来保护客户和其他类型的专用数据，并借此满足行业和区域性的法规和要求。</span><span class="sxs-lookup"><span data-stu-id="cacc4-137">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="cacc4-138">数据合规性和安全性员工正在使用 Office 365 安全与合规仪表板来监视 DLP 事件。</span><span class="sxs-lookup"><span data-stu-id="cacc4-138">Your data compliance and security staff are using the Office 365 Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="cacc4-139">必要时请执行[步骤 5](infoprotect-data-loss-prevention.md)，这样做有助于满足此要求。</span><span class="sxs-lookup"><span data-stu-id="cacc4-139">If needed, [Step 5](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a><span data-ttu-id="cacc4-140">必需：为你的组织定义安全和信息保护级别</span><span class="sxs-lookup"><span data-stu-id="cacc4-140">Optional: Email encryption is configured</span></span>

<span data-ttu-id="cacc4-141">已根据组织的需要配置以下电子邮件加密：</span><span class="sxs-lookup"><span data-stu-id="cacc4-141">You've configured the following email encryption as needed for your organization:</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="cacc4-142">**加密方法**</span><span class="sxs-lookup"><span data-stu-id="cacc4-142">**Encryption method**</span></span> | <span data-ttu-id="cacc4-143">**对于已发送的电子邮件**</span><span class="sxs-lookup"><span data-stu-id="cacc4-143">**For email sent**</span></span> |
| [<span data-ttu-id="cacc4-144">Office 365 邮件加密 (OME)</span><span class="sxs-lookup"><span data-stu-id="cacc4-144">Office 365 Message Encryption (OME)</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | <span data-ttu-id="cacc4-145">在组织外部加密</span><span class="sxs-lookup"><span data-stu-id="cacc4-145">Outside your organization with encryption</span></span> |
| [<span data-ttu-id="cacc4-146">信息权限管理 (IRM)</span><span class="sxs-lookup"><span data-stu-id="cacc4-146">Information Rights Management (IRM)</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | <span data-ttu-id="cacc4-147">具有加密和权限</span><span class="sxs-lookup"><span data-stu-id="cacc4-147">With both encryption and permissions</span></span> |
| [<span data-ttu-id="cacc4-148">安全/多用途 Internet 邮件扩展 (S/MIME)</span><span class="sxs-lookup"><span data-stu-id="cacc4-148">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | <span data-ttu-id="cacc4-149">具有加密和数字签名（使用公钥加密）</span><span class="sxs-lookup"><span data-stu-id="cacc4-149">With both encryption and digital signatures using public key cryptography</span></span> |
|||

<span data-ttu-id="cacc4-150">必要时请执行[步骤 6](infoprotect-email-encryption.md)，这样做有助于满足此要求。</span><span class="sxs-lookup"><span data-stu-id="cacc4-150">If needed, [Step 6](infoprotect-email-encryption.md) can help you meet this requirement.</span></span>

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="cacc4-151">可选：配置 Office 365 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="cacc4-151">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="cacc4-152">你已使用[在 Office 365 中配置特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)主题中的信息来启用特权访问并在组织中创建一个或多个特权访问策略。</span><span class="sxs-lookup"><span data-stu-id="cacc4-152">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="cacc4-153">你已配置这些策略，且实时访问已启用，可访问敏感数据或关键配置设置。</span><span class="sxs-lookup"><span data-stu-id="cacc4-153">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="cacc4-154">如果需要，请执行[步骤 7](infoprotect-configure-privileged-access-management.md)，这样做有助于满足此要求。</span><span class="sxs-lookup"><span data-stu-id="cacc4-154">If needed, [Step 7](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="cacc4-155">结果和后续步骤</span><span class="sxs-lookup"><span data-stu-id="cacc4-155">Results and next steps</span></span>

<span data-ttu-id="cacc4-156">Microsoft 365 企业版的信息保护基础结构使用定义的安全级别、Office 365 增强安全性、使用敏感数据和标签的分类、Windows 信息保护、数据丢失防护、电子邮件加密以及特权访问权限管理。</span><span class="sxs-lookup"><span data-stu-id="cacc4-156">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, Windows Information Protection, Data Loss Prevention, email encryption, and privileged access management.</span></span>

<span data-ttu-id="cacc4-157">如果你正在执行 Microsoft 365 企业版端到端部署，那么你现在已准备好让你的[工作负载和应用场景](deploy-workloads.md)充分利用底层基础结构的所有功能和配置。</span><span class="sxs-lookup"><span data-stu-id="cacc4-157">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
