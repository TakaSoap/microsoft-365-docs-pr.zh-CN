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
ms.openlocfilehash: 427b0589da0347008cca0e2004bc23f494bebb29
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907464"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="328e4-103">针对 Microsoft 365 的标识和设备访问测试环境</span><span class="sxs-lookup"><span data-stu-id="328e4-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="328e4-104">*本测试实验室指南仅适用于 Microsoft 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="328e4-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="328e4-105">[标识和设备访问](../security/office-365-security/microsoft-365-policies-configurations.md) 配置是一组建议配置和条件访问策略，用于保护对与 Azure AD (Azure Active Directory 集成的所有服务) 。</span><span class="sxs-lookup"><span data-stu-id="328e4-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="328e4-106">若要创建具有通用标识和设备访问配置的测试环境，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="328e4-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="328e4-107">根据所选的标识模型和身份验证方法，使用必备标识和安全功能来配置测试环境：</span><span class="sxs-lookup"><span data-stu-id="328e4-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="328e4-108">仅限云</span><span class="sxs-lookup"><span data-stu-id="328e4-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="328e4-109">PHS (密码哈希) </span><span class="sxs-lookup"><span data-stu-id="328e4-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="328e4-110">直通身份验证 (PTA)</span><span class="sxs-lookup"><span data-stu-id="328e4-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="328e4-111">使用 [通用标识和设备](../security/office-365-security/identity-access-policies.md) 访问策略配置基于为测试环境配置的先决条件构建的策略，并探索并验证标识和设备保护。</span><span class="sxs-lookup"><span data-stu-id="328e4-111">Use [Common identity and device access policies](../security/office-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="328e4-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="328e4-112">See also</span></span>

[<span data-ttu-id="328e4-113">其他标识测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="328e4-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="328e4-114">标识路线图</span><span class="sxs-lookup"><span data-stu-id="328e4-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="328e4-115">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="328e4-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="328e4-116">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="328e4-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="328e4-117">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="328e4-117">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)