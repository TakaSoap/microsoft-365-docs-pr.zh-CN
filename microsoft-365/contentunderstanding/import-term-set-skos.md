---
title: 使用基于 SKOS 的格式导入术语集
description: 了解如何使用基于 SKOS 的格式导入术语集
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: aaed88463f690853672780b48a8ee3857a956847
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295795"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="fd645-103">使用基于 SKOS 的格式导入术语集</span><span class="sxs-lookup"><span data-stu-id="fd645-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="fd645-104">您可以使用基于 SKOS 的格式导入术语集。</span><span class="sxs-lookup"><span data-stu-id="fd645-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="fd645-105">有关格式的详细信息，请参阅 [SharePoint 分类 SKOS 格式参考](skos-format-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="fd645-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span>

<span data-ttu-id="fd645-106">建议将您的导入文件保留为少于20000个术语。</span><span class="sxs-lookup"><span data-stu-id="fd645-106">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="fd645-107">较大的文件可能会增加验证和导入所需的时间。</span><span class="sxs-lookup"><span data-stu-id="fd645-107">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="fd645-108">在 SharePoint 管理中心中，展开 " **内容服务**"，然后单击 " **术语库**"。</span><span class="sxs-lookup"><span data-stu-id="fd645-108">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="fd645-109">选择要在其中导入术语集的术语组。</span><span class="sxs-lookup"><span data-stu-id="fd645-109">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="fd645-110">在命令栏中，单击 " **导入术语集**"。</span><span class="sxs-lookup"><span data-stu-id="fd645-110">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="fd645-111">如果要下载用作模板的示例文件，请单击 **sample-metadata** 以获取使用基于 SKOS 的格式的示例文件。</span><span class="sxs-lookup"><span data-stu-id="fd645-111">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="fd645-112">创建包含要导入 & 术语的术语集的导入文件。</span><span class="sxs-lookup"><span data-stu-id="fd645-112">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="fd645-113">在 " **文件格式**" 下，选择 " \*\*SKOS ( \* ttl) \*\*。</span><span class="sxs-lookup"><span data-stu-id="fd645-113">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="fd645-114">单击 " **浏览** " 并导航到您的导入文件并将其添加。</span><span class="sxs-lookup"><span data-stu-id="fd645-114">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="fd645-115">单击“导入”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fd645-115">Click **Import**.</span></span> <span data-ttu-id="fd645-116">在导入完成之前，请勿关闭面板。</span><span class="sxs-lookup"><span data-stu-id="fd645-116">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="fd645-117">成功导入文件后，将显示一条成功消息，并且术语库将刷新，并且您可以导航到新创建的术语集。</span><span class="sxs-lookup"><span data-stu-id="fd645-117">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd645-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd645-118">See also</span></span>

[<span data-ttu-id="fd645-119">托管元数据简介</span><span class="sxs-lookup"><span data-stu-id="fd645-119">Introduction to managed metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata)

[<span data-ttu-id="fd645-120">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="fd645-120">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="fd645-121"> (网站级别) 导入术语集 </span><span class="sxs-lookup"><span data-stu-id="fd645-121">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)