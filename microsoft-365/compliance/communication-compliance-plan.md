---
title: 规划通信合规性
description: 了解有关在组织中使用通信合规性的规划。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 214c5376d4c074525253707e181eee69cefff85e
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045845"
---
# <a name="plan-for-communication-compliance"></a><span data-ttu-id="c23cd-103">规划通信合规性</span><span class="sxs-lookup"><span data-stu-id="c23cd-103">Plan for communication compliance</span></span>

<span data-ttu-id="c23cd-104">在组织中开始使用[通信合规性](communication-compliance.md)之前，您的信息技术和合规性管理团队应检查重要的规划活动和注意事项。</span><span class="sxs-lookup"><span data-stu-id="c23cd-104">Before getting started with [communication compliance](communication-compliance.md) in your organization, there are important planning activities and considerations that should be reviewed by your information technology and compliance management teams.</span></span> <span data-ttu-id="c23cd-105">在以下方面全面了解和规划部署可帮助确保实现和使用通信合规性功能，并与解决方案的最佳做法保持一致。</span><span class="sxs-lookup"><span data-stu-id="c23cd-105">Thoroughly understanding and planning for deployment in the following areas will help ensure that your implementation and use of communication compliance features goes smoothly and is aligned with the best practices for the solution.</span></span>

## <a name="work-with-stakeholders-in-your-organization"></a><span data-ttu-id="c23cd-106">与组织中的利益干系人合作</span><span class="sxs-lookup"><span data-stu-id="c23cd-106">Work with stakeholders in your organization</span></span>

