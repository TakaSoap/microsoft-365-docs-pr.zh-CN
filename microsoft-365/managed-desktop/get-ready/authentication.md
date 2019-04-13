---
title: 为 Microsoft 托管桌面准备本地资源访问
description: 确保 Azure AD 可以与本地 AD 通信以提供身份验证的重要步骤
keywords: microsoft 托管桌面, microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 2317a0581b356dadbde2042920ed2542f0e2203c
ms.sourcegitcommit: 392b906e64d27366b47931e8285b625e5e2f884e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2019
ms.locfileid: "31838163"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a><span data-ttu-id="b530e-104">为 Microsoft 托管桌面准备本地资源访问</span><span class="sxs-lookup"><span data-stu-id="b530e-104">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>

<span data-ttu-id="b530e-105">在 Microsoft 托管桌面中, 设备会自动加入 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="b530e-105">In Microsoft Managed Desktop, devices are automatically joined to Azure Active Directory.</span></span> <span data-ttu-id="b530e-106">这意味着, 如果您使用的是本地 active directory, 则必须检查一些事项, 以确保加入到 Azure AD 的设备可以与您的本地 active directory 进行通信。</span><span class="sxs-lookup"><span data-stu-id="b530e-106">This means that if you are using an on-premises Active Directory, you'll have to check some things to ensure that devices joined to Azure AD can communicate with your on-premises Active Directory.</span></span> 

> [!NOTE]  
> <span data-ttu-id="b530e-107">*混合*Microsoft 托管桌面不支持 Azure AD 加入。</span><span class="sxs-lookup"><span data-stu-id="b530e-107">*Hybrid* Azure AD join is not supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="b530e-108">通过 Azure Active Directory, 用户可以利用单一登录 (SSO), 这意味着在每次使用资源时, 他们通常不需要提供凭据。</span><span class="sxs-lookup"><span data-stu-id="b530e-108">Azure Active Directory lets your users take advantage of Single Sign-On (SSO), which means they typically won't have to provide credentials every time they use resources.</span></span>

<span data-ttu-id="b530e-109">有关加入 azure Active Directory 的信息, 请参阅 how [to: Plan a azure AD join 实现](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)。</span><span class="sxs-lookup"><span data-stu-id="b530e-109">For information about joining Azure Active Directory, refer to [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan).</span></span> <span data-ttu-id="b530e-110">有关加入到 azure ad 的设备上的单一登录 (sso) 的背景信息, 请参阅[本地资源的 SSO 在 Azure ad 联接设备上的工作原理](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)。</span><span class="sxs-lookup"><span data-stu-id="b530e-110">For background information about Single Sign-On (SSO) on devices joined to Azure AD, see [How SSO to on-premises resources works on Azure AD joined devices](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).</span></span>


<span data-ttu-id="b530e-111">本主题介绍要检查的内容, 以确保依赖于本地 Active Directory 连接的应用和其他资源将在 Microsoft 托管桌面中正常运行。</span><span class="sxs-lookup"><span data-stu-id="b530e-111">This topic explains the things you need to check in order to ensure that apps and other resources that depend on local Active Directory connectivity will work smoothly with Microsoft Managed Desktop.</span></span>


## <a name="single-sign-on-for-on-premises-resources"></a><span data-ttu-id="b530e-112">本地资源的单一登录</span><span class="sxs-lookup"><span data-stu-id="b530e-112">Single Sign-On for on-premises resources</span></span>

<span data-ttu-id="b530e-113">默认情况下, 使用 UPN 和密码的单一登录 (SSO) 在 Microsoft 托管桌面设备上启用。</span><span class="sxs-lookup"><span data-stu-id="b530e-113">Single Sign-On (SSO) by using UPN and passwords is enabled by default on Microsoft Managed Desktop Devices.</span></span> <span data-ttu-id="b530e-114">但您的用户也可以使用 Windows Hello 企业版, 这需要执行一些额外的设置步骤。</span><span class="sxs-lookup"><span data-stu-id="b530e-114">But your users can also use Windows Hello for Business, which requires some extra setup steps.</span></span> 

### <a name="single-sign-on-by-using-upn-and-passwords"></a><span data-ttu-id="b530e-115">使用 UPN 和密码的单一登录</span><span class="sxs-lookup"><span data-stu-id="b530e-115">Single Sign-On by using UPN and passwords</span></span>

