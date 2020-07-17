---
title: Set up Information Rights Management (IRM) in SharePoint admin center
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
description: 了解如何通过 Microsoft Azure Active Directory 权限管理服务（RMS）使用 SharePoint Online IRM 来保护 SharePoint 列表和文档库。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 33e5a72ea1d0733656379bc4efdca7dd14f78cb1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819192"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a><span data-ttu-id="279e9-103">Set up Information Rights Management (IRM) in SharePoint admin center</span><span class="sxs-lookup"><span data-stu-id="279e9-103">Set up Information Rights Management (IRM) in SharePoint admin center</span></span>

<span data-ttu-id="279e9-104">在 SharePoint Online 中，IRM 保护应用于列表和库级别的文件。</span><span class="sxs-lookup"><span data-stu-id="279e9-104">Within SharePoint Online, IRM protection is applied to files at the list and library level.</span></span> <span data-ttu-id="279e9-105">您的组织可以使用 IRM 保护之前，必须先设置权限管理。</span><span class="sxs-lookup"><span data-stu-id="279e9-105">Before your organization can use IRM protection, you must first set up Rights Management.</span></span> <span data-ttu-id="279e9-106">IRM 依赖 azure 权限管理服务（来自 Azure 信息保护）来加密和分配使用限制。</span><span class="sxs-lookup"><span data-stu-id="279e9-106">IRM relies on the Azure Rights Management service from Azure Information Protection to encrypt and assign usage restrictions.</span></span> <span data-ttu-id="279e9-107">一些 Microsoft 365 计划包括 Azure 权限管理，但并非全部。</span><span class="sxs-lookup"><span data-stu-id="279e9-107">Some Microsoft 365 plans include Azure Rights Management, but not all.</span></span> <span data-ttu-id="279e9-108">若要了解详细信息，请参阅[Office 应用程序和服务如何支持 Azure 权限管理](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support)。</span><span class="sxs-lookup"><span data-stu-id="279e9-108">To learn more, read [How Office applications and services support Azure Rights Management](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support).</span></span>
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a><span data-ttu-id="279e9-109">使用 SharePoint 管理中心打开 IRM 服务</span><span class="sxs-lookup"><span data-stu-id="279e9-109">Turn on IRM service using SharePoint admin center</span></span>

<span data-ttu-id="279e9-110">在您的组织可以对 SharePoint 列表和库进行 IRM 保护之前，必须首先为您的组织激活权限管理服务。</span><span class="sxs-lookup"><span data-stu-id="279e9-110">Before your organization can IRM-protect SharePoint lists and libraries, you must first activate the Rights Management service for your organization.</span></span> <span data-ttu-id="279e9-111">若要了解如何查看 "[激活 Azure 权限管理](https://docs.microsoft.com/information-protection/deploy-use/activate-service)"。</span><span class="sxs-lookup"><span data-stu-id="279e9-111">To learn how see [Activating Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-service).</span></span> <span data-ttu-id="279e9-112">您必须使用具有全局管理员权限的工作或学校帐户来启用 Rights Management service。</span><span class="sxs-lookup"><span data-stu-id="279e9-112">You must use a work or school account that has global administrator privileges to enable the Rights Management service.</span></span> <span data-ttu-id="279e9-113">否则，将无法将 IRM 功能与 SharePoint Online 一起使用。</span><span class="sxs-lookup"><span data-stu-id="279e9-113">Otherwise, you won't be able to use IRM features with SharePoint Online.</span></span>
  
<span data-ttu-id="279e9-114">激活 Rights Management service 后，登录到 SharePoint 管理中心以打开 IRM。</span><span class="sxs-lookup"><span data-stu-id="279e9-114">After activating the Rights Management service, sign in to the SharePoint admin center to turn on IRM.</span></span>
  
1. <span data-ttu-id="279e9-115">以全局管理员或 SharePoint 管理员身份登录。</span><span class="sxs-lookup"><span data-stu-id="279e9-115">Sign in as a global admin or SharePoint admin.</span></span>
    
2. <span data-ttu-id="279e9-116">依次选择左上角的应用启动器图标 ![Office 365 中的应用启动器图标](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) 和“管理员”\*\*\*\*，以打开 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="279e9-116">Select the app launcher icon ![The app launcher icon in Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) in the upper-left and choose **Admin** to open the Microsoft 365 admin center.</span></span> <span data-ttu-id="279e9-117">（如果看不到 "管理员" 磁贴，则您的组织中不具有管理员权限。）</span><span class="sxs-lookup"><span data-stu-id="279e9-117">(If you don't see the Admin tile, you don't have administrator permissions in your organization.)</span></span> 
    
3. <span data-ttu-id="279e9-118">在左窗格中，选择 "**管理中心**" " \> **SharePoint**"。</span><span class="sxs-lookup"><span data-stu-id="279e9-118">In the left pane, choose **Admin centers** \> **SharePoint**.</span></span>
    
