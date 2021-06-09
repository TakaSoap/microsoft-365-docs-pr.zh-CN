---
title: 优化 ASR 规则部署和检测
description: 优化攻击面减少 (ASR) 规则，以识别和阻止典型的恶意软件攻击。
keywords: 载入， Intune 管理， Microsoft Defender for Endpoint， Microsoft Defender， Windows Defender， 攻击面减少， ASR， 安全基线
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a5590e62e7838bb9f611320b6d0e5c573b2be084
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841554"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a><span data-ttu-id="cde3d-104">优化 ASR 规则部署和检测</span><span class="sxs-lookup"><span data-stu-id="cde3d-104">Optimize ASR rule deployment and detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cde3d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="cde3d-105">**Applies to:**</span></span>
- [<span data-ttu-id="cde3d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="cde3d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cde3d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cde3d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cde3d-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="cde3d-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="cde3d-109">[注册免费试用版](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="cde3d-109">[Sign up for a free trial](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span></span>

<span data-ttu-id="cde3d-110">[攻击面减少 (ASR) 识别](./attack-surface-reduction.md) 并阻止典型的恶意软件攻击。</span><span class="sxs-lookup"><span data-stu-id="cde3d-110">[Attack surface reduction (ASR) rules](./attack-surface-reduction.md) identify and prevent typical malware exploits.</span></span> <span data-ttu-id="cde3d-111">它们控制何时以及如何运行潜在的恶意代码。</span><span class="sxs-lookup"><span data-stu-id="cde3d-111">They control when and how potentially malicious code can run.</span></span> <span data-ttu-id="cde3d-112">例如，它们可以防止 JavaScript 或 VBScript 启动下载的可执行文件、阻止从 Office 宏调用 Win32 API 以及阻止从 USB 驱动器运行的进程。</span><span class="sxs-lookup"><span data-stu-id="cde3d-112">For example, they can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, and block processes that run from USB drives.</span></span>

<span data-ttu-id="cde3d-113">![攻击面管理卡](images/secconmgmt_asr_card.png)</span><span class="sxs-lookup"><span data-stu-id="cde3d-113">![Attack surface management card](images/secconmgmt_asr_card.png)</span></span><br>
<span data-ttu-id="cde3d-114">*攻击面管理卡*</span><span class="sxs-lookup"><span data-stu-id="cde3d-114">*Attack surface management card*</span></span>

<span data-ttu-id="cde3d-115">攻击 *面管理卡* 是安全中心中Microsoft 365入口点，可用于：</span><span class="sxs-lookup"><span data-stu-id="cde3d-115">The *Attack surface management card* is an entry point to tools in Microsoft 365 security center that you can use to:</span></span>

* <span data-ttu-id="cde3d-116">了解 ASR 规则当前在组织中是如何部署的。</span><span class="sxs-lookup"><span data-stu-id="cde3d-116">Understand how ASR rules are currently deployed in your organization.</span></span>
* <span data-ttu-id="cde3d-117">查看 ASR 检测并识别可能的不正确检测。</span><span class="sxs-lookup"><span data-stu-id="cde3d-117">Review ASR detections and identify possible incorrect detections.</span></span>
* <span data-ttu-id="cde3d-118">分析排除的影响并生成要排除的文件路径列表。</span><span class="sxs-lookup"><span data-stu-id="cde3d-118">Analyze the impact of exclusions and generate the list of file paths to exclude.</span></span>

<span data-ttu-id="cde3d-119">选择 **转到攻击面管理**  >  **监视&报告>攻击面减少规则>添加排除项**。</span><span class="sxs-lookup"><span data-stu-id="cde3d-119">Select **Go to attack surface management** > **Monitoring & reports > Attack surface reduction rules > Add exclusions**.</span></span> <span data-ttu-id="cde3d-120">然后，你可以导航到安全中心Microsoft 365分区。</span><span class="sxs-lookup"><span data-stu-id="cde3d-120">From there, you can navigate to other sections of Microsoft 365 security center.</span></span>

<span data-ttu-id="cde3d-121">![在安全中心的"攻击面减少规则"Microsoft 365排除项"选项卡](images/secconmgmt_asr_m365exlusions.png)</span><span class="sxs-lookup"><span data-stu-id="cde3d-121">![Add exclusions tab in the Attack surface reduction rules page in Microsoft 365 security center](images/secconmgmt_asr_m365exlusions.png)</span></span><br>
<span data-ttu-id="cde3d-122">安全 ***中心的"攻击** 面减少规则"页中的"添加排除Microsoft 365选项卡*</span><span class="sxs-lookup"><span data-stu-id="cde3d-122">The ***Add exclusions** tab in the Attack surface reduction rules page in Microsoft 365 security center*</span></span>

> [!NOTE]
> <span data-ttu-id="cde3d-123">若要访问Microsoft 365安全中心，您需要一个 Microsoft 365 E3 或 E5 许可证以及一个在安全中心具有特定角色Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="cde3d-123">To access Microsoft 365 security center, you need a Microsoft 365 E3 or E5 license and an account that has certain roles on Azure Active Directory.</span></span> <span data-ttu-id="cde3d-124">[阅读所需的许可证和权限](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)。</span><span class="sxs-lookup"><span data-stu-id="cde3d-124">[Read about required licenses and permissions](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="cde3d-125">有关安全中心中 ASR 规则部署Microsoft 365，请参阅监视和管理[ASR 规则部署和检测](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)。</span><span class="sxs-lookup"><span data-stu-id="cde3d-125">For more information about ASR rule deployment in Microsoft 365 security center, see [Monitor and manage ASR rule deployment and detections](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).</span></span>

<span data-ttu-id="cde3d-126">**相关主题**</span><span class="sxs-lookup"><span data-stu-id="cde3d-126">**Related topics**</span></span>

* [<span data-ttu-id="cde3d-127">确保设备配置正确</span><span class="sxs-lookup"><span data-stu-id="cde3d-127">Ensure your devices are configured properly</span></span>](configure-machines.md)
* [<span data-ttu-id="cde3d-128">获取载入到 Microsoft Defender for Endpoint 的设备</span><span class="sxs-lookup"><span data-stu-id="cde3d-128">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
* [<span data-ttu-id="cde3d-129">监视 Microsoft Defender 终结点安全基线的合规性</span><span class="sxs-lookup"><span data-stu-id="cde3d-129">Monitor compliance to the Microsoft Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
