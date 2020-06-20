---
title: 有关导入 PST 文件的常见问题解答
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
ms.custom: seo-marvel-apr2020
description: 本文包含有关使用 Office 365 导入服务将 PST 文件导入到 Microsoft 365 的一些常见问题的解答。
ms.openlocfilehash: 0f490b7bae3f462bb07725bf14453a6b9a4d7b9e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817731"
---
# <a name="faq-about-importing-pst-files"></a><span data-ttu-id="c8147-103">有关导入 PST 文件的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="c8147-103">FAQ about importing PST files</span></span>

<span data-ttu-id="c8147-104">**本文适用于管理员。是否要将 PST 文件导入到自己的邮箱？请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|</span><span class="sxs-lookup"><span data-stu-id="c8147-104">**This article is for administrators. Do you want to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|</span></span>
   
<span data-ttu-id="c8147-105">下面是一些有关使用 Office 365 导入服务将 PST 文件批量导入 Microsoft 365 邮箱的常见问题。</span><span class="sxs-lookup"><span data-stu-id="c8147-105">Here are some frequently asked questions about using the Office 365 Import Service to bulk-import PST files to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="c8147-106">有关如何导入 PST 文件的详细信息，请参阅[将 pst 文件导入到 Office 365 概述](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365)。</span><span class="sxs-lookup"><span data-stu-id="c8147-106">For more information about how to import PST files, see [Overview of importing PST files to Office 365](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365).</span></span>
  
## <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="c8147-107">使用网络上传导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="c8147-107">Using network upload to import PST files</span></span>

<span data-ttu-id="c8147-108">有关分步说明，请参阅[使用网络上载将 PST 文件导入到 Office 365](use-network-upload-to-import-pst-files.md)。</span><span class="sxs-lookup"><span data-stu-id="c8147-108">For step-by-step instructions, see [Use network upload to import PST files to Office 365](use-network-upload-to-import-pst-files.md).</span></span>
  
 <span data-ttu-id="c8147-109">**在 Office 365 导入服务中创建导入作业需要哪些权限？**</span><span class="sxs-lookup"><span data-stu-id="c8147-109">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="c8147-110">必须分配有 Exchange Online 中的邮箱导入导出角色，才能将 PST 文件导入到 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="c8147-110">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="c8147-111">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="c8147-111">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="c8147-112">您可以向“组织管理”角色组添加“邮箱导入导出”角色。</span><span class="sxs-lookup"><span data-stu-id="c8147-112">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="c8147-113">或者可以创建新的角色组，分配邮箱导入导出角色，然后将自己或其他用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="c8147-113">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="c8147-114">有关详细信息，请参阅[管理 Exchange Online 中的角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)中的“向角色组添加角色”或“创建角色组”部分。</span><span class="sxs-lookup"><span data-stu-id="c8147-114">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="c8147-115">此外，若要在安全与合规中心创建导入作业，必须满足以下条件之一：</span><span class="sxs-lookup"><span data-stu-id="c8147-115">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="c8147-116">必须分配有 Exchange Onlin 中的“邮件收件人”角色。</span><span class="sxs-lookup"><span data-stu-id="c8147-116">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="c8147-117">默认情况下，此角色分配给“组织管理和收件人管理”角色组。</span><span class="sxs-lookup"><span data-stu-id="c8147-117">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="c8147-118">或</span><span class="sxs-lookup"><span data-stu-id="c8147-118">Or</span></span>
    
- <span data-ttu-id="c8147-119">必须是你组织中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="c8147-119">You have to be a global administrator in your organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="c8147-120">请考虑在 Exchange Online 中创建新角色组，此角色组专门用于将 PST 文件导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c8147-120">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="c8147-121">若要获取导入 PST 文件所需的最低级别权限，请将“邮件导入导出和邮件收件人”角色分配给新角色组，然后添加成员。</span><span class="sxs-lookup"><span data-stu-id="c8147-121">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="c8147-122">**网络上传在哪些地区提供？**</span><span class="sxs-lookup"><span data-stu-id="c8147-122">**Where is network upload available?**</span></span>
  
