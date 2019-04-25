---
title: 信息保护基础结构退出条件
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 检查基于信息保护的服务和基础结构的条件，确保你的配置满足 Microsoft 365 企业版的要求。
ms.openlocfilehash: 681b3bb2500680b4f5d5801486347aec1b801714
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283690"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="3065e-103">信息保护基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="3065e-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="3065e-104">确保你的信息保护基础结构符合以下必需条件，以及你认为可选的那些条件。</span><span class="sxs-lookup"><span data-stu-id="3065e-104">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="3065e-105">必需：为你的组织定义安全和信息保护级别。</span><span class="sxs-lookup"><span data-stu-id="3065e-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="3065e-p101">已计划并确定组织需要的安全级别。这些级别定义了最低安全级别，以及对敏感信息及其所需数据安全性提升保护的额外安全级别。</span><span class="sxs-lookup"><span data-stu-id="3065e-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="3065e-108">至少，当前需要使用三种安全级别：</span><span class="sxs-lookup"><span data-stu-id="3065e-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="3065e-109">基线</span><span class="sxs-lookup"><span data-stu-id="3065e-109">Baseline</span></span>
- <span data-ttu-id="3065e-110">敏感</span><span class="sxs-lookup"><span data-stu-id="3065e-110">Sensitive</span></span>
- <span data-ttu-id="3065e-111">高度管控</span><span class="sxs-lookup"><span data-stu-id="3065e-111">Highly regulated</span></span>

<span data-ttu-id="3065e-112">如果需要，可在[步骤 1](infoprotect-define-sec-infoprotect-levels.md) 中进行设置以满足此要求。</span><span class="sxs-lookup"><span data-stu-id="3065e-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="3065e-113">必需：已配置增强的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="3065e-113">Required: Increased security for Office 365 is configured</span></span>

<span data-ttu-id="3065e-114">你已配置 [Office 365 增强安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)的以下设置：</span><span class="sxs-lookup"><span data-stu-id="3065e-114">You've configured the following settings for increased security based on the information in [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="3065e-115">Microsoft 365 安全中心中的威胁管理策略</span><span class="sxs-lookup"><span data-stu-id="3065e-115">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="3065e-116">其他 Exchange Online 租户范围内设置</span><span class="sxs-lookup"><span data-stu-id="3065e-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="3065e-117">SharePoint 管理中心中的租户范围内共享策略</span><span class="sxs-lookup"><span data-stu-id="3065e-117">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="3065e-118">Azure Active Directory 中的设置 (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="3065e-118">CORS support in Microsoft Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="3065e-119">你还已[启用 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 高级威胁防护 (ATP)](https://docs.microsoft.com/zh-CN/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams)。</span><span class="sxs-lookup"><span data-stu-id="3065e-119">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/zh-CN/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="3065e-120">如果需要，请执行[第 3 步](infoprotect-configure-increased-security-office-365.md)，这样做有助于满足此要求。</span><span class="sxs-lookup"><span data-stu-id="3065e-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="3065e-121">可选：已在整个环境中配置分类</span><span class="sxs-lookup"><span data-stu-id="3065e-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="3065e-122">你已与法律和合规性团队合作，为组织数据管理和安全策略制定了适当的分类和标签方案。</span><span class="sxs-lookup"><span data-stu-id="3065e-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data, which include the following:</span></span> 

<span data-ttu-id="3065e-123">这些策略对应于以下项的配置和部署：</span><span class="sxs-lookup"><span data-stu-id="3065e-123">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="3065e-124">敏感数据类型</span><span class="sxs-lookup"><span data-stu-id="3065e-124">Sensitive data types</span></span>
- <span data-ttu-id="3065e-125">保留标签</span><span class="sxs-lookup"><span data-stu-id="3065e-125">Retention labels</span></span>
- <span data-ttu-id="3065e-126">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="3065e-126">Sensitivity labels</span></span>
- <span data-ttu-id="3065e-127">Azure 信息保护标签</span><span class="sxs-lookup"><span data-stu-id="3065e-127">Azure Information Protection labels</span></span>

<span data-ttu-id="3065e-128">如果需要，请执行[第 2 步](infoprotect-configure-classification.md)，这样做有助于满足此要求。</span><span class="sxs-lookup"><span data-stu-id="3065e-128">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="3065e-129">可选：配置 Office 365 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="3065e-129">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="3065e-130">你已使用[在 Office 365 中配置特权访问管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)主题中的信息来启用特权访问并在组织中创建一个或多个特权访问策略。</span><span class="sxs-lookup"><span data-stu-id="3065e-130">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access  and create one or more privileged access policies in your Office 365 organization. You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="3065e-131">你已配置这些策略，且实时访问已启用，可访问敏感数据或关键配置设置。</span><span class="sxs-lookup"><span data-stu-id="3065e-131">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="3065e-132">如果需要，请执行[第 4 步](infoprotect-configure-privileged-access-management.md)，这样做有助于满足此要求。</span><span class="sxs-lookup"><span data-stu-id="3065e-132">If needed, [Step 4](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="3065e-133">结果和后续步骤</span><span class="sxs-lookup"><span data-stu-id="3065e-133">Validation and next steps</span></span>

<span data-ttu-id="3065e-134">Microsoft 365 企业版的信息保护基础结构使用定义的安全级别、Office 365 增强安全性、使用敏感数据和标签的分类以及特权访问权限管理。</span><span class="sxs-lookup"><span data-stu-id="3065e-134">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, and privileged access management.</span></span>

<span data-ttu-id="3065e-135">如果你正在执行 Microsoft 365 企业版端到端部署，那么你现在已准备好让你的[工作负载和应用场景](deploy-workloads.md)充分利用底层基础结构的所有功能和配置。</span><span class="sxs-lookup"><span data-stu-id="3065e-135">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
