---
title: 单个项目错误更正
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
description: 您可以修复高级电子数据展示中的审阅集中的文档中的处理错误，而无需遵循批量错误修正过程。
ms.openlocfilehash: c049ce4b5d3f8fc12a015a61ea927b744ae76eb3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601489"
---
# <a name="single-item-error-remediation"></a><span data-ttu-id="fd706-103">单个项目错误更正</span><span class="sxs-lookup"><span data-stu-id="fd706-103">Single item error remediation</span></span>

<span data-ttu-id="fd706-104">错误修正使高级电子数据展示用户能够修正阻止高级电子数据展示正确处理内容的数据问题。</span><span class="sxs-lookup"><span data-stu-id="fd706-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="fd706-105">例如，受密码保护的文件无法处理，因为这些文件已锁定或加密。</span><span class="sxs-lookup"><span data-stu-id="fd706-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="fd706-106">以前，只能使用[此工作流](error-remediation-when-processing-data-in-advanced-ediscovery.md)对批量更正错误。</span><span class="sxs-lookup"><span data-stu-id="fd706-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="fd706-107">但有时，如果您不确定这些文件中的任何文件是否响应您正在调查的事例，则在多个文件中修正错误并不有意义。</span><span class="sxs-lookup"><span data-stu-id="fd706-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="fd706-108">在您有机会查看文件元数据（如文件位置或谁有权访问）之前，可能无法对错误进行修正，以帮助您提前做出有关响应的决策。</span><span class="sxs-lookup"><span data-stu-id="fd706-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="fd706-109">称为 "*单个项目错误修正*" 的新功能使电子数据展示管理器能够查看带有处理错误的文件的元数据，并在必要时直接在审阅集中更正错误。</span><span class="sxs-lookup"><span data-stu-id="fd706-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="fd706-110">本文讨论如何使用审阅集中的处理错误来标识、忽略和修正文件。</span><span class="sxs-lookup"><span data-stu-id="fd706-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="fd706-111">识别出错的文档</span><span class="sxs-lookup"><span data-stu-id="fd706-111">Identify documents with errors</span></span>

<span data-ttu-id="fd706-112">在审阅集中有处理错误的文档现在标识为（带有横幅）。</span><span class="sxs-lookup"><span data-stu-id="fd706-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="fd706-113">您可以修正或忽略该错误。</span><span class="sxs-lookup"><span data-stu-id="fd706-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="fd706-114">下面的屏幕截图显示了 Word 文档在受密码保护的审阅集中的处理错误横幅。</span><span class="sxs-lookup"><span data-stu-id="fd706-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="fd706-115">此外，还请注意，您可以查看包含处理错误的文档的文件元数据。</span><span class="sxs-lookup"><span data-stu-id="fd706-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![显示有处理错误的文档的横幅](media/SIERimage1.png)

<span data-ttu-id="fd706-117">您还可以通过在[审阅集中查询文档](review-set-search.md)时使用**处理状态**条件来搜索具有处理错误的文档。</span><span class="sxs-lookup"><span data-stu-id="fd706-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![使用处理状态条件搜索错误文档](media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="fd706-119">忽略错误</span><span class="sxs-lookup"><span data-stu-id="fd706-119">Ignore errors</span></span>

<span data-ttu-id="fd706-120">您可以通过单击处理错误标题中的 "**忽略**" 忽略处理错误。</span><span class="sxs-lookup"><span data-stu-id="fd706-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="fd706-121">当您忽略错误时，文档将从[批量错误修正工作流](error-remediation-when-processing-data-in-advanced-ediscovery.md)中删除。</span><span class="sxs-lookup"><span data-stu-id="fd706-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="fd706-122">错误被忽略后，文档标题将更改颜色并指示处理错误已被忽略。</span><span class="sxs-lookup"><span data-stu-id="fd706-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="fd706-123">您可以随时单击 "**还原**"，恢复决定忽略错误。</span><span class="sxs-lookup"><span data-stu-id="fd706-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![单击 "忽略" 忽略处理错误](media/SIERimage3.png)

