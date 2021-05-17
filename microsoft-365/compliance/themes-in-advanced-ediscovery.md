---
title: 主题 - 电子数据展示
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 使用文档中Advanced eDiscovery主题，通过查找每个文档中的基准主题来组织审阅集。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285528"
---
# <a name="themes-in-advanced-ediscovery"></a><span data-ttu-id="7a33a-103">主题Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7a33a-103">Themes in Advanced eDiscovery</span></span>

<span data-ttu-id="7a33a-104">人员如何编写文档？</span><span class="sxs-lookup"><span data-stu-id="7a33a-104">How does a person write a document?</span></span> <span data-ttu-id="7a33a-105">他们通常从想要在文档中传达的一个或多个想法开始，然后使用与想法一致的字词撰写。</span><span class="sxs-lookup"><span data-stu-id="7a33a-105">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="7a33a-106">一种想法越流行，与该想法相关的字词越频繁。</span><span class="sxs-lookup"><span data-stu-id="7a33a-106">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="7a33a-107">这还通知用户如何使用文档。</span><span class="sxs-lookup"><span data-stu-id="7a33a-107">This informs how people consume documents as well.</span></span> <span data-ttu-id="7a33a-108">从阅读文档时，需要了解的一个重要内容是文档尝试传达的想法、哪些想法显示在何处以及这些想法之间的关系是什么。</span><span class="sxs-lookup"><span data-stu-id="7a33a-108">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="7a33a-109">这可扩展到用户想要使用一组文档的方式。</span><span class="sxs-lookup"><span data-stu-id="7a33a-109">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="7a33a-110">他们希望了解集合中的哪些想法，以及哪些文档正在讨论这些想法。</span><span class="sxs-lookup"><span data-stu-id="7a33a-110">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="7a33a-111">此外，如果他们找到感兴趣的特定文档，他们希望能够查看讨论类似想法的文档。</span><span class="sxs-lookup"><span data-stu-id="7a33a-111">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="7a33a-112">主题主题功能Advanced eDiscovery分析审阅集讨论的主题，并将主题分配给审阅集内的文档，来模拟用户对文档的原因。</span><span class="sxs-lookup"><span data-stu-id="7a33a-112">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="7a33a-113">在Advanced eDiscovery中，主题进一步 *标识每个文档中* 的基准主题。</span><span class="sxs-lookup"><span data-stu-id="7a33a-113">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="7a33a-114">基准主题是在文档中显示最为频繁的主题。</span><span class="sxs-lookup"><span data-stu-id="7a33a-114">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="7a33a-115">主题如何工作？</span><span class="sxs-lookup"><span data-stu-id="7a33a-115">How does Themes work?</span></span>

<span data-ttu-id="7a33a-116">主题功能可分析审阅集中含有文本的文档，解析出在审阅集内所有文档中的常见主题。</span><span class="sxs-lookup"><span data-stu-id="7a33a-116">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="7a33a-117">高级电子数据展示将主题分配給显示了这些主题的文档。</span><span class="sxs-lookup"><span data-stu-id="7a33a-117">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="7a33a-118">它还使用文档中能够代表主题的文字来标记每个主题。</span><span class="sxs-lookup"><span data-stu-id="7a33a-118">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="7a33a-119">由于文档可以包含各种类型的主题，因此高级电子数据展示通常会向文档分配多个主题。</span><span class="sxs-lookup"><span data-stu-id="7a33a-119">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="7a33a-120">文档中最突出的主题被指定为优势主题。</span><span class="sxs-lookup"><span data-stu-id="7a33a-120">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>