4. <span data-ttu-id="279e9-119">在左窗格中，选择 "**设置**"，然后选择 "**经典设置" 页**。</span><span class="sxs-lookup"><span data-stu-id="279e9-119">In the left pane, choose **settings**, and then choose **classic settings page**.</span></span>
    
5. <span data-ttu-id="279e9-120">在 "**信息权限管理（IRM）** " 部分中，选择 "**使用您的配置中指定的 IRM 服务**"，然后选择 "**刷新 IRM 设置**"。</span><span class="sxs-lookup"><span data-stu-id="279e9-120">In the **Information Rights Management (IRM)** section, choose **Use the IRM service specified in your configuration**, and then choose **Refresh IRM Settings**.</span></span> <span data-ttu-id="279e9-121">刷新 IRM 设置后，组织中的用户可以开始在其 SharePoint 列表和文档库中使用 IRM。</span><span class="sxs-lookup"><span data-stu-id="279e9-121">After you refresh IRM settings, people in your organization can begin using IRM in their SharePoint lists and document libraries.</span></span> <span data-ttu-id="279e9-122">但是，执行此操作的选项可能需要一个小时才能显示在 "库设置" 和 "列表设置" 中。</span><span class="sxs-lookup"><span data-stu-id="279e9-122">However, the options to do so may take up to an hour to appear in Library Settings and List Settings.</span></span>
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a><span data-ttu-id="279e9-123">IRM-启用 SharePoint 文档库和列表</span><span class="sxs-lookup"><span data-stu-id="279e9-123">IRM-enable SharePoint document libraries and lists</span></span>
<span data-ttu-id="279e9-124"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="279e9-124"><a name="__toc220831191"> </a></span></span>

<span data-ttu-id="279e9-125">刷新 IRM 设置后，网站所有者可以对其 SharePoint 列表和文档库进行 IRM 保护。</span><span class="sxs-lookup"><span data-stu-id="279e9-125">After refreshing IRM settings, site owners can IRM-protect their SharePoint lists and document libraries.</span></span> <span data-ttu-id="279e9-126">有关详细信息，请参阅[将信息权限管理应用于列表或库](apply-irm-to-a-list-or-library.md)。</span><span class="sxs-lookup"><span data-stu-id="279e9-126">For more information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="279e9-127">当网站所有者为列表或库启用 IRM 时，他们可以保护该列表或库中的任何受支持的文件类型。</span><span class="sxs-lookup"><span data-stu-id="279e9-127">When site owners enable IRM for a list or library, they can protect any supported file types in that list or library.</span></span> <span data-ttu-id="279e9-128">对库启用 IRM 时，权限管理将应用于该库中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="279e9-128">When IRM is enabled for a library, rights management applies to all of the files in that library.</span></span> <span data-ttu-id="279e9-129">为列表启用 IRM 时，权限管理仅适用于附加到列表项（而不是实际列表项）的文件。</span><span class="sxs-lookup"><span data-stu-id="279e9-129">When you enable IRM for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="279e9-130">当用户下载启用 IRM 的列表或库中的文件时，将对这些文件进行加密，以便仅获得授权的用户可以查看这些文件。</span><span class="sxs-lookup"><span data-stu-id="279e9-130">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them.</span></span> <span data-ttu-id="279e9-131">每个权限管理文件还包含一个发布许可证，该许可证对查看文件的人员施加限制。</span><span class="sxs-lookup"><span data-stu-id="279e9-131">Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file.</span></span> <span data-ttu-id="279e9-132">典型限制包括将文件设为只读、禁用文本复制、阻止用户保存本地副本以及阻止用户打印文件。</span><span class="sxs-lookup"><span data-stu-id="279e9-132">Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file.</span></span> <span data-ttu-id="279e9-133">可以读取受 IRM 支持的文件类型的客户端程序使用权限管理文件中的发布许可证来强制实施这些限制。</span><span class="sxs-lookup"><span data-stu-id="279e9-133">Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions.</span></span> <span data-ttu-id="279e9-134">这是权限管理文件在下载后仍保留其保护的方式。</span><span class="sxs-lookup"><span data-stu-id="279e9-134">This is how a rights-managed file retains its protection even after it is downloaded.</span></span> <span data-ttu-id="279e9-135">若要对列表或库启用 IRM，请参阅[将信息权限管理应用于列表或库](apply-irm-to-a-list-or-library.md)。</span><span class="sxs-lookup"><span data-stu-id="279e9-135">To enable IRM on a list or library, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="279e9-136">无法在浏览器中使用 Office 在启用 IRM 的库中创建或编辑文档。</span><span class="sxs-lookup"><span data-stu-id="279e9-136">You cannot create or edit documents in an IRM-enabled library using Office in a browser.</span></span> <span data-ttu-id="279e9-137">相反，一次只能有一个人下载和编辑 IRM 加密文件。</span><span class="sxs-lookup"><span data-stu-id="279e9-137">Instead, one person at a time can download and edit IRM-encrypted files.</span></span> <span data-ttu-id="279e9-138">使用签入和签出管理*共同创作*，或跨多个用户进行创作。</span><span class="sxs-lookup"><span data-stu-id="279e9-138">Use check-in and check-out to manage  *co-authoring*  , or authoring across multiple users.</span></span> 
  
