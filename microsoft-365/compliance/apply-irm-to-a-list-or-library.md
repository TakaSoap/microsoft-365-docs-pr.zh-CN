---
title: 将信息权限管理 (IRM) 列表或库
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
ms.collection:
- M365-security-compliance
- SPO_Content
description: 您可以使用信息权限管理 (IRM) 来帮助控制和保护从列表或库下载的文件。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0648d511ee882765f1905e83ebdea673f306c186
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233348"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a><span data-ttu-id="c2c1c-103">将信息权限管理 (IRM) 列表或库</span><span class="sxs-lookup"><span data-stu-id="c2c1c-103">Apply Information Rights Management (IRM) to a list or library</span></span>

<span data-ttu-id="c2c1c-104">您可以使用信息权限管理 (IRM) 来帮助控制和保护从列表或库下载的文件。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-104">You can use Information Rights Management (IRM) to help control and protect files that are downloaded from lists or libraries.</span></span> <span data-ttu-id="c2c1c-105">此功能仅在 Microsoft 全局云中受支持。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-105">This feature is only supported in the Microsoft global cloud.</span></span> <span data-ttu-id="c2c1c-106">国家云部署中的 SharePoint 列表和库不支持 IRM。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-106">IRM is not supported for SharePoint lists and libraries in national cloud deployments.</span></span>
  
## <a name="administrator-preparations-before-applying-irm"></a><span data-ttu-id="c2c1c-107">应用 IRM 之前管理员准备</span><span class="sxs-lookup"><span data-stu-id="c2c1c-107">Administrator preparations before applying IRM</span></span>

- <span data-ttu-id="c2c1c-108">Azure 权限管理服务 (Azure RMS) Azure 信息保护，本地等效的 Active Directory Rights Management Services (AD RMS) 支持网站的信息权限管理。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-108">The Azure Rights Management service (Azure RMS) from Azure Information Protection, and the on-premises equivalent, Active Directory Rights Management Services (AD RMS), support Information Rights Management for sites.</span></span> <span data-ttu-id="c2c1c-109">无需单独安装或其他安装。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-109">No separate or additional installations are required.</span></span>

- <span data-ttu-id="c2c1c-110">在将 IRM 应用到列表或库之前，需要为网站启用 IRM。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-110">Before you apply IRM to a list or library, you need to enable IRM for your site.</span></span> <span data-ttu-id="c2c1c-111">需要管理员权限才能启用 IRM。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-111">You'll need administrator permissions to enable IRM.</span></span>

- <span data-ttu-id="c2c1c-112">若要将 IRM 应用于列表或库，您必须具有该列表或库的管理员权限。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-112">To apply IRM to a list or library, you must have administrator permissions for that list or library.</span></span>

- <span data-ttu-id="c2c1c-113">如果使用的是 SharePoint Online，用户在下载受 IRM 保护的较大文件时可能会遇到超时。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-113">If you're using SharePoint Online, your users might experience timeouts when downloading larger IRM-protected files.</span></span> <span data-ttu-id="c2c1c-114">若要避免超时，请使用 Office 程序应用 IRM 保护，将较大的文件存储在不使用 IRM 的 SharePoint 库中。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-114">To avoid timeouts, use your Office programs to apply IRM protection, and store larger files in a SharePoint library that doesn't use IRM.</span></span>

> [!NOTE]
> <span data-ttu-id="c2c1c-115">如果使用的是 SharePoint Server 2013，则服务器管理员必须在所有前端 Web 服务器上为组织成员希望使用 IRM 保护的每种文件类型安装保护程序。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-115">If you're using SharePoint Server 2013, a server administrator must install protectors on all front-end Web servers for every file type that the people in your organization want to protect by using IRM.</span></span>
  
