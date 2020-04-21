---
title: 由世纪互联运营的 Office 365
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- MET150
- GEU150
- GEA150
description: 了解有关由世纪互联运营的 Office 365 的 Azure 信息保护以及如何为中国的客户配置它的详细信息。
monikerRange: o365-21vianet
ms.openlocfilehash: 3d24b450cc9ba9a6427732d408e35af1394b4a34
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627650"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a><span data-ttu-id="1a9db-103">由世纪互联运营的 Office 365 的 Azure 信息保护与商业产品之间的奇偶校验</span><span class="sxs-lookup"><span data-stu-id="1a9db-103">Parity between Azure Information Protection for Office 365 operated by 21Vianet and commercial offerings</span></span>

<span data-ttu-id="1a9db-104">虽然我们的目标是使用由世纪互联运营的 Office 365 的 Azure 信息保护为中国的客户提供所有商业特性和功能，但我们仍需要突出显示一些缺少的功能。</span><span class="sxs-lookup"><span data-stu-id="1a9db-104">While our goal is to deliver all commercial features and functionality to customers in China with our Azure Information Protection for Office 365 operated by 21Vianet offer, there is some missing functionality that we'd like to highlight.</span></span>

<span data-ttu-id="1a9db-105">这些是由世纪互联运营的 Office 365 的 Azure 信息保护与年7月2019的商业产品的现有差距：</span><span class="sxs-lookup"><span data-stu-id="1a9db-105">These are the existing gaps between Azure Information Protection for Office 365 operated by 21Vianet and our commercial offerings as of July 2019:</span></span>

- <span data-ttu-id="1a9db-106">仅适用于企业版（内部版本11731.10000 或更高版本）的 Microsoft 365 应用程序支持信息权限管理（IRM）。</span><span class="sxs-lookup"><span data-stu-id="1a9db-106">Information Rights Management (IRM) is supported only for Microsoft 365 Apps for enterprise (build 11731.10000 or higher).</span></span> <span data-ttu-id="1a9db-107">Office 2010、Office 2013 和其他 Office 2016 版本不受支持。</span><span class="sxs-lookup"><span data-stu-id="1a9db-107">Office 2010, Office 2013, and other Office 2016 versions are not supported.</span></span>

- <span data-ttu-id="1a9db-108">从 Active Directory 权限管理服务（AD RMS）到 Azure 信息保护的迁移目前不可用。</span><span class="sxs-lookup"><span data-stu-id="1a9db-108">Migration from Active Directory Rights Management Services (AD RMS) to Azure Information Protection is currently not available.</span></span>
  
- <span data-ttu-id="1a9db-109">支持将受保护的电子邮件共享到商业云中的用户。</span><span class="sxs-lookup"><span data-stu-id="1a9db-109">Sharing of protected emails to users in the commercial cloud is supported.</span></span>
  
- <span data-ttu-id="1a9db-110">商业云中用户的文档和电子邮件附件共享目前不可用。</span><span class="sxs-lookup"><span data-stu-id="1a9db-110">Sharing of documents and email attachments to users in the commercial cloud is currently not available.</span></span> <span data-ttu-id="1a9db-111">这包括由商业云中由世纪互联用户运营的 Office 365、商业云中由世纪互联用户运营的非 Office 365 以及拥有 RMS for 个人许可证的用户。</span><span class="sxs-lookup"><span data-stu-id="1a9db-111">This includes Office 365 operated by 21Vianet users in the commercial cloud, non-Office 365 operated by 21Vianet users in the commercial cloud, and users with an RMS for Individuals license.</span></span>
  
- <span data-ttu-id="1a9db-112">具有 SharePoint 的 IRM （受 IRM 保护的网站和库）当前不可用。</span><span class="sxs-lookup"><span data-stu-id="1a9db-112">IRM with SharePoint (IRM-protected sites and libraries) is currently not available.</span></span>
  
- <span data-ttu-id="1a9db-113">权限管理连接器当前不可用。</span><span class="sxs-lookup"><span data-stu-id="1a9db-113">The Rights Management Connector is currently not available.</span></span>
  
- <span data-ttu-id="1a9db-114">AD RMS 的移动设备扩展目前不可用。</span><span class="sxs-lookup"><span data-stu-id="1a9db-114">The Mobile Device Extension for AD RMS is currently not available.</span></span>

## <a name="configuring-azure-information-protection-for-customers-in-china"></a><span data-ttu-id="1a9db-115">为中国的客户配置 Azure 信息保护</span><span class="sxs-lookup"><span data-stu-id="1a9db-115">Configuring Azure Information Protection for customers in China</span></span>

