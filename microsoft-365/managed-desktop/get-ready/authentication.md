---
title: 为 Microsoft 托管桌面准备本地资源访问权限
description: 确保 Azure AD 可以与本地 AD 进行通信以提供身份验证的重要步骤
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 6df23e0d7e3ea0ecd7ebacd96f00cb47b9e0aa84
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574591"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a><span data-ttu-id="98dff-104">为 Microsoft 托管桌面准备本地资源访问权限</span><span class="sxs-lookup"><span data-stu-id="98dff-104">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>

<span data-ttu-id="98dff-105">在 Microsoft 托管桌面中，设备会自动加入到 Azure AD (Azure Active Directory) 。</span><span class="sxs-lookup"><span data-stu-id="98dff-105">In Microsoft Managed Desktop, devices are automatically joined to Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="98dff-106">因此，如果你使用的是本地 Active Directory，必须检查一些内容，以确保加入 Azure AD 的设备可以与本地 Active Directory 通信。</span><span class="sxs-lookup"><span data-stu-id="98dff-106">For this reason, if you are using an on-premises Active Directory, you'll have to check some things to ensure that devices joined to Azure AD can communicate with your on-premises Active Directory.</span></span> 

> [!NOTE]  
> <span data-ttu-id="98dff-107">*混合* Microsoft 托管桌面不支持加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="98dff-107">*Hybrid* Azure AD join is not supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="98dff-108">Azure Active Directory 允许你的用户利用单一 Sign-On (SSO) ，这意味着他们通常不需要每次使用资源时都提供凭据。</span><span class="sxs-lookup"><span data-stu-id="98dff-108">Azure Active Directory lets your users take advantage of Single Sign-On (SSO), which means they typically won't have to provide credentials every time they use resources.</span></span>

