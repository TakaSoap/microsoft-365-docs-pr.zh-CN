---
title: 为 Microsoft 365 企业版的 azure AD 身份保护测试环境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: 配置 Azure AD 身份保护并分析 Microsoft 365 企业版测试环境中的当前帐户。
ms.openlocfilehash: 165667ad2122839336ef0790ab5661cff53ca32b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865483"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c57e5-103">为 Microsoft 365 企业版的 azure AD 身份保护测试环境</span><span class="sxs-lookup"><span data-stu-id="c57e5-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c57e5-p101">Azure AD 身份保护可以检测潜在安全漏洞影响组织的标识、 配置自动的答复，并调查事件。本文介绍如何启用 Azure AD 身份保护并查看分析的测试环境帐户。</span><span class="sxs-lookup"><span data-stu-id="c57e5-p101">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents. This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="c57e5-106">有两个阶段设置 Microsoft 365 企业版测试环境中的 Azure AD 身份保护：</span><span class="sxs-lookup"><span data-stu-id="c57e5-106">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="c57e5-107">创建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="c57e5-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="c57e5-108">启用并使用 Azure AD 身份保护。</span><span class="sxs-lookup"><span data-stu-id="c57e5-108">Enable and use Azure AD Identity Protection.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="c57e5-110">单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="c57e5-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c57e5-111">第 1 阶段： 构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="c57e5-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c57e5-112">如果您只想要测试的最低硬件要求与轻型方式 Azure AD 身份保护，按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="c57e5-112">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="c57e5-113">如果您想要测试模拟企业中的 Azure AD 身份保护，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="c57e5-113">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c57e5-p102">测试 Azure AD 身份保护不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试 Azure AD 身份保护并与之试验环境值，该值代表典型组织中。</span><span class="sxs-lookup"><span data-stu-id="c57e5-p102">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="c57e5-116">第 2 阶段： 启用并使用 Azure AD 身份保护</span><span class="sxs-lookup"><span data-stu-id="c57e5-116">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="c57e5-117">打开浏览器的专用实例并登录到 Azure 门户在[https://portal.azure.com](https://portal.azure.com)与 Microsoft 365 企业版测试环境的全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="c57e5-117">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="c57e5-118">在 Azure 门户中，单击**所有服务 > 市场**。</span><span class="sxs-lookup"><span data-stu-id="c57e5-118">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="c57e5-119">键入**Azure AD 身份保护**，然后单击它。</span><span class="sxs-lookup"><span data-stu-id="c57e5-119">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="c57e5-120">**Getting Started**刀片上,**设置**下单击**Onboard** ，单击**固定至仪表板**，，然后单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="c57e5-120">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="c57e5-121">在 Azure 门户中，单击仪表板上的**Azure AD 身份防护**。</span><span class="sxs-lookup"><span data-stu-id="c57e5-121">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="c57e5-p103">您应看到**Azure AD 身份保护-概述**刀片仪表板。在下，**安全漏洞**，请注意，它决定不多因素身份验证注册的用户帐户数。此号码将因以前 Microsoft 365 Enterprise 测试实验室指南，您已完成。</span><span class="sxs-lookup"><span data-stu-id="c57e5-p103">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard. Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration. This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="c57e5-125">单击通过**调查**以查看是否有任何用户或已检测到的事件类别。</span><span class="sxs-lookup"><span data-stu-id="c57e5-125">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="c57e5-126">进一步测试和实验，请参阅[模拟风险事件](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)。</span><span class="sxs-lookup"><span data-stu-id="c57e5-126">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="c57e5-127">在标识阶段的信息和链接以部署生产环境中的 Azure AD 身份保护，请参阅[Protect 针对凭据损害](identity-azure-ad-identity-protection.md)步骤。</span><span class="sxs-lookup"><span data-stu-id="c57e5-127">See the [Protect against credential compromise](identity-azure-ad-identity-protection.md) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="c57e5-128">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c57e5-128">Next step</span></span>

<span data-ttu-id="c57e5-129">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="c57e5-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c57e5-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c57e5-130">See also</span></span>

[<span data-ttu-id="c57e5-131">阶段 2：身份</span><span class="sxs-lookup"><span data-stu-id="c57e5-131">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="c57e5-132">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="c57e5-132">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c57e5-133">Microsoft 365 企业版部署</span><span class="sxs-lookup"><span data-stu-id="c57e5-133">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="c57e5-134">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="c57e5-134">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
