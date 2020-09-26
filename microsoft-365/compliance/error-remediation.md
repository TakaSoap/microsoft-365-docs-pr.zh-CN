---
title: 处理调查数据时的错误修正
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
description: 了解如何使用错误修正来更正数据调查中的数据问题 (预览) 可能阻止对内容进行正确处理。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: c6c62bb1a3191e369d553df5eb451d4656e704d7
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286028"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a><span data-ttu-id="a6037-103">处理调查数据时的错误修正</span><span class="sxs-lookup"><span data-stu-id="a6037-103">Error remediation when processing data for an investigation</span></span>

<span data-ttu-id="a6037-104">错误修正使调查人员能够修正数据问题，从而防止数据调查 (预览) 能够正确处理内容。</span><span class="sxs-lookup"><span data-stu-id="a6037-104">Error remediation allows investigators the ability to rectify data issues that prevent Data Investigations (preview) from properly processing the content.</span></span> <span data-ttu-id="a6037-105">例如，由于文件被锁定或加密，因此无法处理受密码保护的文件。</span><span class="sxs-lookup"><span data-stu-id="a6037-105">For example, files that are password protected cannot be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="a6037-106">使用错误修正，调查人员可以下载具有此类错误的文件，删除密码保护，并上传修正的文件。</span><span class="sxs-lookup"><span data-stu-id="a6037-106">Using error remediation, investigators can download files with such errors, remove the password protection, and upload the remediated files.</span></span>

