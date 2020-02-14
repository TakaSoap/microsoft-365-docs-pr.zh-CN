---
title: 数据保护影响评估
description: 这些文档为数据控制者相关信息，帮助他们确定是否需要 DPIA 以及要包含的详细信息。
keywords: 数据保护影响评估, DPIA, Dynamics 365, Microsoft 专业服务, Microsoft 365, Microsoft 365 文档, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 0a62cf2ef40bbf9da219309cf75eed27ea8739e4
ms.sourcegitcommit: 2498cd4af90c31771167a1be9f8f12a96dc6500f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41916897"
---
# <a name="data-protection-impact-assessment-for-the-gdpr"></a><span data-ttu-id="51112-104">GDPR 规定的数据保护影响评估</span><span class="sxs-lookup"><span data-stu-id="51112-104">Data Protection Impact Assessment for the GDPR</span></span>

<span data-ttu-id="51112-105">一般数据保护条例 (GDPR) 引入了新规定，适用于向欧盟 (EU) 民众提供商品和服务的组织，或收集并分析欧盟居民相关数据的组织。无论你或你的企业位于何处，都要遵守这些新规定。</span><span class="sxs-lookup"><span data-stu-id="51112-105">The General Data Protection Regulation (GDPR) introduces new rules for organizations that offer goods and services to people in the European Union (EU), or that collect and analyze data for EU residents no matter where you or your enterprise are located.</span></span> <span data-ttu-id="51112-106">如需了解更多详情，可以参阅 [GDPR 摘要主题](gdpr.md)。</span><span class="sxs-lookup"><span data-stu-id="51112-106">Additional details can be found in the [GDPR Summary topic](gdpr.md).</span></span> <span data-ttu-id="51112-107">本文档介绍了 GDPR 规定在使用 Microsoft 产品和服务时执行的数据保护影响评估 (DPIA)。</span><span class="sxs-lookup"><span data-stu-id="51112-107">This document guides you to information regarding Data Protection Impact Assessments (DPIAs) under the GDPR when using Microsoft products and services.</span></span>

## <a name="terminology"></a><span data-ttu-id="51112-108">术语</span><span class="sxs-lookup"><span data-stu-id="51112-108">Terminology</span></span>

<span data-ttu-id="51112-109">本文档中使用的 GDPR 术语的有用定义：</span><span class="sxs-lookup"><span data-stu-id="51112-109">Helpful definitions for GDPR terms used in this document:</span></span>

- <span data-ttu-id="51112-110">*数据控制者（控制者）*：单独或与他人共同确定个人数据处理目的和方法的法人、公共机关、机构或其他团体。</span><span class="sxs-lookup"><span data-stu-id="51112-110">*Data Controller (Controller)*: A legal person, public authority, agency or other body which, alone or jointly with others, determines the purposes and means of the processing of personal data.</span></span>  
- <span data-ttu-id="51112-111">*个人数据*和*数据主体*：与已识别或可识别的自然人（数据主体）相关的任何信息；可识别的自然人是可以直接或间接识别的自然人。</span><span class="sxs-lookup"><span data-stu-id="51112-111">*Personal data* and *data subject*: Any information relating to an identified or identifiable natural person (data subject); an identifiable natural person is one who can be identified, directly or indirectly.</span></span>  
- <span data-ttu-id="51112-112">*处理者*：代表控制者处理个人数据的自然人或法人、公共机关、机构或其他团队。</span><span class="sxs-lookup"><span data-stu-id="51112-112">*Processor*: A natural or legal person, public authority, agency, or other body, which processes personal data on behalf of the controller.</span></span>  
- <span data-ttu-id="51112-113">*客户数据*：在企业日常运营中生成和存储的数据。</span><span class="sxs-lookup"><span data-stu-id="51112-113">*Customer Data*: Data produced and stored in the day-to-day operations of running your business.</span></span>

## <a name="what-is-a-dpia"></a><span data-ttu-id="51112-114">什么是 DPIA？</span><span class="sxs-lookup"><span data-stu-id="51112-114">What is a DPIA?</span></span>

<span data-ttu-id="51112-115">GDPR 要求，数据控制者必须准备对“可能会对自然人的权利和自由造成高风险”的操作执行数据保护影响评估 (DPIA)。</span><span class="sxs-lookup"><span data-stu-id="51112-115">The GDPR requires controllers to prepare a Data Protection Impact Assessment (DPIA) for operations that are 'likely to result in a high risk to the rights and freedoms of natural persons.'</span></span> <span data-ttu-id="51112-116">Microsoft 产品和服务不需要创建 DPIA。</span><span class="sxs-lookup"><span data-stu-id="51112-116">There is nothing inherent in Microsoft products and services that need the creation of a DPIA.</span></span> <span data-ttu-id="51112-117">不过，由于 Microsoft 产品和服务可高度自定义，因此是否需要创建 DPIA 具体视 Microsoft 配置详细信息而定。</span><span class="sxs-lookup"><span data-stu-id="51112-117">However, because Microsoft products and services are highly customizable, a DPIA may be needed depending on the details of your Microsoft configuration.</span></span> <span data-ttu-id="51112-118">Microsoft 无法控制此类信息，几乎或根本不了解此类信息。</span><span class="sxs-lookup"><span data-stu-id="51112-118">Microsoft has no control over, and little or no insight into such information.</span></span> <span data-ttu-id="51112-119">作为数据控制者，你必须确定此类数据的正确使用。</span><span class="sxs-lookup"><span data-stu-id="51112-119">You, as a data controller must determine appropriate uses of their data.</span></span>

