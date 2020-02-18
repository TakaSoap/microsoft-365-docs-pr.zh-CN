---
title: 步骤 1：定义安全和信息保护级别
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
description: 了解并为组织配置安全和信息保护级别。
ms.openlocfilehash: d3ba5f490b7aa80c9149a0451059914c78b8f2f1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067209"
---
# <a name="step-1-define-security-and-information-protection-levels"></a><span data-ttu-id="f0633-103">步骤 1：定义安全和信息保护级别</span><span class="sxs-lookup"><span data-stu-id="f0633-103">Step 1: Define security and information protection levels</span></span>

<span data-ttu-id="f0633-104">*此步骤是必需的，适用于 Microsoft 365 企业版的 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="f0633-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![第 6 阶段：信息保护](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="f0633-106">在此步骤中，将为组织定义安全和保护级别。</span><span class="sxs-lookup"><span data-stu-id="f0633-106">In this step, you'll define the levels of security and protection for your organization.</span></span> <span data-ttu-id="f0633-107">例如，销售部门可能仅需要低安全级别，</span><span class="sxs-lookup"><span data-stu-id="f0633-107">For example, your sales department might only require a low security level.</span></span> <span data-ttu-id="f0633-108">但是，研究部门及其极为重要的知识产权信息可能需要高的安全级别，以加密文件并将访问权限限制为仅研究人员。</span><span class="sxs-lookup"><span data-stu-id="f0633-108">However, your research department and its highly valuable intellectual property might require a high security level that encrypts files and limits access to only research staff.</span></span>

<span data-ttu-id="f0633-109">虽然可以定义自己的安全级别而且内部可能已设置了一些，但 Microsoft 建议制定至少使用三个不同级别的、可加以应用的安全和保护计划。</span><span class="sxs-lookup"><span data-stu-id="f0633-109">Although you can define your own security levels and might already have some in place, Microsoft recommends that you develop a plan to use at least three different levels of security and protection that can be applied.</span></span> <span data-ttu-id="f0633-110">下面是一个可帮助你开始的列表：</span><span class="sxs-lookup"><span data-stu-id="f0633-110">Here is a list to get you started:</span></span> 

- <span data-ttu-id="f0633-p103">\*\*\*\* 基线：这是用于保护数据以及访问数据的标识和设备的最低标准。你可以按照基线安全和保护建议提供强的默认保护，以满足许多组织或其部门的需要。</span><span class="sxs-lookup"><span data-stu-id="f0633-p103">**Baseline:** This is a minimum standard for protecting data and for the identities and devices that access your data. You can follow baseline security and protection recommendations to provide strong default protection that meets the needs of many organizations or their departments.</span></span>
- <span data-ttu-id="f0633-p104">\*\*\*\* 敏感：这是对数据子集的额外保护，必须高于基线级别。你可以在 Office 365 环境中将此提升的保护应用于特定数据集。此外，Microsoft 还建议将敏感安全级别应用到访问敏感数据的标识和设备。</span><span class="sxs-lookup"><span data-stu-id="f0633-p104">**Sensitive:** This is additional protection for a subset of your data that must be protected beyond the baseline level. You can apply this increased protection to specific data sets in your Office 365 environment. Microsoft also recommends applying the sensitive security level to identities and devices that access sensitive data.</span></span>
- <span data-ttu-id="f0633-p105">\*\*\*\* 高度管控：这是组织的最高保护级别，通常是高度机密的、视为知识产权或商业机密的小量数据，或必须遵循严格安全规定的数据。Microsoft 365 企业版具有相关功能，可帮助组织满足这些高安全要求，包括对标识和设备的同等保护。</span><span class="sxs-lookup"><span data-stu-id="f0633-p105">**Highly regulated:** This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations. Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span>

<span data-ttu-id="f0633-118">有关详细信息，请参阅[三层保护](microsoft-365-policies-configurations.md#three-tiers-of-protection)。</span><span class="sxs-lookup"><span data-stu-id="f0633-118">For more information, see [Three tiers of protection](microsoft-365-policies-configurations.md#three-tiers-of-protection).</span></span>

<span data-ttu-id="f0633-119">作为临时检查点，请查看对应于此步骤的[退出条件](infoprotect-exit-criteria.md#crit-infoprotect-step1)。</span><span class="sxs-lookup"><span data-stu-id="f0633-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step1) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="f0633-120">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f0633-120">Next step</span></span>

|||
|:-------|:-----|
|![第 2 步](../media/stepnumbers/Step2.png)|[<span data-ttu-id="f0633-122">配置环境分类</span><span class="sxs-lookup"><span data-stu-id="f0633-122">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
