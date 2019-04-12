---
title: 为 Microsoft 托管桌面准备本地资源访问
description: 确保 Azure AD 可以与本地 AD 通信以提供身份验证的重要步骤
keywords: microsoft 托管桌面, microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0f9cbe6712b8d16f435cfdf5fd84875656fa9c2e
ms.sourcegitcommit: ef589025820ddf6edb5f454826b1c12c9bcb8e49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2019
ms.locfileid: "31824462"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a><span data-ttu-id="c8c55-104">为 Microsoft 托管桌面准备本地资源访问</span><span class="sxs-lookup"><span data-stu-id="c8c55-104">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>

<span data-ttu-id="c8c55-105">在 Microsoft 托管桌面中, 设备会自动加入 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="c8c55-105">In Microsoft Managed Desktop, devices are automatically joined to Azure Active Directory.</span></span> <span data-ttu-id="c8c55-106">这意味着, 如果您使用的是本地 active directory, 则必须检查一些事项, 以确保加入到 Azure AD 的设备可以与您的本地 active directory 进行通信。</span><span class="sxs-lookup"><span data-stu-id="c8c55-106">This means that if you are using an on-premises Active Directory, you'll have to check some things to ensure that devices joined to Azure AD can communicate with your on-premises Active Directory.</span></span> 

> [!NOTE]  
> <span data-ttu-id="c8c55-107">*混合*Microsoft 托管桌面不支持 Azure AD 加入。</span><span class="sxs-lookup"><span data-stu-id="c8c55-107">*Hybrid* Azure AD join is not supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="c8c55-108">通过 Azure Active Directory, 用户可以利用单一登录 (SSO), 这意味着他们在每次想要执行某些操作时, 通常都不需要提供凭据。</span><span class="sxs-lookup"><span data-stu-id="c8c55-108">Azure Active Directory lets your users take advantage of Single Sign-On (SSO), which means they typically won't have to provide credentials every time they want to do something.</span></span> <span data-ttu-id="c8c55-109">如果你完全是 Azure active directory 的新内容, 请参阅 how [to: Plan a azure AD join 实现](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)--但是, 在引用 azure Active Directory 文档时, 请记住 Microsoft 不支持*混合*Azure ad join托管桌面。</span><span class="sxs-lookup"><span data-stu-id="c8c55-109">If you're completely new to Azure Active Directory, refer to [How to: Plan your Azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)--however, as you reference Azure Active Directory documentation, keep in mind that *hybrid* Azure AD join is not supported by Microsoft Managed Desktop.</span></span>


<span data-ttu-id="c8c55-110">本主题介绍要检查的内容, 以确保依赖于本地 Active Directory 连接的应用和其他资源将在 Microsoft 托管桌面中正常运行。</span><span class="sxs-lookup"><span data-stu-id="c8c55-110">This topic explains the things you need to check in order to ensure that apps and other resources that depend on local Active Directory connectivity will work smoothly with Microsoft Managed Desktop.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="c8c55-111">若要使用户能够在 Azure Active Directory 中注册设备并注册 Intune (Microsoft 托管桌面必需), 请按照[配置设备设置](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings)中的步骤操作, 然后再继续本主题的其余部分。</span><span class="sxs-lookup"><span data-stu-id="c8c55-111">For users to be able to register devices in Azure Active Directory and enroll in Intune (required for Microsoft Managed Desktop), follow the steps in [Configure your device settings](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) before proceeding with the rest of this topic.</span></span>


## <a name="single-sign-on-for-on-premises-resources"></a><span data-ttu-id="c8c55-112">本地资源的单一登录</span><span class="sxs-lookup"><span data-stu-id="c8c55-112">Single Sign-On for on-premises resources</span></span>

<span data-ttu-id="c8c55-113">默认情况下, 使用 UPN 或密码 (默认方法) 的设备的单一登录 (SSO) 应已生效。</span><span class="sxs-lookup"><span data-stu-id="c8c55-113">Single Sign-On (SSO) for your devices by using UPN or passwords (the default method) should already work by default.</span></span> <span data-ttu-id="c8c55-114">但您也可以使用 Windows Hello 企业版, 这需要执行一些额外的设置步骤。</span><span class="sxs-lookup"><span data-stu-id="c8c55-114">But you can also use Windows Hello for Business, which requires some extra setup steps.</span></span> <span data-ttu-id="c8c55-115">有关 sso 的背景信息, 请参阅[本地资源的 sso 在 Azure AD 联接设备上的工作原理](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)。</span><span class="sxs-lookup"><span data-stu-id="c8c55-115">For background information about SSO, see [How SSO to on-premises resources works on Azure AD joined devices](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).</span></span>


