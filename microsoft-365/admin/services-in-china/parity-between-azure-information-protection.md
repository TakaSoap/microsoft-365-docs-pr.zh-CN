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
ms.openlocfilehash: 300e7633237511fb9de64199ae7cf54594f2239e
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099674"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a><span data-ttu-id="0c9e2-103">由世纪银行运营的 Office 365 的 Azure 信息保护支持</span><span class="sxs-lookup"><span data-stu-id="0c9e2-103">Azure Information Protection support for Office 365 operated by 21Vianet</span></span>

<span data-ttu-id="0c9e2-104">本文介绍了 Azure 信息保护 (AIP) 对由世纪银行运营的 Office 365 和商业产品/服务的支持之间的差异，以及为中国客户配置 AIP 的详细说明，包括如何安装 AIP 本地扫描程序和管理内容扫描作业。 &mdash;</span><span class="sxs-lookup"><span data-stu-id="0c9e2-104">This article covers the differences between Azure Information Protection (AIP) support for Office 365 operated by 21Vianet and commercial offerings, as well as specific instructions for configuring AIP for customers in China&mdash;including how to install the AIP on-premises scanner and manage content scan jobs.</span></span>

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="0c9e2-105">由世纪银行运营的 Office 365 的 AIP 与商业产品/服务之间的差异</span><span class="sxs-lookup"><span data-stu-id="0c9e2-105">Differences between AIP for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="0c9e2-106">虽然我们的目标是通过由世纪银行运营的 Office 365 的 AIP 产品/服务，为中国客户提供所有商业特性和功能，但还有一些缺少的功能需要我们重点介绍。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-106">While our goal is to deliver all commercial features and functionality to customers in China with our AIP for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="0c9e2-107">以下列表包括世纪银行运营的 Office 365 的 AIP 与自 2021 年 1 月开始的商业产品/服务之间的现有差异：</span><span class="sxs-lookup"><span data-stu-id="0c9e2-107">The following list includes the existing gaps between AIP for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="0c9e2-108">信息权限 (IRM) 仅适用于 Microsoft 365 企业应用版 (版本 11731.10000 或更高版本) 。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-108">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="0c9e2-109">不支持 Office 2010、Office 2013 和其他 Office 2016 版本。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-109">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="0c9e2-110">目前Active Directory Rights Management Services (AD RMS) AIP 的迁移不可用。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-110">Migration from Active Directory Rights Management Services (AD RMS) to AIP is currently not available.</span></span>
  
- <span data-ttu-id="0c9e2-111">支持与商业云中的用户共享受保护的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-111">Sharing of protected emails with users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="0c9e2-112">目前，无法与商业云中的用户共享文档和电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-112">Sharing of documents and email attachments with users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="0c9e2-113">这包括由商业云中的世纪版用户运营的 Office 365、由商业云中的世纪银行运营的非 Office 365 用户和拥有 RMS 个人版许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-113">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="0c9e2-114">SharePoint 的 IRM (受 IRM 保护的网站和) 目前不可用。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-114">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="0c9e2-115">AD RMS 的移动设备扩展当前不可用。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-115">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="0c9e2-116">Azure [China](/azure/information-protection/rms-client/mobile-app-faq) 21Vianet 不支持移动查看器。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-116">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

- <span data-ttu-id="0c9e2-117">Azure 门户的 AIP 区域在中国客户无法使用。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-117">The AIP area of the Azure portal is unavailable to customers in China.</span></span> <span data-ttu-id="0c9e2-118">使用 [PowerShell](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 命令，而不是在门户中执行诸如安装本地扫描程序和管理内容扫描作业等操作。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-118">Use [PowerShell commands](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) instead of performing actions in the portal, such as installing the on-premises scanner and managing your content scan jobs.</span></span>

## <a name="configure-aip-for-customers-in-china"></a><span data-ttu-id="0c9e2-119">为中国客户配置 AIP</span><span class="sxs-lookup"><span data-stu-id="0c9e2-119">Configure AIP for customers in China</span></span>

