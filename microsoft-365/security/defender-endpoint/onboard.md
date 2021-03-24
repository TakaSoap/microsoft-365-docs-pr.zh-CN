---
title: 配置和管理 Microsoft Defender ATP 功能
ms.reviewer: ''
description: 配置和管理 Microsoft Defender ATP 功能，如攻击面减少和下一代保护
keywords: 配置， 管理， 功能， 攻击面减少， 下一代保护， 安全控制， 终结点检测和响应， 自动调查和修正， 安全控制， 控制
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
ms.technology: mde
ms.openlocfilehash: e2082929cf1fb7f4b55331cf62adcd9b936168d0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054667"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="ca197-104">配置和管理适用于终结点的 Microsoft Defender 功能</span><span class="sxs-lookup"><span data-stu-id="ca197-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ca197-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ca197-105">**Applies to:**</span></span>
- [<span data-ttu-id="ca197-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ca197-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="ca197-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ca197-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ca197-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="ca197-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ca197-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="ca197-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="ca197-110">配置和管理所有 Defender for Endpoint 功能，为组织提供最佳安全保护。</span><span class="sxs-lookup"><span data-stu-id="ca197-110">Configure and manage all the Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="ca197-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="ca197-111">In this section</span></span> 
<span data-ttu-id="ca197-112">主题</span><span class="sxs-lookup"><span data-stu-id="ca197-112">Topic</span></span> | <span data-ttu-id="ca197-113">说明</span><span class="sxs-lookup"><span data-stu-id="ca197-113">Description</span></span> 
:---|:---
[<span data-ttu-id="ca197-114">配置攻击面减少功能</span><span class="sxs-lookup"><span data-stu-id="ca197-114">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) |  <span data-ttu-id="ca197-115">通过确保正确设置配置设置并应用攻击缓解技术，这些功能集可抵御攻击和利用。</span><span class="sxs-lookup"><span data-stu-id="ca197-115">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="ca197-116">配置下一代保护</span><span class="sxs-lookup"><span data-stu-id="ca197-116">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="ca197-117">配置下一代保护，以捕获所有类型的新兴威胁。</span><span class="sxs-lookup"><span data-stu-id="ca197-117">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="ca197-118">配置 Microsoft 威胁专家功能</span><span class="sxs-lookup"><span data-stu-id="ca197-118">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="ca197-119">配置和管理希望如何从 Microsoft 威胁专家获取网络安全威胁智能。</span><span class="sxs-lookup"><span data-stu-id="ca197-119">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="ca197-120">配置 Microsoft 威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="ca197-120">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration)| <span data-ttu-id="ca197-121">配置与 Defender for Endpoint 集成的其他解决方案。</span><span class="sxs-lookup"><span data-stu-id="ca197-121">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="ca197-122">管理和 API 支持</span><span class="sxs-lookup"><span data-stu-id="ca197-122">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis)| <span data-ttu-id="ca197-123">将警报拉取到 SIEM 或使用 API 创建自定义警报。</span><span class="sxs-lookup"><span data-stu-id="ca197-123">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="ca197-124">创建和生成 Power BI 报表。</span><span class="sxs-lookup"><span data-stu-id="ca197-124">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="ca197-125">配置 Microsoft Defender 安全中心设置</span><span class="sxs-lookup"><span data-stu-id="ca197-125">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) |  <span data-ttu-id="ca197-126">配置与门户相关的设置，如常规设置、高级功能、启用预览体验和其他设置。</span><span class="sxs-lookup"><span data-stu-id="ca197-126">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



