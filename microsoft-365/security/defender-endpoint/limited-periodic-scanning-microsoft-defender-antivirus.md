---
title: 启用有限定期 Microsoft Defender 防病毒扫描功能
description: 有限定期扫描使你可以使用 Microsoft Defender 防病毒以及其他已安装的 AV 提供程序
keywords: lps， 受限， 定期， 扫描， 兼容性， 第三方， 其他 av， 禁用
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 64b65363ff53773f73cbbdc33b05a0a1beaf7f92
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689987"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a><span data-ttu-id="ea9e1-104">在 Microsoft Defender 防病毒中使用有限定期扫描</span><span class="sxs-lookup"><span data-stu-id="ea9e1-104">Use limited periodic scanning in Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ea9e1-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ea9e1-105">**Applies to:**</span></span>

- [<span data-ttu-id="ea9e1-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ea9e1-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ea9e1-107">有限定期扫描是一种特殊类型的威胁检测和修正，当你在 Windows 10 设备上安装了其他防病毒产品时，可以启用它。</span><span class="sxs-lookup"><span data-stu-id="ea9e1-107">Limited periodic scanning is a special type of threat detection and remediation that can be enabled when you have installed another antivirus product on a Windows 10 device.</span></span>

<span data-ttu-id="ea9e1-108">它只能在特定情况下启用。</span><span class="sxs-lookup"><span data-stu-id="ea9e1-108">It can only be enabled in certain situations.</span></span> <span data-ttu-id="ea9e1-109">有关有限定期扫描以及 Microsoft Defender 防病毒如何与其他防病毒产品一起运行的详细信息，请参阅 [Microsoft Defender 防病毒兼容性](microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="ea9e1-109">For more information about limited periodic scanning and how Microsoft Defender Antivirus works with other antivirus products, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

<span data-ttu-id="ea9e1-110">**Microsoft 不建议在企业环境中使用此功能。这是一项主要面向消费者的功能。**</span><span class="sxs-lookup"><span data-stu-id="ea9e1-110">**Microsoft does not recommend using this feature in enterprise environments. This is a feature primarily intended for consumers.**</span></span> <span data-ttu-id="ea9e1-111">此功能仅使用 Microsoft Defender 防病毒功能的有限子集来检测恶意软件，并且无法检测大多数恶意软件和可能不需要的软件。</span><span class="sxs-lookup"><span data-stu-id="ea9e1-111">This feature only uses a limited subset of the Microsoft Defender Antivirus capabilities to detect malware, and will not be able to detect most malware and potentially unwanted software.</span></span> <span data-ttu-id="ea9e1-112">此外，管理和报告功能将受到限制。</span><span class="sxs-lookup"><span data-stu-id="ea9e1-112">Also, management and reporting capabilities will be limited.</span></span> <span data-ttu-id="ea9e1-113">Microsoft 建议企业选择其主防病毒解决方案，并专门使用它。</span><span class="sxs-lookup"><span data-stu-id="ea9e1-113">Microsoft recommends enterprises choose their primary antivirus solution and use it exclusively.</span></span>

## <a name="how-to-enable-limited-periodic-scanning"></a><span data-ttu-id="ea9e1-114">如何启用有限定期扫描</span><span class="sxs-lookup"><span data-stu-id="ea9e1-114">How to enable limited periodic scanning</span></span>

<span data-ttu-id="ea9e1-115">默认情况下，如果没有安装其他防病毒产品，或者其他产品过期、过期或无法正常工作，Microsoft Defender 防病毒将在 Windows 10 设备上自行启用。</span><span class="sxs-lookup"><span data-stu-id="ea9e1-115">By default, Microsoft Defender Antivirus will enable itself on a Windows 10 device if there is no other antivirus product installed, or if the other product is out-of-date, expired, or not working correctly.</span></span>

<span data-ttu-id="ea9e1-116">如果启用了 Microsoft Defender 防病毒，则将显示用于配置该设备的常用选项：</span><span class="sxs-lookup"><span data-stu-id="ea9e1-116">If Microsoft Defender Antivirus is enabled, the usual options will appear to configure it on that device:</span></span>

![显示 Microsoft Defender AV 选项（包括扫描选项、设置和更新选项）的 Windows 安全应用](images/vtp-wdav.png)

<span data-ttu-id="ea9e1-118">如果安装了另一个防病毒产品并正常运行，Microsoft Defender 防病毒将自行禁用。</span><span class="sxs-lookup"><span data-stu-id="ea9e1-118">If another antivirus product is installed and working correctly, Microsoft Defender Antivirus will disable itself.</span></span> <span data-ttu-id="ea9e1-119">Windows 安全应用 **将更改病毒** &威胁防护部分以显示有关 AV 产品的状态，并提供指向产品配置选项的链接。</span><span class="sxs-lookup"><span data-stu-id="ea9e1-119">The Windows Security app will change the **Virus & threat protection** section to show status about the AV product, and provide a link to the product's configuration options.</span></span>

<span data-ttu-id="ea9e1-120">在任何第三方 AV 产品下，新链接将显示为 **Microsoft Defender 防病毒选项**。</span><span class="sxs-lookup"><span data-stu-id="ea9e1-120">Underneath any third party AV products, a new link will appear as **Microsoft Defender Antivirus options**.</span></span> <span data-ttu-id="ea9e1-121">单击此链接将展开以显示启用有限定期扫描的切换。</span><span class="sxs-lookup"><span data-stu-id="ea9e1-121">Clicking this link will expand to show the toggle that enables limited periodic scanning.</span></span> <span data-ttu-id="ea9e1-122">请注意，有限定期选项是启用或禁用定期扫描的开关。</span><span class="sxs-lookup"><span data-stu-id="ea9e1-122">Note that the limited periodic option is a toggle to enable or disable periodic scanning.</span></span> 

<span data-ttu-id="ea9e1-123">将开关滑动到 **开** 将显示第三方 AV 产品下方的标准 Microsoft Defender AV 选项。</span><span class="sxs-lookup"><span data-stu-id="ea9e1-123">Sliding the switch to **On** will show the standard Microsoft Defender AV options underneath the third party AV product.</span></span> <span data-ttu-id="ea9e1-124">有限定期扫描选项将显示在页面底部。</span><span class="sxs-lookup"><span data-stu-id="ea9e1-124">The limited periodic scanning option will appear at the bottom of the page.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ea9e1-125">相关文章</span><span class="sxs-lookup"><span data-stu-id="ea9e1-125">Related articles</span></span>

- [<span data-ttu-id="ea9e1-126">配置行为、启发式和实时保护</span><span class="sxs-lookup"><span data-stu-id="ea9e1-126">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ea9e1-127">Windows 10 中的 Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="ea9e1-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)