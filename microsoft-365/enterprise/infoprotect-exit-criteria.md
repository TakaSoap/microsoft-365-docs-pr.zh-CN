---
title: 信息保护基础结构退出条件
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 检查基于信息保护的服务和基础结构的条件，确保你的配置满足 Microsoft 365 企业版的要求。
ms.openlocfilehash: 10d7b3b888999b65e5faff81e9a2d32e595294cf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865927"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="92d37-103">信息保护基础结构退出条件</span><span class="sxs-lookup"><span data-stu-id="92d37-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="92d37-104">完成底层基础结构之前，请确保信息保护基础结构满足以下条件。</span><span class="sxs-lookup"><span data-stu-id="92d37-104">Before you are complete with your foundation infrastructure, make sure that your information protection infrastructure meets these conditions.</span></span> 

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="92d37-105">必需：为你的组织定义安全和信息保护级别。</span><span class="sxs-lookup"><span data-stu-id="92d37-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="92d37-p101">已计划并确定组织需要的安全级别。这些级别定义了最低安全级别，以及对敏感信息及其所需数据安全性提升保护的额外安全级别。</span><span class="sxs-lookup"><span data-stu-id="92d37-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="92d37-108">至少，当前需要使用三种安全级别：</span><span class="sxs-lookup"><span data-stu-id="92d37-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="92d37-109">基线</span><span class="sxs-lookup"><span data-stu-id="92d37-109">Baseline</span></span>
- <span data-ttu-id="92d37-110">敏感</span><span class="sxs-lookup"><span data-stu-id="92d37-110">Sensitive</span></span>
- <span data-ttu-id="92d37-111">高度管控</span><span class="sxs-lookup"><span data-stu-id="92d37-111">Highly regulated</span></span>

<span data-ttu-id="92d37-112">如果需要，[步骤 1](infoprotect-define-sec-infoprotect-levels.md) 可以帮助你满足此要求。</span><span class="sxs-lookup"><span data-stu-id="92d37-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-office-365-is-configured"></a><span data-ttu-id="92d37-113">必需：已配置增强的 Office 365 安全性</span><span class="sxs-lookup"><span data-stu-id="92d37-113">Required: Increased security for Office 365 is configured</span></span>

<span data-ttu-id="92d37-114">为了提升安全性，已根据[配置 Office 365 租户以提高安全性](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)中的信息配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="92d37-114">You've configured the following settings for increased security based on the information in [Configure your Office 365 tenant for increased security](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355):</span></span>

- <span data-ttu-id="92d37-115">Office 365 安全与合规中心的威胁管理策略</span><span class="sxs-lookup"><span data-stu-id="92d37-115">Threat management policies in the Office 365 Security & Compliance Center</span></span>
- <span data-ttu-id="92d37-116">其他 Exchange Online 租户范围内设置</span><span class="sxs-lookup"><span data-stu-id="92d37-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="92d37-117">SharePoint 管理中心中的租户范围内共享策略</span><span class="sxs-lookup"><span data-stu-id="92d37-117">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="92d37-118">Azure Active Directory 中的设置</span><span class="sxs-lookup"><span data-stu-id="92d37-118">Settings in Azure Active Directory</span></span>

<span data-ttu-id="92d37-119">此外，已[启用 Office 365 高级威胁防护 (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton)。</span><span class="sxs-lookup"><span data-stu-id="92d37-119">You've also [enabled Office 365 Advanced Threat Protection (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span></span>

<span data-ttu-id="92d37-120">如果需要，请执行[第 3 步](infoprotect-configure-increased-security-office-365.md)，这样做有助于满足此要求。</span><span class="sxs-lookup"><span data-stu-id="92d37-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="92d37-121">可选：已在整个环境中配置分类</span><span class="sxs-lookup"><span data-stu-id="92d37-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="92d37-122">你已与法律和合规性团队合作，为组织数据制定了适当的分类和标签方案，包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="92d37-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data, which include the following:</span></span>

- <span data-ttu-id="92d37-123">敏感数据类型</span><span class="sxs-lookup"><span data-stu-id="92d37-123">Sensitive data types</span></span>
- <span data-ttu-id="92d37-124">Office 365 标签</span><span class="sxs-lookup"><span data-stu-id="92d37-124">Office 365 labels</span></span>
- <span data-ttu-id="92d37-125">Azure 信息保护标签</span><span class="sxs-lookup"><span data-stu-id="92d37-125">Azure Information Protection labels</span></span>

<span data-ttu-id="92d37-126">如果需要，请执行[第 2 步](infoprotect-configure-classification.md)，这样做有助于满足此要求。</span><span class="sxs-lookup"><span data-stu-id="92d37-126">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="92d37-127">可选：配置 Office 365 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="92d37-127">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="92d37-p102">已根据[配置 Office 365 Privileged Access Management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) 主题中的信息启用特权访问，并在 Office 365 组织中创建一个或多个特权访问策略。已配置这些策略，并已启用实时访问权限，可访问敏感数据或关键配置设置。</span><span class="sxs-lookup"><span data-stu-id="92d37-p102">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access  and create one or more privileged access policies in your Office 365 organization. You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="92d37-130">如果需要，请执行[第 4 步](infoprotect-configure-privileged-access-management.md)，这样做有助于满足此要求。</span><span class="sxs-lookup"><span data-stu-id="92d37-130">If needed, [Step 4](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="next-step"></a><span data-ttu-id="92d37-131">后续步骤</span><span class="sxs-lookup"><span data-stu-id="92d37-131">Next Step</span></span>

<span data-ttu-id="92d37-132">现已准备好部署[工作负载和方案](deploy-workloads.md)，如在 Microsoft 365 企业版底层基础结构之上运行的 Microsoft Teams 和 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="92d37-132">You're now ready to deploy [workloads and scenarios](deploy-workloads.md), such as Microsoft Teams and Exchange Online, that run on top of your Microsoft 365 Enterprise foundation infrastructure.</span></span>
