---
title: 将非 Microsoft 365 数据加载到审阅集
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何将非Microsoft 365数据导入审阅集，以在Advanced eDiscovery分析。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9f705080ad5a769032581a1517b2daee8e822b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903498"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a><span data-ttu-id="cc9c9-103">将非 Microsoft 365 数据加载到审阅集</span><span class="sxs-lookup"><span data-stu-id="cc9c9-103">Load non-Microsoft 365 data into a review set</span></span>

<span data-ttu-id="cc9c9-104">并非所有需要在文档中分析Advanced eDiscovery文档都位于Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Microsoft 365.</span></span> <span data-ttu-id="cc9c9-105">使用高级电子数据展示中的非 Microsoft 365 数据导入功能，可以将不在 Microsoft 365 中的文档上传到审阅集。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-105">With the non-Microsoft 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Microsoft 365 to a review set.</span></span> <span data-ttu-id="cc9c9-106">本文演示如何将非文档Microsoft 365文档Advanced eDiscovery进行分析。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-106">This article shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>

## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="cc9c9-107">上载非内容Office 365的要求</span><span class="sxs-lookup"><span data-stu-id="cc9c9-107">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="cc9c9-108">使用本文Microsoft 365上传非网站功能需要具备以下各项：</span><span class="sxs-lookup"><span data-stu-id="cc9c9-108">Using the upload non-Microsoft 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="cc9c9-109">必须为要关联非托管Microsoft 365的所有保管人分配适当的许可证。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-109">All custodians that you want to associate non-Microsoft 365 content to must be assigned the appropriate license.</span></span> <span data-ttu-id="cc9c9-110">有关详细信息，请参阅开始[Advanced eDiscovery。](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)</span><span class="sxs-lookup"><span data-stu-id="cc9c9-110">For more information, see [Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span></span>

- <span data-ttu-id="cc9c9-111">现有Advanced eDiscovery案例。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-111">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="cc9c9-112">必须将保管人添加到案例，然后才能上载非托管数据并将其Microsoft 365关联。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-112">Custodians must be added to the case before you can upload and associate the non-Microsoft 365 data to them.</span></span>

- <span data-ttu-id="cc9c9-113">非 Microsoft 365 数据必须是高级电子数据展示支持的文件类型。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-113">Non-Microsoft 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="cc9c9-114">有关详细信息，请参阅 [高级电子数据展示中受支持的文件类型](supported-filetypes-ediscovery20.md)。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-114">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="cc9c9-115">上传到审阅集的所有文件必须位于文件夹中，每个文件夹与特定保管人关联。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-115">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="cc9c9-116">这些文件夹的名称必须使用以下命名格式：*alias@domainname*。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-116">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="cc9c9-117">alias@domainname 必须是用户的 Microsoft 365 别名和域。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-117">The alias@domainname must be the user's Microsoft 365 alias and domain.</span></span> <span data-ttu-id="cc9c9-118">你可以收集根文件夹中alias@domainname文件夹。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-118">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="cc9c9-119">根文件夹只能包含alias@domainname文件夹。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-119">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="cc9c9-120">根文件夹中的松散文件不受支持。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-120">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="cc9c9-121">要上载的非Microsoft 365文件夹结构与以下示例类似：</span><span class="sxs-lookup"><span data-stu-id="cc9c9-121">The folder structure for the non-Microsoft 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="cc9c9-122">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="cc9c9-122">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="cc9c9-123">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="cc9c9-123">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="cc9c9-124">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="cc9c9-124">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="cc9c9-125">其中 abraham.mcmahon@contoso.com、jewell.gordon@contoso.com 和 staci.gonzalez@contoso.com 是本例中保管人 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-125">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![非Microsoft 365数据上载文件夹结构](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="cc9c9-127">分配给电子数据展示管理员角色组的帐户 (添加为电子数据展示管理员) 。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-127">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="cc9c9-128">AzCopy v8.1 工具安装在有权访问非内容文件夹Microsoft 365计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-128">The AzCopy v8.1 tool installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span> <span data-ttu-id="cc9c9-129">若要安装 AzCopy，请参阅 Windows 上的[使用 AzCopy v8.1 传输Windows。](/previous-versions/azure/storage/storage-use-azcopy)</span><span class="sxs-lookup"><span data-stu-id="cc9c9-129">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="cc9c9-130">请务必将 AzCopy 安装在默认位置，即 **%ProgramFiles (x86) %\Microsoft SDKs\Azure\AzCopy**。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-130">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="cc9c9-131">必须使用 AzCopy v8.1。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-131">You must use AzCopy v8.1.</span></span> <span data-ttu-id="cc9c9-132">AzCopy 的其他版本在 Advanced eDiscovery 中加载非 Microsoft 365 时可能Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-132">Other versions of AzCopy may not work when loading non-Microsoft 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a><span data-ttu-id="cc9c9-133">Upload非Microsoft 365内容放入Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="cc9c9-133">Upload non-Microsoft 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="cc9c9-134">作为电子数据展示管理员或电子数据展示管理员，Advanced eDiscovery，然后转到非Microsoft 365数据将上载到的情况。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-134">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, and go to the case that the non-Microsoft 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="cc9c9-135">单击 **"** 审阅集"，然后选择要将数据上载到的非Microsoft 365审阅集。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-135">Click **Review sets**, and then select the review set to upload the non-Microsoft 365 data to.</span></span>  <span data-ttu-id="cc9c9-136">如果没有审阅集，可以创建一个审阅集。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-136">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="cc9c9-137">在审阅设置中，单击“**管理审阅集**”，然后在“**非 Microsoft 365 数据**”磁铁上单击“**查看内容**”。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-137">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Microsoft 365 data** tile.</span></span>

