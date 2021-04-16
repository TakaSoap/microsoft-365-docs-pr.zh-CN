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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3ad23e030048506784edd8f1988fa33263a085ae
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861331"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="d9303-104">配置和管理适用于终结点的 Microsoft Defender 功能</span><span class="sxs-lookup"><span data-stu-id="d9303-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d9303-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d9303-105">**Applies to:**</span></span>

- [<span data-ttu-id="d9303-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d9303-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d9303-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9303-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d9303-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="d9303-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d9303-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="d9303-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="d9303-110">了解如何配置和管理适用于终结点功能的 Defender，以为组织提供最佳安全保护。</span><span class="sxs-lookup"><span data-stu-id="d9303-110">Learn how to configure and manage Defender for Endpoint features, to get the best security protection for your organization.</span></span>

<span data-ttu-id="d9303-111">有关在组织中连接新设备的实用建议，请参阅将设备载入 [到 Microsoft Defender for Endpoint 服务](./onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="d9303-111">For practical advice on connecting new devices in your organization, see [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d9303-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="d9303-112">In this section</span></span>

<span data-ttu-id="d9303-113">主题</span><span class="sxs-lookup"><span data-stu-id="d9303-113">Topic</span></span> | <span data-ttu-id="d9303-114">说明</span><span class="sxs-lookup"><span data-stu-id="d9303-114">Description</span></span>
:---|:---
[<span data-ttu-id="d9303-115">配置 Microsoft Defender 安全中心设置</span><span class="sxs-lookup"><span data-stu-id="d9303-115">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="d9303-116">配置与门户相关的设置，如常规设置、高级功能或启用预览体验。</span><span class="sxs-lookup"><span data-stu-id="d9303-116">Configure portal-related settings such as general settings, advanced features, or enable the preview experience.</span></span>
[<span data-ttu-id="d9303-117">配置攻击面减少功能</span><span class="sxs-lookup"><span data-stu-id="d9303-117">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) | <span data-ttu-id="d9303-118">配置攻击面减少功能，以确保正确应用设置，并设置攻击缓解技术。</span><span class="sxs-lookup"><span data-stu-id="d9303-118">Configure attack surface reduction capabilities, to ensure that settings are properly applied, and exploit mitigation techniques are set.</span></span>
[<span data-ttu-id="d9303-119">配置下一代保护</span><span class="sxs-lookup"><span data-stu-id="d9303-119">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="d9303-120">配置下一代保护，以捕获所有类型的新兴威胁。</span><span class="sxs-lookup"><span data-stu-id="d9303-120">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="d9303-121">配置 Microsoft 威胁专家功能</span><span class="sxs-lookup"><span data-stu-id="d9303-121">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="d9303-122">配置和管理来自 Microsoft 威胁专家的网络安全威胁智能。</span><span class="sxs-lookup"><span data-stu-id="d9303-122">Configure and manage cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="d9303-123">配置 Microsoft 威胁防护集成</span><span class="sxs-lookup"><span data-stu-id="d9303-123">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration) | <span data-ttu-id="d9303-124">配置与 Defender for Endpoint 集成的其他解决方案。</span><span class="sxs-lookup"><span data-stu-id="d9303-124">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="d9303-125">管理和 API 支持</span><span class="sxs-lookup"><span data-stu-id="d9303-125">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis) | <span data-ttu-id="d9303-126">将警报拉取到 SIEM 安全信息和事件 (SIEM) 或使用 API 创建自定义警报。</span><span class="sxs-lookup"><span data-stu-id="d9303-126">Pull alerts to your Security Information and Event Management (SIEM) or use APIs to create custom alerts.</span></span> <span data-ttu-id="d9303-127">创建和生成 Power BI 报表。</span><span class="sxs-lookup"><span data-stu-id="d9303-127">Create and build Power BI reports.</span></span>
