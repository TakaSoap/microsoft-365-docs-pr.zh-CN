---
title: 适用于 Microsoft 365 企业版测试环境的 Azure AD 标识保护
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 配置 Azure AD 标识保护并分析 Microsoft 365 企业版测试环境中的当前帐户。
ms.openlocfilehash: c0d364eaef9cfd37531d9f9e1803db66739a7984
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802097"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b010c-103">适用于 Microsoft 365 企业版测试环境的 Azure AD 标识保护</span><span class="sxs-lookup"><span data-stu-id="b010c-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b010c-104">*此测试实验室指南仅可用于 Microsoft 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="b010c-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="b010c-105">Azure Active Directory （Azure AD） Identity Protection 允许您检测影响组织标识、配置自动响应和调查事件的潜在漏洞。</span><span class="sxs-lookup"><span data-stu-id="b010c-105">Azure Active Directory (Azure AD) Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="b010c-106">本文介绍如何使用 Azure AD Identity Protection 查看测试环境帐户的分析。</span><span class="sxs-lookup"><span data-stu-id="b010c-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="b010c-107">在 Microsoft 365 企业版测试环境中设置 Azure AD 标识保护有两个阶段：</span><span class="sxs-lookup"><span data-stu-id="b010c-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="b010c-108">创建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="b010c-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="b010c-109">使用 Azure AD Identity Protection。</span><span class="sxs-lookup"><span data-stu-id="b010c-109">Use Azure AD Identity Protection.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="b010c-111">单击[此处](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。</span><span class="sxs-lookup"><span data-stu-id="b010c-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b010c-112">阶段 1：构建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="b010c-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b010c-113">如果只想使用最低要求以轻型方式测试 Azure AD 标识保护，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="b010c-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b010c-114">如果要在模拟的企业中测试 Azure AD 标识保护，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="b010c-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b010c-115">测试 Azure AD Identity Protection 不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务（AD DS）林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="b010c-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b010c-116">此处提供它作为选项，以便您可以在代表典型组织的环境中测试 Azure AD 标识保护并对其进行实验。</span><span class="sxs-lookup"><span data-stu-id="b010c-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="b010c-117">第2阶段：使用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="b010c-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="b010c-118">打开浏览器的私有实例，并[https://portal.azure.com](https://portal.azure.com)使用 Microsoft 365 企业版测试环境的全局管理员帐户登录到 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="b010c-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="b010c-119">在 Azure 门户中，在搜索框中键入**标识保护**，然后单击 " **Azure AD identity protection**"。</span><span class="sxs-lookup"><span data-stu-id="b010c-119">In the Azure portal, type **identity protection** in the search box, and then click **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="b010c-120">在 "**身份保护-概述**" 刀片中，单击每个报告以查看报告的内容。</span><span class="sxs-lookup"><span data-stu-id="b010c-120">In the **Identity Protection - Overview** blade, click on each of the reports to see what they are reporting.</span></span>
4. <span data-ttu-id="b010c-121">在 "**通知**" 下，单击 "用户"，**查看风险检测警报**。</span><span class="sxs-lookup"><span data-stu-id="b010c-121">Under **Notify**, click **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="b010c-122">在 "**检测到风险的用户警报**" 窗格中，选择 "**中**"。</span><span class="sxs-lookup"><span data-stu-id="b010c-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="b010c-123">对于**向以下用户发送电子邮件**，请单击 "**包含**"，并验证全局管理员帐户是否在所选成员列表中。</span><span class="sxs-lookup"><span data-stu-id="b010c-123">For **Emails are sent to the following users**, click **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="b010c-124">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="b010c-124">Click **Save**.</span></span>

<span data-ttu-id="b010c-125">依次单击 "**保护**" 下的不同策略以查看如何配置它们。</span><span class="sxs-lookup"><span data-stu-id="b010c-125">Click through the different policies under **Protect** to see how to configure them.</span></span> <span data-ttu-id="b010c-126">如果您创建并激活策略，请确保它没有阻止对条件范围过宽的访问，或者您可能无法登录，即使是全局管理员也是如此。</span><span class="sxs-lookup"><span data-stu-id="b010c-126">If you create and activate a policy, make sure it is not blocking access for too wide a scope of conditions, or you might not be able to sign in, even as the global admin.</span></span>

<span data-ttu-id="b010c-127">有关进一步的测试和实验，请参阅[模拟风险事件](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)。</span><span class="sxs-lookup"><span data-stu-id="b010c-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="b010c-128">若要了解如何在生产环境中部署 Azure AD 标识保护的信息和链接，请参阅 Identity 阶段中的防止[凭据泄露](identity-secure-user-sign-ins.md#identity-ident-prot)步骤。</span><span class="sxs-lookup"><span data-stu-id="b010c-128">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="b010c-129">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b010c-129">Next step</span></span>

<span data-ttu-id="b010c-130">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="b010c-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b010c-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b010c-131">See also</span></span>

[<span data-ttu-id="b010c-132">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="b010c-132">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="b010c-133">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="b010c-133">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b010c-134">Microsoft 365 企业版部署</span><span class="sxs-lookup"><span data-stu-id="b010c-134">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b010c-135">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="b010c-135">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
