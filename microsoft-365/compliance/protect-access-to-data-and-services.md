---
title: 保护用户和设备的访问权限
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 了解如何保护用户和设备访问数据Microsoft 365服务，并防御数据丢失。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ff7bd2ff8b4b333eb30a6cc82797a8968941e0b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051694"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="5fd75-103">保护用户和设备的访问权限</span><span class="sxs-lookup"><span data-stu-id="5fd75-103">Protect user and device access</span></span>

<span data-ttu-id="5fd75-104">保护对Microsoft 365和服务的访问对于防御网络攻击和防止数据丢失至关重要。</span><span class="sxs-lookup"><span data-stu-id="5fd75-104">Protecting access to your Microsoft 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="5fd75-105">相同的保护可以应用于环境中的其他 SaaS 应用程序，甚至应用于使用 Azure Active Directory 应用程序代理发布的本地应用程序。</span><span class="sxs-lookup"><span data-stu-id="5fd75-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="5fd75-106">步骤 1：查看建议</span><span class="sxs-lookup"><span data-stu-id="5fd75-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="5fd75-107">用于保护访问 Office 365 设备、其他 SaaS 服务以及使用 Azure AD 应用代理发布的本地应用的标识和设备的推荐功能。</span><span class="sxs-lookup"><span data-stu-id="5fd75-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="5fd75-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [更多语言](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="5fd75-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="5fd75-109">步骤 2：保护管理员帐户和访问权限</span><span class="sxs-lookup"><span data-stu-id="5fd75-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="5fd75-110">用于管理环境的管理帐户Microsoft 365提升的权限。</span><span class="sxs-lookup"><span data-stu-id="5fd75-110">The administrative accounts you use to administer your Microsoft 365 environment include elevated privileges.</span></span> <span data-ttu-id="5fd75-111">这些是黑客和网络攻击的有价值目标。</span><span class="sxs-lookup"><span data-stu-id="5fd75-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="5fd75-112">首先，仅将管理员帐户用于管理。</span><span class="sxs-lookup"><span data-stu-id="5fd75-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="5fd75-113">管理员应具有单独的用户帐户，用于常规的非管理用途，并且仅在必要时使用其管理帐户来完成与其工作职能相关联的任务。</span><span class="sxs-lookup"><span data-stu-id="5fd75-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="5fd75-114">使用多重身份验证和条件访问保护管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="5fd75-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="5fd75-115">有关详细信息，请参阅 [保护管理员帐户](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts)。</span><span class="sxs-lookup"><span data-stu-id="5fd75-115">For more information, see [Protecting administrator accounts](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="5fd75-116">接下来，在 Office 365 中配置特权访问Office 365。</span><span class="sxs-lookup"><span data-stu-id="5fd75-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="5fd75-117">特权访问管理允许在 Office 365 中对特权管理任务精细的访问控制。</span><span class="sxs-lookup"><span data-stu-id="5fd75-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="5fd75-118">它可以帮助保护组织免受可能使用现有特权管理员帐户（长期访问敏感数据或访问关键配置设置）的泄露。</span><span class="sxs-lookup"><span data-stu-id="5fd75-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="5fd75-119">特权访问管理概述</span><span class="sxs-lookup"><span data-stu-id="5fd75-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="5fd75-120">配置特权访问管理</span><span class="sxs-lookup"><span data-stu-id="5fd75-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="5fd75-121">另一个首要建议是使用专为管理工作配置的工作站。</span><span class="sxs-lookup"><span data-stu-id="5fd75-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="5fd75-122">这些是仅用于管理任务的专用设备。</span><span class="sxs-lookup"><span data-stu-id="5fd75-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="5fd75-123">请参阅 [保护特权访问](/windows-server/identity/securing-privileged-access/securing-privileged-access)。</span><span class="sxs-lookup"><span data-stu-id="5fd75-123">See [Securing privileged access](/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="5fd75-124">最后，可以通过在租户中创建两个或多个紧急访问帐户来缓解意外缺少管理访问的影响。</span><span class="sxs-lookup"><span data-stu-id="5fd75-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="5fd75-125">请参阅 [在 Azure AD 中管理紧急访问帐户](/azure/active-directory/users-groups-roles/directory-emergency-access)。</span><span class="sxs-lookup"><span data-stu-id="5fd75-125">See [Manage emergency access accounts in Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="5fd75-126">步骤 3：配置推荐的标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="5fd75-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="5fd75-127">MFA (和) 访问策略的多重身份验证是抵御帐户损坏和未授权访问的强大工具。</span><span class="sxs-lookup"><span data-stu-id="5fd75-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="5fd75-128">我们建议实现一组已一起测试的策略。</span><span class="sxs-lookup"><span data-stu-id="5fd75-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="5fd75-129">有关详细信息（包括部署步骤，请参阅 [标识和设备访问配置](../security/defender-365-security/microsoft-365-policies-configurations.md)）。</span><span class="sxs-lookup"><span data-stu-id="5fd75-129">For more information, including deployment steps, see [Identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md).</span></span>

 <span data-ttu-id="5fd75-130">这些策略实现以下功能：</span><span class="sxs-lookup"><span data-stu-id="5fd75-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="5fd75-131">多重身份验证</span><span class="sxs-lookup"><span data-stu-id="5fd75-131">Mult-factor authentication</span></span>
- <span data-ttu-id="5fd75-132">条件访问</span><span class="sxs-lookup"><span data-stu-id="5fd75-132">Conditional access</span></span>
- <span data-ttu-id="5fd75-133">Intune 应用 (应用和数据保护功能，适用于) </span><span class="sxs-lookup"><span data-stu-id="5fd75-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="5fd75-134">Intune 设备合规性</span><span class="sxs-lookup"><span data-stu-id="5fd75-134">Intune device compliance</span></span>
- <span data-ttu-id="5fd75-135">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="5fd75-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="5fd75-136">实现 Intune 设备合规性需要设备注册。</span><span class="sxs-lookup"><span data-stu-id="5fd75-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="5fd75-137">通过管理设备，可以确保设备正常运行且合规，然后再允许它们访问环境中的资源。</span><span class="sxs-lookup"><span data-stu-id="5fd75-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="5fd75-138">请参阅 [在 Intune 中注册设备以管理](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="5fd75-138">See [Enroll devices for management in Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="5fd75-139">步骤 4：SharePoint设备访问策略</span><span class="sxs-lookup"><span data-stu-id="5fd75-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="5fd75-140">Microsoft 建议通过设备访问控制SharePoint敏感和高度管控内容保护网站中的内容。</span><span class="sxs-lookup"><span data-stu-id="5fd75-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="5fd75-141">有关详细信息，请参阅[用于保护网站和文件SharePoint策略建议](../security/defender-365-security/sharepoint-file-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="5fd75-141">For more information, see [Policy recommendations for securing SharePoint sites and files](../security/defender-365-security/sharepoint-file-access-policies.md).</span></span>



