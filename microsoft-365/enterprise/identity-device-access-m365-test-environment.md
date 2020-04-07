---
title: 针对 Microsoft 365 的标识和设备访问测试环境
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 创建一个 Microsoft 365 环境来测试标识和设备访问情况。
ms.openlocfilehash: 45749140698553a75df50ed1111cdbfc8eb15684
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153734"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="eada4-103">针对 Microsoft 365 的标识和设备访问测试环境</span><span class="sxs-lookup"><span data-stu-id="eada4-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="eada4-104">*此测试实验室指南仅可用于 Microsoft 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="eada4-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="eada4-105">[标识和设备访问配置](microsoft-365-policies-configurations.md)是一组功能和条件访问策略，用于保护对与 Azure Active Directory (Azure AD) 集成的所有服务的访问，包括 Microsoft 365 企业版中的 Office 365 和 Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="eada4-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and Conditional Access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Microsoft Intune in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="eada4-106">要创建一个部署有这些策略的测试环境：</span><span class="sxs-lookup"><span data-stu-id="eada4-106">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="eada4-107">根据所选的标识模型和身份验证方法，使用必备标识和安全功能来配置测试环境：</span><span class="sxs-lookup"><span data-stu-id="eada4-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="eada4-108">仅限云</span><span class="sxs-lookup"><span data-stu-id="eada4-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="eada4-109">密码哈希同步 (PHS)</span><span class="sxs-lookup"><span data-stu-id="eada4-109">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="eada4-110">直通身份验证 (PTA)</span><span class="sxs-lookup"><span data-stu-id="eada4-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="eada4-111">使用[常见标识和设备访问策略](identity-access-policies.md)来配置基于先决条件构建的策略并对标识和设备的保护进行测试。</span><span class="sxs-lookup"><span data-stu-id="eada4-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="eada4-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eada4-112">See also</span></span>

[<span data-ttu-id="eada4-113">其他标识测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="eada4-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="eada4-114">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="eada4-114">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="eada4-115">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="eada4-115">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="eada4-116">Microsoft 365 企业版部署</span><span class="sxs-lookup"><span data-stu-id="eada4-116">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="eada4-117">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="eada4-117">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