<span data-ttu-id="c8147-123">网络上传目前在以下地区可用：美国、加拿大、巴西、英国、法国、欧洲、印度、东亚、东南亚、日本、韩国、澳大利亚和阿拉伯联合酋长国（UAE）。</span><span class="sxs-lookup"><span data-stu-id="c8147-123">Network upload is currently available in these regions: United States, Canada, Brazil, the United Kingdom, France, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, Australia, and United Arab Emirates (UAE).</span></span> <span data-ttu-id="c8147-124">Network upload will be available in more regions soon.</span><span class="sxs-lookup"><span data-stu-id="c8147-124">Network upload will be available in more regions soon.</span></span>

> [!NOTE]
> <span data-ttu-id="c8147-125">目前，不可在德国和瑞士使用 PST 文件的网络上传功能。</span><span class="sxs-lookup"><span data-stu-id="c8147-125">At this time, network upload of PST files is not available in Germany and Switzerland.</span></span> <span data-ttu-id="c8147-126">当这些国家/地区提供网络上传功能后，此常见问题解答将更新。</span><span class="sxs-lookup"><span data-stu-id="c8147-126">This FAQ will be updated when network upload is available in these countries.</span></span>
  
 <span data-ttu-id="c8147-127">**使用网络上传导入 PST 文件的定价如何？**</span><span class="sxs-lookup"><span data-stu-id="c8147-127">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="c8147-128">Using network upload to import PST files is free.</span><span class="sxs-lookup"><span data-stu-id="c8147-128">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="c8147-129">这也意味着 PST 文件从 Azure 存储区域删除后，将不再显示在 Microsoft 365 管理中心已完成导入作业的文件列表中。</span><span class="sxs-lookup"><span data-stu-id="c8147-129">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c8147-130">虽然导入作业可能仍然列在“**将数据导入到 Office 365**”页面，但查看较早导入作业的详细信息时，PST 文件的列表可能为空。</span><span class="sxs-lookup"><span data-stu-id="c8147-130">Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="c8147-131">**哪个版本的 PST 文件格式支持导入到 Office 365？**</span><span class="sxs-lookup"><span data-stu-id="c8147-131">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="c8147-132">可选两个版本的 PST 文件格式：ANSI 和 Unicode。</span><span class="sxs-lookup"><span data-stu-id="c8147-132">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="c8147-133">建议导入使用 Unicode PST 文件格式的文件。</span><span class="sxs-lookup"><span data-stu-id="c8147-133">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="c8147-134">但是，采用 ANSI PST 文件格式的文件也可以导入到 Office 365，如语言采用双字节字符集 (DBCS) 的文件。</span><span class="sxs-lookup"><span data-stu-id="c8147-134">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365.</span></span> <span data-ttu-id="c8147-135">有关导入 ANSI PST 文件的详细信息，请参阅 "[使用网络上载将组织的 PST 文件导入到 Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)" 中的步骤4。</span><span class="sxs-lookup"><span data-stu-id="c8147-135">For more information about importing ANSI PST files, see Step 4 in [Use network upload to import your organization's PST files to Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="c8147-136">此外，来自 Outlook 2007 和更高版本 Outlook 的 PST 文件可导入到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c8147-136">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="c8147-137">**将 PST 文件上传到 Azure 存储区域后，这些文件在删除前可在 Azure 中保留多长时间？**</span><span class="sxs-lookup"><span data-stu-id="c8147-137">**After I upload my PST files to the Azure Storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="c8147-138">使用网络上传的方法导入 PST 文件时，需要将它们上传到名为 **ingestiondata** 的 Azure Blob 容器。</span><span class="sxs-lookup"><span data-stu-id="c8147-138">When you use the network upload method to import PST files, you upload them to an Azure blob container named **ingestiondata**.</span></span> <span data-ttu-id="c8147-139">如果安全与合规中心中的“**导入 PST 页面**”页面上没有正在进行的导入作业，则 Azure 中 **ingestiondata** 容器内的所有 PST 文件都会在安全与合规中心中创建最新导入作业 30 天后被删除。</span><span class="sxs-lookup"><span data-stu-id="c8147-139">If there are no import jobs in progress on the **Import PST files** page in the Security & Compliance Center), then all PST files in the **ingestiondata** container in Azure are deleted 30 days after the most recent import job was created in the Security & Compliance Center.</span></span> <span data-ttu-id="c8147-140">这也意味着须在将 PST 文件上传到 Azure 后的 30 天内在安全与合规中心中创建新的导入作业（如网络上传说明的步骤 5 中所述）。</span><span class="sxs-lookup"><span data-stu-id="c8147-140">That also means you have to create a new import job in the Security & Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span> 
  
