---
title: Microsoft Cloud App Security 集成概述
ms.reviewer: ''
description: Microsoft Defender for Endpoint 通过转发所有云应用网络活动与 Cloud App Security 集成。
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
ms.openlocfilehash: d756c738f9f61638a9e7424aa3fdf639f8f02f2a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185595"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a><span data-ttu-id="06aa1-104">Defender for Endpoint 中的 Microsoft Cloud App Security 概述</span><span class="sxs-lookup"><span data-stu-id="06aa1-104">Microsoft Cloud App Security in Defender for Endpoint overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="06aa1-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="06aa1-105">**Applies to:**</span></span>
- [<span data-ttu-id="06aa1-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="06aa1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="06aa1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="06aa1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="06aa1-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="06aa1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="06aa1-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="06aa1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="06aa1-110">Microsoft Cloud App Security (Cloud App Security) 是一个全面的解决方案，通过允许您控制和限制对云应用的访问权限，同时对云中存储的数据强制执行合规性要求，可了解云应用和服务。</span><span class="sxs-lookup"><span data-stu-id="06aa1-110">Microsoft Cloud App Security (Cloud App Security) is a comprehensive solution that gives visibility into cloud apps and services by allowing you to control and limit access to cloud apps, while enforcing compliance requirements on data stored in the cloud.</span></span> <span data-ttu-id="06aa1-111">有关详细信息，请参阅[Cloud App Security。](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)</span><span class="sxs-lookup"><span data-stu-id="06aa1-111">For more information, see [Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).</span></span>

>[!NOTE]
><span data-ttu-id="06aa1-112">此功能随 E5 许可证一起提供[](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)，适用于运行 Windows 10 版本 1809 或更高版本的设备上企业移动性 + 安全性。</span><span class="sxs-lookup"><span data-stu-id="06aa1-112">This feature is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10 version 1809 or later.</span></span>

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a><span data-ttu-id="06aa1-113">Microsoft Defender for Endpoint 和 Cloud App Security 集成</span><span class="sxs-lookup"><span data-stu-id="06aa1-113">Microsoft Defender for Endpoint and Cloud App Security integration</span></span> 

<span data-ttu-id="06aa1-114">Cloud App Security 发现依赖于从企业防火墙和代理服务器转发到它的云流量日志。</span><span class="sxs-lookup"><span data-stu-id="06aa1-114">Cloud App Security discovery relies on cloud traffic logs being forwarded to it from enterprise firewall and proxy servers.</span></span> <span data-ttu-id="06aa1-115">Microsoft Defender for Endpoint 通过收集和转发所有云应用网络活动与 Cloud App Security 集成，从而提供云应用使用情况的可见度。</span><span class="sxs-lookup"><span data-stu-id="06aa1-115">Microsoft Defender for Endpoint integrates with Cloud App Security by collecting and forwarding all cloud app networking activities, providing unparalleled visibility to cloud app usage.</span></span> <span data-ttu-id="06aa1-116">监控功能内置于设备中，可提供网络活动的完全覆盖。</span><span class="sxs-lookup"><span data-stu-id="06aa1-116">The monitoring functionality is built into the device, providing complete coverage of network activity.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


<span data-ttu-id="06aa1-117">集成对现有云应用安全发现提供了以下重大改进：</span><span class="sxs-lookup"><span data-stu-id="06aa1-117">The integration provides the following major improvements to the existing Cloud App Security discovery:</span></span> 

- <span data-ttu-id="06aa1-118">可在任何位置使用 - 由于网络活动直接从终结点收集，因此无论设备位于公司网络内部还是外部，设备都可用，因为它不再依赖于通过企业防火墙或代理服务器路由的流量。</span><span class="sxs-lookup"><span data-stu-id="06aa1-118">Available everywhere - Since the network activity is collected directly from the endpoint, it's available wherever the device is, on or off corporate network, as it's no longer depended on traffic routed through the enterprise firewall or proxy servers.</span></span> 

- <span data-ttu-id="06aa1-119">开箱即用，无需配置 - 将云流量日志转发到 Cloud App Security 需要防火墙和代理服务器配置。</span><span class="sxs-lookup"><span data-stu-id="06aa1-119">Works out of the box, no configuration required - Forwarding cloud traffic logs to Cloud App Security requires firewall and proxy server configuration.</span></span> <span data-ttu-id="06aa1-120">借助 Defender for Endpoint 和 Cloud App Security 集成，无需任何配置。</span><span class="sxs-lookup"><span data-stu-id="06aa1-120">With the Defender for Endpoint and Cloud App Security integration, there's no configuration required.</span></span> <span data-ttu-id="06aa1-121">只需在 Microsoft Defender 安全中心设置中打开它，你可继续操作。</span><span class="sxs-lookup"><span data-stu-id="06aa1-121">Just switch it on in Microsoft Defender Security Center settings and you're good to go.</span></span> 

- <span data-ttu-id="06aa1-122">设备上下文 - 云流量日志缺少设备上下文。</span><span class="sxs-lookup"><span data-stu-id="06aa1-122">Device context - Cloud traffic logs lack device context.</span></span> <span data-ttu-id="06aa1-123">Defender for Endpoint 网络活动通过设备上下文报告 (哪些设备访问了云应用) ，因此你能够准确了解 (设备) 网络活动的发生位置，以及执行网络活动的 () 用户。</span><span class="sxs-lookup"><span data-stu-id="06aa1-123">Defender for Endpoint network activity is reported with the device context (which device accessed the cloud app), so you are able to understand exactly where (device) the network activity took place, in addition to who (user) performed it.</span></span> 

<span data-ttu-id="06aa1-124">有关云发现详细信息，请参阅 [使用发现的应用](https://docs.microsoft.com/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="06aa1-124">For more information about cloud discovery, see [Working with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

## <a name="related-topic"></a><span data-ttu-id="06aa1-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="06aa1-125">Related topic</span></span>

- [<span data-ttu-id="06aa1-126">配置 Microsoft Cloud App Security 集成</span><span class="sxs-lookup"><span data-stu-id="06aa1-126">Configure Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-config.md)
