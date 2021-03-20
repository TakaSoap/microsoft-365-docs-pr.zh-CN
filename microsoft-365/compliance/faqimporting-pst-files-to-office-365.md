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
description: 本文包含管理员有关使用 Office 365 导入服务将 PST 文件导入到 Microsoft 365 的一些常见问题的解答。
ms.openlocfilehash: adcc84df7aed25f0d51c8fb6a1899bfa56453854
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906786"
---
# <a name="faq-about-importing-pst-files"></a><span data-ttu-id="f1141-103">有关导入 PST 文件的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="f1141-103">FAQ about importing PST files</span></span>

<span data-ttu-id="f1141-104">**本文适用于管理员。是否要将 PST 文件导入到您自己的邮箱？请参阅 [从 Outlook .pst](https://go.microsoft.com/fwlink/p/?LinkID=785075)文件导入电子邮件、联系人和日历**</span><span class="sxs-lookup"><span data-stu-id="f1141-104">**This article is for administrators. Do you want to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**</span></span>
   
<span data-ttu-id="f1141-105">以下是有关使用 Office 365 导入服务将 PST 文件批量导入到 Microsoft 365 邮箱的一些常见问题。</span><span class="sxs-lookup"><span data-stu-id="f1141-105">Here are some frequently asked questions about using the Office 365 Import Service to bulk-import PST files to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="f1141-106">若要详细了解如何导入 PST 文件，请参阅 [将 PST 文件导入到 Office 365 的概述](./importing-pst-files-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="f1141-106">For more information about how to import PST files, see [Overview of importing PST files to Office 365](./importing-pst-files-to-office-365.md).</span></span>
  
## <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="f1141-107">使用网络上传导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="f1141-107">Using network upload to import PST files</span></span>

<span data-ttu-id="f1141-108">有关分步说明，请参阅使用网络上传将[PST 文件导入到 Office 365。](use-network-upload-to-import-pst-files.md)</span><span class="sxs-lookup"><span data-stu-id="f1141-108">For step-by-step instructions, see [Use network upload to import PST files to Office 365](use-network-upload-to-import-pst-files.md).</span></span>
  
 <span data-ttu-id="f1141-109">**在 Office 365 导入服务中创建导入作业需要哪些权限？**</span><span class="sxs-lookup"><span data-stu-id="f1141-109">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="f1141-110">必须分配有 Exchange Online 中的邮箱导入导出角色，才能将 PST 文件导入到 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="f1141-110">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="f1141-111">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="f1141-111">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="f1141-112">您可以向“组织管理”角色组添加“邮箱导入导出”角色。</span><span class="sxs-lookup"><span data-stu-id="f1141-112">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="f1141-113">或者可以创建新的角色组，分配邮箱导入导出角色，然后将自己或其他用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="f1141-113">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="f1141-114">有关详细信息，请参阅[管理 Exchange Online 中的角色组](/Exchange/permissions-exo/role-groups)中的“向角色组添加角色”或“创建角色组”部分。</span><span class="sxs-lookup"><span data-stu-id="f1141-114">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](/Exchange/permissions-exo/role-groups).</span></span>
  
<span data-ttu-id="f1141-115">此外，若要在安全与合规中心创建导入作业，必须满足以下条件之一：</span><span class="sxs-lookup"><span data-stu-id="f1141-115">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="f1141-116">必须分配有 Exchange Onlin 中的“邮件收件人”角色。</span><span class="sxs-lookup"><span data-stu-id="f1141-116">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="f1141-117">默认情况下，此角色分配给“组织管理和收件人管理”角色组。</span><span class="sxs-lookup"><span data-stu-id="f1141-117">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="f1141-118">或</span><span class="sxs-lookup"><span data-stu-id="f1141-118">Or</span></span>
    
- <span data-ttu-id="f1141-119">必须是你组织中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="f1141-119">You have to be a global administrator in your organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="f1141-120">请考虑在 Exchange Online 中创建新角色组，此角色组专门用于将 PST 文件导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f1141-120">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="f1141-121">若要获取导入 PST 文件所需的最低级别权限，请将“邮件导入导出和邮件收件人”角色分配给新角色组，然后添加成员。</span><span class="sxs-lookup"><span data-stu-id="f1141-121">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="f1141-122">**网络上传在哪些地区提供？**</span><span class="sxs-lookup"><span data-stu-id="f1141-122">**Where is network upload available?**</span></span>
  
<span data-ttu-id="f1141-p105">目前，在以下区域提供网络上传功能：美国、加拿大、巴西、英国、法国、德国、瑞士、挪威、欧洲、印度、东亚、东南亚、日本、韩国、澳大利亚和阿拉伯联合酋长国 (UAE)。该功能将很快在更多区域中提供。</span><span class="sxs-lookup"><span data-stu-id="f1141-p105">Network upload is currently available in these regions: United States, Canada, Brazil, the United Kingdom, France, Germany, Switzerland, Norway, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, Australia, and United Arab Emirates (UAE). Network upload will be available in more regions soon.</span></span>
  
 <span data-ttu-id="f1141-125">**使用网络上传导入 PST 文件的定价如何？**</span><span class="sxs-lookup"><span data-stu-id="f1141-125">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="f1141-126">Using network upload to import PST files is free.</span><span class="sxs-lookup"><span data-stu-id="f1141-126">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="f1141-127">这也意味着 PST 文件从 Azure 存储区域删除后，将不再显示在 Microsoft 365 管理中心已完成导入作业的文件列表中。</span><span class="sxs-lookup"><span data-stu-id="f1141-127">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f1141-128">虽然导入作业可能仍然列在“**将数据导入到 Office 365**”页面，但查看较早导入作业的详细信息时，PST 文件的列表可能为空。</span><span class="sxs-lookup"><span data-stu-id="f1141-128">Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="f1141-129">**哪个版本的 PST 文件格式支持导入到 Office 365？**</span><span class="sxs-lookup"><span data-stu-id="f1141-129">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="f1141-130">可选两个版本的 PST 文件格式：ANSI 和 Unicode。</span><span class="sxs-lookup"><span data-stu-id="f1141-130">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="f1141-131">建议导入使用 Unicode PST 文件格式的文件。</span><span class="sxs-lookup"><span data-stu-id="f1141-131">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="f1141-132">但是，采用 ANSI PST 文件格式的文件也可以导入到 Office 365，如语言采用双字节字符集 (DBCS) 的文件。</span><span class="sxs-lookup"><span data-stu-id="f1141-132">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365.</span></span> <span data-ttu-id="f1141-133">有关导入 ANSI PST 文件的信息，请参阅使用网络上传将组织的 PST 文件导入 [到 Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)中的步骤 4。</span><span class="sxs-lookup"><span data-stu-id="f1141-133">For more information about importing ANSI PST files, see Step 4 in [Use network upload to import your organization's PST files to Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="f1141-134">此外，来自 Outlook 2007 和更高版本 Outlook 的 PST 文件可导入到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f1141-134">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="f1141-135">**将 PST 文件上传到 Azure 存储区域后，这些文件在删除前可在 Azure 中保留多长时间？**</span><span class="sxs-lookup"><span data-stu-id="f1141-135">**After I upload my PST files to the Azure Storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="f1141-136">当使用网络上传方法导入 PST 文件时，会将文件上传到已命名的 Azure Blob 容器`ingestiondata`。</span><span class="sxs-lookup"><span data-stu-id="f1141-136">When you use the network upload method to import PST files, you upload them to an Azure blob container named `ingestiondata`.</span></span> <span data-ttu-id="f1141-137">如果安全与合规中心中的“**导入 PST 页面**”页面上没有正在进行的导入作业，则 Azure 中 `ingestiondata` 容器内的所有 PST 文件都会在安全与合规中心中创建最新导入作业 30 天后被删除。</span><span class="sxs-lookup"><span data-stu-id="f1141-137">If there are no import jobs in progress on the **Import PST files** page in the Security & Compliance Center), then all PST files in the `ingestiondata` container in Azure are deleted 30 days after the most recent import job was created in the Security & Compliance Center.</span></span> <span data-ttu-id="f1141-138">这也意味着须在将 PST 文件上传到 Azure 后的 30 天内在安全与合规中心中创建新的导入作业（如网络上传说明的步骤 5 中所述）。</span><span class="sxs-lookup"><span data-stu-id="f1141-138">That also means you have to create a new import job in the Security & Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span> 
  