### <a name="enable-rights-management-for-the-tenant"></a><span data-ttu-id="1a9db-116">为租户启用权限管理</span><span class="sxs-lookup"><span data-stu-id="1a9db-116">Enable Rights Management for the tenant</span></span>

<span data-ttu-id="1a9db-117">为使加密正常工作，必须为租户启用 RMS。</span><span class="sxs-lookup"><span data-stu-id="1a9db-117">For the encryption to work correctly, the RMS must be enabled for the tenant.</span></span>

- <span data-ttu-id="1a9db-118">检查是否已启用 RMS：</span><span class="sxs-lookup"><span data-stu-id="1a9db-118">Check if the RMS is enabled:</span></span>
  1. <span data-ttu-id="1a9db-119">以管理员身份启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1a9db-119">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="1a9db-120">如果未安装 AIPService 模块，请运行 `Install-Module AipService`。</span><span class="sxs-lookup"><span data-stu-id="1a9db-120">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="1a9db-121">使用`Import-Module AipService`导入模块。</span><span class="sxs-lookup"><span data-stu-id="1a9db-121">Import the module using `Import-Module AipService`.</span></span>
  4. <span data-ttu-id="1a9db-122">使用 `Connect-AipService -environmentname azurechinacloud`连接到服务。</span><span class="sxs-lookup"><span data-stu-id="1a9db-122">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  5. <span data-ttu-id="1a9db-123">运行 `(Get-AipServiceConfiguration).FunctionalState` 并检查状态是否为 `Enabled`。</span><span class="sxs-lookup"><span data-stu-id="1a9db-123">Run `(Get-AipServiceConfiguration).FunctionalState` and check if the state is `Enabled`.</span></span>

- <span data-ttu-id="1a9db-124">如果功能状态为 `Disabled`，则运行 `Enable-AipService`。</span><span class="sxs-lookup"><span data-stu-id="1a9db-124">If the functional state is `Disabled`, run `Enable-AipService`.</span></span>

### <a name="dns-configuration-for-encryption-windows"></a><span data-ttu-id="1a9db-125">用于加密的 DNS 配置（Windows）</span><span class="sxs-lookup"><span data-stu-id="1a9db-125">DNS configuration for encryption (Windows)</span></span>

<span data-ttu-id="1a9db-126">若要使加密正常工作，Office 客户端应用程序必须连接到服务的中国实例，并从那里启动引导。</span><span class="sxs-lookup"><span data-stu-id="1a9db-126">For encryption to work correctly, Office client applications must connect to the China instance of the service and bootstrap from there.</span></span> <span data-ttu-id="1a9db-127">若要将客户端应用程序重定向到正确的服务实例，租户管理员必须使用有关 Azure RMS URL 的信息配置 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="1a9db-127">To redirect client applications to the right service instance, the tenant admin must configure a DNS SRV record with information about the Azure RMS URL.</span></span> <span data-ttu-id="1a9db-128">如果没有 DNS SRV 记录，客户端应用程序将在默认情况下尝试连接到公共云实例，并将失败。</span><span class="sxs-lookup"><span data-stu-id="1a9db-128">Without the DNS SRV record, the client application will attempt to connect to the public cloud instance by default and will fail.</span></span>

<span data-ttu-id="1a9db-129">此外，假定用户将使用基于租户拥有的域的用户名登录（例如， `joe@contoso.cn`），而不是`onmschina`用户名（例如， `joe@contoso.onmschina.cn`）。</span><span class="sxs-lookup"><span data-stu-id="1a9db-129">Also, the assumption is that users will log in with a username based off the tenant-owned domain (for example, `joe@contoso.cn`), and not the `onmschina` username (for example, `joe@contoso.onmschina.cn`).</span></span> <span data-ttu-id="1a9db-130">用户名中的域名用于将 DNS 重定向到正确的服务实例。</span><span class="sxs-lookup"><span data-stu-id="1a9db-130">The domain name from the username is used for DNS redirection to the correct service instance.</span></span>

- <span data-ttu-id="1a9db-131">获取 RMS ID：</span><span class="sxs-lookup"><span data-stu-id="1a9db-131">Get the RMS ID:</span></span>
  1. <span data-ttu-id="1a9db-132">以管理员身份启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1a9db-132">Launch PowerShell as an administrator.</span></span>
  2. <span data-ttu-id="1a9db-133">如果未安装 AIPService 模块，请运行 `Install-Module AipService`。</span><span class="sxs-lookup"><span data-stu-id="1a9db-133">If the AIPService module is not installed, run `Install-Module AipService`.</span></span>
  3. <span data-ttu-id="1a9db-134">使用 `Connect-AipService -environmentname azurechinacloud`连接到服务。</span><span class="sxs-lookup"><span data-stu-id="1a9db-134">Connect to the service using `Connect-AipService -environmentname azurechinacloud`.</span></span>
  4. <span data-ttu-id="1a9db-135">运行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 以获取 RMS ID。</span><span class="sxs-lookup"><span data-stu-id="1a9db-135">Run `(Get-AipServiceConfiguration).RightsManagementServiceId` to get the RMS ID.</span></span>