<span data-ttu-id="fd706-125">您还可以搜索在审阅集中查询文档时使用 "*忽略的处理错误*" 条件忽略的处理错误的所有文档。</span><span class="sxs-lookup"><span data-stu-id="fd706-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![使用 "忽略的处理错误" 条件搜索忽略的错误文档](media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="fd706-127">修正有错误的文档</span><span class="sxs-lookup"><span data-stu-id="fd706-127">Remediate a document with errors</span></span>

<span data-ttu-id="fd706-128">有时，您可能需要修正文档中的处理错误（通过删除密码、解密加密文件或恢复损坏的文档），然后将修正的文档添加到评审集。</span><span class="sxs-lookup"><span data-stu-id="fd706-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="fd706-129">这使您可以查看错误文档并将其与审阅集中的其他文档一起导出。</span><span class="sxs-lookup"><span data-stu-id="fd706-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="fd706-130">若要修正单个文档，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="fd706-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="fd706-131">单击 "**下载** > **原始**版本" 将该文件的副本下载到本地计算机。</span><span class="sxs-lookup"><span data-stu-id="fd706-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![下载包含处理错误的文档](media/SIERimage5.png)

2. <span data-ttu-id="fd706-133">脱机更正文件中的错误。</span><span class="sxs-lookup"><span data-stu-id="fd706-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="fd706-134">对于需要解密软件的加密文件，若要删除密码保护，请提供密码并保存该文件，或使用密码破解程序。</span><span class="sxs-lookup"><span data-stu-id="fd706-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="fd706-135">修正文件后，请转到下一步。</span><span class="sxs-lookup"><span data-stu-id="fd706-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="fd706-136">在审阅集中，选择包含修正的处理错误的文件，然后单击 "**修正**"。</span><span class="sxs-lookup"><span data-stu-id="fd706-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![在包含处理错误的文档的标题中单击 "修正"](media/SIERimage6.png)


4. <span data-ttu-id="fd706-138">单击 "**浏览**"，转到您的本地计算机上已修正文件的位置，然后选择该文件。</span><span class="sxs-lookup"><span data-stu-id="fd706-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![单击 "浏览" 并选择本地计算机上的修正文件](media/SIERimage7.png)

    <span data-ttu-id="fd706-140">选择修正的文件后，会自动将其上载到审阅集。</span><span class="sxs-lookup"><span data-stu-id="fd706-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="fd706-141">您可以跟踪文件的处理状态。</span><span class="sxs-lookup"><span data-stu-id="fd706-141">You can track the processing status of the file.</span></span>

    ![将显示修正过程的状态](media/SIERimage8.png)

   <span data-ttu-id="fd706-143">处理完成后，您可以查看修正的文档。</span><span class="sxs-lookup"><span data-stu-id="fd706-143">After processing is completed, you can view the remediated document.</span></span>

    ![您可以在审阅集中以本机格式查看修正的文件](media/SIERimage9.png)

<span data-ttu-id="fd706-145">有关修正文档时所发生情况的详细信息，请参阅[当修正文件时会发生什么情况](error-remediation.md#what-happens-when-files-are-remediated)。</span><span class="sxs-lookup"><span data-stu-id="fd706-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="fd706-146">搜索已修正的文档</span><span class="sxs-lookup"><span data-stu-id="fd706-146">Search for remediated documents</span></span>

<span data-ttu-id="fd706-147">您可以使用**关键字**条件搜索已修正的审阅集中的所有文档，并指定以下属性：值对： **IsFromErrorRemediation： true**。</span><span class="sxs-lookup"><span data-stu-id="fd706-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="fd706-148">当您从审阅集中导出文档时，也可以在导出加载文件中使用此属性。</span><span class="sxs-lookup"><span data-stu-id="fd706-148">This property is also available in the export load file when you export documents from a review set.</span></span>
