---
title: 配置 Microsoft Cloud App Security 集成
ms.reviewer: ''
description: 了解如何启用设置以启用 Microsoft Defender 终结点与 Microsoft Cloud App Security 集成。
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
ms.openlocfilehash: ddf32b26191826ab6ecbad6b9d047ac7bbb6276a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056526"
---
# <a name="configure-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="dbd70-104">在 Microsoft Defender for Endpoint 中配置 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="dbd70-104">Configure Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dbd70-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="dbd70-105">**Applies to:**</span></span>
- [<span data-ttu-id="dbd70-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dbd70-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="dbd70-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dbd70-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="dbd70-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="dbd70-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dbd70-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="dbd70-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="dbd70-110">若要从适用于 Endpoint 的 Microsoft Defender 云应用发现信号中获益，请启用 Microsoft Cloud App Security 集成。</span><span class="sxs-lookup"><span data-stu-id="dbd70-110">To benefit from Microsoft Defender for Endpoint cloud app discovery signals, turn on Microsoft Cloud App Security integration.</span></span>

>[!NOTE]
><span data-ttu-id="dbd70-111">此功能将在运行 Windows 10 版本 1709 (OS 内部版本 16299.1085（具有[KB4493441](https://support.microsoft.com/help/4493441)版本）的设备上提供企业移动性[+](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)安全性的 E5) ， Windows 10 版本 1803 (OS 内部版本 17134.704（带[KB4493464](https://support.microsoft.com/help/4493464)) 、Windows 10 版本 1809 (操作系统版本 17763.379，具有[KB4489899](https://support.microsoft.com/help/4489899)) 或更高版本的 Windows 10 版本）。</span><span class="sxs-lookup"><span data-stu-id="dbd70-111">This feature will be available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10, version 1709 (OS Build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, version 1803 (OS Build 17134.704 with [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, version 1809 (OS Build 17763.379 with [KB4489899](https://support.microsoft.com/help/4489899)) or later Windows 10 versions.</span></span>

> <span data-ttu-id="dbd70-112">有关 Microsoft Defender for Endpoint 与 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration) 的详细集成，请参阅 Microsoft Defender for Endpoint integration with Microsoft Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="dbd70-112">See [Microsoft Defender for Endpoint integration with Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration) for detailed integration of Microsoft Defender for Endpoint with Microsoft Cloud App Security.</span></span> 

## <a name="enable-microsoft-cloud-app-security-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="dbd70-113">在 Microsoft Defender for Endpoint 中启用 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="dbd70-113">Enable Microsoft Cloud App Security in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="dbd70-114">在导航窗格中，选择 **首选项设置**  >  **高级功能**。</span><span class="sxs-lookup"><span data-stu-id="dbd70-114">In the navigation pane, select **Preferences setup** > **Advanced features**.</span></span>
2. <span data-ttu-id="dbd70-115">选择 **"Microsoft Cloud App Security"，** 将开关切换到 **"开"。**</span><span class="sxs-lookup"><span data-stu-id="dbd70-115">Select **Microsoft Cloud App Security** and switch the toggle to **On**.</span></span>
3. <span data-ttu-id="dbd70-116">单击 **保存首选项**。</span><span class="sxs-lookup"><span data-stu-id="dbd70-116">Click **Save preferences**.</span></span>

<span data-ttu-id="dbd70-117">激活后，Microsoft Defender for Endpoint 将立即开始将发现信号转发到 Cloud App Security。</span><span class="sxs-lookup"><span data-stu-id="dbd70-117">Once activated, Microsoft Defender for Endpoint will immediately start forwarding discovery signals to Cloud App Security.</span></span>

## <a name="view-the-data-collected"></a><span data-ttu-id="dbd70-118">查看收集的数据</span><span class="sxs-lookup"><span data-stu-id="dbd70-118">View the data collected</span></span>

<span data-ttu-id="dbd70-119">若要查看和访问 Microsoft Cloud Apps Security 中的 Microsoft Defender for Endpoint 数据，请参阅调查 [Cloud App Security 中的设备](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security)。</span><span class="sxs-lookup"><span data-stu-id="dbd70-119">To view and access Microsoft Defender for Endpoint data in Microsoft Cloud Apps Security, see [Investigate devices in Cloud App Security](https://docs.microsoft.com/cloud-app-security/mde-integration#investigate-devices-in-cloud-app-security).</span></span>


<span data-ttu-id="dbd70-120">有关云发现详细信息，请参阅 [使用发现的应用](https://docs.microsoft.com/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="dbd70-120">For more information about cloud discovery, see [Working with discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

<span data-ttu-id="dbd70-121">如果你对试用 Microsoft Cloud App Security 感兴趣，请参阅 [Microsoft Cloud App Security 试用版](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1)。</span><span class="sxs-lookup"><span data-stu-id="dbd70-121">If you're interested in trying Microsoft Cloud App Security, see [Microsoft Cloud App Security Trial](https://signup.microsoft.com/Signup?OfferId=757c4c34-d589-46e4-9579-120bba5c92ed&ali=1).</span></span>

## <a name="related-topic"></a><span data-ttu-id="dbd70-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="dbd70-122">Related topic</span></span>
- [<span data-ttu-id="dbd70-123">Microsoft Cloud App Security 集成</span><span class="sxs-lookup"><span data-stu-id="dbd70-123">Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-integration.md)
