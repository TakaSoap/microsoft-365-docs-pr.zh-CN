---
title: 将非 Microsoft 365 数据加载到证据中
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
ms.openlocfilehash: 9eef3b38ceef7efc42e1f66c45069f51a0a95d45
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632627"
---
# <a name="load-non-microsoft-365-data-into-evidence"></a><span data-ttu-id="4b28f-102">将非 Microsoft 365 数据加载到证据中</span><span class="sxs-lookup"><span data-stu-id="4b28f-102">Load non-Microsoft 365 data into evidence</span></span>

<span data-ttu-id="4b28f-103">并非所有可能需要在数据调查中进行分析的文档都将位于 Microsoft 365 中。</span><span class="sxs-lookup"><span data-stu-id="4b28f-103">Not all documents that you may need to analyze in a data investigation will be located in Microsoft 365.</span></span> <span data-ttu-id="4b28f-104">使用非 Microsoft 365 内容导入功能，可以将不在 Microsoft 365 中的文档上传到证据，以便可以在数据调查中分析这些文档。</span><span class="sxs-lookup"><span data-stu-id="4b28f-104">With the Non-Microsoft 365 content import feature you can upload documents that don't live in Microsoft 365 into evidence so they can be analyzed in a data investigation.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4b28f-105">准备工作</span><span class="sxs-lookup"><span data-stu-id="4b28f-105">Before you begin</span></span>

<span data-ttu-id="4b28f-106">使用此过程中所述的上传非 Microsoft 365 功能时，需要具备以下条件：</span><span class="sxs-lookup"><span data-stu-id="4b28f-106">Using the upload Non-Microsoft 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="4b28f-107">Microsoft 365 或 Office 365 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="4b28f-107">A Microsoft 365 or Office 365 E5 subscription.</span></span>

- <span data-ttu-id="4b28f-108">将上载其非 Microsoft 365 内容的所有感兴趣的人都必须具有相应的 E5 或 E5 附加许可证。</span><span class="sxs-lookup"><span data-stu-id="4b28f-108">All people of interest whose non-Microsoft 365 content will be uploaded must have the appropriate E5 or E5 add-on license.</span></span>

- <span data-ttu-id="4b28f-109">现有电子数据展示事例。</span><span class="sxs-lookup"><span data-stu-id="4b28f-109">An existing eDiscovery case.</span></span>

- <span data-ttu-id="4b28f-110">将上载的所有文件都收集到每个保管人都有一个文件夹的文件夹中，文件夹的名称*alias@domainname*的格式。</span><span class="sxs-lookup"><span data-stu-id="4b28f-110">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname*.</span></span> <span data-ttu-id="4b28f-111">*Alias@domainname*必须是用户的别名和域。</span><span class="sxs-lookup"><span data-stu-id="4b28f-111">The *alias@domainname* must be user's alias and domain.</span></span> <span data-ttu-id="4b28f-112">您可以将所有*alias@domainname*文件夹收集到一个根文件夹中。</span><span class="sxs-lookup"><span data-stu-id="4b28f-112">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="4b28f-113">根文件夹只能包含*alias@domainname*文件夹，根文件夹中必须没有松散文件。</span><span class="sxs-lookup"><span data-stu-id="4b28f-113">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="4b28f-114">一种帐户，既可以是电子数据展示管理器，也可以是安装在可访问非 Microsoft 365 内容文件夹结构的计算机上的电子数据展示管理员 Microsoft Azure 存储工具。</span><span class="sxs-lookup"><span data-stu-id="4b28f-114">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span>

- <span data-ttu-id="4b28f-115">安装 AzCopy，您可以从以下位置执行此操作：https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="4b28f-115">Install AzCopy, which you can do from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

## <a name="upload-non-microsoft-365-content-in-to-a-data-investigation"></a><span data-ttu-id="4b28f-116">将非 Microsoft 365 内容上传到数据调查</span><span class="sxs-lookup"><span data-stu-id="4b28f-116">Upload non-Microsoft 365 content in to a data investigation</span></span>