- <span data-ttu-id="1a9db-136">登录到您的 DNS 提供商，导航到域的 DNS 设置，然后添加新的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="1a9db-136">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="1a9db-137">服务 = `_rmsredir`</span><span class="sxs-lookup"><span data-stu-id="1a9db-137">Service = `_rmsredir`</span></span>
  - <span data-ttu-id="1a9db-138">协议 = `_http`</span><span class="sxs-lookup"><span data-stu-id="1a9db-138">Protocol = `_http`</span></span>
  - <span data-ttu-id="1a9db-139">名称 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="1a9db-139">Name = `_tcp`</span></span>
  - <span data-ttu-id="1a9db-140">Target = `[GUID].rms.aadrm.cn` （其中 GUID 是 RMS ID）</span><span class="sxs-lookup"><span data-stu-id="1a9db-140">Target = `[GUID].rms.aadrm.cn` (where GUID is the RMS ID)</span></span>
  - <span data-ttu-id="1a9db-141">优先级、权重、秒、TTL = 默认值</span><span class="sxs-lookup"><span data-stu-id="1a9db-141">Priority, Weight, Seconds, TTL = default values</span></span>

- <span data-ttu-id="1a9db-142">将自定义域与 [Azure 门户](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)中的租户相关联。</span><span class="sxs-lookup"><span data-stu-id="1a9db-142">Associate the custom domain with the tenant in the [Azure portal](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains).</span></span> <span data-ttu-id="1a9db-143">这将在 DNS 中添加一个条目，在将值添加到 DNS 设置后，可能需要几分钟的时间来进行验证。</span><span class="sxs-lookup"><span data-stu-id="1a9db-143">This will add an entry in DNS, which might take several minutes to get verified after you add the value to the DNS settings.</span></span>

- <span data-ttu-id="1a9db-144">使用相应的全局管理员凭据登录到 Microsoft 365 管理中心，并添加域（例如， `contoso.cn`）以供用户创建。</span><span class="sxs-lookup"><span data-stu-id="1a9db-144">Log in to the Microsoft 365 admin center with the corresponding global admin credentials and add the domain (for example, `contoso.cn`) for user creation.</span></span> <span data-ttu-id="1a9db-145">在验证过程中，可能需要进行其他 DNS 更改。</span><span class="sxs-lookup"><span data-stu-id="1a9db-145">In the verification process, additional DNS changes might be required.</span></span> <span data-ttu-id="1a9db-146">验证完成后，可以创建用户。</span><span class="sxs-lookup"><span data-stu-id="1a9db-146">Once verification is done, users can be created.</span></span>

### <a name="dns-configuration-for-encryption-mac-ios-android"></a><span data-ttu-id="1a9db-147">用于加密的 DNS 配置（Mac、iOS、Android）</span><span class="sxs-lookup"><span data-stu-id="1a9db-147">DNS configuration for encryption (Mac, iOS, Android)</span></span>

- <span data-ttu-id="1a9db-148">登录到您的 DNS 提供商，导航到域的 DNS 设置，然后添加新的 SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="1a9db-148">Log in to your DNS provider, navigate to the DNS settings for the domain, and then add a new SRV record.</span></span>
  - <span data-ttu-id="1a9db-149">服务 = `_rmsdisco`</span><span class="sxs-lookup"><span data-stu-id="1a9db-149">Service = `_rmsdisco`</span></span>
  - <span data-ttu-id="1a9db-150">协议 = `_http`</span><span class="sxs-lookup"><span data-stu-id="1a9db-150">Protocol = `_http`</span></span>
  - <span data-ttu-id="1a9db-151">名称 = `_tcp`</span><span class="sxs-lookup"><span data-stu-id="1a9db-151">Name = `_tcp`</span></span>
  - <span data-ttu-id="1a9db-152">目标 = `api.aadrm.cn`</span><span class="sxs-lookup"><span data-stu-id="1a9db-152">Target = `api.aadrm.cn`</span></span>
  - <span data-ttu-id="1a9db-153">端口 = `80`</span><span class="sxs-lookup"><span data-stu-id="1a9db-153">Port = `80`</span></span>
  - <span data-ttu-id="1a9db-154">优先级、权重、秒、TTL = 默认值</span><span class="sxs-lookup"><span data-stu-id="1a9db-154">Priority, Weight, Seconds, TTL = default values</span></span>
