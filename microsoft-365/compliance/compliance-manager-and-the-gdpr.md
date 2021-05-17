---
title: Microsoft 合规性管理器和 GDPR
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合规性管理器是 Microsoft 服务信任门户中基于工作流的免费风险评估工具。 合规性管理器使你能够跟踪、分配和验证与 Microsoft 云服务相关的法规合规性活动。
ms.openlocfilehash: 69e6551620fb654cb09d46554e6e3c98b6a2fc60
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595799"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a><span data-ttu-id="ebd49-104">Microsoft 合规性管理器和 GDPR</span><span class="sxs-lookup"><span data-stu-id="ebd49-104">Microsoft Compliance Manager and the GDPR</span></span>

<span data-ttu-id="ebd49-105">根据欧盟 (GDPR) 一般数据保护条例可能会影响合规性策略，并强制采取特定操作来管理合规性管理器中使用的用户和客户信息。</span><span class="sxs-lookup"><span data-stu-id="ebd49-105">The General Data Protection Regulation (GDPR) enacted by the European Union can impact your compliance strategy and mandate specific actions to manage user and customer information used in Compliance Manager.</span></span>

## <a name="user-privacy-settings"></a><span data-ttu-id="ebd49-106">用户隐私设置</span><span class="sxs-lookup"><span data-stu-id="ebd49-106">User Privacy settings</span></span>

<span data-ttu-id="ebd49-107">某些法规要求组织必须能够删除用户历史记录数据。</span><span class="sxs-lookup"><span data-stu-id="ebd49-107">Certain regulations require that an organization must be able to delete user history data.</span></span> <span data-ttu-id="ebd49-108">合规性管理器 **提供用户隐私设置** 功能，使管理员能够：</span><span class="sxs-lookup"><span data-stu-id="ebd49-108">Compliance Manager provides **User Privacy Settings** functions that allow administrators to:</span></span>
  
