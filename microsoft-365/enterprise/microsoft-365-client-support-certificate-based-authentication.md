---
title: Microsoft 365客户端应用支持：基于证书的身份验证
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 本文详细介绍了如何Microsoft 365基于证书的身份验证的客户端应用支持。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d5ebef7c10aa61ba28c8fb841468be244f6e8542
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904982"
---
# <a name="microsoft-365-client-app-support-certificate-based-authentication"></a><span data-ttu-id="ab1e3-103">Microsoft 365客户端应用支持：基于证书的身份验证</span><span class="sxs-lookup"><span data-stu-id="ab1e3-103">Microsoft 365 Client App Support: Certificate-based Authentication</span></span>

<span data-ttu-id="ab1e3-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="ab1e3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ab1e3-105">新式验证是一个综合术语，用于组合身份验证和授权方法。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-105">Modern authentication is an umbrella term for a combination of authentication and authorization methods.</span></span> <span data-ttu-id="ab1e3-106">这些方法包括：</span><span class="sxs-lookup"><span data-stu-id="ab1e3-106">These methods include:</span></span>

- <span data-ttu-id="ab1e3-107">**身份验证方法**：多重身份验证;基于客户端证书的身份验证。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-107">**Authentication methods**: Multi-factor Authentication; Client Certificate-based authentication.</span></span>
- <span data-ttu-id="ab1e3-108">**授权方法**：Microsoft 的 Open Authorization (OAuth) 。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-108">**Authorization methods**: Microsoft's implementation of Open Authorization (OAuth).</span></span>

<span data-ttu-id="ab1e3-109">使用身份验证库启用新式验证，如 Active Directory 身份验证库 (ADAL) 或 Microsoft 身份验证库 (MSAL) 。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-109">Modern authentication is enabled by using an authentication library, like Active Directory Authentication Library (ADAL) or Microsoft Authentication Library (MSAL).</span></span> <span data-ttu-id="ab1e3-110">新式验证是客户端用于验证和授权访问 Microsoft 365资源。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-110">Modern authentication is what clients use to authenticate and authorize access to Microsoft 365 resources.</span></span> <span data-ttu-id="ab1e3-111">新式验证使用 OAuth，并提供一种安全机制，使客户端无需访问Microsoft 365即可访问服务。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-111">Modern authentication uses OAuth and provides a secure mechanism for clients to access Microsoft 365 services, without requiring access to user credentials.</span></span> <span data-ttu-id="ab1e3-112">登录时，用户直接使用 Azure Active Directory进行身份验证，并接收访问/刷新令牌对。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-112">At sign-in, the user authenticates directly with Azure Active Directory and receives an access/refresh token pair in return.</span></span> <span data-ttu-id="ab1e3-113">访问令牌授予客户端对租户中相应资源Microsoft 365权限。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-113">The access token grants the client access to the appropriate resources in the Microsoft 365 tenant.</span></span> <span data-ttu-id="ab1e3-114">刷新令牌用于在当前访问令牌过期时获取新的访问令牌或刷新令牌对。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-114">A refresh token is used to obtain a new access or refresh token pair when the current access token expires.</span></span>

<span data-ttu-id="ab1e3-115">新式身份验证支持不同的身份验证机制，如基于证书的身份验证。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-115">Modern authentication supports different authentication mechanisms, like certificate-based authentication.</span></span> <span data-ttu-id="ab1e3-116">Windows、Android 或 iOS 设备上的客户端可以使用基于证书的身份验证 (CBA) ，Azure Active Directory设备上的客户端证书向 Azure Active Directory 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-116">Clients on Windows, Android, or iOS devices can use certificate-based authentication (CBA) to authenticate to Azure Active Directory using a client certificate on the device.</span></span> <span data-ttu-id="ab1e3-117">证书不是典型的用户名/密码，而是用于从用户获取访问/刷新Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-117">Instead of a typical username/password, the certificate is used to obtain an access/refresh token pair from Azure Active Directory.</span></span>

