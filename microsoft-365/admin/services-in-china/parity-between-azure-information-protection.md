---
title: 由世纪银行运营的 Office 365 的 Azure 信息保护和商业产品/服务之间的奇偶校验
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
ms.reviewer: arthurj
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
ms.openlocfilehash: 50269749b5f4e544263f790ec9c7e4474af57219
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840297"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="2a70a-103">由世纪银行运营的 Office 365 的 Azure 信息保护和商业产品/服务之间的奇偶校验</span><span class="sxs-lookup"><span data-stu-id="2a70a-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="2a70a-104">虽然我们的目标是通过由世纪版运营的 Office 365 的 Azure 信息保护 (AIP) 产品/服务，为中国客户提供所有商业特性和功能，但我们希望重点介绍一些缺少的功能。</span><span class="sxs-lookup"><span data-stu-id="2a70a-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection (AIP) for Office 365 operated by 21Vianet offer, there's some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="2a70a-105">以下列表包括由世纪银行运营的 Office 365 的 Azure 信息保护与自 2021 年 1 月开始的商业产品/服务之间的现有差异：</span><span class="sxs-lookup"><span data-stu-id="2a70a-105">The following list includes the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of January 2021:</span></span>

- <span data-ttu-id="2a70a-106">信息权限 (IRM) 仅适用于 Microsoft 365 企业应用版 (版本 11731.10000 或更高版本) 。</span><span class="sxs-lookup"><span data-stu-id="2a70a-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="2a70a-107">不支持 Office 2010、Office 2013 和其他 Office 2016 版本。</span><span class="sxs-lookup"><span data-stu-id="2a70a-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="2a70a-108">目前Active Directory Rights Management Services (AD RMS) 迁移到 Azure 信息保护。</span><span class="sxs-lookup"><span data-stu-id="2a70a-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="2a70a-109">支持在商业云中向用户共享受保护的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2a70a-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="2a70a-110">目前，无法向商业云中的用户共享文档和电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="2a70a-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="2a70a-111">这包括由商业云中的世纪版用户运营的 Office 365、由商业云中的世纪银行运营的非 Office 365 用户和拥有 RMS 个人版许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="2a70a-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="2a70a-112">SharePoint 的 IRM (受 IRM 保护的网站和) 目前不可用。</span><span class="sxs-lookup"><span data-stu-id="2a70a-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="2a70a-113">AD RMS 的移动设备扩展当前不可用。</span><span class="sxs-lookup"><span data-stu-id="2a70a-113">The Mobile Device Extension for AD RMS is currently not available.</span></span>

