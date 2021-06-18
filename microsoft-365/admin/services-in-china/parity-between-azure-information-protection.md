---
title: 适用于由世纪互联运营的 Office 365 的 Azure 信息保护支持
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: 深入了解适用于由世纪互联运营的 Office 365 的 Azure 信息保护 （AIP） 以及如何为中国客户进行配置。
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535838"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="85350-103">适用于由世纪互联运营的 Office 365 的 Azure 信息保护支持</span><span class="sxs-lookup"><span data-stu-id="85350-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="85350-104">本文介绍了 Azure 信息保护 （AIP） 对由世纪互联运营的 Office 365 和商业产品/服务之间的差异，以及为中国&mdash;客户配置 AIP 的详细说明，包括如何安装 AIP 本地扫描仪和管理内容扫描作业。</span><span class="sxs-lookup"><span data-stu-id="85350-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="85350-105">由世纪互联运营的 Office 365 的 AIP 与商业产品之间的差异</span><span class="sxs-lookup"><span data-stu-id="85350-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="85350-106">我们的目标是通过针对由世纪互联运营的 Office 365 的 AIP 产品，为中国客户提供所有商业特性和功能，但是我们要强调的一些缺失功能。</span><span class="sxs-lookup"><span data-stu-id="85350-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="85350-107">以下列表包含世纪互联运营的 Office 365 的 AIP 与 2021 年 1 月前的商业产品之间的现有缺陷：</span><span class="sxs-lookup"><span data-stu-id="85350-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="85350-108">仅 Microsoft 365 企业版应用（内部版本 11731.10000 或更高版本）支持信息权限管理 （IRM）。</span><span class="sxs-lookup"><span data-stu-id="85350-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="85350-109">不支持 Office 2010、Office 2013 和其他 Office 2016 版本。</span><span class="sxs-lookup"><span data-stu-id="85350-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="85350-110">目前无法从 Active Directory 权限管理服务 （AD RMS） 迁移到 AIP。</span><span class="sxs-lookup"><span data-stu-id="85350-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="85350-111">支持在商业云中与用户共享受保护的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="85350-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="85350-112">目前，不可在商业云中与用户共享文档和电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="85350-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="85350-113">这包括商业云中由世纪互联络用户运营的 Office 365、在商业云中由世纪互联用户运营的非 Office 365 用户，以及拥有个人版 RMS 许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="85350-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="85350-114">具有 SharePoint（受 IRM 保护的网站和库）的 IRM 当前不可用。</span><span class="sxs-lookup"><span data-stu-id="85350-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="85350-115">AD RMS 的移动设备扩展当前不可用。</span><span class="sxs-lookup"><span data-stu-id="85350-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="85350-116">Azure 中国世纪互联不支持该[手机阅读器](/azure/information-protection/rms-client/mobile-app-faq)。</span><span class="sxs-lookup"><span data-stu-id="85350-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="85350-117">Azure 门户的 AIP 区域不可用于中国客户。</span><span class="sxs-lookup"><span data-stu-id="85350-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="85350-118">使用 [PowerShell 命令](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)而不是在门户中执行操作，例如管理和运行内容扫描作业。</span><span class="sxs-lookup"><span data-stu-id="85350-118">Use [PowerShell commands](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as managing and running your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="85350-119">为中国的客户配置 AIP</span><span class="sxs-lookup"><span data-stu-id="85350-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="85350-120">为中国的客户配置 AIP：</span><span class="sxs-lookup"><span data-stu-id="85350-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="85350-121">[为租户启用权限](#step-1-enable-rights-management-for-the-tenant)。</span><span class="sxs-lookup"><span data-stu-id="85350-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

1. <span data-ttu-id="85350-122">[添加“Microsoft 信息保护同步服务”服务主体](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)。</span><span class="sxs-lookup"><span data-stu-id="85350-122">[Add the Microsoft Information Protection Sync Service service principal](#step-2-add-the-microsoft-information-protection-sync-service-service-principal).</span></span>

1. <span data-ttu-id="85350-123">[配置 DNS 加密](#step-3-configure-dns-encryption)。</span><span class="sxs-lookup"><span data-stu-id="85350-123">[Configure DNS encryption](#step-3-configure-dns-encryption).</span></span>

1. <span data-ttu-id="85350-124">[安装和配置 AIP 统一标签客户端](#step-4-install-and-configure-the-aip-unified-labeling-client)。</span><span class="sxs-lookup"><span data-stu-id="85350-124">[Install and configure the AIP unified labeling client](#step-4-install-and-configure-the-aip-unified-labeling-client).</span></span>

1. <span data-ttu-id="85350-125">[在 Windows 桌面应用中配置 AIP](#step-5-configure-aip-apps-on-windows)。</span><span class="sxs-lookup"><span data-stu-id="85350-125">[Configure AIP apps on Windows](#step-5-configure-aip-apps-on-windows).</span></span>

1. <span data-ttu-id="85350-126">[安装 AIP 本地扫描仪和管理内容扫描作业](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。</span><span class="sxs-lookup"><span data-stu-id="85350-126">[Install the AIP on-premises scanner and manage content scan jobs](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="85350-127">步骤 1：为租户启用权限管理</span><span class="sxs-lookup"><span data-stu-id="85350-127">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="85350-128">若要使加密能正常工作，必须为租户启用 RMS。</span><span class="sxs-lookup"><span data-stu-id="85350-128">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="85350-129">检查是否已启用 RMS：</span><span class="sxs-lookup"><span data-stu-id="85350-129">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="85350-130">以管理员角色启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="85350-130">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="85350-131">如果未安装 AIPService 模块，请运行 `Install-Module AipService`。</span><span class="sxs-lookup"><span data-stu-id="85350-131">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="85350-132">使用 `Import-Module AipService`。</span><span class="sxs-lookup"><span data-stu-id="85350-132">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="85350-133">使用 `Connect-AipService -environmentname azurechinacloud`连接到服务。</span><span class="sxs-lookup"><span data-stu-id="85350-133">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="85350-134">运行 `(Get-AipServiceConfiguration).FunctionalState` ，检查状态是否 `Enabled`。</span><span class="sxs-lookup"><span data-stu-id="85350-134">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="85350-135">如果功能状态为 `Disabled`，请运行 `Enable-AipService`。</span><span class="sxs-lookup"><span data-stu-id="85350-135">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a><span data-ttu-id="85350-136">步骤 2：添加“Microsoft 信息保护同步服务”服务主体</span><span class="sxs-lookup"><span data-stu-id="85350-136">Step 2: Add the Microsoft Information Protection Sync Service service principal</span></span>

<span data-ttu-id="85350-137">默认情况下，“**Microsoft 信息保护同步服务**”服务主体在 Azure 中国租户中不可用，而 Azure 信息保护需要该服务主体。</span><span class="sxs-lookup"><span data-stu-id="85350-137">The **Microsoft Information Protection Sync Service** service principal is not available in Azure China tenants by default, and is required for Azure Information Protection.</span></span>

1. <span data-ttu-id="85350-138">使用 [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) cmdlet 和 Microsoft 信息保护同步服务的 `870c4f2e-85b6-4d43-bdda-6ed9a579b725` 应用程序 ID 手动创建此服务主体。</span><span class="sxs-lookup"><span data-stu-id="85350-138">Create this service principal manually using the [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) cmdlet and the `870c4f2e-85b6-4d43-bdda-6ed9a579b725` application ID for the Microsoft Information Protection Sync Service.</span></span> 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. <span data-ttu-id="85350-139">添加服务主体后，请添加服务所需的相关权限。</span><span class="sxs-lookup"><span data-stu-id="85350-139">After adding the service principal, add the relevant permissions required to the service.</span></span>

### <a name="step-3-configure-dns-encryption"></a><span data-ttu-id="85350-140">步骤 3：配置 DNS 加密</span><span class="sxs-lookup"><span data-stu-id="85350-140">Step 3: Configure DNS encryption</span></span>

<span data-ttu-id="85350-141">为使加密能正常工作，Office 客户端应用程序必须连接到服务的中国实例并请从其中启动。</span><span class="sxs-lookup"><span data-stu-id="85350-141">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="85350-142">若要将客户端应用程序重定向到正确的服务实例，租户管理员必须配置包含 Azure RMS URL 相关信息的 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="85350-142">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="85350-143">如果没有 DNS SRV 记录，客户端应用程序将默认尝试连接到公共云实例，且将失败。</span><span class="sxs-lookup"><span data-stu-id="85350-143">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="85350-144">此外，假设用户将会使用基于租户拥有的域（例如 `joe@contoso.cn`）而不是 `onmschina` 用户名（例如 `joe@contoso.onmschina.cn`）登录。</span><span class="sxs-lookup"><span data-stu-id="85350-144">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="85350-145">用户名中的域名用于 DNS 重定向到正确的服务实例。</span><span class="sxs-lookup"><span data-stu-id="85350-145">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="85350-146">配置 DNS 加密 - Windows</span><span class="sxs-lookup"><span data-stu-id="85350-146">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="85350-147">获取 RMS ID：</span><span class="sxs-lookup"><span data-stu-id="85350-147">Get the RMS ID:</span></span>

    1. <span data-ttu-id="85350-148">以管理员角色启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="85350-148">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="85350-149">如果未安装 AIPService 模块，请运行 `Install-Module AipService`。</span><span class="sxs-lookup"><span data-stu-id="85350-149">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="85350-150">使用 `Connect-AipService -environmentname azurechinacloud`连接到服务。</span><span class="sxs-lookup"><span data-stu-id="85350-150">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="85350-151">运行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 获得 RMS ID。</span><span class="sxs-lookup"><span data-stu-id="85350-151">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="85350-152">登录到您的 DNS 提供商，导航到域的 DNS 设置，然后添加新的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="85350-152">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="85350-153">服务 = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="85350-153">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="85350-154">协议 = `_http`</span><span class="sxs-lookup"><span data-stu-id="85350-154">Protocol = `_http`</span></span>
    - <span data-ttu-id="85350-155">名称 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="85350-155">Name = `_tcp`</span></span>
    - <span data-ttu-id="85350-156">目标 = `[GUID].rms.aadrm.cn`（其中 GUID 为 RMS ID）</span><span class="sxs-lookup"><span data-stu-id="85350-156">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="85350-157">优先级、权重、秒数、TTL = 默认值</span><span class="sxs-lookup"><span data-stu-id="85350-157">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="85350-158">将自定义域与 [门户中的租户](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)。</span><span class="sxs-lookup"><span data-stu-id="85350-158">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="85350-159">这将在 DNS 中添加条目，这可能需要几分钟时间才能在向 DNS 设置添加该值后进行验证。</span><span class="sxs-lookup"><span data-stu-id="85350-159">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="85350-160">使用相应的全局管理员凭据登录 Microsoft 365 管理中心，并添加域（例如， `contoso.cn`）供用户创建。</span><span class="sxs-lookup"><span data-stu-id="85350-160">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="85350-161">在验证过程中，可能需要其他 DNS 更改。</span><span class="sxs-lookup"><span data-stu-id="85350-161">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="85350-162">验证完成后，可创建用户。</span><span class="sxs-lookup"><span data-stu-id="85350-162">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="85350-163">配置 DNS 加密 - Mac、iOS、Android</span><span class="sxs-lookup"><span data-stu-id="85350-163">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="85350-164">登录到您的 DNS 提供商，导航到域的 DNS 设置，然后添加新的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="85350-164">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="85350-165">服务 = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="85350-165">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="85350-166">协议 = `_http`</span><span class="sxs-lookup"><span data-stu-id="85350-166">Protocol = `_http`</span></span>
- <span data-ttu-id="85350-167">名称 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="85350-167">Name = `_tcp`</span></span>
- <span data-ttu-id="85350-168">目标 = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="85350-168">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="85350-169">端口 = `80`</span><span class="sxs-lookup"><span data-stu-id="85350-169">Port = `80`</span></span>
- <span data-ttu-id="85350-170">优先级、权重、秒数、TTL = 默认值</span><span class="sxs-lookup"><span data-stu-id="85350-170">Priority, Weight, Seconds, TTL = default values</span></span>


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="85350-171">步骤 4：安装和配置 AIP 统一标记客户端</span><span class="sxs-lookup"><span data-stu-id="85350-171">Step 4: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="85350-172">从 [Microsoft 下载中心](https://www.microsoft.com/download/details.aspx?id=53018)下载并安装 AIP 统一标记客户端。</span><span class="sxs-lookup"><span data-stu-id="85350-172">Download and install the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="85350-173">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="85350-173">For more information, see:</span></span>

- [<span data-ttu-id="85350-174">AIP 文档</span><span class="sxs-lookup"><span data-stu-id="85350-174">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="85350-175">AIP 版本历史记录和支持策略</span><span class="sxs-lookup"><span data-stu-id="85350-175">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="85350-176">AIP 系统要求</span><span class="sxs-lookup"><span data-stu-id="85350-176">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="85350-177">AIP 快速入门：部署 AIP 客户端</span><span class="sxs-lookup"><span data-stu-id="85350-177">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="85350-178">AIP 管理员指南</span><span class="sxs-lookup"><span data-stu-id="85350-178">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="85350-179">AIP 用户指南</span><span class="sxs-lookup"><span data-stu-id="85350-179">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="85350-180">了解 Microsoft 365 敏感度标签</span><span class="sxs-lookup"><span data-stu-id="85350-180">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a><span data-ttu-id="85350-181">步骤 5：在 Windows 上配置 AIP 应用</span><span class="sxs-lookup"><span data-stu-id="85350-181">Step 5: Configure AIP apps on Windows</span></span>

<span data-ttu-id="85350-182">Windows 上的 AIP 应用需要以下注册表项，用于指向 Azure China 的正确主权云：</span><span class="sxs-lookup"><span data-stu-id="85350-182">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="85350-183">注册表节点 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="85350-183">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="85350-184">名称 = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="85350-184">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="85350-185">值 = `6`（默认 = 0）</span><span class="sxs-lookup"><span data-stu-id="85350-185">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="85350-186">类型 = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="85350-186">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85350-187">请确保卸载后不会删除注册表项。</span><span class="sxs-lookup"><span data-stu-id="85350-187">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="85350-188">如果密钥为空、不正确或不存在，则功能将按默认值（商业云的默认值 = 0）运行。</span><span class="sxs-lookup"><span data-stu-id="85350-188">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="85350-189">如果密钥为空或不正确，也会向日志添加打印错误。</span><span class="sxs-lookup"><span data-stu-id="85350-189">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="85350-190">步骤 6：安装 AIP 本地扫描程序和管理内容扫描作业</span><span class="sxs-lookup"><span data-stu-id="85350-190">Step 6: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="85350-191">安装 AIP 本地扫描仪扫描网络和内容共享以访问敏感数据，并按组织策略中配置应用分类和保护标签。</span><span class="sxs-lookup"><span data-stu-id="85350-191">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="85350-192">在配置和管理内容扫描作业时，请使用以下过程而不是商业产品/服务使用的 [Azure 门户界面](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only)。</span><span class="sxs-lookup"><span data-stu-id="85350-192">When configuring and managing your content scan jobs, use the following procedure instead of the [Azure portal interface](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) that's used by the commercial offerings.</span></span>

<span data-ttu-id="85350-193">有关详细信息，请参阅[什么是 Azure 信息保护统一标签扫描程序？](/azure/information-protection/deploy-aip-scanner)和[使仅用 PowerShell 管理内容扫描作业](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。</span><span class="sxs-lookup"><span data-stu-id="85350-193">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>

<span data-ttu-id="85350-194">**若要安装和配置扫描程序，请执行以下操作**：</span><span class="sxs-lookup"><span data-stu-id="85350-194">**To install and configure your scanner**:</span></span>

1. <span data-ttu-id="85350-195">登录到将运行扫描程序的 Windows Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="85350-195">Sign in to the Windows Server computer that will run the scanner.</span></span> <span data-ttu-id="85350-196">使用具有本地管理员权限并有权写入 SQL Server 主数据库的帐户。</span><span class="sxs-lookup"><span data-stu-id="85350-196">Use an account that has local administrator rights and that has permissions to write to the SQL Server master database.</span></span>

1. <span data-ttu-id="85350-197">在关闭 PowerShell 的情况下开始。</span><span class="sxs-lookup"><span data-stu-id="85350-197">Start with PowerShell closed.</span></span> <span data-ttu-id="85350-198">如果之前已安装 AIP 客户端和扫描程序，请确保已停止 **AIPScanner** 服务。</span><span class="sxs-lookup"><span data-stu-id="85350-198">If you've previously installed the AIP client and scanner, make sure that the **AIPScanner** service is stopped.</span></span>

1. <span data-ttu-id="85350-199">使用“**以管理员身份运行**”选项打开 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="85350-199">Open a Windows PowerShell session with the **Run as an administrator** option.</span></span>

1. <span data-ttu-id="85350-200">运行 [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) cmdlet，指定要在其上为 Azure 信息保护扫描程序创建数据库的 SQL Server 实例，并为扫描程序群集指定有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="85350-200">Run the [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) cmdlet, specifying your SQL Server instance on which to create a database for the Azure Information Protection scanner, and a meaningful name for your scanner cluster.</span></span>

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > <span data-ttu-id="85350-201">可以在 [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) 命令中使用相同的群集名称将多个扫描程序节点关联到同一群集。</span><span class="sxs-lookup"><span data-stu-id="85350-201">You can use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="85350-202">对多个扫描程序节点使用同一群集可以使多个扫描程序协同工作以执行扫描。</span><span class="sxs-lookup"><span data-stu-id="85350-202">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
    > 

1. <span data-ttu-id="85350-203">使用“**管理工具**” > “**服务**”验证现在是否安装了该服务。</span><span class="sxs-lookup"><span data-stu-id="85350-203">Verify that the service is now installed by using **Administrative Tools** > **Services**.</span></span>

    <span data-ttu-id="85350-204">安装的服务命名为 **Azure 信息保护扫描程序**，并配置为使用你创建的扫描程序服务帐户运行。</span><span class="sxs-lookup"><span data-stu-id="85350-204">The installed service is named **Azure Information Protection Scanner** and is configured to run by using the scanner service account that you created.</span></span>

1. <span data-ttu-id="85350-205">获取用于扫描程序的 Azure 令牌。</span><span class="sxs-lookup"><span data-stu-id="85350-205">Get an Azure token to use with your scanner.</span></span> <span data-ttu-id="85350-206">Azure AD 令牌允许扫描程序向 Azure 信息保护服务进行身份验证，从而使扫描程序能够以非交互方式运行。</span><span class="sxs-lookup"><span data-stu-id="85350-206">An Azure AD token allows the scanner to authenticate to the Azure Information Protection service, enabling the scanner to run non-interactively.</span></span> 

    1. <span data-ttu-id="85350-207">打开 Azure 门户并创建 Azure AD 应用程序，以指定用于身份验证的访问令牌。</span><span class="sxs-lookup"><span data-stu-id="85350-207">Open the Azure portal and create an Azure AD application to specify an access token for authentication.</span></span> <span data-ttu-id="85350-208">有关详细信息，请参阅[如何为 Azure 信息保护以非交互方式标记文件](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)。</span><span class="sxs-lookup"><span data-stu-id="85350-208">For more information, see [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>
    
        > [!TIP]
        > <span data-ttu-id="85350-209">为 [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) 命令创建和配置 Azure AD 应用程序时，"**请求 API 权限**"窗格显示 **我的组织使用的API** 选项卡，而不是 **Microsoft API** 选项卡。选择 **使用** 的 API，然后选择 **Azure Rights Management Services 中的**。</span><span class="sxs-lookup"><span data-stu-id="85350-209">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span> 
        >

    1. <span data-ttu-id="85350-210">在 Windows Server 计算机上，如果扫描程序服务帐户已被授予安装的“**在本机登录**”权限，请使用此帐户登录并启动 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="85350-210">From the Windows Server computer, if your scanner service account has been granted the **Log on locally** right for the installation, sign in with this account and start a PowerShell session.</span></span> 
    
        <span data-ttu-id="85350-211">如果扫描程序服务帐户无法获得安装的“**在本机登录**”权限，请配合使用 *OnBehalfOf* 参数和 [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)，如[如何为 Azure 信息保护以非交互方式标记文件](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)中所述。</span><span class="sxs-lookup"><span data-stu-id="85350-211">If your scanner service account cannot be granted the **Log on locally** right for the installation, use the *OnBehalfOf* parameter with [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), as described in [How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).</span></span>

    1. <span data-ttu-id="85350-212">运行 [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)，指定从 Azure AD 应用程序复制的值：</span><span class="sxs-lookup"><span data-stu-id="85350-212">Run [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), specifying values copied from your Azure AD application:</span></span>

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      <span data-ttu-id="85350-213">例如：</span><span class="sxs-lookup"><span data-stu-id="85350-213">For example:</span></span>

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    <span data-ttu-id="85350-214">扫描程序现在有一个令牌可对 Azure AD 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="85350-214">The scanner now has a token to authenticate to Azure AD.</span></span> <span data-ttu-id="85350-215">根据你在 Azure AD 中对 **Web 应用/API** 客户端密码的配置，此令牌的有效期为一年、两年或从不。</span><span class="sxs-lookup"><span data-stu-id="85350-215">This token is valid for one year, two years, or never, according to your configuration of the **Web app /API** client secret in Azure AD.</span></span> <span data-ttu-id="85350-216">当令牌过期时，你必须重复此过程。</span><span class="sxs-lookup"><span data-stu-id="85350-216">When the token expires, you must repeat this procedure.</span></span>

1. <span data-ttu-id="85350-217">运行 [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) cmdlet，将扫描程序设置为在脱机模式下运行。</span><span class="sxs-lookup"><span data-stu-id="85350-217">Run the [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) cmdlet to set the scanner to function in offline mode.</span></span> <span data-ttu-id="85350-218">运行：</span><span class="sxs-lookup"><span data-stu-id="85350-218">Run:</span></span>

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. <span data-ttu-id="85350-219">运行 [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet 以创建默认内容扫描作业。</span><span class="sxs-lookup"><span data-stu-id="85350-219">Run the [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet to create a default content scan job.</span></span>

    <span data-ttu-id="85350-220">**Set-AIPScannerContentScanJob** cmdlet 中唯一必需的参数是 **Enforce**。</span><span class="sxs-lookup"><span data-stu-id="85350-220">The only required parameter in the **Set-AIPScannerContentScanJob** cmdlet is **Enforce**.</span></span> <span data-ttu-id="85350-221">但是，此时你可能需要为内容扫描作业定义其他设置。</span><span class="sxs-lookup"><span data-stu-id="85350-221">However, you may want to define other settings for your content scan job at this time.</span></span> <span data-ttu-id="85350-222">例如：</span><span class="sxs-lookup"><span data-stu-id="85350-222">For example:</span></span>

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    <span data-ttu-id="85350-223">在你继续配置时，上述语法会配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="85350-223">The syntax above configures the following settings while you continue the configuration:</span></span>

    - <span data-ttu-id="85350-224">将扫描程序运行计划保持为“*手动*”</span><span class="sxs-lookup"><span data-stu-id="85350-224">Keeps the scanner run scheduling to *manual*</span></span>
    - <span data-ttu-id="85350-225">根据敏感度标记策略设置要发现的信息类型</span><span class="sxs-lookup"><span data-stu-id="85350-225">Sets the information types to be discovered based on the sensitivity labeling policy</span></span>
    - <span data-ttu-id="85350-226">*不* 强制实施敏感度标记策略</span><span class="sxs-lookup"><span data-stu-id="85350-226">Does *not* enforce a sensitivity labeling policy</span></span>
    - <span data-ttu-id="85350-227">使用为敏感度标记策略定义的默认标签，根据内容自动标记文件</span><span class="sxs-lookup"><span data-stu-id="85350-227">Automatically labels files based on content, using the default label defined for the sensitivity labeling policy</span></span>
    - <span data-ttu-id="85350-228">*不* 允许重新标记文件</span><span class="sxs-lookup"><span data-stu-id="85350-228">Does *not* allow for relabeling files</span></span>
    - <span data-ttu-id="85350-229">在扫描和自动标记时保留文件详细信息，包括 *修改日期*、*上次修改时间* 和 *修改者* 值</span><span class="sxs-lookup"><span data-stu-id="85350-229">Preserves file details while scanning and auto-labeling, including *date modified*, *last modified*, and *modified by* values</span></span>
    - <span data-ttu-id="85350-230">将扫描程序设置为在运行时排除 .msg 和 .tmp 文件</span><span class="sxs-lookup"><span data-stu-id="85350-230">Sets the scanner to exclude .msg and .tmp files when running</span></span>
    - <span data-ttu-id="85350-231">将默认所有者设置为在运行扫描程序时要使用的帐户</span><span class="sxs-lookup"><span data-stu-id="85350-231">Sets the default owner to the account you want to use when running the scanner</span></span>

1. <span data-ttu-id="85350-232">使用 [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) cmdlet 定义要在内容扫描作业中扫描的存储库。</span><span class="sxs-lookup"><span data-stu-id="85350-232">Use the [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) cmdlet to define the repositories you want to scan in your content scan job.</span></span> <span data-ttu-id="85350-233">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="85350-233">For example, run:</span></span>

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    <span data-ttu-id="85350-234">根据所添加的存储库类型使用以下语法之一：</span><span class="sxs-lookup"><span data-stu-id="85350-234">Use one of the following syntaxes, depending on the type of repository you're adding:</span></span>

    - <span data-ttu-id="85350-235">对于网络共享，请使用 `\\Server\Folder`。</span><span class="sxs-lookup"><span data-stu-id="85350-235">For a network share, use `\\Server\Folder`.</span></span>
    - <span data-ttu-id="85350-236">对于 SharePoint 库，请使用 `http://sharepoint.contoso.com/Shared%20Documents/Folder`。</span><span class="sxs-lookup"><span data-stu-id="85350-236">For a SharePoint library, use `http://sharepoint.contoso.com/Shared%20Documents/Folder`.</span></span>
    - <span data-ttu-id="85350-237">对于本地路径：`C:\Folder`</span><span class="sxs-lookup"><span data-stu-id="85350-237">For a local path: `C:\Folder`</span></span>
    - <span data-ttu-id="85350-238">对于 UNC 路径：`\\Server\Folder`</span><span class="sxs-lookup"><span data-stu-id="85350-238">For a UNC path: `\\Server\Folder`</span></span>

    > [!NOTE]
    > <span data-ttu-id="85350-239">不支持通配符，也不支持 WebDav 位置。</span><span class="sxs-lookup"><span data-stu-id="85350-239">Wildcards are not supported and WebDav locations are not supported.</span></span>
    >
    > <span data-ttu-id="85350-240">若要稍后修改存储库，请改用 [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="85350-240">To modify the repository later on, use the [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) cmdlet instead.</span></span> 


<span data-ttu-id="85350-241">根据需要继续执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="85350-241">Continue with the following steps as needed:</span></span>

- [<span data-ttu-id="85350-242">运行发现周期并查看扫描程序的报告</span><span class="sxs-lookup"><span data-stu-id="85350-242">Run a discovery cycle and view reports for the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [<span data-ttu-id="85350-243">使用 PowerShell 配置扫描程序以应用分类和保护</span><span class="sxs-lookup"><span data-stu-id="85350-243">Use PowerShell to configure the scanner to apply classification and protection</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [<span data-ttu-id="85350-244">使用 PowerShell 为扫描程序配置 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="85350-244">Use PowerShell to configure a DLP policy with the scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

<span data-ttu-id="85350-245">下表列出了与安装扫描程序和管理内容扫描作业相关的 PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="85350-245">The following table lists PowerShell cmdlets that are relevant for installing the scanner and managing your content scan jobs:</span></span>

| <span data-ttu-id="85350-246">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="85350-246">Cmdlet</span></span> | <span data-ttu-id="85350-247">说明</span><span class="sxs-lookup"><span data-stu-id="85350-247">Description</span></span> |
|--|--|
| [<span data-ttu-id="85350-248">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="85350-248">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="85350-249">将新的存储库添加到内容扫描作业。</span><span class="sxs-lookup"><span data-stu-id="85350-249">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="85350-250">Get-AIPScannerConfiguration</span><span class="sxs-lookup"><span data-stu-id="85350-250">Get-AIPScannerConfiguration</span></span>](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|<span data-ttu-id="85350-251">返回有关群集的详细信息。</span><span class="sxs-lookup"><span data-stu-id="85350-251">Returns details about your cluster.</span></span> |
| [<span data-ttu-id="85350-252">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="85350-252">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="85350-253">获取内容扫描作业的详细信息。</span><span class="sxs-lookup"><span data-stu-id="85350-253">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="85350-254">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="85350-254">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="85350-255">获取定义用于内容扫描作业的存储库的详细信息。</span><span class="sxs-lookup"><span data-stu-id="85350-255">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="85350-256">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="85350-256">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="85350-257">删除内容扫描作业。</span><span class="sxs-lookup"><span data-stu-id="85350-257">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="85350-258">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="85350-258">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="85350-259">从内容扫描作业中删除存储库。</span><span class="sxs-lookup"><span data-stu-id="85350-259">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="85350-260">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="85350-260">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="85350-261">定义内容扫描作业的设置。</span><span class="sxs-lookup"><span data-stu-id="85350-261">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="85350-262">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="85350-262">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="85350-263">定义内容扫描作业中现有存储库的设置。</span><span class="sxs-lookup"><span data-stu-id="85350-263">Defines settings for an existing repository in your content scan job.</span></span> |
| | |

<span data-ttu-id="85350-264">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="85350-264">For more information, see:</span></span>

- [<span data-ttu-id="85350-265">什么是 Azure 信息保护统一标记扫描程序？</span><span class="sxs-lookup"><span data-stu-id="85350-265">What is the Azure Information Protection unified labeling scanner?</span></span>](/azure/information-protection/deploy-aip-scanner)
- [<span data-ttu-id="85350-266">配置和安装 Azure 信息保护 (AIP) 统一标记扫描程序</span><span class="sxs-lookup"><span data-stu-id="85350-266">Configuring and installing the Azure Information Protection (AIP) unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- <span data-ttu-id="85350-267">[仅使用 PowerShell 管理内容扫描作业](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。</span><span class="sxs-lookup"><span data-stu-id="85350-267">[Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>
