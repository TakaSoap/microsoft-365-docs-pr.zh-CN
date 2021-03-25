---
title: 使用 Microsoft Defender ATP for Mac 检测并阻止可能不需要的应用程序
description: 使用 Microsoft Defender ATP for Mac (并阻止 PUA) 可能不需要的应用程序。
keywords: microsoft， defender， atp， mac， pua， pus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6e65e847403160d24eac04a553ca16a46314e33d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187417"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="ba177-104">使用 Microsoft Defender for Endpoint for Mac 检测并阻止可能不需要的应用程序</span><span class="sxs-lookup"><span data-stu-id="ba177-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ba177-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ba177-105">**Applies to:**</span></span>
- [<span data-ttu-id="ba177-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ba177-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ba177-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ba177-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ba177-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="ba177-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ba177-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="ba177-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="ba177-110">Microsoft Defender for Mac (PUA) 保护功能中可能不需要的应用程序可以检测和阻止网络中终结点上的 PUA 文件。</span><span class="sxs-lookup"><span data-stu-id="ba177-110">The potentially unwanted application (PUA) protection feature in Microsoft Defender for Endpoint for Mac can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="ba177-111">这些应用程序不被视为病毒、恶意软件或其他类型的威胁，但可能会对终结点执行对性能或使用产生不利影响的操作。</span><span class="sxs-lookup"><span data-stu-id="ba177-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="ba177-112">PUA 还可以指信誉不佳的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ba177-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="ba177-113">这些应用程序会增加网络受到恶意软件感染的风险，导致恶意软件感染更难识别，并且可能会浪费 IT 资源来清理应用程序。</span><span class="sxs-lookup"><span data-stu-id="ba177-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="ba177-114">运作方式</span><span class="sxs-lookup"><span data-stu-id="ba177-114">How it works</span></span>

<span data-ttu-id="ba177-115">适用于 Mac 的 Microsoft Defender for Endpoint 可以检测和报告 PUA 文件。</span><span class="sxs-lookup"><span data-stu-id="ba177-115">Microsoft Defender for Endpoint for Mac can detect and report PUA files.</span></span> <span data-ttu-id="ba177-116">在阻止模式下配置时，PUA 文件将移动到隔离区。</span><span class="sxs-lookup"><span data-stu-id="ba177-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="ba177-117">在终结点上检测到 PUA 时，除非已禁用通知，否则 Microsoft Defender for Mac 终结点会向用户显示通知。</span><span class="sxs-lookup"><span data-stu-id="ba177-117">When a PUA is detected on an endpoint, Microsoft Defender for Endpoint for Mac presents a notification to the user, unless notifications have been disabled.</span></span> <span data-ttu-id="ba177-118">威胁名称将包含单词"Application"。</span><span class="sxs-lookup"><span data-stu-id="ba177-118">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="ba177-119">配置 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="ba177-119">Configure PUA protection</span></span>

<span data-ttu-id="ba177-120">可通过以下方法之一配置 Microsoft Defender for Endpoint for Mac 中的 PUA 保护：</span><span class="sxs-lookup"><span data-stu-id="ba177-120">PUA protection in Microsoft Defender for Endpoint for Mac can be configured in one of the following ways:</span></span>

- <span data-ttu-id="ba177-121">**关闭**：PUA 保护已禁用。</span><span class="sxs-lookup"><span data-stu-id="ba177-121">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="ba177-122">**审核**：PUA 文件在产品日志中报告，但不在 Microsoft Defender 安全中心中报告。</span><span class="sxs-lookup"><span data-stu-id="ba177-122">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="ba177-123">不会向用户显示任何通知，产品不会采取任何操作。</span><span class="sxs-lookup"><span data-stu-id="ba177-123">No notification is presented to the user and no action is taken by the product.</span></span>
- <span data-ttu-id="ba177-124">**阻止**：PUA 文件在产品日志和 Microsoft Defender 安全中心中报告。</span><span class="sxs-lookup"><span data-stu-id="ba177-124">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="ba177-125">用户会收到通知，产品会采取操作。</span><span class="sxs-lookup"><span data-stu-id="ba177-125">The user is presented with a notification and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="ba177-126">默认情况下，PUA 保护在 **审核模式下配置** 。</span><span class="sxs-lookup"><span data-stu-id="ba177-126">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="ba177-127">你可以配置从命令行或管理控制台处理 PUA 文件的方式。</span><span class="sxs-lookup"><span data-stu-id="ba177-127">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="ba177-128">使用命令行工具配置 PUA 保护：</span><span class="sxs-lookup"><span data-stu-id="ba177-128">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="ba177-129">在终端中，执行以下命令以配置 PUA 保护：</span><span class="sxs-lookup"><span data-stu-id="ba177-129">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="ba177-130">使用管理控制台配置 PUA 保护：</span><span class="sxs-lookup"><span data-stu-id="ba177-130">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="ba177-131">在你的企业中，你可以从管理控制台（如 JAMF 或 Intune）配置 PUA 保护，类似于配置其他产品设置的方式。</span><span class="sxs-lookup"><span data-stu-id="ba177-131">In your enterprise, you can configure PUA protection from a management console, such as JAMF or Intune, similarly to how other product settings are configured.</span></span> <span data-ttu-id="ba177-132">有关详细信息，请参阅设置适用于[](mac-preferences.md#threat-type-settings)Mac 的 Microsoft [Defender for Endpoint 的](mac-preferences.md)首选项主题中的威胁类型设置部分。</span><span class="sxs-lookup"><span data-stu-id="ba177-132">For more information, see the [Threat type settings](mac-preferences.md#threat-type-settings) section of the [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md) topic.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ba177-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="ba177-133">Related topics</span></span>

- [<span data-ttu-id="ba177-134">设置适用于 Mac 的 Microsoft Defender 终结点的首选项</span><span class="sxs-lookup"><span data-stu-id="ba177-134">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>](mac-preferences.md)