<span data-ttu-id="f1141-139">这也意味着 PST 文件从 Azure 存储区域删除后，将不再显示在安全与合规中心已完成导入作业的文件列表中。</span><span class="sxs-lookup"><span data-stu-id="f1141-139">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="f1141-140">虽然导入作业可能仍然列在安全与合规中心的“**导入 PST 文件**”页面，但查看较早导入作业的详细信息时，PST 文件的列表可能为空。</span><span class="sxs-lookup"><span data-stu-id="f1141-140">Although an import job might still be listed on the **Import PST files** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="f1141-141">**将 PST 文件导入到邮箱需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="f1141-141">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="f1141-142">这取决于你的网络容量，但每 TB 数据通常需要几个小时才能上传到组织的 Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="f1141-142">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure Storage area for your organization.</span></span> <span data-ttu-id="f1141-143">PST 文件复制到 Azure 存储区域后，PST 文件将以每天至少 24 GB 的速度导入到 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="f1141-143">After the PST files are copied to the Azure Storage area, a PST file is imported to a Microsoft 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="f1141-144">如果此速度不满足你的需求，可能需要考虑采用其他方法将电子邮件数据迁移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f1141-144">If this rate doesn't meet your needs, you might consider other methods for migrating email data to Office 365.</span></span> <span data-ttu-id="f1141-145">有关详细信息，请参阅[将多个电子邮件帐户迁移到 Office 365 的方法](/Exchange/mailbox-migration/mailbox-migration)。</span><span class="sxs-lookup"><span data-stu-id="f1141-145">For more information, see [Ways to migrate multiple email accounts to Office 365](/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
<span data-ttu-id="f1141-146">如果不同的 PST 文件导入到不同的目标邮箱中，则导入过程将以并行方式进行；也就是说，每个 PST/邮箱对是同时导入的。</span><span class="sxs-lookup"><span data-stu-id="f1141-146">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="f1141-147">同样，如果多个 PST 文件导入到同一个邮箱中，也将同时导入这些文件。</span><span class="sxs-lookup"><span data-stu-id="f1141-147">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="f1141-148">**PST 导入进程如何处理重复的电子邮件项？**</span><span class="sxs-lookup"><span data-stu-id="f1141-148">**How does the PST import process handle duplicate email items?**</span></span>