<span data-ttu-id="c8147-141">这也意味着 PST 文件从 Azure 存储区域删除后，将不再显示在安全与合规中心已完成导入作业的文件列表中。</span><span class="sxs-lookup"><span data-stu-id="c8147-141">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="c8147-142">虽然导入作业可能仍然列在安全与合规中心的“**导入 PST 文件**”页面，但查看较早导入作业的详细信息时，PST 文件的列表可能为空。</span><span class="sxs-lookup"><span data-stu-id="c8147-142">Although an import job might still be listed on the **Import PST files** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="c8147-143">**将 PST 文件导入到邮箱需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="c8147-143">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="c8147-144">这取决于你的网络容量，但每 TB 数据通常需要几个小时才能上传到组织的 Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="c8147-144">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure Storage area for your organization.</span></span> <span data-ttu-id="c8147-145">PST 文件复制到 Azure 存储区域后，PST 文件将以每天至少 24 GB 的速度导入到 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="c8147-145">After the PST files are copied to the Azure Storage area, a PST file is imported to a Microsoft 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="c8147-146">如果此速度不满足你的需求，可能需要考虑采用其他方法将电子邮件数据迁移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c8147-146">If this rate doesn't meet your needs, you might consider other methods for migrating email data to Office 365.</span></span> <span data-ttu-id="c8147-147">有关详细信息，请参阅[将多个电子邮件帐户迁移到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)。</span><span class="sxs-lookup"><span data-stu-id="c8147-147">For more information, see [Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
<span data-ttu-id="c8147-148">如果不同的 PST 文件导入到不同的目标邮箱中，则导入过程将以并行方式进行；也就是说，每个 PST/邮箱对是同时导入的。</span><span class="sxs-lookup"><span data-stu-id="c8147-148">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="c8147-149">同样，如果多个 PST 文件导入到同一个邮箱中，也将同时导入这些文件。</span><span class="sxs-lookup"><span data-stu-id="c8147-149">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="c8147-150">**PST 导入进程如何处理重复的电子邮件项？**</span><span class="sxs-lookup"><span data-stu-id="c8147-150">**How does the PST import process handle duplicate email items?**</span></span>

<span data-ttu-id="c8147-151">如果目标邮箱或目标存档的目标文件夹中存在匹配项，PST 导入进程将检查重复的项目，并且不会将邮件项从 PST 文件复制到邮箱或存档。</span><span class="sxs-lookup"><span data-stu-id="c8147-151">The PST import process checks for duplicate items and doesn't copy the items from a PST file to the mailbox or archive if a matching item exists in the target folder in the target mailbox or target archive.</span></span> <span data-ttu-id="c8147-152">如果重新导入相同的 PST 文件并指定与上一个导入作业中指定的文件夹不同的目标文件夹（使用 PST 导入映射文件中的 TargetRootFolder 属性），将重新导入 PST 文件中的所有项。</span><span class="sxs-lookup"><span data-stu-id="c8147-152">If you re-import the same PST file and specify a different target folder (using the TargetRootFolder property in the PST import mapping file) than the one you specified in a previous import job, all items in the PST file will be reimported.</span></span>

 <span data-ttu-id="c8147-153">**导入 PST 文件时是否有邮件大小限制？**</span><span class="sxs-lookup"><span data-stu-id="c8147-153">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="c8147-154">是。</span><span class="sxs-lookup"><span data-stu-id="c8147-154">Yes.</span></span> <span data-ttu-id="c8147-155">如果 PST 文件包含大于 150 MB 的邮件项，则将在导入过程中跳过此项。</span><span class="sxs-lookup"><span data-stu-id="c8147-155">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="c8147-156">**PST 文件导入到 Microsoft 365 邮箱时，是否会保留邮件发送时间或接收时间、收件人列表和其他邮件属性？**</span><span class="sxs-lookup"><span data-stu-id="c8147-156">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to a Microsoft 365 mailbox?**</span></span>
  
