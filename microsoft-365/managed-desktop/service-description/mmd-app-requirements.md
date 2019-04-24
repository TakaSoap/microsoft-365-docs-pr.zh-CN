---
title: Microsoft 托管桌面应用程序要求
description: ''
keywords: microsoft 托管桌面, microsoft 365, 服务, 文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: de6cc7d77e023a9d41961e5fbcce060f1bb659ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278332"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="ecb4c-103">Microsoft 托管桌面应用程序要求</span><span class="sxs-lookup"><span data-stu-id="ecb4c-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="ecb4c-104">要部署到 Microsoft 托管桌面设备的业务线应用程序必须满足本主题中的要求。</span><span class="sxs-lookup"><span data-stu-id="ecb4c-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="ecb4c-105">应用程序条件</span><span class="sxs-lookup"><span data-stu-id="ecb4c-105">Application condition</span></span>

<span data-ttu-id="ecb4c-106">应用程序不会对 Microsoft 托管桌面环境产生负面影响, 这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="ecb4c-106">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="ecb4c-107">以下是应用程序必须满足以让 Microsoft 部署它的要求。</span><span class="sxs-lookup"><span data-stu-id="ecb4c-107">The following are the requirements that an application must meet in order for Microsoft to deploy it.</span></span> <span data-ttu-id="ecb4c-108">对于任何给定的应用程序或驱动程序, Microsoft 可能会停征此处提供的任何要求。</span><span class="sxs-lookup"><span data-stu-id="ecb4c-108">For any given application or driver, Microsoft may waive any requirement provided herein.</span></span> <span data-ttu-id="ecb4c-109">microsoft 可能会决定删除对 Microsoft 托管桌面设备的性能和可靠性产生负面影响的任何应用程序或驱动程序。</span><span class="sxs-lookup"><span data-stu-id="ecb4c-109">Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="ecb4c-110">可使用 Microsoft 技术部署</span><span class="sxs-lookup"><span data-stu-id="ecb4c-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="ecb4c-111">Microsoft 托管桌面使用 Intune、microsoft store 和 microsoft store for Business 来部署应用程序。</span><span class="sxs-lookup"><span data-stu-id="ecb4c-111">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications.</span></span> <span data-ttu-id="ecb4c-112">因此, 应用程序必须以可由这些服务的当前版本部署的方式进行打包。</span><span class="sxs-lookup"><span data-stu-id="ecb4c-112">Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="ecb4c-113">禁止的应用程序类</span><span class="sxs-lookup"><span data-stu-id="ecb4c-113">Prohibited app classes</span></span>

<span data-ttu-id="ecb4c-114">Microsoft 托管桌面设备上不允许某些应用程序类型:</span><span class="sxs-lookup"><span data-stu-id="ecb4c-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="ecb4c-115">第三方反病毒、安全性或审核软件</span><span class="sxs-lookup"><span data-stu-id="ecb4c-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="ecb4c-116">第三方 web 浏览器</span><span class="sxs-lookup"><span data-stu-id="ecb4c-116">3rd party web browsers</span></span>
- <span data-ttu-id="ecb4c-117">office 365 Pro Plus 之前的 Microsoft Office 版本</span><span class="sxs-lookup"><span data-stu-id="ecb4c-117">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="ecb4c-118">安装或捆绑其他第三方软件的应用程序</span><span class="sxs-lookup"><span data-stu-id="ecb4c-118">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="ecb4c-119">受限制的应用程序行为</span><span class="sxs-lookup"><span data-stu-id="ecb4c-119">Restricted app behaviors</span></span>

<span data-ttu-id="ecb4c-120">某些应用程序行为可能会对用户体验造成损害或向 Microsoft 托管桌面设备带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="ecb4c-120">Certain application behaviors can either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="ecb4c-121">应用程序不应表现出以下行为或特征:</span><span class="sxs-lookup"><span data-stu-id="ecb4c-121">Applications shall not exhibit the following behaviors or characteristics:</span></span> 

<span data-ttu-id="ecb4c-122">用户体验:</span><span class="sxs-lookup"><span data-stu-id="ecb4c-122">User Experience:</span></span>
- <span data-ttu-id="ecb4c-123">安装后台服务或生成长时间运行的后台进程</span><span class="sxs-lookup"><span data-stu-id="ecb4c-123">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="ecb4c-124">将自身添加到 Windows 启动路径</span><span class="sxs-lookup"><span data-stu-id="ecb4c-124">Add itself to the Windows startup path</span></span>

<span data-ttu-id="ecb4c-125">安全性：</span><span class="sxs-lookup"><span data-stu-id="ecb4c-125">Security:</span></span>
- <span data-ttu-id="ecb4c-126">调用未记录的 windows 或 office api 或对内部 Windows 或 office 数据结构进行依赖关系</span><span class="sxs-lookup"><span data-stu-id="ecb4c-126">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="ecb4c-127">充当应用商店或具有内置扩展管理器</span><span class="sxs-lookup"><span data-stu-id="ecb4c-127">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="ecb4c-128">提升最终用户的权限</span><span class="sxs-lookup"><span data-stu-id="ecb4c-128">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="ecb4c-129">存在已知的安全漏洞</span><span class="sxs-lookup"><span data-stu-id="ecb4c-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="ecb4c-130">使用不会汇总到受信任的根的证书进行签名</span><span class="sxs-lookup"><span data-stu-id="ecb4c-130">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="ecb4c-131">加密或限制对最终用户数据的访问</span><span class="sxs-lookup"><span data-stu-id="ecb4c-131">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="ecb4c-132">在运行时修改操作系统代码</span><span class="sxs-lookup"><span data-stu-id="ecb4c-132">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="ecb4c-133">驱动程序部署</span><span class="sxs-lookup"><span data-stu-id="ecb4c-133">Driver deployment</span></span>

<span data-ttu-id="ecb4c-134">除非驱动程序在 windows 更新中可用或由 windows 硬件质量实验室 (WHQL) 单独签名, 否则 microsoft 必须先批准驱动程序, 然后才能将驱动程序部署到 microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="ecb4c-134">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>
