---
title: 使用 Mac 上的 Microsoft Defender for Endpoint 检测并阻止可能不需要的应用程序
description: 使用适用于 Mac 的终结点上的 Microsoft Defender (并阻止 PUA) 可能不需要的应用程序。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， pua， pus
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
ms.openlocfilehash: 2d32dd96cd506ebf1752e48d2b7c66208b1abc11
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934533"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="4cf48-104">使用 macOS 上的 Microsoft Defender for Endpoint 检测并阻止可能不需要的应用程序</span><span class="sxs-lookup"><span data-stu-id="4cf48-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4cf48-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4cf48-105">**Applies to:**</span></span>
- [<span data-ttu-id="4cf48-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4cf48-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4cf48-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4cf48-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4cf48-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="4cf48-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4cf48-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4cf48-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="4cf48-110">macOS 上的 Microsoft Defender for Endpoint (PUA) 保护功能可能不需要的应用程序可以检测和阻止网络中终结点上的 PUA 文件。</span><span class="sxs-lookup"><span data-stu-id="4cf48-110">The potentially unwanted application (PUA) protection feature in Microsoft Defender for Endpoint on macOS can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="4cf48-111">这些应用程序不被视为病毒、恶意软件或其他类型的威胁，但可能会对终结点执行对性能或使用产生不利影响的操作。</span><span class="sxs-lookup"><span data-stu-id="4cf48-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="4cf48-112">PUA 还可以指信誉不佳的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4cf48-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="4cf48-113">这些应用程序会增加网络受到恶意软件感染的风险，导致恶意软件感染更难识别，并且可能会浪费 IT 资源来清理应用程序。</span><span class="sxs-lookup"><span data-stu-id="4cf48-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="4cf48-114">运作方式</span><span class="sxs-lookup"><span data-stu-id="4cf48-114">How it works</span></span>

<span data-ttu-id="4cf48-115">macOS 上的 Microsoft Defender for Endpoint 可以检测和报告 PUA 文件。</span><span class="sxs-lookup"><span data-stu-id="4cf48-115">Microsoft Defender for Endpoint on macOS can detect and report PUA files.</span></span> <span data-ttu-id="4cf48-116">在阻止模式下配置时，PUA 文件将移动到隔离区。</span><span class="sxs-lookup"><span data-stu-id="4cf48-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="4cf48-117">在终结点上检测到 PUA 时，macOS 上的 Microsoft Defender for Endpoint 会向用户显示通知，除非已禁用通知。</span><span class="sxs-lookup"><span data-stu-id="4cf48-117">When a PUA is detected on an endpoint, Microsoft Defender for Endpoint on macOS presents a notification to the user, unless notifications have been disabled.</span></span> <span data-ttu-id="4cf48-118">威胁名称将包含单词"Application"。</span><span class="sxs-lookup"><span data-stu-id="4cf48-118">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="4cf48-119">配置 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="4cf48-119">Configure PUA protection</span></span>

<span data-ttu-id="4cf48-120">可通过以下方法之一配置 macOS 上适用于终结点的 Microsoft Defender 中的 PUA 保护：</span><span class="sxs-lookup"><span data-stu-id="4cf48-120">PUA protection in Microsoft Defender for Endpoint on macOS can be configured in one of the following ways:</span></span>

- <span data-ttu-id="4cf48-121">**关闭**：PUA 保护已禁用。</span><span class="sxs-lookup"><span data-stu-id="4cf48-121">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="4cf48-122">**审核**：PUA 文件在产品日志中报告，但不在Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="4cf48-122">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="4cf48-123">不会向用户显示任何通知，产品不会采取任何操作。</span><span class="sxs-lookup"><span data-stu-id="4cf48-123">No notification is presented to the user and no action is taken by the product.</span></span>
- <span data-ttu-id="4cf48-124">**Block**：PUA 文件在产品日志中和产品日志中Microsoft Defender 安全中心。</span><span class="sxs-lookup"><span data-stu-id="4cf48-124">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="4cf48-125">用户会收到通知，产品会采取操作。</span><span class="sxs-lookup"><span data-stu-id="4cf48-125">The user is presented with a notification and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="4cf48-126">默认情况下，PUA 保护在 **审核模式下配置** 。</span><span class="sxs-lookup"><span data-stu-id="4cf48-126">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="4cf48-127">你可以配置从命令行或管理控制台处理 PUA 文件的方式。</span><span class="sxs-lookup"><span data-stu-id="4cf48-127">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="4cf48-128">使用命令行工具配置 PUA 保护：</span><span class="sxs-lookup"><span data-stu-id="4cf48-128">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="4cf48-129">在终端中，执行以下命令以配置 PUA 保护：</span><span class="sxs-lookup"><span data-stu-id="4cf48-129">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="4cf48-130">使用管理控制台配置 PUA 保护：</span><span class="sxs-lookup"><span data-stu-id="4cf48-130">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="4cf48-131">在你的企业中，你可以从管理控制台（如 JAMF 或 Intune）配置 PUA 保护，类似于配置其他产品设置的方式。</span><span class="sxs-lookup"><span data-stu-id="4cf48-131">In your enterprise, you can configure PUA protection from a management console, such as JAMF or Intune, similarly to how other product settings are configured.</span></span> <span data-ttu-id="4cf48-132">有关详细信息，请参阅在 macOS 上设置 Microsoft Defender for Endpoint 的首选项主题[中的威胁类型](mac-preferences.md)设置部分。 [](mac-preferences.md#threat-type-settings)</span><span class="sxs-lookup"><span data-stu-id="4cf48-132">For more information, see the [Threat type settings](mac-preferences.md#threat-type-settings) section of the [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md) topic.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4cf48-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="4cf48-133">Related topics</span></span>

- [<span data-ttu-id="4cf48-134">在 macOS 上设置适用于终结点的 Microsoft Defender 的首选项</span><span class="sxs-lookup"><span data-stu-id="4cf48-134">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>](mac-preferences.md)
