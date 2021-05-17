---
title: 步骤 5. 适用于企业租户Microsoft 365应用的设备和应用管理
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
description: 为租户部署正确的设备和应用管理Microsoft 365选项。
ms.openlocfilehash: 0351f6be3f191e1a131da5b0b665a205a0abda8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050990"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="f7124-104">步骤 5.</span><span class="sxs-lookup"><span data-stu-id="f7124-104">Step 5.</span></span> <span data-ttu-id="f7124-105">适用于企业租户Microsoft 365应用的设备和应用管理</span><span class="sxs-lookup"><span data-stu-id="f7124-105">Device and app management for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="f7124-106">Microsoft 365企业版包括以下功能：通过移动设备管理 (MDM) 和移动应用程序管理 (MAM) 帮助管理设备以及在这些设备上使用应用。</span><span class="sxs-lookup"><span data-stu-id="f7124-106">Microsoft 365 for enterprise includes features to help manage devices and the use of apps on those devices within your organization with mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="f7124-107">你可以管理 iOS、Android、macOS Windows设备来保护对组织资源（包括数据）的访问。</span><span class="sxs-lookup"><span data-stu-id="f7124-107">You can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="f7124-108">例如，可以阻止向组织外部人员发送电子邮件，或将组织数据与工作者的个人设备中的个人数据隔离。</span><span class="sxs-lookup"><span data-stu-id="f7124-108">For example, you can prevent emails from being sent to people outside your organization or isolate organization data from personal data on your worker's personal devices.</span></span>

