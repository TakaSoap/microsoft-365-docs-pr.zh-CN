---
title: 配置 Microsoft Cloud App Security 集成
ms.reviewer: ''
description: 了解如何打开设置以启用 Microsoft Defender for Endpoint 与 Microsoft Cloud App Security。
keywords: 云， 应用， 安全性， 设置， 集成， 发现， 报告
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4f7aca5cb532510d55042c70d04d65f2aa08baa3
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844750"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="4f19b-104">在Microsoft Cloud App Security Microsoft Defender for Endpoint 中配置策略</span><span class="sxs-lookup"><span data-stu-id="4f19b-104">Configure Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4f19b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4f19b-105">**Applies to:**</span></span>
- [<span data-ttu-id="4f19b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4f19b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4f19b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4f19b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4f19b-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="4f19b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4f19b-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4f19b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="4f19b-110">若要从适用于终结点的 Microsoft Defender 云应用发现信号中获益，请打开Microsoft Cloud App Security集成。</span><span class="sxs-lookup"><span data-stu-id="4f19b-110">To benefit from Microsoft Defender for Endpoint cloud app discovery signals, turn on Microsoft Cloud App Security integration.</span></span>

>[!NOTE]
><span data-ttu-id="4f19b-111">此功能将在运行[Windows 10](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)版本 1709 (OS 内部版本 16299.1085（具有[KB4493441](https://support.microsoft.com/help/4493441)版本）的设备上随 企业移动性 + 安全性 一起提供) 。 Windows 10，版本 1803 (OS 内部版本 17134.704，包含[KB4493464](https://support.microsoft.com/help/4493464)) 、Windows 10、版本 1809 (OS 内部版本 17763.379（具有[KB4489899](https://support.microsoft.com/help/4489899)) 或更高版本 Windows 10 版本）。</span><span class="sxs-lookup"><span data-stu-id="4f19b-111">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)) or later Windows 10 versions.</span></span>

> <span data-ttu-id="4f19b-112">请参阅[Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration) for Microsoft Defender for Endpoint with Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="4f19b-112">See [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration) for detailed integration of Microsoft Defender for Endpoint with Microsoft Cloud App Security.</span></span> 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="4f19b-113">启用Microsoft Cloud App Security在 Microsoft Defender for Endpoint 中启用</span><span class="sxs-lookup"><span data-stu-id="4f19b-113">Enable Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="4f19b-114">在导航窗格中，选择 **首选项设置**  >  **高级功能**。</span><span class="sxs-lookup"><span data-stu-id="4f19b-114">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="4f19b-115">选择 **Microsoft Cloud App Security，** 将开关切换到 **开**。</span><span class="sxs-lookup"><span data-stu-id="4f19b-115">Select **Microsoft Cloud App Security** and switch the toggle to **On**.</span></span>
3. <span data-ttu-id="4f19b-116">单击 **保存首选项**。</span><span class="sxs-lookup"><span data-stu-id="4f19b-116">Click **Save preferences**.</span></span>

<span data-ttu-id="4f19b-117">激活后，Microsoft Defender for Endpoint 将立即开始将发现信号转发到云应用安全。</span><span class="sxs-lookup"><span data-stu-id="4f19b-117">Once activated, Microsoft Defender for Endpoint will immediately start forwarding discovery signals to Cloud App Security.</span></span>

## <a name="view-the-data-collected"></a><span data-ttu-id="4f19b-118">查看收集的数据</span><span class="sxs-lookup"><span data-stu-id="4f19b-118">View the data collected</span></span>

<span data-ttu-id="4f19b-119">若要查看和访问 Microsoft Cloud Apps Security 中的 Microsoft Defender 终结点数据，请参阅调查 云应用安全 中的[设备](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)。</span><span class="sxs-lookup"><span data-stu-id="4f19b-119">To view and access Microsoft Defender for Endpoint data in Microsoft Cloud Apps Security, see [Investigate devices in Cloud App Security](/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span></span>


<span data-ttu-id="4f19b-120">有关云发现详细信息，请参阅 [使用发现的应用](/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="4f19b-120">For more information about cloud discovery, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

<span data-ttu-id="4f19b-121">如果你有兴趣尝试使用Microsoft Cloud App Security，请参阅Microsoft Cloud App Security[试用版](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)。</span><span class="sxs-lookup"><span data-stu-id="4f19b-121">If you're interested in trying Microsoft Cloud App Security, see [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span></span>

## <a name="related-topic"></a><span data-ttu-id="4f19b-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="4f19b-122">Related topic</span></span>
- [<span data-ttu-id="4f19b-123">Microsoft Cloud App Security集成</span><span class="sxs-lookup"><span data-stu-id="4f19b-123">Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-integration.md)
