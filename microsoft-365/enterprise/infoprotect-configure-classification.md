---
title: 第 2 步：配置环境分类
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并配置对组织中的数据进行分类的各种方法。
ms.openlocfilehash: 483549e7eaa7f6b77b775cf35bda7b0f42834ad2
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072252"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="512e3-103">第 2 步：配置环境分类</span><span class="sxs-lookup"><span data-stu-id="512e3-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="512e3-104">\*\* 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本</span><span class="sxs-lookup"><span data-stu-id="512e3-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="512e3-105">在步骤此中，配合法律和合规性团队来定义组织数据的分类方案。</span><span class="sxs-lookup"><span data-stu-id="512e3-105">In this step, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-365-classification-types"></a><span data-ttu-id="512e3-106">Microsoft 365 分类类型</span><span class="sxs-lookup"><span data-stu-id="512e3-106">Microsoft 365 classification types</span></span>

<span data-ttu-id="512e3-107">Microsoft 365 包括四种类型的分类：</span><span class="sxs-lookup"><span data-stu-id="512e3-107">Microsoft 365 includes four types of classification:</span></span>

- <span data-ttu-id="512e3-108">敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="512e3-108">Sensitive information types</span></span>
- <span data-ttu-id="512e3-109">保留标签</span><span class="sxs-lookup"><span data-stu-id="512e3-109">Retention labels</span></span>
- <span data-ttu-id="512e3-110">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="512e3-110">Sensitivity labels</span></span>
- <span data-ttu-id="512e3-111">Azure 信息保护标签和保护</span><span class="sxs-lookup"><span data-stu-id="512e3-111">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="512e3-112">敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="512e3-112">Sensitive information types</span></span>

