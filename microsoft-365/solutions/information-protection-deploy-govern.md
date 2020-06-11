---
title: 管理受数据隐私法规约束的信息
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
- M365solutions
ms.custom: ''
description: 使用 Microsoft 365 保留标签和策略来管理 Microsoft 365 环境中的个人数据。
ms.openlocfilehash: 4c65eafa167d7224c4022d5634ce089952fada19
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695157"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="cc000-103">管理受数据隐私法规约束的信息</span><span class="sxs-lookup"><span data-stu-id="cc000-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="cc000-104">可以在您的环境中使用信息控制控件，以帮助满足数据隐私合规性需求，其中包括特定于常规数据保护法规（GDPR）、HIPAA-高科技（美国卫生保健隐私法案）、加利福尼亚州消费者保护法（CCPA）和巴西数据保护法案（LGPD）的数字。</span><span class="sxs-lookup"><span data-stu-id="cc000-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="cc000-105">这些控件主要分为以下几个解决方案领域：</span><span class="sxs-lookup"><span data-stu-id="cc000-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="cc000-106">保留策略</span><span class="sxs-lookup"><span data-stu-id="cc000-106">Retention policies</span></span>
- <span data-ttu-id="cc000-107">保留标签</span><span class="sxs-lookup"><span data-stu-id="cc000-107">Retention labels</span></span>
- <span data-ttu-id="cc000-108">记录管理</span><span class="sxs-lookup"><span data-stu-id="cc000-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="cc000-109">影响信息治理控制的数据隐私条例</span><span class="sxs-lookup"><span data-stu-id="cc000-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="cc000-110">下面的示例列出了可能与信息治理控制相关的数据隐私法规：</span><span class="sxs-lookup"><span data-stu-id="cc000-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="cc000-111">GDPR 文章（13）（2）（a）</span><span class="sxs-lookup"><span data-stu-id="cc000-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="cc000-112">GDPR 文章（5）（1）（f）</span><span class="sxs-lookup"><span data-stu-id="cc000-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="cc000-113">HIPAA-高科技（45 CFR 164.312 （c）（2））</span><span class="sxs-lookup"><span data-stu-id="cc000-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="cc000-114">HIPAA-高科技（45 CFR 164.316 （b）（1）（i））</span><span class="sxs-lookup"><span data-stu-id="cc000-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="cc000-115">HIPAA-高科技（45 CFR 164.316 （b）（1）（ii））</span><span class="sxs-lookup"><span data-stu-id="cc000-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="cc000-116">LGPD 文章46</span><span class="sxs-lookup"><span data-stu-id="cc000-116">LGPD Article 46</span></span>

<span data-ttu-id="cc000-117">有关这些管理法规的详细信息，请参阅[评估数据隐私风险和确定敏感信息文章](information-protection-deploy-assess.md)。</span><span class="sxs-lookup"><span data-stu-id="cc000-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="cc000-118">对于信息治理，数据隐私规章通常会调用以下内容：</span><span class="sxs-lookup"><span data-stu-id="cc000-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="cc000-119">对于存储在 Microsoft 365 中的个人数据，应采用一种技术方案进行保留和删除。</span><span class="sxs-lookup"><span data-stu-id="cc000-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="cc000-120">如果要存储个人数据，请通知主题将存储数据的时间长度，这是前端 web 系统上现在的标准做法。</span><span class="sxs-lookup"><span data-stu-id="cc000-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="cc000-121">应保护个人数据，防止使用可验证的方法意外处理、丢失或更改。</span><span class="sxs-lookup"><span data-stu-id="cc000-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="cc000-122">应记录对个人数据执行的任何操作，并且文档应在指定时间段内保留。</span><span class="sxs-lookup"><span data-stu-id="cc000-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="cc000-123">由于数据隐私法规在数据保留和删除方面不是非常特定的，因此需要考虑其他因素，这可能规定了 Microsoft 365 订阅中存储的个人信息的信息治理准则。</span><span class="sxs-lookup"><span data-stu-id="cc000-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="cc000-124">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="cc000-124">Here are a few examples:</span></span>

- <span data-ttu-id="cc000-125">在5年的不活动后，需要删除或 anonymization 帐户数据的情况下，在该时间点之后对消费者帐户进行老化，要求在存储与通知和其他自动化相关的数据和工作流的系统之间进行业务流程。</span><span class="sxs-lookup"><span data-stu-id="cc000-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="cc000-126">配置用于保留与 GDPR 相关的策略和过程的规则，这些规则和过程已被取代（与组织的策略和程序的保留计划一致）的三年。</span><span class="sxs-lookup"><span data-stu-id="cc000-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="cc000-127">维护单独的订阅，以便通过其支持组织与使用者进行通信。</span><span class="sxs-lookup"><span data-stu-id="cc000-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="cc000-128">两周后所有的电子邮件通信都将保留并删除，以减少系统中的任何隐私债务堆积。</span><span class="sxs-lookup"><span data-stu-id="cc000-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="cc000-129">要回答的主要问题是：</span><span class="sxs-lookup"><span data-stu-id="cc000-129">A key question to answer is:</span></span> 