<span data-ttu-id="f1141-149">如果目标邮箱或目标存档的目标文件夹中存在匹配项，PST 导入进程将检查重复的项目，并且不会将邮件项从 PST 文件复制到邮箱或存档。</span><span class="sxs-lookup"><span data-stu-id="f1141-149">The PST import process checks for duplicate items and doesn't copy the items from a PST file to the mailbox or archive if a matching item exists in the target folder in the target mailbox or target archive.</span></span> <span data-ttu-id="f1141-150">如果重新导入相同的 PST 文件并指定与上一个导入作业中指定的文件夹不同的目标文件夹（使用 PST 导入映射文件中的 TargetRootFolder 属性），将重新导入 PST 文件中的所有项。</span><span class="sxs-lookup"><span data-stu-id="f1141-150">If you reimport the same PST file and specify a different target folder (using the TargetRootFolder property in the PST import mapping file) than the one you specified in a previous import job, all items in the PST file will be reimported.</span></span>

 <span data-ttu-id="f1141-151">**导入 PST 文件时是否有邮件大小限制？**</span><span class="sxs-lookup"><span data-stu-id="f1141-151">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="f1141-152">是。</span><span class="sxs-lookup"><span data-stu-id="f1141-152">Yes.</span></span> <span data-ttu-id="f1141-153">如果 PST 文件包含大于 150 MB 的邮件项，则将在导入过程中跳过此项。</span><span class="sxs-lookup"><span data-stu-id="f1141-153">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="f1141-154">**PST 文件导入到 Microsoft 365 邮箱时，是否会保留邮件发送时间或接收时间、收件人列表和其他邮件属性？**</span><span class="sxs-lookup"><span data-stu-id="f1141-154">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to a Microsoft 365 mailbox?**</span></span>
  
