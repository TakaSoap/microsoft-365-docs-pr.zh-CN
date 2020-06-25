---
title: 有关导入组织的 PST 文件的概述
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
ms.custom:
- seo-marvel-apr2020
description: 了解如何使用安全与合规中心的导入服务将电子邮件数据（PST 文件）批量导入到用户邮箱中。
ms.openlocfilehash: 8c80f42261ab008d2c3d0957661d5b295695ef6e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817581"
---
# <a name="overview-of-importing-your-organizations-pst-files"></a><span data-ttu-id="2b9fb-103">有关导入组织的 PST 文件的概述</span><span class="sxs-lookup"><span data-stu-id="2b9fb-103">Overview of importing your organization's PST files</span></span>

> [!NOTE]
> <span data-ttu-id="2b9fb-104">本文适用于管理员。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-104">This article is for administrators.</span></span> <span data-ttu-id="2b9fb-105">你正在尝试将 PST 文件导入到自己的邮箱吗？</span><span class="sxs-lookup"><span data-stu-id="2b9fb-105">Are you trying to import PST files to your own mailbox?</span></span> <span data-ttu-id="2b9fb-106">请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://go.microsoft.com/fwlink/p/?LinkID=785075)。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-106">See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075).</span></span>

<span data-ttu-id="2b9fb-107">可以使用安全与合规中心的导入服务，将 PST 文件快速批量导入到组织的 Exchange Online 邮箱中。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-107">You can use the Import service in the Security & Compliance Center to quickly bulk-import PST files to Exchange Online mailboxes in your organization.</span></span> <span data-ttu-id="2b9fb-108">可通过两种方法将 PST 文件导入到 Office 365 中：</span><span class="sxs-lookup"><span data-stu-id="2b9fb-108">There are two ways you can import PST files to Office 365:</span></span>

- <span data-ttu-id="2b9fb-109">**网络上传** ![云上传](../media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) - 通过网络将 PST 文件上传到 Microsoft 云中的临时 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-109">**Network upload** ![Cloud upload](../media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) - Upload the PST files over the network to a temporary Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="2b9fb-110">然后，使用 Office 365 导入服务将 PST 数据导入到组织的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-110">Then you use the Office 365 Import service to import the PST data to mailboxes in your organization.</span></span> 

- <span data-ttu-id="2b9fb-111">**驱动器寄送** ![硬盘](../media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) - 将 PST 文件复制到 BitLocker 加密的硬盘中，然后将驱动器实际寄到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-111">**Drive shipping** ![Hard disk](../media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) - Copy the PST files to a BitLocker-encrypted hard drive and then physically ship the drive to Microsoft.</span></span> <span data-ttu-id="2b9fb-112">Microsoft 收到硬盘后，数据中心工作人员会将数据上传到 Microsoft 云中的临时 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-112">When Microsoft receives the hard drive, data center personnel upload the data to a temporary Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="2b9fb-113">然后，使用 Office 365 导入服务将数据导入到组织的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-113">Then you use the Office 365 Import service to import the data to mailboxes in your organization.</span></span>

## <a name="step-by-step-instructions"></a><span data-ttu-id="2b9fb-114">分步说明</span><span class="sxs-lookup"><span data-stu-id="2b9fb-114">Step-by-step instructions</span></span>
  
<span data-ttu-id="2b9fb-115">请参阅以下主题，获取有关将组织的 PST 文件导入到 Office 365 的详细分步说明。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-115">See one of the following topics for detailed, step-by-step instructions for bulk-importing your organization's PST files to Office 365.</span></span> 

- [<span data-ttu-id="2b9fb-116">使用网络上载将 PST 文件导入到 Office 365</span><span class="sxs-lookup"><span data-stu-id="2b9fb-116">Use network upload to import PST files to Office 365</span></span>](use-network-upload-to-import-pst-files.md)

