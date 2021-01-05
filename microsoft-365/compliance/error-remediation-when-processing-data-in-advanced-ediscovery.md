---
title: 修正处理数据时出现的错误
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
description: 了解如何使用错误修正来更正高级电子数据展示中可能阻止正确处理内容的数据问题。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c6ef1076e44fca0d060d766fc85a435550c40059
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750795"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="19cdf-103">修正处理数据时出现的错误</span><span class="sxs-lookup"><span data-stu-id="19cdf-103">Error remediation when processing data</span></span>

<span data-ttu-id="19cdf-104">错误修正使电子数据展示管理员可以纠正阻止高级电子数据展示正确处理内容的数据问题。</span><span class="sxs-lookup"><span data-stu-id="19cdf-104">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="19cdf-105">例如，由于文件被锁定或加密，因此无法处理受密码保护的文件。</span><span class="sxs-lookup"><span data-stu-id="19cdf-105">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="19cdf-106">通过使用错误修正，电子数据展示管理员可以下载包含此类错误的文件，删除密码保护，然后上载修正后的文件。</span><span class="sxs-lookup"><span data-stu-id="19cdf-106">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="19cdf-107">使用以下工作流修正高级电子数据展示事例中出现错误的文件。</span><span class="sxs-lookup"><span data-stu-id="19cdf-107">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="19cdf-108">创建错误修正会话以修正包含处理错误的文件</span><span class="sxs-lookup"><span data-stu-id="19cdf-108">Create an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="19cdf-109">如果错误修正向导在下面的过程中随时关闭，则可以通过在"视图"下拉菜单中选择"修正"，从"处理"选项卡返回到错误修正会话。 </span><span class="sxs-lookup"><span data-stu-id="19cdf-109">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Remediations** in the **View** drop-down menu.</span></span>

