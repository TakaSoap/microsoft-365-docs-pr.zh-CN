---
title: 适用于 Microsoft 365 企业版测试环境的 Azure AD 标识保护
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 配置 Azure AD 标识保护并分析 Microsoft 365 企业版测试环境中的当前帐户。
ms.openlocfilehash: a21b20f4ca774ad38990e44abc18d666426e74d5
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640401"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4f467-103">适用于 Microsoft 365 企业版测试环境的 Azure AD 标识保护</span><span class="sxs-lookup"><span data-stu-id="4f467-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4f467-104">通过 Azure AD 标识保护，可以检测影响组织标识、配置自动响应和调查事件的潜在漏洞。</span><span class="sxs-lookup"><span data-stu-id="4f467-104">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="4f467-105">本文介绍如何启用 Azure AD Identity Protection 并查看测试环境帐户的分析。</span><span class="sxs-lookup"><span data-stu-id="4f467-105">This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="4f467-106">在 Microsoft 365 企业版测试环境中设置 Azure AD 标识保护有两个阶段：</span><span class="sxs-lookup"><span data-stu-id="4f467-106">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="4f467-107">创建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="4f467-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="4f467-108">启用和使用 Azure AD Identity Protection。</span><span class="sxs-lookup"><span data-stu-id="4f467-108">Enable and use Azure AD Identity Protection.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="4f467-110">单击[此处](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。</span><span class="sxs-lookup"><span data-stu-id="4f467-110">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="4f467-111">阶段 1：构建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="4f467-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="4f467-112">如果只想使用最低要求以轻型方式测试 Azure AD 标识保护，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="4f467-112">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4f467-113">如果要在模拟的企业中测试 Azure AD 标识保护，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="4f467-113">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f467-114">测试 Azure AD Identity Protection 不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务（AD DS）林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="4f467-114">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="4f467-115">此处提供它作为选项，以便您可以在代表典型组织的环境中测试 Azure AD 标识保护并对其进行实验。</span><span class="sxs-lookup"><span data-stu-id="4f467-115">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="4f467-116">第2阶段：启用和使用 Azure AD 标识保护</span><span class="sxs-lookup"><span data-stu-id="4f467-116">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="4f467-117">打开浏览器的私有实例，并[https://portal.azure.com](https://portal.azure.com)使用 Microsoft 365 企业版测试环境的全局管理员帐户登录到 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="4f467-117">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="4f467-118">在 Azure 门户中，单击 "**所有服务 > Marketplace**"。</span><span class="sxs-lookup"><span data-stu-id="4f467-118">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="4f467-119">键入**AZURE AD Identity Protection** ，然后单击它。</span><span class="sxs-lookup"><span data-stu-id="4f467-119">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="4f467-120">在 "**入门" 边栏选项**卡上的 **"设置** **" 下，单击 "** **固定到仪表板**"，然后单击 "**创建**"。</span><span class="sxs-lookup"><span data-stu-id="4f467-120">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="4f467-121">在 Azure 门户中，单击仪表板上的 " **AZURE AD 标识保护**"。</span><span class="sxs-lookup"><span data-stu-id="4f467-121">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="4f467-122">您应该会看到一个带有仪表板的**AZURE AD 标识保护-概述**刀片。</span><span class="sxs-lookup"><span data-stu-id="4f467-122">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard.</span></span> <span data-ttu-id="4f467-123">在 "**漏洞**" 下，请注意，它确定了没有多重身份验证注册的用户帐户数。</span><span class="sxs-lookup"><span data-stu-id="4f467-123">Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration.</span></span> <span data-ttu-id="4f467-124">此数字取决于您已完成的以前的 Microsoft 365 企业测试实验室指南。</span><span class="sxs-lookup"><span data-stu-id="4f467-124">This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="4f467-125">依次单击要进行**调查**的类别，以查看是否有任何用户或事件已检测到。</span><span class="sxs-lookup"><span data-stu-id="4f467-125">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="4f467-126">有关进一步的测试和实验，请参阅[模拟风险事件](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)。</span><span class="sxs-lookup"><span data-stu-id="4f467-126">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="4f467-127">若要了解如何在生产环境中部署 Azure AD 标识保护的信息和链接，请参阅 Identity 阶段中的防止[凭据泄露](identity-secure-user-sign-ins.md#identity-ident-prot)步骤。</span><span class="sxs-lookup"><span data-stu-id="4f467-127">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="4f467-128">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4f467-128">Next step</span></span>

<span data-ttu-id="4f467-129">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="4f467-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f467-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f467-130">See also</span></span>

[<span data-ttu-id="4f467-131">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="4f467-131">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="4f467-132">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="4f467-132">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4f467-133">Microsoft 365 企业版部署</span><span class="sxs-lookup"><span data-stu-id="4f467-133">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="4f467-134">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="4f467-134">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