<span data-ttu-id="512e3-113">Microsoft 365 中的敏感信息类型定义了自动化流程（例如搜索）如何识别特定信息类型。</span><span class="sxs-lookup"><span data-stu-id="512e3-113">Sensitive information types for Microsoft 365 define how automated processes such as search recognize specific information types.</span></span> <span data-ttu-id="512e3-114">这些信息包括员工或客户的敏感数据，例如医疗服务号码和信用卡号。</span><span class="sxs-lookup"><span data-stu-id="512e3-114">These include sensitive employee or customer data such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="512e3-115">你可以使用敏感信息类型查找敏感数据并应用数据丢失保护 (DLP) 规则策略，以保护这些数据。</span><span class="sxs-lookup"><span data-stu-id="512e3-115">You use sensitive information types to find sensitive data and apply data loss prevention (DLP) rules and policies to protect this data.</span></span> <span data-ttu-id="512e3-116">有关详细信息，请参阅 [DLP 策略包含的内容](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains)。</span><span class="sxs-lookup"><span data-stu-id="512e3-116">For more information, see [what a DLP policy contains](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span></span> 

<span data-ttu-id="512e3-117">敏感信息类型对于满足合规性和法规要求（例如通用数据保护条例 (GDPR)）尤其有用。</span><span class="sxs-lookup"><span data-stu-id="512e3-117">Sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="512e3-118">保留标签</span><span class="sxs-lookup"><span data-stu-id="512e3-118">Retention labels</span></span>

<span data-ttu-id="512e3-119">定义数据管理策略的一部分就是确定特定类型的文档或含有特定内容的文档应保留多长时间，以符合组织政策和区域法规要求。</span><span class="sxs-lookup"><span data-stu-id="512e3-119">Part of defining a data governance strategy is deciding how long specific types of documents or documents with specific contents should be retained in compliance with organization policies and regional regulations.</span></span> <span data-ttu-id="512e3-120">例如，某些类型的文档应在保留一段时间之后删除，有些文档则必须永久保留。</span><span class="sxs-lookup"><span data-stu-id="512e3-120">For example, some types of documents should be retained for a set amount of time and then deleted and others must be retained indefinitely.</span></span>

<span data-ttu-id="512e3-121">对于 Microsoft 365 中存储的文档，你可以对 Exchange 电子邮件、SharePoint Online、OneDrive for Business 和 Teams 聊天和渠道消息中存储的文档和数据定义并应用保留标签。</span><span class="sxs-lookup"><span data-stu-id="512e3-121">For documents stored in Microsoft 365, you define and apply retention labels to documents and data stored in Exchange email, SharePoint Online, OneDrive for Business, and Teams chat and channel messages.</span></span> 

<span data-ttu-id="512e3-122">如果使用保留标签，则应为需要应用保留标签的每个类别的文件创建标签。</span><span class="sxs-lookup"><span data-stu-id="512e3-122">If you use retention labels, you should configure a label for each category of file that needs to have a retention policy applied.</span></span> <span data-ttu-id="512e3-123">在保留标签中，你可以指定：</span><span class="sxs-lookup"><span data-stu-id="512e3-123">Within the retention label, you can specify:</span></span>

- <span data-ttu-id="512e3-124">一组文件描述符（例如，按业务部门、文件类别或法规）。</span><span class="sxs-lookup"><span data-stu-id="512e3-124">A set of descriptors for the files (for example, by business department, file category, or regulation).</span></span>
- <span data-ttu-id="512e3-125">已附加保留标签的文件的保留设置，例如保留时间以及达到保留时间之后的行为。</span><span class="sxs-lookup"><span data-stu-id="512e3-125">The retention settings for the files that have the retention label attached, such as retain times and behaviors after the retain time has been reached.</span></span>

<span data-ttu-id="512e3-126">也可以通过配置 SharePoint Online 网站将默认保留标签应用到网站中的所有新文档，以此为文件自动应用保留标签。</span><span class="sxs-lookup"><span data-stu-id="512e3-126">You can also apply a retention label to files automatically by configuring a SharePoint Online site to apply a default retention label to all new documents in the site.</span></span> 

<span data-ttu-id="512e3-127">有关详细信息，请参阅[保留标签概述](https://docs.microsoft.com/office365/securitycompliance/labels)。</span><span class="sxs-lookup"><span data-stu-id="512e3-127">For more information, see the [overview of retention labels](https://docs.microsoft.com/office365/securitycompliance/labels).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="512e3-128">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="512e3-128">Sensitivity labels</span></span>

<span data-ttu-id="512e3-129">为特定类型的文档或含有特定内容的文档提供保护和实施安全措施的一部分就是将其贴上标签，以便应用其他安全性。</span><span class="sxs-lookup"><span data-stu-id="512e3-129">Part of protecting and implementing security for specific types of documents or documents with specific contents is marking them with a label so that the additional security can be applied.</span></span> <span data-ttu-id="512e3-130">借助 Microsoft 365 中的敏感度标签，你可以：</span><span class="sxs-lookup"><span data-stu-id="512e3-130">With sensitivity labels in Microsoft 365, you can:</span></span>

- <span data-ttu-id="512e3-131">执行保护设置，例如加密、权限或添加水印。</span><span class="sxs-lookup"><span data-stu-id="512e3-131">Enforce protection settings such as encryption, permissions, or adding a watermark.</span></span>
- <span data-ttu-id="512e3-132">使用 Microsoft Intune 中的终结点保护功能，防止运行 Windows 的设备上的敏感内容流出你的组织。</span><span class="sxs-lookup"><span data-stu-id="512e3-132">Prevent sensitive content from leaving your organization on devices running Windows, by using endpoint protection in Microsoft Intune.</span></span> 
- <span data-ttu-id="512e3-133">使用 Windows 信息保护 (WIP) 终结点保护阻止此类内容被复制到第三方应用（如 Twitter 或 Gmail），或者被复制到可移除存储设备（如 U 盘）。</span><span class="sxs-lookup"><span data-stu-id="512e3-133">Use Windows Information Protection (WIP) endpoint protection to prevent that content from being copied to a third-party app, such as Twitter or Gmail, or being copied to removable storage, such as a USB drive.</span></span>
- <span data-ttu-id="512e3-134">使用 Microsoft Cloud App Security 保护第三方应用和服务中的内容。</span><span class="sxs-lookup"><span data-stu-id="512e3-134">Use Microsoft Cloud App Security to protect content in third-party apps and services.</span></span> 
- <span data-ttu-id="512e3-135">对内容进行分类，无需使用任何保护设置。</span><span class="sxs-lookup"><span data-stu-id="512e3-135">Classify content without using any protection settings.</span></span>

<span data-ttu-id="512e3-136">如果使用敏感度标签，则应为每个安全和信息保护级别配置标签。</span><span class="sxs-lookup"><span data-stu-id="512e3-136">If you use sensitivity labels, you should configure a label for each security and information protection level.</span></span> <span data-ttu-id="512e3-137">例如，为以下对象创建三个敏感度标签：</span><span class="sxs-lookup"><span data-stu-id="512e3-137">For example, create three sensitivity labels for:</span></span>

- <span data-ttu-id="512e3-138">基线</span><span class="sxs-lookup"><span data-stu-id="512e3-138">Baseline</span></span>
- <span data-ttu-id="512e3-139">敏感</span><span class="sxs-lookup"><span data-stu-id="512e3-139">Sensitive</span></span>
- <span data-ttu-id="512e3-140">高度管控</span><span class="sxs-lookup"><span data-stu-id="512e3-140">Highly regulated</span></span>

<span data-ttu-id="512e3-141">有关详细信息，请参阅此[敏感度标签概述](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="512e3-141">For more information, see this [overview of sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="512e3-142">Azure 信息保护标签和保护</span><span class="sxs-lookup"><span data-stu-id="512e3-142">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="512e3-143">可以使用 Azure 信息保护标签来分类并选择性地保护组织的文档和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="512e3-143">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails.</span></span> <span data-ttu-id="512e3-144">这些标签可以应用于存储在 Microsoft 365 之外的文档。</span><span class="sxs-lookup"><span data-stu-id="512e3-144">These labels can apply to documents that are stored outside of Microsoft 365.</span></span> <span data-ttu-id="512e3-145">这些标签可以由定义规则和条件的管理员自动应用、由用户手动应用或是组合应用（在这种情况下会向用户提供建议）。</span><span class="sxs-lookup"><span data-stu-id="512e3-145">These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="512e3-146">若要规划和部署 Azure 信息保护标签和保护，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="512e3-146">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="512e3-147">审阅 [Azure 信息保护要求](https://docs.microsoft.com/information-protection/get-started/requirements)。</span><span class="sxs-lookup"><span data-stu-id="512e3-147">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="512e3-148">请按照[分类、标签和保护的部署路线图](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection)。</span><span class="sxs-lookup"><span data-stu-id="512e3-148">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="512e3-149">有关详细信息，请参阅 [Azure 信息保护文档库](https://docs.microsoft.com/information-protection/)。</span><span class="sxs-lookup"><span data-stu-id="512e3-149">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

<span data-ttu-id="512e3-150">现有 Azure 信息保护标签与敏感度标签无缝工作。</span><span class="sxs-lookup"><span data-stu-id="512e3-150">Existing Azure Information Protection labels work seamlessly with sensitivity labels.</span></span> <span data-ttu-id="512e3-151">例如，你可以保留现有 Azure 信息保护标签以及应用于文档和电子邮件的标签。</span><span class="sxs-lookup"><span data-stu-id="512e3-151">For example, you can keep your existing Azure Information Protection labels and the labels that are applied to documents and email.</span></span>

<span data-ttu-id="512e3-152">如果使用了敏感度和 Azure 信息保护标签，则应[将 Azure 信息保护标签迁移到敏感度标签](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels)。</span><span class="sxs-lookup"><span data-stu-id="512e3-152">If you have both sensitivity and Azure Information Protection labels, you should [migrate your Azure Information Protection labels to sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span></span>

## <a name="example-classification-for-gdpr"></a><span data-ttu-id="512e3-153">示例：GDPR 分类</span><span class="sxs-lookup"><span data-stu-id="512e3-153">Example: Classification for GDPR</span></span>

<span data-ttu-id="512e3-154">有关包括个人数据的 GDPR 分类方案示例，请参阅[为个人数据构建分类方案](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data)。</span><span class="sxs-lookup"><span data-stu-id="512e3-154">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

## <a name="take-it-for-a-test-drive"></a><span data-ttu-id="512e3-155">体验一下</span><span class="sxs-lookup"><span data-stu-id="512e3-155">Take it for a test drive</span></span>

|||
|:-------|:-----|
|![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="512e3-157">测试实验室指南：数据分类</span><span class="sxs-lookup"><span data-stu-id="512e3-157">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="512e3-158">作为临时检查点，请查看对应于此步骤的[退出条件](infoprotect-exit-criteria.md#crit-infoprotect-step2)。</span><span class="sxs-lookup"><span data-stu-id="512e3-158">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step2) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="512e3-159">后续步骤</span><span class="sxs-lookup"><span data-stu-id="512e3-159">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="512e3-160">为 Office 365 配置提高的安全性</span><span class="sxs-lookup"><span data-stu-id="512e3-160">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

