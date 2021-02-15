---
title: 针对 Microsoft 365 的标识和设备访问测试环境
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 创建一个 Microsoft 365 环境来测试标识和设备访问情况。
ms.openlocfilehash: ed143341079a55d6bdd1d4a68feea68acb86ef85
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233724"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="2cea4-103">针对 Microsoft 365 的标识和设备访问测试环境</span><span class="sxs-lookup"><span data-stu-id="2cea4-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="2cea4-104">*本测试实验室指南仅适用于 Microsoft 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="2cea4-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="2cea4-105">[标识和设备访问](../security/office-365-security/microsoft-365-policies-configurations.md) 配置是一组推荐的配置和条件访问策略，用于保护对与 Azure Active Directory (Azure AD) 集成的所有服务的访问。</span><span class="sxs-lookup"><span data-stu-id="2cea4-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="2cea4-106">若要创建具有通用标识和设备访问配置的测试环境，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2cea4-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="2cea4-107">根据所选的标识模型和身份验证方法，使用必备标识和安全功能来配置测试环境：</span><span class="sxs-lookup"><span data-stu-id="2cea4-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="2cea4-108">仅限云</span><span class="sxs-lookup"><span data-stu-id="2cea4-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="2cea4-109">PHS (密码哈希) </span><span class="sxs-lookup"><span data-stu-id="2cea4-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="2cea4-110">直通身份验证 (PTA)</span><span class="sxs-lookup"><span data-stu-id="2cea4-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="2cea4-111">使用 [通用标识和设备](identity-access-policies.md) 访问策略配置基于为测试环境配置的先决条件构建的策略，并探索和验证标识和设备保护。</span><span class="sxs-lookup"><span data-stu-id="2cea4-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="2cea4-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cea4-112">See also</span></span>

[<span data-ttu-id="2cea4-113">其他标识测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="2cea4-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="2cea4-114">标识路线图</span><span class="sxs-lookup"><span data-stu-id="2cea4-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="2cea4-115">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="2cea4-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2cea4-116">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="2cea4-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2cea4-117">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="2cea4-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
