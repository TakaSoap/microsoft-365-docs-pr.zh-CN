---
title: 由世纪银行运营的 Office 365 的 Azure 信息保护支持
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
description: 了解有关由世纪 (运营的 Office 365 的 Azure 信息保护) AIP 服务以及如何为中国客户配置它。
monikerRange: o365-21vianet
ms.openlocfilehash: cee50384587ffc3e1e43eb9c6bb07d2e0ced7e13
ms.sourcegitcommit: cbe8724bd71d1c002395d98f1451c5f578c824f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "49988040"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="5a1d9-103">由世纪银行运营的 Office 365 的 Azure 信息保护支持</span><span class="sxs-lookup"><span data-stu-id="5a1d9-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="5a1d9-104">本文介绍了 Azure 信息保护 (AIP) 对由世纪银行运营的 Office 365 和商业产品/服务的支持之间的差异，以及为中国客户配置 AIP 的详细说明，包括如何安装 AIP 本地扫描程序和管理内容扫描作业。 &mdash;</span><span class="sxs-lookup"><span data-stu-id="5a1d9-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="5a1d9-105">由世纪银行运营的 Office 365 的 AIP 与商业产品/服务之间的差异</span><span class="sxs-lookup"><span data-stu-id="5a1d9-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="5a1d9-106">虽然我们的目标是通过由世纪银行运营的 Office 365 的 AIP 产品/服务，为中国客户提供所有商业特性和功能，但还有一些缺少的功能需要我们重点介绍。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="5a1d9-107">以下列表包括世纪银行运营的 Office 365 的 AIP 与自 2021 年 1 月开始的商业产品/服务之间的现有差异：</span><span class="sxs-lookup"><span data-stu-id="5a1d9-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="5a1d9-108">信息权限 (IRM) 仅适用于 Microsoft 365 企业应用版 (版本 11731.10000 或更高版本) 。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="5a1d9-109">不支持 Office 2010、Office 2013 和其他 Office 2016 版本。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="5a1d9-110">目前Active Directory Rights Management Services (AD RMS) AIP 的迁移不可用。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="5a1d9-111">支持与商业云中的用户共享受保护的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="5a1d9-112">目前，无法与商业云中的用户共享文档和电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="5a1d9-113">这包括由商业云中的世纪银行运营的 Office 365、由商业云中的世纪银行运营的非 Office 365 用户以及拥有 RMS for 个人版许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="5a1d9-114">SharePoint 的 IRM (受 IRM 保护的网站和) 目前不可用。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="5a1d9-115">AD RMS 的移动设备扩展当前不可用。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="5a1d9-116">Azure [China](/azure/information-protection/rms-client/mobile-app-faq) 21Vianet 不支持移动查看器。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="5a1d9-117">为中国客户配置 AIP</span><span class="sxs-lookup"><span data-stu-id="5a1d9-117">Configure AIP for customers in China</span></span>

