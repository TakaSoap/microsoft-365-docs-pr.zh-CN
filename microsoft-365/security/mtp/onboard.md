---
title: 配置和管理适用于终结点的 Microsoft Defender 功能
ms.reviewer: ''
description: 配置和管理适用于终结点的 Microsoft Defender 功能，例如攻击面减少和下一代保护
keywords: 配置， 管理， 功能， 攻击面减少， 下一代保护， 安全控制， 终结点检测和响应， 自动调查和修正， 安全控制， 控制
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c3bb09820f4a22c8ecb1e49c699db5b6f4cabc68
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928612"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="b3082-104">配置和管理适用于终结点的 Microsoft Defender 功能</span><span class="sxs-lookup"><span data-stu-id="b3082-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b3082-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b3082-105">**Applies to:**</span></span>

- [<span data-ttu-id="b3082-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b3082-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="b3082-107">配置和管理所有 Microsoft Defender for Endpoint 功能，为组织提供最佳安全保护。</span><span class="sxs-lookup"><span data-stu-id="b3082-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="b3082-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="b3082-108">In this section</span></span> 
<span data-ttu-id="b3082-109">主题</span><span class="sxs-lookup"><span data-stu-id="b3082-109">Topic</span></span> | <span data-ttu-id="b3082-110">说明</span><span class="sxs-lookup"><span data-stu-id="b3082-110">Description</span></span> 
:---|:---
[<span data-ttu-id="b3082-111">配置攻击面减少功能</span><span class="sxs-lookup"><span data-stu-id="b3082-111">Configure attack surface reduction capabilities</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="b3082-112">通过确保正确设置配置设置并应用攻击缓解技术，这些功能集可抵御攻击和利用。</span><span class="sxs-lookup"><span data-stu-id="b3082-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="b3082-113">配置下一代保护</span><span class="sxs-lookup"><span data-stu-id="b3082-113">Configure next generation protection</span></span>](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="b3082-114">配置下一代保护，以捕获所有类型的新兴威胁。</span><span class="sxs-lookup"><span data-stu-id="b3082-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="b3082-115">配置 Microsoft 威胁专家功能</span><span class="sxs-lookup"><span data-stu-id="b3082-115">Configure Microsoft Threat Experts capabilities</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="b3082-116">配置和管理希望如何从 Microsoft 威胁专家获取网络安全威胁智能。</span><span class="sxs-lookup"><span data-stu-id="b3082-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="b3082-117">配置 Microsoft 365 Defender 集成</span><span class="sxs-lookup"><span data-stu-id="b3082-117">Configure Microsoft 365 Defender integration</span></span>](/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="b3082-118">配置与 Microsoft Defender for Endpoint 集成的其他解决方案。</span><span class="sxs-lookup"><span data-stu-id="b3082-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="b3082-119">管理和 API 支持</span><span class="sxs-lookup"><span data-stu-id="b3082-119">Management and API support</span></span>](/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="b3082-120">将警报拉取到 SIEM 或使用 API 创建自定义警报。</span><span class="sxs-lookup"><span data-stu-id="b3082-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="b3082-121">创建和生成 Power BI 报表。</span><span class="sxs-lookup"><span data-stu-id="b3082-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="b3082-122">配置 Microsoft Defender 安全中心设置</span><span class="sxs-lookup"><span data-stu-id="b3082-122">Configure Microsoft Defender Security Center settings</span></span>](/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="b3082-123">配置与门户相关的设置，如常规设置、高级功能、启用预览体验和其他设置。</span><span class="sxs-lookup"><span data-stu-id="b3082-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>