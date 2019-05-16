---
title: 针对 Microsoft 365 的标识和设备访问测试环境
author: JoeDavies-MSFT
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
ms.openlocfilehash: 9195f532222511fc9dce474617ed52916d8e382a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073592"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="2ffc7-103">针对 Microsoft 365 的标识和设备访问测试环境</span><span class="sxs-lookup"><span data-stu-id="2ffc7-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="2ffc7-104">[标识和设备访问配置](microsoft-365-policies-configurations.md)是一组功能和条件访问策略，用于保护对与 Azure Active Directory (Azure AD) 集成的所有服务的访问，包括 Microsoft 365 企业版中的 Office 365 和企业移动性 + 安全性 (EMS)。</span><span class="sxs-lookup"><span data-stu-id="2ffc7-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="2ffc7-105">要创建一个部署有这些策略的测试环境：</span><span class="sxs-lookup"><span data-stu-id="2ffc7-105">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="2ffc7-106">根据所选的标识模型和身份验证方法，使用必备标识和安全功能来配置测试环境：</span><span class="sxs-lookup"><span data-stu-id="2ffc7-106">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="2ffc7-107">仅限云</span><span class="sxs-lookup"><span data-stu-id="2ffc7-107">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="2ffc7-108">密码哈希同步 (PHS)</span><span class="sxs-lookup"><span data-stu-id="2ffc7-108">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="2ffc7-109">直通身份验证 (PTA)</span><span class="sxs-lookup"><span data-stu-id="2ffc7-109">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="2ffc7-110">使用[常见标识和设备访问策略](identity-access-policies.md)来配置基于先决条件构建的策略并对标识和设备的保护进行测试。</span><span class="sxs-lookup"><span data-stu-id="2ffc7-110">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="2ffc7-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ffc7-111">See also</span></span>

[<span data-ttu-id="2ffc7-112">其他标识测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="2ffc7-112">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="2ffc7-113">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="2ffc7-113">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="2ffc7-114">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="2ffc7-114">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2ffc7-115">Microsoft 365 企业版部署</span><span class="sxs-lookup"><span data-stu-id="2ffc7-115">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="2ffc7-116">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="2ffc7-116">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