## <a name="apply-irm-to-a-list-or-library"></a><span data-ttu-id="c2c1c-116">将 IRM 应用于列表或库</span><span class="sxs-lookup"><span data-stu-id="c2c1c-116">Apply IRM to a list or library</span></span>
<span data-ttu-id="c2c1c-117"><a name="__toc256598179"> </a></span><span class="sxs-lookup"><span data-stu-id="c2c1c-117"><a name="__toc256598179"> </a></span></span>

![信息权限管理设置](../media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. <span data-ttu-id="c2c1c-119">转到要配置 IRM 的列表或库。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-119">Go to the list or library for which you want to configure IRM.</span></span>

2. <span data-ttu-id="c2c1c-120">在功能区上，选择 **"库"** 选项卡，然后选择"**库设置"。**</span><span class="sxs-lookup"><span data-stu-id="c2c1c-120">On the ribbon, select the **Library** tab, and then select **Library Settings**.</span></span> <span data-ttu-id="c2c1c-121"> (如果在列表中工作，请选择"列表"选项卡，然后选择"列表设置 **") 。**</span><span class="sxs-lookup"><span data-stu-id="c2c1c-121">(If you're working in a list, select the **List** tab, and then select **List Settings**).</span></span>
    
    ![功能区上的 SharePoint 库设置按钮](../media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. <span data-ttu-id="c2c1c-123">在 **"权限和管理"下**，**选择"信息权限管理"。**</span><span class="sxs-lookup"><span data-stu-id="c2c1c-123">Under **Permissions and Management**, select **Information Rights Management**.</span></span> <span data-ttu-id="c2c1c-124">如果未显示信息权限管理链接，可能无法为您的网站启用 IRM。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-124">If the Information Rights Management link doesn't appear, IRM might not be enabled for your site.</span></span> <span data-ttu-id="c2c1c-125">请与服务器管理员联系，查看能否为网站启用 IRM。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-125">Contact your server administrator to see if you can enable IRM for your site.</span></span> <span data-ttu-id="c2c1c-126">图片 **库** 不会显示"信息权限管理"链接。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-126">The **Information Rights Management** link doesn't appear for picture libraries.</span></span>

4. <span data-ttu-id="c2c1c-127">在 **"信息权限管理设置**"页上，选中"下载时限制此库中的文档的权限"复选框，以将受限权限应用于用户从此列表或库中下载的文档。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-127">On the **Information Rights Management Settings** page, select the **Restrict permission to documents in this library on download** check box to apply restricted permission to documents users download from this list or library.</span></span>

5. <span data-ttu-id="c2c1c-128">在 **"创建权限策略标题"框中** ，输入策略的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-128">In the **Create a permission policy title** box, enter a descriptive name for the policy.</span></span> <span data-ttu-id="c2c1c-129">使用可帮助您从其他策略识别此策略的名称。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-129">Use a name that helps you identify this policy from other policies.</span></span> <span data-ttu-id="c2c1c-130">例如，使用 **公司** 机密将受限权限应用于包含机密公司文档的列表或库。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-130">For example, use **Company Confidential** to apply restricted permissions to a list or library that contains confidential company documents.</span></span>

6. <span data-ttu-id="c2c1c-131">在"添加权限 **策略** 说明"框中，键入对使用此列表或库的用户显示的说明，说明他们应如何处理此列表或库中的文档。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-131">In the **Add a permission policy description** box, type a description that will appear to people who use this list or library that explains how they should handle the documents in this list or library.</span></span> <span data-ttu-id="c2c1c-132">例如，如果要将访问这些文档中的信息限制为内部员工，可以只与其他员工键入"讨论本文档的内容"。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-132">For example, you can type **Discuss the contents of this document only with other employees** if you want to restrict access to the information in these documents to internal employees.</span></span> 

7. <span data-ttu-id="c2c1c-133">若要对此列表或库中的文档应用其他限制，请选择"显示选项"，然后执行下列任一操作： </span><span class="sxs-lookup"><span data-stu-id="c2c1c-133">To apply additional restrictions to the documents in this list or library, select **Show Options**, and do any of the following:</span></span>

|<span data-ttu-id="c2c1c-134">**为此，请执行以下操作：**</span><span class="sxs-lookup"><span data-stu-id="c2c1c-134">**To do this:**</span></span>|<span data-ttu-id="c2c1c-135">**为此：**</span><span class="sxs-lookup"><span data-stu-id="c2c1c-135">**Do this:**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c2c1c-136">允许用户从此列表或库中打印文档</span><span class="sxs-lookup"><span data-stu-id="c2c1c-136">Allow people to print documents from this list or library</span></span>|<span data-ttu-id="c2c1c-137">选中 **"允许查看者打印"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-137">Select the **Allow viewers to print** check box.</span></span>|
|<span data-ttu-id="c2c1c-138">允许至少具有"查看项目"权限的用户对文档运行嵌入代码或宏。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-138">Allow people with at least the View Items permission to run embedded code or macros on a document.</span></span>|<span data-ttu-id="c2c1c-139">选中 **"允许查看者运行脚本和屏幕阅读器以对下载的文档** 运行功能"复选框。如果选择此选项，则用户可以运行代码来提取文档的内容。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-139">Select the **Allow viewers to run script and screen reader to function on downloaded documents** check box.If you select this option, users could run code to extract the contents of a document.</span></span>           |
|<span data-ttu-id="c2c1c-140">如果要将内容访问限制为指定时间段，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-140">Select this option if you want to restrict access to content to a specified period of time.</span></span> <span data-ttu-id="c2c1c-141">如果选择此选项，访问内容的颁发许可证将在指定的天数后过期，并且用户需要返回到服务器以验证其凭据并下载新副本。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-141">If you select this option, people's issuance licenses to access the content will expire after the specified number of days, and people will be required to return to the server to verify their credentials and download a new copy.</span></span>|<span data-ttu-id="c2c1c-142">选中"下载后，文档访问权限将在这些天数 **后过期 (1-365) "** 复选框，然后指定您希望文档可查看的天数。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-142">Select the **After download, document access rights will expire after these number of days (1-365)** check box, and then specify the number of days for which you want the document to be viewable.</span></span>|
| <span data-ttu-id="c2c1c-143">阻止用户将不支持 IRM 的文档上载到此列表或库。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-143">Prevent people from uploading documents that do not support IRM to this list or library.</span></span> <span data-ttu-id="c2c1c-144">如果选择此选项，用户将无法上载以下任何文件类型：未在所有前端 Web 服务器上安装相应 IRM 保护程序的文件类型。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-144">If you select this option, people will not be able to upload any of the following file types: File types that do not have corresponding IRM protectors installed on all of the front-end web servers.</span></span> <span data-ttu-id="c2c1c-145">SharePoint Server 2010 无法解密的文件类型。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-145">File types that SharePoint Server 2010 cannot decrypt.</span></span> <span data-ttu-id="c2c1c-146">在另一个程序中受 IRM 保护的文件类型。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-146">File types that are IRM protected in another program.</span></span>|<span data-ttu-id="c2c1c-147">选中 **"不允许用户上载不支持 IRM** 的文档"复选框。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-147">Select the **Do not allow users to upload documents that do not support IRM** check box.</span></span>|
|<span data-ttu-id="c2c1c-148">在特定的日期从此列表或库中删除受限权限。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-148">Remove restricted permissions from this list or library on a specific date.</span></span>|<span data-ttu-id="c2c1c-149">选中 **"停止限制对** 库的访问"复选框，然后选择需要的日期。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-149">Select the **Stop restricting access to the library at** check box, and then select the date that you want.</span></span>|
|<span data-ttu-id="c2c1c-150">控制为授权打开文档的程序缓存凭据的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-150">Control the interval that credentials are cached for the program that is licensed to open the document.</span></span>|<span data-ttu-id="c2c1c-151">选中 **"用户必须使用** 此间隔验证其凭据 (天) 复选框，然后输入缓存凭据的间隔（以天为单位）。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-151">Select the **Users must verify their credentials using this interval (days)** check box, then enter the interval for caching credentials in number of days.</span></span>|
|<span data-ttu-id="c2c1c-152">允许组保护，以便用户可以与同一组的成员共享。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-152">Allow group protection so that users can share with members of the same group.</span></span>|<span data-ttu-id="c2c1c-153">选择 **"允许组保护**"，然后输入组的名称进行共享。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-153">Select **Allow group protection**, and enter the group's name for sharing.</span></span>|

8. <span data-ttu-id="c2c1c-154">选择完想要的选项后，选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="c2c1c-154">After you finish selecting the options you want, select **OK**.</span></span>
  
## <a name="what-is-information-rights-management"></a><span data-ttu-id="c2c1c-155">什么是信息权限管理？</span><span class="sxs-lookup"><span data-stu-id="c2c1c-155">What is Information Rights Management?</span></span>
<span data-ttu-id="c2c1c-156"><a name="__toc256598175"> </a></span><span class="sxs-lookup"><span data-stu-id="c2c1c-156"><a name="__toc256598175"> </a></span></span>

<span data-ttu-id="c2c1c-157">信息权限 (IRM) 使您可以限制用户可以对从列表或库下载的文件采取的操作。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-157">Information Rights Management (IRM) enables you to limit the actions that users can take on files that have been downloaded from lists or libraries.</span></span> <span data-ttu-id="c2c1c-158">IRM 对下载的文件进行加密并限制允许解密这些文件的用户和程序组。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-158">IRM encrypts the downloaded files and limits the set of users and programs that are allowed to decrypt these files.</span></span> <span data-ttu-id="c2c1c-159">IRM 还可限制允许读取文件的用户的权限，以便这些用户无法执行打印文件的副本或复制文件中的文本等操作。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-159">IRM can also limit the rights of the users who are allowed to read files, so that they cannot take actions such as print copies of the files or copy text from them.</span></span>
  
<span data-ttu-id="c2c1c-160">可以在列表或库上使用 IRM 来限制敏感内容的传播。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-160">You can use IRM on lists or libraries to limit the dissemination of sensitive content.</span></span> <span data-ttu-id="c2c1c-161">例如，如果要创建一个文档库来与选定的营销代表共享即将推出的产品的信息，可以使用 IRM 阻止这些人员与公司的其他员工共享此内容。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-161">For example, if you are creating a document library to share information about upcoming products with selected marketing representatives, you can use IRM to prevent these individuals from sharing this content with other employees in the company.</span></span>
  
<span data-ttu-id="c2c1c-162">在站点上，将 IRM 应用于整个列表或库，而不是单个文件。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-162">On a site, you apply IRM to an entire list or library, rather than to individual files.</span></span> <span data-ttu-id="c2c1c-163">这样一来，可以更轻松地确保对一组文档或文件的一致保护。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-163">This makes it easier to ensure a consistent level of protection for an entire set of documents or files.</span></span> <span data-ttu-id="c2c1c-164">因此，IRM 可帮助组织强制执行管理机密或专有信息的使用和分发的公司策略。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-164">IRM can thus help your organization to enforce corporate policies that govern the use and dissemination of confidential or proprietary information.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c2c1c-165">此页上有关信息权限管理的信息将取代任何 Microsoft SharePoint Server 2013 和 SharePoint Server 2016 许可条款协议中引用"信息权限管理"的任何术语。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-165">The information on this page regarding Information Rights Management supersedes any terms that reference 'Information Rights Management' in any Microsoft SharePoint Server 2013 and SharePoint Server 2016 license term agreements.</span></span> 
  
### <a name="how-irm-can-help-protect-content"></a><span data-ttu-id="c2c1c-166">IRM 如何帮助保护内容</span><span class="sxs-lookup"><span data-stu-id="c2c1c-166">How IRM can help protect content</span></span>
<span data-ttu-id="c2c1c-167"><a name="__toc256598176"> </a></span><span class="sxs-lookup"><span data-stu-id="c2c1c-167"><a name="__toc256598176"> </a></span></span>

<span data-ttu-id="c2c1c-168">IRM 通过以下方式帮助保护受限制的内容：</span><span class="sxs-lookup"><span data-stu-id="c2c1c-168">IRM helps to protect restricted content in the following ways:</span></span>
  
- <span data-ttu-id="c2c1c-169">有助于防止授权查看者复制、修改、打印、传真或复制和粘贴内容以未经授权</span><span class="sxs-lookup"><span data-stu-id="c2c1c-169">Helps to prevent an authorized viewer from copying, modifying, printing, faxing, or copying and pasting the content for unauthorized use</span></span>
    
- <span data-ttu-id="c2c1c-170">有助于防止授权查看器使用 Microsoft Windows 中的打印屏幕功能复制内容</span><span class="sxs-lookup"><span data-stu-id="c2c1c-170">Helps to prevent an authorized viewer from copying the content by using the Print Screen feature in Microsoft Windows</span></span>
    
- <span data-ttu-id="c2c1c-171">有助于防止未经授权的查看器在从服务器下载内容后以电子邮件方式发送内容时查看内容</span><span class="sxs-lookup"><span data-stu-id="c2c1c-171">Helps to prevent an unauthorized viewer from viewing the content if it is sent in e-mail after it is downloaded from the server</span></span>
    
- <span data-ttu-id="c2c1c-172">将内容访问限制在指定的时段内，在此时间段之后，用户必须确认其凭据并再次下载内容</span><span class="sxs-lookup"><span data-stu-id="c2c1c-172">Restricts access to content to a specified period of time, after which users must confirm their credentials and download the content again</span></span>
    
- <span data-ttu-id="c2c1c-173">帮助强制执行管理组织内内容的使用和分发的公司策略</span><span class="sxs-lookup"><span data-stu-id="c2c1c-173">Helps to enforce corporate policies that govern the use and dissemination of content within your organization</span></span>
    
### <a name="how-irm-cannot-help-protect-content"></a><span data-ttu-id="c2c1c-174">IRM 如何帮助保护内容</span><span class="sxs-lookup"><span data-stu-id="c2c1c-174">How IRM cannot help protect content</span></span>
<span data-ttu-id="c2c1c-175"><a name="__toc256598177"> </a></span><span class="sxs-lookup"><span data-stu-id="c2c1c-175"><a name="__toc256598177"> </a></span></span>

<span data-ttu-id="c2c1c-176">IRM 无法保护受限内容免受以下限制：</span><span class="sxs-lookup"><span data-stu-id="c2c1c-176">IRM cannot protect restricted content from the following:</span></span>
  
- <span data-ttu-id="c2c1c-177">恶意程序（如特洛伊木马、击键记录程序和某些类型的间谍软件）清除、盗窃、捕获或传输</span><span class="sxs-lookup"><span data-stu-id="c2c1c-177">Erasure, theft, capture, or transmission by malicious programs such as Trojan horses, keystroke loggers, and certain types of spyware</span></span>
    
- <span data-ttu-id="c2c1c-178">由于计算机病毒的操作而丢失或损坏</span><span class="sxs-lookup"><span data-stu-id="c2c1c-178">Loss or corruption because of the actions of computer viruses</span></span>
    
- <span data-ttu-id="c2c1c-179">手动复制或重新设置屏幕上的显示内容</span><span class="sxs-lookup"><span data-stu-id="c2c1c-179">Manual copying or retyping of content from the display on a screen</span></span>
    
- <span data-ttu-id="c2c1c-180">屏幕上显示的内容的数字或电影放映</span><span class="sxs-lookup"><span data-stu-id="c2c1c-180">Digital or film photography of content that is displayed on a screen</span></span>
    
- <span data-ttu-id="c2c1c-181">使用第三方屏幕捕获程序进行复制</span><span class="sxs-lookup"><span data-stu-id="c2c1c-181">Copying through the use of third-party screen-capture programs</span></span>
    
- <span data-ttu-id="c2c1c-182">使用第三 (捕获程序或复制粘贴) 复制列值复制内容元数据</span><span class="sxs-lookup"><span data-stu-id="c2c1c-182">Copying of content metadata (column values) through the use of third-party screen-capture programs or copy-and-paste action</span></span>
  
## <a name="how-irm-works-for-lists-and-libraries"></a><span data-ttu-id="c2c1c-183">IRM 如何用于列表和库</span><span class="sxs-lookup"><span data-stu-id="c2c1c-183">How IRM works for lists and libraries</span></span>
<span data-ttu-id="c2c1c-184"><a name="__toc256598178"> </a></span><span class="sxs-lookup"><span data-stu-id="c2c1c-184"><a name="__toc256598178"> </a></span></span>

<span data-ttu-id="c2c1c-185">IRM 保护应用于列表或库级别的文件。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-185">IRM protection is applied to files at the list or library level.</span></span> <span data-ttu-id="c2c1c-186">为库启用 IRM 后，权限管理将应用于该库中的所有文件。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-186">When IRM is enabled for a library, rights management applies to all of the files in that library.</span></span> <span data-ttu-id="c2c1c-187">为列表启用 IRM 时，权限管理仅适用于附加到列表项的文件，而不是实际列表项。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-187">When IRM is enabled for a list, rights management applies only to files that are attached to list items, not the actual list items.</span></span>
  
<span data-ttu-id="c2c1c-188">当用户在启用 IRM 的列表或库中下载文件时，文件会进行加密，以便只有授权人员才能查看它们。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-188">When people download files in an IRM-enabled list or library, the files are encrypted so that only authorized people can view them.</span></span> <span data-ttu-id="c2c1c-189">每个权限管理文件还包含对查看该文件的人施加限制的发布许可证。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-189">Each rights-managed file also contains an issuance license that imposes restrictions on the people who view the file.</span></span> <span data-ttu-id="c2c1c-190">典型限制包括使文件成为只读文件、禁用文本复制、阻止用户保存本地副本以及阻止用户打印文件。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-190">Typical restrictions include making a file read-only, disabling the copying of text, preventing people from saving a local copy, and preventing people from printing the file.</span></span> <span data-ttu-id="c2c1c-191">可读取支持 IRM 的文件类型的客户端程序使用权限管理文件内的发布许可证强制实施这些限制。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-191">Client programs that can read IRM-supported file types use the issuance license within the rights-managed file to enforce these restrictions.</span></span> <span data-ttu-id="c2c1c-192">这是权限管理文件在从服务器下载后仍保留其保护的方式。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-192">This is how a rights-managed file retains its protection even after it is downloaded from the server.</span></span>
  
<span data-ttu-id="c2c1c-193">从列表或库下载文件时应用于文件的限制类型基于单个用户对包含该文件的网站的权限。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-193">The types of restrictions that are applied to a file when it is downloaded from a list or library are based on the individual user's permissions on the site that contains the file.</span></span> <span data-ttu-id="c2c1c-194">下表说明了网站权限如何与 IRM 权限对应。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-194">The following table explains how the permissions on sites correspond to IRM permissions.</span></span>
  
|<span data-ttu-id="c2c1c-195">**权限**</span><span class="sxs-lookup"><span data-stu-id="c2c1c-195">**Permissions**</span></span>|<span data-ttu-id="c2c1c-196">**IRM 权限**</span><span class="sxs-lookup"><span data-stu-id="c2c1c-196">**IRM Permissions**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c2c1c-197">管理权限、管理网站</span><span class="sxs-lookup"><span data-stu-id="c2c1c-197">Manage Permissions, Manage Web Site</span></span>|<span data-ttu-id="c2c1c-198">**客户端** (定义的完全控制权限) ：此权限通常允许用户读取、编辑、复制、保存和修改权限管理内容的权限。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-198">**Full control** (as defined by the client program): This permission generally allows a user to read, edit, copy, save, and modify permissions of rights-managed content.</span></span>|
|<span data-ttu-id="c2c1c-199">编辑项目、管理列表、添加和自定义页面</span><span class="sxs-lookup"><span data-stu-id="c2c1c-199">Edit Items, Manage Lists, Add and Customize Pages</span></span>|<span data-ttu-id="c2c1c-200">**编辑**、**复制** 和 **保存**：只有在列表或库的信息权限管理设置页上选中了"允许用户打印文档"复选框时，用户才能打印文件。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-200">**Edit**, **Copy**, and **Save**: A user can print a file only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>|
|<span data-ttu-id="c2c1c-201">查看项目</span><span class="sxs-lookup"><span data-stu-id="c2c1c-201">View Items</span></span>|<span data-ttu-id="c2c1c-202">**读取**：用户可以读取文档，但不能复制或修改其内容。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-202">**Read**: A user can read the document, but cannot copy or modify its content.</span></span> <span data-ttu-id="c2c1c-203">只有在列表或库的"信息权限管理设置"页上选中了"允许用户打印文档"复选框时，用户才能打印。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-203">A user can print only if the **Allow users to print documents** check box is selected on the Information Rights Management Settings page for the list or library.</span></span>|
|<span data-ttu-id="c2c1c-204">其他</span><span class="sxs-lookup"><span data-stu-id="c2c1c-204">Other</span></span>|<span data-ttu-id="c2c1c-205">任何其他权限都直接与 IRM 权限对应。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-205">No other permissions correspond directly to IRM permissions.</span></span>|
   
<span data-ttu-id="c2c1c-206">在 SharePoint Server 2013 中为列表或库启用 IRM 时，只能保护所有前端 Web 服务器上安装了保护程序的列表或库中的文件类型。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-206">When you enable IRM for a list or library in SharePoint Server 2013, you can only protect file types in that list or library for which a protector is installed on all front-end web servers.</span></span> <span data-ttu-id="c2c1c-207">保护程序是控制特定文件格式权限管理文件的加密和解密的程序。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-207">A protector is a program that controls the encryption and decryption of rights-managed files of a specific file format.</span></span> <span data-ttu-id="c2c1c-208">SharePoint 包括以下文件类型的保护程序：</span><span class="sxs-lookup"><span data-stu-id="c2c1c-208">SharePoint includes protectors for the following file types:</span></span>
  
- <span data-ttu-id="c2c1c-209">Microsoft Office InfoPath 表单</span><span class="sxs-lookup"><span data-stu-id="c2c1c-209">Microsoft Office InfoPath forms</span></span>
    
- <span data-ttu-id="c2c1c-210">以下 97-2003 文件格式Microsoft Office Word、Excel 和 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c2c1c-210">The 97-2003 file formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="c2c1c-211">以下应用程序的程序的 Office Open XML Microsoft Office：Word、Excel 和 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c2c1c-211">The Office Open XML Formats for the following Microsoft Office programs: Word, Excel, and PowerPoint</span></span>
    
- <span data-ttu-id="c2c1c-212">XML 纸张规范 (XPS) 格式</span><span class="sxs-lookup"><span data-stu-id="c2c1c-212">The XML Paper Specification (XPS) format</span></span>
    
<span data-ttu-id="c2c1c-213">如果组织计划使用 IRM 保护除上面列出的文件类型之外的其他任何文件类型，则服务器管理员必须安装这些其他文件格式的保护程序。</span><span class="sxs-lookup"><span data-stu-id="c2c1c-213">If your organization plans to use IRM to protect any other file types in addition to those listed above, your server administrator must install protectors for these additional file formats.</span></span>
  

