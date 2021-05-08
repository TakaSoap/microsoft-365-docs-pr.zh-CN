---
title: 评估 Microsoft Defender 防病毒软件
description: 各种规模的企业都可以使用本指南评估和测试企业在Microsoft Defender 防病毒所提供的Windows 10。
keywords: Microsoft Defender 防病毒， 云保护， 云， 反恶意软件， 安全性， defender， 评估， 测试， 保护， 比较， 实时保护
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4f789ab80d48966d4cf922811d05d74882d728fe
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274732"
---
# <a name="evaluate-microsoft-defender-antivirus"></a><span data-ttu-id="ece2b-104">评估 Microsoft Defender 防病毒软件</span><span class="sxs-lookup"><span data-stu-id="ece2b-104">Evaluate Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ece2b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="ece2b-105">**Applies to:**</span></span>

- [<span data-ttu-id="ece2b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ece2b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ece2b-107">使用本指南可确定Microsoft Defender 防病毒保护您免受病毒、恶意软件和可能不需要的应用程序的侵害。</span><span class="sxs-lookup"><span data-stu-id="ece2b-107">Use this guide to determine how well Microsoft Defender Antivirus protects you from viruses, malware, and potentially unwanted applications.</span></span>

>[!TIP]
><span data-ttu-id="ece2b-108">还可以访问 Microsoft Defender for Endpoint 演示[](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)网站，demo.wd.microsoft.com 以确认以下功能是否正常工作并查看这些功能如何工作：</span><span class="sxs-lookup"><span data-stu-id="ece2b-108">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working and see how they work:</span></span>
>- <span data-ttu-id="ece2b-109">云端保护</span><span class="sxs-lookup"><span data-stu-id="ece2b-109">Cloud-delivered protection</span></span>
>- <span data-ttu-id="ece2b-110">快速学习 (包括首次看到时阻止) </span><span class="sxs-lookup"><span data-stu-id="ece2b-110">Fast learning (including Block at first sight)</span></span>
>- <span data-ttu-id="ece2b-111">可能不需要的应用程序阻止</span><span class="sxs-lookup"><span data-stu-id="ece2b-111">Potentially unwanted application blocking</span></span>

<span data-ttu-id="ece2b-112">它介绍了适用于中小型企业的 Microsoft Defender 防病毒 的重要下一代保护功能，以及这些功能如何增强整个网络的恶意软件检测和保护。</span><span class="sxs-lookup"><span data-stu-id="ece2b-112">It explains the important next-generation protection features of Microsoft Defender Antivirus available for both small and large enterprises, and how they increase malware detection and protection across your network.</span></span>

<span data-ttu-id="ece2b-113">可以选择单独配置和评估每个设置，也可以一次配置和评估所有设置。</span><span class="sxs-lookup"><span data-stu-id="ece2b-113">You can choose to configure and evaluate each setting independently, or all at once.</span></span> <span data-ttu-id="ece2b-114">我们已根据典型评估方案对类似的设置进行分组，并包括有关使用 PowerShell 启用设置的说明。</span><span class="sxs-lookup"><span data-stu-id="ece2b-114">We have grouped similar settings based upon typical evaluation scenarios, and include instructions for using PowerShell to enable the settings.</span></span>

<span data-ttu-id="ece2b-115">本指南以 PDF 格式提供，以便脱机查看：</span><span class="sxs-lookup"><span data-stu-id="ece2b-115">The guide is available in PDF format for offline viewing:</span></span>

- [<span data-ttu-id="ece2b-116">下载 PDF 格式的指南</span><span class="sxs-lookup"><span data-stu-id="ece2b-116">Download the guide in PDF format</span></span>](https://www.microsoft.com/download/details.aspx?id=54795)

<span data-ttu-id="ece2b-117">还可以下载 PowerShell，以自动启用指南中所述的所有设置。</span><span class="sxs-lookup"><span data-stu-id="ece2b-117">You can also download a PowerShell that will enable all the settings described in the guide automatically.</span></span> <span data-ttu-id="ece2b-118">你可以与上述 PDF 下载一起获取脚本，也可以从 PowerShell 库单独获取：</span><span class="sxs-lookup"><span data-stu-id="ece2b-118">You can obtain the script alongside the PDF download above, or individually from PowerShell Gallery:</span></span>

- [<span data-ttu-id="ece2b-119">下载 PowerShell 脚本以自动配置设置</span><span class="sxs-lookup"><span data-stu-id="ece2b-119">Download the PowerShell script to automatically configure the settings</span></span>](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> <span data-ttu-id="ece2b-120">本指南目前适用于单计算机对Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="ece2b-120">The guide is currently intended for single-machine evaluation of Microsoft Defender Antivirus.</span></span> <span data-ttu-id="ece2b-121">启用本指南中所有设置可能不适合实际部署。</span><span class="sxs-lookup"><span data-stu-id="ece2b-121">Enabling all of the settings in this guide may not be suitable for real-world deployment.</span></span>
>
> <span data-ttu-id="ece2b-122">有关跨网络实际部署和监视 Microsoft Defender 防病毒的最新建议，请参阅部署[Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="ece2b-122">For the latest recommendations for real-world deployment and monitoring of Microsoft Defender Antivirus across a network, see [Deploy Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ece2b-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="ece2b-123">Related topics</span></span>

- [<span data-ttu-id="ece2b-124">Microsoft Defender 防病毒Windows 10</span><span class="sxs-lookup"><span data-stu-id="ece2b-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="ece2b-125">部署Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="ece2b-125">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)