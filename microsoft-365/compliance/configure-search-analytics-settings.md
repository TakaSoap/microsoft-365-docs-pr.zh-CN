---
title: 配置搜索和分析设置-数据调查
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解如何在管理数据调查时配置搜索和分析设置，如临近重复项、电子邮件线程和主题。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3100c83fc027e793f7937a4d27e059ce7e3038a0
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527348"
---
# <a name="configure-search-and-analytics-settings"></a><span data-ttu-id="4cda0-103">配置搜索和分析设置</span><span class="sxs-lookup"><span data-stu-id="4cda0-103">Configure search and analytics settings</span></span>

## <a name="near-duplicates-and-email-threading"></a><span data-ttu-id="4cda0-104">临近重复项和电子邮件线程</span><span class="sxs-lookup"><span data-stu-id="4cda0-104">Near duplicates and email threading</span></span>

<span data-ttu-id="4cda0-105">在此部分中，您可以设置重复检测、接近重复检测和电子邮件线程的参数。</span><span class="sxs-lookup"><span data-stu-id="4cda0-105">In this section, you can set parameters for duplicate detection, near duplicate detection, and email threading.</span></span>

- <span data-ttu-id="4cda0-106">启用/禁用：包括重复检测、接近重复检测和电子邮件线程（如果已启用）作为分析流的一部分。</span><span class="sxs-lookup"><span data-stu-id="4cda0-106">Enable/disable: include duplicate detection, near duplicate detection, and email threading as part of analytics flow if enabled.</span></span> <span data-ttu-id="4cda0-107">由于它们是相互依赖的，因此必须全部启用或禁用所有这些版本。</span><span class="sxs-lookup"><span data-stu-id="4cda0-107">Because they build on top of each other, you must enable all of them or disable all of them.</span></span>

- <span data-ttu-id="4cda0-108">阈值：如果两个文档的相似性级别高于阈值，则它们将放在相同的临近重复集内。</span><span class="sxs-lookup"><span data-stu-id="4cda0-108">Threshold: if the similarity level of two documents is above the threshold, they will be put in the same near duplicate set.</span></span>

- <span data-ttu-id="4cda0-109">默认情况下隐藏重复项：如果启用此设置，则默认情况下将在工作集中应用用于隐藏重复文档的筛选器。</span><span class="sxs-lookup"><span data-stu-id="4cda0-109">Hide duplicates by default: if this setting is on, a filter to hide duplicate documents will be applied in the working set by default.</span></span> <span data-ttu-id="4cda0-110">如果需要，可以在工作集中手动删除筛选器。</span><span class="sxs-lookup"><span data-stu-id="4cda0-110">The filter can be removed manually in the working set if necessary.</span></span>

- <span data-ttu-id="4cda0-111">最小/最大单词数：临近重复项和电子邮件线程处理将仅在至少包含最少单词数和最大单词数的文档中运行。</span><span class="sxs-lookup"><span data-stu-id="4cda0-111">Minimum/maximum number of words: near duplicates and email threading will run only on documents that have at least the minimum number of words and at most the maximum number of words.</span></span>

<span data-ttu-id="4cda0-112">有关详细信息，请参阅[接近重复检测](near-duplicates.md)和[电子邮件线程](email-threading.md)。</span><span class="sxs-lookup"><span data-stu-id="4cda0-112">For more information, see [Near duplicate detection](near-duplicates.md) and [Email threading](email-threading.md).</span></span>

## <a name="themes"></a><span data-ttu-id="4cda0-113">主题</span><span class="sxs-lookup"><span data-stu-id="4cda0-113">Themes</span></span>

<span data-ttu-id="4cda0-114">在本节中，您可以设置主题的参数。</span><span class="sxs-lookup"><span data-stu-id="4cda0-114">In this section, you can set parameters for themes.</span></span>

- <span data-ttu-id="4cda0-115">启用/禁用：将主题群集包含为分析流（如果已启用）的一部分。</span><span class="sxs-lookup"><span data-stu-id="4cda0-115">Enable/disable: include themes clustering as part of analytics flow if enabled.</span></span>

- <span data-ttu-id="4cda0-116">动态调整主题的最大数量：在某些情况下，没有足够的文档来生成所需数量的主题。</span><span class="sxs-lookup"><span data-stu-id="4cda0-116">Adjust maximum number of themes dynamically: in certain cases, there are not enough documents to produce the desired number of themes.</span></span> <span data-ttu-id="4cda0-117">如果启用此设置，则不是尝试强制实施所需的最大主题数，系统会动态调整最大主题数。</span><span class="sxs-lookup"><span data-stu-id="4cda0-117">If this setting is turned on, then rather than trying to force the desired maximum number of themes, the system adjusts maximum number of themes dynamically.</span></span>

- <span data-ttu-id="4cda0-118">主题的最大数量：所需的主题数。</span><span class="sxs-lookup"><span data-stu-id="4cda0-118">Maximum number of themes: desired number of themes.</span></span>

- <span data-ttu-id="4cda0-119">主题中包含数字：如果启用此选项，它将在生成主题时包含数字。</span><span class="sxs-lookup"><span data-stu-id="4cda0-119">Include numbers in themes: When enabled, it will include numbers in when generating themes.</span></span>  

## <a name="optical-character-recognition-ocr"></a><span data-ttu-id="4cda0-120">光学字符识别（OCR）</span><span class="sxs-lookup"><span data-stu-id="4cda0-120">Optical character recognition (OCR)</span></span>

<span data-ttu-id="4cda0-121">启用此设置后，OCR 将在引入工作集的图像上运行，以便可以对其进行搜索。</span><span class="sxs-lookup"><span data-stu-id="4cda0-121">When this setting is turned on, OCR will be run on images that are ingested into working sets so that they can be searchable.</span></span>

## <a name="ignore-text"></a><span data-ttu-id="4cda0-122">忽略文本</span><span class="sxs-lookup"><span data-stu-id="4cda0-122">Ignore text</span></span>

<span data-ttu-id="4cda0-123">有些情况下，某些文本会降低分析质量，例如，如果不考虑电子邮件的内容，则添加到特定电子邮件的冗长免责声明。</span><span class="sxs-lookup"><span data-stu-id="4cda0-123">There are instances where certain texts will diminish the quality of analytics, such as lengthy disclaimers that get added to certain emails regardless of the content of the email.</span></span> <span data-ttu-id="4cda0-124">如果您知道这种情况，可以通过指定文本（RegEx 受支持）以及应排除文本的模块来从分析中排除此文本。</span><span class="sxs-lookup"><span data-stu-id="4cda0-124">If you are aware of such cases, you can exclude this text from analytics by specifying the text (RegEx is supported) and which modules that text should be excluded for.</span></span>
