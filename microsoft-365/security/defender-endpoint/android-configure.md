---
title: 在 Android 功能上配置 Microsoft Defender for Endpoint
description: 介绍如何在 Android 上配置适用于终结点的 Microsoft Defender
keywords: microsoft， defender， Microsoft Defender for Endpoint， mde， android， 配置
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 462fa6177ee35d5d988efa985422b499e2339ff4
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935313"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a><span data-ttu-id="0b95d-104">在 Android 功能上配置适用于终结点的 Defender</span><span class="sxs-lookup"><span data-stu-id="0b95d-104">Configure Defender for Endpoint on Android features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0b95d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="0b95d-105">**Applies to:**</span></span>
- [<span data-ttu-id="0b95d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0b95d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0b95d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b95d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a><span data-ttu-id="0b95d-108">在 Android 上通过 Defender for Endpoint 进行条件访问</span><span class="sxs-lookup"><span data-stu-id="0b95d-108">Conditional Access with Defender for Endpoint on Android</span></span>  
<span data-ttu-id="0b95d-109">Android 上的 Microsoft Defender for Endpoint 以及 Microsoft Intune 和 Azure Active Directory 支持根据设备风险级别强制执行设备合规性和条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="0b95d-109">Microsoft Defender for Endpoint on Android along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="0b95d-110">Defender for Endpoint 是移动威胁防护 (MTD) 解决方案，你可以部署该解决方案以通过 Intune 利用此功能。</span><span class="sxs-lookup"><span data-stu-id="0b95d-110">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="0b95d-111">若要详细了解如何在 Android 和条件访问上设置适用于终结点的 Defender，请参阅[Defender for Endpoint 和 Intune。](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="0b95d-111">For more information about how to set up Defender for Endpoint on Android and Conditional Access, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="0b95d-112">配置自定义指示器</span><span class="sxs-lookup"><span data-stu-id="0b95d-112">Configure custom indicators</span></span>  

> [!NOTE]
> <span data-ttu-id="0b95d-113">Android 上的 Defender for Endpoint 仅支持为 IP 地址和 URL/域创建自定义指示器。</span><span class="sxs-lookup"><span data-stu-id="0b95d-113">Defender for Endpoint on Android only supports creating custom indicators for IP addresses and URLs/domains.</span></span>

<span data-ttu-id="0b95d-114">Android 上的 Defender for Endpoint 使管理员能够配置自定义指示器以支持 Android 设备。</span><span class="sxs-lookup"><span data-stu-id="0b95d-114">Defender for Endpoint on Android enables admins to configure custom indicators to support Android devices as well.</span></span> <span data-ttu-id="0b95d-115">若要详细了解如何配置自定义指示器，请参阅管理 [指示器](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="0b95d-115">For more information on how to configure custom indicators, see [Manage indicators](manage-indicators.md).</span></span>

## <a name="configure-web-protection"></a><span data-ttu-id="0b95d-116">配置 Web 保护</span><span class="sxs-lookup"><span data-stu-id="0b95d-116">Configure web protection</span></span>
<span data-ttu-id="0b95d-117">Android 上的 Defender for Endpoint 允许 IT 管理员配置 Web 保护功能。</span><span class="sxs-lookup"><span data-stu-id="0b95d-117">Defender for Endpoint on Android allows IT Administrators the ability to configure the web protection feature.</span></span> <span data-ttu-id="0b95d-118">此功能在 Microsoft Endpoint Manager 管理中心内可用。</span><span class="sxs-lookup"><span data-stu-id="0b95d-118">This capability is available within the Microsoft Endpoint Manager Admin center.</span></span>

> [!NOTE]
> <span data-ttu-id="0b95d-119">Android 上的 Defender for Endpoint 将使用 VPN 来提供 Web 保护功能。</span><span class="sxs-lookup"><span data-stu-id="0b95d-119">Defender for Endpoint on Android would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="0b95d-120">这不是常规 VPN，它是不接受设备外流量的本地/自循环 VPN。</span><span class="sxs-lookup"><span data-stu-id="0b95d-120">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span> <span data-ttu-id="0b95d-121">有关详细信息，请参阅在运行 [Android 的设备上配置 Web 保护](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)。</span><span class="sxs-lookup"><span data-stu-id="0b95d-121">For more information, see [Configure web protection on devices that run Android](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0b95d-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="0b95d-122">Related topics</span></span>
- [<span data-ttu-id="0b95d-123">Android 上的 Microsoft Defender for Endpoint 概述</span><span class="sxs-lookup"><span data-stu-id="0b95d-123">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="0b95d-124">使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0b95d-124">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