<span data-ttu-id="b530e-116">在大多数组织中, 用户将能够使用 SSO 在 Microsoft 托管桌面设备上通过 UPN 和密码进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="b530e-116">In most organizations, your users will be able to use SSO to authenticate by UPN and password on Microsoft Managed Desktop Devices.</span></span> <span data-ttu-id="b530e-117">但是, 为了确保这能够正常运行, 应仔细检查以下各项:</span><span class="sxs-lookup"><span data-stu-id="b530e-117">However, to make sure this will work, you should double-check the following:</span></span>

- <span data-ttu-id="b530e-118">确认已设置 Azure Active directory (AAD) Connect 并使用运行 Windows server 2008 R2 或更高版本的本地 Active directory 服务器。</span><span class="sxs-lookup"><span data-stu-id="b530e-118">Confirm that Azure Active Directory (AAD) Connect is set up and uses an on-premises Active Directory server running Windows Server 2008 R2 or later.</span></span>
- <span data-ttu-id="b530e-119">确认 AAD 连接运行的是受支持的版本, 并将其设置为将这三个属性与 Azure AD 同步:</span><span class="sxs-lookup"><span data-stu-id="b530e-119">Confirm that AAD Connect is running a supported version and is set to sync these three attributes with Azure AD:</span></span> 
    - <span data-ttu-id="b530e-120">内部部署 Active Directory (最终用户所在的位置) 的 DNS 域名称</span><span class="sxs-lookup"><span data-stu-id="b530e-120">DNS domain name of the on-premises Active Directory (where the end-users are located)</span></span>
    - <span data-ttu-id="b530e-121">yor 本地 Active Directory (其中的第一个最终用户位于其中) 的 NetBIOS</span><span class="sxs-lookup"><span data-stu-id="b530e-121">NetBIOS of yor on-premises Active Directory (where th end-users are located)</span></span>
    - <span data-ttu-id="b530e-122">SAM 帐户的用户名称</span><span class="sxs-lookup"><span data-stu-id="b530e-122">SAM account name of the user</span></span>


### <a name="single-sign-on-by-using-windows-hello-for-business"></a><span data-ttu-id="b530e-123">使用 Windows Hello 企业版的单一登录</span><span class="sxs-lookup"><span data-stu-id="b530e-123">Single Sign-On by using Windows Hello for Business</span></span>

<span data-ttu-id="b530e-124">Microsoft 托管桌面设备还通过采用 Windows Hello 企业版为你的用户提供了快速、passwordless 的体验。</span><span class="sxs-lookup"><span data-stu-id="b530e-124">Microsoft Managed Desktop devices also offer your users a fast, passwordless experience by employing Windows Hello for Business.</span></span> <span data-ttu-id="b530e-125">若要确保 Windows hello 企业版能够正常工作, 而用户无需提供 UPN 和密码, 请访问[使用 Windows Hello 企业版的本地单一登录配置 Azure AD 加入设备](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)以检查要求, 然后按照此处提供的步骤。</span><span class="sxs-lookup"><span data-stu-id="b530e-125">To ensure Windows Hello for Business will work without your users having to provide UPN and passwords, visit [Configure Azure AD joined devices for On-premises Single-Sign On using Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) to check the requirements, and then follow the steps provided there.</span></span>


## <a name="apps-and-resources-that-use-authentication"></a><span data-ttu-id="b530e-126">使用身份验证的应用程序和资源</span><span class="sxs-lookup"><span data-stu-id="b530e-126">Apps and resources that use authentication</span></span>