1. <span data-ttu-id="4b28f-117">打开**数据调查**并转到调查，以将非 Microsoft 365 数据上载到。</span><span class="sxs-lookup"><span data-stu-id="4b28f-117">Open **Data Investigations** and go to the investigation that the non-Microsoft 365 data will be uploaded to.</span></span>  <span data-ttu-id="4b28f-118">单击 "**证据**" 选项卡，然后选择您希望将数据加载到的证据集。</span><span class="sxs-lookup"><span data-stu-id="4b28f-118">Click the **Evidence** tab, then select the evidence set you wish to load the data to.</span></span>  <span data-ttu-id="4b28f-119">如果尚未创建证据集，现在可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4b28f-119">If you have not already created an evidence set, you can do so now.</span></span>  <span data-ttu-id="4b28f-120">最后，单击 "**管理证据**"，然后查看 "数据" 部分中的 "**上载**"</span><span class="sxs-lookup"><span data-stu-id="4b28f-120">Finally, click **Manage evidence** then **View uploads** in the data section</span></span>

2. <span data-ttu-id="4b28f-121">单击 "**上载文件**" 按钮以启动 "非 Microsoft 365 数据导入向导"。</span><span class="sxs-lookup"><span data-stu-id="4b28f-121">Click the **Upload files** button to start the Non-Microsoft 365 data import wizard.</span></span>

![上传文件](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="4b28f-123">向导中的第一步是为要上载的文件准备一个安全的 Azure blob。</span><span class="sxs-lookup"><span data-stu-id="4b28f-123">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="4b28f-124">准备完成后，单击 "**下一步：上传文件**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="4b28f-124">After the preparation is complete, click the **Next: Upload files** button.</span></span>

![准备非 Microsoft 365 数据导入](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="4b28f-126">在 "**上载文件**" 步骤中，指定**文件位置的路径**，这是您计划导入的非 Microsoft 365 数据所在的位置。</span><span class="sxs-lookup"><span data-stu-id="4b28f-126">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Microsoft 365 data you plan on importing is located.</span></span>  <span data-ttu-id="4b28f-127">设置正确的位置可确保正确更新 AzCopy 命令。</span><span class="sxs-lookup"><span data-stu-id="4b28f-127">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="4b28f-128">如果尚未安装 AzCopy，可以从以下位置执行此操作：https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="4b28f-128">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="4b28f-129">通过单击 "**复制到剪贴板**" 链接复制预定义命令。</span><span class="sxs-lookup"><span data-stu-id="4b28f-129">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="4b28f-130">启动 windows 命令提示符，粘贴命令并按 enter。</span><span class="sxs-lookup"><span data-stu-id="4b28f-130">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="4b28f-131">将在下一步中将文件上载到安全 Azure blob 存储。</span><span class="sxs-lookup"><span data-stu-id="4b28f-131">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![上载非 Microsoft 365 数据导入的文件](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![使用 AzCopy 导入非 Microsoft 365 数据](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="4b28f-134">最后，返回到安全 & 合规性，然后单击 "**下一步：处理文件**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="4b28f-134">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="4b28f-135">这将启动已上载文件的处理、文本提取和索引。</span><span class="sxs-lookup"><span data-stu-id="4b28f-135">This initiates processing, text extraction, and indexing of the uploaded files.</span></span>  <span data-ttu-id="4b28f-136">您可以在此处或在 "**作业**" 选项卡中跟踪处理进度。 完成后，新文件就会出现在证据集中。</span><span class="sxs-lookup"><span data-stu-id="4b28f-136">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files are available in the evidence set.</span></span>  <span data-ttu-id="4b28f-137">处理完成后，可以关闭向导。</span><span class="sxs-lookup"><span data-stu-id="4b28f-137">After processing is complete, you can dismiss the wizard.</span></span>

![非 Microsoft 365 导入过程文件](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

