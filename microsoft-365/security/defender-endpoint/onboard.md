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
ms.openlocfilehash: c58d7d4192afd0aa13a5ffb0c7f3204b4eaf0315
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844402"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="22904-104">配置和管理适用于终结点的 Microsoft Defender 功能</span><span class="sxs-lookup"><span data-stu-id="22904-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="22904-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="22904-105">**Applies to:**</span></span>

- [<span data-ttu-id="22904-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="22904-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="22904-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22904-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="22904-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="22904-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="22904-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="22904-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="22904-110">了解如何配置和管理适用于终结点功能的 Defender，以为组织提供最佳安全保护。</span><span class="sxs-lookup"><span data-stu-id="22904-110">Learn how to configure and manage Defender for Endpoint features, to get the best security protection for your organization.</span></span>

<span data-ttu-id="22904-111">有关在组织中连接新设备的实用建议，请参阅将设备载入 [到 Microsoft Defender for Endpoint 服务](./onboard-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="22904-111">For practical advice on connecting new devices in your organization, see [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="22904-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="22904-112">In this section</span></span>

<span data-ttu-id="22904-113">主题</span><span class="sxs-lookup"><span data-stu-id="22904-113">Topic</span></span> | <span data-ttu-id="22904-114">说明</span><span class="sxs-lookup"><span data-stu-id="22904-114">Description</span></span>
:---|:---
[<span data-ttu-id="22904-115">配置Microsoft Defender 安全中心设置</span><span class="sxs-lookup"><span data-stu-id="22904-115">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="22904-116">配置与门户相关的设置，如常规设置、高级功能或启用预览体验。</span><span class="sxs-lookup"><span data-stu-id="22904-116">Configure portal-related settings such as general settings, advanced features, or enable the preview experience.</span></span>
[<span data-ttu-id="22904-117">配置攻击面减少功能</span><span class="sxs-lookup"><span data-stu-id="22904-117">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) | <span data-ttu-id="22904-118">配置攻击面减少功能，以确保正确应用设置，并设置攻击缓解技术。</span><span class="sxs-lookup"><span data-stu-id="22904-118">Configure attack surface reduction capabilities, to ensure that settings are properly applied, and exploit mitigation techniques are set.</span></span>
[<span data-ttu-id="22904-119">配置下一代保护</span><span class="sxs-lookup"><span data-stu-id="22904-119">Configure next-generation protection</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="22904-120">配置下一代保护，以捕获所有类型的新兴威胁。</span><span class="sxs-lookup"><span data-stu-id="22904-120">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="22904-121">配置Microsoft 威胁专家功能</span><span class="sxs-lookup"><span data-stu-id="22904-121">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="22904-122">配置和管理来自安全中心的网络安全威胁Microsoft 威胁专家。</span><span class="sxs-lookup"><span data-stu-id="22904-122">Configure and manage cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="22904-123">配置 Microsoft 365 Defender 集成</span><span class="sxs-lookup"><span data-stu-id="22904-123">Configure Microsoft 365 Defender integration</span></span>](/microsoft-365/security/defender-endpoint/threat-protection-integration) | <span data-ttu-id="22904-124">配置与 Defender for Endpoint 集成的其他解决方案。</span><span class="sxs-lookup"><span data-stu-id="22904-124">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="22904-125">管理和 API 支持</span><span class="sxs-lookup"><span data-stu-id="22904-125">Management and API support</span></span>](/microsoft-365/security/defender-endpoint/management-apis) | <span data-ttu-id="22904-126">将警报拉取到 SIEM 安全信息和事件 (SIEM) 或使用 API 创建自定义警报。</span><span class="sxs-lookup"><span data-stu-id="22904-126">Pull alerts to your Security Information and Event Management (SIEM) or use APIs to create custom alerts.</span></span> <span data-ttu-id="22904-127">创建和生成Power BI报告。</span><span class="sxs-lookup"><span data-stu-id="22904-127">Create and build Power BI reports.</span></span>
