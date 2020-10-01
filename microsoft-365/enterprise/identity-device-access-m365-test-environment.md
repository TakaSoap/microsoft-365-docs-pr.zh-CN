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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 创建一个 Microsoft 365 环境来测试标识和设备访问情况。
ms.openlocfilehash: 84af7747fc1d0e80e933397f4f0f96018ed246c3
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327803"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="422a1-103">针对 Microsoft 365 的标识和设备访问测试环境</span><span class="sxs-lookup"><span data-stu-id="422a1-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="422a1-104">*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="422a1-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="422a1-105">[标识和设备访问配置](microsoft-365-policies-configurations.md) 是一组功能和条件访问策略，用于保护与 Azure Active Directory (azure AD) 集成的所有服务的访问权限。</span><span class="sxs-lookup"><span data-stu-id="422a1-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="422a1-106">若要创建具有通用标识和设备访问配置的测试环境，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="422a1-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="422a1-107">根据所选的标识模型和身份验证方法，使用必备标识和安全功能来配置测试环境：</span><span class="sxs-lookup"><span data-stu-id="422a1-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="422a1-108">仅限云</span><span class="sxs-lookup"><span data-stu-id="422a1-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="422a1-109"> (PHS) 的密码哈希同步 </span><span class="sxs-lookup"><span data-stu-id="422a1-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="422a1-110">直通身份验证 (PTA)</span><span class="sxs-lookup"><span data-stu-id="422a1-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="422a1-111">使用 [通用标识和设备访问策略](identity-access-policies.md) 来配置基于为测试环境配置的先决条件的策略，并探索并验证身份和设备的保护。</span><span class="sxs-lookup"><span data-stu-id="422a1-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="422a1-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="422a1-112">See also</span></span>

[<span data-ttu-id="422a1-113">其他标识测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="422a1-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="422a1-114">标识路线图</span><span class="sxs-lookup"><span data-stu-id="422a1-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="422a1-115">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="422a1-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="422a1-116">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="422a1-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="422a1-117">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="422a1-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