<span data-ttu-id="c8147-157">可以。</span><span class="sxs-lookup"><span data-stu-id="c8147-157">Yes.</span></span> <span data-ttu-id="c8147-158">导入过程中不会更改任何原始邮件元数据。</span><span class="sxs-lookup"><span data-stu-id="c8147-158">The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="c8147-159">**我想要导入邮箱的 PST 文件是否存在文件夹层次结构的级别数目限制？**</span><span class="sxs-lookup"><span data-stu-id="c8147-159">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="c8147-160">Yes.</span><span class="sxs-lookup"><span data-stu-id="c8147-160">Yes.</span></span> <span data-ttu-id="c8147-161">You can't import a PST file that has 300 or more levels of nested folders.</span><span class="sxs-lookup"><span data-stu-id="c8147-161">You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="c8147-162">**是否可以使用网络上传将 PST 文件导入到 Office 365 中的非活动邮箱？**</span><span class="sxs-lookup"><span data-stu-id="c8147-162">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="c8147-163">是的，这一功能现已推出。</span><span class="sxs-lookup"><span data-stu-id="c8147-163">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="c8147-164">**是否可以使用网络上传将 PST 文件导入到 Exchange 混合部署中的联机存档邮箱？**</span><span class="sxs-lookup"><span data-stu-id="c8147-164">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="c8147-165">是的，这一功能现已推出。 </span><span class="sxs-lookup"><span data-stu-id="c8147-165">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="c8147-166">**是否可以使用网络上传将 PST 文件导入 Exchange Online 中的公用文件夹？**</span><span class="sxs-lookup"><span data-stu-id="c8147-166">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="c8147-167">否，无法将 PST 文件导入公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="c8147-167">No, you can't import PST files to public folders.</span></span>
  
## <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="c8147-168">使用驱动器寄送导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="c8147-168">Using drive shipping to import PST files</span></span>

