---
title: 主题
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
description: ''
ms.openlocfilehash: 4387c5e8fc199f0f8642041473d5f28f2f9b401b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601379"
---
# <a name="themes"></a><span data-ttu-id="d0ce5-102">主题</span><span class="sxs-lookup"><span data-stu-id="d0ce5-102">Themes</span></span>

<span data-ttu-id="d0ce5-103">用户如何编写文档？</span><span class="sxs-lookup"><span data-stu-id="d0ce5-103">How does a person write a document?</span></span> <span data-ttu-id="d0ce5-104">它们通常从要在文档中传达的一个或多个想法开始，并使用与想法一致的单词进行撰写。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-104">They generally start with one or more ideas they want to convey in the document, and compose using words that align with the ideas.</span></span> <span data-ttu-id="d0ce5-105">概念越普遍，与该想法相关的词越常见。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-105">The more prevalent an idea is, the more frequent the words that are related to that idea tend to be.</span></span> <span data-ttu-id="d0ce5-106">这将通知用户也如何使用文档。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-106">This informs how people consume documents as well.</span></span> <span data-ttu-id="d0ce5-107">从阅读文档中了解的重要一点是文档试图传达的想法、在何处显示了哪些想法以及这些想法之间的关系。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-107">The important thing to understand from reading a document is the ideas that the document is trying to convey, which ideas appear where, and what the relationships between the ideas are.</span></span>

<span data-ttu-id="d0ce5-108">这可以扩展到用户想要使用一组文档的方式。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-108">This can be extended to how a person wants to consume a set of documents.</span></span> <span data-ttu-id="d0ce5-109">他们想要了解哪些想法在集合中，以及哪些文档在谈论这些想法。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-109">They want to see which ideas are present in the sets, and which documents are talking about those ideas.</span></span> <span data-ttu-id="d0ce5-110">此外，如果他们找到感兴趣的特定文档，他们希望能够查看讨论类似想法的文档。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-110">Also, if they find a particular document of interest, they want to be able to see documents that discuss similar ideas.</span></span>

<span data-ttu-id="d0ce5-111">高级电子数据展示中的主题功能尝试通过分析审阅集中讨论的*主题*并将主题分配给审阅集中的文档来模拟有关文档的人为原因的情况。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-111">The Themes functionality in Advanced eDiscovery attempts to mimic how humans reason about documents, by analyzing the *themes* that are discussed in a review set and assigning a theme to documents in the review set.</span></span> <span data-ttu-id="d0ce5-112">在高级电子数据展示中，主题更进一步，并确定每个文档中的*主要主题*。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-112">In Advanced eDiscovery, Themes goes one step further and identifies the *dominant theme* in each document.</span></span> <span data-ttu-id="d0ce5-113">主主题是在文档中显示的最常用主题。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-113">The dominant theme is the one that appears the most often in a document.</span></span>

## <a name="how-does-themes-work"></a><span data-ttu-id="d0ce5-114">主题的工作原理是什么？</span><span class="sxs-lookup"><span data-stu-id="d0ce5-114">How does Themes work?</span></span>

<span data-ttu-id="d0ce5-115">主题功能使用审阅集中的文本分析文档，以分析在审阅集中的所有文档中显示的常见主题。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-115">The Themes functionality analyzes documents with text in a review set to parse out common themes that appear across all the documents in the review set.</span></span> <span data-ttu-id="d0ce5-116">高级电子数据展示将这些主题分配到它们出现的文档中。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-116">Advanced eDiscovery assigns those themes to the documents in which they appear.</span></span> <span data-ttu-id="d0ce5-117">它还将每个主题标记为主题的代表文档中使用的单词。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-117">It also labels each theme with the words used in the documents that are representative of the theme.</span></span> <span data-ttu-id="d0ce5-118">由于文档可以包含各种类型的主题，因此高级电子数据展示通常会为文档分配多个主题。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-118">Because a document can contain various types of subject matter, Advanced eDiscovery often assigns multiple themes to documents.</span></span> <span data-ttu-id="d0ce5-119">文档中显示最醒目的主题被指定为其主要主题。</span><span class="sxs-lookup"><span data-stu-id="d0ce5-119">The theme that appears most prominently in a document is designated as its dominant theme.</span></span>