<span data-ttu-id="f1141-155">可以。</span><span class="sxs-lookup"><span data-stu-id="f1141-155">Yes.</span></span> <span data-ttu-id="f1141-156">导入过程中不会更改任何原始邮件元数据。</span><span class="sxs-lookup"><span data-stu-id="f1141-156">The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="f1141-157">**我想要导入邮箱的 PST 文件是否存在文件夹层次结构的级别数目限制？**</span><span class="sxs-lookup"><span data-stu-id="f1141-157">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="f1141-p115">是的。不能导入包含 300 个或更多级别的嵌套文件夹的 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="f1141-p115">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="f1141-160">**是否可以使用网络上传将 PST 文件导入到 Office 365 中的非活动邮箱？**</span><span class="sxs-lookup"><span data-stu-id="f1141-160">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="f1141-161">是的，这一功能现已推出。</span><span class="sxs-lookup"><span data-stu-id="f1141-161">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="f1141-162">**是否可以使用网络上传将 PST 文件导入到 Exchange 混合部署中的联机存档邮箱？**</span><span class="sxs-lookup"><span data-stu-id="f1141-162">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="f1141-163">是的，这一功能现已推出。 </span><span class="sxs-lookup"><span data-stu-id="f1141-163">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="f1141-164">**是否可以使用网络上传将 PST 文件导入 Exchange Online 中的公用文件夹？**</span><span class="sxs-lookup"><span data-stu-id="f1141-164">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="f1141-165">否，无法将 PST 文件导入公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1141-165">No, you can't import PST files to public folders.</span></span>
  
## <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="f1141-166">使用驱动器寄送导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="f1141-166">Using drive shipping to import PST files</span></span>

<span data-ttu-id="f1141-167">有关分步说明，请参阅使用驱动器寄送将[PST 文件导入到 Office 365。](use-drive-shipping-to-import-pst-files-to-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="f1141-167">For step-by-step instructions, see [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).</span></span>
  
 <span data-ttu-id="f1141-168">**在 Office 365 导入服务中创建导入作业需要哪些权限？**</span><span class="sxs-lookup"><span data-stu-id="f1141-168">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="f1141-169">必须分配有邮箱导入导出角色，才能将 PST 文件导入到 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="f1141-169">You have to be assigned the Mailbox Import Export role to import PST files to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="f1141-170">默认情况下，不会向 Exchange Online 中任何角色组分配此角色。</span><span class="sxs-lookup"><span data-stu-id="f1141-170">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="f1141-171">您可以向“组织管理”角色组添加“邮箱导入导出”角色。</span><span class="sxs-lookup"><span data-stu-id="f1141-171">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="f1141-172">或者可以创建新的角色组，分配邮箱导入导出角色，然后将自己或其他用户添加为成员。</span><span class="sxs-lookup"><span data-stu-id="f1141-172">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="f1141-173">有关详细信息，请参阅[管理 Exchange Online 中的角色组](/Exchange/permissions-exo/role-groups)中的“向角色组添加角色”或“创建角色组”部分。</span><span class="sxs-lookup"><span data-stu-id="f1141-173">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](/Exchange/permissions-exo/role-groups).</span></span>
  
<span data-ttu-id="f1141-174">此外，若要在安全与合规中心创建导入作业，必须满足以下条件之一：</span><span class="sxs-lookup"><span data-stu-id="f1141-174">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="f1141-175">必须分配有 Exchange Onlin 中的“邮件收件人”角色。</span><span class="sxs-lookup"><span data-stu-id="f1141-175">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="f1141-176">默认情况下，此角色分配给“组织管理和收件人管理”角色组。</span><span class="sxs-lookup"><span data-stu-id="f1141-176">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="f1141-177">或</span><span class="sxs-lookup"><span data-stu-id="f1141-177">Or</span></span>
    
- <span data-ttu-id="f1141-178">必须是你组织中的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="f1141-178">You have to be a global administrator in your organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="f1141-179">请考虑在 Exchange Online 中创建新角色组，此角色组专门用于将 PST 文件导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f1141-179">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="f1141-180">若要获取导入 PST 文件所需的最低级别权限，请将“邮件导入导出和邮件收件人”角色分配给新角色组，然后添加成员。</span><span class="sxs-lookup"><span data-stu-id="f1141-180">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="f1141-181">**哪些地区提供驱动器寄送服务？**</span><span class="sxs-lookup"><span data-stu-id="f1141-181">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="f1141-182">当前，美国、加拿大、巴西、英国、欧洲、印度、东亚地址、东南亚、日本、韩国和澳大利亚已推出驱动器传送。</span><span class="sxs-lookup"><span data-stu-id="f1141-182">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia.</span></span> <span data-ttu-id="f1141-183">不久之后，还会有更多地区推出驱动器传送。</span><span class="sxs-lookup"><span data-stu-id="f1141-183">Drive shipping will be available in more regions soon.</span></span>

