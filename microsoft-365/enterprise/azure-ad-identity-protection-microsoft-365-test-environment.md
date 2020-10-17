---
title: 适用于 Microsoft 365 企业版测试环境的 Azure AD 标识保护
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
description: 配置 Azure AD 标识保护并分析 Microsoft 365 for 企业测试环境中的当前帐户。
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487704"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="04735-103">适用于 Microsoft 365 企业版测试环境的 Azure AD 标识保护</span><span class="sxs-lookup"><span data-stu-id="04735-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="04735-104">*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="04735-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="04735-105">您可以使用 Azure Active Directory (Azure AD) 标识保护，以检测影响组织的身份、配置自动响应和调查事件的潜在漏洞。</span><span class="sxs-lookup"><span data-stu-id="04735-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="04735-106">本文介绍如何使用 Azure AD Identity Protection 查看测试环境帐户的分析。</span><span class="sxs-lookup"><span data-stu-id="04735-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="04735-107">在 Microsoft 365 for 企业测试环境中设置 Azure AD 标识保护包括两个阶段：</span><span class="sxs-lookup"><span data-stu-id="04735-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="04735-108">第1阶段：构建您的 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="04735-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="04735-109">第2阶段：使用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="04735-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="04735-111">若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="04735-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="04735-112">第1阶段：构建您的 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="04735-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="04735-113">如果你希望仅使用最低要求以轻型方式测试 Azure AD Identity Protection，请按照 [轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="04735-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="04735-114">如果要在模拟的企业中测试 Azure AD 标识保护，请按照 [传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="04735-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="04735-115">测试 Azure AD 标识保护不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="04735-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="04735-116">此处提供它作为选项，以便您可以在代表典型组织的环境中测试 Azure AD 标识保护并对其进行实验。</span><span class="sxs-lookup"><span data-stu-id="04735-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="04735-117">第2阶段：使用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="04735-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="04735-118">打开浏览器的私有实例，并 [https://portal.azure.com](https://portal.azure.com) 使用 Microsoft 365 for 企业版测试环境的全局管理员帐户登录 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="04735-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="04735-119">在 Azure 门户中，在搜索框中键入 **identity protection** ，然后选择 " **Azure AD identity protection**"。</span><span class="sxs-lookup"><span data-stu-id="04735-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="04735-120">在 " **身份保护-概述** " 刀片中，选择每个报告以查看报告的内容。</span><span class="sxs-lookup"><span data-stu-id="04735-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="04735-121">在 " **通知**" 下，选择 "用户" " **风险检测警报**"。</span><span class="sxs-lookup"><span data-stu-id="04735-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="04735-122">在 " **检测到风险的用户警报** " 窗格中，选择 " **中**"。</span><span class="sxs-lookup"><span data-stu-id="04735-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="04735-123">对于 **向以下用户发送电子邮件**，请选择 " **包含** "，并验证全局管理员帐户是否在所选成员列表中。</span><span class="sxs-lookup"><span data-stu-id="04735-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="04735-124">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="04735-124">Select **Save**.</span></span>

<span data-ttu-id="04735-125">在 " **保护**" 下，选择各种策略以查看如何配置它们。</span><span class="sxs-lookup"><span data-stu-id="04735-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="04735-126">如果您创建并激活策略，请确保它不会阻止对所有用户的访问，否则您可能无法登录。</span><span class="sxs-lookup"><span data-stu-id="04735-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="04735-127">若要防止出现这种情况，请排除特定用户帐户，如全局管理员。</span><span class="sxs-lookup"><span data-stu-id="04735-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="04735-128">有关进一步的测试和实验，请参阅 [模拟风险事件](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)。</span><span class="sxs-lookup"><span data-stu-id="04735-128">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="04735-129">后续步骤</span><span class="sxs-lookup"><span data-stu-id="04735-129">Next step</span></span>

<span data-ttu-id="04735-130">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="04735-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="04735-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04735-131">See also</span></span>

[<span data-ttu-id="04735-132">标识路线图</span><span class="sxs-lookup"><span data-stu-id="04735-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="04735-133">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="04735-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="04735-134">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="04735-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="04735-135">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="04735-135">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
