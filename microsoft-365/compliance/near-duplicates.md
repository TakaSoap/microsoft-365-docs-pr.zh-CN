---
title: 接近重复检测-数据调查
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
description: 在管理数据调查时，在分析数据调查中的证据时，使用接近重复检测功能将类似的文档分组在一起 (预览) 。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 37ce968016e674ec83da536c65361d2075cf9bbb
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285948"
---
# <a name="near-duplicate-detection"></a><span data-ttu-id="95cee-103">近似重复检测</span><span class="sxs-lookup"><span data-stu-id="95cee-103">Near duplicate detection</span></span>

<span data-ttu-id="95cee-104">考虑要审阅的一组文档，其中子集基于同一个模板，大多数采用相同的样本语言，但此处和此处有一些差异。</span><span class="sxs-lookup"><span data-stu-id="95cee-104">Consider a set of documents to be reviewed in which a subset is based on the same template and has mostly the same boilerplate language, with a few differences here and there.</span></span> <span data-ttu-id="95cee-105">如果某个审阅者可以识别此子集，请仔细查看其中一项，并查看 rest 的不同之处，他们不会错过任何独特的信息，而只需要花费一小时间来阅读所有文档封面。</span><span class="sxs-lookup"><span data-stu-id="95cee-105">If a reviewer could identify this subset, review one of them thoroughly, and review the differences for the rest, they would not have missed any unique information while taking only a fraction of time that would have taken them to read all documents cover to cover.</span></span> <span data-ttu-id="95cee-106">临近的重复检测将多个类似的文档组合在一起，以帮助您更有效地查看您的审阅过程。</span><span class="sxs-lookup"><span data-stu-id="95cee-106">Near duplicate detection groups textually similar documents together to help you make your review process more efficient.</span></span>

## <a name="how-does-it-work"></a><span data-ttu-id="95cee-107">它是如何运行的？</span><span class="sxs-lookup"><span data-stu-id="95cee-107">How does it work?</span></span>

<span data-ttu-id="95cee-108">在接近重复检测运行时，系统会使用文本分析每个文档。</span><span class="sxs-lookup"><span data-stu-id="95cee-108">When near duplicate detection is run, the system parses every document with text.</span></span> <span data-ttu-id="95cee-109">然后，它将每个文档进行比较，以确定它们的相似性是否大于设定的阈值。</span><span class="sxs-lookup"><span data-stu-id="95cee-109">Then, it compares every document against each other to determine whether their similarity is greater than the set threshold.</span></span> <span data-ttu-id="95cee-110">如果是，则将文档组合在一起。</span><span class="sxs-lookup"><span data-stu-id="95cee-110">If it is, the documents are grouped together.</span></span> <span data-ttu-id="95cee-111">对所有文档进行了比较和分组后，每个组中的一个文档将标记为 "pivot";在审阅文档中，可以先查看数据透视，并查看相同临近重复集的其他文档，重点介绍正在审阅的数据透视和文档之间的差异。</span><span class="sxs-lookup"><span data-stu-id="95cee-111">Once all documents have been compared and grouped, a document from each group is marked as the "pivot"; in reviewing your documents, you can review a pivot first and review the other documents in the same near duplicate set, focusing on the difference between the pivot and the document that is in review.</span></span>