### <a name="single-sign-on-by-using-upn-and-passwords"></a><span data-ttu-id="c8c55-116">使用 UPN 和密码的单一登录</span><span class="sxs-lookup"><span data-stu-id="c8c55-116">Single Sign-On by using UPN and passwords</span></span>

<span data-ttu-id="c8c55-117">用户无需特殊设置即可通过 UPN 和密码进行身份验证--默认情况下, 你可以从 Azure 获取此设置。</span><span class="sxs-lookup"><span data-stu-id="c8c55-117">No special setup is required for your users to authenticate by UPN and password--you get this by default from Azure.</span></span> <span data-ttu-id="c8c55-118">但是, 为了确保这能够正常运行, 应仔细检查以下各项:</span><span class="sxs-lookup"><span data-stu-id="c8c55-118">However, to make sure this will work, you should double-check the following:</span></span>

- <span data-ttu-id="c8c55-119">确认已使用运行 Windows server 2008 R2 或更高版本的本地 Active directory 服务器设置 Azure Active directory (AAD) 连接。</span><span class="sxs-lookup"><span data-stu-id="c8c55-119">Confirm that Azure Active Directory (AAD) Connect is set up with an on-premises Active Directory server running Windows Server 2008 R2 or later.</span></span>
- <span data-ttu-id="c8c55-120">AAD 连接运行受支持的版本, 并将其设置为将这三个关键属性与 Azure AD 同步:</span><span class="sxs-lookup"><span data-stu-id="c8c55-120">AAD Connect is running a supported version and is set to sync these three key attributes with Azure AD:</span></span> 
    - <span data-ttu-id="c8c55-121">用户在本地 Active Directory 中存在的 DNS 域的名称</span><span class="sxs-lookup"><span data-stu-id="c8c55-121">DNS domain name where the user is present in your on-premises Active Directory</span></span>
    - <span data-ttu-id="c8c55-122">用户在本地 Active Directory 中存在的 NetBIOS 域名</span><span class="sxs-lookup"><span data-stu-id="c8c55-122">NetBIOS domain name where the user is present in your on-premises Active Directory</span></span>
    - <span data-ttu-id="c8c55-123">SAM 帐户的用户名称</span><span class="sxs-lookup"><span data-stu-id="c8c55-123">SAM account name of the user</span></span>


### <a name="sso-by-using-windows-hello-for-business"></a><span data-ttu-id="c8c55-124">使用 Windows Hello 企业版的 SSO</span><span class="sxs-lookup"><span data-stu-id="c8c55-124">SSO by using Windows Hello for Business</span></span>

<span data-ttu-id="c8c55-125">你也可以通过使用 Windows Hello 企业版, 为你的用户提供快速、passwordless 的体验。</span><span class="sxs-lookup"><span data-stu-id="c8c55-125">Alternately, you can offer your users a fast, passwordless experience by employing Windows Hello for Business.</span></span> <span data-ttu-id="c8c55-126">若要对此进行设置, 请参阅[使用 Windows Hello 企业版上的本地单一登录配置 Azure AD 加入设备](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)以检查要求, 然后按照此处提供的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="c8c55-126">To set this up, visit [Configure Azure AD joined devices for On-premises Single-Sign On using Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) to check the requirements, and then follow the steps provided there.</span></span>


## <a name="apps-and-resources-that-use-authentication"></a><span data-ttu-id="c8c55-127">使用身份验证的应用程序和资源</span><span class="sxs-lookup"><span data-stu-id="c8c55-127">Apps and resources that use authentication</span></span>

<span data-ttu-id="c8c55-128">请参阅了解 azure 内容集中[应用程序和资源的注意事项](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources), 以获取有关设置应用程序以与 Azure Active Directory 配合使用的完整指南。</span><span class="sxs-lookup"><span data-stu-id="c8c55-128">Refer to [Understand considerations for applications and resources](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) in the Azure content set for full guidance on setting up apps to work with Azure Active Directory.</span></span> <span data-ttu-id="c8c55-129">摘要:</span><span class="sxs-lookup"><span data-stu-id="c8c55-129">In summary:</span></span>


