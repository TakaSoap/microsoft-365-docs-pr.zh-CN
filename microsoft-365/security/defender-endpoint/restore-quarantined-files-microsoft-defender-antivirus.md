---
title: 在 Microsoft Defender AV 中还原隔离的文件
description: 你可以还原 Microsoft Defender AV 隔离的文件和文件夹。
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/20/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: e0253c4ac7d92c91e3fda45681568d721645f2b0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275380"
---
# <a name="restore-quarantined-files-in-microsoft-defender-av"></a><span data-ttu-id="83963-103">在 Microsoft Defender AV 中还原隔离的文件</span><span class="sxs-lookup"><span data-stu-id="83963-103">Restore quarantined files in Microsoft Defender AV</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="83963-104">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="83963-104">**Applies to:**</span></span>

- [<span data-ttu-id="83963-105">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="83963-105">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="83963-106">如果Microsoft Defender 防病毒配置为检测和修正设备上的威胁，Microsoft Defender 防病毒隔离可疑文件。</span><span class="sxs-lookup"><span data-stu-id="83963-106">If Microsoft Defender Antivirus is configured to detect and remediate threats on your device, Microsoft Defender Antivirus quarantines suspicious files.</span></span> <span data-ttu-id="83963-107">如果确定隔离文件不是威胁，可以还原它。</span><span class="sxs-lookup"><span data-stu-id="83963-107">If you are certain a quarantined file is not a threat, you can restore it.</span></span>

1. <span data-ttu-id="83963-108">打开 **Windows 安全中心。**</span><span class="sxs-lookup"><span data-stu-id="83963-108">Open **Windows Security**.</span></span>
2. <span data-ttu-id="83963-109">选择 **病毒&威胁防护，** 然后单击保护 **历史记录**。</span><span class="sxs-lookup"><span data-stu-id="83963-109">Select **Virus & threat protection** and then click **Protection history**.</span></span>
3. <span data-ttu-id="83963-110">在所有最近项的列表中，筛选"**隔离项目"。**</span><span class="sxs-lookup"><span data-stu-id="83963-110">In the list of all recent items, filter on **Quarantined Items**.</span></span>
4. <span data-ttu-id="83963-111">选择要保留的项，然后执行还原等操作。</span><span class="sxs-lookup"><span data-stu-id="83963-111">Select an item you want to keep, and take an action, such as restore.</span></span>

> [!TIP]
> <span data-ttu-id="83963-112">还可使用命令提示符从隔离区还原文件。</span><span class="sxs-lookup"><span data-stu-id="83963-112">Restoring a file from quarantine can also be done using Command Prompt.</span></span> <span data-ttu-id="83963-113">请参阅 [从隔离区还原文件](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine)。</span><span class="sxs-lookup"><span data-stu-id="83963-113">See [Restore a file from quarantine](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine).</span></span> 

## <a name="related-articles"></a><span data-ttu-id="83963-114">相关文章</span><span class="sxs-lookup"><span data-stu-id="83963-114">Related articles</span></span>

- [<span data-ttu-id="83963-115">配置扫描修正</span><span class="sxs-lookup"><span data-stu-id="83963-115">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
- [<span data-ttu-id="83963-116">查看扫描结果</span><span class="sxs-lookup"><span data-stu-id="83963-116">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md)
- [<span data-ttu-id="83963-117">根据文件名、扩展名和文件夹位置配置并验证排除项</span><span class="sxs-lookup"><span data-stu-id="83963-117">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="83963-118">配置并验证进程打开的文件的排除项</span><span class="sxs-lookup"><span data-stu-id="83963-118">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="83963-119">在 Microsoft Defender 防病毒 服务器上配置Windows排除项</span><span class="sxs-lookup"><span data-stu-id="83963-119">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)