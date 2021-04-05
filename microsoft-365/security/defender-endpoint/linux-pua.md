---
title: 使用 Microsoft Defender ATP for Linux 检测并阻止可能不需要的应用程序
description: 使用 Microsoft Defender ATP for Linux (并阻止 PUA) 可能不需要的应用程序。
keywords: microsoft， defender， atp， linux， pua， pus
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a6f2e2057ca78cb0e1114ed86829cd931dc1cd2b
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587547"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="ddb7a-104">使用 Microsoft Defender for Endpoint for Linux 检测并阻止可能不需要的应用程序</span><span class="sxs-lookup"><span data-stu-id="ddb7a-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ddb7a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ddb7a-105">**Applies to:**</span></span>
- [<span data-ttu-id="ddb7a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ddb7a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ddb7a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ddb7a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ddb7a-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="ddb7a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ddb7a-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="ddb7a-110">适用于 Linux 的 Defender (PUA) 保护功能中可能不需要的应用程序可以检测和阻止网络中终结点上的 PUA 文件。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-110">The potentially unwanted application (PUA) protection feature in Defender for Endpoint for Linux can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="ddb7a-111">这些应用程序不被视为病毒、恶意软件或其他类型的威胁，但可能会对终结点执行对性能或使用产生不利影响的操作。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="ddb7a-112">PUA 还可以指信誉不佳的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="ddb7a-113">这些应用程序会增加网络受到恶意软件感染的风险，导致恶意软件感染更难识别，并且可能会浪费 IT 资源来清理应用程序。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="ddb7a-114">运作方式</span><span class="sxs-lookup"><span data-stu-id="ddb7a-114">How it works</span></span>

<span data-ttu-id="ddb7a-115">适用于 Linux 的 Defender for Endpoint 可以检测和报告 PUA 文件。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-115">Defender for Endpoint for Linux can detect and report PUA files.</span></span> <span data-ttu-id="ddb7a-116">在阻止模式下配置时，PUA 文件将移动到隔离区。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="ddb7a-117">在终结点上检测到 PUA 时，Linux 的 Defender for Endpoint 会记录威胁历史记录中的感染情况。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-117">When a PUA is detected on an endpoint, Defender for Endpoint for Linux keeps a record of the infection in the threat history.</span></span> <span data-ttu-id="ddb7a-118">可以从 Microsoft Defender 安全中心门户或命令行工具可视化 `mdatp` 历史记录。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-118">The history can be visualized from the Microsoft Defender Security Center portal or through the `mdatp` command-line tool.</span></span> <span data-ttu-id="ddb7a-119">威胁名称将包含单词"Application"。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-119">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="ddb7a-120">配置 PUA 保护</span><span class="sxs-lookup"><span data-stu-id="ddb7a-120">Configure PUA protection</span></span>

<span data-ttu-id="ddb7a-121">可通过以下方法之一配置适用于 Linux 的 Defender 终结点中的 PUA 保护：</span><span class="sxs-lookup"><span data-stu-id="ddb7a-121">PUA protection in Defender for Endpoint for Linux can be configured in one of the following ways:</span></span>

- <span data-ttu-id="ddb7a-122">**关闭**：PUA 保护已禁用。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-122">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="ddb7a-123">**审核**：PUA 文件在产品日志中报告，但不在 Microsoft Defender 安全中心中报告。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-123">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="ddb7a-124">威胁历史记录中未存储任何感染记录，产品不采取措施。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-124">No record of the infection is stored in the threat history and no action is taken by the product.</span></span>
- <span data-ttu-id="ddb7a-125">**阻止**：PUA 文件在产品日志和 Microsoft Defender 安全中心中报告。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-125">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="ddb7a-126">感染的记录存储在威胁历史记录中，产品会采取措施。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-126">A record of the infection is stored in the threat history and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="ddb7a-127">默认情况下，PUA 保护在 **审核模式下配置** 。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-127">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="ddb7a-128">你可以配置从命令行或管理控制台处理 PUA 文件的方式。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-128">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="ddb7a-129">使用命令行工具配置 PUA 保护：</span><span class="sxs-lookup"><span data-stu-id="ddb7a-129">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="ddb7a-130">在终端中，执行以下命令以配置 PUA 保护：</span><span class="sxs-lookup"><span data-stu-id="ddb7a-130">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="ddb7a-131">使用管理控制台配置 PUA 保护：</span><span class="sxs-lookup"><span data-stu-id="ddb7a-131">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="ddb7a-132">在企业中，你可以配置管理控制台（如"小数"或"Ansible"）的 PUA 保护，这类似于配置其他产品设置的方式。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-132">In your enterprise, you can configure PUA protection from a management console, such as Puppet or Ansible, similarly to how other product settings are configured.</span></span> <span data-ttu-id="ddb7a-133">有关详细信息，请参阅设置适用于[](linux-preferences.md#threat-type-settings)Linux 的 Defender[终结点](linux-preferences.md)的首选项文章的威胁类型设置部分。</span><span class="sxs-lookup"><span data-stu-id="ddb7a-133">For more information, see the [Threat type settings](linux-preferences.md#threat-type-settings) section of the [Set preferences for Defender for Endpoint for Linux](linux-preferences.md) article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ddb7a-134">相关文章</span><span class="sxs-lookup"><span data-stu-id="ddb7a-134">Related articles</span></span>

- [<span data-ttu-id="ddb7a-135">设置适用于 Linux 的 Defender 终结点的首选项</span><span class="sxs-lookup"><span data-stu-id="ddb7a-135">Set preferences for Defender for Endpoint for Linux</span></span>](linux-preferences.md)
