---
title: 近重复检测 - 电子数据展示
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
description: 在分析文档中的大小写数据时，使用近重复检测对文本类似的文档Advanced eDiscovery。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286018"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a><span data-ttu-id="99a96-103">在数据中接近重复Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="99a96-103">Near duplicate detection in Advanced eDiscovery</span></span>

<span data-ttu-id="99a96-104">请考虑要审阅的一组文档，其中一个子集基于同一模板，并且主要具有相同的样本语言，并且存在一些差异。</span><span class="sxs-lookup"><span data-stu-id="99a96-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="99a96-105">如果审阅者可以识别此子集，彻底审阅其中一个子集，并查看其余部分的差异，则他们不会错过任何唯一信息，而只是花时间阅读所有文档涵盖内容所花时间的一小部分。</span><span class="sxs-lookup"><span data-stu-id="99a96-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="99a96-106">近似重复检测组将文本类似的文档整理到一起，以便帮助你提高审阅流程的效率。</span><span class="sxs-lookup"><span data-stu-id="99a96-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="99a96-107">它的工作原理</span><span class="sxs-lookup"><span data-stu-id="99a96-107">How does it work?</span></span>

<span data-ttu-id="99a96-108">运行近似重复检测时，系统会对每一份包含文本的文档展开分析。</span><span class="sxs-lookup"><span data-stu-id="99a96-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="99a96-109">然后，系统会将每份文档相互比对，以确定其相似性是否大于设置阈值。</span><span class="sxs-lookup"><span data-stu-id="99a96-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="99a96-110">如果是，则这些文档将被组合在一起。</span><span class="sxs-lookup"><span data-stu-id="99a96-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="99a96-111">对所有文档进行比对和分组后，每一组会有一份文档被标记为“核心文档”；在审阅文档时，可以先查看“核心文档”，然后查看位于相同近似重复集内的其他文件。重点关注核心文档和正在审阅的文档之间的差异。</span><span class="sxs-lookup"><span data-stu-id="99a96-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
