---
title: 在 SharePoint 管理中心设置信息权限管理 (IRM)
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: 了解如何通过 Microsoft Azure Active Directory Rights Management Services (RMS) SharePoint Online IRM 来保护 SharePoint 列表和文档库。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68db84118ac8ccd7c734152aa28816db819198f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919398"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a><span data-ttu-id="7baa6-103">在 SharePoint 管理中心设置信息权限管理 (IRM)</span><span class="sxs-lookup"><span data-stu-id="7baa6-103">Set up Information Rights Management (IRM) in SharePoint admin center</span></span>

<span data-ttu-id="7baa6-104">在 SharePoint Online 中，IRM 保护适用于列表和库级别的文件。</span><span class="sxs-lookup"><span data-stu-id="7baa6-104">Within SharePoint Online, IRM protection is applied to files at the list and library level.</span></span> <span data-ttu-id="7baa6-105">必须先设置权限管理，你的组织才能使用 IRM 保护。</span><span class="sxs-lookup"><span data-stu-id="7baa6-105">Before your organization can use IRM protection, you must first set up Rights Management.</span></span> <span data-ttu-id="7baa6-106">IRM 依靠 Azure 信息保护的 Azure 权限管理服务来加密和分配使用限制。</span><span class="sxs-lookup"><span data-stu-id="7baa6-106">IRM relies on the Azure Rights Management service from Azure Information Protection to encrypt and assign usage restrictions.</span></span> <span data-ttu-id="7baa6-107">某些 Microsoft 365 计划包括 Azure 权限管理，但不是全部。</span><span class="sxs-lookup"><span data-stu-id="7baa6-107">Some Microsoft 365 plans include Azure Rights Management, but not all.</span></span> <span data-ttu-id="7baa6-108">若要了解更多信息，请阅读 [Office 应用程序和服务如何支持 Azure 权限管理](/azure/information-protection/understand-explore/office-apps-services-support)。</span><span class="sxs-lookup"><span data-stu-id="7baa6-108">To learn more, read [How Office applications and services support Azure Rights Management](/azure/information-protection/understand-explore/office-apps-services-support).</span></span>
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a><span data-ttu-id="7baa6-109">使用 SharePoint 管理中心启用 IRM 服务</span><span class="sxs-lookup"><span data-stu-id="7baa6-109">Turn on IRM service using SharePoint admin center</span></span>

<span data-ttu-id="7baa6-110">在组织可以 IRM 保护 SharePoint 列表和库之前，必须先为组织激活权限管理服务。</span><span class="sxs-lookup"><span data-stu-id="7baa6-110">Before your organization can IRM-protect SharePoint lists and libraries, you must first activate the Rights Management service for your organization.</span></span> <span data-ttu-id="7baa6-111">若要了解如何操作 [，请参阅激活 Azure 权限管理](/information-protection/deploy-use/activate-service)。</span><span class="sxs-lookup"><span data-stu-id="7baa6-111">To learn how see [Activating Azure Rights Management](/information-protection/deploy-use/activate-service).</span></span> <span data-ttu-id="7baa6-112">必须使用具有全局管理员权限的工作或学校帐户才能启用权限管理服务。</span><span class="sxs-lookup"><span data-stu-id="7baa6-112">You must use a work or school account that has global administrator privileges to enable the Rights Management service.</span></span> <span data-ttu-id="7baa6-113">否则，将无法将 IRM 功能与 SharePoint Online 一同使用。</span><span class="sxs-lookup"><span data-stu-id="7baa6-113">Otherwise, you won't be able to use IRM features with SharePoint Online.</span></span>
  
<span data-ttu-id="7baa6-114">激活权限管理服务后，登录到 SharePoint 管理中心以打开 IRM。</span><span class="sxs-lookup"><span data-stu-id="7baa6-114">After activating the Rights Management service, sign in to the SharePoint admin center to turn on IRM.</span></span>
  
1. <span data-ttu-id="7baa6-115">以全局管理员或 SharePoint 管理员登录。</span><span class="sxs-lookup"><span data-stu-id="7baa6-115">Sign in as a global admin or SharePoint admin.</span></span>
    
2. <span data-ttu-id="7baa6-116">依次选择左上角的应用启动器图标 ![Office 365 中的应用启动器图标](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) 和“管理员”，以打开 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="7baa6-116">Select the app launcher icon ![The app launcher icon in Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) in the upper-left and choose **Admin** to open the Microsoft 365 admin center.</span></span> <span data-ttu-id="7baa6-117"> (如果看不到"管理员"磁贴，则在你的组织中没有管理员权限。) </span><span class="sxs-lookup"><span data-stu-id="7baa6-117">(If you don't see the Admin tile, you don't have administrator permissions in your organization.)</span></span> 
    