<span data-ttu-id="a6037-107">使用以下工作流修正在数据调查中出现错误的文件 (预览) 案例。</span><span class="sxs-lookup"><span data-stu-id="a6037-107">Use the following workflow to remediate files with errors in Data Investigations (preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="a6037-108">创建错误修正会话以纠正带有处理错误的文件</span><span class="sxs-lookup"><span data-stu-id="a6037-108">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="a6037-109">如果在以下过程中随时关闭错误修正向导，则可以通过在 "**视图**" 下拉菜单中选择 "**错误" remediations**返回到 "**处理**" 选项卡中的 "错误修正" 会话。</span><span class="sxs-lookup"><span data-stu-id="a6037-109">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="a6037-110">在数据调查的 "**处理**" 选项卡上，选择 "**视图**" 下拉菜单中的 "**错误**"。</span><span class="sxs-lookup"><span data-stu-id="a6037-110">On the **Processing** tab in a data investigation, select **Errors** in the **View** dropdown menu.</span></span>

2. <span data-ttu-id="a6037-111">通过单击 "错误类型" 或 "文件类型" 旁边的单选按钮，选择要修正的错误。</span><span class="sxs-lookup"><span data-stu-id="a6037-111">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="a6037-112">在下面的示例中，我们正在修正受密码保护的文件。</span><span class="sxs-lookup"><span data-stu-id="a6037-112">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="a6037-113">单击 " **+ 新错误修正**"。</span><span class="sxs-lookup"><span data-stu-id="a6037-113">Click **+ New error remediation**.</span></span>

    ![单击 "新建错误修正" 按钮](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="a6037-115">错误修正会话开始，从准备阶段开始，其中将包含错误的文件复制到安全 Azure 位置，以便可以下载它们。</span><span class="sxs-lookup"><span data-stu-id="a6037-115">The error remediation session begins, starting with a preparation stage where the files with errors are copied to a secure Azure location so that they can be downloaded.</span></span>

    ![为错误修正做准备](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="a6037-117">准备完成后，单击 " **下一步：下载文件** " 以继续下载。</span><span class="sxs-lookup"><span data-stu-id="a6037-117">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![下载需要修正的文件](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="a6037-119">若要下载文件，请指定 **下载的目标路径**。</span><span class="sxs-lookup"><span data-stu-id="a6037-119">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="a6037-120">这是您的本地计算机上应下载文件的路径。</span><span class="sxs-lookup"><span data-stu-id="a6037-120">This is a path on your local computer where the file should be downloaded.</span></span>  <span data-ttu-id="a6037-121">默认路径 "%USERPROFILE%\Downloads\errors" 指向已登录用户的 "下载" 文件夹;可以根据需要对此进行更改。</span><span class="sxs-lookup"><span data-stu-id="a6037-121">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="a6037-122">建议使用本地文件路径，而不是远程网络路径，以实现最佳性能。</span><span class="sxs-lookup"><span data-stu-id="a6037-122">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a6037-123">如果尚未安装 AzCopy，请转到 [AzCopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) 以安装它。</span><span class="sxs-lookup"><span data-stu-id="a6037-123">If you haven't installed AzCopy, go to [Get started with AzCopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) to install it.</span></span>

6. <span data-ttu-id="a6037-124">通过单击 " **复制到剪贴板**" 复制预定义命令。</span><span class="sxs-lookup"><span data-stu-id="a6037-124">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="a6037-125">启动 windows 命令提示符，粘贴命令，然后按 **enter**。</span><span class="sxs-lookup"><span data-stu-id="a6037-125">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="a6037-126">将下载这些文件。</span><span class="sxs-lookup"><span data-stu-id="a6037-126">The files will be downloaded.</span></span>

    ![有关在命令提示符中下载的文件的信息](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="a6037-128">如果您在运行此命令时遇到问题，请参阅 [解决 AzCopy In 高级电子数据展示](troubleshooting-azcopy.md)问题。</span><span class="sxs-lookup"><span data-stu-id="a6037-128">If you have issues running this command, see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

7. <span data-ttu-id="a6037-129">下载文件后，可以使用适当的工具对它们进行修正。</span><span class="sxs-lookup"><span data-stu-id="a6037-129">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="a6037-130">对于受密码保护的文件，可以使用几种密码破解工具。</span><span class="sxs-lookup"><span data-stu-id="a6037-130">For password protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="a6037-131">如果您知道这些文件的密码，则可以打开它们并删除密码保护。</span><span class="sxs-lookup"><span data-stu-id="a6037-131">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    
   > [!NOTE]
    > <span data-ttu-id="a6037-132">必须保留已修正文件的目录结构和文件名，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="a6037-132">It's important that you retain the directory structure and file names of the remediated files.</span></span> <span data-ttu-id="a6037-133">通过下载的文件和文件夹的路径名称，可以将修正的文件与原始文件进行关联。</span><span class="sxs-lookup"><span data-stu-id="a6037-133">The path names of the downloaded files and folders make it possible to associate the remediated files with the original files.</span></span>  <span data-ttu-id="a6037-134">如果更改了目录结构或文件的名称，您将收到以下错误： `Cannot apply Error Remediation to the current Evidenceset` 。</span><span class="sxs-lookup"><span data-stu-id="a6037-134">If the directory structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Evidenceset`.</span></span>

8. <span data-ttu-id="a6037-135">现在，返回到 "数据调查" (预览) 并单击 " **下一步：上传文件**"。</span><span class="sxs-lookup"><span data-stu-id="a6037-135">Now, return to Data Investigations (preview) and click **Next: Upload files**.</span></span>  <span data-ttu-id="a6037-136">此操作将移至下一步，你现在可以在其中上传文件。</span><span class="sxs-lookup"><span data-stu-id="a6037-136">This will move to the next step where you can now upload the files.</span></span>

    !["上载文件" 选项卡](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="a6037-138">在 " **文件的位置路径** " 文本框中指定修正的文件的位置，然后单击 " **复制到剪贴板**"。</span><span class="sxs-lookup"><span data-stu-id="a6037-138">Specify the location of the remediated files in the **Path to location of files** text box, then click **Copy to clipboard**.</span></span>

10. <span data-ttu-id="a6037-139">将命令粘贴到 Windows 命令提示符中，然后按 **enter** 上传文件。</span><span class="sxs-lookup"><span data-stu-id="a6037-139">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![有关在命令提示符中上载的文件的信息](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="a6037-141">最后，返回到 "数据调查" (预览) 并单击 " **下一步：处理文件**"。</span><span class="sxs-lookup"><span data-stu-id="a6037-141">Finally, return to Data Investigations (preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="a6037-142">处理完成时。</span><span class="sxs-lookup"><span data-stu-id="a6037-142">When processing is complete.</span></span>  <span data-ttu-id="a6037-143">您可以返回到工作集并查看修正的文件。</span><span class="sxs-lookup"><span data-stu-id="a6037-143">You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="a6037-144">修正文件时会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="a6037-144">What happens when files are remediated</span></span>

<span data-ttu-id="a6037-145">当上载修正的文件时，原始元数据将保留，但以下字段除外：</span><span class="sxs-lookup"><span data-stu-id="a6037-145">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="a6037-146">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="a6037-146">ExtractedTextSize</span></span>
- <span data-ttu-id="a6037-147">HasText</span><span class="sxs-lookup"><span data-stu-id="a6037-147">HasText</span></span>
- <span data-ttu-id="a6037-148">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="a6037-148">IsErrorRemediate</span></span>
- <span data-ttu-id="a6037-149">LoadId</span><span class="sxs-lookup"><span data-stu-id="a6037-149">LoadId</span></span>
- <span data-ttu-id="a6037-150">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="a6037-150">ProcessingErrorMessage</span></span>
- <span data-ttu-id="a6037-151">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="a6037-151">ProcessingStatus</span></span>
- <span data-ttu-id="a6037-152">文本</span><span class="sxs-lookup"><span data-stu-id="a6037-152">Text</span></span>
- <span data-ttu-id="a6037-153">WordCount</span><span class="sxs-lookup"><span data-stu-id="a6037-153">WordCount</span></span>
- <span data-ttu-id="a6037-154">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="a6037-154">WorkingsetId</span></span>

<span data-ttu-id="a6037-155">有关数据调查中所有文档元数据字段的定义 (预览) ，请参阅 [document metadata fields](document-metadata-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="a6037-155">For a definition of all document metadata fields in Data Investigations (preview), see [Document metadata fields](document-metadata-fields.md).</span></span>