- [<span data-ttu-id="ebd49-109">搜索用户</span><span class="sxs-lookup"><span data-stu-id="ebd49-109">Search for a user</span></span>](#search-for-a-user)
- [<span data-ttu-id="ebd49-110">导出帐户数据历史记录报告</span><span class="sxs-lookup"><span data-stu-id="ebd49-110">Export a report of account data history</span></span>](#export-a-report-of-account-data-history)
- [<span data-ttu-id="ebd49-111">删除用户数据历史记录</span><span class="sxs-lookup"><span data-stu-id="ebd49-111">Delete user data history</span></span>](#delete-user-data-history)
  
## <a name="search-for-a-user"></a><span data-ttu-id="ebd49-112">搜索用户</span><span class="sxs-lookup"><span data-stu-id="ebd49-112">Search for a user</span></span>

<span data-ttu-id="ebd49-113">若要搜索用户帐户，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ebd49-113">To search for a user account:</span></span>
  
1. <span data-ttu-id="ebd49-114">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the domain suffix list on the right.</span><span class="sxs-lookup"><span data-stu-id="ebd49-114">Enter the user email alias (the information to the left of the @ symbol) and choose the domain name from the  domain suffix list on the right.</span></span> <span data-ttu-id="ebd49-115">对于具有多个注册域的组织，请仔细检查域名后缀以确保其正确无误。</span><span class="sxs-lookup"><span data-stu-id="ebd49-115">For organizations with multiple registered domains, double check the domain name suffix to ensure that it is correct.</span></span>

2. <span data-ttu-id="ebd49-116">正确输入用户名后，请选择"搜索 **"。**</span><span class="sxs-lookup"><span data-stu-id="ebd49-116">When you have the username correctly entered, select **Search**.</span></span>

3. <span data-ttu-id="ebd49-117">对于未返回的用户帐户，页面将显示未找到 **用户**。</span><span class="sxs-lookup"><span data-stu-id="ebd49-117">For user accounts not returned, the page displays **User not found**.</span></span> <span data-ttu-id="ebd49-118">检查用户的电子邮件地址信息并在必要时进行更正。</span><span class="sxs-lookup"><span data-stu-id="ebd49-118">Check the user's email address information and make corrections as necessary.</span></span> <span data-ttu-id="ebd49-119">若要重试，请选择"搜索 **"。**</span><span class="sxs-lookup"><span data-stu-id="ebd49-119">To retry, select **Search**.</span></span>

4. <span data-ttu-id="ebd49-120">对于返回的用户帐户，按钮文本从 **"搜索"** 更改为 **"清除"。**</span><span class="sxs-lookup"><span data-stu-id="ebd49-120">For user accounts returned, the text of the button changes from **Search** to **Clear**.</span></span> <span data-ttu-id="ebd49-121">这表示返回的用户帐户是其他函数的操作上下文，并且这些函数适用于此用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ebd49-121">This indicates that the returned user account is the operating context for the additional functions and that these functions apply to this user account.</span></span>

5. <span data-ttu-id="ebd49-122">若要清除搜索结果并搜索其他用户，请选择"清除 **"。**</span><span class="sxs-lookup"><span data-stu-id="ebd49-122">To clear search results and search for a different user, select **Clear**.</span></span>

## <a name="export-a-report-of-account-data-history"></a><span data-ttu-id="ebd49-123">导出帐户数据历史记录报告</span><span class="sxs-lookup"><span data-stu-id="ebd49-123">Export a report of account data history</span></span>

<span data-ttu-id="ebd49-124">对于标识的每个用户帐户，可以生成链接到该帐户的依赖关系报告。</span><span class="sxs-lookup"><span data-stu-id="ebd49-124">For each user account identified, you can generate a report of dependencies linked to the account.</span></span> <span data-ttu-id="ebd49-125">此信息允许你重新分配打开的操作项或确保访问以前上载的证据。</span><span class="sxs-lookup"><span data-stu-id="ebd49-125">This information allows you to reassign open Action Items or ensure access to previously uploaded evidence.</span></span>
  
 <span data-ttu-id="ebd49-126">若要生成并导出报告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ebd49-126">To generate and export a report:</span></span>
  
1. <span data-ttu-id="ebd49-127">选择 **"** 导出"可生成并下载当前分配给返回用户帐户的合规性管理器控制行动项的报告，以及该用户上载的文档列表。</span><span class="sxs-lookup"><span data-stu-id="ebd49-127">Select **Export** to generate and download a report of the Compliance Manager control Action Items currently assigned to the returned user account, and the list of documents uploaded by that user.</span></span> <span data-ttu-id="ebd49-128">如果没有分配的操作或上载的文档，则会显示一条错误消息，指出"此用户没有数据"。</span><span class="sxs-lookup"><span data-stu-id="ebd49-128">If there are no assigned actions or uploaded documents, an error message states "No data for this user".</span></span>

2. <span data-ttu-id="ebd49-129">如果看不到要检查浏览器下载历史记录的下载弹出窗口，报告将下载到活动浏览器窗口的后台。</span><span class="sxs-lookup"><span data-stu-id="ebd49-129">The report downloads in the background of the active browser window — if you don't see a download popup that you want to check your browser download history.</span></span>

3. <span data-ttu-id="ebd49-130">打开文档即可查看报告数据。</span><span class="sxs-lookup"><span data-stu-id="ebd49-130">Open the document to review the report data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebd49-131">报表数据不是保留并显示对操作项分配历史记录的状态更改的历史列表。</span><span class="sxs-lookup"><span data-stu-id="ebd49-131">The report data is not a historical list that retains and displays state changes to Action Item assignment history.</span></span> <span data-ttu-id="ebd49-132">生成的报告是运行报告时分配的控件行动项的快照 (日期和时间戳写入报告) 。</span><span class="sxs-lookup"><span data-stu-id="ebd49-132">The generated report is a snapshot of the control Action Items assigned at the time that the report is run (date and time stamp written into the report).</span></span> <span data-ttu-id="ebd49-133">例如，如果为同一用户再次生成报告，则任何后续行动项重新分配都会导致不同的快照报告数据。</span><span class="sxs-lookup"><span data-stu-id="ebd49-133">For example, any subsequent reassignment of Action Items result in different snapshot report data if the report is generated again for the same user.</span></span>
  
## <a name="delete-user-data-history"></a><span data-ttu-id="ebd49-134">删除用户数据历史记录</span><span class="sxs-lookup"><span data-stu-id="ebd49-134">Delete user data history</span></span>

<span data-ttu-id="ebd49-135">将分配给返回用户的所有控件操作项都设置为"未分配"。</span><span class="sxs-lookup"><span data-stu-id="ebd49-135">Sets all control Action Items assigned to the returned user to 'unassigned'.</span></span> <span data-ttu-id="ebd49-136">将 **返回用户上载** 的任何文档的上传值设置为"已删除用户"。</span><span class="sxs-lookup"><span data-stu-id="ebd49-136">Sets the **uploaded by** value for any documents uploaded by the returned user to 'user removed'.</span></span>
  
<span data-ttu-id="ebd49-137">若要删除用户帐户操作项和文档上载历史记录，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ebd49-137">To delete the user account Action Item and document upload history:</span></span>
  
1. <span data-ttu-id="ebd49-138">选择“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="ebd49-138">Select **Delete**.</span></span>

    <span data-ttu-id="ebd49-139">此时将显示确认对话框："*这将删除所选用户的所有控件行动项分配和文档上载历史记录。此操作是永久性的。确定要继续吗？*"</span><span class="sxs-lookup"><span data-stu-id="ebd49-139">A confirmation dialog is displayed: "*This removes all control Action Item assignments and the document upload history for the selected user. This action is permanent. Are you sure you want to continue?*"</span></span>

2. <span data-ttu-id="ebd49-140">若要继续，请选择 **"确定"，** 否则选择"**取消"。**</span><span class="sxs-lookup"><span data-stu-id="ebd49-140">To continue select **OK**, otherwise select **Cancel**.</span></span>
