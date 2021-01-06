---
title: Microsoft 365 Defender 服务问题疑难解答
description: 查找解决方案并解决已知的 Microsoft 365 Defender 问题
keywords: Microsoft 威胁防护疑难解答， 疑难解答， Azure ATP， 问题， 加载项， 设置页面
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
ms.openlocfilehash: b7b6ea55d084c114b79dfee0e061b09c8ede8632
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760454"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="692c7-104">Microsoft 365 Defender 服务问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="692c7-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="692c7-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="692c7-105">**Applies to:**</span></span>
- <span data-ttu-id="692c7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="692c7-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="692c7-107">本部分介绍使用 Microsoft 365 Defender 服务时可能出现的问题。</span><span class="sxs-lookup"><span data-stu-id="692c7-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="692c7-108">我看不到 Microsoft 365 Defender 内容</span><span class="sxs-lookup"><span data-stu-id="692c7-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="692c7-109">如果在导航窗格中看不到功能，如门户中的事件、操作中心或搜寻，则需要验证租户是否具有相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="692c7-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="692c7-110">有关详细信息，请参阅[必备条件](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="692c7-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="692c7-111">Microsoft Defender for Identity 警报未显示在 Microsoft 365 Defender 事件中</span><span class="sxs-lookup"><span data-stu-id="692c7-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="692c7-112">如果你的环境中部署了 Microsoft Defender for Identity，但看不到 Defender for Identity 警报作为 Microsoft 365 Defender 事件的一部分，则需要确保 Microsoft Cloud App Security 和 Defender for Identity 集成已启用。</span><span class="sxs-lookup"><span data-stu-id="692c7-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="692c7-113">有关详细信息，请参阅 [Microsoft Defender for Identity 集成](https://docs.microsoft.com/cloud-app-security/mdi-integration)。</span><span class="sxs-lookup"><span data-stu-id="692c7-113">For more information, see [Microsoft Defender for Identity integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="692c7-114">用于打开服务的设置页在哪里？</span><span class="sxs-lookup"><span data-stu-id="692c7-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="692c7-115">若要打开 Microsoft 365 Defender，请从 Microsoft 365 安全中心的导航窗格中访问"设置"。 </span><span class="sxs-lookup"><span data-stu-id="692c7-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="692c7-116">只有拥有必备权限和许可证时，才能看到 [此导航项](mtp-enable.md#check-license-eligibility-and-required-permissions)。</span><span class="sxs-lookup"><span data-stu-id="692c7-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