> [!NOTE]
> <span data-ttu-id="f1141-184">目前，不可在德国和瑞士使用驱动器发运导入 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="f1141-184">At this time, drive shipping to import PST files is not available in Germany and Switzerland.</span></span> <span data-ttu-id="f1141-185">当这些国家/地区提供驱动器发运功能后，此常见问题解答将更新。</span><span class="sxs-lookup"><span data-stu-id="f1141-185">This FAQ will be updated when drive shipping is available in these countries.</span></span>
  
 <span data-ttu-id="f1141-186">**哪些商业许可协议支持驱动器发运？**</span><span class="sxs-lookup"><span data-stu-id="f1141-186">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="f1141-187">驱动器传送可通过 Microsoft 企业协议 (EA) 将 PST 文件导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="f1141-187">Drive shipping to import PST files to Microsoft 365 is available through a Microsoft Enterprise Agreement (EA).</span></span> <span data-ttu-id="f1141-188">驱动器寄送不可通过 Microsoft 产品和服务协议 (MPSA) 实现。</span><span class="sxs-lookup"><span data-stu-id="f1141-188">Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="f1141-189">**使用驱动器传送将 PST 文件导入到 Microsoft 365 的定价如何？**</span><span class="sxs-lookup"><span data-stu-id="f1141-189">**What is the pricing for using drive shipping to import PST files to Microsoft 365?**</span></span>
  
<span data-ttu-id="f1141-190">使用驱动器传送将 PST 文件导入到 Microsoft 365 邮箱的费用为每 GB 数据 2 美元。</span><span class="sxs-lookup"><span data-stu-id="f1141-190">The cost to use drive shipping to import PST files to Microsoft 365 mailboxes is $2 USD per GB of data.</span></span> <span data-ttu-id="f1141-191">例如，如果发运的硬盘包含 1,000 GB (1 TB) 的 PST 文件，则费用为 2,000 美元。</span><span class="sxs-lookup"><span data-stu-id="f1141-191">For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD.</span></span> <span data-ttu-id="f1141-192">您可以与合作伙伴共同协作来支付导入费用。</span><span class="sxs-lookup"><span data-stu-id="f1141-192">You can work with a partner to pay the import fee.</span></span> <span data-ttu-id="f1141-193">有关查找合作伙伴的信息，请参阅[查找 Microsoft 合作伙伴或经销商](../admin/manage/find-your-partner-or-reseller.md)。</span><span class="sxs-lookup"><span data-stu-id="f1141-193">For information about finding a partner, see [Find your Microsoft partner or reseller](../admin/manage/find-your-partner-or-reseller.md).</span></span>
  
 <span data-ttu-id="f1141-194">**哪类硬盘支持驱动器发运？**</span><span class="sxs-lookup"><span data-stu-id="f1141-194">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="f1141-195">仅支持将 2.5 英寸固态硬盘 (SSD) 或 2.5 英寸或 3.5 英寸 SATA II/III 内部硬盘驱动器与 Office 365 导入服务一同使用。</span><span class="sxs-lookup"><span data-stu-id="f1141-195">Only 2.5-inch solid-state drives (SSDs) or 2.5-inch or 3.5-inch SATA II/III internal hard drives are supported for use with the Office 365 Import service.</span></span> <span data-ttu-id="f1141-196">可使用最多 10 TB 的硬盘。</span><span class="sxs-lookup"><span data-stu-id="f1141-196">You can use hard drives up to 10 TB.</span></span> <span data-ttu-id="f1141-197">对于导入作业，仅将处理硬盘上的第一个数据卷。</span><span class="sxs-lookup"><span data-stu-id="f1141-197">For import jobs, only the first data volume on the hard drive will be processed.</span></span> <span data-ttu-id="f1141-198">必须使用 NTFS 格式化数据卷。</span><span class="sxs-lookup"><span data-stu-id="f1141-198">The data volume must be formatted with NTFS.</span></span> <span data-ttu-id="f1141-199">将数据复制到硬盘驱动器时，可以使用 2.5 英寸 SSD 或 2.5 英寸或 3.5 英寸 SATA II/III 连接器直接连接它，或者可以使用外部 2.5 英寸 SSD 或 2.5 英寸或 3.5 英寸 SATA II/III USB 适配器将其外部连接。</span><span class="sxs-lookup"><span data-stu-id="f1141-199">When copying data to a hard drive, you can attach it directly using a 2.5-inch SSD or 2.5-inch or 3.5-inch SATA II/III connector or you can attach it externally using an external 2.5-inch SSD or 2.5-inch or 3.5-inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f1141-200">Office 365 导入服务中不支持内置 USB 适配器随附的外部硬盘。</span><span class="sxs-lookup"><span data-stu-id="f1141-200">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service.</span></span> <span data-ttu-id="f1141-201">此外，无法使用外部硬盘盒内的磁盘。</span><span class="sxs-lookup"><span data-stu-id="f1141-201">Additionally, the disk inside the casing of an external hard drive can't be used.</span></span> <span data-ttu-id="f1141-202">请不要发运外部硬盘。</span><span class="sxs-lookup"><span data-stu-id="f1141-202">Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="f1141-203">**单个导入作业可以发运多少个硬盘？**</span><span class="sxs-lookup"><span data-stu-id="f1141-203">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="f1141-204">单个导入作业最多可以发运 10 个硬盘。</span><span class="sxs-lookup"><span data-stu-id="f1141-204">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="f1141-205">**发运硬盘后，需要多长时间才能转到 Microsoft 数据中心？**</span><span class="sxs-lookup"><span data-stu-id="f1141-205">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span></span>
  
