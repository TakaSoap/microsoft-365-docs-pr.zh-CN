---
title: 解决 Microsoft 威胁防护服务问题
description: 查找已知 Microsoft 威胁防护问题的解决方案和变通方法
keywords: 解决 Microsoft 威胁防护服务问题, 疑难解答, 问题
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
ms.openlocfilehash: 2f7faec3223ca707e166c229b48093193be09d1e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599969"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="d9954-104">解决 Microsoft 威胁防护服务问题</span><span class="sxs-lookup"><span data-stu-id="d9954-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

<span data-ttu-id="d9954-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d9954-105">**Applies to:**</span></span>
- <span data-ttu-id="d9954-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="d9954-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="d9954-107">本节介绍使用 Microsoft 威胁防护服务时可能会出现的问题。</span><span class="sxs-lookup"><span data-stu-id="d9954-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="not-seeing-microsoft-threat-protection-content"></a><span data-ttu-id="d9954-108">看不到 Microsoft 威胁防护内容</span><span class="sxs-lookup"><span data-stu-id="d9954-108">Not seeing Microsoft Threat Protection content</span></span>
<span data-ttu-id="d9954-109">如果在门户中看不到导航页面上的功能（如事件、操作中心或搜索），需要验证租户是否持有相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="d9954-109">If you don't see capabilities on the navigation page such as the Incidents, Action Center, or Hunting in your portal you'll need to verify that your tenant has the appropriate license.</span></span> 

<span data-ttu-id="d9954-110">有关详细信息，请参阅[必备条件](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="d9954-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="d9954-111">Azure ATP 警报未在 Microsoft 威胁防护事件中显示</span><span class="sxs-lookup"><span data-stu-id="d9954-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="d9954-112">如果在环境中部署了 Azure ATP，但在 Microsoft 威胁防护事件中看不到 Azure ATP 警报，需要确保启用 Microsoft Cloud App Security 和 Azure ATP 集成。</span><span class="sxs-lookup"><span data-stu-id="d9954-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="d9954-113">有关详细信息，请参阅[Azure ATP 集成](https://docs.microsoft.com/cloud-app-security/aatp-integration)。</span><span class="sxs-lookup"><span data-stu-id="d9954-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="d9954-114">Microsoft 威胁防护是否可供美国政府社区云（GCC）或 GCC High使用？</span><span class="sxs-lookup"><span data-stu-id="d9954-114">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="d9954-115">目前不可用。</span><span class="sxs-lookup"><span data-stu-id="d9954-115">At the moment, it is not available.</span></span> 


