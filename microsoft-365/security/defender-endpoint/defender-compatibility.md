---
title: Microsoft Defender 防病毒与适用于终结点的 Defender 的兼容性
description: 了解 Windows Defender Defender for Endpoint 的工作原理，以及它如何使用第三方反恶意软件客户端。
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: a8dca4a80385fabcdc64a5584474214d05be4a6c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935373"
---
# <a name="microsoft-defender-antivirus-compatibility-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="eab16-104">Microsoft Defender 防病毒与 Microsoft Defender for Endpoint 的兼容性</span><span class="sxs-lookup"><span data-stu-id="eab16-104">Microsoft Defender Antivirus compatibility with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eab16-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="eab16-105">**Applies to:**</span></span>
- [<span data-ttu-id="eab16-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="eab16-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eab16-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eab16-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="eab16-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="eab16-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="eab16-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="eab16-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

<span data-ttu-id="eab16-110">Microsoft Defender for Endpoint 代理依赖 Microsoft Defender 防病毒进行某些功能，如文件扫描。</span><span class="sxs-lookup"><span data-stu-id="eab16-110">The Microsoft Defender for Endpoint agent depends on Microsoft Defender Antivirus for some capabilities such as file scanning.</span></span>

>[!IMPORTANT]
><span data-ttu-id="eab16-111">Defender for Endpoint 不遵循 Microsoft Defender 防病毒排除设置。</span><span class="sxs-lookup"><span data-stu-id="eab16-111">Defender for Endpoint does not adhere to the Microsoft Defender Antivirus Exclusions settings.</span></span> 

<span data-ttu-id="eab16-112">你必须在 Defender for Endpoint 设备上配置安全智能更新，无论 Microsoft Defender 防病毒是否是活动的反恶意软件。</span><span class="sxs-lookup"><span data-stu-id="eab16-112">You must configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="eab16-113">有关详细信息，请参阅管理 [Microsoft Defender 防病毒更新和应用基线](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="eab16-113">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="eab16-114">如果载入的设备受第三方反恶意软件客户端保护，该终结点上的 Microsoft Defender 防病毒将进入被动模式。</span><span class="sxs-lookup"><span data-stu-id="eab16-114">If an onboarded device is protected by a third-party antimalware client, Microsoft Defender Antivirus on that endpoint will enter into passive mode.</span></span>

<span data-ttu-id="eab16-115">Microsoft Defender 防病毒将继续接收更新 *，mspeng.exe* 进程将列为正在运行的服务，但它不会执行扫描，并且不会替换正在运行的第三方反恶意软件客户端。</span><span class="sxs-lookup"><span data-stu-id="eab16-115">Microsoft Defender Antivirus will continue to receive updates, and the *mspeng.exe* process will be listed as a running a service, but it will not perform scans and will not replace the running third-party antimalware client.</span></span>

<span data-ttu-id="eab16-116">Microsoft Defender 防病毒界面将被禁用，并且设备上的用户将不能使用 Microsoft Defender 防病毒执行按需扫描或配置大多数选项。</span><span class="sxs-lookup"><span data-stu-id="eab16-116">The Microsoft Defender Antivirus interface will be disabled, and users on the device will not be able to use Microsoft Defender Antivirus to perform on-demand scans or configure most options.</span></span>

<span data-ttu-id="eab16-117">有关详细信息，请参阅 Microsoft [Defender 防病毒和适用于终结点的 Defender 兼容性主题](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。</span><span class="sxs-lookup"><span data-stu-id="eab16-117">For more information, see the [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