<span data-ttu-id="f1141-p125">这取决于几点，例如你与 Microsoft 数据中心之间的距离、使用哪种类型的送货选项来配送硬盘（如隔天送达、两天送达或地面配送）。对于大多数运货商，可使用跟踪编号跟踪配送状态。</span><span class="sxs-lookup"><span data-stu-id="f1141-p125">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="f1141-208">**硬盘驱动器到达 Microsoft 数据中心后，需要多久才能将 PST文件上传到 Azure？**</span><span class="sxs-lookup"><span data-stu-id="f1141-208">**After my hard drive arrives at the Microsoft data center, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="f1141-209">在 Microsoft 数据中心收到硬盘驱动器后，需要 7 到 10 个工作日将 PST 文件上传到组织的 Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="f1141-209">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Azure Storage area for your organization.</span></span> <span data-ttu-id="f1141-210">PST 文件将上传到名为 `ingestiondata` 的 Azure Blob 容器。</span><span class="sxs-lookup"><span data-stu-id="f1141-210">The PST files will be uploaded to an Azure blob container named `ingestiondata`.</span></span> 
  
 <span data-ttu-id="f1141-211">**将 PST 文件导入到邮箱需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="f1141-211">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="f1141-212">将 PST 文件上传到 Azure 存储区域后，Microsoft 365 采用安全方式分析 PST 文件中的数据，确定 PST 文件中所含项目的存在时长以及各种邮件类型。</span><span class="sxs-lookup"><span data-stu-id="f1141-212">After the PST files are uploaded to the Azure Storage area, Microsoft 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files.</span></span> <span data-ttu-id="f1141-213">分析完成后，可以选择将所有数据导入 PST 文件，或设置筛选器控制导入的数据。</span><span class="sxs-lookup"><span data-stu-id="f1141-213">When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported.</span></span> <span data-ttu-id="f1141-214">开始导入作业后，PST 文件将以每天至少 24 GB 的速度导入到 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="f1141-214">After you start the import job, a PST file is imported to a Microsoft 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="f1141-215">如果此速度不满足你的需求，可能需要考虑采用其他方法将电子邮件数据导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f1141-215">If this rate doesn't meet your needs, you might consider other methods for importing email data to Office 365.</span></span> <span data-ttu-id="f1141-216">有关详细信息，请参阅[将多个电子邮件帐户迁移到 Office 365 的方法](/Exchange/mailbox-migration/mailbox-migration)。</span><span class="sxs-lookup"><span data-stu-id="f1141-216">For more information, see [Ways to migrate multiple email accounts to Office 365](/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
