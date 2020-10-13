---
title: 配置和管理 Microsoft Defender ATP 功能
ms.reviewer: ''
description: 配置和管理 Microsoft Defender ATP 功能，如攻击面降低、下一代保护和安全控制
keywords: 配置、管理、功能、攻击面降低、下一代保护、安全控制、终结点检测和响应、自动调查和修正、安全控制、控制
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 64c6e5f7eefad50aa59301de3fd46cae60d6876f
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429427"
---
# <a name="configure-and-manage-microsoft-defender-atp-capabilities"></a><span data-ttu-id="df986-104">配置和管理 Microsoft Defender ATP 功能</span><span class="sxs-lookup"><span data-stu-id="df986-104">Configure and manage Microsoft Defender ATP capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="df986-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="df986-105">**Applies to:**</span></span>

- [<span data-ttu-id="df986-106">Microsoft Defender 高级威胁防护 (Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="df986-106">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="df986-107">配置和管理所有 Microsoft Defender ATP 功能，以获取组织的最佳安全保护。</span><span class="sxs-lookup"><span data-stu-id="df986-107">Configure and manage all the Microsoft Defender ATP capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="df986-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="df986-108">In this section</span></span> 
<span data-ttu-id="df986-109">主题</span><span class="sxs-lookup"><span data-stu-id="df986-109">Topic</span></span> | <span data-ttu-id="df986-110">说明</span><span class="sxs-lookup"><span data-stu-id="df986-110">Description</span></span> 
:---|:---
[<span data-ttu-id="df986-111">配置攻击面减少功能</span><span class="sxs-lookup"><span data-stu-id="df986-111">Configure attack surface reduction capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="df986-112">通过确保正确设置了配置设置并应用了利用缓解技术，这些功能组可抵御攻击和 exploitations。</span><span class="sxs-lookup"><span data-stu-id="df986-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitations.</span></span> 
[<span data-ttu-id="df986-113">配置下一代保护</span><span class="sxs-lookup"><span data-stu-id="df986-113">Configure next generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="df986-114">配置下一代保护以捕捉所有类型的新兴威胁。</span><span class="sxs-lookup"><span data-stu-id="df986-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="df986-115">配置 Microsoft 威胁专家功能</span><span class="sxs-lookup"><span data-stu-id="df986-115">Configure Microsoft Threat Experts capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="df986-116">配置和管理你希望从 Microsoft 威胁专家获取 cybersecurity 威胁情报的方式。</span><span class="sxs-lookup"><span data-stu-id="df986-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="df986-117">配置 Microsoft 威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="df986-117">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="df986-118">配置与 Microsoft Defender ATP 集成的其他解决方案。</span><span class="sxs-lookup"><span data-stu-id="df986-118">Configure other solutions that integrate with Microsoft Defender ATP.</span></span>
[<span data-ttu-id="df986-119">管理和 API 支持</span><span class="sxs-lookup"><span data-stu-id="df986-119">Management and API support</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="df986-120">将警报拉出给 SIEM 或使用 Api 创建自定义警报。</span><span class="sxs-lookup"><span data-stu-id="df986-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="df986-121">创建和构建 Power BI 报告。</span><span class="sxs-lookup"><span data-stu-id="df986-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="df986-122">配置 Microsoft Defender 安全中心设置</span><span class="sxs-lookup"><span data-stu-id="df986-122">Configure Microsoft Defender Security Center settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="df986-123">配置与门户相关的设置，如常规设置、高级功能、启用预览体验和其他设置。</span><span class="sxs-lookup"><span data-stu-id="df986-123">Configure portal related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



