---
title: 管理受数据隐私条例约束的信息
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: 使用 Microsoft 365 保留标签和策略管理 Microsoft 365 环境中的个人数据。
ms.openlocfilehash: 62c2386ac8f9c5b31650df8be2c2a411d8b75959
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928432"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="6b8e4-103">管理受数据隐私条例约束的信息</span><span class="sxs-lookup"><span data-stu-id="6b8e4-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="6b8e4-104">可以在环境中使用信息治理控制来帮助满足数据隐私合规性需求，包括特定于一般数据保护条例 (GDPR) 、HIPAA-HITECH (美国医疗保健隐私法案) 、加州消费者保护法案 (CCPA) 和巴西数据保护法案 (LGPD) 等。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="6b8e4-105">这些控件主要属于以下解决方案区域：</span><span class="sxs-lookup"><span data-stu-id="6b8e4-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="6b8e4-106">保留策略</span><span class="sxs-lookup"><span data-stu-id="6b8e4-106">Retention policies</span></span>
- <span data-ttu-id="6b8e4-107">保留标签</span><span class="sxs-lookup"><span data-stu-id="6b8e4-107">Retention labels</span></span>
- <span data-ttu-id="6b8e4-108">记录管理</span><span class="sxs-lookup"><span data-stu-id="6b8e4-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="6b8e4-109">影响信息治理控制的数据隐私法规</span><span class="sxs-lookup"><span data-stu-id="6b8e4-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="6b8e4-110">下面是可能与信息治理控制相关的数据隐私法规示例列表：</span><span class="sxs-lookup"><span data-stu-id="6b8e4-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="6b8e4-111">GDPR 文章 (2)  (2)  (13) </span><span class="sxs-lookup"><span data-stu-id="6b8e4-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="6b8e4-112">GDPR 文章 (5)  (1)  (f) </span><span class="sxs-lookup"><span data-stu-id="6b8e4-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="6b8e4-113">HIPAA-HITECH (45 CFR 164.312 (c)  (2) ) </span><span class="sxs-lookup"><span data-stu-id="6b8e4-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="6b8e4-114">HIPAA-HITECH (45 CFR 164.316 (b)  (1)  (i) ) </span><span class="sxs-lookup"><span data-stu-id="6b8e4-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="6b8e4-115">HIPAA-HITECH (45 CFR 164.316 (b)  (1)  (ii) ) </span><span class="sxs-lookup"><span data-stu-id="6b8e4-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="6b8e4-116">LGPD 文章 46</span><span class="sxs-lookup"><span data-stu-id="6b8e4-116">LGPD Article 46</span></span>

<span data-ttu-id="6b8e4-117">有关这些法规详细信息，请参阅评估数据 [隐私风险并识别敏感信息文章](information-protection-deploy-assess.md)。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="6b8e4-118">对于信息治理，数据隐私法规通常要求：</span><span class="sxs-lookup"><span data-stu-id="6b8e4-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="6b8e4-119">你应该为 Microsoft 365 中存储的个人数据采用保留和删除技术方案。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="6b8e4-120">如果要存储个人数据，请告知主体数据将存储多久，这是现在前端 Web 系统上的标准做法。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="6b8e4-121">应该防止个人数据使用可验证的方法意外处理、丢失或更改。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="6b8e4-122">对个人数据执行的任何操作都应进行记录，并且该文档应保留指定的期限。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="6b8e4-123">由于数据隐私法规在数据保留和删除方面并不十分具体，因此需要考虑其他因素，这些因素可能规定 Microsoft 365 订阅中存储的个人信息的信息治理准则。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="6b8e4-124">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="6b8e4-124">Here are a few examples:</span></span>