## <a name="dpia-in-action"></a><span data-ttu-id="51112-120">DPIA 演示</span><span class="sxs-lookup"><span data-stu-id="51112-120">DPIA in Action</span></span>

<span data-ttu-id="51112-121">DPIA 指南适用于 Office 365、Azure、Dynamics 365 以及 Microsoft 支持和专业服务。</span><span class="sxs-lookup"><span data-stu-id="51112-121">The DPIA guidance applies to Office 365, Azure, Dynamics 365, and Microsoft Support and Professional Services.</span></span> <span data-ttu-id="51112-122">相应指南包括以下注意事项：</span><span class="sxs-lookup"><span data-stu-id="51112-122">That guidance includes consideration of:</span></span>

<span data-ttu-id="51112-123">**何时需要 DPIA？**</span><span class="sxs-lookup"><span data-stu-id="51112-123">**When is a DPIA needed?**</span></span>

<span data-ttu-id="51112-124">在考虑是否完成 DPIA 时，应考虑下列风险因素。</span><span class="sxs-lookup"><span data-stu-id="51112-124">The risk factors listed below should be addressed when considering whether to complete a DPIA.</span></span> <span data-ttu-id="51112-125">每个指南的第 1 部分中介绍了其他潜在因素和更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="51112-125">Other potential factors and further details are found in Part 1 of each of the guidelines.</span></span>  

- <span data-ttu-id="51112-126">基于自动化处理的系统而广泛的数据评估。</span><span class="sxs-lookup"><span data-stu-id="51112-126">A systematic and extensive evaluation of data based on automated processing.</span></span>  
- <span data-ttu-id="51112-127">大规模地处理特殊类别的数据（揭示唯一识别自然人的信息的数据），或与刑事犯罪和违法行为相关的个人数据。</span><span class="sxs-lookup"><span data-stu-id="51112-127">Processing on a large scale of special categories of data (data revealing information uniquely identifying a natural person), or of personal data relating to criminal convictions and offenses.</span></span>
- <span data-ttu-id="51112-128">大规模地系统监视公开区域。</span><span class="sxs-lookup"><span data-stu-id="51112-128">Systematic monitoring of a publicly accessible area on a large scale.</span></span>

<span data-ttu-id="51112-129">GDPR 澄清：“如果处理所涉及的个人数据来自个体医生、其他医疗保健专业人员或律师的患者或客户，不得将个人数据处理视为大规模。</span><span class="sxs-lookup"><span data-stu-id="51112-129">The GDPR clarifies 'The processing of personal data should not be considered to be on a large scale if the processing concerns personal data from patients or clients by an individual physician, other health care professional, or lawyer.</span></span> <span data-ttu-id="51112-130">在这种情况下，不得强制进行数据保护影响评估。”</span><span class="sxs-lookup"><span data-stu-id="51112-130">In such cases, a data protection impact assessment should not be mandatory.'</span></span>

<span data-ttu-id="51112-131">**完成 DPIA 需要什么？**</span><span class="sxs-lookup"><span data-stu-id="51112-131">**What is required to complete a DPIA?**</span></span>

<span data-ttu-id="51112-132">DPIA 应提供预期处理的具体信息，详见指南的第 2 部分。</span><span class="sxs-lookup"><span data-stu-id="51112-132">A DPIA should provide specific information about the intended processing, which is detailed in Part 2 of the guidance.</span></span> <span data-ttu-id="51112-133">此类信息包括：</span><span class="sxs-lookup"><span data-stu-id="51112-133">That information includes:</span></span>

- <span data-ttu-id="51112-134">评估与 DPIA 目的相关的数据处理必要性和合理性。</span><span class="sxs-lookup"><span data-stu-id="51112-134">Assessment of the necessity, and proportionality of data processing in relation to the purpose of the DPIA.</span></span>  
- <span data-ttu-id="51112-135">评估对自然人的权利和自由造成的风险。</span><span class="sxs-lookup"><span data-stu-id="51112-135">Assessment of the risks to the rights and freedoms of natural persons.</span></span>
- <span data-ttu-id="51112-136">旨在消除风险的预期措施（包括安全措施和机制），以确保保护个人数据并证明 GDPR 合规性。</span><span class="sxs-lookup"><span data-stu-id="51112-136">Intended measures to address the risks, including safeguards, security measures, and mechanisms to ensure the protection of personal data and demonstrate compliance with the GDPR.</span></span>
- <span data-ttu-id="51112-137">处理目的</span><span class="sxs-lookup"><span data-stu-id="51112-137">Purposes of processing</span></span>  
- <span data-ttu-id="51112-138">处理的个人数据类别</span><span class="sxs-lookup"><span data-stu-id="51112-138">Categories of personal data processed</span></span>  
- <span data-ttu-id="51112-139">数据保留</span><span class="sxs-lookup"><span data-stu-id="51112-139">Data retention</span></span>  
- <span data-ttu-id="51112-140">个人数据的位置和传输</span><span class="sxs-lookup"><span data-stu-id="51112-140">Location and transfers of personal data</span></span>  
- <span data-ttu-id="51112-141">与第三方下级处理者分享的数据</span><span class="sxs-lookup"><span data-stu-id="51112-141">Data sharing with third-party subprocessors</span></span>  
- <span data-ttu-id="51112-142">与独立第三方分享的数据</span><span class="sxs-lookup"><span data-stu-id="51112-142">Data sharing with independent third-parties</span></span>  
- <span data-ttu-id="51112-143">数据主体权利</span><span class="sxs-lookup"><span data-stu-id="51112-143">Data subject rights</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="51112-144">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="51112-144">Additional Considerations</span></span>

