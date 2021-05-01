---
title: 在更改计划之前备份数据
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
- PPM_jmueller
ms.reviewer: jkinma
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: 在Outlook OneDrive计划Yammer备份SharePoint、Microsoft 365内容。
ms.date: 03/17/2021
ms.openlocfilehash: cdbeb7267105742082358dcd985e8fd1052a5679
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107420"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a><span data-ttu-id="1dd7e-103">在切换业务Microsoft 365之前备份数据</span><span class="sxs-lookup"><span data-stu-id="1dd7e-103">Back up data before switching Microsoft 365 for business plans</span></span>

<span data-ttu-id="1dd7e-104">如果用户将切换到具有较少数据相关服务的另一个订阅，或者用户离开组织，可以在切换到新订阅之前下载存储在 Microsoft 365 中的数据副本。</span><span class="sxs-lookup"><span data-stu-id="1dd7e-104">If a user will be switched to another subscription that has fewer data-related services or a user leaves the organization, a copy of their data that's stored in Microsoft 365 can be downloaded before they are switched to the new subscription.</span></span>

<span data-ttu-id="1dd7e-105">如果要将用户移动到具有相同或更多服务的订阅，则无需备份用户数据。</span><span class="sxs-lookup"><span data-stu-id="1dd7e-105">If you're moving a user to a subscription that has the same or more services, you don't need to back up user data.</span></span> <span data-ttu-id="1dd7e-106">请参阅 [将用户移动到其他订阅](./move-users-different-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="1dd7e-106">See [Move users to a different subscription](./move-users-different-subscription.md).</span></span>
  
## <a name="save-a-copy-of-outlook-information"></a><span data-ttu-id="1dd7e-107">保存信息Outlook副本</span><span class="sxs-lookup"><span data-stu-id="1dd7e-107">Save a copy of Outlook information</span></span>

<span data-ttu-id="1dd7e-108">如果用户已Outlook，可以在切换计划之前将电子邮件、联系人和日历导出或备份到[Outlook .pst](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91)文件中。</span><span class="sxs-lookup"><span data-stu-id="1dd7e-108">If users have Outlook, they can [export or backup email, contacts, and calendar to an Outlook .pst file](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) before their plan is switched.</span></span>
  
<span data-ttu-id="1dd7e-109">切换到新计划后，用户可以从[.pst](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)文件导入电子邮件、Outlook日历。</span><span class="sxs-lookup"><span data-stu-id="1dd7e-109">After the switch to the new plan is finished, users can [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>
  
## <a name="save-files-stored-in-onedrive-for-business"></a><span data-ttu-id="1dd7e-110">保存存储在OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="1dd7e-110">Save files stored in OneDrive for Business</span></span>

<span data-ttu-id="1dd7e-111">在切换到其他订阅之前，用户可以将文件和文件夹从 OneDrive 或[SharePoint](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05)下载到其他位置，例如计算机硬盘驱动器上的文件夹或组织网络上的文件共享。</span><span class="sxs-lookup"><span data-stu-id="1dd7e-111">Before being switched to a different subscription, users can [download files and folders from OneDrive or SharePoint](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) to a different location, such as a folder on their computer's hard drive, or a file share on the organization's network.</span></span>
  
## <a name="save-yammer-information"></a><span data-ttu-id="1dd7e-112">保存Yammer信息</span><span class="sxs-lookup"><span data-stu-id="1dd7e-112">Save Yammer information</span></span>

<span data-ttu-id="1dd7e-113">管理员可以将所有邮件、笔记、文件、主题、用户和组导出到.zip文件。</span><span class="sxs-lookup"><span data-stu-id="1dd7e-113">Admins can export all messages, notes, files, topics, users, and groups to a .zip file.</span></span> <span data-ttu-id="1dd7e-114">有关详细信息，请参阅从数据库[导出Yammer Enterprise。](/yammer/manage-security-and-compliance/export-yammer-enterprise-data)</span><span class="sxs-lookup"><span data-stu-id="1dd7e-114">For more information, see [Export data from Yammer Enterprise](/yammer/manage-security-and-compliance/export-yammer-enterprise-data).</span></span> <span data-ttu-id="1dd7e-115">开发人员可以使用[Yammer API](https://go.microsoft.com/fwlink/p/?linkid=842495)来这样做。</span><span class="sxs-lookup"><span data-stu-id="1dd7e-115">Developers can use the [Yammer API](https://go.microsoft.com/fwlink/p/?linkid=842495) to do this, as well.</span></span>
  
## <a name="how-to-save-sharepoint-information"></a><span data-ttu-id="1dd7e-116">如何保存SharePoint信息</span><span class="sxs-lookup"><span data-stu-id="1dd7e-116">How to save SharePoint information</span></span>

<span data-ttu-id="1dd7e-117">如果用户从具有 SharePoint Online 的订阅切换到没有订阅的订阅，SharePoint 磁贴将不再显示在其Microsoft 365菜单中。 </span><span class="sxs-lookup"><span data-stu-id="1dd7e-117">If a user is switched from a subscription that has SharePoint Online to one that doesn't have it, the **SharePoint** tile will no longer appear in their Microsoft 365 menu.</span></span>
  
<span data-ttu-id="1dd7e-118">但是，只要新订阅与切换自的订阅位于同一个组织中，用户仍可以访问SharePoint网站。</span><span class="sxs-lookup"><span data-stu-id="1dd7e-118">However, as long as the new subscription is within the same organization as the one they are switched from, users will still be able to access the SharePoint team site.</span></span> <span data-ttu-id="1dd7e-119">他们可以使用指向工作组网站的直接 URL 查看和更新笔记本、文档、任务和日历。</span><span class="sxs-lookup"><span data-stu-id="1dd7e-119">They can view and update notebooks, documents, tasks, and calendars by using the direct URL to the team site.</span></span>
  
> [!TIP]
> <span data-ttu-id="1dd7e-120">我们建议用户在切换订阅之前转到团队网站，并将其 URL 保存为浏览器中的收藏夹或书签。</span><span class="sxs-lookup"><span data-stu-id="1dd7e-120">We recommend that users go to the team site before their subscription is switched and save the URL as a favorite or bookmark in their browser.</span></span>
  
<span data-ttu-id="1dd7e-121">默认情况下，团队网站的 URL 格式为：</span><span class="sxs-lookup"><span data-stu-id="1dd7e-121">By default, the URL of the team website is in this form:</span></span>
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

<span data-ttu-id="1dd7e-122">其中  _\<orgDomain\>_ 是组织的 URL。</span><span class="sxs-lookup"><span data-stu-id="1dd7e-122">where  _\<orgDomain\>_ is the organization's URL.</span></span>
  
<span data-ttu-id="1dd7e-123">例如，如果组织的域为 contoso.onmicrosoft.com，则指向团队网站的直接 URL 为 `https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx` 。</span><span class="sxs-lookup"><span data-stu-id="1dd7e-123">For example, if the domain of the organization is contoso.onmicrosoft.com, then the direct URL to the team site would be `https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx`.</span></span>
  
<span data-ttu-id="1dd7e-124">当然，用户还可以SharePoint网站将 SharePoint Online 文档下载到本地计算机或其他位置。</span><span class="sxs-lookup"><span data-stu-id="1dd7e-124">Of course, users can also download SharePoint Online documents from the SharePoint team site to their local computer or to another location at any time.</span></span>