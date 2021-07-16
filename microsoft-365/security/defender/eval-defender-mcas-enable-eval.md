---
title: 启用评估环境Microsoft Cloud App Security
description: 了解 Microsoft Defender 中 MCAS 的体系结构，Office 365并了解产品之间的Microsoft 365 Defender交互。
keywords: Microsoft 365 Defender试用版， 试用 Microsoft 365 Defender， 评估 Microsoft 365 Defender， Microsoft 365 Defender 评估实验室， Microsoft 365 Defender 试点， 网络安全， 高级永久性威胁， 企业安全， 设备， 设备， 标识， 用户， 数据， 应用程序， 事件， 自动调查和修正， 高级搜寻
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6ada9613f852e085158b7002cbbb9a9928d36d58
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457626"
---
# <a name="enable-the-evaluation-environment-for-microsoft-cloud-app-security"></a><span data-ttu-id="75504-104">启用评估环境Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="75504-104">Enable the evaluation environment for Microsoft Cloud App Security</span></span>


<span data-ttu-id="75504-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="75504-105">**Applies to:**</span></span>

- <span data-ttu-id="75504-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="75504-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="75504-107">本文是设置评估环境的过程中第 2 步（第 2 步，第[2](eval-defender-mcas-overview.md)步Microsoft Cloud App Security）。</span><span class="sxs-lookup"><span data-stu-id="75504-107">This article is [Step 2 of 2](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security.</span></span> <span data-ttu-id="75504-108">有关此过程详细信息，请参阅 [概述文章](eval-defender-mcas-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="75504-108">For more information about this process, see the [overview article](eval-defender-mcas-overview.md).</span></span>

<span data-ttu-id="75504-109">本文将指导你完成访问云应用门户云应用安全配置收集云应用流量数据所需的集成的过程。</span><span class="sxs-lookup"><span data-stu-id="75504-109">This article walks you through the process of accessing the Cloud App Security portal and configuring the necessary integration to collect cloud app traffic data.</span></span>

<span data-ttu-id="75504-110">若要发现环境中使用的云应用，你可以执行以下一项或两项操作：</span><span class="sxs-lookup"><span data-stu-id="75504-110">To discover cloud apps used in your environment, you can do one or both of the following:</span></span>

- <span data-ttu-id="75504-111">与 Microsoft Defender for Endpoint 集成，快速启动并运行云发现。</span><span class="sxs-lookup"><span data-stu-id="75504-111">Get up and running quickly with Cloud Discovery by integrating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="75504-112">通过此本机集成，你可以立即开始在 Windows 10 设备上、网络上和网络上收集云流量上的数据。</span><span class="sxs-lookup"><span data-stu-id="75504-112">This native integration enables you to immediately start collecting data on cloud traffic across your Windows 10 devices, on and off your network.</span></span>
- <span data-ttu-id="75504-113">若要发现连接到网络的所有设备访问的所有云应用，云应用安全防火墙和其他代理上部署安全日志收集器。</span><span class="sxs-lookup"><span data-stu-id="75504-113">To discover all cloud apps accessed by all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies.</span></span> <span data-ttu-id="75504-114">这将从终结点收集数据，并将其发送到云应用安全进行分析。</span><span class="sxs-lookup"><span data-stu-id="75504-114">This collects data from your endpoints and sends it to Cloud App Security for analysis.</span></span> <span data-ttu-id="75504-115">云应用安全与一些第三方代理进行本机集成，以使用更多功能。</span><span class="sxs-lookup"><span data-stu-id="75504-115">Cloud App Security natively integrates with some third-party proxies for even more capabilities.</span></span>

<span data-ttu-id="75504-116">本文包括这两种方法的指南。</span><span class="sxs-lookup"><span data-stu-id="75504-116">This article includes guidance for both methods.</span></span>

<span data-ttu-id="75504-117">使用以下步骤设置Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="75504-117">Use the following steps to set up Microsoft Cloud App Security.</span></span>

![在 Microsoft Defender Microsoft Cloud App Security环境中启用 Microsoft 支持的步骤](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [<span data-ttu-id="75504-119">步骤 1.连接门户云应用安全</span><span class="sxs-lookup"><span data-stu-id="75504-119">Step 1. Connect to the Cloud App Security portal</span></span>](#step-1-connect-to-the-cloud-app-security-portal)
- [<span data-ttu-id="75504-120">步骤 2.与 Microsoft Defender for Endpoint 集成</span><span class="sxs-lookup"><span data-stu-id="75504-120">Step 2. Integrate with Microsoft Defender for Endpoint</span></span>](#step-2-integrate-with-microsoft-defender-for-endpoint)
- [<span data-ttu-id="75504-121">步骤 3.在云应用安全和其他代理上部署日志收集器</span><span class="sxs-lookup"><span data-stu-id="75504-121">Step 3. Deploy the Cloud App Security log collector on your firewalls and other proxies</span></span>](#step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies)
- [<span data-ttu-id="75504-122">步骤 4.查看云发现仪表板以查看组织中使用的应用</span><span class="sxs-lookup"><span data-stu-id="75504-122">Step 4. View the Cloud Discovery dashboard to see what apps are being used in your organization</span></span>](#step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization)

## <a name="step-1-connect-to-the-cloud-app-security-portal"></a><span data-ttu-id="75504-123">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="75504-123">Step 1.</span></span> <span data-ttu-id="75504-124">连接门户云应用安全</span><span class="sxs-lookup"><span data-stu-id="75504-124">Connect to the Cloud App Security portal</span></span>

<span data-ttu-id="75504-125">若要验证许可并连接到 云应用安全 门户，请参阅[快速入门：Microsoft Cloud App Security。](/cloud-app-security/getting-started-with-cloud-app-security)</span><span class="sxs-lookup"><span data-stu-id="75504-125">To verify licensing and to connect to the Cloud App Security portal, see [Quickstart: Get started with Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security).</span></span> 

<span data-ttu-id="75504-126">如果无法立即连接到门户，可能需要将 IP 地址添加到防火墙的允许列表中。</span><span class="sxs-lookup"><span data-stu-id="75504-126">If you're not immediately able to connect to the portal, you might need to add the IP address to the allow list of your firewall.</span></span> <span data-ttu-id="75504-127">请参阅[基本设置了解云应用安全。](/cloud-app-security/general-setup)</span><span class="sxs-lookup"><span data-stu-id="75504-127">See [Basic setup for Cloud App Security](/cloud-app-security/general-setup).</span></span>

<span data-ttu-id="75504-128">如果仍有问题，请查看网络 [要求](/cloud-app-security/network-requirements)。</span><span class="sxs-lookup"><span data-stu-id="75504-128">If you're still having trouble, review [Network requirements](/cloud-app-security/network-requirements).</span></span>

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="75504-129">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="75504-129">Step 2.</span></span> <span data-ttu-id="75504-130">与 Microsoft Defender for Endpoint 集成</span><span class="sxs-lookup"><span data-stu-id="75504-130">Integrate with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="75504-131">Microsoft Cloud App Security与 Microsoft Defender for Endpoint 本地集成。</span><span class="sxs-lookup"><span data-stu-id="75504-131">Microsoft Cloud App Security integrates with Microsoft Defender for Endpoint natively.</span></span> <span data-ttu-id="75504-132">集成简化了云发现的推出，将云发现功能扩展到企业网络之外，并启用基于设备的调查。</span><span class="sxs-lookup"><span data-stu-id="75504-132">The integration simplifies roll out of Cloud Discovery, extends Cloud Discovery capabilities beyond your corporate network, and enables device-based investigation.</span></span> <span data-ttu-id="75504-133">此集成显示从 IT 托管的设备访问的云Windows 10服务。</span><span class="sxs-lookup"><span data-stu-id="75504-133">This integration reveals cloud apps and services being accessed from IT-managed Windows 10 devices.</span></span> 

<span data-ttu-id="75504-134">如果你已设置 Microsoft Defender for Endpoint，则配置与 云应用安全 的集成是 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="75504-134">If you've already set up Microsoft Defender for Endpoint, configuring integration with Cloud App Security is a toggle in Microsoft 365 Defender.</span></span> <span data-ttu-id="75504-135">启用集成后，你可以返回到 云应用安全门户，并查看云发现仪表板中的丰富数据。</span><span class="sxs-lookup"><span data-stu-id="75504-135">After integration is turned on, you can return to the Cloud App Security portal and view rich data in the Cloud Discovery Dashboard.</span></span>

<span data-ttu-id="75504-136">若要完成这些任务，请参阅[Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration)。</span><span class="sxs-lookup"><span data-stu-id="75504-136">To accomplish these tasks, see [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration).</span></span> 

## <a name="step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies"></a><span data-ttu-id="75504-137">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="75504-137">Step 3.</span></span> <span data-ttu-id="75504-138">在云应用安全和其他代理上部署日志收集器</span><span class="sxs-lookup"><span data-stu-id="75504-138">Deploy the Cloud App Security log collector on your firewalls and other proxies</span></span>

<span data-ttu-id="75504-139">要覆盖连接到网络的所有设备，请将 云应用安全 日志收集器部署到防火墙和其他代理上，以从终结点收集数据并将其发送到 云应用安全 进行分析。</span><span class="sxs-lookup"><span data-stu-id="75504-139">For coverage on all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies to collect data from your endpoints and send it to Cloud App Security for analysis.</span></span> 

<span data-ttu-id="75504-140">如果您使用的是 SWG 中的以下安全 Web 网关 (之) ，云应用安全无缝部署和集成：</span><span class="sxs-lookup"><span data-stu-id="75504-140">If you're using one of the following Secure Web Gateways (SWG), Cloud App Security provides seamless deployment and integration:</span></span>
- <span data-ttu-id="75504-141">Zscaler</span><span class="sxs-lookup"><span data-stu-id="75504-141">Zscaler</span></span>
- <span data-ttu-id="75504-142">iboss</span><span class="sxs-lookup"><span data-stu-id="75504-142">iboss</span></span>
- <span data-ttu-id="75504-143">Corrata</span><span class="sxs-lookup"><span data-stu-id="75504-143">Corrata</span></span>
- <span data-ttu-id="75504-144">Menlo 安全性</span><span class="sxs-lookup"><span data-stu-id="75504-144">Menlo Security</span></span>

<span data-ttu-id="75504-145">有关与这些网络设备集成的信息，请参阅设置 [云发现](/cloud-app-security/set-up-cloud-discovery)。</span><span class="sxs-lookup"><span data-stu-id="75504-145">For more information on integrating with these network devices, see [Set up Cloud Discovery](/cloud-app-security/set-up-cloud-discovery).</span></span> 
## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a><span data-ttu-id="75504-146">步骤 4.</span><span class="sxs-lookup"><span data-stu-id="75504-146">Step 4.</span></span> <span data-ttu-id="75504-147">查看云发现仪表板以查看组织中使用的应用</span><span class="sxs-lookup"><span data-stu-id="75504-147">View the Cloud Discovery dashboard to see what apps are being used in your organization</span></span>

<span data-ttu-id="75504-148">云发现仪表板旨在让你深入了解如何在组织中使用云应用。</span><span class="sxs-lookup"><span data-stu-id="75504-148">The Cloud Discovery dashboard is designed to give you more insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="75504-149">它概述了使用的应用类型、打开的警报以及组织中应用程序的风险级别。</span><span class="sxs-lookup"><span data-stu-id="75504-149">It provides an at-a-glance overview of what kinds of apps are being used, your open alerts, and the risk levels of apps in your organization.</span></span> 

<span data-ttu-id="75504-150">若要开始使用云发现仪表板，请参阅 [使用发现的应用](/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="75504-150">To get started using the Cloud Discovery dashboard, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="next-steps"></a><span data-ttu-id="75504-151">后续步骤</span><span class="sxs-lookup"><span data-stu-id="75504-151">Next steps</span></span>

<span data-ttu-id="75504-152">步骤 3/3：[试点Microsoft Cloud App Security](eval-defender-mcas-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="75504-152">Step 3 of 3: [Pilot Microsoft Cloud App Security](eval-defender-mcas-pilot.md)</span></span>

<span data-ttu-id="75504-153">返回到评估结果[概述Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span><span class="sxs-lookup"><span data-stu-id="75504-153">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="75504-154">返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="75504-154">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>