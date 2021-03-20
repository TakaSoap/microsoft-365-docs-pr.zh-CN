---
title: 适用于 Microsoft 365 企业版测试环境的 Azure AD Identity Protection
f1.keywords:
- NOCSH
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
description: 配置 Azure AD Identity Protection 并分析 Microsoft 365 企业版测试环境中的当前帐户。
ms.openlocfilehash: 0cb0acf3faee13676573b04178bd6b4d3d36da4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905340"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="55e84-103">适用于 Microsoft 365 企业版测试环境的 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="55e84-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="55e84-104">*本测试实验室指南仅适用于 Microsoft 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="55e84-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="55e84-105">可以使用 Azure Active Directory (Azure AD) Identity Protection 检测影响组织标识的潜在漏洞，配置自动响应并调查事件。</span><span class="sxs-lookup"><span data-stu-id="55e84-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="55e84-106">本文介绍如何使用 Azure AD Identity Protection 查看测试环境帐户的分析。</span><span class="sxs-lookup"><span data-stu-id="55e84-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="55e84-107">在 Microsoft 365 企业版测试环境中设置 Azure AD Identity Protection 涉及两个阶段：</span><span class="sxs-lookup"><span data-stu-id="55e84-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="55e84-108">第 1 阶段：构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="55e84-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="55e84-109">阶段 2：使用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="55e84-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="55e84-111">有关 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观地图，请转到 [Microsoft 365 企业版测试实验室指南堆栈](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="55e84-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="55e84-112">第 1 阶段：构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="55e84-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="55e84-113">如果你希望仅测试具有最低要求的轻型 Azure AD Identity Protection，请按照轻型基本配置 [中的说明进行操作](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="55e84-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="55e84-114">如果要在模拟的企业中测试 Azure AD Identity Protection，请按照传递身份验证 [中的说明操作](pass-through-auth-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="55e84-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="55e84-115">测试 Azure AD Identity Protection 不需要模拟的企业测试环境，该环境中包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务 (AD DS) 的目录同步。</span><span class="sxs-lookup"><span data-stu-id="55e84-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="55e84-116">它在此处作为一个选项提供，以便你可以测试 Azure AD Identity Protection，在代表典型组织的环境中试验它。</span><span class="sxs-lookup"><span data-stu-id="55e84-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="55e84-117">阶段 2：使用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="55e84-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="55e84-118">打开浏览器的专用实例，然后使用 Microsoft 365 企业版测试环境的全局管理员帐户登录到 Azure [https://portal.azure.com](https://portal.azure.com) 门户 。。</span><span class="sxs-lookup"><span data-stu-id="55e84-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="55e84-119">在 Azure 门户中， **在搜索框中** 键入标识保护，然后选择 **Azure AD Identity Protection**。</span><span class="sxs-lookup"><span data-stu-id="55e84-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="55e84-120">在 **"Identity Protection - 概述"** 边栏选项卡中，选择每个报告以查看报告内容。</span><span class="sxs-lookup"><span data-stu-id="55e84-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="55e84-121">在 **"通知"** 下 **，选择"处于风险中检测到警报的用户"。**</span><span class="sxs-lookup"><span data-stu-id="55e84-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="55e84-122">在"**存在风险的用户检测到警报"窗格中**，选择"中等 **"。**</span><span class="sxs-lookup"><span data-stu-id="55e84-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="55e84-123">For **Emails are sent to the following users，** select **Included** and verify that your global admin account is in the list of selected members.</span><span class="sxs-lookup"><span data-stu-id="55e84-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="55e84-124">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="55e84-124">Select **Save**.</span></span>

<span data-ttu-id="55e84-125">在 **"保护**"下，选择各种策略以查看如何配置策略。</span><span class="sxs-lookup"><span data-stu-id="55e84-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="55e84-126">如果创建并激活策略，请确保它不会阻止所有用户的访问，否则可能无法登录。</span><span class="sxs-lookup"><span data-stu-id="55e84-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="55e84-127">若要阻止这种情况发生，请排除特定用户帐户，例如全局管理员。</span><span class="sxs-lookup"><span data-stu-id="55e84-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="55e84-128">有关进一步测试和实验，请参阅 [模拟风险事件](/azure/active-directory/active-directory-identityprotection-playbook)。</span><span class="sxs-lookup"><span data-stu-id="55e84-128">For further testing and experimentation, see [Simulating risk events](/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="55e84-129">后续步骤</span><span class="sxs-lookup"><span data-stu-id="55e84-129">Next step</span></span>

<span data-ttu-id="55e84-130">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="55e84-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="55e84-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55e84-131">See also</span></span>

[<span data-ttu-id="55e84-132">标识路线图</span><span class="sxs-lookup"><span data-stu-id="55e84-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="55e84-133">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="55e84-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="55e84-134">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="55e84-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="55e84-135">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="55e84-135">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)