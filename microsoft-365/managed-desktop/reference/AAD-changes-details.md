---
title: Azure Active Directory 租户详细信息
description: 本主题介绍在注册 Microsoft 托管桌面时对 AAD 帐户所做的更改。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 6b2b30d8dedba1086bfa9268fb0fdbce20367c20
ms.sourcegitcommit: dd426c686b52cf79325f11022b2d99bc45285577
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643943"
---
# <a name="azure-active-directory-tenant-details"></a><span data-ttu-id="e0ec9-104">Azure Active Directory 租户详细信息</span><span class="sxs-lookup"><span data-stu-id="e0ec9-104">Azure Active Directory tenant details</span></span>
<span data-ttu-id="e0ec9-105">{gory 帐户、API 调用、权限等的详细信息, 等等。</span><span class="sxs-lookup"><span data-stu-id="e0ec9-105">{gory details about accounts, API calls, perms, etc., etc.}</span></span>


## <a name="data-transmitted-to-and-from-your-aad-account"></a><span data-ttu-id="e0ec9-106">向 AAD 帐户传输数据的数据</span><span class="sxs-lookup"><span data-stu-id="e0ec9-106">Data transmitted to and from your AAD account</span></span>


<span data-ttu-id="e0ec9-107">向你的帐户发送的来自 Microsoft 的数据:</span><span class="sxs-lookup"><span data-stu-id="e0ec9-107">Data sent to your account from Microsoft:</span></span>

- <span data-ttu-id="e0ec9-108">组名称</span><span class="sxs-lookup"><span data-stu-id="e0ec9-108">Group names</span></span>
- <span data-ttu-id="e0ec9-109">安全策略配置</span><span class="sxs-lookup"><span data-stu-id="e0ec9-109">Security policy configuration</span></span>
- <span data-ttu-id="e0ec9-110">设备订单</span><span class="sxs-lookup"><span data-stu-id="e0ec9-110">Device orders</span></span>
- <span data-ttu-id="e0ec9-111">用户帐户 (msadmin、mstest、mwaas_soc_ro、mwaas_wdgsoc)</span><span class="sxs-lookup"><span data-stu-id="e0ec9-111">User accounts (msadmin, mstest, mwaas_soc_ro, mwaas_wdgsoc)</span></span>
- <span data-ttu-id="e0ec9-112">将 E5 许可证分配给用户帐户</span><span class="sxs-lookup"><span data-stu-id="e0ec9-112">E5 License assignment to the user accounts</span></span>
- <span data-ttu-id="e0ec9-113">更新响铃的 Windows 更新策略</span><span class="sxs-lookup"><span data-stu-id="e0ec9-113">Windows update policies for update rings</span></span>

<span data-ttu-id="e0ec9-114">从你的帐户发送到 Microsoft 的数据:</span><span class="sxs-lookup"><span data-stu-id="e0ec9-114">Data sent to Microsoft from your account:</span></span>

- <span data-ttu-id="e0ec9-115">设备更新、使用率和可靠性数据</span><span class="sxs-lookup"><span data-stu-id="e0ec9-115">Device update, usage and reliability data</span></span>
- <span data-ttu-id="e0ec9-116">应用程序部署和可靠性数据</span><span class="sxs-lookup"><span data-stu-id="e0ec9-116">App deployment and reliability data</span></span>
- <span data-ttu-id="e0ec9-117">更新和安全策略部署数据</span><span class="sxs-lookup"><span data-stu-id="e0ec9-117">Update and security policy deployment data</span></span>
- <span data-ttu-id="e0ec9-118">分配到设备的用户</span><span class="sxs-lookup"><span data-stu-id="e0ec9-118">Users assigned to devices</span></span>  

<span data-ttu-id="e0ec9-119">从你的帐户传输的数据存储在 Microsoft 租户 (美国托管的 Microsoft 租户) 中的 Azure SQL 数据库中。</span><span class="sxs-lookup"><span data-stu-id="e0ec9-119">Data transmitted from your account is stored in Azure SQL databases in the Microsoft tenant hosted in the USA.</span></span> <span data-ttu-id="e0ec9-120">根据 {Microsoft Azure security} 中所述的策略存储和处理数据。</span><span class="sxs-lookup"><span data-stu-id="e0ec9-120">Data is stored and handled in accordance the policies described in {Microsoft Azure security}.</span></span> 

## <a name="api-permissions-and-calls"></a><span data-ttu-id="e0ec9-121">API 权限和调用</span><span class="sxs-lookup"><span data-stu-id="e0ec9-121">API permissions and calls</span></span>

<span data-ttu-id="e0ec9-122">**注册期间:**</span><span class="sxs-lookup"><span data-stu-id="e0ec9-122">**During enrollment:**</span></span>

<span data-ttu-id="e0ec9-123">API 权限:</span><span class="sxs-lookup"><span data-stu-id="e0ec9-123">API permissions:</span></span>
- <span data-ttu-id="e0ec9-124">DeviceManagementServiceConfig.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e0ec9-124">DeviceManagementServiceConfig.ReadWrite.All</span></span>
- <span data-ttu-id="e0ec9-125">Directory.AccessAsUser.All</span><span class="sxs-lookup"><span data-stu-id="e0ec9-125">Directory.AccessAsUser.All</span></span>
- <span data-ttu-id="e0ec9-126">User.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e0ec9-126">User.ReadWrite.All</span></span>
- <span data-ttu-id="e0ec9-127">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e0ec9-127">DeviceManagementConfiguration.ReadWrite.All</span></span>
- <span data-ttu-id="e0ec9-128">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e0ec9-128">DeviceManagementManagedDevices.ReadWrite.All</span></span>
- <span data-ttu-id="e0ec9-129">Group.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e0ec9-129">Group.ReadWrite.All</span></span>

<span data-ttu-id="e0ec9-130">API 调用:</span><span class="sxs-lookup"><span data-stu-id="e0ec9-130">API calls:</span></span>
- <span data-ttu-id="e0ec9-131">POST/organization/{organizationId}/setMobileDeviceManagementAuthority</span><span class="sxs-lookup"><span data-stu-id="e0ec9-131">POST /organization/{organizationId}/setMobileDeviceManagementAuthority</span></span>
- <span data-ttu-id="e0ec9-132">GET/POST/directoryRoles/{id}/members</span><span class="sxs-lookup"><span data-stu-id="e0ec9-132">GET/POST /directoryRoles/{id}/members</span></span>
- <span data-ttu-id="e0ec9-133">GET/POST/users</span><span class="sxs-lookup"><span data-stu-id="e0ec9-133">GET/POST /users</span></span>
- <span data-ttu-id="e0ec9-134">GET/POST/groups</span><span class="sxs-lookup"><span data-stu-id="e0ec9-134">GET/POST /groups</span></span>
- <span data-ttu-id="e0ec9-135">修补程序/groups/{id}</span><span class="sxs-lookup"><span data-stu-id="e0ec9-135">PATCH /groups/{id}</span></span>
- <span data-ttu-id="e0ec9-136">GET/POST/deviceManagement/deviceConfigurations</span><span class="sxs-lookup"><span data-stu-id="e0ec9-136">GET/POST /deviceManagement/deviceConfigurations</span></span>
- <span data-ttu-id="e0ec9-137">获取/deviceManagement/detectedApps</span><span class="sxs-lookup"><span data-stu-id="e0ec9-137">GET /deviceManagement/detectedApps</span></span>

<span data-ttu-id="e0ec9-138">**注册后, 在常规管理过程中:**</span><span class="sxs-lookup"><span data-stu-id="e0ec9-138">**After enrollment, during ordinary management:**</span></span>

<span data-ttu-id="e0ec9-139">API 权限:</span><span class="sxs-lookup"><span data-stu-id="e0ec9-139">API permissions:</span></span>
- <span data-ttu-id="e0ec9-140">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e0ec9-140">DeviceManagementManagedDevices.ReadWrite.All</span></span>
- <span data-ttu-id="e0ec9-141">DeviceManagementApps.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e0ec9-141">DeviceManagementApps.ReadWrite.All</span></span>
- <span data-ttu-id="e0ec9-142">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e0ec9-142">DeviceManagementConfiguration.ReadWrite.All</span></span>
- <span data-ttu-id="e0ec9-143">Reports.Read.All</span><span class="sxs-lookup"><span data-stu-id="e0ec9-143">Reports.Read.All</span></span>
- <span data-ttu-id="e0ec9-144">User.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e0ec9-144">User.ReadWrite.All</span></span>
- <span data-ttu-id="e0ec9-145">Group.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e0ec9-145">Group.ReadWrite.All</span></span>
- <span data-ttu-id="e0ec9-146">Directory.AccessAsUser.All</span><span class="sxs-lookup"><span data-stu-id="e0ec9-146">Directory.AccessAsUser.All</span></span>

<span data-ttu-id="e0ec9-147">API 调用:</span><span class="sxs-lookup"><span data-stu-id="e0ec9-147">API calls:</span></span>
- <span data-ttu-id="e0ec9-148">GET/POST/directoryRoles/{id}/members</span><span class="sxs-lookup"><span data-stu-id="e0ec9-148">GET/POST /directoryRoles/{id}/members</span></span>
- <span data-ttu-id="e0ec9-149">GET/PATCH/POST/users</span><span class="sxs-lookup"><span data-stu-id="e0ec9-149">GET/PATCH/POST /users</span></span>
- <span data-ttu-id="e0ec9-150">GET/POST/groups</span><span class="sxs-lookup"><span data-stu-id="e0ec9-150">GET/POST /groups</span></span>
- <span data-ttu-id="e0ec9-151">修补程序/groups/{id}</span><span class="sxs-lookup"><span data-stu-id="e0ec9-151">PATCH /groups/{id}</span></span>
- <span data-ttu-id="e0ec9-152">GET/POST/deviceManagement/deviceConfigurations</span><span class="sxs-lookup"><span data-stu-id="e0ec9-152">GET/POST /deviceManagement/deviceConfigurations</span></span>
- <span data-ttu-id="e0ec9-153">GET/POST/deviceAppManagement/mobileApps</span><span class="sxs-lookup"><span data-stu-id="e0ec9-153">GET/POST /deviceAppManagement/mobileApps</span></span>
- <span data-ttu-id="e0ec9-154">获取/deviceManagement/detectedApps</span><span class="sxs-lookup"><span data-stu-id="e0ec9-154">GET /deviceManagement/detectedApps</span></span>
- <span data-ttu-id="e0ec9-155">获取/devices</span><span class="sxs-lookup"><span data-stu-id="e0ec9-155">GET /devices</span></span>
- <span data-ttu-id="e0ec9-156">POST/users/{id | userPrincipalName}/assignLicense</span><span class="sxs-lookup"><span data-stu-id="e0ec9-156">POST /users/{id | userPrincipalName}/assignLicense</span></span>
- <span data-ttu-id="e0ec9-157">获取/subscribedSkus</span><span class="sxs-lookup"><span data-stu-id="e0ec9-157">GET /subscribedSkus</span></span>

## <a name="accounts-used-by-microsoft-managed-desktop"></a><span data-ttu-id="e0ec9-158">Microsoft 托管桌面使用的帐户</span><span class="sxs-lookup"><span data-stu-id="e0ec9-158">Accounts used by Microsoft Managed Desktop</span></span>





| <span data-ttu-id="e0ec9-159">帐户</span><span class="sxs-lookup"><span data-stu-id="e0ec9-159">Account</span></span> | <span data-ttu-id="e0ec9-160">说明</span><span class="sxs-lookup"><span data-stu-id="e0ec9-160">Description</span></span>  | <span data-ttu-id="e0ec9-161">条件访问</span><span class="sxs-lookup"><span data-stu-id="e0ec9-161">Conditional access</span></span>  | <span data-ttu-id="e0ec9-162">多重身份验证</span><span class="sxs-lookup"><span data-stu-id="e0ec9-162">Multi-factor authentication</span></span>  | <span data-ttu-id="e0ec9-163">为什么这一点很正常</span><span class="sxs-lookup"><span data-stu-id="e0ec9-163">Why this is OK</span></span> |
|---------|---------|---------|---------|--------------|
| <span data-ttu-id="e0ec9-164">msadmin @ \* onmmicrosoft</span><span class="sxs-lookup"><span data-stu-id="e0ec9-164">msadmin@\*onmmicrosoft.com</span></span> | <span data-ttu-id="e0ec9-165">具有管理员权限的有限服务帐户, 用作 Microsoft Intune 和用户管理员 {这是什么？</span><span class="sxs-lookup"><span data-stu-id="e0ec9-165">Limited service account with administrator privileges, used as a Microsoft Intune and User administrator {what's this?}</span></span> <span data-ttu-id="e0ec9-166">为 Microsoft 新式桌面设备定义和配置租户。</span><span class="sxs-lookup"><span data-stu-id="e0ec9-166">to define and configure the tenant for Microsoft Modern Desktop devices.</span></span><span data-ttu-id="e0ec9-167">没有交互式登录权限;仅通过服务执行操作。</span><span class="sxs-lookup"><span data-stu-id="e0ec9-167">  Does not have interactive login permissions; performs operations only through the service.</span></span>  | <span data-ttu-id="e0ec9-168">排除, 因为它不是源自您的网络</span><span class="sxs-lookup"><span data-stu-id="e0ec9-168">Excluded, because it doesn't originate in your network</span></span>        | <span data-ttu-id="e0ec9-169">由于没有交互式登录而被排除</span><span class="sxs-lookup"><span data-stu-id="e0ec9-169">Excluded because there is no interactive logon</span></span>        | <span data-ttu-id="e0ec9-170">存储在 Azure Key Vault 中的密码</span><span class="sxs-lookup"><span data-stu-id="e0ec9-170">Password stored in Azure Key Vault</span></span> |
| <span data-ttu-id="e0ec9-171">mstest @ \* onmmicrosoft</span><span class="sxs-lookup"><span data-stu-id="e0ec9-171">mstest@\*onmmicrosoft.com</span></span>     |         |         |         |
| <span data-ttu-id="e0ec9-172">mssupport @ \* onmmicrosoft</span><span class="sxs-lookup"><span data-stu-id="e0ec9-172">mssupport@\*onmmicrosoft.com</span></span>     |         |         |         |
| <span data-ttu-id="e0ec9-173">msadminint @ \* onmmicrosoft</span><span class="sxs-lookup"><span data-stu-id="e0ec9-173">msadminint@\*onmmicrosoft.com</span></span>     |         |         |         |
