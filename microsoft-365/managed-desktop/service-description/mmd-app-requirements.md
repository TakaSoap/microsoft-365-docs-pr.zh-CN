---
title: Microsoft 托管桌面应用程序要求
description: ''
keywords: microsoft 托管桌面, microsoft 365, 服务, 文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 07e4719d87cb11910a90665ce9beb95edf6641a4
ms.sourcegitcommit: e15cf5d0d8ff3dfdc457b469992d72ac802e6434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2019
ms.locfileid: "33467740"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="78684-103">Microsoft 托管桌面应用程序要求</span><span class="sxs-lookup"><span data-stu-id="78684-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="78684-104">为了保证 Microsoft 托管桌面设备的性能、可靠性和可维护性, 客户的业务线应用程序不一定会严重影响最终用户体验, 也不能修改安全的态度。</span><span class="sxs-lookup"><span data-stu-id="78684-104">In order to guarantee the performance, reliability, and serviceability of Microsoft Managed Desktop devices a customer’s line of business apps must not seriously impact end user experience or modify the security stance.</span></span> <span data-ttu-id="78684-105">因此, 要部署到 Microsoft 托管桌面设备的业务线应用程序必须满足本主题中的要求。</span><span class="sxs-lookup"><span data-stu-id="78684-105">Consequently, line of business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span>

## <a name="application-condition"></a><span data-ttu-id="78684-106">应用程序条件</span><span class="sxs-lookup"><span data-stu-id="78684-106">Application condition</span></span>

<span data-ttu-id="78684-107">应用程序不会对 Microsoft 托管桌面环境产生负面影响, 这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="78684-107">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="78684-108">以下是应用程序必须满足部署应用程序的要求。</span><span class="sxs-lookup"><span data-stu-id="78684-108">The following are the requirements that an application must meet for an application to be deployed.</span></span> <span data-ttu-id="78684-109">对于任何给定的应用程序或驱动程序, Microsoft 可能会停征此处提供的任何要求。</span><span class="sxs-lookup"><span data-stu-id="78684-109">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="78684-110">microsoft 可能会决定删除对 Microsoft 托管桌面设备的性能和可靠性产生负面影响的任何应用程序或驱动程序。</span><span class="sxs-lookup"><span data-stu-id="78684-110">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="centrally-managed-apps"></a><span data-ttu-id="78684-111">集中管理的应用程序</span><span class="sxs-lookup"><span data-stu-id="78684-111">Centrally managed apps</span></span>

<span data-ttu-id="78684-112">所有安装在 Microsoft 托管设备上的应用程序和驱动程序都必须通过 Intune、microsoft store 或 microsoft store for Business 进行部署;如果可用, 还将通过 Windows Update 服务部署驱动程序。</span><span class="sxs-lookup"><span data-stu-id="78684-112">All applications and drivers installed on Microsoft Managed Devices must be deployed through Intune, the Microsoft Store, or the Microsoft Store for Business; if available, drivers will also be deployed through the Windows Update service.</span></span> 

## <a name="prohibited-app-classes"></a><span data-ttu-id="78684-113">禁止的应用程序类</span><span class="sxs-lookup"><span data-stu-id="78684-113">Prohibited app classes</span></span>

<span data-ttu-id="78684-114">Microsoft 托管桌面设备上不允许某些应用程序类型:</span><span class="sxs-lookup"><span data-stu-id="78684-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="78684-115">第三方反病毒、安全性或审核软件</span><span class="sxs-lookup"><span data-stu-id="78684-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="78684-116">office 365 Pro Plus 之前的 Microsoft Office 版本</span><span class="sxs-lookup"><span data-stu-id="78684-116">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="78684-117">安装或捆绑其他第三方软件的应用程序</span><span class="sxs-lookup"><span data-stu-id="78684-117">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="78684-118">受限制的应用程序行为</span><span class="sxs-lookup"><span data-stu-id="78684-118">Restricted app behaviors</span></span>

<span data-ttu-id="78684-119">某些应用程序行为可能会对用户体验产生负面影响, 也可能对 Microsoft 托管桌面设备带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="78684-119">Certain app behaviors can negatively impact the user experience or may present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="78684-120">不允许在 microsoft 托管桌面环境中运行具有以下行为的应用程序, 而无需从 microsoft 进行特定的例外。</span><span class="sxs-lookup"><span data-stu-id="78684-120">Apps with the following behaviors are not permitted to run in the Microsoft Managed Desktop environment without a specific exemption from Microsoft.</span></span>

<span data-ttu-id="78684-121">用户体验:</span><span class="sxs-lookup"><span data-stu-id="78684-121">User Experience:</span></span>
- <span data-ttu-id="78684-122">安装后台服务</span><span class="sxs-lookup"><span data-stu-id="78684-122">Install background services</span></span>
- <span data-ttu-id="78684-123">将自身添加到 Windows 启动路径</span><span class="sxs-lookup"><span data-stu-id="78684-123">Add itself to the Windows startup path</span></span>
- <span data-ttu-id="78684-124">依赖驱动程序的应用程序</span><span class="sxs-lookup"><span data-stu-id="78684-124">Applications dependent on drivers</span></span>
- <span data-ttu-id="78684-125">第三方 web 浏览器</span><span class="sxs-lookup"><span data-stu-id="78684-125">3rd party web browsers</span></span>

<span data-ttu-id="78684-126">安全性：</span><span class="sxs-lookup"><span data-stu-id="78684-126">Security:</span></span>
- <span data-ttu-id="78684-127">提升最终用户的权限</span><span class="sxs-lookup"><span data-stu-id="78684-127">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="78684-128">充当应用商店或具有内置扩展管理器</span><span class="sxs-lookup"><span data-stu-id="78684-128">Act as an app store or have a built-in extension manager</span></span>
- <span data-ttu-id="78684-129">存在已知的安全漏洞</span><span class="sxs-lookup"><span data-stu-id="78684-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="78684-130">加密或限制对最终用户数据的访问</span><span class="sxs-lookup"><span data-stu-id="78684-130">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="78684-131">未签名或使用不会汇总到受信任的根的证书进行签名</span><span class="sxs-lookup"><span data-stu-id="78684-131">Is unsigned or is signed using a certificate which doesn’t roll up to a trusted root</span></span>


## <a name="driver-deployment"></a><span data-ttu-id="78684-132">驱动程序部署</span><span class="sxs-lookup"><span data-stu-id="78684-132">Driver deployment</span></span>

<span data-ttu-id="78684-133">microsoft 托管桌面仅支持通过 microsoft 托管设备在 Windows 更新或已安装的收件箱中提供的设备驱动程序。</span><span class="sxs-lookup"><span data-stu-id="78684-133">Microsoft Managed Desktop only supports device drivers that are available through Windows Update or installed inbox with the Microsoft Managed Device.</span></span> 

<span data-ttu-id="78684-134">如果应用程序需要特定驱动程序来运行它, 则会将其视为受限制的应用程序, 并要求将豁免部署到 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="78684-134">If an application requires a specific driver(s) to run it is considered a Restricted Application and requires an exemption to be deployed to Microsoft Managed Desktop.</span></span> 