<span data-ttu-id="f7124-109">下面是验证和管理用户及其设备，以及他们使用本地和云生产力应用（如 Microsoft Teams） 的示例。</span><span class="sxs-lookup"><span data-stu-id="f7124-109">Here is an example of the validation and management of users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![用户、设备和应用的验证和管理](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

<span data-ttu-id="f7124-111">为了帮助你保护组织的资源，Microsoft 365企业版包括可帮助管理设备及其对应用的访问权限的功能。</span><span class="sxs-lookup"><span data-stu-id="f7124-111">To help you secure and protect your organization's resources, Microsoft 365 for enterprise includes features to help manage devices and their access to apps.</span></span> <span data-ttu-id="f7124-112">设备管理有两个选项：</span><span class="sxs-lookup"><span data-stu-id="f7124-112">There are two options for device management:</span></span>

- <span data-ttu-id="f7124-113">Microsoft Intune，它是一款全面的企业设备和应用管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="f7124-113">Microsoft Intune, which is a comprehensive device and app management solution for enterprises.</span></span>
- <span data-ttu-id="f7124-114">基本移动性和安全性，它是所有用于管理组织中设备的 Microsoft 365 产品中包含的 Intune 服务的子集。</span><span class="sxs-lookup"><span data-stu-id="f7124-114">Basic Mobility and Security, which is a subset of Intune services included with all Microsoft 365 products for managing devices in your organization.</span></span> <span data-ttu-id="f7124-115">有关详细信息，请参阅[Capabilities of Basic Mobility and Security。](../admin/basic-mobility-security/capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="f7124-115">For more information, see [Capabilities of Basic Mobility and Security](../admin/basic-mobility-security/capabilities.md).</span></span>

<span data-ttu-id="f7124-116">如果你拥有Microsoft 365 E3 E5，则应该使用 Intune。</span><span class="sxs-lookup"><span data-stu-id="f7124-116">If you have Microsoft 365 E3 or E5, you should use Intune.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="f7124-117">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f7124-117">Microsoft Intune</span></span>

<span data-ttu-id="f7124-118">可使用[Microsoft Intune](/mem/intune/fundamentals/planning-guide) MDM 或 MAM 管理对组织的访问权限。</span><span class="sxs-lookup"><span data-stu-id="f7124-118">You use [Microsoft Intune](/mem/intune/fundamentals/planning-guide) to manage access to your organization using MDM or MAM.</span></span> <span data-ttu-id="f7124-119">MDM 是用户在 Intune 中"注册"其设备时。</span><span class="sxs-lookup"><span data-stu-id="f7124-119">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="f7124-120">注册设备后，该设备即为托管设备，可接收组织的策略、规则和设置。</span><span class="sxs-lookup"><span data-stu-id="f7124-120">After a device is enrolled, it is a managed device and can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="f7124-121">例如，你可以安装特定应用、创建密码策略、安装 VPN 连接等。</span><span class="sxs-lookup"><span data-stu-id="f7124-121">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="f7124-122">具有其自己的个人设备的用户可能不希望注册其设备或由 Intune 和组织的策略进行管理。</span><span class="sxs-lookup"><span data-stu-id="f7124-122">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="f7124-123">但仍需要保护组织的资源和数据。</span><span class="sxs-lookup"><span data-stu-id="f7124-123">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="f7124-124">在此方案中，可以使用 MAM 保护应用。</span><span class="sxs-lookup"><span data-stu-id="f7124-124">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="f7124-125">例如，可以使用 MAM 策略，该策略要求用户在访问设备上SharePoint PIN。</span><span class="sxs-lookup"><span data-stu-id="f7124-125">For example, you can use an MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="f7124-126">你还将确定如何管理个人设备和组织拥有的设备。</span><span class="sxs-lookup"><span data-stu-id="f7124-126">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="f7124-127">你可能希望以不同方式处理设备，具体取决于设备的用途。</span><span class="sxs-lookup"><span data-stu-id="f7124-127">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="f7124-128">标识和设备访问配置</span><span class="sxs-lookup"><span data-stu-id="f7124-128">Identity and device access configurations</span></span>

<span data-ttu-id="f7124-129">Microsoft 提供了一组用于标识 [和设备访问的配置](../security/defender-365-security/microsoft-365-policies-configurations.md) ，以确保员工安全高效。</span><span class="sxs-lookup"><span data-stu-id="f7124-129">Microsoft provides a set of configurations for [identity and device access](../security/defender-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="f7124-130">这些配置包括使用：</span><span class="sxs-lookup"><span data-stu-id="f7124-130">These configurations include the use of:</span></span>

- <span data-ttu-id="f7124-131">Azure AD 条件访问策略</span><span class="sxs-lookup"><span data-stu-id="f7124-131">Azure AD Conditional Access policies</span></span>
- <span data-ttu-id="f7124-132">Microsoft Intune设备合规性应用保护策略</span><span class="sxs-lookup"><span data-stu-id="f7124-132">Microsoft Intune device compliance and app protection policies</span></span>
- <span data-ttu-id="f7124-133">Azure AD Identity Protection 用户风险策略</span><span class="sxs-lookup"><span data-stu-id="f7124-133">Azure AD Identity Protection user risk policies</span></span>
- <span data-ttu-id="f7124-134">云应用的其他策略</span><span class="sxs-lookup"><span data-stu-id="f7124-134">Additional policies of cloud apps</span></span>

<span data-ttu-id="f7124-135">下面是应用这些设置和策略以验证和限制用户及其设备，以及用户对本地和云生产力应用（如 Microsoft Teams）的使用的示例。</span><span class="sxs-lookup"><span data-stu-id="f7124-135">Here is an example of the application of these settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![针对用户、设备及其应用使用的要求和限制的标识和设备访问配置](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

<span data-ttu-id="f7124-137">对于设备访问和应用管理，请使用以下文章中的配置：</span><span class="sxs-lookup"><span data-stu-id="f7124-137">For device access and app management, use the configurations in these articles:</span></span>

- [<span data-ttu-id="f7124-138">先决条件</span><span class="sxs-lookup"><span data-stu-id="f7124-138">Prerequisites</span></span>](../security/defender-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="f7124-139">常见标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="f7124-139">Common identity and device access policies</span></span>](../security/defender-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a><span data-ttu-id="f7124-140">步骤 5 的结果</span><span class="sxs-lookup"><span data-stu-id="f7124-140">Results of Step 5</span></span>

<span data-ttu-id="f7124-141">对于 Microsoft 365 租户的设备和应用管理，你已确定 Intune 设置和策略，以验证和限制用户、其设备以及本地和云生产力应用的使用。</span><span class="sxs-lookup"><span data-stu-id="f7124-141">For device and app management for your Microsoft 365 tenant, you have determined the Intune settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps.</span></span>

<span data-ttu-id="f7124-142">下面是一个租户示例，其中突出显示了新元素的 Intune 设备和应用管理。</span><span class="sxs-lookup"><span data-stu-id="f7124-142">Here is an example of a tenant with Intune device and app management with the new elements highlighted.</span></span>

![使用 Intune 设备和应用管理的租户示例](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

<span data-ttu-id="f7124-144">在此图中，租户具有：</span><span class="sxs-lookup"><span data-stu-id="f7124-144">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="f7124-145">在 Intune 中注册的组织拥有的设备。</span><span class="sxs-lookup"><span data-stu-id="f7124-145">Organization-owned devices enrolled in Intune.</span></span>
- <span data-ttu-id="f7124-146">适用于已注册和个人设备的 Intune 设备和应用策略。</span><span class="sxs-lookup"><span data-stu-id="f7124-146">Intune device and app policies for enrolled and personal devices.</span></span>

## <a name="ongoing-maintenance-for-device-and-app-management"></a><span data-ttu-id="f7124-147">持续维护设备和应用管理</span><span class="sxs-lookup"><span data-stu-id="f7124-147">Ongoing maintenance for device and app management</span></span>

<span data-ttu-id="f7124-148">您可能需要持续：</span><span class="sxs-lookup"><span data-stu-id="f7124-148">On an ongoing basis, you might need to:</span></span> 

- <span data-ttu-id="f7124-149">管理设备注册。</span><span class="sxs-lookup"><span data-stu-id="f7124-149">Manage device enrollment.</span></span>
- <span data-ttu-id="f7124-150">针对其他应用、设备和安全要求修改设置和策略。</span><span class="sxs-lookup"><span data-stu-id="f7124-150">Revise your settings and policies for additional apps, devices, and security requirements.</span></span>