<span data-ttu-id="c8147-169">有关分步说明，请参阅[使用驱动器发货将 PST 文件导入到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="c8147-169">For step-by-step instructions, see [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).</span></span>
  
 <span data-ttu-id="c8147-170">**在 Office 365 导入服务中创建导入作业需要哪些权限？**</span><span class="sxs-lookup"><span data-stu-id="c8147-170">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="c8147-171">必须分配有邮箱导入导出角色，才能将 PST 文件导入到 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="c8147-171">You have to be assigned the Mailbox Import Export role to import PST files to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="c8147-172">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="c8147-172">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="c8147-173">您可以向“组织管理”角色组添加“邮箱导入导出”角色。</span><span class="sxs-lookup"><span data-stu-id="c8147-173">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="c8147-174">或者可以创建新的角色组，分配邮箱导入导出角色，然后将自己或其他用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="c8147-174">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="c8147-175">有关详细信息，请参阅[管理 Exchange Online 中的角色组](https://go.microsoft.com/fwlink/p/?LinkId=730688)中的“向角色组添加角色”或“创建角色组”部分。</span><span class="sxs-lookup"><span data-stu-id="c8147-175">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="c8147-176">此外，若要在安全与合规中心创建导入作业，必须满足以下条件之一：</span><span class="sxs-lookup"><span data-stu-id="c8147-176">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="c8147-177">必须分配有 Exchange Onlin 中的“邮件收件人”角色。</span><span class="sxs-lookup"><span data-stu-id="c8147-177">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="c8147-178">默认情况下，此角色分配给“组织管理和收件人管理”角色组。</span><span class="sxs-lookup"><span data-stu-id="c8147-178">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="c8147-179">或</span><span class="sxs-lookup"><span data-stu-id="c8147-179">Or</span></span>
    
- <span data-ttu-id="c8147-180">必须是你组织中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="c8147-180">You have to be a global administrator in your organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="c8147-181">请考虑在 Exchange Online 中创建新角色组，此角色组专门用于将 PST 文件导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c8147-181">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="c8147-182">若要获取导入 PST 文件所需的最低级别权限，请将“邮件导入导出和邮件收件人”角色分配给新角色组，然后添加成员。</span><span class="sxs-lookup"><span data-stu-id="c8147-182">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="c8147-183">**哪些地区提供驱动器寄送服务？**</span><span class="sxs-lookup"><span data-stu-id="c8147-183">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="c8147-184">当前，美国、加拿大、巴西、英国、欧洲、印度、东亚地址、东南亚、日本、韩国和澳大利亚已推出驱动器传送。</span><span class="sxs-lookup"><span data-stu-id="c8147-184">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia.</span></span> <span data-ttu-id="c8147-185">不久之后，还会有更多地区推出驱动器传送。</span><span class="sxs-lookup"><span data-stu-id="c8147-185">Drive shipping will be available in more regions soon.</span></span>

> [!NOTE]
> <span data-ttu-id="c8147-186">目前，不可在德国和瑞士使用驱动器发运导入 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="c8147-186">At this time, drive shipping to import PST files is not available in Germany and Switzerland.</span></span> <span data-ttu-id="c8147-187">当这些国家/地区提供驱动器发运功能后，此常见问题解答将更新。</span><span class="sxs-lookup"><span data-stu-id="c8147-187">This FAQ will be updated when drive shipping is available in these countries.</span></span>
  
 <span data-ttu-id="c8147-188">**哪些商业许可协议支持驱动器发运？**</span><span class="sxs-lookup"><span data-stu-id="c8147-188">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="c8147-189">驱动器传送可通过 Microsoft 企业协议 (EA) 将 PST 文件导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="c8147-189">Drive shipping to import PST files to Microsoft 365 is available through a Microsoft Enterprise Agreement (EA).</span></span> <span data-ttu-id="c8147-190">驱动器寄送不可通过 Microsoft 产品和服务协议 (MPSA) 实现。</span><span class="sxs-lookup"><span data-stu-id="c8147-190">Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="c8147-191">**使用驱动器传送将 PST 文件导入到 Microsoft 365 的定价如何？**</span><span class="sxs-lookup"><span data-stu-id="c8147-191">**What is the pricing for using drive shipping to import PST files to Microsoft 365?**</span></span>
  
<span data-ttu-id="c8147-192">使用驱动器传送将 PST 文件导入到 Microsoft 365 邮箱的费用为每 GB 数据 2 美元。</span><span class="sxs-lookup"><span data-stu-id="c8147-192">The cost to use drive shipping to import PST files to Microsoft 365 mailboxes is $2 USD per GB of data.</span></span> <span data-ttu-id="c8147-193">例如，如果发运的硬盘包含 1,000 GB (1 TB) 的 PST 文件，则费用为 2,000 美元。</span><span class="sxs-lookup"><span data-stu-id="c8147-193">For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD.</span></span> <span data-ttu-id="c8147-194">您可以与合作伙伴共同协作来支付导入费用。</span><span class="sxs-lookup"><span data-stu-id="c8147-194">You can work with a partner to pay the import fee.</span></span> <span data-ttu-id="c8147-195">有关查找合作伙伴的信息，请参阅[查找 Microsoft 合作伙伴或经销商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。</span><span class="sxs-lookup"><span data-stu-id="c8147-195">For information about finding a partner, see [Find your Microsoft partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
  
 <span data-ttu-id="c8147-196">**哪类硬盘支持驱动器发运？**</span><span class="sxs-lookup"><span data-stu-id="c8147-196">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="c8147-197">仅支持将 2.5 英寸固态硬盘 (SSD) 或 2.5 或 3.5 英寸 SATA II/III 内部硬盘与 Office 365 导入服务结合使用。</span><span class="sxs-lookup"><span data-stu-id="c8147-197">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service.</span></span> <span data-ttu-id="c8147-198">可使用最多 10 TB 的硬盘。</span><span class="sxs-lookup"><span data-stu-id="c8147-198">You can use hard drives up to 10 TB.</span></span> <span data-ttu-id="c8147-199">对于导入作业，仅将处理硬盘上的第一个数据卷。</span><span class="sxs-lookup"><span data-stu-id="c8147-199">For import jobs, only the first data volume on the hard drive will be processed.</span></span> <span data-ttu-id="c8147-200">必须使用 NTFS 格式化数据卷。</span><span class="sxs-lookup"><span data-stu-id="c8147-200">The data volume must be formatted with NTFS.</span></span> <span data-ttu-id="c8147-201">将数据复制到硬盘时，可使用 2.5 英寸 SSD 或 2.5 或 3.5 英寸 SATA II/III 连接器直接连接，或可使用外部 2.5 英寸 SSD 或 2.5 或 3.5 英寸 SATA II/III USB 适配器在外部将其连接。</span><span class="sxs-lookup"><span data-stu-id="c8147-201">When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c8147-202">Office 365 导入服务中不支持内置 USB 适配器随附的外部硬盘。</span><span class="sxs-lookup"><span data-stu-id="c8147-202">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service.</span></span> <span data-ttu-id="c8147-203">此外，无法使用外部硬盘盒内的磁盘。</span><span class="sxs-lookup"><span data-stu-id="c8147-203">Additionally, the disk inside the casing of an external hard drive can't be used.</span></span> <span data-ttu-id="c8147-204">请不要发运外部硬盘。</span><span class="sxs-lookup"><span data-stu-id="c8147-204">Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="c8147-205">**单个导入作业可以发运多少个硬盘？**</span><span class="sxs-lookup"><span data-stu-id="c8147-205">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="c8147-206">单个导入作业最多可以发运 10 个硬盘。</span><span class="sxs-lookup"><span data-stu-id="c8147-206">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="c8147-207">**发运硬盘后，需要多长时间才能转到 Microsoft 数据中心？**</span><span class="sxs-lookup"><span data-stu-id="c8147-207">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span></span>
  
<span data-ttu-id="c8147-208">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery).</span><span class="sxs-lookup"><span data-stu-id="c8147-208">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery).</span></span> <span data-ttu-id="c8147-209">With most shippers, you can use the tracking number to track the status of your delivery.</span><span class="sxs-lookup"><span data-stu-id="c8147-209">With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="c8147-210">**硬盘驱动器到达 Microsoft 数据中心后，需要多久才能将 PST文件上传到 Azure？**</span><span class="sxs-lookup"><span data-stu-id="c8147-210">**After my hard drive arrives at the Microsoft data center, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="c8147-211">在 Microsoft 数据中心收到硬盘驱动器后，需要7到10个工作日才能将 PST 文件上传到组织的 Azure 存储区。</span><span class="sxs-lookup"><span data-stu-id="c8147-211">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Azure Storage area for your organization.</span></span> <span data-ttu-id="c8147-212">PST 文件将被上传到名为**ingestiondata**的 Azure blob 容器中。</span><span class="sxs-lookup"><span data-stu-id="c8147-212">The PST files will be uploaded to an Azure blob container named **ingestiondata**.</span></span> 
  
 <span data-ttu-id="c8147-213">**将 PST 文件导入到邮箱需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="c8147-213">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="c8147-214">将 PST 文件上传到 Azure 存储区域后，Microsoft 365 采用安全方式分析 PST 文件中的数据，确定 PST 文件中所含项目的存在时长以及各种邮件类型。</span><span class="sxs-lookup"><span data-stu-id="c8147-214">After the PST files are uploaded to the Azure Storage area, Microsoft 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files.</span></span> <span data-ttu-id="c8147-215">分析完成后，可以选择将所有数据导入 PST 文件，或设置筛选器控制导入的数据。</span><span class="sxs-lookup"><span data-stu-id="c8147-215">When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported.</span></span> <span data-ttu-id="c8147-216">开始导入作业后，PST 文件将以每天至少 24 GB 的速度导入到 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="c8147-216">After you start the import job, a PST file is imported to a Microsoft 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="c8147-217">如果此速度不满足你的需求，可能需要考虑采用其他方法将电子邮件数据导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c8147-217">If this rate doesn't meet your needs, you might consider other methods for importing email data to Office 365.</span></span> <span data-ttu-id="c8147-218">有关详细信息，请参阅[将多个电子邮件帐户迁移到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)。</span><span class="sxs-lookup"><span data-stu-id="c8147-218">For more information, see [Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
<span data-ttu-id="c8147-219">如果不同的 PST 文件导入到不同的目标邮箱中，则导入过程将以并行方式进行；也就是说，每个 PST/邮箱对是同时导入的。</span><span class="sxs-lookup"><span data-stu-id="c8147-219">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="c8147-220">同样，如果多个 PST 文件导入到同一个邮箱中，也将同时导入这些文件。</span><span class="sxs-lookup"><span data-stu-id="c8147-220">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="c8147-221">**Microsoft 将 PST 文件上传到 Azure 后，这些文件在删除前可在 Azure 中保留多长时间？**</span><span class="sxs-lookup"><span data-stu-id="c8147-221">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="c8147-222">在安全 & 合规中心的 "**导入 PST 文件**" 页上创建最近的导入作业之后30天内，将删除您的组织的 Azure 存储位置中的所有 PST 文件（在 blob 容器中名为**ingestiondata**）。</span><span class="sxs-lookup"><span data-stu-id="c8147-222">All PST files in the Azure Storage location for your organization (in blob container named **ingestiondata**), are deleted 30 days after the most recent import job was created on the **Import PST files** page in the Security & Compliance Center.</span></span> 
  
<span data-ttu-id="c8147-223">这也意味着 PST 文件从 Azure 存储区域删除后，将不再显示在安全与合规中心已完成导入作业的文件列表中。</span><span class="sxs-lookup"><span data-stu-id="c8147-223">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="c8147-224">虽然导入作业可能仍然列在安全与合规中心的“**导入 PST 文件**”页面，但查看较早导入作业的详细信息时，PST 文件的列表可能为空。</span><span class="sxs-lookup"><span data-stu-id="c8147-224">Although an import job might still be listed on the **Import PST files** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="c8147-225">**哪个版本的 PST 文件格式支持导入到 Microsoft 365？**</span><span class="sxs-lookup"><span data-stu-id="c8147-225">**What version of the PST file format is supported for importing to Microsoft 365?**</span></span>
  
<span data-ttu-id="c8147-226">可选两个版本的 PST 文件格式：ANSI 和 Unicode。</span><span class="sxs-lookup"><span data-stu-id="c8147-226">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="c8147-227">建议导入使用 Unicode PST 文件格式的文件。</span><span class="sxs-lookup"><span data-stu-id="c8147-227">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="c8147-228">但是，采用 ANSI PST 文件格式的文件也可以导入到 Microsoft 365，如语言采用双字节字符集 (DBCS) 的文件。</span><span class="sxs-lookup"><span data-stu-id="c8147-228">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Microsoft 365.</span></span> <span data-ttu-id="c8147-229">有关导入 ANSI PST 文件的详细信息，请参阅 "[使用驱动器传送将 PST 文件导入到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)" 中的步骤3。</span><span class="sxs-lookup"><span data-stu-id="c8147-229">For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="c8147-230">此外，来自 Outlook 2007 和更高版本 Outlook 的 PST 文件可导入到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="c8147-230">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="c8147-231">**导入 PST 文件时是否有邮件大小限制？**</span><span class="sxs-lookup"><span data-stu-id="c8147-231">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="c8147-232">是。</span><span class="sxs-lookup"><span data-stu-id="c8147-232">Yes.</span></span> <span data-ttu-id="c8147-233">如果 PST 文件包含大于 150 MB 的邮件项，则将在导入过程中跳过此项。</span><span class="sxs-lookup"><span data-stu-id="c8147-233">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
  <span data-ttu-id="c8147-234">**PST 导入进程如何处理重复的电子邮件项？**</span><span class="sxs-lookup"><span data-stu-id="c8147-234">**How does the PST import process handle duplicate email items?**</span></span>

<span data-ttu-id="c8147-235">如果目标邮箱或目标存档的目标文件夹中存在匹配项，PST 导入进程将检查重复的项目，并且不会将邮件项从 PST 文件复制到邮箱或存档。</span><span class="sxs-lookup"><span data-stu-id="c8147-235">The PST import process checks for duplicate items and doesn't copy the items from a PST file to the mailbox or archive if a matching item exists in the target folder in the target mailbox or target archive.</span></span> <span data-ttu-id="c8147-236">如果重新导入相同的 PST 文件并指定与上一个导入作业中指定的文件夹不同的目标文件夹（使用 PST 导入映射文件中的 TargetRootFolder 属性），将重新导入 PST 文件中的所有项。</span><span class="sxs-lookup"><span data-stu-id="c8147-236">If you re-import the same PST file and specify a different target folder (using the TargetRootFolder property in the PST import mapping file) than the one you specified in a previous import job, all items in the PST file will be reimported.</span></span>
 
 <span data-ttu-id="c8147-237">**PST 文件导入到 Microsoft 365 邮箱时，是否会保留邮件发送时间或接收时间、收件人列表和其他邮件属性？**</span><span class="sxs-lookup"><span data-stu-id="c8147-237">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to a Microsoft 365 mailbox?**</span></span>
  
<span data-ttu-id="c8147-238">可以。</span><span class="sxs-lookup"><span data-stu-id="c8147-238">Yes.</span></span> <span data-ttu-id="c8147-239">导入过程中不会更改原始邮件的元数据</span><span class="sxs-lookup"><span data-stu-id="c8147-239">The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="c8147-240">**我想要导入邮箱的 PST 文件是否存在文件夹层次结构的级别数目限制？**</span><span class="sxs-lookup"><span data-stu-id="c8147-240">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="c8147-241">Yes.</span><span class="sxs-lookup"><span data-stu-id="c8147-241">Yes.</span></span> <span data-ttu-id="c8147-242">You can't import a PST file that has 300 or more levels of nested folders.</span><span class="sxs-lookup"><span data-stu-id="c8147-242">You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="c8147-243">**是否可以使用驱动器传送将 PST 文件导入到 Microsoft 365 中的非活动邮箱？**</span><span class="sxs-lookup"><span data-stu-id="c8147-243">**Can I use drive shipping to import PST files to an inactive mailbox in Microsoft 365?**</span></span>
  
<span data-ttu-id="c8147-244">是的，这一功能现已推出。</span><span class="sxs-lookup"><span data-stu-id="c8147-244">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="c8147-245">**是否可以使用驱动器发运将 PST 文件导入到 Exchange 混合部署中的联机存档邮箱？**</span><span class="sxs-lookup"><span data-stu-id="c8147-245">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="c8147-246">是的，这一功能现已推出。</span><span class="sxs-lookup"><span data-stu-id="c8147-246">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="c8147-247">**是否可以使用驱动器发运将 PST 文件导入 Exchange Online 中的公用文件夹？**</span><span class="sxs-lookup"><span data-stu-id="c8147-247">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="c8147-248">否，无法将 PST 文件导入公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="c8147-248">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="c8147-249">**Microsoft 将硬盘运回给我之前，是否会进行擦除？**</span><span class="sxs-lookup"><span data-stu-id="c8147-249">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="c8147-250">No, Microsoft can't wipe hard drives before shipping them back to customers.</span><span class="sxs-lookup"><span data-stu-id="c8147-250">No, Microsoft can't wipe hard drives before shipping them back to customers.</span></span> <span data-ttu-id="c8147-251">Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c8147-251">Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="c8147-252">**Microsoft 是否会销毁我的硬盘，而不是寄回给我？**</span><span class="sxs-lookup"><span data-stu-id="c8147-252">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="c8147-253">No, Microsoft can't destroy your hard drive.</span><span class="sxs-lookup"><span data-stu-id="c8147-253">No, Microsoft can't destroy your hard drive.</span></span> <span data-ttu-id="c8147-254">Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c8147-254">Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="c8147-255">**寄回时支持哪些快递服务？**</span><span class="sxs-lookup"><span data-stu-id="c8147-255">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="c8147-256">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive.</span><span class="sxs-lookup"><span data-stu-id="c8147-256">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive.</span></span> <span data-ttu-id="c8147-257">For all other regions, Microsoft uses DHL.</span><span class="sxs-lookup"><span data-stu-id="c8147-257">For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="c8147-258">**寄回的运费是多少？**</span><span class="sxs-lookup"><span data-stu-id="c8147-258">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="c8147-259">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to.</span><span class="sxs-lookup"><span data-stu-id="c8147-259">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to.</span></span> <span data-ttu-id="c8147-260">Microsoft will bill your FedEx or DHL account to return your hard drive.</span><span class="sxs-lookup"><span data-stu-id="c8147-260">Microsoft will bill your FedEx or DHL account to return your hard drive.</span></span> <span data-ttu-id="c8147-261">The cost of return shipping is your responsibility.</span><span class="sxs-lookup"><span data-stu-id="c8147-261">The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="c8147-262">**是否可以使用 FedEx Custom Shipping 等自定义快递运输服将我的硬盘寄送至 Microsoft？**</span><span class="sxs-lookup"><span data-stu-id="c8147-262">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="c8147-263">是。</span><span class="sxs-lookup"><span data-stu-id="c8147-263">Yes.</span></span>
  
 <span data-ttu-id="c8147-264">**如果我必须将我的硬盘发运到其他国家/地区，是否有任何需要执行的操作？**</span><span class="sxs-lookup"><span data-stu-id="c8147-264">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="c8147-265">The hard drive that you ship to Microsoft might have to cross international borders.</span><span class="sxs-lookup"><span data-stu-id="c8147-265">The hard drive that you ship to Microsoft might have to cross international borders.</span></span> <span data-ttu-id="c8147-266">If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws.</span><span class="sxs-lookup"><span data-stu-id="c8147-266">If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws.</span></span> <span data-ttu-id="c8147-267">Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center.</span><span class="sxs-lookup"><span data-stu-id="c8147-267">Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center.</span></span> <span data-ttu-id="c8147-268">This will help to ensure that it reaches Microsoft in a timely manner.</span><span class="sxs-lookup"><span data-stu-id="c8147-268">This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
