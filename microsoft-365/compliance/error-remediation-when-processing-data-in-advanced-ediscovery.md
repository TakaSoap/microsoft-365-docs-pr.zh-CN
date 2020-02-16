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
description: ''
ms.openlocfilehash: 5421ba811e401bdd191aee0ddbff21a1286dc9fe
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074569"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="b4565-102">修正处理数据时出现的错误</span><span class="sxs-lookup"><span data-stu-id="b4565-102">Error remediation when processing data</span></span>

<span data-ttu-id="b4565-103">错误修正使电子数据展示管理员能够修正阻止高级电子数据展示的数据问题，从而无法正确处理内容。</span><span class="sxs-lookup"><span data-stu-id="b4565-103">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="b4565-104">例如，由于文件被锁定或加密，因此无法处理受密码保护的文件。</span><span class="sxs-lookup"><span data-stu-id="b4565-104">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="b4565-105">使用错误修正，电子数据展示管理员可以下载具有此类错误的文件，删除密码保护，然后上传修正的文件。</span><span class="sxs-lookup"><span data-stu-id="b4565-105">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="b4565-106">使用以下工作流修正高级电子数据展示事例中有错误的文件。</span><span class="sxs-lookup"><span data-stu-id="b4565-106">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="b4565-107">创建错误修正会话以修正带有处理错误的文件</span><span class="sxs-lookup"><span data-stu-id="b4565-107">Create an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="b4565-108">如果在以下过程中随时关闭错误修正向导，则可以通过在 "**视图**" 下拉菜单中选择 " **Remediations** " 从 "**处理**" 选项卡返回到错误修正会话。</span><span class="sxs-lookup"><span data-stu-id="b4565-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Remediations** in the **View** drop-down menu.</span></span>

