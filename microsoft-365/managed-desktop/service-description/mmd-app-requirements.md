---
title: Microsoft 托管桌面应用程序要求
description: ''
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/08/2019
ms.openlocfilehash: 6b6c6f6a2e719496578ac1d15c9b94a92a2ab492
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865383"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="a77e2-103">Microsoft 托管桌面应用程序要求</span><span class="sxs-lookup"><span data-stu-id="a77e2-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="a77e2-104">您想要部署到 Microsoft 托管桌面设备上的业务线应用程序必须满足本主题中的要求。</span><span class="sxs-lookup"><span data-stu-id="a77e2-104">Line-of-business applications that you want to deploy to Microsoft Managed Desktop devices must meet the requirements in this topic.</span></span> 

## <a name="application-condition"></a><span data-ttu-id="a77e2-105">应用程序条件</span><span class="sxs-lookup"><span data-stu-id="a77e2-105">Application condition</span></span>

<span data-ttu-id="a77e2-p101">非常重要的应用程序不对 Microsoft 托管桌面环境产生不利影响。以下是应用程序必须满足 microsoft 将其部署顺序的要求。对于任何给定应用程序或驱动程序中，Microsoft 可能放弃根据此处提供的任何要求。Microsoft 可能决定删除任何应用程序或带来负面影响性能和可靠性 Microsoft 托管桌面设备的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="a77e2-p101">It’s important that applications don’t adversely impact the Microsoft Managed Desktop environment. The following are the requirements that an application must meet in order for Microsoft to deploy it. For any given application or driver, Microsoft may waive any requirement provided herein. Microsoft may decide to remove any application or driver that negatively impacts performance and reliability of Microsoft Managed Desktop devices.</span></span>

## <a name="deployable-using-microsoft-technologies"></a><span data-ttu-id="a77e2-110">可使用 Microsoft 技术部署</span><span class="sxs-lookup"><span data-stu-id="a77e2-110">Deployable using Microsoft technologies</span></span>

<span data-ttu-id="a77e2-p102">Microsoft 托管桌面使用 Intune、 Microsoft 存储和 Microsoft Store for Business 部署应用程序。因此，必须能够通过这些服务的新版本部署方式打包应用程序。</span><span class="sxs-lookup"><span data-stu-id="a77e2-p102">Microsoft Managed Desktop uses Intune,  Microsoft Store, and  Microsoft Store for Business to deploy applications. Consequently, applications must be packaged in a manner able to be deployed by the then-current version of those services.</span></span>

## <a name="prohibited-app-classes"></a><span data-ttu-id="a77e2-113">禁止应用程序类</span><span class="sxs-lookup"><span data-stu-id="a77e2-113">Prohibited app classes</span></span>

<span data-ttu-id="a77e2-114">某些应用程序类型不是允许使用 Microsoft 托管桌面设备上：</span><span class="sxs-lookup"><span data-stu-id="a77e2-114">Certain application types are not permitted on Microsoft Managed Desktop devices:</span></span>
- <span data-ttu-id="a77e2-115">第三方防病毒、 安全性或审核软件</span><span class="sxs-lookup"><span data-stu-id="a77e2-115">3rd party anti-virus, security, or audit software</span></span>
- <span data-ttu-id="a77e2-116">第三方 web 浏览器</span><span class="sxs-lookup"><span data-stu-id="a77e2-116">3rd party web browsers</span></span>
- <span data-ttu-id="a77e2-117">Office 365 Pro Plus 之前的 Microsoft Office 版本</span><span class="sxs-lookup"><span data-stu-id="a77e2-117">Versions of Microsoft Office prior to Office 365 Pro Plus</span></span>
- <span data-ttu-id="a77e2-118">安装或捆绑其他第三方软件应用程序</span><span class="sxs-lookup"><span data-stu-id="a77e2-118">Applications that install or bundle other 3rd party software</span></span>

## <a name="restricted-app-behaviors"></a><span data-ttu-id="a77e2-119">受限制的应用程序行为</span><span class="sxs-lookup"><span data-stu-id="a77e2-119">Restricted app behaviors</span></span>

<span data-ttu-id="a77e2-p103">某些应用程序行为可对用户体验造成不利影响或带来安全风险到 Microsoft 托管桌面设备。应用程序应表现出以下行为或特征：</span><span class="sxs-lookup"><span data-stu-id="a77e2-p103">Certain application behaviors can either be detrimental to user experience or present a security risk to Microsoft Managed Desktop devices. Applications shall not exhibit the following behaviors or characteristics:</span></span> 

<span data-ttu-id="a77e2-122">用户体验：</span><span class="sxs-lookup"><span data-stu-id="a77e2-122">User Experience:</span></span>
- <span data-ttu-id="a77e2-123">安装后台服务或生成长时间运行背景进程</span><span class="sxs-lookup"><span data-stu-id="a77e2-123">Install background services or spawn long-running background processes</span></span>
- <span data-ttu-id="a77e2-124">自动添加到 Windows 启动路径</span><span class="sxs-lookup"><span data-stu-id="a77e2-124">Add itself to the Windows startup path</span></span>

<span data-ttu-id="a77e2-125">安全性：</span><span class="sxs-lookup"><span data-stu-id="a77e2-125">Security:</span></span>
- <span data-ttu-id="a77e2-126">呼叫未记录 Windows 或 Office Api 或承担内部 Windows 或 Office 数据结构依赖项</span><span class="sxs-lookup"><span data-stu-id="a77e2-126">Call undocumented Windows or Office APIs or take dependencies on internal Windows or Office data structures</span></span>
- <span data-ttu-id="a77e2-127">用作应用程序商店或内置扩展管理器</span><span class="sxs-lookup"><span data-stu-id="a77e2-127">Act as an app store or have built-in extension manager</span></span>
- <span data-ttu-id="a77e2-128">将最终用户的权限提升</span><span class="sxs-lookup"><span data-stu-id="a77e2-128">Elevate the end user’s privileges</span></span>
- <span data-ttu-id="a77e2-129">具有已知安全漏洞</span><span class="sxs-lookup"><span data-stu-id="a77e2-129">Have known security vulnerabilities</span></span>
- <span data-ttu-id="a77e2-130">使用其不能上卷到受信任的根证书签名</span><span class="sxs-lookup"><span data-stu-id="a77e2-130">Signed using a certificate which doesn’t roll up to a trusted root</span></span>
- <span data-ttu-id="a77e2-131">加密或限制对最终用户数据访问</span><span class="sxs-lookup"><span data-stu-id="a77e2-131">Encrypt or restrict access to end-user data</span></span>
- <span data-ttu-id="a77e2-132">在运行时修改操作系统代码</span><span class="sxs-lookup"><span data-stu-id="a77e2-132">Modify operating system code at run time</span></span>

## <a name="driver-deployment"></a><span data-ttu-id="a77e2-133">驱动程序部署</span><span class="sxs-lookup"><span data-stu-id="a77e2-133">Driver deployment</span></span>

<span data-ttu-id="a77e2-134">驱动程序 Windows Update 中可用，或者单独签名的 Windows 硬件质量实验室 (WHQL)，除非 Microsoft Microsoft 将部署到 Microsoft 托管桌面设备驱动程序之前必须批准驱动程序。</span><span class="sxs-lookup"><span data-stu-id="a77e2-134">Unless a driver is available in Windows Update or is separately signed by Windows Hardware Quality Lab (WHQL), Microsoft must approve a driver before Microsoft will deploy the driver to Microsoft Managed Desktop devices.</span></span>
