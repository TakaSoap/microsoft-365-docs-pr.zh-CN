---
title: 步骤 5. 适用于企业租户的 Microsoft 365 设备和应用管理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: 为 Microsoft 365 租户部署正确的设备和应用管理选项。
ms.openlocfilehash: 96412cb52540e87341fa67e20382951db7becfbe
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406368"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="c6cec-104">步骤 5.</span><span class="sxs-lookup"><span data-stu-id="c6cec-104">Step 5.</span></span> <span data-ttu-id="c6cec-105">适用于企业租户的 Microsoft 365 设备和应用管理</span><span class="sxs-lookup"><span data-stu-id="c6cec-105">Device and app management for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="c6cec-106">Microsoft 365 企业版包括以下功能：通过移动设备管理 (MDM) 和移动应用程序管理 (MAM) 帮助管理设备以及在这些设备上使用应用。</span><span class="sxs-lookup"><span data-stu-id="c6cec-106">Microsoft 365 for enterprise includes features to help manage devices and the use of apps on those devices within your organization with mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="c6cec-107">你可以管理 iOS、Android、macOS 和 Windows 设备，以保护对组织资源（包括数据）的访问。</span><span class="sxs-lookup"><span data-stu-id="c6cec-107">You can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="c6cec-108">例如，可以阻止向组织外部人员发送电子邮件，或将组织数据与工作者的个人设备上个人数据隔离。</span><span class="sxs-lookup"><span data-stu-id="c6cec-108">For example, you can prevent emails from being sent to people outside your organization or isolate organization data from personal data on your worker's personal devices.</span></span>