- <span data-ttu-id="2a70a-114">Azure [China](/azure/information-protection/rms-client/mobile-app-faq) 21Vianet 不支持移动查看器。</span><span class="sxs-lookup"><span data-stu-id="2a70a-114">The [Mobile Viewer](/azure/information-protection/rms-client/mobile-app-faq) is not supported by Azure China 21Vianet.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="2a70a-115">为中国客户配置 Azure 信息保护</span><span class="sxs-lookup"><span data-stu-id="2a70a-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="2a70a-116">为租户启用权限管理</span><span class="sxs-lookup"><span data-stu-id="2a70a-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="2a70a-117">若要使加密正常工作，必须为租户启用 RMS。</span><span class="sxs-lookup"><span data-stu-id="2a70a-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="2a70a-118">检查 RMS 是否已启用：</span><span class="sxs-lookup"><span data-stu-id="2a70a-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="2a70a-119">以管理员角色启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2a70a-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="2a70a-120">如果未安装 AIPService 模块，请运行 `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="2a70a-120">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="2a70a-121">使用 导入模块 `Import-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="2a70a-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="2a70a-122">使用 连接到服务 `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="2a70a-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="2a70a-123">运行 `(Get-AipServiceConfiguration).FunctionalState` 并检查状态是否 `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="2a70a-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="2a70a-124">如果功能状态为 `Disabled` ，则运行 `Enable-AipService` 。</span><span class="sxs-lookup"><span data-stu-id="2a70a-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="2a70a-125">Windows (加密的 DNS) </span><span class="sxs-lookup"><span data-stu-id="2a70a-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="2a70a-126">若要使加密正常工作，Office 客户端应用程序必须连接到服务的中国实例，然后从该实例启动。</span><span class="sxs-lookup"><span data-stu-id="2a70a-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="2a70a-127">若要将客户端应用程序重定向到正确的服务实例，租户管理员必须使用有关 Azure RMS URL 的信息配置 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="2a70a-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="2a70a-128">如果没有 DNS SRV 记录，客户端应用程序将默认尝试连接到公共云实例，并且将失败。</span><span class="sxs-lookup"><span data-stu-id="2a70a-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="2a70a-129">此外，假定用户使用基于租户拥有域的用户名登录 (例如，) ，而不是用户名 (`joe@contoso.cn` `onmschina` 例如 `joe@contoso.onmschina.cn` ，) 。</span><span class="sxs-lookup"><span data-stu-id="2a70a-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="2a70a-130">用户名中的域名用于将 DNS 重定向到正确的服务实例。</span><span class="sxs-lookup"><span data-stu-id="2a70a-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="2a70a-131">获取 RMS ID：</span><span class="sxs-lookup"><span data-stu-id="2a70a-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="2a70a-132">以管理员角色启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2a70a-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="2a70a-133">如果未安装 AIPService 模块，请运行 `Install-Module AipService` 。</span><span class="sxs-lookup"><span data-stu-id="2a70a-133">If the AIPService module isn't installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="2a70a-134">使用 连接到服务 `Connect-AipService -environmentname azurechinacloud` 。</span><span class="sxs-lookup"><span data-stu-id="2a70a-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="2a70a-135">运行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 以获取 RMS ID。</span><span class="sxs-lookup"><span data-stu-id="2a70a-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="2a70a-136">登录到 DNS 提供程序，导航到域的 DNS 设置，然后添加新的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="2a70a-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="2a70a-137">服务 = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="2a70a-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="2a70a-138">协议 = `_http`</span><span class="sxs-lookup"><span data-stu-id="2a70a-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="2a70a-139">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="2a70a-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="2a70a-140">目标 = `[GUID].rms.aadrm.cn` (GUID 是 RMS ID) </span><span class="sxs-lookup"><span data-stu-id="2a70a-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="2a70a-141">Priority、Weight、Seconds、TTL = 默认值</span><span class="sxs-lookup"><span data-stu-id="2a70a-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="2a70a-142">将自定义域与 Azure 门户中的 [租户关联](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)。</span><span class="sxs-lookup"><span data-stu-id="2a70a-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="2a70a-143">这会在 DNS 中添加条目，在将值添加到 DNS 设置后，可能需要几分钟时间才能进行验证。</span><span class="sxs-lookup"><span data-stu-id="2a70a-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="2a70a-144">使用相应的全局管理员凭据登录到 Microsoft 365 管理中心，并添加域 (例如，) `contoso.cn` 用户创建。</span><span class="sxs-lookup"><span data-stu-id="2a70a-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="2a70a-145">在验证过程中，可能需要进行其他 DNS 更改。</span><span class="sxs-lookup"><span data-stu-id="2a70a-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="2a70a-146">验证完成后，可创建用户。</span><span class="sxs-lookup"><span data-stu-id="2a70a-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="2a70a-147">用于加密的 DNS (Mac、iOS、Android) </span><span class="sxs-lookup"><span data-stu-id="2a70a-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

<span data-ttu-id="2a70a-148">登录到 DNS 提供程序，导航到域的 DNS 设置，然后添加新的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="2a70a-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>

- <span data-ttu-id="2a70a-149">服务 = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="2a70a-149">Service = `_rmsdisco`</span></span>
- <span data-ttu-id="2a70a-150">协议 = `_http`</span><span class="sxs-lookup"><span data-stu-id="2a70a-150">Protocol = `_http`</span></span>
- <span data-ttu-id="2a70a-151">Name = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="2a70a-151">Name = `_tcp`</span></span>
- <span data-ttu-id="2a70a-152">目标 = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="2a70a-152">Target = `api.aadrm.cn`</span></span>
- <span data-ttu-id="2a70a-153">端口 = `80`</span><span class="sxs-lookup"><span data-stu-id="2a70a-153">Port = `80`</span></span>
- <span data-ttu-id="2a70a-154">Priority、Weight、Seconds、TTL = 默认值</span><span class="sxs-lookup"><span data-stu-id="2a70a-154">Priority, Weight, Seconds, TTL = default values</span></span>

### <a name="aip-client-configuration"></a><span data-ttu-id="2a70a-155">AIP 客户端配置</span><span class="sxs-lookup"><span data-stu-id="2a70a-155">AIP client configuration</span></span>

<span data-ttu-id="2a70a-156">可以从 Microsoft 下载中心下载统一的 AIP [客户端](https://www.microsoft.com/download/details.aspx?id=53018)。</span><span class="sxs-lookup"><span data-stu-id="2a70a-156">The unified AIP client can be downloaded from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

<span data-ttu-id="2a70a-157">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="2a70a-157">For more information, see:</span></span>

- [<span data-ttu-id="2a70a-158">Azure 信息保护文档</span><span class="sxs-lookup"><span data-stu-id="2a70a-158">Azure Information Protection documentation</span></span>](/azure/information-protection/)
- [<span data-ttu-id="2a70a-159">AIP 版本历史记录和支持策略</span><span class="sxs-lookup"><span data-stu-id="2a70a-159">AIP version history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [<span data-ttu-id="2a70a-160">AIP 系统要求</span><span class="sxs-lookup"><span data-stu-id="2a70a-160">AIP system requirements</span></span>](/azure/information-protection/requirements)
- [<span data-ttu-id="2a70a-161">AIP 快速入门：部署 AIP 客户端</span><span class="sxs-lookup"><span data-stu-id="2a70a-161">AIP quickstart: Deploy the AIP client</span></span>](/azure/information-protection/quickstart-deploy-client)
- [<span data-ttu-id="2a70a-162">AIP 管理员指南</span><span class="sxs-lookup"><span data-stu-id="2a70a-162">AIP administrator guide</span></span>](/azure/information-protection/rms-client/clientv2-admin-guide)
- [<span data-ttu-id="2a70a-163">AIP 用户指南</span><span class="sxs-lookup"><span data-stu-id="2a70a-163">AIP user guide</span></span>](/azure/information-protection/rms-client/clientv2-user-guide)
- [<span data-ttu-id="2a70a-164">了解 Microsoft 365 敏感度标签</span><span class="sxs-lookup"><span data-stu-id="2a70a-164">Learn about Microsoft 365 sensitivity labels</span></span>](/microsoft-365/compliance/sensitivity-labels)

### <a name="aip-apps-configuration-unified-labeling-client-only"></a><span data-ttu-id="2a70a-165">AIP 应用配置 (统一标记客户端) </span><span class="sxs-lookup"><span data-stu-id="2a70a-165">AIP apps configuration (unified labeling client only)</span></span>

<span data-ttu-id="2a70a-166">对于统一标记解决方案，Windows 上的 AIP 应用需要以下注册表项来将它们指向 Azure China 的正确主云：</span><span class="sxs-lookup"><span data-stu-id="2a70a-166">For the unified labeling solution, AIP apps on Windows need the following registry key to point them to the correct sovereign cloud for Azure China:</span></span>

- <span data-ttu-id="2a70a-167">注册表节点 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span><span class="sxs-lookup"><span data-stu-id="2a70a-167">Registry node = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`</span></span>
- <span data-ttu-id="2a70a-168">Name = `CloudEnvType`</span><span class="sxs-lookup"><span data-stu-id="2a70a-168">Name = `CloudEnvType`</span></span>
- <span data-ttu-id="2a70a-169">值 = `6` (默认值 = 0) </span><span class="sxs-lookup"><span data-stu-id="2a70a-169">Value = `6` (default = 0)</span></span>
- <span data-ttu-id="2a70a-170">Type = `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="2a70a-170">Type = `REG_DWORD`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a70a-171">确保在卸载后不删除注册表项。</span><span class="sxs-lookup"><span data-stu-id="2a70a-171">Make sure you don't delete the registry key after an uninstall.</span></span> <span data-ttu-id="2a70a-172">如果密钥为空、不正确或不存在，则该功能的行为将为默认值 (默认值 = 0，用于商业云) 。</span><span class="sxs-lookup"><span data-stu-id="2a70a-172">If the key is empty, incorrect, or non-existent, the functionality will behave as the default value (default value = 0 for the commercial cloud).</span></span> <span data-ttu-id="2a70a-173">如果键为空或不正确，也会向日志中添加打印错误。</span><span class="sxs-lookup"><span data-stu-id="2a70a-173">If the key is empty or incorrect, a print error is also added to the log.</span></span>

### <a name="manage-azure-information-protection-content-scan-jobs"></a><span data-ttu-id="2a70a-174">管理 Azure 信息保护内容扫描作业</span><span class="sxs-lookup"><span data-stu-id="2a70a-174">Manage Azure Information Protection content scan jobs</span></span>

<span data-ttu-id="2a70a-175">若要使用 Azure 中国扫描程序服务器管理 Azure 信息保护内容扫描作业，请使用以下 cmdlet，而不是 Azure 门户：</span><span class="sxs-lookup"><span data-stu-id="2a70a-175">To manage your Azure Information Protection content scan jobs with an Azure China scanner server, use the following cmdlets instead of the Azure portal:</span></span><br><br>

| <span data-ttu-id="2a70a-176">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2a70a-176">Cmdlet</span></span> | <span data-ttu-id="2a70a-177">说明</span><span class="sxs-lookup"><span data-stu-id="2a70a-177">Description</span></span> |
|--|--|
| [<span data-ttu-id="2a70a-178">Add-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="2a70a-178">Add-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/add-aipscannerrepository) | <span data-ttu-id="2a70a-179">向内容扫描作业添加新存储库。</span><span class="sxs-lookup"><span data-stu-id="2a70a-179">Adds a new repository to your content scan job.</span></span> |
| [<span data-ttu-id="2a70a-180">Get-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="2a70a-180">Get-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | <span data-ttu-id="2a70a-181">获取有关内容扫描作业的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2a70a-181">Gets details about your content scan job.</span></span> |
| [<span data-ttu-id="2a70a-182">Get-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="2a70a-182">Get-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/get-aipscannerrepository) | <span data-ttu-id="2a70a-183">获取为内容扫描作业定义的存储库的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2a70a-183">Gets details about repositories defined for your content scan job.</span></span> |
| [<span data-ttu-id="2a70a-184">Remove-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="2a70a-184">Remove-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | <span data-ttu-id="2a70a-185">删除内容扫描作业。</span><span class="sxs-lookup"><span data-stu-id="2a70a-185">Deletes your content scan job.</span></span> |
| [<span data-ttu-id="2a70a-186">Remove-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="2a70a-186">Remove-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | <span data-ttu-id="2a70a-187">从内容扫描作业中删除存储库。</span><span class="sxs-lookup"><span data-stu-id="2a70a-187">Removes a repository from your content scan job.</span></span> |
| [<span data-ttu-id="2a70a-188">Set-AIPScannerContentScanJob</span><span class="sxs-lookup"><span data-stu-id="2a70a-188">Set-AIPScannerContentScanJob</span></span>](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | <span data-ttu-id="2a70a-189">定义内容扫描作业的设置。</span><span class="sxs-lookup"><span data-stu-id="2a70a-189">Defines settings for your content scan job.</span></span> |
| [<span data-ttu-id="2a70a-190">Set-AIPScannerRepository</span><span class="sxs-lookup"><span data-stu-id="2a70a-190">Set-AIPScannerRepository</span></span>](/powershell/module/azureinformationprotection/set-aipscannerrepository) | <span data-ttu-id="2a70a-191">定义内容扫描作业中现有存储库的设置。</span><span class="sxs-lookup"><span data-stu-id="2a70a-191">Defines settings for an existing repository in your content scan job.</span></span> |

<span data-ttu-id="2a70a-192">有关详细信息，请参阅 [仅使用 PowerShell 管理内容扫描作业](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。</span><span class="sxs-lookup"><span data-stu-id="2a70a-192">For more information, see [Manage your content scan jobs using PowerShell only](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).</span></span>