4. <span data-ttu-id="cc9c9-138">单击“**上传文件**”以启动数据导入向导。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-138">Click **Upload files** to start the data import wizard.</span></span>

   ![上传文件](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="cc9c9-140">向导中的第一步是为上传文件准备安全的由 Microsoft 提供的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-140">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="cc9c9-141">准备完成后，“**下一步：上传文件**”按钮转为活动状态。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-141">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![非Microsoft 365导入：准备](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="cc9c9-143">单击“**下一步：上传文件**”。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-143">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="cc9c9-144">在 **Upload文件"** 页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="cc9c9-144">On the **Upload files** page, do the following:</span></span>

   ![非Microsoft 365导入：Upload文件](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="cc9c9-146">a.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-146">a.</span></span> <span data-ttu-id="cc9c9-147">在 **"文件的位置** 的路径"框中，验证或键入要上载的非文件存储Microsoft 365文件夹的位置。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-147">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Microsoft 365 data you want to upload.</span></span> <span data-ttu-id="cc9c9-148">例如，对于"开始之前"部分中显示的示例文件的位置，键入 **%USERPROFILE\Downloads\nonO365**。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-148">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="cc9c9-149">提供正确的位置可确保正确更新路径下的框中显示的 AzCopy 命令。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-149">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="cc9c9-150">b.</span><span class="sxs-lookup"><span data-stu-id="cc9c9-150">b.</span></span> <span data-ttu-id="cc9c9-151">单击 **"复制到剪贴板** "以复制显示在框中的命令。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-151">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="cc9c9-152">启动Windows提示符，粘贴在上一步中复制的命令，然后按 **Enter** 启动 AzCopy 命令。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-152">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="cc9c9-153">启动命令后，非Microsoft 365文件将上载到步骤 4 Azure 存储准备的位置。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-153">After you start the command, the non-Microsoft 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![非Microsoft 365导入：AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="cc9c9-155">如前所述，您必须使用 AzCopy v8.1 成功使用"文件"页上Upload **命令**。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-155">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="cc9c9-156">如果提供的 AzCopy 命令失败，请参阅疑难解答[AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md)。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-156">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="cc9c9-157">返回到安全与&中心，然后单击向导中的"下一 **步： 处理** 文件"。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-157">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="cc9c9-158">此操作将启动对已上传到 Azure 存储位置的非 Microsoft 365 文件的处理、文本提取和编制索引。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-158">This initiates processing, text extraction, and indexing of the non-Microsoft 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="cc9c9-159">通过查看名为将非文件数据添加到审阅集的作业，跟踪"进程文件"页或"作业"**选项卡Microsoft 365处理文件的进度**。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-159">Track the progress of processing the files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Microsoft 365 data to a review set**.</span></span>  <span data-ttu-id="cc9c9-160">作业完成后，新文件将在审阅集内可用。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-160">After the job is finished, the new files will be available in the review set.</span></span>

   ![非Microsoft 365导入：处理文件](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="cc9c9-162">处理完成后，可以关闭该向导。</span><span class="sxs-lookup"><span data-stu-id="cc9c9-162">After the processing is finished, you can close the wizard.</span></span>