<span data-ttu-id="f1141-217">如果不同的 PST 文件导入到不同的目标邮箱中，则导入过程将以并行方式进行；也就是说，每个 PST/邮箱对是同时导入的。</span><span class="sxs-lookup"><span data-stu-id="f1141-217">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="f1141-218">同样，如果多个 PST 文件导入到同一个邮箱中，也将同时导入这些文件。</span><span class="sxs-lookup"><span data-stu-id="f1141-218">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="f1141-219">**Microsoft 将 PST 文件上传到 Azure 后，这些文件在删除前可在 Azure 中保留多长时间？**</span><span class="sxs-lookup"><span data-stu-id="f1141-219">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="f1141-220">在安全与合规中心的“**导入 PST 文件**”页面上创建最新导入作业的 30 天后，将删除组织的 Azure 存储位置（位于名为 `ingestiondata` 的 Blob 容器中）内的所有 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="f1141-220">All PST files in the Azure Storage location for your organization (in blob container named `ingestiondata`), are deleted 30 days after the most recent import job was created on the **Import PST files** page in the Security & Compliance Center.</span></span> 
  
<span data-ttu-id="f1141-221">这也意味着 PST 文件从 Azure 存储区域删除后，将不再显示在安全与合规中心已完成导入作业的文件列表中。</span><span class="sxs-lookup"><span data-stu-id="f1141-221">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="f1141-222">虽然导入作业可能仍然列在安全与合规中心的“**导入 PST 文件**”页面，但查看较早导入作业的详细信息时，PST 文件的列表可能为空。</span><span class="sxs-lookup"><span data-stu-id="f1141-222">Although an import job might still be listed on the **Import PST files** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="f1141-223">**哪个版本的 PST 文件格式支持导入到 Microsoft 365？**</span><span class="sxs-lookup"><span data-stu-id="f1141-223">**What version of the PST file format is supported for importing to Microsoft 365?**</span></span>
  
<span data-ttu-id="f1141-224">可选两个版本的 PST 文件格式：ANSI 和 Unicode。</span><span class="sxs-lookup"><span data-stu-id="f1141-224">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="f1141-225">建议导入使用 Unicode PST 文件格式的文件。</span><span class="sxs-lookup"><span data-stu-id="f1141-225">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="f1141-226">但是，采用 ANSI PST 文件格式的文件也可以导入到 Microsoft 365，如语言采用双字节字符集 (DBCS) 的文件。</span><span class="sxs-lookup"><span data-stu-id="f1141-226">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Microsoft 365.</span></span> <span data-ttu-id="f1141-227">有关导入 ANSI PST 文件的信息，请参阅使用驱动器寄送将 PST 文件导入 [到 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)中的步骤 3。</span><span class="sxs-lookup"><span data-stu-id="f1141-227">For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="f1141-228">此外，来自 Outlook 2007 和更高版本 Outlook 的 PST 文件可导入到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f1141-228">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="f1141-229">**导入 PST 文件时是否有邮件大小限制？**</span><span class="sxs-lookup"><span data-stu-id="f1141-229">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="f1141-230">是。</span><span class="sxs-lookup"><span data-stu-id="f1141-230">Yes.</span></span> <span data-ttu-id="f1141-231">如果 PST 文件包含大于 150 MB 的邮件项，则将在导入过程中跳过此项。</span><span class="sxs-lookup"><span data-stu-id="f1141-231">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
  <span data-ttu-id="f1141-232">**PST 导入进程如何处理重复的电子邮件项？**</span><span class="sxs-lookup"><span data-stu-id="f1141-232">**How does the PST import process handle duplicate email items?**</span></span>

<span data-ttu-id="f1141-233">如果目标邮箱或目标存档的目标文件夹中存在匹配项，PST 导入进程将检查重复的项目，并且不会将邮件项从 PST 文件复制到邮箱或存档。</span><span class="sxs-lookup"><span data-stu-id="f1141-233">The PST import process checks for duplicate items and doesn't copy the items from a PST file to the mailbox or archive if a matching item exists in the target folder in the target mailbox or target archive.</span></span> <span data-ttu-id="f1141-234">如果重新导入相同的 PST 文件并指定与上一个导入作业中指定的文件夹不同的目标文件夹（使用 PST 导入映射文件中的 TargetRootFolder 属性），将重新导入 PST 文件中的所有项。</span><span class="sxs-lookup"><span data-stu-id="f1141-234">If you reimport the same PST file and specify a different target folder (using the TargetRootFolder property in the PST import mapping file) than the one you specified in a previous import job, all items in the PST file will be reimported.</span></span>
 
 <span data-ttu-id="f1141-235">**PST 文件导入到 Microsoft 365 邮箱时，是否会保留邮件发送时间或接收时间、收件人列表和其他邮件属性？**</span><span class="sxs-lookup"><span data-stu-id="f1141-235">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to a Microsoft 365 mailbox?**</span></span>
  
