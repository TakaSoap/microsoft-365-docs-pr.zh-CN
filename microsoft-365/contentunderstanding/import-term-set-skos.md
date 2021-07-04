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
ms.collection: enabler-strategic
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 8a1b61088d0a1594bf1a71542158ade389cce2ab
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288511"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="a4b2d-103">使用基于 SKOS 的格式导入术语集</span><span class="sxs-lookup"><span data-stu-id="a4b2d-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="a4b2d-104">可以使用基于 SKOS 的格式导入术语集。</span><span class="sxs-lookup"><span data-stu-id="a4b2d-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="a4b2d-105">有关格式的详细信息，请参阅 [SharePoint 分类 SKOS 格式参考](skos-format-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="a4b2d-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span> <span data-ttu-id="a4b2d-106">此功能需要 [SharePoint Syntex](index.md) 许可证。</span><span class="sxs-lookup"><span data-stu-id="a4b2d-106">This feature requires a [SharePoint Syntex](index.md) license.</span></span>

<span data-ttu-id="a4b2d-107">建议将导入文件保持在 20,000 个术语以下。</span><span class="sxs-lookup"><span data-stu-id="a4b2d-107">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="a4b2d-108">较大的文件可能会增加验证和导入所需的时间。</span><span class="sxs-lookup"><span data-stu-id="a4b2d-108">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="a4b2d-109">在 SharePoint 管理中心中，展开“**内容服务**”，然后单击“**术语库**”。</span><span class="sxs-lookup"><span data-stu-id="a4b2d-109">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="a4b2d-110">选择要导入术语集的术语组。</span><span class="sxs-lookup"><span data-stu-id="a4b2d-110">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="a4b2d-111">在命令栏中，单击“**导入术语集**”。</span><span class="sxs-lookup"><span data-stu-id="a4b2d-111">In the command bar, click **Import term set**.</span></span>

4. <span data-ttu-id="a4b2d-112">若要下载用作模板的示例文件，请单击 **sample-metadata.ttl** 以获取使用基于 SKOS 的格式的示例文件。</span><span class="sxs-lookup"><span data-stu-id="a4b2d-112">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>

5. <span data-ttu-id="a4b2d-113">创建包含了要导入的术语集和术语的导入文件。</span><span class="sxs-lookup"><span data-stu-id="a4b2d-113">Create the import file that contains the term sets & terms you wish to import.</span></span>

6. <span data-ttu-id="a4b2d-114">在“**文件格式**”下，选择 **SKOS (\*.ttl)**。</span><span class="sxs-lookup"><span data-stu-id="a4b2d-114">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7. <span data-ttu-id="a4b2d-115">单击“**浏览**”，然后导航到添加导入文件的地方。</span><span class="sxs-lookup"><span data-stu-id="a4b2d-115">Click **Browse** and navigate to and add your import file.</span></span>

8. <span data-ttu-id="a4b2d-116">单击 **“导入”**。</span><span class="sxs-lookup"><span data-stu-id="a4b2d-116">Click **Import**.</span></span> <span data-ttu-id="a4b2d-117">在导入完成前，请勿关闭面板。</span><span class="sxs-lookup"><span data-stu-id="a4b2d-117">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="a4b2d-118">成功导入文件时，将显示一条成功消息，并且将刷新术语库，以及可以导航到新创建的术语集。</span><span class="sxs-lookup"><span data-stu-id="a4b2d-118">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4b2d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4b2d-119">See also</span></span>

[<span data-ttu-id="a4b2d-120">托管元数据简介</span><span class="sxs-lookup"><span data-stu-id="a4b2d-120">Introduction to managed metadata</span></span>](/sharepoint/managed-metadata)

[<span data-ttu-id="a4b2d-121">文档理解概述</span><span class="sxs-lookup"><span data-stu-id="a4b2d-121">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="a4b2d-122">导入术语集（网站级别）</span><span class="sxs-lookup"><span data-stu-id="a4b2d-122">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)