<span data-ttu-id="98dff-109">有关加入 Azure Active Directory 的信息，请参阅 [如何：规划 Azure AD 加入实现](/azure/active-directory/devices/azureadjoin-plan)。</span><span class="sxs-lookup"><span data-stu-id="98dff-109">For information about joining Azure Active Directory, refer to [How to: Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan).</span></span> <span data-ttu-id="98dff-110">有关加入 Azure AD 的Sign-On (SSO) ，请参阅 SSO 到本地资源在 [加入 Azure AD](/azure/active-directory/devices/azuread-join-sso#how-it-works)的设备上的工作原理。</span><span class="sxs-lookup"><span data-stu-id="98dff-110">For background information about Single Sign-On (SSO) on devices joined to Azure AD, see [How SSO to on-premises resources works on Azure AD joined devices](/azure/active-directory/devices/azuread-join-sso#how-it-works).</span></span>


<span data-ttu-id="98dff-111">本文介绍了需要检查哪些内容，以确保依赖于本地 Active Directory 连接的应用和其他资源能够顺利使用 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="98dff-111">This article explains the things you need to check in order to ensure that apps and other resources that depend on local Active Directory connectivity will work smoothly with Microsoft Managed Desktop.</span></span>


## <a name="single-sign-on-for-on-premises-resources"></a><span data-ttu-id="98dff-112">用于Sign-On资源的单个资源</span><span class="sxs-lookup"><span data-stu-id="98dff-112">Single Sign-On for on-premises resources</span></span>

<span data-ttu-id="98dff-113">默认情况下Sign-On (Microsoft 托管桌面) 启用使用 UPN 和密码的单一 SSO 设置。</span><span class="sxs-lookup"><span data-stu-id="98dff-113">Single Sign-On (SSO) by using UPN and password is enabled by default on Microsoft Managed Desktop Devices.</span></span> <span data-ttu-id="98dff-114">但是，你的用户也可以使用 Windows Hello 企业应用，这需要一些额外的设置步骤。</span><span class="sxs-lookup"><span data-stu-id="98dff-114">But your users can also use Windows Hello for Business, which requires some extra setup steps.</span></span> 

### <a name="single-sign-on-by-using-upn-and-password"></a><span data-ttu-id="98dff-115">单Sign-On UPN 和密码进行加密</span><span class="sxs-lookup"><span data-stu-id="98dff-115">Single Sign-On by using UPN and password</span></span>

<span data-ttu-id="98dff-116">在大多数组织中，用户将能够使用 SSO 通过 UPN 进行身份验证，并使用 Microsoft 托管桌面设备上的密码进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="98dff-116">In most organizations, your users will be able to use SSO to authenticate by UPN and password on Microsoft Managed Desktop Devices.</span></span> <span data-ttu-id="98dff-117">但是，若要确保此函数正常工作，应仔细检查以下内容：</span><span class="sxs-lookup"><span data-stu-id="98dff-117">However, to make sure this function will work, you should double-check the following things:</span></span>

- <span data-ttu-id="98dff-118">确认已设置 Azure AD Connect 并使用运行 Windows Server 2008 R2 或更高版本的本地 Active Directory 服务器。</span><span class="sxs-lookup"><span data-stu-id="98dff-118">Confirm that Azure AD Connect is set up and uses an on-premises Active Directory server running Windows Server 2008 R2 or later.</span></span>
- <span data-ttu-id="98dff-119">确认 Azure AD Connect 正在运行受支持的版本，并设置为与 Azure AD 同步这三个属性：</span><span class="sxs-lookup"><span data-stu-id="98dff-119">Confirm that Azure AD Connect is running a supported version and is set to sync these three attributes with Azure AD:</span></span> 
    - <span data-ttu-id="98dff-120">用户所在的本地 Active Directory (DNS 域名) </span><span class="sxs-lookup"><span data-stu-id="98dff-120">DNS domain name of the on-premises Active Directory (where the users are located)</span></span>
    - <span data-ttu-id="98dff-121">用户所在的本地 Active Directory (的 NetBIOS) </span><span class="sxs-lookup"><span data-stu-id="98dff-121">NetBIOS of your on-premises Active Directory (where the users are located)</span></span>
    - <span data-ttu-id="98dff-122">用户的 SAM 帐户名</span><span class="sxs-lookup"><span data-stu-id="98dff-122">SAM account name of the user</span></span>


### <a name="single-sign-on-by-using-windows-hello-for-business"></a><span data-ttu-id="98dff-123">使用 windows hello 企业Sign-On单一应用</span><span class="sxs-lookup"><span data-stu-id="98dff-123">Single Sign-On by using Windows Hello for Business</span></span>

<span data-ttu-id="98dff-124">Microsoft 托管桌面设备还通过使用 Windows Hello 企业版为用户提供快速、无密码的体验。</span><span class="sxs-lookup"><span data-stu-id="98dff-124">Microsoft Managed Desktop devices also offer your users a fast, passwordless experience by employing Windows Hello for Business.</span></span> <span data-ttu-id="98dff-125">若要确保 Windows Hello 企业版本在用户无需提供各自的 UPN 和密码的情况下工作，请访问为本地 Single-Sign 配置 [加入 Azure AD](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) 的设备。使用 Windows Hello 企业版本检查要求，然后按照那里提供的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="98dff-125">To ensure Windows Hello for Business will work without your users having to provide respective UPN and password, visit [Configure Azure AD joined devices for On-premises Single-Sign On using Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) to check the requirements, and then follow the steps provided there.</span></span>


## <a name="apps-and-resources-that-use-authentication"></a><span data-ttu-id="98dff-126">使用身份验证的应用和资源</span><span class="sxs-lookup"><span data-stu-id="98dff-126">Apps and resources that use authentication</span></span>

<span data-ttu-id="98dff-127">有关 [设置应用以使用](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) Azure Active Directory 的完整指南，请参阅了解 Azure 内容集内应用程序和资源注意事项。</span><span class="sxs-lookup"><span data-stu-id="98dff-127">Refer to [Understand considerations for applications and resources](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in the Azure content set for full guidance on setting up apps to work with Azure Active Directory.</span></span> <span data-ttu-id="98dff-128">摘要：</span><span class="sxs-lookup"><span data-stu-id="98dff-128">In summary:</span></span>


- <span data-ttu-id="98dff-129">如果你使用 **基于云的应用**（例如添加到 Azure AD 应用库的应用），则大多数应用无需进一步准备，以使用 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="98dff-129">If you use **cloud-based apps**, such as those added to the Azure AD app gallery, most don't require any further preparation to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="98dff-130">但是，任何不使用 Web 帐户管理器或 WAM (Win32) 可能仍提示用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="98dff-130">However, any Win32 apps that don't use Web Account Manager (WAM) might still prompt users for authentication.</span></span>

- <span data-ttu-id="98dff-131">对于在本地 **托管的应用，** 请确保将这些应用添加到浏览器的受信任站点列表。</span><span class="sxs-lookup"><span data-stu-id="98dff-131">For apps that are **hosted on-premises**, be sure to add those apps to the trusted sites list in your browsers.</span></span> <span data-ttu-id="98dff-132">此步骤将使 Windows 身份验证无缝工作，而不会提示用户提供凭据。</span><span class="sxs-lookup"><span data-stu-id="98dff-132">This step will enable Windows authentication to work seamlessly, without users being prompted for credentials.</span></span> <span data-ttu-id="98dff-133">若要添加应用，请参阅可 [配置设置](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) 参考 [中的受信任的站点](../working-with-managed-desktop/config-setting-ref.md)。</span><span class="sxs-lookup"><span data-stu-id="98dff-133">To add apps, refer to [Trusted sites](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) in the [Configurable settings reference](../working-with-managed-desktop/config-setting-ref.md).</span></span>

- <span data-ttu-id="98dff-134">如果使用的是 Active Directory 联合服务，则使用使用 AD FS 验证和管理单一登录中的步骤检查 [SSO 是否已启用](/previous-versions/azure/azure-services/jj151809(v=azure.100))。</span><span class="sxs-lookup"><span data-stu-id="98dff-134">If you are using Active Directory Federated Services, check that SSO is enabled by using the steps in [Verify and manage single sign-on with AD FS](/previous-versions/azure/azure-services/jj151809(v=azure.100)).</span></span> 

- <span data-ttu-id="98dff-135">对于 **本地和使用旧** 协议的应用，无需额外设置，只要设备有权访问本地域控制器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="98dff-135">For apps that are **on-premises and use older protocols**, no extra setup is required, as long as the devices have access to an on-premises domain controller to authenticate.</span></span> <span data-ttu-id="98dff-136">但是，若要为这些应用程序提供安全访问，应部署 Azure AD 应用程序代理。</span><span class="sxs-lookup"><span data-stu-id="98dff-136">To provide secure access for these applications, however, you should deploy Azure AD Application Proxy.</span></span> <span data-ttu-id="98dff-137">有关详细信息，请参阅通过 [Azure Active Directory](/azure/active-directory/manage-apps/application-proxy)的应用程序代理远程访问本地应用程序。</span><span class="sxs-lookup"><span data-stu-id="98dff-137">For more information, see [Remote access to on-premises applications through Azure Active Directory's Application Proxy](/azure/active-directory/manage-apps/application-proxy).</span></span>

- <span data-ttu-id="98dff-138">不支持 **在本地运行并依赖** 计算机身份验证的应用，因此应考虑将它们替换为较新版本。</span><span class="sxs-lookup"><span data-stu-id="98dff-138">Apps that run **on-premises and rely on machine authentication** aren't supported, so you should consider replacing them with newer versions.</span></span>

### <a name="network-shares-that-use-authentication"></a><span data-ttu-id="98dff-139">使用身份验证的网络共享</span><span class="sxs-lookup"><span data-stu-id="98dff-139">Network shares that use authentication</span></span>

<span data-ttu-id="98dff-140">只要设备能够使用 UNC 路径访问本地域控制器，用户就无需进行额外的设置，即访问网络共享。</span><span class="sxs-lookup"><span data-stu-id="98dff-140">No extra setup is required for users to access network shares, as long as the devices have access to an on-premises domain controller by using a UNC path.</span></span>

### <a name="printers"></a><span data-ttu-id="98dff-141">打印机</span><span class="sxs-lookup"><span data-stu-id="98dff-141">Printers</span></span>

<span data-ttu-id="98dff-142">Microsoft 托管桌面设备无法连接到发布到本地 Active Directory 的打印机，除非已配置 [混合云打印](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。</span><span class="sxs-lookup"><span data-stu-id="98dff-142">Microsoft Managed Desktop devices cannot connect to printers that are published to your on-premises Active Directory unless you have configured [Hybrid Cloud Print](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>

<span data-ttu-id="98dff-143">虽然无法自动在仅云环境中发现打印机，但只要设备可以访问本地域控制器，用户就可以使用打印机路径或打印机队列路径来使用本地打印机。</span><span class="sxs-lookup"><span data-stu-id="98dff-143">While printers can't be automatically discovered in a cloud only environment, your users can use on-premises printers by using the printer path or printer queue path, as long as the devices have access to an on-premises domain controller.</span></span>

<!--add fuller material on printers when available-->
## <a name="steps-to-get-ready"></a><span data-ttu-id="98dff-144">准备步骤</span><span class="sxs-lookup"><span data-stu-id="98dff-144">Steps to get ready</span></span>

1. <span data-ttu-id="98dff-145">查看 [Microsoft 托管桌面的先决条件](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="98dff-145">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="98dff-146">使用 [准备情况评估工具](readiness-assessment-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="98dff-146">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="98dff-147">来宾帐户的先决条件</span><span class="sxs-lookup"><span data-stu-id="98dff-147">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="98dff-148">Microsoft 托管桌面的网络配置</span><span class="sxs-lookup"><span data-stu-id="98dff-148">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="98dff-149">为 Microsoft 托管桌面准备证书和网络配置文件</span><span class="sxs-lookup"><span data-stu-id="98dff-149">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. <span data-ttu-id="98dff-150">[Prepare on-premises resources access for Microsoft Managed Desktop](authentication.md) (This article) </span><span class="sxs-lookup"><span data-stu-id="98dff-150">[Prepare on-premises resources access for Microsoft Managed Desktop](authentication.md) (This article)</span></span>
7. [<span data-ttu-id="98dff-151">Microsoft 托管桌面中的应用</span><span class="sxs-lookup"><span data-stu-id="98dff-151">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="98dff-152">为 Microsoft 托管桌面准备映射的驱动器</span><span class="sxs-lookup"><span data-stu-id="98dff-152">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="98dff-153">为 Microsoft 托管桌面准备打印资源</span><span class="sxs-lookup"><span data-stu-id="98dff-153">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
