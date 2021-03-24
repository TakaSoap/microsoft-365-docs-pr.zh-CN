---
title: Microsoft Defender 安全中心
description: Microsoft Defender 安全中心是你可以访问 Microsoft Defender for Endpoint 的门户。
keywords: windows， defender， 安全， 中心， defender， 高级， 威胁， 保护
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
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 521c24c24ecc46c81f74e0bab28642aaf581274d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054786"
---
# <a name="microsoft-defender-security-center"></a><span data-ttu-id="a284b-104">Microsoft Defender 安全中心</span><span class="sxs-lookup"><span data-stu-id="a284b-104">Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a284b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a284b-105">**Applies to:**</span></span>
- [<span data-ttu-id="a284b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a284b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="a284b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a284b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a284b-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="a284b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a284b-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="a284b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="a284b-110">Microsoft Defender 安全中心是一个门户，你可以在这里访问 Microsoft Defender for Endpoint 功能。</span><span class="sxs-lookup"><span data-stu-id="a284b-110">Microsoft Defender Security Center is the portal where you can access Microsoft Defender for Endpoint capabilities.</span></span> <span data-ttu-id="a284b-111">它为企业安全运营团队提供了单一的窗格体验，以帮助保护网络安全。</span><span class="sxs-lookup"><span data-stu-id="a284b-111">It gives enterprise security operations teams a single pane of glass experience to help secure networks.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="a284b-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="a284b-112">In this section</span></span>

<span data-ttu-id="a284b-113">主题</span><span class="sxs-lookup"><span data-stu-id="a284b-113">Topic</span></span> | <span data-ttu-id="a284b-114">说明</span><span class="sxs-lookup"><span data-stu-id="a284b-114">Description</span></span>
:---|:---
<span data-ttu-id="a284b-115">入门</span><span class="sxs-lookup"><span data-stu-id="a284b-115">Get started</span></span>  |  <span data-ttu-id="a284b-116">了解最低要求、验证许可和完整设置、了解预览功能、了解数据存储和隐私以及如何为门户分配用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="a284b-116">Learn about the minimum requirements, validate licensing and complete setup, know about preview features, understand data storage and privacy, and how to assign user access to the portal.</span></span>
[<span data-ttu-id="a284b-117">载入设备</span><span class="sxs-lookup"><span data-stu-id="a284b-117">Onboard devices</span></span>](onboard-configure.md) | <span data-ttu-id="a284b-118">了解载入客户端、服务器和非 Windows 设备。</span><span class="sxs-lookup"><span data-stu-id="a284b-118">Learn about onboarding client, server, and non-Windows devices.</span></span> <span data-ttu-id="a284b-119">了解如何运行检测测试、配置代理和 Internet 连接设置以及如何解决潜在的载入问题。</span><span class="sxs-lookup"><span data-stu-id="a284b-119">Learn how to run a detection test, configure proxy and Internet connectivity settings, and how to troubleshoot potential onboarding issues.</span></span>
[<span data-ttu-id="a284b-120">了解门户</span><span class="sxs-lookup"><span data-stu-id="a284b-120">Understand the portal</span></span>](use.md) | <span data-ttu-id="a284b-121">了解安全操作、安全分数和威胁分析仪表板以及如何导航门户。</span><span class="sxs-lookup"><span data-stu-id="a284b-121">Understand the Security operations, Secure Score, and Threat analytics dashboards as well as how to navigate the portal.</span></span>
<span data-ttu-id="a284b-122">调查和修正威胁</span><span class="sxs-lookup"><span data-stu-id="a284b-122">Investigate and remediate threats</span></span> | <span data-ttu-id="a284b-123">调查警报、设备和采取响应操作来修正威胁。</span><span class="sxs-lookup"><span data-stu-id="a284b-123">Investigate alerts, devices, and take response actions to remediate threats.</span></span>
<span data-ttu-id="a284b-124">API 和 SIEM 支持</span><span class="sxs-lookup"><span data-stu-id="a284b-124">API and SIEM support</span></span> | <span data-ttu-id="a284b-125">使用受支持的 API 拉取和创建自定义警报，或自动化工作流。</span><span class="sxs-lookup"><span data-stu-id="a284b-125">Use the supported APIs to pull and create custom alerts, or automate workflows.</span></span> <span data-ttu-id="a284b-126">使用受支持的 SIEM 工具从 Microsoft Defender 安全中心拉取警报。</span><span class="sxs-lookup"><span data-stu-id="a284b-126">Use the supported SIEM tools to pull alerts from Microsoft Defender Security Center.</span></span>
<span data-ttu-id="a284b-127">Reporting</span><span class="sxs-lookup"><span data-stu-id="a284b-127">Reporting</span></span> | <span data-ttu-id="a284b-128">使用 Microsoft Defender for Endpoint 数据创建和生成 Power BI 报告。</span><span class="sxs-lookup"><span data-stu-id="a284b-128">Create and build Power BI reports using Microsoft Defender for Endpoint data.</span></span>
<span data-ttu-id="a284b-129">检查服务运行状况和传感器状态</span><span class="sxs-lookup"><span data-stu-id="a284b-129">Check service health and sensor state</span></span> | <span data-ttu-id="a284b-130">验证服务是否正在运行，并检查设备的传感器状态。</span><span class="sxs-lookup"><span data-stu-id="a284b-130">Verify that the service is running and check the sensor state on devices.</span></span>
[<span data-ttu-id="a284b-131">配置 Microsoft Defender 安全中心设置</span><span class="sxs-lookup"><span data-stu-id="a284b-131">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="a284b-132">配置常规设置、启用预览体验、通知并启用其他功能。</span><span class="sxs-lookup"><span data-stu-id="a284b-132">Configure general settings, turn on the preview experience, notifications, and enable other features.</span></span>
[<span data-ttu-id="a284b-133">访问 Microsoft Defender for Endpoint 社区中心</span><span class="sxs-lookup"><span data-stu-id="a284b-133">Access the Microsoft Defender for Endpoint Community Center</span></span>](community.md) | <span data-ttu-id="a284b-134">访问 Microsoft Defender for Endpoint 社区中心，了解、协作和共享产品体验。</span><span class="sxs-lookup"><span data-stu-id="a284b-134">Access the Microsoft Defender for Endpoint Community Center to learn, collaborate, and share experiences about the product.</span></span>
[<span data-ttu-id="a284b-135">解决服务问题</span><span class="sxs-lookup"><span data-stu-id="a284b-135">Troubleshoot service issues</span></span>](troubleshoot-mdatp.md) | <span data-ttu-id="a284b-136">本部分解决使用 Microsoft Defender for Endpoint 服务时可能出现的问题。</span><span class="sxs-lookup"><span data-stu-id="a284b-136">This section addresses issues that might arise as you use the Microsoft Defender for Endpoint service.</span></span>