<span data-ttu-id="c23cd-107">确定组织中相应的利益干系人进行协作，以针对通信合规性警报采取措施。</span><span class="sxs-lookup"><span data-stu-id="c23cd-107">Identify the appropriate stakeholders in your organization to collaborate for taking actions on communication compliance alerts.</span></span> <span data-ttu-id="c23cd-108">一些建议的利益干系人（包括在初始规划和端到端[通信合规性工作流](communication-compliance.md#workflow)中）是组织中以下区域的人员：</span><span class="sxs-lookup"><span data-stu-id="c23cd-108">Some recommended stakeholders to consider including in initial planning and the end-to-end [communication compliance workflow](communication-compliance.md#workflow) are people from the following areas of your organization:</span></span>

- <span data-ttu-id="c23cd-109">信息技术</span><span class="sxs-lookup"><span data-stu-id="c23cd-109">Information technology</span></span>
- <span data-ttu-id="c23cd-110">合规性</span><span class="sxs-lookup"><span data-stu-id="c23cd-110">Compliance</span></span>
- <span data-ttu-id="c23cd-111">隐私</span><span class="sxs-lookup"><span data-stu-id="c23cd-111">Privacy</span></span>
- <span data-ttu-id="c23cd-112">安全性</span><span class="sxs-lookup"><span data-stu-id="c23cd-112">Security</span></span>
- <span data-ttu-id="c23cd-113">人力资源人员</span><span class="sxs-lookup"><span data-stu-id="c23cd-113">Human resources</span></span>
- <span data-ttu-id="c23cd-114">法律</span><span class="sxs-lookup"><span data-stu-id="c23cd-114">Legal</span></span>

## <a name="plan-for-the-investigation-and-remediation-workflow"></a><span data-ttu-id="c23cd-115">规划调查和修正工作流</span><span class="sxs-lookup"><span data-stu-id="c23cd-115">Plan for the investigation and remediation workflow</span></span>

<span data-ttu-id="c23cd-116">选择 "专用审阅者" 以在[Microsoft 365 合规性中心](https://compliance.microsoft.com/)中的定期节奏上监视和查看警报。</span><span class="sxs-lookup"><span data-stu-id="c23cd-116">Select dedicated reviewers to monitor and review the alerts on a regular cadence in the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="c23cd-117">请记住，您需要[创建新的角色组](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance)，以启用具有**监管审核管理员**、**案例管理**、**合规性管理员**和**审阅**角色的审阅者的权限，以使用策略匹配来调查和修正邮件。</span><span class="sxs-lookup"><span data-stu-id="c23cd-117">Remember, you’ll need to [create a new role group](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) to enable permissions for reviewers with the **Supervisory Review Administrator**, **Case Management**, **Compliance Administrator**, and **Review** roles to investigate and remediate messages with policy matches.</span></span>

## <a name="plan-for-policies"></a><span data-ttu-id="c23cd-118">规划策略</span><span class="sxs-lookup"><span data-stu-id="c23cd-118">Plan for policies</span></span>

<span data-ttu-id="c23cd-119">使用[预定义](communication-compliance-feature-reference.md#policy-templates)的攻击性语言模板、敏感信息和法规遵从性，创建通信合规性策略是快速且轻松的。</span><span class="sxs-lookup"><span data-stu-id="c23cd-119">Creating communication compliance policies is quick and easy with the [pre-defined templates](communication-compliance-feature-reference.md#policy-templates) for offensive language, sensitive information, and regulatory compliance.</span></span> <span data-ttu-id="c23cd-120">自定义通信合规性策略允许您灵活地检测和调查特定于您的组织和要求的问题。</span><span class="sxs-lookup"><span data-stu-id="c23cd-120">Custom communication compliance policies allow the flexibility for detecting and investigation issues specific to your organization and requirements.</span></span>

<span data-ttu-id="c23cd-121">在规划通信合规性策略时，请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="c23cd-121">When planning for communication compliance policies, consider the following:</span></span>

- <span data-ttu-id="c23cd-122">考虑将组织中的所有用户添加为您的通信合规性策略的范围内。</span><span class="sxs-lookup"><span data-stu-id="c23cd-122">Consider adding all users in your organization as in-scope for your communication compliance policies.</span></span> <span data-ttu-id="c23cd-123">在某些情况下，将特定用户标识为范围内的各个策略是有用的，但是大多数组织应包括针对骚扰或歧视检测而优化的通信合规性策略中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="c23cd-123">Identifying specific users as in-scope for individual policies are useful in some circumstances, however most organizations should include all users in communication compliance policies optimized for harassment or discrimination detection.</span></span>
- <span data-ttu-id="c23cd-124">若要简化设置，请考虑为需要查看其通信的用户创建组。</span><span class="sxs-lookup"><span data-stu-id="c23cd-124">To simplify your setup, consider creating groups for people who need their communications reviewed.</span></span> <span data-ttu-id="c23cd-125">如果使用的是组;您可能需要多个。</span><span class="sxs-lookup"><span data-stu-id="c23cd-125">If you're using groups; you might need several.</span></span> <span data-ttu-id="c23cd-126">例如，如果要扫描两个不同的人员组之间的通信，或者要指定未受监督的组。</span><span class="sxs-lookup"><span data-stu-id="c23cd-126">For example, if you want to scan communications between two distinct groups of people, or if you want to specify a group that isn't supervised.</span></span>
- <span data-ttu-id="c23cd-127">配置要在100% 查看的通信百分比，以确保策略能够捕获组织中的所有问题的相关问题。</span><span class="sxs-lookup"><span data-stu-id="c23cd-127">Configure the percentage of communications to review at 100% to ensure that policies are catching all issues of concern in communications for your organization.</span></span>
- <span data-ttu-id="c23cd-128">您可以扫描[第三方源](communication-compliance-feature-reference.md#supported-communication-types)的通信，以获取导入到 Microsoft 365 组织中的邮箱的数据。</span><span class="sxs-lookup"><span data-stu-id="c23cd-128">You can scan communications from [third-party sources](communication-compliance-feature-reference.md#supported-communication-types) for data imported into mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="c23cd-129">若要在这些平台中包括通信审查，需要先将连接器配置为这些服务，然后才能通过通信策略监视邮件会议策略条件。</span><span class="sxs-lookup"><span data-stu-id="c23cd-129">To include review of communications in these platforms, you’ll need to configure a connector to these services before messages meeting policy conditions are monitored by communication policy.</span></span>
- <span data-ttu-id="c23cd-130">在自定义通信合规性策略中，策略可以支持非英语的监视语言。</span><span class="sxs-lookup"><span data-stu-id="c23cd-130">Policies can support monitoring languages other than English in custom communication compliance policies.</span></span> <span data-ttu-id="c23cd-131">使用您选择的语言构建冒犯性词的[自定义关键字词典](communication-compliance-feature-reference.md#custom-keyword-dictionaries)，或使用 Microsoft 365 中的[trainable 分类](classifier-getting-started-with.md)程序构建您自己的机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="c23cd-131">Build a [custom keyword dictionary](communication-compliance-feature-reference.md#custom-keyword-dictionaries) of offensive words in the language of your choice or build your own machine-learning model using [trainable classifiers](classifier-getting-started-with.md) in Microsoft 365.</span></span>
- <span data-ttu-id="c23cd-132">所有组织都具有不同的通信标准和策略需求。</span><span class="sxs-lookup"><span data-stu-id="c23cd-132">All organizations have different communication standards and policy needs.</span></span> <span data-ttu-id="c23cd-133">使用通信合规性[策略条件](communication-compliance-feature-reference.md#conditional-settings)监视特定关键字，或使用[自定义敏感信息类型](create-a-custom-sensitive-information-type.md)监视特定类型的信息。</span><span class="sxs-lookup"><span data-stu-id="c23cd-133">Monitor for specific keywords using communication compliance [policy conditions](communication-compliance-feature-reference.md#conditional-settings) or monitor for specific types of information with [custom sensitive information types](create-a-custom-sensitive-information-type.md).</span></span>

## <a name="ready-to-get-started"></a><span data-ttu-id="c23cd-134">准备好开始了吗？</span><span class="sxs-lookup"><span data-stu-id="c23cd-134">Ready to get started?</span></span>

<span data-ttu-id="c23cd-135">若要为 Microsoft 365 组织配置通信合规性，请参阅[configure communication 合规性 For microsoft 365](communication-compliance-configure.md)或查看[Contoso 的个案研究](communication-compliance-case-study.md)，以及如何快速将通信合规性策略配置为在 Microsoft 团队、Exchange Online 和 Yammer 通信中监视是否有攻击性的语言。</span><span class="sxs-lookup"><span data-stu-id="c23cd-135">To configure communication compliance for your Microsoft 365 organization, see [Configure communication compliance for Microsoft 365](communication-compliance-configure.md) or check out the [case study for Contoso](communication-compliance-case-study.md) and how they quickly configured a communication compliance policy to monitor for offensive language in Microsoft Teams, Exchange Online, and Yammer communications.</span></span>