3. <span data-ttu-id="7baa6-118">在左窗格中，选择"**管理中心** \> **""SharePoint"。**</span><span class="sxs-lookup"><span data-stu-id="7baa6-118">In the left pane, choose **Admin centers** \> **SharePoint**.</span></span>
    
4. <span data-ttu-id="7baa6-119">在左侧窗格中，选择 **"设置"，** 然后选择" **经典设置"页面**。</span><span class="sxs-lookup"><span data-stu-id="7baa6-119">In the left pane, choose **settings**, and then choose **classic settings page**.</span></span>
    
5. <span data-ttu-id="7baa6-120">在"**信息权限** 管理 (IRM) 部分中，选择"使用配置中指定的 **IRM** 服务"，然后选择"刷新 **IRM 设置"。**</span><span class="sxs-lookup"><span data-stu-id="7baa6-120">In the **Information Rights Management (IRM)** section, choose **Use the IRM service specified in your configuration**, and then choose **Refresh IRM Settings**.</span></span> <span data-ttu-id="7baa6-121">刷新 IRM 设置后，组织成员可以开始在 SharePoint 列表和文档库中使用 IRM。</span><span class="sxs-lookup"><span data-stu-id="7baa6-121">After you refresh IRM settings, people in your organization can begin using IRM in their SharePoint lists and document libraries.</span></span> <span data-ttu-id="7baa6-122">但是，这样做的选项最多可能需要一个小时才显示在"库设置"和"列表设置"中。</span><span class="sxs-lookup"><span data-stu-id="7baa6-122">However, the options to do so may take up to an hour to appear in Library Settings and List Settings.</span></span>
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a><span data-ttu-id="7baa6-123">启用 IRM 的 SharePoint 文档库和列表</span><span class="sxs-lookup"><span data-stu-id="7baa6-123">IRM-enable SharePoint document libraries and lists</span></span>
<span data-ttu-id="7baa6-124"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="7baa6-124"><a name="__toc220831191"> </a></span></span>

<span data-ttu-id="7baa6-125">刷新 IRM 设置后，网站所有者可以 IRM 保护其 SharePoint 列表和文档库。</span><span class="sxs-lookup"><span data-stu-id="7baa6-125">After refreshing IRM settings, site owners can IRM-protect their SharePoint lists and document libraries.</span></span> <span data-ttu-id="7baa6-126">有关详细信息，请参阅将 [信息权限管理应用于列表或库](apply-irm-to-a-list-or-library.md)。</span><span class="sxs-lookup"><span data-stu-id="7baa6-126">For more information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="7baa6-127">当网站所有者为列表或库启用 IRM 时，他们可以保护该列表或库中任何受支持的文件类型。</span><span class="sxs-lookup"><span data-stu-id="7baa6-127">When site owners enable IRM for a list or library, they can protect any supported file types in that list or library.</span></span> <span data-ttu-id="7baa6-128">当为库启用 IRM 时，权限管理将应用于该库中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="7baa6-128">When IRM is enabled for a library, rights management applies to all of the files in that library.</span></span> <span data-ttu-id="7baa6-129">为列表启用 IRM 时，权限管理仅适用于附加到列表项的文件，而不是实际列表项。</span><span class="sxs-lookup"><span data-stu-id="7baa6-129">When you enable IRM for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="7baa6-130">当用户在启用 IRM 的列表或库中下载文件时，文件会进行加密，以便只有授权人员才能查看这些文件。</span><span class="sxs-lookup"><span data-stu-id="7baa6-130">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them.</span></span> <span data-ttu-id="7baa6-131">每个权限管理文件还包含对查看该文件的人施加限制的发布许可证。</span><span class="sxs-lookup"><span data-stu-id="7baa6-131">Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file.</span></span> <span data-ttu-id="7baa6-132">典型限制包括使文件成为只读、禁用文本复制、阻止用户保存本地副本以及阻止用户打印文件。</span><span class="sxs-lookup"><span data-stu-id="7baa6-132">Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file.</span></span> <span data-ttu-id="7baa6-133">可读取支持 IRM 的文件类型的客户端程序使用权限管理文件内的颁发许可证来强制执行这些限制。</span><span class="sxs-lookup"><span data-stu-id="7baa6-133">Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions.</span></span> <span data-ttu-id="7baa6-134">这是权限管理文件即使在下载后仍保留其保护的方式。</span><span class="sxs-lookup"><span data-stu-id="7baa6-134">This is how a rights-managed file retains its protection even after it is downloaded.</span></span> <span data-ttu-id="7baa6-135">若要对列表或库启用 IRM，请参阅将 [信息权限管理应用于列表或库](apply-irm-to-a-list-or-library.md)。</span><span class="sxs-lookup"><span data-stu-id="7baa6-135">To enable IRM on a list or library, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="7baa6-136">不能在浏览器中使用 Office 在启用 IRM 的库中创建或编辑文档。</span><span class="sxs-lookup"><span data-stu-id="7baa6-136">You cannot create or edit documents in an IRM-enabled library using Office in a browser.</span></span> <span data-ttu-id="7baa6-137">相反，一个人一次可以下载和编辑 IRM 加密的文件。</span><span class="sxs-lookup"><span data-stu-id="7baa6-137">Instead, one person at a time can download and edit IRM-encrypted files.</span></span> <span data-ttu-id="7baa6-138">使用签入和签出管理多个  *用户*  之间的共同创作或创作。</span><span class="sxs-lookup"><span data-stu-id="7baa6-138">Use check-in and check-out to manage  *co-authoring*  , or authoring across multiple users.</span></span> 
  