1. <span data-ttu-id="19cdf-110">在高级 **电子** 数据展示案例的"处理"选项卡上，在"查看"下拉菜单中选择"错误"，然后在"范围"下拉菜单中选择审阅集或整个案例。 </span><span class="sxs-lookup"><span data-stu-id="19cdf-110">On the **Processing** tab in the Advanced eDiscovery case, select **Errors** in the **View** drop-down menu and then select a review set or the entire case in the **Scope** drop-down menu.</span></span> <span data-ttu-id="19cdf-111">此部分显示来自案例的所有错误或特定审阅集的错误。</span><span class="sxs-lookup"><span data-stu-id="19cdf-111">This section displays all errors from the case or error from a specific review set.</span></span>

   ![错误修正](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. <span data-ttu-id="19cdf-113">单击错误类型或文件类型旁边的单选按钮，选择要修正的错误。</span><span class="sxs-lookup"><span data-stu-id="19cdf-113">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="19cdf-114">在下面的示例中，我们将修正受密码保护的文件。</span><span class="sxs-lookup"><span data-stu-id="19cdf-114">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="19cdf-115">单击 **"新建错误修正"。**</span><span class="sxs-lookup"><span data-stu-id="19cdf-115">Click **New error remediation**.</span></span>

    <span data-ttu-id="19cdf-116">错误修正工作流从准备阶段开始，其中将包含错误的文件复制到 Microsoft 提供的 Azure 存储位置，以便你可以将其下载到本地计算机进行修正。</span><span class="sxs-lookup"><span data-stu-id="19cdf-116">The error remediation workflow starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![准备错误修正](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="19cdf-118">准备工作完成后，单击"下一步 **： 下载文件** "以继续下载。</span><span class="sxs-lookup"><span data-stu-id="19cdf-118">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![下载文件](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="19cdf-120">若要下载文件，请指定 **下载的目标路径**。</span><span class="sxs-lookup"><span data-stu-id="19cdf-120">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="19cdf-121">这是本地计算机上将下载该文件的父文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="19cdf-121">This is a path to the parent folder on your local computer where the file will be downloaded.</span></span>  <span data-ttu-id="19cdf-122">默认路径 %USERPROFILE%\Downloads\errors 指向登录用户的下载文件夹。</span><span class="sxs-lookup"><span data-stu-id="19cdf-122">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="19cdf-123">如果需要，可以更改此路径。</span><span class="sxs-lookup"><span data-stu-id="19cdf-123">You can change this path if desired.</span></span> <span data-ttu-id="19cdf-124">如果更改了该路径，建议您使用本地文件路径以获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="19cdf-124">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="19cdf-125">请勿使用远程网络路径。</span><span class="sxs-lookup"><span data-stu-id="19cdf-125">Don't use a remote network path.</span></span> <span data-ttu-id="19cdf-126">例如，可以使用路径 **C：\Remediation。**</span><span class="sxs-lookup"><span data-stu-id="19cdf-126">For example, you could use the path **C:\Remediation**.</span></span> 

   <span data-ttu-id="19cdf-127">父文件夹的路径会自动添加到 AzCopy 命令 (**作为 /Dest** 参数的值) 。</span><span class="sxs-lookup"><span data-stu-id="19cdf-127">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Dest** parameter).</span></span>

6. <span data-ttu-id="19cdf-128">通过单击"复制到剪贴板 **"复制预定义的命令**。</span><span class="sxs-lookup"><span data-stu-id="19cdf-128">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="19cdf-129">打开 Windows 命令提示符，粘贴 AzCopy 命令，然后按 **Enter。**</span><span class="sxs-lookup"><span data-stu-id="19cdf-129">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span>  

    ![准备错误修正](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > <span data-ttu-id="19cdf-131">您必须使用 AzCopy v8.1 成功使用"下载文件"页上 **提供** 的命令。</span><span class="sxs-lookup"><span data-stu-id="19cdf-131">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="19cdf-132">还必须使用 AzCopy v8.1 上载步骤 10 中的文件。</span><span class="sxs-lookup"><span data-stu-id="19cdf-132">You also must use AzCopy v8.1 to upload the files in step 10.</span></span> <span data-ttu-id="19cdf-133">若要安装此版本的 AzCopy，请参阅 Windows 上的 [AzCopy v8.1 传输数据](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="19cdf-133">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="19cdf-134">如果提供的 AzCopy 命令失败，请参阅高级电子数据 [展示中的 AzCopy 疑难解答](troubleshooting-azcopy.md)。</span><span class="sxs-lookup"><span data-stu-id="19cdf-134">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

    <span data-ttu-id="19cdf-135">所选的文件将下载到步骤 5 中指定的位置。</span><span class="sxs-lookup"><span data-stu-id="19cdf-135">The files that you selected are downloaded to the location that you specified in step 5.</span></span> <span data-ttu-id="19cdf-136">在父文件夹 (例如 **C：\Remediation**) ，将自动创建以下子文件夹结构：</span><span class="sxs-lookup"><span data-stu-id="19cdf-136">In the parent folder (for example, **C:\Remediation**), the following subfolder structure is automatically created:</span></span>

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - <span data-ttu-id="19cdf-137">*子文件夹 1* 使用案例或审阅集的 ID 进行命名，具体取决于在步骤 1 中所选的范围。</span><span class="sxs-lookup"><span data-stu-id="19cdf-137">*Subfolder 1* is named with the ID for the case or the review set, depending on the scope that you selected in step 1.</span></span>

    - <span data-ttu-id="19cdf-138">*使用下载* 的文件的文件 ID 命名子文件夹 2</span><span class="sxs-lookup"><span data-stu-id="19cdf-138">*Subfolder 2* is named with the file ID of the downloaded file</span></span>

    - <span data-ttu-id="19cdf-139">下载的文件位于子文件夹 *2* 中，并且也使用文件 ID 命名。</span><span class="sxs-lookup"><span data-stu-id="19cdf-139">The downloaded file is located in *Subfolder 2* and is also named with the file ID.</span></span>

    <span data-ttu-id="19cdf-140">下面是将项目下载到 **C：\Remediation** 父文件夹时创建的文件夹路径和错误文件名的示例：</span><span class="sxs-lookup"><span data-stu-id="19cdf-140">Here's an example of the folder path and error file name that's created when items are downloaded to the **C:\Remediation** parent folder:</span></span>

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    <span data-ttu-id="19cdf-141">如果下载多个文件，每个文件将下载到使用文件 ID 命名的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="19cdf-141">If multiple files are downloaded, each one is downloaded to a subfolder that's named with the file ID.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="19cdf-142">在步骤 9 和步骤 10 中上载文件时，修正的文件必须具有相同的文件名，并且位于同一子文件夹结构中。</span><span class="sxs-lookup"><span data-stu-id="19cdf-142">When you upload files in step 9 and step 10, the remediated files must have that same filename and be located in the same subfolder structure.</span></span> <span data-ttu-id="19cdf-143">子文件夹和文件名用于将修正的文件与原始错误文件关联。</span><span class="sxs-lookup"><span data-stu-id="19cdf-143">The subfolder and file names are used to associated the remediated file with the original error file.</span></span> <span data-ttu-id="19cdf-144">如果更改文件夹结构或文件名，您将收到以下 `Cannot apply Error Remediation to the current Workingset` 错误：</span><span class="sxs-lookup"><span data-stu-id="19cdf-144">If the folder structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span> <span data-ttu-id="19cdf-145">为了防止出现任何问题，我们建议将修正的文件保留在同一父文件夹和子文件夹结构中。</span><span class="sxs-lookup"><span data-stu-id="19cdf-145">To prevent any issues, we recommend that keep the remediated files in the same parent folder and subfolder structure.</span></span>

7. <span data-ttu-id="19cdf-146">下载文件后，可以使用适当的工具修正它们。</span><span class="sxs-lookup"><span data-stu-id="19cdf-146">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="19cdf-147">对于受密码保护的文件，可以使用多个密码破解工具。</span><span class="sxs-lookup"><span data-stu-id="19cdf-147">For password-protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="19cdf-148">如果您知道文件的密码，可以打开它们并删除密码保护。</span><span class="sxs-lookup"><span data-stu-id="19cdf-148">If you know the passwords for the files, you can open them and remove the password protection.</span></span>

8. <span data-ttu-id="19cdf-149">返回到高级电子数据展示和错误修正向导，然后单击"下一步 **： 上载文件"。**</span><span class="sxs-lookup"><span data-stu-id="19cdf-149">Return to Advanced eDiscovery and the error remediation wizard and then click **Next: Upload files**.</span></span>  <span data-ttu-id="19cdf-150">这会移到下一个页面，现在您可以在其中上载文件。</span><span class="sxs-lookup"><span data-stu-id="19cdf-150">This moves to the next page where you can now upload the files.</span></span>

    ![上载文件](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="19cdf-152">在"文件路径位置"文本框中指定已修正文件所在的 **父** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="19cdf-152">Specify the parent folder where the remediated files are located in the **Path to location of files** text box.</span></span> <span data-ttu-id="19cdf-153">同样，父文件夹必须与下载文件时创建的子文件夹结构相同。</span><span class="sxs-lookup"><span data-stu-id="19cdf-153">Again, the parent folder must have the same subfolder structure that was created when you downloaded the files.</span></span>

    <span data-ttu-id="19cdf-154">父文件夹的路径会自动添加到 AzCopy 命令 (**作为 /Source** 参数的值) 。</span><span class="sxs-lookup"><span data-stu-id="19cdf-154">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Source** parameter).</span></span>

10. <span data-ttu-id="19cdf-155">通过单击"复制到剪贴板 **"复制预定义的命令**。</span><span class="sxs-lookup"><span data-stu-id="19cdf-155">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="19cdf-156">打开 Windows 命令提示符，粘贴 AzCopy 命令，然后按 **Enter。**</span><span class="sxs-lookup"><span data-stu-id="19cdf-156">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span> <span data-ttu-id="19cdf-157">上载文件。</span><span class="sxs-lookup"><span data-stu-id="19cdf-157">upload the files.</span></span>

    ![在 Azcopy 中成功上载修正文件的结果](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="19cdf-159">运行 AzCopy 命令后，单击"**下一步： 处理文件"。**</span><span class="sxs-lookup"><span data-stu-id="19cdf-159">After you run the AzCopy command, click **Next: Process files**.</span></span>

    <span data-ttu-id="19cdf-160">处理完成后，可以转到审阅集并查看修正后的文件。</span><span class="sxs-lookup"><span data-stu-id="19cdf-160">When processing is complete, you can go to review set and view the remediated files.</span></span> 

## <a name="remediating-errors-in-container-files"></a><span data-ttu-id="19cdf-161">修正容器文件中的错误</span><span class="sxs-lookup"><span data-stu-id="19cdf-161">Remediating errors in container files</span></span>

<span data-ttu-id="19cdf-162">如果高级电子数据展示无法提取容器文件 (（如 .zip 文件) ）的内容，可以下载容器，将内容展开到原始容器所在的同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="19cdf-162">In situations when the contents of a container file (such as a .zip file) can't be extracted by Advanced eDiscovery, the containers can be downloaded and the contents expanded into the same folder in which the original container resides.</span></span> <span data-ttu-id="19cdf-163">展开的文件将被属性化为父容器，就像它最初由高级电子数据展示扩展一样。</span><span class="sxs-lookup"><span data-stu-id="19cdf-163">The expanded files will be attributed to the parent container as if it was originally expanded by Advanced eDiscovery.</span></span> <span data-ttu-id="19cdf-164">此过程的工作方式如上所述，只是将单个文件上载为替换文件。</span><span class="sxs-lookup"><span data-stu-id="19cdf-164">The process works as described as above except for uploading a single file as the replacement file.</span></span>  <span data-ttu-id="19cdf-165">上传修正后的文件时，请勿包含原始容器文件。</span><span class="sxs-lookup"><span data-stu-id="19cdf-165">When you upload remediated files, don't include the original container file.</span></span>

## <a name="remediating-errors-by-uploading-the-extracted-text"></a><span data-ttu-id="19cdf-166">通过上载提取的文本修正错误</span><span class="sxs-lookup"><span data-stu-id="19cdf-166">Remediating errors by uploading the extracted text</span></span>

<span data-ttu-id="19cdf-167">有时无法将文件修正为高级电子数据展示可以解释的本机格式。</span><span class="sxs-lookup"><span data-stu-id="19cdf-167">Sometimes it's not possible to remediate a file to native format that Advanced eDiscovery can interpret.</span></span> <span data-ttu-id="19cdf-168">但是，可以将原始文件替换为文本文件，其中包含本机文件的原始文本， (称为文本覆盖) 。 </span><span class="sxs-lookup"><span data-stu-id="19cdf-168">But you can replace the original file with a text file that contains the original text of the native file (in a process called *text overlay*).</span></span> <span data-ttu-id="19cdf-169">为此，请按照本文中所述的步骤操作，而不是以本机格式修正原始文件，而是创建一个文本文件，其中包含从原始文件中提取的文本，然后使用附加了 .txt 后缀的原始文件名上载文本文件。</span><span class="sxs-lookup"><span data-stu-id="19cdf-169">To do this, follow the steps described in this article but instead of remediating the original file in the native format, you would create a text file that contains the extracted text from the original file, and then upload the text file using the original filename appended with a .txt suffix.</span></span> <span data-ttu-id="19cdf-170">例如，在文件名为 335850cc-6602-4af0-acfa-1d14d9128ca2.abc 的错误修正过程中下载文件。</span><span class="sxs-lookup"><span data-stu-id="19cdf-170">For example, you download a file during error remediation with the filename 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.</span></span> <span data-ttu-id="19cdf-171">在本机应用程序中打开该文件，复制文本，然后将其粘贴到名为 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt。</span><span class="sxs-lookup"><span data-stu-id="19cdf-171">You open the file in the native application, copy the text, and then paste it into a new file named 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt.</span></span> <span data-ttu-id="19cdf-172">这样做时，请确保先从本地计算机上已修正的文件位置删除原始文件，然后再将修正的文本文件上载到高级电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="19cdf-172">When you do this, be sure to remove the original file in the native format from the remediated file location on your local computer before uploading the remediated text file to Advanced eDiscovery.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="19cdf-173">修复文件时会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="19cdf-173">What happens when files are remediated</span></span>

<span data-ttu-id="19cdf-174">上载修正后的文件时，将保留原始元数据，以下字段除外：</span><span class="sxs-lookup"><span data-stu-id="19cdf-174">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="19cdf-175">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="19cdf-175">ExtractedTextSize</span></span>
- <span data-ttu-id="19cdf-176">HasText</span><span class="sxs-lookup"><span data-stu-id="19cdf-176">HasText</span></span>
- <span data-ttu-id="19cdf-177">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="19cdf-177">IsErrorRemediate</span></span>
- <span data-ttu-id="19cdf-178">LoadId</span><span class="sxs-lookup"><span data-stu-id="19cdf-178">LoadId</span></span>
- <span data-ttu-id="19cdf-179">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="19cdf-179">ProcessingErrorMessage</span></span>
- <span data-ttu-id="19cdf-180">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="19cdf-180">ProcessingStatus</span></span>
- <span data-ttu-id="19cdf-181">文本</span><span class="sxs-lookup"><span data-stu-id="19cdf-181">Text</span></span>
- <span data-ttu-id="19cdf-182">WordCount</span><span class="sxs-lookup"><span data-stu-id="19cdf-182">WordCount</span></span>
- <span data-ttu-id="19cdf-183">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="19cdf-183">WorkingsetId</span></span>

<span data-ttu-id="19cdf-184">有关高级电子数据展示中所有元数据字段的定义，请参阅 [文档元数据字段](document-metadata-fields-in-advanced-ediscovery.md)。</span><span class="sxs-lookup"><span data-stu-id="19cdf-184">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields-in-advanced-ediscovery.md).</span></span>