<span data-ttu-id="279e9-139">当您从受 IRM 保护的库下载 PDF 文件时，Microsoft 365 将创建一个受保护的 PDF 文件。</span><span class="sxs-lookup"><span data-stu-id="279e9-139">When you download a PDF file from an IRM-protected library, Microsoft 365 creates a protected PDF file.</span></span> <span data-ttu-id="279e9-140">文件的分机号码不会改变，但文件是受保护的。</span><span class="sxs-lookup"><span data-stu-id="279e9-140">The file's extension won't change, but the file is protected.</span></span> <span data-ttu-id="279e9-141">若要查看此文件，你将需要 Azure 信息保护查看器、完整的 Azure 信息保护客户端或其他支持查看受保护的 PDF 文件的应用程序。</span><span class="sxs-lookup"><span data-stu-id="279e9-141">To view this file you'll need the Azure Information Protection viewer, the full Azure Information Protection client, or another application that supports viewing protected PDF files.</span></span> 
  
<span data-ttu-id="279e9-142">SharePoint Online 支持对以下文件类型进行加密：</span><span class="sxs-lookup"><span data-stu-id="279e9-142">SharePoint Online supports encryption of the following file types:</span></span>
  
- <span data-ttu-id="279e9-143">PDF</span><span class="sxs-lookup"><span data-stu-id="279e9-143">PDF</span></span>
    
- <span data-ttu-id="279e9-144">以下 Microsoft Office 程序的97-2003 文件格式： Word、Excel 和 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="279e9-144">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="279e9-145">适用于以下 Microsoft Office 程序的 Office Open XML 格式： Word、Excel 和 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="279e9-145">The Office Open XML formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="279e9-146">XML 纸张规范（XPS）格式</span><span class="sxs-lookup"><span data-stu-id="279e9-146">The XML Paper Specification (XPS) format</span></span>
 
> [!NOTE]
> <span data-ttu-id="279e9-147">IRM 保护无法应用于受保护的文档（如数字签名的 PDF 文件），因为 SharePoint 需要在上载时打开文档。</span><span class="sxs-lookup"><span data-stu-id="279e9-147">IRM protection cannot be applied to protected documents (like digitally signed PDF files) as SharePoint needs to open the document on upload.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="279e9-148">后续步骤</span><span class="sxs-lookup"><span data-stu-id="279e9-148">Next steps</span></span>
<span data-ttu-id="279e9-149"><a name="__toc220831191"> </a></span><span class="sxs-lookup"><span data-stu-id="279e9-149"><a name="__toc220831191"> </a></span></span>

<span data-ttu-id="279e9-150">为 SharePoint Online 启用 IRM 后，可以开始将权限管理应用于列表和库。</span><span class="sxs-lookup"><span data-stu-id="279e9-150">Once you've enabled IRM for SharePoint Online, you can start applying rights management to lists and libraries.</span></span> <span data-ttu-id="279e9-151">有关信息，请参阅[将信息权限管理应用于列表或库](apply-irm-to-a-list-or-library.md)。</span><span class="sxs-lookup"><span data-stu-id="279e9-151">For information, see [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).</span></span>
  
<span data-ttu-id="279e9-152">新的 OneDrive 同步客户端现在支持同步受 IRM 保护的 SharePoint 文档库和 OneDrive 位置（只要库的 IRM 设置未设置为 "过期文档访问权限"）。</span><span class="sxs-lookup"><span data-stu-id="279e9-152">The new OneDrive sync client for Windows now supports synchronizing IRM-protected SharePoint document libraries and OneDrive locations (as long as the IRM setting for the library isn't set to expire document access rights).</span></span> <span data-ttu-id="279e9-153">有关详细信息，或者若要开始部署新的同步客户端，请参阅[部署新的 OneDrive 同步客户端 For Windows](https://docs.microsoft.com/onedrive/deploy-on-windows)。</span><span class="sxs-lookup"><span data-stu-id="279e9-153">For more information, or to get started deploying the new sync client, see [Deploy the new OneDrive sync client for Windows](https://docs.microsoft.com/onedrive/deploy-on-windows).</span></span>
  
[<span data-ttu-id="279e9-154">页面顶部</span><span class="sxs-lookup"><span data-stu-id="279e9-154">Top of page</span></span>](set-up-irm-in-sp-admin-center.md)