<span data-ttu-id="b530e-127">请参阅了解 azure 内容集中[应用程序和资源的注意事项](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources), 以获取有关设置应用程序以与 Azure Active Directory 配合使用的完整指南。</span><span class="sxs-lookup"><span data-stu-id="b530e-127">Refer to [Understand considerations for applications and resources](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in the Azure content set for full guidance on setting up apps to work with Azure Active Directory.</span></span> <span data-ttu-id="b530e-128">摘要:</span><span class="sxs-lookup"><span data-stu-id="b530e-128">In summary:</span></span>


- <span data-ttu-id="b530e-129">如果您使用**基于云的应用程序**(例如, 添加到 Azure AD 应用程序库中的应用程序), 则大多数不需要进一步准备使用 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="b530e-129">If you use **cloud-based apps**, such as those added to the Azure AD app gallery, most don't require any further preparation to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="b530e-130">但是, 任何不使用 Web 帐户管理器 (WAM) 的 Win32 应用程序可能仍会提示用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="b530e-130">However, any Win32 apps that don't use Web Account Manager (WAM) might still prompt users for authentication.</span></span>

- <span data-ttu-id="b530e-131">对于**托管在本地**的应用程序, 请务必将这些应用添加到浏览器中的 "受信任的网站" 列表中。</span><span class="sxs-lookup"><span data-stu-id="b530e-131">For apps that are **hosted on-premises**, be sure to add those apps to the trusted sites list in your browsers.</span></span> <span data-ttu-id="b530e-132">这将使 Windows 身份验证能够无缝工作, 而不提示用户提供凭据。</span><span class="sxs-lookup"><span data-stu-id="b530e-132">This will enable Windows authentication to work seamlessly, without users being prompted for credentials.</span></span> <span data-ttu-id="b530e-133">若要执行此操作, 请参阅[可配置的设置参考](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref)中的[受信任站点](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites)。</span><span class="sxs-lookup"><span data-stu-id="b530e-133">To do this, refer to [Trusted sites](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) in the [Configurable settings reference](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref).</span></span>

- <span data-ttu-id="b530e-134">如果使用的是 Active Directory 联合服务, 请检查是否已通过使用 "[使用 AD FS 验证和管理单一登录"](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100))中的步骤启用 SSO。</span><span class="sxs-lookup"><span data-stu-id="b530e-134">If you are using Active Directory Federated Services, check that SSO is enabled by using the steps in [Verify and manage single sign-on with AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)).</span></span> 

- <span data-ttu-id="b530e-135">对于**内部部署和使用较旧协议**的应用程序, 只要设备有权访问内部部署域控制器进行身份验证, 则不需要额外的设置。</span><span class="sxs-lookup"><span data-stu-id="b530e-135">For apps that are **on-premises and use older protocols**, no extra setup is required, as long as the devices have access to an on-premises domain controller to authenticate.</span></span> <span data-ttu-id="b530e-136">但是, 若要提供对这些应用程序的安全访问, 应部署 Azure AD 应用程序代理。</span><span class="sxs-lookup"><span data-stu-id="b530e-136">To provide secure access for these applications, however, you should deploy Azure AD Application Proxy.</span></span> <span data-ttu-id="b530e-137">有关详细信息, 请参阅[通过 Azure Active Directory 应用程序代理远程访问本地应用程序](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)。</span><span class="sxs-lookup"><span data-stu-id="b530e-137">For more information, see [Remote access to on-premises applications through Azure Active Directory's Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

- <span data-ttu-id="b530e-138">不支持**在本地运行和依赖计算机身份验证**的应用程序, 因此应考虑将它们替换为较新的版本。</span><span class="sxs-lookup"><span data-stu-id="b530e-138">Apps that run **on-premises and rely on machine authentication** aren't supported, so you should consider replacing these with newer versions.</span></span>

### <a name="network-shares-that-use-authentication"></a><span data-ttu-id="b530e-139">使用身份验证的网络共享</span><span class="sxs-lookup"><span data-stu-id="b530e-139">Network shares that use authentication</span></span>

<span data-ttu-id="b530e-140">用户无需额外的设置即可访问网络共享, 只要这些设备具有使用 UNC 路径的本地域控制器的访问权限即可。</span><span class="sxs-lookup"><span data-stu-id="b530e-140">No extra setup is required for users to access network shares, as long as the devices have access to an on-premises domain controller by using a UNC path.</span></span>

### <a name="printers"></a><span data-ttu-id="b530e-141">打印机</span><span class="sxs-lookup"><span data-stu-id="b530e-141">Printers</span></span>

<span data-ttu-id="b530e-142">除非您已配置[混合云打印](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy), 否则 Microsoft 托管桌面设备将无法连接到发布到本地 Active Directory 的打印机。</span><span class="sxs-lookup"><span data-stu-id="b530e-142">Microsoft Managed Desktop devices cannot connect to printers that are published to your on-premises Active Directory unless you have configured [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>

<span data-ttu-id="b530e-143">虽然在仅云环境中无法自动发现打印机, 但只要设备具有对本地域控制器的访问权限, 用户就可以使用打印机路径或打印机队列路径的本地打印机。</span><span class="sxs-lookup"><span data-stu-id="b530e-143">While printers can't be automatically discovered in a cloud only environment, your users can use on-premises printers by using the printer path or printer queue path, as long as the devices have access to an on-premises domain controller.</span></span>

<!--add fuller material on printers when available-->