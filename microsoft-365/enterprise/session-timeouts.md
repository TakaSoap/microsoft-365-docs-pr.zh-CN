---
title: 会话的会话Microsoft 365
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: 37a5c116-5b07-4f70-8333-5b86fd2c3c40
ms.collection:
- M365-security-compliance
description: 了解如何使用会话超时在客户端应用中平衡安全性和Microsoft 365访问。
ms.openlocfilehash: b85ed8a45727e8a8eed2537fa2233125cd05ece7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924912"
---
# <a name="session-timeouts-for-microsoft-365"></a><span data-ttu-id="e8527-103">会话的会话Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e8527-103">Session timeouts for Microsoft 365</span></span>

<span data-ttu-id="e8527-104">会话生存期是身份验证的重要部分，Microsoft 365是平衡安全性和提示用户提供凭据次数的重要组件。</span><span class="sxs-lookup"><span data-stu-id="e8527-104">Session lifetimes are an important part of authentication for Microsoft 365 and are an important component in balancing security and the number of times users are prompted for their credentials.</span></span>

## <a name="session-times-for-microsoft-365-services"></a><span data-ttu-id="e8527-105">服务会话Microsoft 365时间</span><span class="sxs-lookup"><span data-stu-id="e8527-105">Session times for Microsoft 365 services</span></span>

<span data-ttu-id="e8527-106">当用户在任何 web 应用或Microsoft 365中进行身份验证时，将建立会话。</span><span class="sxs-lookup"><span data-stu-id="e8527-106">When users authenticate in any of the Microsoft 365 web apps or mobile apps, a session is established.</span></span> <span data-ttu-id="e8527-107">在会话期间，用户无需重新进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e8527-107">For the duration of the session, users won't need to re-authenticate.</span></span> <span data-ttu-id="e8527-108">当用户处于非活动状态、关闭浏览器或选项卡时，或者其身份验证令牌由于其他原因（例如重置其密码时）过期时，会话可能会过期。</span><span class="sxs-lookup"><span data-stu-id="e8527-108">Sessions can expire when users are inactive, when they close the browser or tab, or when their authentication token expires for other reasons such as when their password has been reset.</span></span> <span data-ttu-id="e8527-109">Microsoft 365服务具有不同的会话超时，以对应于每个服务的典型使用。</span><span class="sxs-lookup"><span data-stu-id="e8527-109">The Microsoft 365 services have different session timeouts to correspond with the typical use of each service.</span></span>

<span data-ttu-id="e8527-110">下表列出了所有服务Microsoft 365生存期：</span><span class="sxs-lookup"><span data-stu-id="e8527-110">The following table lists the session lifetimes for Microsoft 365 services:</span></span>