<span data-ttu-id="c6cec-109">下面是验证和管理用户、其设备及其使用本地和云生产力应用（如 Microsoft Teams）的示例。</span><span class="sxs-lookup"><span data-stu-id="c6cec-109">Here is an example of the validation and management of users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![用户、设备和应用的验证和管理](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

<span data-ttu-id="c6cec-111">为了帮助你保护组织的资源，Microsoft 365 企业版包括可帮助管理设备及其访问应用的功能。</span><span class="sxs-lookup"><span data-stu-id="c6cec-111">To help you secure and protect your organization's resources, Microsoft 365 for enterprise includes features to help manage devices and their access to apps.</span></span> <span data-ttu-id="c6cec-112">设备管理有两个选项：</span><span class="sxs-lookup"><span data-stu-id="c6cec-112">There are two options for device management:</span></span>

- <span data-ttu-id="c6cec-113">Microsoft Intune，它是一款全面的设备和企业应用管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="c6cec-113">Microsoft Intune, which is a comprehensive device and app management solution for enterprises.</span></span>
- <span data-ttu-id="c6cec-114">基本移动性和安全性，这是用于管理组织中设备的所有 Microsoft 365 产品中包含的 Intune 服务的子集。</span><span class="sxs-lookup"><span data-stu-id="c6cec-114">Basic Mobility and Security, which is a subset of Intune services included with all Microsoft 365 products for managing devices in your organization.</span></span> <span data-ttu-id="c6cec-115">有关详细信息，请参阅 [基本移动性和安全性的功能](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities)。</span><span class="sxs-lookup"><span data-stu-id="c6cec-115">For more information, see [Capabilities of Basic Mobility and Security](https://docs.microsoft.com/microsoft-365/admin/basic-mobility-security/capabilities).</span></span>

<span data-ttu-id="c6cec-116">如果你有 Microsoft 365 E3 或 E5，你应该使用 Intune。</span><span class="sxs-lookup"><span data-stu-id="c6cec-116">If you have Microsoft 365 E3 or E5, you should use Intune.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="c6cec-117">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c6cec-117">Microsoft Intune</span></span>

<span data-ttu-id="c6cec-118">使用 [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) 使用 MDM 或 MAM 管理对组织的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c6cec-118">You use [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide) to manage access to your organization using MDM or MAM.</span></span> <span data-ttu-id="c6cec-119">MDM 是当用户在 Intune 中"注册"其设备时。</span><span class="sxs-lookup"><span data-stu-id="c6cec-119">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="c6cec-120">注册设备后，该设备即为托管设备，可以接收组织的策略、规则和设置。</span><span class="sxs-lookup"><span data-stu-id="c6cec-120">After a device is enrolled, it is a managed device and can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="c6cec-121">例如，你可以安装特定应用、创建密码策略、安装 VPN 连接等。</span><span class="sxs-lookup"><span data-stu-id="c6cec-121">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="c6cec-122">拥有自己的个人设备的用户可能不希望注册其设备或由 Intune 和组织的策略进行管理。</span><span class="sxs-lookup"><span data-stu-id="c6cec-122">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="c6cec-123">但你仍然需要保护组织的资源和数据。</span><span class="sxs-lookup"><span data-stu-id="c6cec-123">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="c6cec-124">在此方案中，可以使用 MAM 保护应用。</span><span class="sxs-lookup"><span data-stu-id="c6cec-124">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="c6cec-125">例如，可以使用 MAM 策略，该策略要求用户在访问设备的 SharePoint 时输入 PIN。</span><span class="sxs-lookup"><span data-stu-id="c6cec-125">For example, you can use an MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="c6cec-126">你还将确定你将如何管理个人设备和组织拥有的设备。</span><span class="sxs-lookup"><span data-stu-id="c6cec-126">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="c6cec-127">你可能希望根据设备的用途以不同方式处理设备。</span><span class="sxs-lookup"><span data-stu-id="c6cec-127">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="c6cec-128">标识和设备访问配置</span><span class="sxs-lookup"><span data-stu-id="c6cec-128">Identity and device access configurations</span></span>

<span data-ttu-id="c6cec-129">Microsoft 提供了一组用于 [标识和设备访问的配置](../security/office-365-security/microsoft-365-policies-configurations.md) ，以确保员工安全高效。</span><span class="sxs-lookup"><span data-stu-id="c6cec-129">Microsoft provides a set of configurations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="c6cec-130">这些配置包括以下项的使用：</span><span class="sxs-lookup"><span data-stu-id="c6cec-130">These configurations include the use of:</span></span>

- <span data-ttu-id="c6cec-131">Azure AD 条件访问策略</span><span class="sxs-lookup"><span data-stu-id="c6cec-131">Azure AD Conditional Access policies</span></span>
- <span data-ttu-id="c6cec-132">Microsoft Intune 设备合规性应用保护策略</span><span class="sxs-lookup"><span data-stu-id="c6cec-132">Microsoft Intune device compliance and app protection policies</span></span>
- <span data-ttu-id="c6cec-133">Azure AD Identity Protection 用户风险策略</span><span class="sxs-lookup"><span data-stu-id="c6cec-133">Azure AD Identity Protection user risk policies</span></span>
- <span data-ttu-id="c6cec-134">云应用的其他策略</span><span class="sxs-lookup"><span data-stu-id="c6cec-134">Additional policies of cloud apps</span></span>

<span data-ttu-id="c6cec-135">下面是应用这些设置和策略以验证和限制用户及其设备，以及用户对本地和云生产力应用（如 Microsoft Teams）的使用的示例。</span><span class="sxs-lookup"><span data-stu-id="c6cec-135">Here is an example of the application of these settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![针对用户、设备及其应用使用的要求和限制的标识和设备访问配置](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

<span data-ttu-id="c6cec-137">对于设备访问和应用管理，请使用以下文章中的配置：</span><span class="sxs-lookup"><span data-stu-id="c6cec-137">For device access and app management, use the configurations in these articles:</span></span>

- [<span data-ttu-id="c6cec-138">先决条件</span><span class="sxs-lookup"><span data-stu-id="c6cec-138">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="c6cec-139">常见标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="c6cec-139">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a><span data-ttu-id="c6cec-140">步骤 5 的结果</span><span class="sxs-lookup"><span data-stu-id="c6cec-140">Results of Step 5</span></span>

<span data-ttu-id="c6cec-141">对于 Microsoft 365 租户的设备和应用管理，你已确定 Intune 设置和策略以验证和限制用户及其设备，以及用户对本地和云生产力应用的使用。</span><span class="sxs-lookup"><span data-stu-id="c6cec-141">For device and app management for your Microsoft 365 tenant, you have determined the Intune settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps.</span></span>

<span data-ttu-id="c6cec-142">下面是一个租户示例，其中突出显示了新元素的 Intune 设备和应用管理。</span><span class="sxs-lookup"><span data-stu-id="c6cec-142">Here is an example of a tenant with Intune device and app management with the new elements highlighted.</span></span>

![具有 Intune 设备和应用管理的租户示例](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

<span data-ttu-id="c6cec-144">在此图中，租户具有：</span><span class="sxs-lookup"><span data-stu-id="c6cec-144">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="c6cec-145">在 Intune 中注册的组织拥有的设备。</span><span class="sxs-lookup"><span data-stu-id="c6cec-145">Organization-owned devices enrolled in Intune.</span></span>
- <span data-ttu-id="c6cec-146">已注册和个人设备的 Intune 设备和应用策略。</span><span class="sxs-lookup"><span data-stu-id="c6cec-146">Intune device and app policies for enrolled and personal devices.</span></span>

## <a name="ongoing-maintenance-for-device-and-app-management"></a><span data-ttu-id="c6cec-147">设备和应用管理的持续维护</span><span class="sxs-lookup"><span data-stu-id="c6cec-147">Ongoing maintenance for device and app management</span></span>

<span data-ttu-id="c6cec-148">你可能需要持续：</span><span class="sxs-lookup"><span data-stu-id="c6cec-148">On an ongoing basis, you might need to:</span></span> 

- <span data-ttu-id="c6cec-149">管理设备注册。</span><span class="sxs-lookup"><span data-stu-id="c6cec-149">Manage device enrollment.</span></span>
- <span data-ttu-id="c6cec-150">修改其他应用、设备和安全要求的设置和策略。</span><span class="sxs-lookup"><span data-stu-id="c6cec-150">Revise your settings and policies for additional apps, devices, and security requirements.</span></span>
