---
title: 解决 Microsoft 365 Defender 服务问题
description: 查找已知解决方案和解决方法Microsoft 365 Defender 问题
keywords: 疑Microsoft 365 Defender， 疑难解答， Microsoft Defender for Identity， 问题， 加载项， 设置页面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0c933edfe80275dbfa60464ff862a7609b269332
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933393"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="5a5f4-104">解决 Microsoft 365 Defender 服务问题</span><span class="sxs-lookup"><span data-stu-id="5a5f4-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5a5f4-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="5a5f4-105">**Applies to:**</span></span>
- <span data-ttu-id="5a5f4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5a5f4-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5a5f4-107">本部分解决使用 Defender 服务时可能出现的Microsoft 365问题。</span><span class="sxs-lookup"><span data-stu-id="5a5f4-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="5a5f4-108">我看不到Microsoft 365 Defender 内容</span><span class="sxs-lookup"><span data-stu-id="5a5f4-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="5a5f4-109">如果在门户中看不到导航窗格上的功能，如事件、操作中心或搜寻，则需要验证租户是否具有相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="5a5f4-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="5a5f4-110">有关详细信息，请参阅[先决条件](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="5a5f4-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="5a5f4-111">Microsoft Defender 标识警报未显示在 Microsoft 365 Defender 事件中</span><span class="sxs-lookup"><span data-stu-id="5a5f4-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="5a5f4-112">如果你的环境中已部署 Microsoft Defender for Identity，但没有在 Microsoft 365 Defender 事件中看到 Defender for Identity 警报，则需要确保已启用 Microsoft Cloud App Security 和 Defender for Identity 集成。</span><span class="sxs-lookup"><span data-stu-id="5a5f4-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="5a5f4-113">有关详细信息，请参阅 [Microsoft Defender 的标识集成](/cloud-app-security/mdi-integration)。</span><span class="sxs-lookup"><span data-stu-id="5a5f4-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a><span data-ttu-id="5a5f4-114">用于打开服务的设置页在哪里？</span><span class="sxs-lookup"><span data-stu-id="5a5f4-114">Where is the settings page for turning on the service?</span></span>

<span data-ttu-id="5a5f4-115">若要打开 Microsoft 365 Defender，设置安全中心中的导航Microsoft 365访问。</span><span class="sxs-lookup"><span data-stu-id="5a5f4-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="5a5f4-116">只有拥有必备权限和许可证 时，此 [导航项才可见](m365d-enable.md#check-license-eligibility-and-required-permissions)。</span><span class="sxs-lookup"><span data-stu-id="5a5f4-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](m365d-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a><span data-ttu-id="5a5f4-117">如何为文件/URL 创建异常？</span><span class="sxs-lookup"><span data-stu-id="5a5f4-117">How do I create an exception for my file/URL?</span></span>

<span data-ttu-id="5a5f4-118">误报是一种文件或 URL，被检测为恶意文件，但不是威胁。</span><span class="sxs-lookup"><span data-stu-id="5a5f4-118">A false positive is a file or URL that is detected as malicious but is not a threat.</span></span> <span data-ttu-id="5a5f4-119">你可以创建指示器并定义排除项以取消阻止并允许某些文件/URL。</span><span class="sxs-lookup"><span data-stu-id="5a5f4-119">You can create indicators and define exclusions to unblock and allow certain files/URLs.</span></span> <span data-ttu-id="5a5f4-120">请参阅在 Defender for Endpoint 中解决 [误报/负数](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)。</span><span class="sxs-lookup"><span data-stu-id="5a5f4-120">See [Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span></span>