<span data-ttu-id="51112-145">下面介绍了可能与 Microsoft 实现相关的具体详情。</span><span class="sxs-lookup"><span data-stu-id="51112-145">Specific details that may be relevant to your Microsoft implementation are below.</span></span>

- <span data-ttu-id="51112-146">[Office 365](gdpr-dpia-office365.md)：本文档适用于 Office 365 应用程序和服务，包括但不限于 Exchange Online、SharePoint Online、Yammer、Skype for Business 和 Power BI。</span><span class="sxs-lookup"><span data-stu-id="51112-146">[Office 365](gdpr-dpia-office365.md): This document applies to Office 365 applications and services, including but not limited to Exchange Online, SharePoint Online, Yammer, Skype for Business, and Power BI.</span></span> <span data-ttu-id="51112-147">有关详细信息，请参阅表 [1](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed) 和表 [2](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia)。</span><span class="sxs-lookup"><span data-stu-id="51112-147">Refer to Tables [1](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed) and [2](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia) for more details.</span></span>  
- <span data-ttu-id="51112-148">[Azure](gdpr-dpia-azure.md)：我们鼓励客户与其隐私官和法律顾问合作，共同确定与使用 Microsoft Azure 相关的任何 DPIA 的必要性和内容。</span><span class="sxs-lookup"><span data-stu-id="51112-148">[Azure](gdpr-dpia-azure.md): Customers are encouraged to work with their privacy officers and legal counsel to determine the necessity and content of any DPIAs related to their use of Microsoft Azure.</span></span>  
- <span data-ttu-id="51112-149">[Dynamics 365](gdpr-dpia-dynamics.md)：DPIA 的内容可能因你使用的 Dynamics 365 工具而异。</span><span class="sxs-lookup"><span data-stu-id="51112-149">[Dynamics 365](gdpr-dpia-dynamics.md): The contents of a DPIA may vary according to which Dynamics 365 tools you are employing.</span></span> <span data-ttu-id="51112-150">有关具体详细信息，请参阅[第 2 部分 - DPIA 内容](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-dynamics#part-2--contents-of-a-dpia)。</span><span class="sxs-lookup"><span data-stu-id="51112-150">For specific details refer to [Part 2 Contents of a DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-dynamics#part-2--contents-of-a-dpia).</span></span>
- <span data-ttu-id="51112-151">[Microsoft 支持和专业服务](gdpr-dpia-prof-services.md)：专业服务不会执行特定例程或自动数据处理，也不会处理特殊类别或执行便于或需要监视可公开访问数据的任务。</span><span class="sxs-lookup"><span data-stu-id="51112-151">[Microsoft Support and Professional Services](gdpr-dpia-prof-services.md): Professional Services does not conduct certain routine or automated data processing, nor is it intended to process special categories or perform tasks that facilitate or require monitoring of publicly accessible data.</span></span> <span data-ttu-id="51112-152">有关详细信息，请参阅[第 1 部分 - 确定是否需要 DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-1--determining-whether-a-dpia-is-needed)。</span><span class="sxs-lookup"><span data-stu-id="51112-152">For details see [Part 1 — Determining Whether a DPIA is needed](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-1--determining-whether-a-dpia-is-needed).</span></span> <span data-ttu-id="51112-153">控制者必须在专业服务的特定实现和使用上下文中，考虑上面概述的 DPIA 元素以及其他任何相关因素。</span><span class="sxs-lookup"><span data-stu-id="51112-153">Controllers must consider the DPIA elements outlined above, along with any other relevant factors, in the context of the controller’s specific implementations and uses of Professional Services.</span></span> <span data-ttu-id="51112-154">有关专业服务信息，请参阅[第 2 部分 - DPIA 内容](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-2--contents-of-a-dpia)。</span><span class="sxs-lookup"><span data-stu-id="51112-154">For Professional Services information, see [Part 2 — Contents of a DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-2--contents-of-a-dpia).</span></span>

## <a name="learn-more"></a><span data-ttu-id="51112-155">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="51112-155">Learn more</span></span>

- [<span data-ttu-id="51112-156">Microsoft 信任中心</span><span class="sxs-lookup"><span data-stu-id="51112-156">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
