---
title: 解决 Microsoft 365 Defender 服务问题
description: 查找已知 Microsoft 365 Defender 问题的解决方案和解决办法
keywords: 解决 Microsoft 威胁防护、故障排除、Azure ATP、问题、加载项、设置页面
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 16cb1116f400c8d0a83ccc4cac23da06cd1be2a4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844664"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="74939-104">解决 Microsoft 365 Defender 服务问题</span><span class="sxs-lookup"><span data-stu-id="74939-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="74939-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="74939-105">**Applies to:**</span></span>
- <span data-ttu-id="74939-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74939-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="74939-107">本节介绍在使用 Microsoft 365 Defender 服务时可能出现的问题。</span><span class="sxs-lookup"><span data-stu-id="74939-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>


## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="74939-108">我看不到 Microsoft 365 Defender 内容</span><span class="sxs-lookup"><span data-stu-id="74939-108">I don't see Microsoft 365 Defender content</span></span>
<span data-ttu-id="74939-109">如果您在门户中看不到导航窗格中的功能（如事件、操作中心或搜寻），则需要验证您的租户是否具有相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="74939-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="74939-110">有关详细信息，请参阅[必备条件](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="74939-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="74939-111">Microsoft 无法在 Microsoft 365 Defender 事件中显示标识警报的 microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="74939-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>
<span data-ttu-id="74939-112">如果你已在你的环境中部署了 Microsoft Defender，但你没有在 Microsoft 365 Defender 事件中看到标识警报的 Defender，则需要确保已启用 Microsoft 云应用安全和 Defender for Identity 集成。</span><span class="sxs-lookup"><span data-stu-id="74939-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span> 

<span data-ttu-id="74939-113">有关详细信息，请参阅 [Microsoft Defender For Identity integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)。</span><span class="sxs-lookup"><span data-stu-id="74939-113">For more information, see [Microsoft Defender for Identity integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="74939-114">打开服务的设置页面在什么位置？</span><span class="sxs-lookup"><span data-stu-id="74939-114">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="74939-115">若要打开 Microsoft 365 Defender，请访问 Microsoft 365 安全中心导航窗格中的 **设置** 。</span><span class="sxs-lookup"><span data-stu-id="74939-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="74939-116">仅当您具有 [必备权限和许可证](mtp-enable.md#check-license-eligibility-and-required-permissions)时，才会看到此导航项。</span><span class="sxs-lookup"><span data-stu-id="74939-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
 