<span data-ttu-id="7baa6-139">从受 IRM 保护的库下载 PDF 文件时，Microsoft 365 会创建一个受保护的 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="7baa6-139">When you download a PDF file from an IRM-protected library, Microsoft 365 creates a protected PDF file.</span></span> <span data-ttu-id="7baa6-140">文件的扩展名不会更改，但文件受保护。</span><span class="sxs-lookup"><span data-stu-id="7baa6-140">The file's extension won't change, but the file is protected.</span></span> <span data-ttu-id="7baa6-141">若要查看此文件，你需要 Azure 信息保护查看器、完整的 Azure 信息保护客户端或其他支持查看受保护 PDF 文件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7baa6-141">To view this file you'll need the Azure Information Protection viewer, the full Azure Information Protection client, or another application that supports viewing protected PDF files.</span></span> 
  
<span data-ttu-id="7baa6-142">SharePoint Online 支持对以下文件类型进行加密：</span><span class="sxs-lookup"><span data-stu-id="7baa6-142">SharePoint Online supports encryption of the following file types:</span></span>
  
- <span data-ttu-id="7baa6-143">PDF</span><span class="sxs-lookup"><span data-stu-id="7baa6-143">PDF</span></span>
    
- <span data-ttu-id="7baa6-144">以下程序 97-2003 文件格式Microsoft Office Word、Excel 和 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7baa6-144">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="7baa6-145">以下应用程序的程序的 Office Open XML Microsoft Office：Word、Excel 和 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="7baa6-145">The Office Open XML formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="7baa6-146">XML 纸张规范 (XPS) 格式</span><span class="sxs-lookup"><span data-stu-id="7baa6-146">The XML Paper Specification (XPS) format</span></span>
 
> [!NOTE]
> <span data-ttu-id="7baa6-147">IRM 保护无法应用于受保护文档 (如数字签名的 PDF) SharePoint 需要在上载时打开文档。</span><span class="sxs-lookup"><span data-stu-id="7baa6-147">IRM protection cannot be applied to protected documents (like digitally signed PDF files) as SharePoint needs to open the document on upload.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="7baa6-148">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7baa6-148">Next steps</span></span>
<span data-ttu-id="7baa6-149"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="7baa6-149"><a name="__toc220831191"> </a></span></span>

<span data-ttu-id="7baa6-150">为 SharePoint Online 启用 IRM 后，您可以开始对列表和库应用权限管理。</span><span class="sxs-lookup"><span data-stu-id="7baa6-150">Once you've enabled IRM for SharePoint Online, you can start applying rights management to lists and libraries.</span></span> <span data-ttu-id="7baa6-151">有关信息，请参阅 [将信息权限管理应用于列表或库](apply-irm-to-a-list-or-library.md)。</span><span class="sxs-lookup"><span data-stu-id="7baa6-151">For information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="7baa6-152">Windows 的新 OneDrive 同步客户端现在支持同步受 IRM 保护的 SharePoint 文档库和 OneDrive 位置 (只要库的 IRM 设置未设置为过期文档访问权限) 。</span><span class="sxs-lookup"><span data-stu-id="7baa6-152">The new OneDrive sync client for Windows now supports synchronizing IRM-protected SharePoint document libraries and OneDrive locations (as long as the IRM setting for the library isn't set to expire document access rights).</span></span> <span data-ttu-id="7baa6-153">有关详细信息，或者要开始部署新的同步客户端，请参阅部署适用于 Windows 的新 [OneDrive 同步客户端](/onedrive/deploy-on-windows)。</span><span class="sxs-lookup"><span data-stu-id="7baa6-153">For more information, or to get started deploying the new sync client, see [Deploy the new OneDrive sync client for Windows](/onedrive/deploy-on-windows).</span></span>
  
[<span data-ttu-id="7baa6-154">页面顶部</span><span class="sxs-lookup"><span data-stu-id="7baa6-154">Top of page</span></span>](set-up-irm-in-sp-admin-center.md)