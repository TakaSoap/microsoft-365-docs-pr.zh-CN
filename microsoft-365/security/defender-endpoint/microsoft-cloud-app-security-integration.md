---
title: Microsoft Cloud App Security 集成概述
ms.reviewer: ''
description: Microsoft Defender for Endpoint 通过转发云应用安全云应用网络活动与应用集成。
keywords: 云， 应用， 网络， 可见性， 使用情况
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: 5a5a81bde283a9eba4d5db77ed7e4c0b7567abc9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844736"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a><span data-ttu-id="6f061-104">Microsoft Cloud App Security Defender for Endpoint 概述</span><span class="sxs-lookup"><span data-stu-id="6f061-104">Microsoft Cloud App Security in Defender for Endpoint overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="6f061-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="6f061-105">**Applies to:**</span></span>
- [<span data-ttu-id="6f061-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6f061-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6f061-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f061-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="6f061-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="6f061-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6f061-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="6f061-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="6f061-110">Microsoft Cloud App Security (云应用安全) 是一个全面的解决方案，让你能够控制和限制对云应用的访问权限，同时强制执行对云中存储数据的合规性要求，从而了解云应用和服务。</span><span class="sxs-lookup"><span data-stu-id="6f061-110">Microsoft Cloud App Security (Cloud App Security) is a comprehensive solution that gives visibility into cloud apps and services by allowing you to control and limit access to cloud apps, while enforcing compliance requirements on data stored in the cloud.</span></span> <span data-ttu-id="6f061-111">有关详细信息，[请参阅云应用安全。](/cloud-app-security/what-is-cloud-app-security)</span><span class="sxs-lookup"><span data-stu-id="6f061-111">For more information, see [Cloud App Security](/cloud-app-security/what-is-cloud-app-security).</span></span>

>[!NOTE]
><span data-ttu-id="6f061-112">此功能随 E5 许可证[提供，企业移动性 + 安全性](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)版本 1809 或Windows 10设备上使用。</span><span class="sxs-lookup"><span data-stu-id="6f061-112">This feature is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10 version 1809 or later.</span></span>

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a><span data-ttu-id="6f061-113">Microsoft Defender for Endpoint 和 云应用安全 集成</span><span class="sxs-lookup"><span data-stu-id="6f061-113">Microsoft Defender for Endpoint and Cloud App Security integration</span></span> 

<span data-ttu-id="6f061-114">云应用安全依赖于从企业防火墙和代理服务器转发到它的云流量日志。</span><span class="sxs-lookup"><span data-stu-id="6f061-114">Cloud App Security discovery relies on cloud traffic logs being forwarded to it from enterprise firewall and proxy servers.</span></span> <span data-ttu-id="6f061-115">Microsoft Defender for Endpoint 通过收集和转发云应用安全云应用网络活动，从而与云应用集成，从而对云应用使用情况的可见性提高。</span><span class="sxs-lookup"><span data-stu-id="6f061-115">Microsoft Defender for Endpoint integrates with Cloud App Security by collecting and forwarding all cloud app networking activities, providing unparalleled visibility to cloud app usage.</span></span> <span data-ttu-id="6f061-116">监控功能内置于设备中，可提供网络活动的完全覆盖。</span><span class="sxs-lookup"><span data-stu-id="6f061-116">The monitoring functionality is built into the device, providing complete coverage of network activity.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


<span data-ttu-id="6f061-117">集成对现有发现提供了以下主要云应用安全改进：</span><span class="sxs-lookup"><span data-stu-id="6f061-117">The integration provides the following major improvements to the existing Cloud App Security discovery:</span></span> 

- <span data-ttu-id="6f061-118">可在任何位置使用 - 由于网络活动直接从终结点收集，因此无论设备位于公司网络内部还是外部，设备都可用，因为它不再依赖于通过企业防火墙或代理服务器路由的流量。</span><span class="sxs-lookup"><span data-stu-id="6f061-118">Available everywhere - Since the network activity is collected directly from the endpoint, it's available wherever the device is, on or off corporate network, as it's no longer depended on traffic routed through the enterprise firewall or proxy servers.</span></span> 

- <span data-ttu-id="6f061-119">开箱即用，无需配置 - 将云流量日志转发云应用安全防火墙和代理服务器配置。</span><span class="sxs-lookup"><span data-stu-id="6f061-119">Works out of the box, no configuration required - Forwarding cloud traffic logs to Cloud App Security requires firewall and proxy server configuration.</span></span> <span data-ttu-id="6f061-120">使用 Defender for Endpoint 和 云应用安全 集成，无需任何配置。</span><span class="sxs-lookup"><span data-stu-id="6f061-120">With the Defender for Endpoint and Cloud App Security integration, there's no configuration required.</span></span> <span data-ttu-id="6f061-121">只需在Microsoft Defender 安全中心中打开它，你一吧。</span><span class="sxs-lookup"><span data-stu-id="6f061-121">Just switch it on in Microsoft Defender Security Center settings and you're good to go.</span></span> 

- <span data-ttu-id="6f061-122">设备上下文 - 云流量日志缺少设备上下文。</span><span class="sxs-lookup"><span data-stu-id="6f061-122">Device context - Cloud traffic logs lack device context.</span></span> <span data-ttu-id="6f061-123">Defender for Endpoint 网络活动通过设备上下文报告 (哪些设备访问了云应用) ，因此你能够准确了解 (设备) 网络活动的发生位置，以及执行网络活动的 () 用户。</span><span class="sxs-lookup"><span data-stu-id="6f061-123">Defender for Endpoint network activity is reported with the device context (which device accessed the cloud app), so you are able to understand exactly where (device) the network activity took place, in addition to who (user) performed it.</span></span> 

<span data-ttu-id="6f061-124">有关云发现详细信息，请参阅 [使用发现的应用](/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="6f061-124">For more information about cloud discovery, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="related-topic"></a><span data-ttu-id="6f061-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="6f061-125">Related topic</span></span>

- [<span data-ttu-id="6f061-126">配置 Microsoft Cloud App Security 集成</span><span class="sxs-lookup"><span data-stu-id="6f061-126">Configure Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-config.md)
