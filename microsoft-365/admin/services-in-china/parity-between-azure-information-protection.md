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
ms.openlocfilehash: bddba69ecc8b7b80d2b2c7c48d820ec22d293362
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418028"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="a1d7d-103">适用于由世纪互联运营的 Office 365 的 Azure 信息保护支持</span><span class="sxs-lookup"><span data-stu-id="a1d7d-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="a1d7d-104">本文介绍了 Azure 信息保护 （AIP） 对由世纪互联运营的 Office 365 和商业产品/服务之间的差异，以及为中国&mdash;客户配置 AIP 的详细说明，包括如何安装 AIP 本地扫描仪和管理内容扫描作业。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="a1d7d-105">由世纪互联运营的 Office 365 的 AIP 与商业产品之间的差异</span><span class="sxs-lookup"><span data-stu-id="a1d7d-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="a1d7d-106">我们的目标是通过针对由世纪互联运营的 Office 365 的 AIP 产品，为中国客户提供所有商业特性和功能，但是我们要强调的一些缺失功能。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="a1d7d-107">以下列表包含世纪互联运营的 Office 365 的 AIP 与 2021 年 1 月前的商业产品之间的现有缺陷：</span><span class="sxs-lookup"><span data-stu-id="a1d7d-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="a1d7d-108">仅 Microsoft 365 企业版应用（内部版本 11731.10000 或更高版本）支持信息权限管理 （IRM）。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="a1d7d-109">不支持 Office 2010、Office 2013 和其他 Office 2016 版本。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="a1d7d-110">目前无法从 Active Directory 权限管理服务 （AD RMS） 迁移到 AIP。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="a1d7d-111">支持在商业云中与用户共享受保护的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="a1d7d-112">目前，不可在商业云中与用户共享文档和电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="a1d7d-113">这包括商业云中由世纪互联络用户运营的 Office 365、在商业云中由世纪互联用户运营的非 Office 365 用户，以及拥有个人版 RMS 许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="a1d7d-114">具有 SharePoint（受 IRM 保护的网站和库）的 IRM 当前不可用。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="a1d7d-115">AD RMS 的移动设备扩展当前不可用。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="a1d7d-116">Azure 中国世纪互联不支持该[手机阅读器](/azure/information-protection/rms-client/mobile-app-faq)。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="a1d7d-117">Azure 门户的 AIP 区域不可用于中国客户。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="a1d7d-118">使用 [PowerShell 命令](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) ，而不在门户中执行操作，如安装本地扫描仪和管理内容扫描作业。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-118">Use [PowerShell commands](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as installing the on-premises scanner and managing your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="a1d7d-119">为中国的客户配置 AIP</span><span class="sxs-lookup"><span data-stu-id="a1d7d-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="a1d7d-120">为中国的客户配置 AIP：</span><span class="sxs-lookup"><span data-stu-id="a1d7d-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="a1d7d-121">[为租户启用权限](#step-1-enable-rights-management-for-the-tenant)。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="a1d7d-122">[配置 DNS 加密](#step-2-configure-dns-encryption)。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-122">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="a1d7d-123">[安装和配置 AIP 统一标签客户端](#step-3-install-and-configure-the-aip-unified-labeling-client)。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-123">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="a1d7d-124">[在 Windows 桌面应用中配置 AIP](#step-4-configure-aip-apps-on-windows)。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-124">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="a1d7d-125">[安装 AIP 本地扫描仪和管理内容扫描作业](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-125">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="a1d7d-126">步骤 1：为租户启用权限管理</span><span class="sxs-lookup"><span data-stu-id="a1d7d-126">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="a1d7d-127">若要使加密能正常工作，必须为租户启用 RMS。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-127">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="a1d7d-128">检查是否已启用 RMS：</span><span class="sxs-lookup"><span data-stu-id="a1d7d-128">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="a1d7d-129">以管理员角色启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-129">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="a1d7d-130">如果未安装 AIPService 模块，请运行 `Install-Module AipService`。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-130">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="a1d7d-131">使用 `Import-Module AipService`。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-131">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="a1d7d-132">使用 `Connect-AipService -environmentname azurechinacloud`连接到服务。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-132">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="a1d7d-133">运行 `(Get-AipServiceConfiguration).FunctionalState` ，检查状态是否 `Enabled`。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-133">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="a1d7d-134">如果功能状态为 `Disabled`，请运行 `Enable-AipService`。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-134">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="a1d7d-135">步骤 2：配置 DNS 加密</span><span class="sxs-lookup"><span data-stu-id="a1d7d-135">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="a1d7d-136">为使加密能正常工作，Office 客户端应用程序必须连接到服务的中国实例并请从其中启动。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-136">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="a1d7d-137">若要将客户端应用程序重定向到正确的服务实例，租户管理员必须配置包含 Azure RMS URL 相关信息的 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-137">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="a1d7d-138">如果没有 DNS SRV 记录，客户端应用程序将默认尝试连接到公共云实例，且将失败。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-138">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="a1d7d-139">此外，假设用户将会使用基于租户拥有的域（例如 `joe@contoso.cn`）而不是 `onmschina` 用户名（例如 `joe@contoso.onmschina.cn`）登录。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-139">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="a1d7d-140">用户名中的域名用于 DNS 重定向到正确的服务实例。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-140">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="a1d7d-141">配置 DNS 加密 - Windows</span><span class="sxs-lookup"><span data-stu-id="a1d7d-141">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="a1d7d-142">获取 RMS ID：</span><span class="sxs-lookup"><span data-stu-id="a1d7d-142">Get the RMS ID:</span></span>

    1. <span data-ttu-id="a1d7d-143">以管理员角色启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-143">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="a1d7d-144">如果未安装 AIPService 模块，请运行 `Install-Module AipService`。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-144">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="a1d7d-145">使用 `Connect-AipService -environmentname azurechinacloud`连接到服务。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-145">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="a1d7d-146">运行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 获得 RMS ID。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-146">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="a1d7d-147">登录到您的 DNS 提供商，导航到域的 DNS 设置，然后添加新的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="a1d7d-148">服务 = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="a1d7d-148">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="a1d7d-149">协议 = `_http`</span><span class="sxs-lookup"><span data-stu-id="a1d7d-149">Protocol = `_http`</span></span>
    - <span data-ttu-id="a1d7d-150">名称 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="a1d7d-150">Name = `_tcp`</span></span>
    - <span data-ttu-id="a1d7d-151">目标 = `[GUID].rms.aadrm.cn`（其中 GUID 为 RMS ID）</span><span class="sxs-lookup"><span data-stu-id="a1d7d-151">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="a1d7d-152">优先级、权重、秒数、TTL = 默认值</span><span class="sxs-lookup"><span data-stu-id="a1d7d-152">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="a1d7d-153">将自定义域与 [门户中的租户](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-153">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="a1d7d-154">这将在 DNS 中添加条目，这可能需要几分钟时间才能在向 DNS 设置添加该值后进行验证。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-154">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="a1d7d-155">使用相应的全局管理员凭据登录 Microsoft 365 管理中心，并添加域（例如， `contoso.cn`）供用户创建。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-155">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="a1d7d-156">在验证过程中，可能需要其他 DNS 更改。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-156">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="a1d7d-157">验证完成后，可创建用户。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-157">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="a1d7d-158">配置 DNS 加密 - Mac、iOS、Android</span><span class="sxs-lookup"><span data-stu-id="a1d7d-158">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="a1d7d-159">登录到您的 DNS 提供商，导航到域的 DNS 设置，然后添加新的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-159">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="a1d7d-160">服务 = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="a1d7d-160">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="a1d7d-161">协议 = `_http`</span><span class="sxs-lookup"><span data-stu-id="a1d7d-161">Protocol = `_http`</span></span>
- <span data-ttu-id="a1d7d-162">名称 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="a1d7d-162">Name = `_tcp`</span></span>
- <span data-ttu-id="a1d7d-163">目标 = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="a1d7d-163">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="a1d7d-164">端口 = `80`</span><span class="sxs-lookup"><span data-stu-id="a1d7d-164">Port = `80`</span></span>
- <span data-ttu-id="a1d7d-165">优先级、权重、秒数、TTL = 默认值</span><span class="sxs-lookup"><span data-stu-id="a1d7d-165">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="a1d7d-166">步骤 3：安装和配置 AIP 统一标签客户端</span><span class="sxs-lookup"><span data-stu-id="a1d7d-166">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="a1d7d-167">从 Microsoft 下载中心或 [AIP 统一标签](https://www.microsoft.com/download/details.aspx?id=53018)。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-167">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="a1d7d-168">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="a1d7d-168">For more information, see:</span></span>

- [<span data-ttu-id="a1d7d-169">AIP 文档</span><span class="sxs-lookup"><span data-stu-id="a1d7d-169">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="a1d7d-170">AIP 版本历史记录和支持策略</span><span class="sxs-lookup"><span data-stu-id="a1d7d-170">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="a1d7d-171">AIP 系统要求</span><span class="sxs-lookup"><span data-stu-id="a1d7d-171">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="a1d7d-172">AIP 快速入门：部署 AIP 客户端</span><span class="sxs-lookup"><span data-stu-id="a1d7d-172">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="a1d7d-173">AIP 管理员指南</span><span class="sxs-lookup"><span data-stu-id="a1d7d-173">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="a1d7d-174">AIP 用户指南</span><span class="sxs-lookup"><span data-stu-id="a1d7d-174">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="a1d7d-175">了解 Microsoft 365 敏感度标签</span><span class="sxs-lookup"><span data-stu-id="a1d7d-175">Learn about Microsoft 365 sensitivity labels</span></span>](../../compliance/sensitivity-labels.md)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="a1d7d-176">步骤 4：在 Windows 上配置 AIP 应用</span><span class="sxs-lookup"><span data-stu-id="a1d7d-176">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="a1d7d-177">Windows 上的 AIP 应用需要以下注册表项，用于指向 Azure China 的正确主权云：</span><span class="sxs-lookup"><span data-stu-id="a1d7d-177">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="a1d7d-178">注册表节点 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="a1d7d-178">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="a1d7d-179">名称 = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="a1d7d-179">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="a1d7d-180">值 = `6`（默认 = 0）</span><span class="sxs-lookup"><span data-stu-id="a1d7d-180">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="a1d7d-181">类型 = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="a1d7d-181">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1d7d-182">请确保卸载后不会删除注册表项。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-182">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="a1d7d-183">如果密钥为空、不正确或不存在，则功能将按默认值（商业云的默认值 = 0）运行。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-183">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="a1d7d-184">如果密钥为空或不正确，也会向日志添加打印错误。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-184">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="a1d7d-185">步骤 5：安装 AIP 本地扫描仪和管理内容扫描作业</span><span class="sxs-lookup"><span data-stu-id="a1d7d-185">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="a1d7d-186">安装 AIP 本地扫描仪扫描网络和内容共享以访问敏感数据，并按组织策略中配置应用分类和保护标签。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-186">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

- <span data-ttu-id="a1d7d-187">为 [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)命令创建和配置 Azure AD 应用程序时，"请求 **API** 权限"窗格将显示我的组织使用的 API 选项卡，而不是 **Microsoft API** 选项卡。选择 **我的组织使用的 API，** 然后选择 **"Azure 权限管理服务"。**</span><span class="sxs-lookup"><span data-stu-id="a1d7d-187">When creating and configuring Azure AD applications for the [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) command, the **Request API permissions** pane shows the **APIs my organization uses** tab instead of the **Microsoft APIs** tab. Select the **APIs my organization uses** to then select **Azure Rights Management Services**.</span></span>

- <span data-ttu-id="a1d7d-188">安装扫描仪和管理内容扫描作业时，请使用以下 cmdlet，而不是商业产品使用的 Azure 门户界面：</span><span class="sxs-lookup"><span data-stu-id="a1d7d-188">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

    | <span data-ttu-id="a1d7d-189">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a1d7d-189">Cmdlet</span></span> | <span data-ttu-id="a1d7d-190">说明</span><span class="sxs-lookup"><span data-stu-id="a1d7d-190">Description</span></span> |
    |--|--|
    | [<span data-ttu-id="a1d7d-191">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="a1d7d-191">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="a1d7d-192">将新的存储库添加到内容扫描作业。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-192">Adds a new repository to your content scan job.</span></span> |
    | [<span data-ttu-id="a1d7d-193">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="a1d7d-193">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="a1d7d-194">获取内容扫描作业的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-194">Gets details about your content scan job.</span></span> |
    | [<span data-ttu-id="a1d7d-195">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="a1d7d-195">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="a1d7d-196">获取定义用于内容扫描作业的存储库的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-196">Gets details about repositories defined for your content scan job.</span></span> |
    | [<span data-ttu-id="a1d7d-197">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="a1d7d-197">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="a1d7d-198">删除内容扫描作业。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-198">Deletes your content scan job.</span></span> |
    | [<span data-ttu-id="a1d7d-199">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="a1d7d-199">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="a1d7d-200">从内容扫描作业中删除存储库。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-200">Removes a repository from your content scan job.</span></span> |
    | [<span data-ttu-id="a1d7d-201">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="a1d7d-201">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="a1d7d-202">定义内容扫描作业的设置。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-202">Defines settings for your content scan job.</span></span> |
    | [<span data-ttu-id="a1d7d-203">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="a1d7d-203">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="a1d7d-204">定义内容扫描作业中现有存储库的设置。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-204">Defines settings for an existing repository in your content scan job.</span></span> |
    | | |

> [!TIP]
> <span data-ttu-id="a1d7d-205">安装 [扫描程序时](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner)，在 [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) 命令中使用相同的群集名称将多个扫描程序节点关联到同一群集。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-205">When [installing the scanner](/azure/information-protection/deploy-aip-scanner-configure-install#install-the-scanner), use the same cluster name in the [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) command to associate multiple scanner nodes to the same cluster.</span></span> <span data-ttu-id="a1d7d-206">将同一群集用于多个扫描程序节点使多个扫描程序可以协同工作来执行扫描。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-206">Using the same cluster for multiple scanner nodes enables multiple scanners to work together to perform your scans.</span></span>
> 
> <span data-ttu-id="a1d7d-207">使用 [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) cmdlet 可返回有关群集的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-207">Use the [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration) cmdlet to return details about your cluster.</span></span>
> 
<span data-ttu-id="a1d7d-208">有关详细信息，请参阅 [什么是 Azure 信息保护统一标签扫描仪？](/azure/information-protection/deploy-aip-scanner) [PowerShell 管理内容扫描作业](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。</span><span class="sxs-lookup"><span data-stu-id="a1d7d-208">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>