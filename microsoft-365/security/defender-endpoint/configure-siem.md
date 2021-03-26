---
title: 从 Microsoft Defender for Endpoint 将检测拉取到 SIEM 工具
description: 了解如何使用 REST API 并配置支持的安全信息和事件管理工具以接收和拉取检测。
keywords: 配置 siem， 安全信息和事件管理工具， splunk， arcsight， 自定义指示器， rest api， 警报定义， 泄露指示器
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 97a64c8537ff2a6f9948ed6ed056b8aa7379ce69
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222331"
---
# <a name="pull-detections-to-your-siem-tools"></a><span data-ttu-id="b1917-104">将检测拉取到 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="b1917-104">Pull detections to your SIEM tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b1917-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b1917-105">**Applies to:**</span></span>
- [<span data-ttu-id="b1917-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b1917-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b1917-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1917-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b1917-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="b1917-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b1917-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="b1917-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a><span data-ttu-id="b1917-110">使用 SIEM 安全工具中的安全信息和事件 (拉) 检测</span><span class="sxs-lookup"><span data-stu-id="b1917-110">Pull detections using security information and events management (SIEM) tools</span></span>

>[!NOTE]
>- <span data-ttu-id="b1917-111">[Microsoft Defender for Endpoint Alert](alerts.md) 由一个或多个检测组成。</span><span class="sxs-lookup"><span data-stu-id="b1917-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="b1917-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) 由设备上发生的可疑事件及其相关的警报详细信息组成。</span><span class="sxs-lookup"><span data-stu-id="b1917-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="b1917-113">-Microsoft Defender for Endpoint 警报 API 是警报使用的最新 API，包含每个警报的相关证据的详细列表。</span><span class="sxs-lookup"><span data-stu-id="b1917-113">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="b1917-114">有关详细信息，请参阅[警报方法和属性和](alerts.md)[列表警报](get-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="b1917-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="b1917-115">Defender for Endpoint 支持安全信息和事件管理 (SIEM) 拉取检测工具。</span><span class="sxs-lookup"><span data-stu-id="b1917-115">Defender for Endpoint supports security information and event management (SIEM) tools to pull detections.</span></span> <span data-ttu-id="b1917-116">Defender for Endpoint 通过 Azure 中托管的 HTTPS 终结点公开警报。</span><span class="sxs-lookup"><span data-stu-id="b1917-116">Defender for Endpoint exposes alerts through an HTTPS endpoint hosted in Azure.</span></span> <span data-ttu-id="b1917-117">终结点可以配置为使用 AAD 应用程序的 OAuth 2.0 身份验证协议从 Azure Active Directory (AAD) 中的企业租户拉取检测，此协议表示环境中安装的特定 SIEM 连接器。</span><span class="sxs-lookup"><span data-stu-id="b1917-117">The endpoint can be configured to pull detections from your enterprise tenant in Azure Active Directory (AAD) using the OAuth 2.0 authentication protocol for an AAD application that represents the specific SIEM connector installed in your environment.</span></span>

<span data-ttu-id="b1917-118">Defender for Endpoint 当前通过专用 SIEM 集成模型支持以下特定 SIEM 解决方案工具：</span><span class="sxs-lookup"><span data-stu-id="b1917-118">Defender for Endpoint currently supports the following specific SIEM solution tools through a dedicated SIEM integration model:</span></span>

- <span data-ttu-id="b1917-119">IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="b1917-119">IBM QRadar</span></span>
- <span data-ttu-id="b1917-120">Micro Focus ArcSight</span><span class="sxs-lookup"><span data-stu-id="b1917-120">Micro Focus ArcSight</span></span>

<span data-ttu-id="b1917-121">其他 SIEM 解决方案 (Splunk、RSA NetWitness) 基于新的警报 API 的不同集成模型受到支持。</span><span class="sxs-lookup"><span data-stu-id="b1917-121">Other SIEM solutions (such as Splunk, RSA NetWitness) are supported through a different integration model based on the new Alert API.</span></span> <span data-ttu-id="b1917-122">有关详细信息，请参阅合作伙伴 [应用程序页并选择](https://securitycenter.microsoft.com/interoperability/partners) 安全信息和分析部分，获取完整详细信息。</span><span class="sxs-lookup"><span data-stu-id="b1917-122">For more information, view the [Partner application](https://securitycenter.microsoft.com/interoperability/partners) page and select the Security Information and Analytics section for full details.</span></span>

<span data-ttu-id="b1917-123">若要使用这些受支持的 SIEM 工具之一，你将需要：</span><span class="sxs-lookup"><span data-stu-id="b1917-123">To use either of these supported SIEM tools, you'll need to:</span></span>

- [<span data-ttu-id="b1917-124">在 Defender for Endpoint 中启用 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="b1917-124">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- <span data-ttu-id="b1917-125">配置支持的 SIEM 工具：</span><span class="sxs-lookup"><span data-stu-id="b1917-125">Configure the supported SIEM tool:</span></span>
     - [<span data-ttu-id="b1917-126">配置 Micro Focus ArcSight 以拉取 Defender 进行终结点检测</span><span class="sxs-lookup"><span data-stu-id="b1917-126">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>](configure-arcsight.md)
     - <span data-ttu-id="b1917-127">配置 IBM QRadar 以拉取 Defender for Endpoint detections 有关详细信息，请参阅 [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)。</span><span class="sxs-lookup"><span data-stu-id="b1917-127">Configure IBM QRadar to pull Defender for Endpoint detections For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

<span data-ttu-id="b1917-128">有关在检测 API 中公开的字段列表详细信息，请参阅 [Defender for Endpoint Detection fields](api-portal-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="b1917-128">For more information on the list of fields exposed in the Detection API, see [Defender for Endpoint Detection fields](api-portal-mapping.md).</span></span>