<span data-ttu-id="ab1e3-118">详细了解基于 [证书的身份验证](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started)。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-118">Learn more about [certificate-based authentication](/azure/active-directory/authentication/active-directory-certificate-based-authentication-get-started).</span></span>

## <a name="supported-clients--platforms"></a><span data-ttu-id="ab1e3-119">受支持的客户端&平台</span><span class="sxs-lookup"><span data-stu-id="ab1e3-119">Supported clients & platforms</span></span>

<span data-ttu-id="ab1e3-120">在客户端 (中登录 Azure Active Directory 帐户时，以下客户端和平台的最新版本支持基于证书的身份验证) 。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-120">The latest versions of the following clients and platforms support certificate-based authentication when signing into Azure Active Directory accounts within the client (for example, when adding an account to the app).</span></span> <span data-ttu-id="ab1e3-121">有关应用程序平台支持Microsoft 365，请参阅 system [requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources)。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-121">For more information about platform support in Microsoft 365, see [System requirements for Microsoft 365](/microsoft-365/microsoft-365-and-office-resources).</span></span>
<br>
<br>

[!INCLUDE [Certificate-based authentication services support table](../includes/microsoft-365-client-support-certificate-based-authentication-include.md)]

>[!NOTE]
><span data-ttu-id="ab1e3-122">iOS 和 Android 的边缘支持帐户添加流期间基于证书的身份验证。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-122">Edge for iOS and Android supports certificate-based authentication during account add flows.</span></span> <span data-ttu-id="ab1e3-123">对通常为 Intranet 网站的网站执行身份验证时，iOS 和 Android 边缘不支持基于证书的身份验证。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-123">Edge for iOS and Android does not support certificate-based authentication when performing authentication against web sites, which are typically intranet sites.</span></span> <br><br>  <span data-ttu-id="ab1e3-124">在此方案中，用户导航到通常 (Intranet) 网站要求用户通过证书进行身份验证的网站。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-124">In this scenario, a user navigates to a web site (usually on the intranet) where the web site requires the user to authenticate via a certificate.</span></span> <span data-ttu-id="ab1e3-125">这完全不涉及新式验证，也不利用 Microsoft 身份验证库。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-125">This does not involve modern authentication at all and does not leverage a Microsoft authentication library.</span></span> <span data-ttu-id="ab1e3-126">这是由于 iOS 的限制：iOS 阻止第三方应用访问存储证书的系统密钥链 (只有 Apple 应用和 [Safari Webview](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) 控制器可以访问系统密钥链) 。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-126">This is due to a limitation with iOS: iOS prevents third-party apps from accessing the system keychain where the certificates are stored (only Apple apps and the [Safari webview controller](https://developer.apple.com/documentation/safariservices/sfsafariviewcontroller) can access the system keychain).</span></span> <br><br> <span data-ttu-id="ab1e3-127">由于 Edge 依赖 [WebKit](https://developer.apple.com/documentation/webkit) 框架来呈现网站，因此 Edge 无法访问系统密钥链，也无法向用户显示证书选择。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-127">As Edge relies on the [WebKit](https://developer.apple.com/documentation/webkit) framework for rendering web sites, Edge is unable to access the system keychain and present the user with a certificate choice.</span></span> <span data-ttu-id="ab1e3-128">遗憾的是，这是由 Apple 的体系结构设计的。</span><span class="sxs-lookup"><span data-stu-id="ab1e3-128">This, unfortunately, is by design due to Apple's architecture.</span></span>

## <a name="supported-powershell-modules"></a><span data-ttu-id="ab1e3-129">支持的 PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="ab1e3-129">Supported PowerShell modules</span></span>

- [<span data-ttu-id="ab1e3-130">Azure Active DirectoryPowerShell</span><span class="sxs-lookup"><span data-stu-id="ab1e3-130">Azure Active Directory PowerShell</span></span>](/powershell/azure/active-directory/overview?view=azureadps-2.0)
- [<span data-ttu-id="ab1e3-131">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab1e3-131">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)
- [<span data-ttu-id="ab1e3-132">SharePoint Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab1e3-132">SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

