---
title: Microsoft 365 Defender 服务问题疑难解答
description: 查找解决方案并解决已知的 Microsoft 365 Defender 问题
keywords: Microsoft 威胁防护疑难解答， 疑难解答， Azure ATP， 问题， 加载项， 设置页面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: d01912532ad2a00abbecee0d0a337be7baf87017
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918662"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="52c3a-104">Microsoft 365 Defender 服务问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="52c3a-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="52c3a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="52c3a-105">**Applies to:**</span></span>
- <span data-ttu-id="52c3a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="52c3a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="52c3a-107">本部分解决使用 Microsoft 365 Defender 服务时可能出现的问题。</span><span class="sxs-lookup"><span data-stu-id="52c3a-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="52c3a-108">我看不到 Microsoft 365 Defender 内容</span><span class="sxs-lookup"><span data-stu-id="52c3a-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="52c3a-109">如果在门户中看不到导航窗格上的功能，如事件、操作中心或搜寻，则需要验证租户是否具有相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="52c3a-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="52c3a-110">有关详细信息，请参阅[必备条件](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="52c3a-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="52c3a-111">Microsoft 365 Defender 事件中未显示 Microsoft Defender 标识警报</span><span class="sxs-lookup"><span data-stu-id="52c3a-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="52c3a-112">如果你的环境中已部署 Microsoft Defender for Identity，但没有在 Microsoft 365 Defender 事件中看到 Defender for Identity 警报，则需要确保 Microsoft Cloud App Security 和 Defender for Identity 集成已启用。</span><span class="sxs-lookup"><span data-stu-id="52c3a-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="52c3a-113">有关详细信息，请参阅 [Microsoft Defender 的标识集成](/cloud-app-security/mdi-integration)。</span><span class="sxs-lookup"><span data-stu-id="52c3a-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="52c3a-114">用于打开服务的设置页在哪里？</span><span class="sxs-lookup"><span data-stu-id="52c3a-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="52c3a-115">若要打开 Microsoft 365 Defender， **请从** Microsoft 365 安全中心的导航窗格中访问设置。</span><span class="sxs-lookup"><span data-stu-id="52c3a-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="52c3a-116">只有拥有必备权限和许可证 时，此 [导航项才可见](mtp-enable.md#check-license-eligibility-and-required-permissions)。</span><span class="sxs-lookup"><span data-stu-id="52c3a-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>