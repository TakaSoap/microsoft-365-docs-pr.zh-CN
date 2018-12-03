---
title: 第 2 步：配置环境分类
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并配置对组织中的数据进行分类的各种方法。
ms.openlocfilehash: bee0885eb3f8899560532895d1558723b281ab02
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865597"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="69ecc-103">第 2 步：配置环境分类</span><span class="sxs-lookup"><span data-stu-id="69ecc-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="69ecc-104">\*\* 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本</span><span class="sxs-lookup"><span data-stu-id="69ecc-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="69ecc-105">在步骤此中，配合法律和合规性团队来定义组织数据的分类方案。</span><span class="sxs-lookup"><span data-stu-id="69ecc-105">In Step 3, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-classifications"></a><span data-ttu-id="69ecc-106">Microsoft 分类</span><span class="sxs-lookup"><span data-stu-id="69ecc-106">Microsoft classifications</span></span>

<span data-ttu-id="69ecc-107">Microsoft 365 包括三种类型的分类：</span><span class="sxs-lookup"><span data-stu-id="69ecc-107">Microsoft 365 includes three types of classification:</span></span>

- <span data-ttu-id="69ecc-108">Office 365 敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="69ecc-108">Sensitive information types for Office 365</span></span>
- <span data-ttu-id="69ecc-109">Office 365 标签</span><span class="sxs-lookup"><span data-stu-id="69ecc-109">Office 365 labels</span></span>
- <span data-ttu-id="69ecc-110">Azure 信息保护标签和保护</span><span class="sxs-lookup"><span data-stu-id="69ecc-110">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types-for-office-365"></a><span data-ttu-id="69ecc-111">Office 365 敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="69ecc-111">Sensitive information types for Office 365</span></span>

<span data-ttu-id="69ecc-p101">Office 365 敏感信息类型定义了自动化过程（如搜索）如何识别运行状况服务号和信用卡号等的特定信息类型。使用敏感信息类型可以查找敏感数据，并应用数据丢失防护规则和策略来保护此数据。有关详细信息，请参阅[数据丢失防护策略概述](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)。例如，敏感信息类型对于满足合规性和法规要求（如一般数据保护条例 (GDPR)）特别有帮助。</span><span class="sxs-lookup"><span data-stu-id="69ecc-p101">Sensitive information types for Office 365 define how automated processes such as search recognize specific information types such as health service numbers and credit card numbers. You use sensitive information types to find sensitive data and apply data loss prevention rules and policies to protect this data. For more information, see [Overview of data loss prevention policies](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). For example, sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="office-365-labels"></a><span data-ttu-id="69ecc-116">Office 365 标签</span><span class="sxs-lookup"><span data-stu-id="69ecc-116">Office 365 labels</span></span>
<span data-ttu-id="69ecc-p102">可将 Office 365 标签用于存储在 SharePoint Online 和 OneDrive for Business 中的个人数据和高度管控文件以及商业机密文件。有关详细信息（包括如何创建它们），请参阅[标签概述](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30)。</span><span class="sxs-lookup"><span data-stu-id="69ecc-p102">You can use Office 365 labels for personal data and for highly regulated and trade secret files stored in SharePoint Online and OneDrive for Business. For more information, including how to create them, see [Overview of labels](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).</span></span>

<span data-ttu-id="69ecc-p103">如果决定使用 Office 365 标签，应为每个级别的保护配置至少一个标签。例如，为以下安全级别创建三个标签：</span><span class="sxs-lookup"><span data-stu-id="69ecc-p103">If you decide to use Office 365 labels, you should configure at least one for each level of protection. For example, create three labels for:</span></span>

- <span data-ttu-id="69ecc-121">基线</span><span class="sxs-lookup"><span data-stu-id="69ecc-121">Baseline</span></span>
- <span data-ttu-id="69ecc-122">敏感</span><span class="sxs-lookup"><span data-stu-id="69ecc-122">Sensitive</span></span>
- <span data-ttu-id="69ecc-123">高度管控</span><span class="sxs-lookup"><span data-stu-id="69ecc-123">Highly regulated</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="69ecc-124">Azure 信息保护标签和保护</span><span class="sxs-lookup"><span data-stu-id="69ecc-124">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="69ecc-p104">可使用 Azure 信息保护标签进行分类，并选择性地保护组织文档和电子邮件。这些标签可应用到存储在 Office 365 外部的文档。这些标签即可以由定义规则和条件的管理员自动应用，也可以由用户手动应用，或者可以在建议的情况下用户通过组合这两种方式来应用标签。</span><span class="sxs-lookup"><span data-stu-id="69ecc-p104">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails. These labels can apply to documents that are stored outside of Office 365. These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="69ecc-128">若要规划和部署 Azure 信息保护标签和保护，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="69ecc-128">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="69ecc-129">审阅 [Azure 信息保护要求](https://docs.microsoft.com/information-protection/get-started/requirements)。</span><span class="sxs-lookup"><span data-stu-id="69ecc-129">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="69ecc-130">请按照[分类、标签和保护的部署路线图](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection)。</span><span class="sxs-lookup"><span data-stu-id="69ecc-130">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="69ecc-131">有关详细信息，请参阅 [Azure 信息保护文档库](https://docs.microsoft.com/information-protection/)。</span><span class="sxs-lookup"><span data-stu-id="69ecc-131">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

## <a name="classification-for-gdpr"></a><span data-ttu-id="69ecc-132">GDPR 分类</span><span class="sxs-lookup"><span data-stu-id="69ecc-132">Classification for GDPR</span></span>

<span data-ttu-id="69ecc-133">有关包括个人数据的 GDPR 分类方案示例，请参阅[为个人数据构建分类方案](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data)。</span><span class="sxs-lookup"><span data-stu-id="69ecc-133">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="69ecc-135">测试实验室指南：数据分类</span><span class="sxs-lookup"><span data-stu-id="69ecc-135">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="69ecc-136">作为临时检查点，请查看对应于此步骤的[退出条件](infoprotect-exit-criteria.md#crit-infoprotect-step3)。</span><span class="sxs-lookup"><span data-stu-id="69ecc-136">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="69ecc-137">后续步骤</span><span class="sxs-lookup"><span data-stu-id="69ecc-137">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="69ecc-138">为 Office 365 配置提高的安全性</span><span class="sxs-lookup"><span data-stu-id="69ecc-138">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