- <span data-ttu-id="c8c55-130">如果您使用**基于云的应用程序**(例如, 添加到 Azure AD 应用程序库中的应用程序), 则大多数不需要进一步准备使用 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="c8c55-130">If you use **cloud-based apps**, such as those added to the Azure AD app gallery, most don't require any further preparation to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="c8c55-131">但是, 任何不使用 Web 帐户管理器 (WAM) 的 Win32 应用 () {验证此首字母缩略词} 仍可能会提示用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="c8c55-131">However, any Win32 apps that don't use Web Account Manager (WAM) {verify this acronym} might still prompt users for authentication.</span></span>

- <span data-ttu-id="c8c55-132">对于**托管在本地**的应用程序, 请务必将这些应用添加到浏览器中的 "受信任的网站" 列表中。</span><span class="sxs-lookup"><span data-stu-id="c8c55-132">For apps that are **hosted on-premises**, be sure to add those apps to the trusted sites list in your browsers.</span></span> <span data-ttu-id="c8c55-133">这将使 Windows 身份验证能够无缝工作, 而不提示用户提供凭据。</span><span class="sxs-lookup"><span data-stu-id="c8c55-133">This will enable Windows authentication to work seamlessly, without users being prompted for credentials.</span></span>

- <span data-ttu-id="c8c55-134">如果使用的是 Active Directory 联合服务, 请按照[Verify and manage single sign-on with AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100))中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="c8c55-134">If you are using Active Directory Federated Services, follow the steps in [Verify and manage single sign-on with AD FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)).</span></span> 

- <span data-ttu-id="c8c55-135">对于**内部部署和使用较旧协议**的应用程序, 只要设备具有对本地域控制器的访问权限, 就不需要额外的设置。</span><span class="sxs-lookup"><span data-stu-id="c8c55-135">For apps that are **on-premises and use older protocols**, no extra setup is required, as long as the devices have access to an on-premises domain controller.</span></span> <span data-ttu-id="c8c55-136">但是, 若要提供对这些应用程序的安全访问, 应部署 Azure AD 应用程序代理。</span><span class="sxs-lookup"><span data-stu-id="c8c55-136">To provide secure access for these applications, however, you should deploy Azure AD Application Proxy.</span></span> <span data-ttu-id="c8c55-137">有关详细信息, 请参阅[通过 Azure Active Directory 应用程序代理远程访问本地应用程序](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)。</span><span class="sxs-lookup"><span data-stu-id="c8c55-137">For more information, see [Remote access to on-premises applications through Azure Active Directory's Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

- <span data-ttu-id="c8c55-138">不支持**在本地运行和依赖计算机身份验证**的应用程序, 因此应考虑将它们替换为较新的版本。</span><span class="sxs-lookup"><span data-stu-id="c8c55-138">Apps that run **on-premises and rely on machine authentication** aren't supported, so you should consider replacing these with newer versions.</span></span>

## <a name="network-shares-that-use-authentication"></a><span data-ttu-id="c8c55-139">使用身份验证的网络共享</span><span class="sxs-lookup"><span data-stu-id="c8c55-139">Network shares that use authentication</span></span>

<span data-ttu-id="c8c55-140">用户无需额外的设置即可访问网络共享, 只要这些设备具有使用 UNC 路径的本地域控制器的访问权限即可。</span><span class="sxs-lookup"><span data-stu-id="c8c55-140">No extra setup is required for users to access network shares, as long as the devices have access to an on-premises domain controller by using a UNC path.</span></span>

## <a name="printers"></a><span data-ttu-id="c8c55-141">打印机</span><span class="sxs-lookup"><span data-stu-id="c8c55-141">Printers</span></span>

<span data-ttu-id="c8c55-142">虽然无法在仅云环境中自动发现打印机, 但您的用户也可以使用打印机的 UNC 路径直接添加它们。</span><span class="sxs-lookup"><span data-stu-id="c8c55-142">While printers can't be automatically discovered in a cloud only environment, your users can also use the printers’ UNC path to directly add them.</span></span>

<!--add fuller material on printers when available-->