<span data-ttu-id="0c9e2-120">为中国客户配置 AIP：</span><span class="sxs-lookup"><span data-stu-id="0c9e2-120">To configure AIP for customers in China:</span></span>
1. <span data-ttu-id="0c9e2-121">[为租户启用权限管理](#step-1-enable-rights-management-for-the-tenant)。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-121">[Enable Rights Management for the tenant](#step-1-enable-rights-management-for-the-tenant).</span></span>

2. <span data-ttu-id="0c9e2-122">[配置 DNS 加密](#step-2-configure-dns-encryption)。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-122">[Configure DNS encryption](#step-2-configure-dns-encryption).</span></span>

3. <span data-ttu-id="0c9e2-123">[安装和配置 AIP 统一标签客户端](#step-3-install-and-configure-the-aip-unified-labeling-client)。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-123">[Install and configure the AIP unified labeling client](#step-3-install-and-configure-the-aip-unified-labeling-client).</span></span>

4. <span data-ttu-id="0c9e2-124">[在 Windows 上配置 AIP 应用](#step-4-configure-aip-apps-on-windows)。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-124">[Configure AIP apps on Windows](#step-4-configure-aip-apps-on-windows).</span></span>

5. <span data-ttu-id="0c9e2-125">[安装 AIP 本地扫描程序并管理内容扫描作业](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-125">[Install the AIP on-premises scanner and manage content scan jobs](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs).</span></span> 

### <a name="step-1-enable-rights-management-for-the-tenant"></a><span data-ttu-id="0c9e2-126">步骤 1：为租户启用权限管理</span><span class="sxs-lookup"><span data-stu-id="0c9e2-126">Step 1: Enable Rights Management for the tenant</span></span>

<span data-ttu-id="0c9e2-127">若要使加密正常工作，必须为租户启用 RMS。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-127">For the encryption to work correctly, RMS must be enabled for the tenant.</span></span>

1. <span data-ttu-id="0c9e2-128">检查 RMS 是否已启用：</span><span class="sxs-lookup"><span data-stu-id="0c9e2-128">Check if RMS is enabled:</span></span>

    1. <span data-ttu-id="0c9e2-129">以管理员角色启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-129">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="0c9e2-130">如果未安装 AIPService 模块，请运行 `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-130">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="0c9e2-131">使用 导入模块 `Import-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-131">Import the module using `Import-Module AipService`.</span></span>
    4. <span data-ttu-id="0c9e2-132">使用 连接到服务 `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-132">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    5. <span data-ttu-id="0c9e2-133">运行 `(Get-AipServiceConfiguration).FunctionalState` 并检查状态是否 `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-133">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

2. <span data-ttu-id="0c9e2-134">如果功能状态为 `Disabled` ，则运行 `Enable-AipService` 。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-134">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="step-2-configure-dns-encryption"></a><span data-ttu-id="0c9e2-135">步骤 2：配置 DNS 加密</span><span class="sxs-lookup"><span data-stu-id="0c9e2-135">Step 2: Configure DNS encryption</span></span>

<span data-ttu-id="0c9e2-136">若要使加密正常工作，Office 客户端应用程序必须连接到服务的中国实例，然后从该实例启动。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-136">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="0c9e2-137">若要将客户端应用程序重定向到正确的服务实例，租户管理员必须使用有关 Azure RMS URL 的信息配置 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-137">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="0c9e2-138">如果没有 DNS SRV 记录，客户端应用程序将默认尝试连接到公共云实例，并且将失败。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-138">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="0c9e2-139">此外，假定用户使用基于租户拥有域的用户名登录 (例如，) ，而不是用户名 (`joe@contoso.cn` `onmschina` 例如 `joe@contoso.onmschina.cn` ，) 。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-139">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="0c9e2-140">用户名中的域名用于将 DNS 重定向到正确的服务实例。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-140">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

#### <a name="configure-dns-encryption---windows"></a><span data-ttu-id="0c9e2-141">配置 DNS 加密 - Windows</span><span class="sxs-lookup"><span data-stu-id="0c9e2-141">Configure DNS encryption - Windows</span></span>

1. <span data-ttu-id="0c9e2-142">获取 RMS ID：</span><span class="sxs-lookup"><span data-stu-id="0c9e2-142">Get the RMS ID:</span></span>

    1. <span data-ttu-id="0c9e2-143">以管理员角色启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-143">Launch PowerShell as an administrator.</span></span>
    2. <span data-ttu-id="0c9e2-144">如果未安装 AIPService 模块，请运行 `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-144">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
    3. <span data-ttu-id="0c9e2-145">使用 连接到服务 `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-145">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
    4. <span data-ttu-id="0c9e2-146">运行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 以获取 RMS ID。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-146">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

2. <span data-ttu-id="0c9e2-147">登录到 DNS 提供程序，导航到域的 DNS 设置，然后添加新的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-147">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

    - <span data-ttu-id="0c9e2-148">服务 = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="0c9e2-148">Service = `_rmsredir`</span></span>
    - <span data-ttu-id="0c9e2-149">协议 = `_http`</span><span class="sxs-lookup"><span data-stu-id="0c9e2-149">Protocol = `_http`</span></span>
    - <span data-ttu-id="0c9e2-150">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="0c9e2-150">Name = `_tcp`</span></span>
    - <span data-ttu-id="0c9e2-151">目标 = `[GUID].rms.aadrm.cn` (GUID 是 RMS ID) </span><span class="sxs-lookup"><span data-stu-id="0c9e2-151">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
    - <span data-ttu-id="0c9e2-152">Priority、Weight、Seconds、TTL = 默认值</span><span class="sxs-lookup"><span data-stu-id="0c9e2-152">Priority, Weight, Seconds, TTL = default values</span></span>

3. <span data-ttu-id="0c9e2-153">将自定义域与 Azure 门户中的 [租户关联](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-153">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="0c9e2-154">这会在 DNS 中添加条目，在将值添加到 DNS 设置后，可能需要几分钟时间才能进行验证。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-154">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

4. <span data-ttu-id="0c9e2-155">使用相应的全局管理员凭据登录到 Microsoft 365 管理中心，并添加域 (例如，) `contoso.cn` 用户创建。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-155">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="0c9e2-156">在验证过程中，可能需要进行其他 DNS 更改。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-156">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="0c9e2-157">验证完成后，可创建用户。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-157">Once verification is done, users can be created.</span></span>

#### <a name="configure-dns-encryption---mac-ios-android"></a><span data-ttu-id="0c9e2-158">配置 DNS 加密 - Mac、iOS、Android</span><span class="sxs-lookup"><span data-stu-id="0c9e2-158">Configure DNS encryption - Mac, iOS, Android</span></span>

<span data-ttu-id="0c9e2-159">登录到 DNS 提供程序，导航到域的 DNS 设置，然后添加新的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-159">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="0c9e2-160">服务 = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="0c9e2-160">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="0c9e2-161">协议 = `_http`</span><span class="sxs-lookup"><span data-stu-id="0c9e2-161">Protocol = `_http`</span></span>
- <span data-ttu-id="0c9e2-162">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="0c9e2-162">Name = `_tcp`</span></span>
- <span data-ttu-id="0c9e2-163">目标 = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="0c9e2-163">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="0c9e2-164">端口 = `80`</span><span class="sxs-lookup"><span data-stu-id="0c9e2-164">Port = `80`</span></span>
- <span data-ttu-id="0c9e2-165">Priority、Weight、Seconds、TTL = 默认值</span><span class="sxs-lookup"><span data-stu-id="0c9e2-165">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a><span data-ttu-id="0c9e2-166">步骤 3：安装和配置 AIP 统一标记客户端</span><span class="sxs-lookup"><span data-stu-id="0c9e2-166">Step 3: Install and configure the AIP unified labeling client</span></span>

<span data-ttu-id="0c9e2-167">从 Microsoft 下载中心下载 AIP 统一标签 [客户端](https://www.microsoft.com/download/details.aspx?id=53018)。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-167">Download the AIP unified labeling client from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="0c9e2-168">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="0c9e2-168">For more information, see:</span></span>

- [<span data-ttu-id="0c9e2-169">AIP 文档</span><span class="sxs-lookup"><span data-stu-id="0c9e2-169">AIP documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="0c9e2-170">AIP 版本历史记录和支持策略</span><span class="sxs-lookup"><span data-stu-id="0c9e2-170">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="0c9e2-171">AIP 系统要求</span><span class="sxs-lookup"><span data-stu-id="0c9e2-171">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="0c9e2-172">AIP 快速入门：部署 AIP 客户端</span><span class="sxs-lookup"><span data-stu-id="0c9e2-172">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="0c9e2-173">AIP 管理员指南</span><span class="sxs-lookup"><span data-stu-id="0c9e2-173">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="0c9e2-174">AIP 用户指南</span><span class="sxs-lookup"><span data-stu-id="0c9e2-174">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="0c9e2-175">了解 Microsoft 365 敏感度标签</span><span class="sxs-lookup"><span data-stu-id="0c9e2-175">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a><span data-ttu-id="0c9e2-176">步骤 4：在 Windows 上配置 AIP 应用</span><span class="sxs-lookup"><span data-stu-id="0c9e2-176">Step 4: Configure AIP apps on Windows</span></span>

<span data-ttu-id="0c9e2-177">Windows 上的 AIP 应用需要以下注册表项来将它们指向适用于 Azure China 的正确主云：</span><span class="sxs-lookup"><span data-stu-id="0c9e2-177">AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="0c9e2-178">注册表节点 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="0c9e2-178">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="0c9e2-179">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="0c9e2-179">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="0c9e2-180">值 = `6` (默认值 = 0) </span><span class="sxs-lookup"><span data-stu-id="0c9e2-180">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="0c9e2-181">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="0c9e2-181">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c9e2-182">确保在卸载后不删除注册表项。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-182">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="0c9e2-183">如果密钥为空、不正确或不存在，则该功能的行为将为默认值 (默认值 = 0，用于商业云) 。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-183">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="0c9e2-184">如果键为空或不正确，也会向日志中添加打印错误。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-184">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a><span data-ttu-id="0c9e2-185">步骤 5：安装 AIP 本地扫描程序和管理内容扫描作业</span><span class="sxs-lookup"><span data-stu-id="0c9e2-185">Step 5: Install the AIP on-premises scanner and manage content scan jobs</span></span>

<span data-ttu-id="0c9e2-186">安装 AIP 本地扫描程序以扫描网络和内容共享中的敏感数据，并应用组织策略中配置的分类和保护标签。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-186">Install the AIP on-premises scanner to scan your network and content shares for sensitive data, and apply classification and protection labels as configured in your organization's policy.</span></span>

<span data-ttu-id="0c9e2-187">安装扫描程序和管理内容扫描作业时，请使用以下 cmdlet，而不是商业产品/服务使用的 Azure 门户界面：</span><span class="sxs-lookup"><span data-stu-id="0c9e2-187">When installing the scanner and managing your content scan jobs, use the following cmdlets instead of the Azure portal interface that's used by the commercial offerings:</span></span><br><br>

| <span data-ttu-id="0c9e2-188">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0c9e2-188">Cmdlet</span></span> | <span data-ttu-id="0c9e2-189">说明</span><span class="sxs-lookup"><span data-stu-id="0c9e2-189">Description</span></span> |
|--|--|
| [<span data-ttu-id="0c9e2-190">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="0c9e2-190">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="0c9e2-191">向内容扫描作业添加新存储库。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-191">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="0c9e2-192">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="0c9e2-192">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="0c9e2-193">获取有关内容扫描作业的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-193">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="0c9e2-194">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="0c9e2-194">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="0c9e2-195">获取为内容扫描作业定义的存储库的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-195">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="0c9e2-196">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="0c9e2-196">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="0c9e2-197">删除内容扫描作业。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-197">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="0c9e2-198">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="0c9e2-198">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="0c9e2-199">从内容扫描作业中删除存储库。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-199">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="0c9e2-200">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="0c9e2-200">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="0c9e2-201">定义内容扫描作业的设置。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-201">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="0c9e2-202">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="0c9e2-202">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="0c9e2-203">定义内容扫描作业中现有存储库的设置。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-203">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="0c9e2-204">有关详细信息，请参阅什么是 [Azure 信息保护统一标签扫描程序？](/azure/information-protection/deploy-aip-scanner) 以及仅使用 [PowerShell 管理内容扫描作业](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。</span><span class="sxs-lookup"><span data-stu-id="0c9e2-204">For more information, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner) and [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>