- <span data-ttu-id="6b8e4-125">在 5 年不活动后对使用者帐户进行注销，并且要求在此后删除或匿名处理帐户数据，这要求系统在存储数据与与通知和其他自动化相关的工作流之间协调工作。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="6b8e4-126">配置与 GDPR 相关的策略和过程在被取代后保留三年的规则，这符合组织的策略和程序的保留计划。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="6b8e4-127">维护单独的订阅，以通过其支持组织与消费者进行通信。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="6b8e4-128">所有电子邮件通信在两周后保留和删除，以减少系统内的任何隐私债务增加。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="6b8e4-129">要回答的一个关键问题是：</span><span class="sxs-lookup"><span data-stu-id="6b8e4-129">A key question to answer is:</span></span> 

- <span data-ttu-id="6b8e4-130">出于有效的业务原因，包含个人数据的信息需要保留多久，以避免"永久保留"做法？</span><span class="sxs-lookup"><span data-stu-id="6b8e4-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="6b8e4-131">这必须与业务连续性的保留需求相平衡。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="6b8e4-132">无论保留或删除个人信息的法律和业务原因如何，Microsoft 都提供了许多功能来实现 Microsoft 365 中的数据管理方案。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="6b8e4-133">在 Microsoft 365 中管理信息治理</span><span class="sxs-lookup"><span data-stu-id="6b8e4-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="6b8e4-134">首先，请参阅管理 [信息治理](../compliance/manage-information-governance.md) 和 [Microsoft 365 中的数据保留、删除和销毁](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="6b8e4-135">制定容器、电子邮件和内容的数据保留计划</span><span class="sxs-lookup"><span data-stu-id="6b8e4-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="6b8e4-136">请注意下列事项：</span><span class="sxs-lookup"><span data-stu-id="6b8e4-136">Keep the following in mind:</span></span>

- <span data-ttu-id="6b8e4-137">为定义的信息类型建立数据保留计划应被视为实施任何保留或删除方案的先决条件。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="6b8e4-138">鉴于大多数组织认为重要的信息类型以及相应的大型记录保留计划，实施数据保留和记录管理策略需要进行规划。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="6b8e4-139">建立此类型的有效数据管理策略的关键是重点关注需要更正式的管理的最高优先级业务功能和信息类型。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="6b8e4-140">示例包括法律合同、财务报表和监管合规性文档。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="6b8e4-141">尝试避免对每种信息类型使用单独的保留计划。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="6b8e4-142">尽量利用常规类别，例如，常规业务内容的保留计划为 7 年。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="6b8e4-143">在更好地了解环境中的个人信息类型后，为此类内容制定保留和删除计划，并调整信息体系结构，以便更轻松地管理此类信息。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="6b8e4-144">例如，将个人信息隔离在具有受控访问权限的单独网站、库或文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="6b8e4-145">保留策略和保留标签</span><span class="sxs-lookup"><span data-stu-id="6b8e4-145">Retention policies and retention labels</span></span>

<span data-ttu-id="6b8e4-146">使用 [保留策略和保留标签](../compliance/retention.md) 保留或删除 Microsoft 365 中包含或预期包含个人数据的内容。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-146">Use [retention policies and retention labels](../compliance/retention.md) to retain or delete content in Microsoft 365 that contains or is expected to contain personal data.</span></span>

### <a name="records-management"></a><span data-ttu-id="6b8e4-147">记录管理</span><span class="sxs-lookup"><span data-stu-id="6b8e4-147">Records management</span></span>

<span data-ttu-id="6b8e4-148">使用声明内容记录的保留标签，为 Microsoft [](../compliance/records-management.md) 365 中的数据实现记录管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-148">Use retention labels that declare content a record to implement a [records management solution](../compliance/records-management.md) for data in Microsoft 365.</span></span>

<span data-ttu-id="6b8e4-149">对于数据隐私， (部门收到的) DSR 的数据主体请求将被声明为记录，并可以无限期存储或经过证明处理，以遵守法规活动保留规范。</span><span class="sxs-lookup"><span data-stu-id="6b8e4-149">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and can be stored indefinitely or disposed of with proof, to adhere to regulatory activity retention specifications.</span></span>