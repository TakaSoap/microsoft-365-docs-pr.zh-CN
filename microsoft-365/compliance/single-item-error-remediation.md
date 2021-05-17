---
title: 单个项目错误修正
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
description: 您可以修复文档审阅集内文档的处理错误Advanced eDiscovery而无需执行批量错误修正过程。
ms.openlocfilehash: 8e5d8d00f507dc5792a1beda018d4c76632b82f7
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751579"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a><span data-ttu-id="0c8ec-103">单个项目错误修正Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="0c8ec-103">Single item error remediation in Advanced eDiscovery</span></span>

<span data-ttu-id="0c8ec-104">错误修正Advanced eDiscovery用户能够纠正阻止用户正确Advanced eDiscovery处理内容的数据问题。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="0c8ec-105">例如，由于这些文件被锁定或加密，因此无法处理受密码保护的文件。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="0c8ec-106">以前，只能使用此工作流批量 [修正错误](error-remediation-when-processing-data-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="0c8ec-107">但有时，如果你不确定其中任何文件是否对正在调查的案例作出响应，则修正多个文件的错误没有意义。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="0c8ec-108">在有机会查看文件元数据 (例如文件位置或有权访问) 以帮助你做出响应性决策之前，修正错误可能没有意义。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="0c8ec-109">名为 *单个项目错误* 修正的新功能使电子数据展示管理员能够查看包含处理错误的文件的元数据，并在必要时直接在审阅集内修正错误。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="0c8ec-110">本文讨论如何标识、忽略和修正审阅集内出现处理错误的文件。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="0c8ec-111">识别包含错误的文档</span><span class="sxs-lookup"><span data-stu-id="0c8ec-111">Identify documents with errors</span></span>

<span data-ttu-id="0c8ec-112">现在，审阅集内出现处理错误的文档 (横幅) 。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="0c8ec-113">可以修正或忽略错误。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="0c8ec-114">以下屏幕截图显示了受密码保护的审阅集内 Word 文档的处理错误横幅。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="0c8ec-115">另请注意，您可以查看包含处理错误的文档的文件元数据。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![为包含处理错误的文档显示的横幅](../media/SIERimage1.png)

<span data-ttu-id="0c8ec-117">在审阅集内查询文档时，您还可以使用"处理状态"条件搜索具有处理[错误的文档](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![使用"处理状态"条件搜索错误文档](../media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="0c8ec-119">忽略错误</span><span class="sxs-lookup"><span data-stu-id="0c8ec-119">Ignore errors</span></span>

<span data-ttu-id="0c8ec-120">可以通过单击处理错误横幅中的 **"忽略** "来忽略处理错误。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="0c8ec-121">忽略错误时，文档将从批量 [错误修正工作流中删除](error-remediation-when-processing-data-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="0c8ec-122">忽略错误后，文档横幅将更改颜色并指示已忽略处理错误。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="0c8ec-123">您随时都可以通过单击"还原"来恢复忽略错误 **的决定**。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![单击"忽略"忽略处理错误](../media/SIERimage3.png)

<span data-ttu-id="0c8ec-125">您还可以搜索所有具有处理错误的文档，这些文档在查询审阅集内的文档时，使用"忽略处理错误"条件被忽略。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![使用"忽略处理错误"条件搜索被忽略的错误文档](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="0c8ec-127">修正文档出错</span><span class="sxs-lookup"><span data-stu-id="0c8ec-127">Remediate a document with errors</span></span>

<span data-ttu-id="0c8ec-128">有时，您可能需要通过删除密码、解密加密文件或恢复损坏的文档) 然后将修正的文档添加到审阅集来修正文档 (中的处理错误。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="0c8ec-129">这样，您能够查看并导出错误文档以及审阅集内的其他文档。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="0c8ec-130">若要修正单个文档，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="0c8ec-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="0c8ec-131">单击  >  **"下载原始** 文件"，将文件副本下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![下载包含处理错误的文档](../media/SIERimage5.png)

2. <span data-ttu-id="0c8ec-133">脱机修复文件中的错误。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="0c8ec-134">对于需要解密软件才能删除密码保护的加密文件，请提供密码并保存文件或使用密码破解程序。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="0c8ec-135">修正文件后，转到下一步。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="0c8ec-136">在审阅集内，选择具有已修正处理错误的文件，然后单击"修正 **"。**</span><span class="sxs-lookup"><span data-stu-id="0c8ec-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![在包含处理错误的文档的横幅中单击"修正"](../media/SIERimage6.png)


4. <span data-ttu-id="0c8ec-138">单击 **"** 浏览"，转到本地计算机上已修复文件的位置，然后选择该文件。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![单击"浏览"，然后选择本地计算机上修正的文件](../media/SIERimage7.png)

    <span data-ttu-id="0c8ec-140">选择修正文件后，该文件将自动上载到审阅集。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="0c8ec-141">您可以跟踪文件的处理状态。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-141">You can track the processing status of the file.</span></span>

    ![显示修正过程的状态](../media/SIERimage8.png)

   <span data-ttu-id="0c8ec-143">处理完成后，可以查看已修复的文档。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-143">After processing is completed, you can view the remediated document.</span></span>

    ![可以在审阅集内以本机格式查看修正的文件](../media/SIERimage9.png)

<span data-ttu-id="0c8ec-145">有关修正文档时会发生什么情况的信息，请参阅修正 [文件时会发生什么情况](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated)。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="0c8ec-146">搜索修正的文档</span><span class="sxs-lookup"><span data-stu-id="0c8ec-146">Search for remediated documents</span></span>

<span data-ttu-id="0c8ec-147">您可以使用 **Keywords** 条件并指定以下 property：value 对来搜索审阅集内已修正的所有文档 **：IsFromErrorRemediation：true**。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="0c8ec-148">从审阅集导出文档时，导出加载文件中也提供此属性。</span><span class="sxs-lookup"><span data-stu-id="0c8ec-148">This property is also available in the export load file when you export documents from a review set.</span></span>