<span data-ttu-id="f1141-236">可以。</span><span class="sxs-lookup"><span data-stu-id="f1141-236">Yes.</span></span> <span data-ttu-id="f1141-237">导入过程中不会更改原始邮件的元数据</span><span class="sxs-lookup"><span data-stu-id="f1141-237">The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="f1141-238">**我想要导入邮箱的 PST 文件是否存在文件夹层次结构的级别数目限制？**</span><span class="sxs-lookup"><span data-stu-id="f1141-238">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="f1141-p134">是的。不能导入包含 300 个或更多级别的嵌套文件夹的 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="f1141-p134">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="f1141-241">**是否可以使用驱动器传送将 PST 文件导入到 Microsoft 365 中的非活动邮箱？**</span><span class="sxs-lookup"><span data-stu-id="f1141-241">**Can I use drive shipping to import PST files to an inactive mailbox in Microsoft 365?**</span></span>
  
<span data-ttu-id="f1141-242">是的，这一功能现已推出。</span><span class="sxs-lookup"><span data-stu-id="f1141-242">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="f1141-243">**是否可以使用驱动器发运将 PST 文件导入到 Exchange 混合部署中的联机存档邮箱？**</span><span class="sxs-lookup"><span data-stu-id="f1141-243">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="f1141-244">是的，这一功能现已推出。</span><span class="sxs-lookup"><span data-stu-id="f1141-244">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="f1141-245">**是否可以使用驱动器发运将 PST 文件导入 Exchange Online 中的公用文件夹？**</span><span class="sxs-lookup"><span data-stu-id="f1141-245">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="f1141-246">否，无法将 PST 文件导入公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1141-246">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="f1141-247">**Microsoft 将硬盘运回给我之前，是否会进行擦除？**</span><span class="sxs-lookup"><span data-stu-id="f1141-247">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="f1141-p135">不会，Microsoft 将硬盘运回给客户前不会进行擦除。硬盘将以 Microsoft 接收到的状态返回给你。</span><span class="sxs-lookup"><span data-stu-id="f1141-p135">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="f1141-250">**Microsoft 是否会销毁我的硬盘，而不是寄回给我？**</span><span class="sxs-lookup"><span data-stu-id="f1141-250">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="f1141-p136">不会，Microsoft 不会销毁硬盘。硬盘将以 Microsoft 接收到的状态返回给你。</span><span class="sxs-lookup"><span data-stu-id="f1141-p136">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="f1141-253">**寄回时支持哪些快递服务？**</span><span class="sxs-lookup"><span data-stu-id="f1141-253">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="f1141-p137">对于美国或欧洲客户，Microsoft 使用 FedEx 运回硬盘。对于所有其他区域的客户，Microsoft 将使用 DHL。</span><span class="sxs-lookup"><span data-stu-id="f1141-p137">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="f1141-256">**寄回的运费是多少？**</span><span class="sxs-lookup"><span data-stu-id="f1141-256">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="f1141-p138">运回的运费有所不同，具体取决于你与硬盘运达的 Microsoft 数据中心之间的距离。Microsoft 将向你收取通过 FedEx 或 DHL 运回硬盘的费用。返回运费需由你支付。</span><span class="sxs-lookup"><span data-stu-id="f1141-p138">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="f1141-260">**是否可以使用 FedEx Custom Shipping 等自定义快递运输服将我的硬盘寄送至 Microsoft？**</span><span class="sxs-lookup"><span data-stu-id="f1141-260">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="f1141-261">是。</span><span class="sxs-lookup"><span data-stu-id="f1141-261">Yes.</span></span>
  
 <span data-ttu-id="f1141-262">**如果我必须将我的硬盘发运到其他国家/地区，是否有任何需要执行的操作？**</span><span class="sxs-lookup"><span data-stu-id="f1141-262">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="f1141-p139">你发运到 Microsoft 的硬盘可能会跨越国际边界。如果是这种情况，你有责任确保硬盘及其所含数据是根据适用法律导入和/或导出的。发运硬盘前，请与顾问联系，确保驱动器和数据可以合法地发送到指定的 Microsoft 数据中心。这有助于确保它及时送达 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="f1141-p139">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>