- <span data-ttu-id="cc000-130">出于有效的业务原因，包含个人数据的信息需要多长时间才能保持，以避免 "永远不应保留" 做法？</span><span class="sxs-lookup"><span data-stu-id="cc000-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="cc000-131">这必须与业务连续性的保留需求平衡。</span><span class="sxs-lookup"><span data-stu-id="cc000-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="cc000-132">无论个人信息保留或删除个人信息的法律和商业原因如何，Microsoft 都提供了多种在 Microsoft 365 中实施您的数据管理方案的功能。</span><span class="sxs-lookup"><span data-stu-id="cc000-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="cc000-133">在 Microsoft 365 中管理信息治理</span><span class="sxs-lookup"><span data-stu-id="cc000-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="cc000-134">若要开始，请参阅在 Microsoft 365 中[管理信息](../compliance/manage-information-governance.md)管理和[数据保留、删除和销毁](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)。</span><span class="sxs-lookup"><span data-stu-id="cc000-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="cc000-135">为容器、电子邮件和内容开发数据保留计划</span><span class="sxs-lookup"><span data-stu-id="cc000-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="cc000-136">请注意以下几点：</span><span class="sxs-lookup"><span data-stu-id="cc000-136">Keep the following in mind:</span></span>

- <span data-ttu-id="cc000-137">若要为定义的信息类型建立数据保留计划，应考虑实施任何保留或删除方案的先决条件。</span><span class="sxs-lookup"><span data-stu-id="cc000-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="cc000-138">根据大多数组织认为重要的信息类型的数量以及与他们一起提供的相应大型记录保留计划，实现数据保留和记录管理策略需要进行规划。</span><span class="sxs-lookup"><span data-stu-id="cc000-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="cc000-139">建立此类型的有效数据管理策略的关键是重点关注需要更正式管理的最高优先级的业务功能和信息类型。</span><span class="sxs-lookup"><span data-stu-id="cc000-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="cc000-140">例如法律合同、财务报表和法规遵从性文档。</span><span class="sxs-lookup"><span data-stu-id="cc000-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="cc000-141">尽量避免为每种信息类型提供单独的保留计划。</span><span class="sxs-lookup"><span data-stu-id="cc000-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="cc000-142">请尽量充分利用常规类别，例如，将常规业务内容的保留计划安排为7年。</span><span class="sxs-lookup"><span data-stu-id="cc000-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="cc000-143">一旦环境中的个人信息类型更清楚，请为此类型的内容建立保留和删除计划，并调整您的信息体系结构以使此类信息的管理更容易。</span><span class="sxs-lookup"><span data-stu-id="cc000-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="cc000-144">例如，使用受控制的访问隔离单独的网站、库或文件夹中的个人信息。</span><span class="sxs-lookup"><span data-stu-id="cc000-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies"></a><span data-ttu-id="cc000-145">保留策略</span><span class="sxs-lookup"><span data-stu-id="cc000-145">Retention policies</span></span>

<span data-ttu-id="cc000-146">为自动应用的网站中的内容创建和部署[保留策略](../compliance/retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cc000-146">Create and deploy [retention policies](../compliance/retention-policies.md) for content in sites that are automatically applied.</span></span>

<span data-ttu-id="cc000-147">若要获取包含或预期包含个人数据的网站的数据隐私，请指定保留或删除规则以满足组织标准。</span><span class="sxs-lookup"><span data-stu-id="cc000-147">For data privacy for sites that contain or are expected to contain personal data, specify retention or deletion rules to address organizational standards.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="cc000-148">保留标签</span><span class="sxs-lookup"><span data-stu-id="cc000-148">Retention labels</span></span>

<span data-ttu-id="cc000-149">创建和部署内容和电子邮件的[保留标签](../compliance/labels.md)。</span><span class="sxs-lookup"><span data-stu-id="cc000-149">Create and deploy [retention labels](../compliance/labels.md) for content and email.</span></span>

<span data-ttu-id="cc000-150">若要获取包含或预期包含个人数据的网站、库、文件夹和电子邮件的数据隐私，请指定自动保留或删除规则以满足组织标准。</span><span class="sxs-lookup"><span data-stu-id="cc000-150">For data privacy for sites, libraries, folders, and email that contain or are expected to contain personal data, specify auto retention or deletion rules to address organizational standards.</span></span>

### <a name="records-management"></a><span data-ttu-id="cc000-151">记录管理</span><span class="sxs-lookup"><span data-stu-id="cc000-151">Records management</span></span>

<span data-ttu-id="cc000-152">创建和部署基于记录保留计划和文件计划的记录管理的保留标签。</span><span class="sxs-lookup"><span data-stu-id="cc000-152">Create and deploy retention labels for records management based on a records retention schedule and file plan.</span></span>

<span data-ttu-id="cc000-153">对于数据隐私，法律部门收到的数据主体请求（Dsr）声明为记录并无限期存储，以遵守法规活动保留规范。</span><span class="sxs-lookup"><span data-stu-id="cc000-153">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and stored indefinitely to adhere to regulatory activity retention specifications.</span></span>

<span data-ttu-id="cc000-154">有关详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="cc000-154">See these resources for more information:</span></span> 

- [<span data-ttu-id="cc000-155">记录管理</span><span class="sxs-lookup"><span data-stu-id="cc000-155">Records Management</span></span>](../compliance/records-management.md)
- [<span data-ttu-id="cc000-156">文件计划管理器</span><span class="sxs-lookup"><span data-stu-id="cc000-156">File plan manager</span></span>](../compliance/file-plan-manager.md)
- [<span data-ttu-id="cc000-157">基于事件的记录管理保留</span><span class="sxs-lookup"><span data-stu-id="cc000-157">Event-based retention for records management</span></span>](../compliance/automate-event-driven-retention.md)
- [<span data-ttu-id="cc000-158">内容的处置</span><span class="sxs-lookup"><span data-stu-id="cc000-158">Disposition of content</span></span>](../compliance/disposition-reviews.md)
