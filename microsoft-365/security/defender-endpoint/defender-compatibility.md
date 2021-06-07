---
title: 防病毒解决方案与 Defender for Endpoint 的兼容性
description: 了解Windows Defender Microsoft Defender for Endpoint 的工作原理，以及它如何使用第三方反恶意软件客户端。
keywords: windows defender 兼容性， defender， 适用于终结点的 Microsoft Defender， 终结点的 defender， 防病毒， mde
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
ms.topic: conceptual
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: f5a0db755f919cb47c4cd284857ddf4e27d16996
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782881"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="a1a6a-104">防病毒解决方案与 Microsoft Defender for Endpoint 的兼容性</span><span class="sxs-lookup"><span data-stu-id="a1a6a-104">Antivirus solution compatibility with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a1a6a-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a1a6a-105">**Applies to:**</span></span>
- [<span data-ttu-id="a1a6a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a1a6a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a1a6a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1a6a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="a1a6a-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="a1a6a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a1a6a-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="a1a6a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

<span data-ttu-id="a1a6a-110">Microsoft Defender for Endpoint 代理依赖于Microsoft Defender 防病毒某些功能（如文件扫描）的功能。</span><span class="sxs-lookup"><span data-stu-id="a1a6a-110">The Microsoft Defender for Endpoint agent depends on Microsoft Defender Antivirus for some capabilities such as file scanning.</span></span>

>[!IMPORTANT]
><span data-ttu-id="a1a6a-111">Defender for Endpoint 不遵循"Microsoft Defender 防病毒排除"设置。</span><span class="sxs-lookup"><span data-stu-id="a1a6a-111">Defender for Endpoint does not adhere to the Microsoft Defender Antivirus Exclusions settings.</span></span> 

<span data-ttu-id="a1a6a-112">你必须在 Defender for Endpoint 设备上配置安全智能更新，Microsoft Defender 防病毒反恶意软件是否有效。</span><span class="sxs-lookup"><span data-stu-id="a1a6a-112">You must configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="a1a6a-113">有关详细信息，请参阅管理更新[Microsoft Defender 防病毒应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="a1a6a-113">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="a1a6a-114">如果载入的设备受第三方反恶意软件客户端保护，Microsoft Defender 防病毒上的设备将进入被动模式。</span><span class="sxs-lookup"><span data-stu-id="a1a6a-114">If an onboarded device is protected by a third-party antimalware client, Microsoft Defender Antivirus on that endpoint will enter into passive mode.</span></span>

<span data-ttu-id="a1a6a-115">Microsoft Defender 防病毒接收更新，mspeng.exe进程将列为正在运行的服务，但它不会执行扫描，并且不会替换正在运行的第三方反恶意软件客户端。</span><span class="sxs-lookup"><span data-stu-id="a1a6a-115">Microsoft Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.</span></span>

<span data-ttu-id="a1a6a-116">设备Microsoft Defender 防病毒将禁用，并且设备上的用户将Microsoft Defender 防病毒执行按需扫描或配置大多数选项。</span><span class="sxs-lookup"><span data-stu-id="a1a6a-116">The Microsoft Defender Antivirus interface will be disabled, and users on the device will not be able to use Microsoft Defender Antivirus to perform on-demand scans or configure most options.</span></span>

<span data-ttu-id="a1a6a-117">有关详细信息，请参阅适用于终结点的[Microsoft Defender 防病毒和 Defender 兼容性主题](microsoft-defender-antivirus-compatibility.md)。</span><span class="sxs-lookup"><span data-stu-id="a1a6a-117">For more information, see the [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic](microsoft-defender-antivirus-compatibility.md).</span></span>