- [<span data-ttu-id="2b9fb-117">使用驱动器传送导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="2b9fb-117">Use drive shipping to import PST files</span></span>](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a><span data-ttu-id="2b9fb-118">导入 PST 文件的工作原理</span><span class="sxs-lookup"><span data-stu-id="2b9fb-118">How importing PST files works</span></span>

<span data-ttu-id="2b9fb-119">以下是完整 PST 流程的图示和说明。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-119">Here's an illustration and description of the complete PST import process.</span></span> <span data-ttu-id="2b9fb-120">该图示显示了主要工作流程并突出显示了网络上传和驱动器寄送方法之间的差别。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-120">The illustration shows the primary workflow and highlights the differences between the network upload and drive shipping methods.</span></span>
  
![PST 导入流程的工作流](../media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. <span data-ttu-id="2b9fb-122">**将 PST 导入工具和密钥下载到专用 Azure 存储位置** - 第一步是下载用于上传 PST 文件或将其复制到硬盘的工具和访问密钥。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-122">**Download the PST import tools and key to private Azure Storage location** - The first step is to download the tool and access key used to upload the PST files or copy them to a hard drive.</span></span> <span data-ttu-id="2b9fb-123">需要从安全与合规中心的“导入”\*\*\*\* 页获取工具和密钥。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-123">You obtain these from the **Import** page in the Security & Compliance Center.</span></span> <span data-ttu-id="2b9fb-124">密钥为你（如果是驱动器寄送，则是 Microsoft 数据中心人员）提供所需的权限用于将 PST 文件上传到安全的专用 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-124">The key provides you (or Microsoft data center personnel in the case of drive shipping) with the necessary permissions to upload PST files to a private and secure Azure Storage location.</span></span> <span data-ttu-id="2b9fb-125">此访问密钥对组织是唯一的，有助于防止在 PST 文件上传至 Microsoft 云之后对其进行未经授权的访问。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-125">This access key is unique to your organization and helps prevent unauthorized access to your PST files after they're uploaded to the Microsoft cloud.</span></span> <span data-ttu-id="2b9fb-126">将 PST 文件导入到 Microsoft 365 不需要你的组织拥有单独的 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-126">Importing PST files to Microsoft 365 doesn't require your organization to have a separate Azure subscription.</span></span> 
    
2. <span data-ttu-id="2b9fb-127">**上传或复制 PST 文件** - 下一步取决于你是使用网络上传或驱动器寄送来导入 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-127">**Upload or copy the PST files** - The next step depends on whether you're using network upload or drive shipping to import PST files.</span></span> <span data-ttu-id="2b9fb-128">在两种情况下，你均使用在上一步中获得的工具和安全存储密钥。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-128">In both cases, you'll use the tool and secure storage key that you obtained in the previous step.</span></span>
    
    - <span data-ttu-id="2b9fb-129">**网络上传：** AzCopy.exe 工具（在步骤 1 中下载）用于将 PST 文件上传并存储于 Microsoft 云中的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-129">**Network upload:** The AzCopy.exe tool (downloaded in step 1) is used to upload and store your PST files in an Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="2b9fb-130">将 PST 文件上传至的 Azure 存储位置驻留在组织所在的区域 Microsoft 数据中心。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-130">The Azure Storage location that you upload your PST files to resides in the same regional Microsoft datacenter where your organization is located.</span></span>
    
      <span data-ttu-id="2b9fb-131">若要上传，要导入的 PST 文件必须位于组织的文件共享或文件服务器上。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-131">To upload them, the PST files that you want to import have to be located in a file share or file server in your organization.</span></span>
    
    - <span data-ttu-id="2b9fb-132">**驱动器寄送：** WAImportExport.exe 工具（在步骤 1 中下载）用于将 PST 文件复制到硬盘。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-132">**Drive shipping:** The WAImportExport.exe tool (downloaded in step 1) is used to copy your PST files to the hard drive.</span></span> <span data-ttu-id="2b9fb-133">该工具使用 BitLocker 加密硬盘，然后将 PST 复制到硬盘。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-133">This tool encrypts the hard drive with BitLocker and then copies the PSTs to the hard drive.</span></span> <span data-ttu-id="2b9fb-134">与网络上传方法类似，想要复制到硬盘的 PST 文件必须位于组织的文件共享或文件服务器上。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-134">Like network upload, the PST files that you want to copy to the hard drive have to be located in a file share or file server in your organization.</span></span>
    
3. <span data-ttu-id="2b9fb-135">**创建 PST 导入映射文件** - 将 PST 文件上传至 Azure 存储位置或复制到硬盘之后，下一步是创建逗号分隔值 (CSV) 文件，用于指定 PST 文件将要导入到的用户邮箱（并且 PST 文件可导入到用户的主邮箱或其存档邮箱）。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-135">**Create a PST import mapping file** - After the PST files have been uploaded to the Azure Storage location or copied to a hard drive, the next step is to create a comma-separated value (CSV) file that specifies which user mailboxes the PST files will be imported to (and a PST file can be imported to a user's primary mailbox or their archive mailbox).</span></span> <span data-ttu-id="2b9fb-136">Office 365 导入服务将使用此信息来导入 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-136">The Office 365 Import service will use the information to import the PST files.</span></span> 
    
4. <span data-ttu-id="2b9fb-137">**创建 PST 导入作业** - 下一步是在安全与合规中心的“**导入 PST 文件**”页上创建 PST 导入作业并提交在上一步骤创建的 PST 导入映射文件。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-137">**Create a PST import job** - The next step is to create a PST import job on the **Import PST files** page in the Security & Compliance Center and submit the PST import mapping file created in the previous step.</span></span> <span data-ttu-id="2b9fb-138">对于网络上传（因为 PST 文件已上传至 Azure），Microsoft 365 将分析 PST 文件中的数据，然后为你提供设置筛选器的机会，以便控制哪些数据被实际导入到 PST 导入映射文件中指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-138">For network upload (because the PST files have been uploaded to Azure) Microsoft 365 analyzes the data in the PST files and then gives you an opportunity to set filters that control what data actually gets imported to the mailboxes specified in the PST import mapping file.</span></span> 
    
    <span data-ttu-id="2b9fb-139">对于驱动器寄送，在此过程中的这个环节会发生一些其他事情。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-139">For drive shipping, a few additional things happen at this point in the process.</span></span>
    
    - <span data-ttu-id="2b9fb-140">将硬盘实际寄到 Microsoft 数据中心（创建导入作业时，将会显示 Microsoft 数据中心的寄送地址）。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-140">You physically ship the hard drive to a Microsoft data center (the shipping address for the Microsoft data center is displayed when the import job is created).</span></span>
    
    - <span data-ttu-id="2b9fb-141">Microsoft 收到硬盘后，数据中心工作人员会将硬盘上的 PST 文件上传到组织的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-141">When Microsoft receives the hard drive, data center personnel will upload the PST files on the hard drive to the Azure Storage location for your organization.</span></span> <span data-ttu-id="2b9fb-142">如前面所述，PST 文件将上传至驻留在组织所在的区域 Microsoft 数据中心的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-142">As previously explained, your PST files are uploaded to a Azure Storage location that resides in the same regional Microsoft datacenter where your organization is located.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="2b9fb-143">硬盘驱动器上的 PST 文件将在 Microsoft 收到硬盘驱动器之后 7-10 个工作日之内上传至 Azure。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-143">The PST files on the hard drive are uploaded to Azure within 7 to 10 business days after Microsoft receives the hard drive.</span></span>

      <span data-ttu-id="2b9fb-144">与网络上传流程类似，Microsoft 365 随后将分析 PST 文件中的数据，并为你提供设置筛选器的机会，以便控制哪些数据被实际导入到 PST 导入映射文件中指定的邮箱。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-144">Like the network upload process, Microsoft 365 then analyzes the data in the PST files and gives you an opportunity to set filters that control what data actually gets imported to the mailboxes specified in the PST import mapping file.</span></span>
    
    - <span data-ttu-id="2b9fb-145">Microsoft 将硬盘寄回给你。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-145">Microsoft ships the hard drive back to you.</span></span>
    
5. <span data-ttu-id="2b9fb-146">**筛选将要导入到邮箱的 PST 数据** - 创建导入作业之后（并在驱动器传送操作中的 PST 文件上传至 Azure 存储位置后），Microsoft 365 将安全地分析 PST 文件中的数据，方法是标识项目期限以及 PST 文件中所含的不同邮件类型。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-146">**Filter the PST data that will be imported to mailboxes** - After the import job is created (and after the PST files from a drive shipping job are uploaded to the Azure Storage location) Microsoft 365 analyzes the data in the PST files (safely and securely) by identifying the age of the items and the different message types included in the PST files.</span></span> <span data-ttu-id="2b9fb-147">分析完成且数据准备就绪可供导入后，你可以选择导入 PST 文件中包含的所有数据，或者通过设置用于控制可导入哪些数据的筛选器来减少导入的数据。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-147">When the analysis is completed and the data is ready to import, you have the option to import all the data contained in the PST files or you can trim the data that's imported by setting filters that control what data gets imported.</span></span> 
    
6. <span data-ttu-id="2b9fb-148">**启动 PST 导入作业** - 启动导入作业后，Microsoft 365 使用 PST 导入映射文件中的信息将 PST 文件从 Azure 存储位置导入到用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-148">**Start the PST import job** - After the import job is started, Microsoft 365 uses the information in the PST import mapping file to import the PSTs files from the he Azure Storage location to user mailboxes.</span></span> <span data-ttu-id="2b9fb-149">与导入作业相关的状态信息（包括与每个导入的 PST 文件相关的信息）将显示在安全与合规中心的“**导入 PST 文件**”页。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-149">Status information about the import job (including information about each PST file being imported) is displayed on the **Import PST files** page in the Security & Compliance Center.</span></span> <span data-ttu-id="2b9fb-150">导入作业完成后，作业的状态将设置为“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-150">When the import job is finished, the status for the job is set to **Complete**.</span></span>
  
## <a name="why-import-email-data-to-microsoft-365"></a><span data-ttu-id="2b9fb-151">为什么要将电子邮件数据导入到 Microsoft 365？</span><span class="sxs-lookup"><span data-stu-id="2b9fb-151">Why import email data to Microsoft 365?</span></span>

- <span data-ttu-id="2b9fb-152">这是将组织的存档邮件数据导入到 Microsoft 365 的好方法。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-152">It's a good way to import your organization's archival messaging data to Microsoft 365.</span></span>
    
- <span data-ttu-id="2b9fb-153">可以使用“[智能导入](filter-data-when-importing-pst-files.md)”功能来筛选 PST 文件中实际导入到目标邮箱的项。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-153">You can use the [Intelligent Import](filter-data-when-importing-pst-files.md) feature to filter the items in PST files that actually get imported to the target mailboxes.</span></span> <span data-ttu-id="2b9fb-154">这使你能够通过设置用于控制导入的数据的筛选器来减少导入的数据。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-154">This lets you trim the data that's imported by setting filters that control what data gets imported.</span></span> 
    
- <span data-ttu-id="2b9fb-155">通过允许你执行以下操作，将电子邮件数据导入到 Microsoft 365 有助于满足组织的合规性需求：</span><span class="sxs-lookup"><span data-stu-id="2b9fb-155">Importing email data to Microsoft 365 helps address compliance needs of your organization by letting you:</span></span>
    
  - <span data-ttu-id="2b9fb-156">启用[存档邮箱](enable-archive-mailboxes.md)和[无限存档](unlimited-archiving.md)，为用户提供额外的邮箱存储空间。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-156">Enable [archive mailboxes](enable-archive-mailboxes.md) and [unlimited archiving](unlimited-archiving.md) to give users additional mailbox storage space.</span></span> 
    
  - <span data-ttu-id="2b9fb-157">将邮箱置于“[诉讼保留](https://go.microsoft.com/fwlink/?linkid=841243)”以保留内容。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-157">Place mailboxes on [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=841243) to retain content.</span></span> 
    
  - <span data-ttu-id="2b9fb-158">使用“[控制搜索工具](content-search.md)”搜索邮箱内容。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-158">Use the [Content Search tool](content-search.md) to search for mailbox content.</span></span> 
    
  - <span data-ttu-id="2b9fb-159">使用[电子数据展示事例](ediscovery-cases.md)管理组织的法律调查</span><span class="sxs-lookup"><span data-stu-id="2b9fb-159">Use [eDiscovery cases](ediscovery-cases.md) to manage your organization's legal investigations</span></span> 
    
  - <span data-ttu-id="2b9fb-160">使用安全与合规中心的“[保留策略](retention-policies.md)”来控制邮箱内容的保留时长，然后在保留期限到期之后删除内容。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-160">Use [retention policies](retention-policies.md) in the Security & Compliance Center to control how long mailbox content is retained, and then delete content after the retention period expires.</span></span> 

  - <span data-ttu-id="2b9fb-161">使用“[沟通合规性策略](communication-compliance.md)”检查邮件，以确保它们符合邮件标准并添加分类类型。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-161">Use [Communication compliance policies](communication-compliance.md) to examine messages to make sure they are compliant with message standards and add a classification type.</span></span>
    
- <span data-ttu-id="2b9fb-162">将数据导入到 Microsoft 365 有助于防止数据丢失。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-162">Importing data to Microsoft 365 helps protect against data loss.</span></span> <span data-ttu-id="2b9fb-163">导入到 Microsoft 365 的电子邮件数据将继承 Exchange Online 的高可用性功能。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-163">Email data that's imported to Microsoft 365 inherits the high availability features of Exchange Online.</span></span>
    
- <span data-ttu-id="2b9fb-164">用户在任意设备上都可以使用电子邮件数据，因为数据存储在云中。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-164">Email data is available to users from all devices because it's stored in the cloud.</span></span>
    
## <a name="importing-sharepoint-data-to-microsoft-365"></a><span data-ttu-id="2b9fb-165">将 SharePoint 数据导入到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b9fb-165">Importing SharePoint data to Microsoft 365</span></span>

<span data-ttu-id="2b9fb-166">此外，还可以将文件和文档导入到组织中的 SharePoint 网站和 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-166">You can also import files and documents to SharePoint sites and OneDrive accounts in your organization.</span></span> <span data-ttu-id="2b9fb-167">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="2b9fb-167">For more information, see the following articles:</span></span>

- [<span data-ttu-id="2b9fb-168">迁移到 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2b9fb-168">Migrate to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)

- [<span data-ttu-id="2b9fb-169">SharePoint 迁移工具简介</span><span class="sxs-lookup"><span data-stu-id="2b9fb-169">Introducing the SharePoint Migration Tool</span></span>](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [<span data-ttu-id="2b9fb-170">使用 PowerShell 迁移到 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2b9fb-170">Migrate to SharePoint Online using PowerShell</span></span>](https://docs.microsoft.com/sharepointmigration/overview-spmt-ps-cmdlets)

- [<span data-ttu-id="2b9fb-171">使用 Azure Data Box 将文件共享内容迁移到 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2b9fb-171">Migrate your file share content to SharePoint Online using the Azure Data Box</span></span>](https://docs.microsoft.com/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)


## <a name="frequently-asked-questions-about-importing-pst-files"></a><span data-ttu-id="2b9fb-172">有关导入 PST 文件的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="2b9fb-172">Frequently asked questions about importing PST files</span></span>
  
<span data-ttu-id="2b9fb-173">以下是与使用 Office 365 导入服务将 PST 文件批量上传至 Microsoft 365 邮箱相关的常见问题。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-173">Here are some frequently asked questions about using the Office 365 Import service to bulk-import PST files to Microsoft 365 mailboxes.</span></span> 
  
- [<span data-ttu-id="2b9fb-174">使用网络上传导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="2b9fb-174">Using network upload to import PST files</span></span>](#using-network-upload-to-import-pst-files)
  
- [<span data-ttu-id="2b9fb-175">使用驱动器寄送导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="2b9fb-175">Using drive shipping to import PST files</span></span>](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="2b9fb-176">使用网络上传导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="2b9fb-176">Using network upload to import PST files</span></span>

 <span data-ttu-id="2b9fb-177">**在 Office 365 导入服务中创建导入作业需要哪些权限？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-177">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="2b9fb-178">必须分配有 Exchange Online 中的邮箱导入导出角色，才能将 PST 文件导入到 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-178">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="2b9fb-179">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-179">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="2b9fb-180">您可以向“组织管理”角色组添加“邮箱导入导出”角色。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-180">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="2b9fb-181">或者可以创建新的角色组，分配邮箱导入导出角色，然后将自己或其他用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-181">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="2b9fb-182">有关详细信息，请参阅[管理 Exchange Online 中的角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)中的“向角色组添加角色”或“创建角色组”部分。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-182">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="2b9fb-183">此外，若要在安全与合规中心创建导入作业，必须满足以下条件之一：</span><span class="sxs-lookup"><span data-stu-id="2b9fb-183">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="2b9fb-184">必须分配有 Exchange Onlin 中的“邮件收件人”角色。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-184">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="2b9fb-185">默认情况下，此角色分配给“组织管理和收件人管理”角色组。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-185">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>

    <span data-ttu-id="2b9fb-186">或</span><span class="sxs-lookup"><span data-stu-id="2b9fb-186">Or</span></span>
    
- <span data-ttu-id="2b9fb-187">必须是你组织中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-187">You have to be a global administrator in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="2b9fb-188">请考虑在 Exchange Online 中创建新角色组，此角色组专门用于将 PST 文件导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-188">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="2b9fb-189">若要获取导入 PST 文件所需的最低级别权限，请将“邮件导入导出和邮件收件人”角色分配给新角色组，然后添加成员。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-189">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="2b9fb-190">**网络上传在哪些地区提供？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-190">**Where is network upload available?**</span></span>
  
<span data-ttu-id="2b9fb-191">Network upload is currently available in these regions: United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, Australia, and United Arab Emirates (UAE).</span><span class="sxs-lookup"><span data-stu-id="2b9fb-191">Network upload is currently available in these regions: United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, Australia, and United Arab Emirates (UAE).</span></span> <span data-ttu-id="2b9fb-192">Network upload will be available in more regions soon.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-192">Network upload will be available in more regions soon.</span></span>

> [!NOTE]
> <span data-ttu-id="2b9fb-193">目前，不可在德国和瑞士使用 PST 文件的网络上传功能。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-193">At this time, network upload of PST files is not available in Germany and Switzerland.</span></span> <span data-ttu-id="2b9fb-194">当这些国家/地区提供网络上传功能后，此常见问题解答将更新。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-194">This FAQ will be updated when network upload is available in these countries.</span></span>
  
 <span data-ttu-id="2b9fb-195">**使用网络上传导入 PST 文件的定价如何？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-195">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="2b9fb-196">Using network upload to import PST files is free.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-196">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="2b9fb-197">这也意味着 PST 文件从 Azure 存储区域删除后，将不再显示在 Microsoft 365 管理中心已完成导入作业的文件列表中。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-197">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Microsoft 365 admin center.</span></span> <span data-ttu-id="2b9fb-198">虽然导入作业可能仍然列在“**将数据导入到 Office 365**”页面，但查看较早导入作业的详细信息时，PST 文件的列表可能为空。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-198">Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span>
  
 <span data-ttu-id="2b9fb-199">**哪个版本的 PST 文件格式支持导入到 Office 365？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-199">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="2b9fb-200">可选两个版本的 PST 文件格式：ANSI 和 Unicode。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-200">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="2b9fb-201">建议导入使用 Unicode PST 文件格式的文件。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-201">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="2b9fb-202">但是，采用 ANSI PST 文件格式的文件也可以导入到 Office 365，如语言采用双字节字符集 (DBCS) 的文件。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-202">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365.</span></span> <span data-ttu-id="2b9fb-203">有关导入 ANSI PST 文件的详细信息，请参阅[使用网络上传将 PST 文件导入到 Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074) 中的步骤 4。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-203">For more information about importing ANSI PST files, see Step 4 in [Use network upload to import PST files to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074).</span></span>
  
<span data-ttu-id="2b9fb-204">此外，来自 Outlook 2007 和更高版本 Outlook 的 PST 文件可导入到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-204">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="2b9fb-205">**将 PST 文件上传到 Azure 存储区域后，这些文件在删除前可在 Azure 中保留多长时间？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-205">**After I upload my PST files to the Azure Storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="2b9fb-206">使用网络上传的方法导入 PST 文件时，需要将它们上传到名为 **ingestiondata** 的 Azure Blob 容器。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-206">When you use the network upload method to import PST files, you upload them to an Azure blob container named **ingestiondata**.</span></span> <span data-ttu-id="2b9fb-207">如果安全与合规中心中的“**导入 PST 页面**”页面上没有正在进行的导入作业，则 Azure 中 **ingestiondata** 容器内的所有 PST 文件都会在安全与合规中心中创建最新导入作业 30 天后被删除。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-207">If there are no import jobs in progress on the **Import PST files** page in the Security & Compliance Center), then all PST files in the **ingestiondata** container in Azure are deleted 30 days after the most recent import job was created in the Security & Compliance Center.</span></span> <span data-ttu-id="2b9fb-208">这也意味着须在将 PST 文件上传到 Azure 后的 30 天内在安全与合规中心中创建新的导入作业（如网络上传说明的步骤 5 中所述）。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-208">That also means you have to create a new import job in the Security & Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span>
  
<span data-ttu-id="2b9fb-209">这也意味着 PST 文件从 Azure 存储区域删除后，将不再显示在安全与合规中心已完成导入作业的文件列表中。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-209">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="2b9fb-210">虽然导入作业可能仍然列在安全与合规中心的“**导入 PST 文件**”页面，但查看较早导入作业的详细信息时，PST 文件的列表可能为空。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-210">Although an import job might still be listed on the **Import PST files** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span>
  
 <span data-ttu-id="2b9fb-211">**将 PST 文件导入到邮箱需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-211">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="2b9fb-212">这取决于你的网络容量，但每 TB 数据通常需要几个小时才能上传到组织的 Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-212">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure Storage area for your organization.</span></span> <span data-ttu-id="2b9fb-213">PST 文件复制到 Azure 存储区域后，PST 文件将以每天至少 24 GB 的速度导入到 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-213">After the PST files are copied to the Azure Storage area, a PST file is imported to a Microsoft 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="2b9fb-214">如果此速度不满足你的需求，可能需要考虑采用其他方法将电子邮件数据导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-214">If this rate doesn't meet your needs, you might consider other methods to get email data into Office 365.</span></span> <span data-ttu-id="2b9fb-215">有关详细信息，请参阅[将多个电子邮件帐户迁移到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-215">For more information, see [Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
<span data-ttu-id="2b9fb-216">如果不同的 PST 文件导入到不同的目标邮箱中，则导入过程将以并行方式进行；也就是说，每个 PST/邮箱对是同时导入的。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-216">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="2b9fb-217">同样，如果多个 PST 文件导入到同一个邮箱中，也将同时导入这些文件。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-217">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="2b9fb-218">**PST 导入进程如何处理重复的电子邮件项？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-218">**How does the PST import process handle duplicate email items?**</span></span>

<span data-ttu-id="2b9fb-219">如果目标邮箱或目标存档的目标文件夹中存在匹配项，PST 导入进程将检查重复的项目，并且不会将邮件项从 PST 文件复制到邮箱或存档。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-219">The PST import process checks for duplicate items and doesn't copy the items from a PST file to the mailbox or archive if a matching item exists in the target folder in the target mailbox or target archive.</span></span> <span data-ttu-id="2b9fb-220">如果重新导入相同的 PST 文件并指定与上一个导入作业中指定的文件夹不同的目标文件夹（使用 PST 导入映射文件中的 TargetRootFolder 属性），将重新导入 PST 文件中的所有项。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-220">If you re-import the same PST file and specify a different target folder (using the TargetRootFolder property in the PST import mapping file) than the one you specified in a previous import job, all items in the PST file will be reimported.</span></span>
 
 <span data-ttu-id="2b9fb-221">**导入 PST 文件时是否有邮件大小限制？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-221">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="2b9fb-222">是。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-222">Yes.</span></span> <span data-ttu-id="2b9fb-223">如果 PST 文件包含大于 150 MB 的邮件项，则将在导入过程中跳过此项。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-223">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="2b9fb-224">**PST 文件导入到 Microsoft 365 邮箱时，是否会保留邮件发送时间或接收时间、收件人列表和其他邮件属性？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-224">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to a Microsoft 365 mailbox?**</span></span>
  
<span data-ttu-id="2b9fb-225">可以。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-225">Yes.</span></span> <span data-ttu-id="2b9fb-226">导入过程中不会更改任何原始邮件元数据。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-226">The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="2b9fb-227">**我想要导入邮箱的 PST 文件是否存在文件夹层次结构的级别数目限制？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-227">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="2b9fb-228">Yes.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-228">Yes.</span></span> <span data-ttu-id="2b9fb-229">You can't import a PST file that has 300 or more levels of nested folders.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-229">You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="2b9fb-230">**是否可以使用网络上传将 PST 文件导入到 Office 365 中的非活动邮箱？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-230">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="2b9fb-231">是的，这一功能现已推出。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-231">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="2b9fb-232">**是否可以使用网络上传将 PST 文件导入到 Exchange 混合部署中的联机存档邮箱？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-232">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="2b9fb-233">是的，这一功能现已推出。 </span><span class="sxs-lookup"><span data-stu-id="2b9fb-233">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="2b9fb-234">**是否可以使用网络上传将 PST 文件导入 Exchange Online 中的公用文件夹？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-234">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="2b9fb-235">否，无法将 PST 文件导入公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-235">No, you can't import PST files to public folders.</span></span>
  
### <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="2b9fb-236">使用驱动器寄送导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="2b9fb-236">Using drive shipping to import PST files</span></span>

 <span data-ttu-id="2b9fb-237">**在 Office 365 导入服务中创建导入作业需要哪些权限？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-237">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="2b9fb-238">必须分配有邮箱导入导出角色，才能将 PST 文件导入到 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-238">You have to be assigned the Mailbox Import Export role to import PST files to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="2b9fb-239">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-239">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="2b9fb-240">您可以向“组织管理”角色组添加“邮箱导入导出”角色。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-240">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="2b9fb-241">或者可以创建新的角色组，分配邮箱导入导出角色，然后将自己或其他用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-241">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="2b9fb-242">有关详细信息，请参阅[管理 Exchange Online 中的角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)中的“向角色组添加角色”或“创建角色组”部分。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-242">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="2b9fb-243">此外，若要在安全与合规中心创建导入作业，必须满足以下条件之一：</span><span class="sxs-lookup"><span data-stu-id="2b9fb-243">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="2b9fb-244">必须分配有 Exchange Onlin 中的“邮件收件人”角色。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-244">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="2b9fb-245">默认情况下，此角色分配给“组织管理和收件人管理”角色组。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-245">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="2b9fb-246">或</span><span class="sxs-lookup"><span data-stu-id="2b9fb-246">Or</span></span>
    
- <span data-ttu-id="2b9fb-247">必须是你组织中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-247">You have to be a global administrator in your organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="2b9fb-248">请考虑在 Exchange Online 中创建新角色组，此角色组专门用于将 PST 文件导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-248">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="2b9fb-249">若要获取导入 PST 文件所需的最低级别权限，请将“邮件导入导出和邮件收件人”角色分配给新角色组，然后添加成员。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-249">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="2b9fb-250">**哪些地区提供驱动器寄送服务？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-250">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="2b9fb-251">当前，美国、加拿大、巴西、英国、欧洲、印度、东亚地址、东南亚、日本、韩国和澳大利亚已推出驱动器传送。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-251">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia.</span></span> <span data-ttu-id="2b9fb-252">不久之后，还会有更多地区推出驱动器传送。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-252">Drive shipping will be available in more regions soon.</span></span>

> [!NOTE]
> <span data-ttu-id="2b9fb-253">目前，不可在德国和瑞士使用驱动器发运导入 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-253">At this time, drive shipping to import PST files is not available in Germany and Switzerland.</span></span> <span data-ttu-id="2b9fb-254">当这些国家/地区提供驱动器发运功能后，此常见问题解答将更新。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-254">This FAQ will be updated when drive shipping is available in these countries.</span></span>
  
 <span data-ttu-id="2b9fb-255">**哪些商业许可协议支持驱动器发运？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-255">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="2b9fb-256">驱动器传送可通过 Microsoft 企业协议 (EA) 将 PST 文件导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-256">Drive shipping to import PST files to Microsoft 365 is available through a Microsoft Enterprise Agreement (EA).</span></span> <span data-ttu-id="2b9fb-257">驱动器寄送不可通过 Microsoft 产品和服务协议 (MPSA) 实现。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-257">Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="2b9fb-258">**使用驱动器传送将 PST 文件导入到 Microsoft 365 的定价如何？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-258">**What is the pricing for using drive shipping to import PST files to Microsoft 365?**</span></span>
  
<span data-ttu-id="2b9fb-259">使用驱动器传送将 PST 文件导入到 Microsoft 365 邮箱的费用为每 GB 数据 2 美元。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-259">The cost to use drive shipping to import PST files to Microsoft 365 mailboxes is $2 USD per GB of data.</span></span> <span data-ttu-id="2b9fb-260">例如，如果发运的硬盘包含 1,000 GB (1 TB) 的 PST 文件，则费用为 2,000 美元。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-260">For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD.</span></span> <span data-ttu-id="2b9fb-261">您可以与合作伙伴共同协作来支付导入费用。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-261">You can work with a partner to pay the import fee.</span></span> <span data-ttu-id="2b9fb-262">有关查找合作伙伴的信息，请参阅[查找 Microsoft 合作伙伴或经销商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-262">For information about finding a partner, see [Find your Microsoft partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
  
 <span data-ttu-id="2b9fb-263">**哪类硬盘支持驱动器发运？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-263">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="2b9fb-264">仅支持将 2.5 英寸固态硬盘 (SSD) 或 2.5 英寸或 3.5 英寸 SATA II/III 内部硬盘与 Office 365 导入服务结合使用。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-264">Only 2.5 inch solid-state drives (SSDs) or 2.5 inch or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service.</span></span> <span data-ttu-id="2b9fb-265">可使用最多 10 TB 的硬盘。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-265">You can use hard drives up to 10 TB.</span></span> <span data-ttu-id="2b9fb-266">对于导入作业，仅将处理硬盘上的第一个数据卷。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-266">For import jobs, only the first data volume on the hard drive will be processed.</span></span> <span data-ttu-id="2b9fb-267">必须使用 NTFS 格式化数据卷。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-267">The data volume must be formatted with NTFS.</span></span> <span data-ttu-id="2b9fb-268">将数据复制到硬盘时，可使用 2.5 英寸 SSD 或 2.5 英寸或 3.5 英寸 SATA II/III 连接器直接连接硬盘，或可使用外部 2.5 英寸 SSD 或 2.5 英寸或 3.5 英寸 SATA II/III USB 适配器在外部连接硬盘。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-268">When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 inch or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 inch or 3.5 inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2b9fb-269">Office 365 导入服务中不支持内置 USB 适配器随附的外部硬盘。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-269">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service.</span></span> <span data-ttu-id="2b9fb-270">此外，无法使用外部硬盘盒内的磁盘。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-270">Additionally, the disk inside the casing of an external hard drive can't be used.</span></span> <span data-ttu-id="2b9fb-271">请不要发运外部硬盘。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-271">Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="2b9fb-272">**单个导入作业可以发运多少个硬盘？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-272">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="2b9fb-273">单个导入作业最多可以发运 10 个硬盘。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-273">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="2b9fb-274">**传送硬盘后，需要多长时间才能转到 Microsoft 数据中心？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-274">**After I ship my hard drive, how long does it take to get to the Microsoft datacenter?**</span></span>
  
<span data-ttu-id="2b9fb-275">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery).</span><span class="sxs-lookup"><span data-stu-id="2b9fb-275">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery).</span></span> <span data-ttu-id="2b9fb-276">With most shippers, you can use the tracking number to track the status of your delivery.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-276">With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="2b9fb-277">**硬盘驱动器到达 Microsoft 数据中心后，需要多久才能将 PST 文件上传到 Azure？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-277">**After my hard drive arrives at the Microsoft datacenter, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="2b9fb-278">Microsoft 数据中心收到你的硬盘后，需花 7 到 10 个工作日将 PST 文件上传到你组织的 Azure 存储位置。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-278">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Azure Storage location for your organization.</span></span> <span data-ttu-id="2b9fb-279">PST 文件将上传到名为 `ingestiondata` 的 Azure Blob 容器。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-279">The PST files will be uploaded to an Azure blob container named `ingestiondata`.</span></span> 
  
 <span data-ttu-id="2b9fb-280">**将 PST 文件导入到邮箱需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-280">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="2b9fb-281">将 PST 文件上传到 Azure 存储区域后，Microsoft 365 采用安全方式分析 PST 文件中的数据，确定 PST 文件中所含项目的存在时长以及各种邮件类型。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-281">After the PST files are uploaded to the Azure Storage area, Microsoft 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files.</span></span> <span data-ttu-id="2b9fb-282">分析完成后，可以选择将所有数据导入 PST 文件，或设置筛选器控制导入的数据。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-282">When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported.</span></span> <span data-ttu-id="2b9fb-283">开始导入作业后，PST 文件将以每天至少 24 GB 的速度导入到 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-283">After you start the import job, a PST file is imported to a Microsoft 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="2b9fb-284">如果此速度不能满足你的需求，可能需要考虑采用其他方法将电子邮件数据导入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-284">If this rate doesn't meet your needs, you might consider other methods to get email data into Microsoft 365.</span></span> <span data-ttu-id="2b9fb-285">有关详细信息，请参阅[将多个电子邮件帐户迁移到 Microsoft 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-285">For more information, see [Ways to migrate multiple email accounts to Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
<span data-ttu-id="2b9fb-286">如果不同的 PST 文件导入到不同的目标邮箱中，则导入过程将以并行方式进行；也就是说，每个 PST/邮箱对是同时导入的。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-286">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="2b9fb-287">同样，如果多个 PST 文件导入到同一个邮箱中，也将同时导入这些文件。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-287">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="2b9fb-288">**Microsoft 将 PST 文件上传到 Azure 后，这些文件在删除前可在 Azure 中保留多长时间？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-288">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="2b9fb-289">在安全与合规中心的“**导入 PST 文件**”页面上创建最新导入作业的 30 天后，将删除组织的 Azure 存储位置（位于名为 `ingestiondata` 的 Blob 容器中）内的所有 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-289">All PST files in the Azure Storage location for your organization (in blob container named `ingestiondata`), are deleted 30 days after the most recent import job was created on the **Import PST files** page in the Security & Compliance Center.</span></span> 
  
<span data-ttu-id="2b9fb-290">这也意味着 PST 文件从 Azure 存储区域删除后，将不再显示在安全与合规中心已完成导入作业的文件列表中。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-290">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="2b9fb-291">虽然导入作业可能仍然列在安全与合规中心的“**导入 PST 文件**”页面，但查看较早导入作业的详细信息时，PST 文件的列表可能为空。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-291">Although an import job might still be listed on the **Import PST files** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="2b9fb-292">**哪个版本的 PST 文件格式支持导入到 Microsoft 365？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-292">**What version of the PST file format is supported for importing to Microsoft 365?**</span></span>
  
<span data-ttu-id="2b9fb-293">可选两个版本的 PST 文件格式：ANSI 和 Unicode。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-293">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="2b9fb-294">建议导入使用 Unicode PST 文件格式的文件。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-294">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="2b9fb-295">但是，采用 ANSI PST 文件格式的文件也可以导入到 Microsoft 365，如语言采用双字节字符集 (DBCS) 的文件。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-295">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Microsoft 365.</span></span> <span data-ttu-id="2b9fb-296">有关导入 ANSI PST 文件的详细信息，请参阅[使用驱动器传送将组织的 PST 文件导入到 Microsoft 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file) 中的步骤 3。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-296">For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import your organization PST files to Microsoft 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="2b9fb-297">此外，来自 Outlook 2007 和更高版本 Outlook 的 PST 文件可导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-297">Additionally, PST files from Outlook 2007 and later versions can be imported to Microsoft 365.</span></span>
  
 <span data-ttu-id="2b9fb-298">**导入 PST 文件时是否有邮件大小限制？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-298">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="2b9fb-299">是。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-299">Yes.</span></span> <span data-ttu-id="2b9fb-300">如果 PST 文件包含大于 150 MB 的邮件项，则将在导入过程中跳过此项。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-300">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
  <span data-ttu-id="2b9fb-301">**PST 导入进程如何处理重复的电子邮件项？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-301">**How does the PST import process handle duplicate email items?**</span></span>

<span data-ttu-id="2b9fb-302">如果目标邮箱或目标存档的目标文件夹中存在匹配项，PST 导入进程将检查重复的项目，并且不会将邮件项从 PST 文件复制到邮箱或存档。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-302">The PST import process checks for duplicate items and doesn't copy the items from a PST file to the mailbox or archive if a matching item exists in the target folder in the target mailbox or target archive.</span></span> <span data-ttu-id="2b9fb-303">如果重新导入相同的 PST 文件并指定与上一个导入作业中指定的文件夹不同的目标文件夹（使用 PST 导入映射文件中的 TargetRootFolder 属性），将重新导入 PST 文件中的所有项。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-303">If you re-import the same PST file and specify a different target folder (using the TargetRootFolder property in the PST import mapping file) than the one you specified in a previous import job, all items in the PST file will be reimported.</span></span>
 
 <span data-ttu-id="2b9fb-304">**PST 文件导入到 Microsoft 365 邮箱时，是否会保留邮件发送时间或接收时间、收件人列表和其他邮件属性？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-304">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to a Microsoft 365 mailbox?**</span></span>
  
<span data-ttu-id="2b9fb-305">可以。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-305">Yes.</span></span> <span data-ttu-id="2b9fb-306">导入过程中不会更改原始邮件的元数据</span><span class="sxs-lookup"><span data-stu-id="2b9fb-306">The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="2b9fb-307">**我想要导入邮箱的 PST 文件是否存在文件夹层次结构的级别数目限制？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-307">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="2b9fb-308">Yes.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-308">Yes.</span></span> <span data-ttu-id="2b9fb-309">You can't import a PST file that has 300 or more levels of nested folders.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-309">You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="2b9fb-310">**是否可以使用驱动器传送将 PST 文件导入到 Microsoft 365 中的非活动邮箱？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-310">**Can I use drive shipping to import PST files to an inactive mailbox in Microsoft 365?**</span></span>
  
<span data-ttu-id="2b9fb-311">是的，这一功能现已推出。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-311">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="2b9fb-312">**是否可以使用驱动器发运将 PST 文件导入到 Exchange 混合部署中的联机存档邮箱？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-312">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="2b9fb-313">是的，这一功能现已推出。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-313">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="2b9fb-314">**是否可以使用驱动器发运将 PST 文件导入 Exchange Online 中的公用文件夹？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-314">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="2b9fb-315">否，无法将 PST 文件导入公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-315">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="2b9fb-316">**Microsoft 将硬盘运回给我之前，是否会进行擦除？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-316">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="2b9fb-317">No, Microsoft can't wipe hard drives before shipping them back to customers.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-317">No, Microsoft can't wipe hard drives before shipping them back to customers.</span></span> <span data-ttu-id="2b9fb-318">Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-318">Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="2b9fb-319">**Microsoft 是否会销毁我的硬盘，而不是寄回给我？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-319">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="2b9fb-320">No, Microsoft can't destroy your hard drive.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-320">No, Microsoft can't destroy your hard drive.</span></span> <span data-ttu-id="2b9fb-321">Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-321">Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="2b9fb-322">**寄回时支持哪些快递服务？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-322">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="2b9fb-323">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-323">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive.</span></span> <span data-ttu-id="2b9fb-324">For all other regions, Microsoft uses DHL.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-324">For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="2b9fb-325">**寄回的运费是多少？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-325">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="2b9fb-326">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-326">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to.</span></span> <span data-ttu-id="2b9fb-327">Microsoft will bill your FedEx or DHL account to return your hard drive.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-327">Microsoft will bill your FedEx or DHL account to return your hard drive.</span></span> <span data-ttu-id="2b9fb-328">The cost of return shipping is your responsibility.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-328">The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="2b9fb-329">**是否可以使用 FedEx Custom Shipping 等自定义快递运输服将我的硬盘寄送至 Microsoft？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-329">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="2b9fb-330">是。</span><span class="sxs-lookup"><span data-stu-id="2b9fb-330">Yes.</span></span>
  
 <span data-ttu-id="2b9fb-331">**如果我必须将我的硬盘发运到其他国家/地区，是否有任何需要执行的操作？**</span><span class="sxs-lookup"><span data-stu-id="2b9fb-331">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="2b9fb-332">The hard drive that you ship to Microsoft might have to cross international borders.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-332">The hard drive that you ship to Microsoft might have to cross international borders.</span></span> <span data-ttu-id="2b9fb-333">If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-333">If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws.</span></span> <span data-ttu-id="2b9fb-334">Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-334">Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center.</span></span> <span data-ttu-id="2b9fb-335">This will help to ensure that it reaches Microsoft in a timely manner.</span><span class="sxs-lookup"><span data-stu-id="2b9fb-335">This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