<span data-ttu-id="5a1d9-118">为中国客户配置 AIP：</span><span class="sxs-lookup"><span data-stu-id="5a1d9-118">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="5a1d9-119">[为租户启用权限管理](#step-1-enable-rights-management-for-the-tenant)。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-119">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="5a1d9-120">[配置 DNS 加密](#step-2-configure-dns-encryption)。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-120">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="5a1d9-121">[安装和配置 AIP 统一标签客户端](#step-3-install-and-configure-the-aip-unified-labeling-client)。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-121">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="5a1d9-122">[在 Windows 上配置 AIP 应用](#step-4-configure-aip-apps-on-windows)。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-122">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="5a1d9-123">[安装 AIP 本地扫描程序并管理内容扫描作业](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-123">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="5a1d9-124">步骤 1：为租户启用权限管理</span><span class="sxs-lookup"><span data-stu-id="5a1d9-124">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="5a1d9-125">若要使加密正常工作，必须为租户启用 RMS。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-125">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="5a1d9-126">检查 RMS 是否已启用：</span><span class="sxs-lookup"><span data-stu-id="5a1d9-126">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="5a1d9-127">以管理员角色启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-127">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="5a1d9-128">如果未安装 AIPService 模块，请运行 `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-128">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="5a1d9-129">使用 导入模块 `Import-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-129">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="5a1d9-130">使用 连接到服务 `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-130">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="5a1d9-131">运行 `(Get-AipServiceConfiguration).FunctionalState` 并检查状态是否 `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-131">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="5a1d9-132">如果功能状态为 `Disabled` ，则运行 `Enable-AipService` 。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-132">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="5a1d9-133">步骤 2：配置 DNS 加密</span><span class="sxs-lookup"><span data-stu-id="5a1d9-133">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="5a1d9-134">若要使加密正常工作，Office 客户端应用程序必须连接到服务的中国实例，然后从该实例启动。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-134">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="5a1d9-135">若要将客户端应用程序重定向到正确的服务实例，租户管理员必须使用有关 Azure RMS URL 的信息配置 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-135">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="5a1d9-136">如果没有 DNS SRV 记录，客户端应用程序将默认尝试连接到公共云实例，并且将失败。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-136">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="5a1d9-137">此外，假定用户使用基于租户拥有域的用户名登录 (例如，) ，而不是用户名 (`joe@contoso.cn` `onmschina` 例如 `joe@contoso.onmschina.cn` ，) 。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-137">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="5a1d9-138">用户名中的域名用于将 DNS 重定向到正确的服务实例。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-138">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="5a1d9-139">配置 DNS 加密 - Windows</span><span class="sxs-lookup"><span data-stu-id="5a1d9-139">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="5a1d9-140">获取 RMS ID：</span><span class="sxs-lookup"><span data-stu-id="5a1d9-140">Get the RMS ID:</span></span>

    1. <span data-ttu-id="5a1d9-141">以管理员角色启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-141">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="5a1d9-142">如果未安装 AIPService 模块，请运行 `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-142">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="5a1d9-143">使用 连接到服务 `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-143">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="5a1d9-144">运行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 以获取 RMS ID。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-144">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="5a1d9-145">登录到 DNS 提供程序，导航到域的 DNS 设置，然后添加新的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-145">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="5a1d9-146">服务 = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="5a1d9-146">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="5a1d9-147">协议 = `_http`</span><span class="sxs-lookup"><span data-stu-id="5a1d9-147">Protocol = `_http`</span></span>
    - <span data-ttu-id="5a1d9-148">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="5a1d9-148">Name = `_tcp`</span></span>
    - <span data-ttu-id="5a1d9-149">目标 = `[GUID].rms.aadrm.cn` (GUID 是 RMS ID) </span><span class="sxs-lookup"><span data-stu-id="5a1d9-149">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="5a1d9-150">Priority、Weight、Seconds、TTL = 默认值</span><span class="sxs-lookup"><span data-stu-id="5a1d9-150">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="5a1d9-151">将自定义域与 Azure 门户中的 [租户关联](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-151">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="5a1d9-152">这会在 DNS 中添加条目，在将值添加到 DNS 设置后，可能需要几分钟时间才能进行验证。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-152">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="5a1d9-153">使用相应的全局管理员凭据登录到 Microsoft 365 管理中心，并添加域 (例如，) `contoso.cn` 用户创建。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-153">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="5a1d9-154">在验证过程中，可能需要进行其他 DNS 更改。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-154">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="5a1d9-155">验证完成后，可创建用户。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-155">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="5a1d9-156">配置 DNS 加密 - Mac、iOS、Android</span><span class="sxs-lookup"><span data-stu-id="5a1d9-156">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="5a1d9-157">登录到 DNS 提供程序，导航到域的 DNS 设置，然后添加新的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-157">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="5a1d9-158">服务 = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="5a1d9-158">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="5a1d9-159">协议 = `_http`</span><span class="sxs-lookup"><span data-stu-id="5a1d9-159">Protocol = `_http`</span></span>
- <span data-ttu-id="5a1d9-160">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="5a1d9-160">Name = `_tcp`</span></span>
- <span data-ttu-id="5a1d9-161">目标 = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="5a1d9-161">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="5a1d9-162">端口 = `80`</span><span class="sxs-lookup"><span data-stu-id="5a1d9-162">Port = `80`</span></span>
- <span data-ttu-id="5a1d9-163">Priority、Weight、Seconds、TTL = 默认值</span><span class="sxs-lookup"><span data-stu-id="5a1d9-163">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="5a1d9-164">步骤 3：安装和配置 AIP 统一标记客户端</span><span class="sxs-lookup"><span data-stu-id="5a1d9-164">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="5a1d9-165">从 Microsoft 下载中心下载 AIP 统一标签 [客户端](https://www.microsoft.com/download/details.aspx?id=53018)。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-165">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="5a1d9-166">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="5a1d9-166">For more information, see:</span></span>

- [<span data-ttu-id="5a1d9-167">AIP 文档</span><span class="sxs-lookup"><span data-stu-id="5a1d9-167">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="5a1d9-168">AIP 版本历史记录和支持策略</span><span class="sxs-lookup"><span data-stu-id="5a1d9-168">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="5a1d9-169">AIP 系统要求</span><span class="sxs-lookup"><span data-stu-id="5a1d9-169">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="5a1d9-170">AIP 快速入门：部署 AIP 客户端</span><span class="sxs-lookup"><span data-stu-id="5a1d9-170">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="5a1d9-171">AIP 管理员指南</span><span class="sxs-lookup"><span data-stu-id="5a1d9-171">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="5a1d9-172">AIP 用户指南</span><span class="sxs-lookup"><span data-stu-id="5a1d9-172">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="5a1d9-173">了解 Microsoft 365 敏感度标签</span><span class="sxs-lookup"><span data-stu-id="5a1d9-173">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="5a1d9-174">步骤 4：在 Windows 上配置 AIP 应用</span><span class="sxs-lookup"><span data-stu-id="5a1d9-174">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="5a1d9-175">Windows 上的 AIP 应用需要以下注册表项来将它们指向适用于 Azure China 的正确主云：</span><span class="sxs-lookup"><span data-stu-id="5a1d9-175">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="5a1d9-176">注册表节点 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="5a1d9-176">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="5a1d9-177">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="5a1d9-177">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="5a1d9-178">值 = `6` (默认值 = 0) </span><span class="sxs-lookup"><span data-stu-id="5a1d9-178">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="5a1d9-179">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="5a1d9-179">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a1d9-180">确保在卸载后不删除注册表项。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-180">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="5a1d9-181">如果密钥为空、不正确或不存在，则该功能的行为将为默认值 (默认值 = 0，用于商业云) 。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-181">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="5a1d9-182">如果键为空或不正确，也会向日志中添加打印错误。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-182">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="5a1d9-183">步骤 5：安装 AIP 本地扫描程序并管理内容扫描作业</span><span class="sxs-lookup"><span data-stu-id="5a1d9-183">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="5a1d9-184">安装 AIP 本地扫描程序以扫描网络和内容共享中的敏感数据，并应用组织策略中配置的分类和保护标签。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-184">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="5a1d9-185">安装扫描程序和管理内容扫描作业时，请使用以下 cmdlet，而不是商业产品/服务使用的 Azure 门户界面：</span><span class="sxs-lookup"><span data-stu-id="5a1d9-185">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

| <span data-ttu-id="5a1d9-186">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="5a1d9-186">Cmdlet</span></span> | <span data-ttu-id="5a1d9-187">说明</span><span class="sxs-lookup"><span data-stu-id="5a1d9-187">Description</span></span> |
|--|--|
| [<span data-ttu-id="5a1d9-188">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="5a1d9-188">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="5a1d9-189">向内容扫描作业添加新存储库。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-189">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="5a1d9-190">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="5a1d9-190">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="5a1d9-191">获取有关内容扫描作业的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-191">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="5a1d9-192">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="5a1d9-192">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="5a1d9-193">获取为内容扫描作业定义的存储库的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-193">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="5a1d9-194">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="5a1d9-194">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="5a1d9-195">删除内容扫描作业。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-195">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="5a1d9-196">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="5a1d9-196">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="5a1d9-197">从内容扫描作业中删除存储库。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-197">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="5a1d9-198">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="5a1d9-198">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="5a1d9-199">定义内容扫描作业的设置。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-199">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="5a1d9-200">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="5a1d9-200">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="5a1d9-201">定义内容扫描作业中现有存储库的设置。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-201">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="5a1d9-202">有关详细信息，请参阅什么是 [Azure 信息保护统一标签扫描程序？](/azure/information-protection/deploy-aip-scanner) 以及仅使用 [PowerShell 管理内容扫描作业](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。</span><span class="sxs-lookup"><span data-stu-id="5a1d9-202">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>