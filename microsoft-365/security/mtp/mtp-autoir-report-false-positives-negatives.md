---
title: 如何在 Microsoft 威胁防护中报告空气中的误报或虚假否定
description: 无线在 Microsoft 威胁防护中是否已错过或错误地检测到了什么？ 了解如何向 Microsoft 提交误报或漏报以进行分析。
keywords: 自动化、调查、警报、触发器、操作、修正、误报、假负
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: d62f10cdf9805cdcfae7ba5bd5381ca589d1297c
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260190"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="49faf-105">如何报告自动调查和响应功能中的误报/否定</span><span class="sxs-lookup"><span data-stu-id="49faf-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="49faf-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="49faf-106">**Applies to:**</span></span>
- <span data-ttu-id="49faf-107">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="49faf-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="49faf-108">在 Microsoft 威胁防护中是否进行了[自动化调查和响应功能](mtp-autoir.md)丢失或错误地检测到了什么？</span><span class="sxs-lookup"><span data-stu-id="49faf-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="49faf-109">你可以将其报告给 Microsoft 或调整你的通知（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="49faf-109">You can report it to Microsoft or adjust your alerts (if needed).</span></span> <span data-ttu-id="49faf-110">使用下表作为指南：</span><span class="sxs-lookup"><span data-stu-id="49faf-110">Use the following table as a guide:</span></span> 


|<span data-ttu-id="49faf-111">Item</span><span class="sxs-lookup"><span data-stu-id="49faf-111">Item</span></span>  |<span data-ttu-id="49faf-112">检测人</span><span class="sxs-lookup"><span data-stu-id="49faf-112">Detected by</span></span>  |<span data-ttu-id="49faf-113">如何报告</span><span class="sxs-lookup"><span data-stu-id="49faf-113">How to report it</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="49faf-114">电子邮件</span><span class="sxs-lookup"><span data-stu-id="49faf-114">Email message</span></span> <br/><span data-ttu-id="49faf-115">电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="49faf-115">Email attachment</span></span> <br/><span data-ttu-id="49faf-116">电子邮件或 Office 文件中的 URL</span><span class="sxs-lookup"><span data-stu-id="49faf-116">URL in an email message or Office file</span></span>      |[<span data-ttu-id="49faf-117">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="49faf-117">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="49faf-118">将可疑的垃圾邮件、网络钓鱼、Url 和文件提交到 Microsoft for Office 365 扫描</span><span class="sxs-lookup"><span data-stu-id="49faf-118">Submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="49faf-119">设备上的文件或应用</span><span class="sxs-lookup"><span data-stu-id="49faf-119">File or app on a device</span></span>    |[<span data-ttu-id="49faf-120">Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="49faf-120">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="49faf-121">将文件提交给 Microsoft 进行恶意软件分析</span><span class="sxs-lookup"><span data-stu-id="49faf-121">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |
|<span data-ttu-id="49faf-122">由合法使用触发的警报</span><span class="sxs-lookup"><span data-stu-id="49faf-122">Alert triggered by legitimate use</span></span> <br/><span data-ttu-id="49faf-123">警报不准确</span><span class="sxs-lookup"><span data-stu-id="49faf-123">Inaccurate alert</span></span>    |[<span data-ttu-id="49faf-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="49faf-124">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="49faf-125">或</span><span class="sxs-lookup"><span data-stu-id="49faf-125">or</span></span> <br/>[<span data-ttu-id="49faf-126">Azure 高级威胁检测</span><span class="sxs-lookup"><span data-stu-id="49faf-126">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="49faf-127">在云应用安全门户中管理通知</span><span class="sxs-lookup"><span data-stu-id="49faf-127">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |


## <a name="next-steps"></a><span data-ttu-id="49faf-128">后续步骤</span><span class="sxs-lookup"><span data-stu-id="49faf-128">Next steps</span></span>

- [<span data-ttu-id="49faf-129">批准或拒绝与自动调查和响应相关的操作</span><span class="sxs-lookup"><span data-stu-id="49faf-129">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="49faf-130">详细了解操作中心</span><span class="sxs-lookup"><span data-stu-id="49faf-130">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="49faf-131">通过 Microsoft 威胁防护中的高级搜寻主动搜寻威胁</span><span class="sxs-lookup"><span data-stu-id="49faf-131">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
