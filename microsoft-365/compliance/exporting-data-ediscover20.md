---
title: 在高级电子数据展示中导出事例数据
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
description: 了解如何在高级电子数据展示事例中导出或下载演示文稿或外部审阅的审阅集中的内容。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 114264f342a51f3ce68696f321cf7c6e929dc6d1
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726474"
---
# <a name="export-case-data-in-advanced-ediscovery"></a><span data-ttu-id="02c9e-103">在高级电子数据展示中导出事例数据</span><span class="sxs-lookup"><span data-stu-id="02c9e-103">Export case data in Advanced eDiscovery</span></span>

<span data-ttu-id="02c9e-104">有三种方法可从审阅集中导出数据：</span><span class="sxs-lookup"><span data-stu-id="02c9e-104">There are three ways to export data from a review set:</span></span>

<span data-ttu-id="02c9e-105">**下载：** 下载（通过使用浏览器）一组较小的本机文件。</span><span class="sxs-lookup"><span data-stu-id="02c9e-105">**Download:** Download (by using a browser) a small set of native files.</span></span> <span data-ttu-id="02c9e-106">这是导出少量数据集的最快方法。</span><span class="sxs-lookup"><span data-stu-id="02c9e-106">This is the quickest way to export a small set of data.</span></span> <span data-ttu-id="02c9e-107">此方法保留本机文件名称。</span><span class="sxs-lookup"><span data-stu-id="02c9e-107">This method preserves the native file names.</span></span>

<span data-ttu-id="02c9e-108">**导出：** 自定义要导出的数据。</span><span class="sxs-lookup"><span data-stu-id="02c9e-108">**Export:** Customize what data is exported.</span></span> <span data-ttu-id="02c9e-109">这包括导出文件元数据、本机文件、文本文件和已保存到 PDF 文件的编辑文档。</span><span class="sxs-lookup"><span data-stu-id="02c9e-109">This includes exporting file metadata, native files, text files, and redacted documents that have been saved to a PDF file.</span></span> <span data-ttu-id="02c9e-110">将导出的数据上载到 Azure 存储位置后，可以将其下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="02c9e-110">After the exported data is uploaded to an Azure Storage location, you can download it to a local computer.</span></span> <span data-ttu-id="02c9e-111">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="02c9e-111">For more information, see:</span></span>

- [<span data-ttu-id="02c9e-112">从审阅集中导出文档</span><span class="sxs-lookup"><span data-stu-id="02c9e-112">Export documents from a review set</span></span>](export-documents-from-review-set.md)

- [<span data-ttu-id="02c9e-113">下载导出作业</span><span class="sxs-lookup"><span data-stu-id="02c9e-113">Download export jobs</span></span>](download-export-jobs.md)

<span data-ttu-id="02c9e-114">**添加到另一个审阅集：** 将数据从一个审阅集复制到不同的审阅集。</span><span class="sxs-lookup"><span data-stu-id="02c9e-114">**Add to another review set:** Copy data from one review set to a different review set.</span></span> <span data-ttu-id="02c9e-115">有关详细信息，请参阅[将数据从一个评审集添加到另一个评审集](add-data-to-review-set-from-another-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="02c9e-115">For more information, see [Add data from one review set to another review set](add-data-to-review-set-from-another-review-set.md).</span></span>

> [!NOTE]
> <span data-ttu-id="02c9e-116">在 Microsoft 365 中，将对数据进行哈希运算，并在输出文件中提供这些哈希以供验证之用。</span><span class="sxs-lookup"><span data-stu-id="02c9e-116">In Microsoft 365, data is hashed and those hashes are provided in the output file for verification purposes.</span></span> <span data-ttu-id="02c9e-117">这是由审核日志和报告功能（如集合统计信息、负载设置报告和导出报告（包括导出加载文件）补充而成。</span><span class="sxs-lookup"><span data-stu-id="02c9e-117">This is supplemented by audit logs and reporting functionality, such as collection statistics, load set reports, and export reports (including the export load file).</span></span>