1. <span data-ttu-id="b4565-109">在高级电子数据展示事例的 "**处理**" 选项卡上，选择 "**视图**" 下拉菜单中的 "**错误**"，然后选择 "**范围**" 下拉菜单中的 "检查集" 或 "整个事例"。</span><span class="sxs-lookup"><span data-stu-id="b4565-109">On the **Processing** tab in the Advanced eDiscovery case, select **Errors** in the **View** drop-down menu and then select a review set or the entire case in the **Scope** drop-down menu.</span></span> <span data-ttu-id="b4565-110">此部分显示来自特定审阅集的事例或错误中的所有错误。</span><span class="sxs-lookup"><span data-stu-id="b4565-110">This section displays all errors from the case or error from a specific review set.</span></span>

   ![错误修正](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. <span data-ttu-id="b4565-112">通过单击 "错误类型" 或 "文件类型" 旁边的单选按钮，选择要修正的错误。</span><span class="sxs-lookup"><span data-stu-id="b4565-112">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="b4565-113">在下面的示例中，我们正在修正受密码保护的文件。</span><span class="sxs-lookup"><span data-stu-id="b4565-113">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="b4565-114">单击 "**新建错误修正**"。</span><span class="sxs-lookup"><span data-stu-id="b4565-114">Click **New error remediation**.</span></span>

    <span data-ttu-id="b4565-115">错误修正工作流从准备阶段开始，其中有错误的文件复制到 Microsoft 提供的 Azure 存储位置，以便您可以将其下载到本地计算机以进行修正。</span><span class="sxs-lookup"><span data-stu-id="b4565-115">The error remediation workflow starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![准备错误修正](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="b4565-117">准备完成后，单击 "**下一步：下载文件**" 以继续下载。</span><span class="sxs-lookup"><span data-stu-id="b4565-117">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![下载文件](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="b4565-119">若要下载文件，请指定**下载的目标路径**。</span><span class="sxs-lookup"><span data-stu-id="b4565-119">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="b4565-120">这是您的本地计算机上的父文件夹的路径，将在该文件夹中下载文件。</span><span class="sxs-lookup"><span data-stu-id="b4565-120">This is a path to the parent folder on your local computer where the file will be downloaded.</span></span>  <span data-ttu-id="b4565-121">默认路径 "%USERPROFILE%\Downloads\errors" 指向已登录用户的 "下载" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="b4565-121">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="b4565-122">如果需要，可以更改此路径。</span><span class="sxs-lookup"><span data-stu-id="b4565-122">You can change this path if desired.</span></span> <span data-ttu-id="b4565-123">如果您确实要更改它，建议使用本地文件路径以获得最佳性能。</span><span class="sxs-lookup"><span data-stu-id="b4565-123">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="b4565-124">请勿使用远程网络路径。</span><span class="sxs-lookup"><span data-stu-id="b4565-124">Don't use a remote network path.</span></span> <span data-ttu-id="b4565-125">例如，可以使用路径**C:\Remediation**。</span><span class="sxs-lookup"><span data-stu-id="b4565-125">For example, you could use the path **C:\Remediation**.</span></span> 

   <span data-ttu-id="b4565-126">父文件夹的路径将自动添加到 AzCopy 命令（作为 **/Dest**参数的值）。</span><span class="sxs-lookup"><span data-stu-id="b4565-126">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Dest** parameter).</span></span>

6. <span data-ttu-id="b4565-127">通过单击 "**复制到剪贴板**" 复制预定义命令。</span><span class="sxs-lookup"><span data-stu-id="b4565-127">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="b4565-128">打开 Windows 命令提示符，粘贴 "AzCopy" 命令，然后按**enter**。</span><span class="sxs-lookup"><span data-stu-id="b4565-128">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span>  

    ![准备进行错误修正](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > <span data-ttu-id="b4565-130">必须使用 AzCopy app-v 8.1 才能成功使用 "**下载文件**" 页上提供的命令。</span><span class="sxs-lookup"><span data-stu-id="b4565-130">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="b4565-131">此外，还必须使用 AzCopy 中的第10步上载文件。</span><span class="sxs-lookup"><span data-stu-id="b4565-131">You also must use AzCopy v8.1 to upload the files in step 10.</span></span> <span data-ttu-id="b4565-132">若要安装此版本的 AzCopy，请参阅[在 Windows 上使用 AzCopy ue-v 8.1 传输数据](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="b4565-132">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="b4565-133">如果提供的 AzCopy 命令失败，请参阅[高级电子数据展示中的疑难解答 AzCopy](troubleshooting-azcopy.md)。</span><span class="sxs-lookup"><span data-stu-id="b4565-133">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

    <span data-ttu-id="b4565-134">您选择的文件将下载到您在步骤5中指定的位置。</span><span class="sxs-lookup"><span data-stu-id="b4565-134">The files that you selected are downloaded to the location that you specified in step 5.</span></span> <span data-ttu-id="b4565-135">在父文件夹（例如， **C:\Remediation**）中，将自动创建以下子文件夹结构：</span><span class="sxs-lookup"><span data-stu-id="b4565-135">In the parent folder (for example, **C:\Remediation**), the following subfolder structure is automatically created:</span></span>

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - <span data-ttu-id="b4565-136">*子文件夹 1*以事例或审阅集的 ID 命名，具体取决于您在步骤1中选择的范围。</span><span class="sxs-lookup"><span data-stu-id="b4565-136">*Subfolder 1* is named with the ID for the case or the review set, depending on the scope that you selected in step 1.</span></span>

    - <span data-ttu-id="b4565-137">*子文件夹 2*以下载文件的文件 ID 命名</span><span class="sxs-lookup"><span data-stu-id="b4565-137">*Subfolder 2* is named with the file ID of the downloaded file</span></span>

    - <span data-ttu-id="b4565-138">下载的文件位于*子文件夹 2*中，也用文件 ID 命名。</span><span class="sxs-lookup"><span data-stu-id="b4565-138">The downloaded file is located in *Subfolder 2* and is also named with the file ID.</span></span>

    <span data-ttu-id="b4565-139">下面的示例展示了在将项目下载到**C:\Remediation**父文件夹时创建的文件夹路径和错误文件名：</span><span class="sxs-lookup"><span data-stu-id="b4565-139">Here's an example of the folder path and error file name that's created when items are downloaded to the **C:\Remediation** parent folder:</span></span>

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    <span data-ttu-id="b4565-140">如果下载了多个文件，则会将每个文件下载到一个以文件 ID 命名的子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b4565-140">If multiple files are downloaded, each one is downloaded to a subfolder that's named with the file ID.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b4565-141">当您在步骤9和步骤10中上传文件时，修正的文件必须具有相同的文件名，并且位于相同的子文件夹结构中。</span><span class="sxs-lookup"><span data-stu-id="b4565-141">When you upload files in step 9 and step 10, the remediated files must have that same filename and be located in the same subfolder structure.</span></span> <span data-ttu-id="b4565-142">子文件夹和文件名用于将修正的文件与原始错误文件相关联。</span><span class="sxs-lookup"><span data-stu-id="b4565-142">The subfolder and file names are used to associated the remediated file with the original error file.</span></span> <span data-ttu-id="b4565-143">如果文件夹结构或文件名称已更改，您将收到以下错误： `Cannot apply Error Remediation to the current Workingset`。</span><span class="sxs-lookup"><span data-stu-id="b4565-143">If the folder structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span> <span data-ttu-id="b4565-144">为了防止出现任何问题，我们建议将修正的文件保留在相同的父文件夹和子文件夹结构中。</span><span class="sxs-lookup"><span data-stu-id="b4565-144">To prevent any issues, we recommend that keep the remediated files in the same parent folder and subfolder structure.</span></span>

7. <span data-ttu-id="b4565-145">下载文件后，可以使用适当的工具对它们进行修正。</span><span class="sxs-lookup"><span data-stu-id="b4565-145">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="b4565-146">对于受密码保护的文件，可以使用几种密码破解工具。</span><span class="sxs-lookup"><span data-stu-id="b4565-146">For password-protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="b4565-147">如果您知道这些文件的密码，则可以打开它们并删除密码保护。</span><span class="sxs-lookup"><span data-stu-id="b4565-147">If you know the passwords for the files, you can open them and remove the password protection.</span></span>

8. <span data-ttu-id="b4565-148">返回到高级电子数据展示和错误修正向导，然后单击 "**下一步：上传文件**"。</span><span class="sxs-lookup"><span data-stu-id="b4565-148">Return to Advanced eDiscovery and the error remediation wizard and then click **Next: Upload files**.</span></span>  <span data-ttu-id="b4565-149">这将移到下一个页面，你现在可以在这里上传文件。</span><span class="sxs-lookup"><span data-stu-id="b4565-149">This moves to the next page where you can now upload the files.</span></span>

    ![上传文件](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="b4565-151">在 "**文件的位置**" 文本框的 "路径" 中，指定修正文件所在的父文件夹。</span><span class="sxs-lookup"><span data-stu-id="b4565-151">Specify the parent folder where the remediated files are located in the **Path to location of files** text box.</span></span> <span data-ttu-id="b4565-152">同样，父文件夹的子文件夹结构必须与下载文件时创建的子文件夹结构相同。</span><span class="sxs-lookup"><span data-stu-id="b4565-152">Again, the parent folder must have the same subfolder structure that was created when you downloaded the files.</span></span>

    <span data-ttu-id="b4565-153">父文件夹的路径将自动添加到 AzCopy 命令（作为 **/source**参数的值）。</span><span class="sxs-lookup"><span data-stu-id="b4565-153">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Source** parameter).</span></span>

10. <span data-ttu-id="b4565-154">通过单击 "**复制到剪贴板**" 复制预定义命令。</span><span class="sxs-lookup"><span data-stu-id="b4565-154">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="b4565-155">打开 Windows 命令提示符，粘贴 "AzCopy" 命令，然后按**enter**。</span><span class="sxs-lookup"><span data-stu-id="b4565-155">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span> <span data-ttu-id="b4565-156">上传文件。</span><span class="sxs-lookup"><span data-stu-id="b4565-156">upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="b4565-158">运行 AzCopy 命令后，单击 "**下一步：处理文件**"。</span><span class="sxs-lookup"><span data-stu-id="b4565-158">After you run the AzCopy command, click **Next: Process files**.</span></span>

    <span data-ttu-id="b4565-159">处理完成后，可以转到 "查看" 设置并查看修正的文件。</span><span class="sxs-lookup"><span data-stu-id="b4565-159">When processing is complete, you can go to review set and view the remediated files.</span></span> 

## <a name="remediating-errors-in-container-files"></a><span data-ttu-id="b4565-160">修正容器文件中的错误</span><span class="sxs-lookup"><span data-stu-id="b4565-160">Remediating errors in container files</span></span>

<span data-ttu-id="b4565-161">在使用高级电子数据展示无法提取容器文件内容（如 .zip 文件）的情况下，可以下载容器，并将内容扩展到原始容器所在的同一个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b4565-161">In situations when the contents of a container file (such as a .zip file) can't be extracted by Advanced eDiscovery, the containers can be downloaded and the contents expanded into the same folder in which the original container resides.</span></span> <span data-ttu-id="b4565-162">扩展的文件将被视为父容器，就像它最初由高级电子数据展示展开一样。</span><span class="sxs-lookup"><span data-stu-id="b4565-162">The expanded files will be attributed to the parent container as if it was originally expanded by Advanced eDiscovery.</span></span> <span data-ttu-id="b4565-163">此过程如上文所述，除了将单个文件上载为替换文件之外。</span><span class="sxs-lookup"><span data-stu-id="b4565-163">The process works as described as above except for uploading a single file as the replacement file.</span></span>  <span data-ttu-id="b4565-164">上载修正的文件时，请勿包含原始容器文件。</span><span class="sxs-lookup"><span data-stu-id="b4565-164">When you upload remediated files, don't include the original container file.</span></span>

## <a name="remediating-errors-by-uploading-the-extracted-text"></a><span data-ttu-id="b4565-165">通过上传提取的文本修正错误</span><span class="sxs-lookup"><span data-stu-id="b4565-165">Remediating errors by uploading the extracted text</span></span>

<span data-ttu-id="b4565-166">有时，不能将文件修正为高级电子数据展示可以解释的本机格式。</span><span class="sxs-lookup"><span data-stu-id="b4565-166">Sometimes it's not possible to remediate a file to native format that Advanced eDiscovery can interpret.</span></span> <span data-ttu-id="b4565-167">但您可以将原始文件替换为包含原文件（在称为*文本覆盖*的过程中）的原始文本的文本文件。</span><span class="sxs-lookup"><span data-stu-id="b4565-167">But you can replace the original file with a text file that contains the original text of the native file (in a process called *text overlay*).</span></span> <span data-ttu-id="b4565-168">为此，请按照本文中介绍的步骤操作，但不是使用本机格式修正原始文件，而是创建一个包含原始文件中提取的文本的文本文件，然后使用原始文件名上传文本文件。附加了 .txt 后缀。</span><span class="sxs-lookup"><span data-stu-id="b4565-168">To do this, follow the steps described in this article but instead of remediating the original file in the native format, you would create a text file that contains the extracted text from the original file, and then upload the text file using the original filename appended with a .txt suffix.</span></span> <span data-ttu-id="b4565-169">例如，在错误修正过程中使用文件名335850cc-6602-4af0-acfa-1d14d9128ca2 下载文件。</span><span class="sxs-lookup"><span data-stu-id="b4565-169">For example, you download a file during error remediation with the filename 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.</span></span> <span data-ttu-id="b4565-170">在本机应用程序中打开文件，复制文本，然后将其粘贴到名为335850cc-6602-4af0-acfa-1d14d9128ca2 的新文件中。</span><span class="sxs-lookup"><span data-stu-id="b4565-170">You open the file in the native application, copy the text, and then paste it into a new file named 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt.</span></span> <span data-ttu-id="b4565-171">执行此操作时，请务必在将修正的文本文件上载到高级电子数据展示之前，从本地计算机上的修正文件位置中删除原始文件（以本机格式）。</span><span class="sxs-lookup"><span data-stu-id="b4565-171">When you do this, be sure to remove the original file in the native format from the remediated file location on your local computer before uploading the remediated text file to Advanced eDiscovery.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="b4565-172">修正文件时会发生什么情况</span><span class="sxs-lookup"><span data-stu-id="b4565-172">What happens when files are remediated</span></span>

<span data-ttu-id="b4565-173">当上载修正的文件时，原始元数据将保留，但以下字段除外：</span><span class="sxs-lookup"><span data-stu-id="b4565-173">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="b4565-174">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="b4565-174">ExtractedTextSize</span></span>
- <span data-ttu-id="b4565-175">HasText</span><span class="sxs-lookup"><span data-stu-id="b4565-175">HasText</span></span>
- <span data-ttu-id="b4565-176">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="b4565-176">IsErrorRemediate</span></span>
- <span data-ttu-id="b4565-177">LoadId</span><span class="sxs-lookup"><span data-stu-id="b4565-177">LoadId</span></span>
- <span data-ttu-id="b4565-178">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="b4565-178">ProcessingErrorMessage</span></span>
- <span data-ttu-id="b4565-179">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="b4565-179">ProcessingStatus</span></span>
- <span data-ttu-id="b4565-180">文本</span><span class="sxs-lookup"><span data-stu-id="b4565-180">Text</span></span>
- <span data-ttu-id="b4565-181">WordCount</span><span class="sxs-lookup"><span data-stu-id="b4565-181">WordCount</span></span>
- <span data-ttu-id="b4565-182">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="b4565-182">WorkingsetId</span></span>

<span data-ttu-id="b4565-183">有关高级电子数据展示中所有元数据字段的定义，请参阅[Document metadata fields](document-metadata-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="b4565-183">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields.md).</span></span>