| <span data-ttu-id="e8527-111">Microsoft 365 服务</span><span class="sxs-lookup"><span data-stu-id="e8527-111">Microsoft 365 service</span></span> | <span data-ttu-id="e8527-112">会话超时</span><span class="sxs-lookup"><span data-stu-id="e8527-112">Session timeout</span></span> |
|:-----|:-----|
|<span data-ttu-id="e8527-113">Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="e8527-113">Microsoft 365 admin center</span></span>  <br/> |<span data-ttu-id="e8527-114">系统要求你每 8 小时提供一次管理中心的凭据。</span><span class="sxs-lookup"><span data-stu-id="e8527-114">You are asked to provide credentials for the admin center every 8 hours.</span></span>  <br/> |
|<span data-ttu-id="e8527-115">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e8527-115">SharePoint Online</span></span>  <br/> |<span data-ttu-id="e8527-116">5 天不活动，只要用户选择"保持 **我登录"。**</span><span class="sxs-lookup"><span data-stu-id="e8527-116">5 days of inactivity as long as the users chooses **Keep me signed in**.</span></span> <span data-ttu-id="e8527-117">如果用户在上一次登录SharePoint 24 小时或数小时后再次访问 Online，超时值将重置为 5 天。</span><span class="sxs-lookup"><span data-stu-id="e8527-117">If the user accesses SharePoint Online again after 24 or more hours have passed from the previous sign-in, the timeout value is reset to 5 days.</span></span>  <br/> |
|<span data-ttu-id="e8527-118">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="e8527-118">Outlook Web App</span></span>  <br/> |<span data-ttu-id="e8527-119">6 小时。</span><span class="sxs-lookup"><span data-stu-id="e8527-119">6 hours.</span></span>  <br/> <span data-ttu-id="e8527-120">可以使用 [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet 中的 _ActivityBasedAuthenticationTimeoutInterval_ 参数更改此值。</span><span class="sxs-lookup"><span data-stu-id="e8527-120">You can change this value by using the  _ActivityBasedAuthenticationTimeoutInterval_ parameter in the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet.</span></span>  <br/> |
|<span data-ttu-id="e8527-121">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e8527-121">Azure Active Directory</span></span>  <br/> <span data-ttu-id="e8527-122"> (在启用了新式Office Microsoft 365的 Windows 客户端中) </span><span class="sxs-lookup"><span data-stu-id="e8527-122">(Used by Office and Microsoft 365 applications in Windows clients with modern authentication enabled)</span></span>  <br/> | <span data-ttu-id="e8527-123">新式身份验证使用访问令牌和刷新令牌向用户授予对使用 Microsoft 365 资源Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="e8527-123">Modern authentication uses access tokens and refresh tokens to grant user access to Microsoft 365 resources using Azure Active Directory.</span></span> <span data-ttu-id="e8527-124">访问令牌是成功进行身份验证后提供的 JSON Web 令牌，有效期为 1 小时。</span><span class="sxs-lookup"><span data-stu-id="e8527-124">An access token is a JSON Web Token provided after a successful authentication and is valid for 1 hour.</span></span> <span data-ttu-id="e8527-125">还提供了生存期较长的刷新令牌。</span><span class="sxs-lookup"><span data-stu-id="e8527-125">A refresh token with a longer lifetime is also provided.</span></span> <span data-ttu-id="e8527-126">当访问令牌过期时，Office客户端使用有效的刷新令牌获取新的访问令牌。</span><span class="sxs-lookup"><span data-stu-id="e8527-126">When access tokens expire, Office clients use a valid refresh token to obtain a new access token.</span></span> <span data-ttu-id="e8527-127">如果用户的初始身份验证仍然有效，则此交换成功。</span><span class="sxs-lookup"><span data-stu-id="e8527-127">This exchange succeeds if the user's initial authentication is still valid.</span></span>  <br/>  <span data-ttu-id="e8527-128">刷新令牌的有效期为 90 天，如果连续使用，则有效期为吊销前。</span><span class="sxs-lookup"><span data-stu-id="e8527-128">Refresh tokens are valid for 90 days, and with continuous use, they can be valid until revoked.</span></span>  <br/>  <span data-ttu-id="e8527-129">刷新令牌可能会因多个事件而失效，例如：</span><span class="sxs-lookup"><span data-stu-id="e8527-129">Refresh tokens can be invalidated by several events such as:</span></span>  <br/>  <span data-ttu-id="e8527-130">自颁发刷新令牌以来，用户密码已更改。</span><span class="sxs-lookup"><span data-stu-id="e8527-130">User's password has changed since the refresh token was issued.</span></span>  <br/>  <span data-ttu-id="e8527-131">管理员可以应用条件访问策略，以限制对用户尝试访问的资源的访问。</span><span class="sxs-lookup"><span data-stu-id="e8527-131">An administrator can apply conditional access policies that restrict access to the resource the user is trying to access.</span></span>  <br/> |
|<span data-ttu-id="e8527-132">SharePoint和OneDrive Android、iOS 和 Windows 10</span><span class="sxs-lookup"><span data-stu-id="e8527-132">SharePoint and OneDrive mobile apps for Android, iOS, and Windows 10</span></span>  <br/> |<span data-ttu-id="e8527-133">访问令牌的默认生存期为 1 小时。</span><span class="sxs-lookup"><span data-stu-id="e8527-133">The default lifetime for the access token is 1 hour.</span></span> <span data-ttu-id="e8527-134">刷新令牌的默认最大非活动时间为 90 天。</span><span class="sxs-lookup"><span data-stu-id="e8527-134">The default max inactive time of the refresh token is 90 days.</span></span>  <br/> [<span data-ttu-id="e8527-135">详细了解令牌以及如何配置令牌生存期</span><span class="sxs-lookup"><span data-stu-id="e8527-135">Learn more about tokens and how to configure token lifetimes</span></span>](/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> <span data-ttu-id="e8527-136">若要撤销刷新令牌，可以重置用户Microsoft 365密码</span><span class="sxs-lookup"><span data-stu-id="e8527-136">To revoke the refresh token, you can reset the user's Microsoft 365 password</span></span>  <br/> |
|<span data-ttu-id="e8527-137">Yammer Microsoft 365 Sign-In</span><span class="sxs-lookup"><span data-stu-id="e8527-137">Yammer with Microsoft 365 Sign-In</span></span>  <br/> |<span data-ttu-id="e8527-138">浏览器的生存期。</span><span class="sxs-lookup"><span data-stu-id="e8527-138">Lifetime of the browser.</span></span> <span data-ttu-id="e8527-139">如果用户关闭浏览器，并Yammer新浏览器中访问Yammer，用户会使用 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="e8527-139">If users close the browser and access Yammer in a new browser, Yammer will re-authenticate them with Microsoft 365.</span></span> <span data-ttu-id="e8527-140">如果用户使用缓存 Cookie 的第三方浏览器，他们可能需要在重新打开浏览器时重新进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e8527-140">If users use third-party browsers that cache cookies, they may not need to re-authenticate when they reopen the browser.</span></span>  <br/> <span data-ttu-id="e8527-141">> [!NOTE]> 这仅适用于使用 Microsoft 365 Sign-In for Yammer 的网络。</span><span class="sxs-lookup"><span data-stu-id="e8527-141">> [!NOTE]> This is valid only for networks using Microsoft 365 Sign-In for Yammer.</span></span>           |