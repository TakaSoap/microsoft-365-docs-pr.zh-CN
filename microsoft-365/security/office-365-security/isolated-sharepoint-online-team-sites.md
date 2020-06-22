---
title: 单独的 SharePoint Online 团队网站
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: 了解独立的 SharePoint Online 团队网站，包括其用途、要求和功能。
ms.openlocfilehash: 0646ffc37256702844b550fd1beb841944b2d509
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819529"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="6010d-103">单独的 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="6010d-103">Isolated SharePoint Online team sites</span></span>

 <span data-ttu-id="6010d-104">**摘要：** 了解有关单独的 SharePoint Online 团队网站的用法。</span><span class="sxs-lookup"><span data-stu-id="6010d-104">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>
  
<span data-ttu-id="6010d-105">SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="6010d-105">SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365.</span></span> <span data-ttu-id="6010d-106">SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization.</span><span class="sxs-lookup"><span data-stu-id="6010d-106">SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization.</span></span> <span data-ttu-id="6010d-107">A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span><span class="sxs-lookup"><span data-stu-id="6010d-107">A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span></span>
  
<span data-ttu-id="6010d-108">However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators.</span><span class="sxs-lookup"><span data-stu-id="6010d-108">However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators.</span></span> <span data-ttu-id="6010d-109">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span><span class="sxs-lookup"><span data-stu-id="6010d-109">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span></span> <span data-ttu-id="6010d-110">You might need an isolated site for the following:</span><span class="sxs-lookup"><span data-stu-id="6010d-110">You might need an isolated site for the following:</span></span>
  
- <span data-ttu-id="6010d-111">组织内的一个机密项目。</span><span class="sxs-lookup"><span data-stu-id="6010d-111">A secret project within your organization.</span></span>
    
- <span data-ttu-id="6010d-112">对于组织高度敏感或宝贵的知识产权的位置。</span><span class="sxs-lookup"><span data-stu-id="6010d-112">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>
    
- <span data-ttu-id="6010d-113">组织所采取的法律行动的资源或组织受约束的资源。</span><span class="sxs-lookup"><span data-stu-id="6010d-113">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>
    
- <span data-ttu-id="6010d-114">在具有某些重叠的多个组织之间共享 Microsoft 365 订阅，但大多数情况下都作为单独业务实体存在。</span><span class="sxs-lookup"><span data-stu-id="6010d-114">To share a Microsoft 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>
    
<span data-ttu-id="6010d-115">下面是单独网站的要求：</span><span class="sxs-lookup"><span data-stu-id="6010d-115">Here are the requirements of an isolated site:</span></span>
  
- <span data-ttu-id="6010d-116">只有 SharePoint Online 管理员可以执行网站管理，其中包括访问网站和配置自定义权限的组成员身份。</span><span class="sxs-lookup"><span data-stu-id="6010d-116">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>
    
- <span data-ttu-id="6010d-117">网站成员不能邀请其他成员到团队网站。</span><span class="sxs-lookup"><span data-stu-id="6010d-117">Members of the site cannot invite other members to the team site.</span></span>
    
- <span data-ttu-id="6010d-118">Users who are not members of the isolated site cannot request access to the site.</span><span class="sxs-lookup"><span data-stu-id="6010d-118">Users who are not members of the isolated site cannot request access to the site.</span></span> <span data-ttu-id="6010d-119">They will receive an access denied web page when they attempt to access any URL associated with the site.</span><span class="sxs-lookup"><span data-stu-id="6010d-119">They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>
    
<span data-ttu-id="6010d-120">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time.</span><span class="sxs-lookup"><span data-stu-id="6010d-120">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time.</span></span> <span data-ttu-id="6010d-121">For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span><span class="sxs-lookup"><span data-stu-id="6010d-121">For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span></span>
  
<span data-ttu-id="6010d-122">单独网站可以与其他功能结合使用，例如：</span><span class="sxs-lookup"><span data-stu-id="6010d-122">An isolated site can be used with other features, such as:</span></span>
  
- <span data-ttu-id="6010d-123">信息权限管理，用于确保网站上的资源保持加密，即使在本地下载资源并将其上传到在整个组织中可用的其他站点。</span><span class="sxs-lookup"><span data-stu-id="6010d-123">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>
    
- <span data-ttu-id="6010d-124">数据丢失防护，用于防止用户发送该网站的资源（如文件、电子邮件）。</span><span class="sxs-lookup"><span data-stu-id="6010d-124">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="6010d-125">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6010d-125">Next steps</span></span>

<span data-ttu-id="6010d-126">若要在试用版订阅中尝试创建单独的 SharePoint Online 团队网站，请参阅[单独的 SharePoint Online 团队网站开发/测试环境](isolated-sharepoint-online-team-site-dev-test-environment.md)中的分步说明。</span><span class="sxs-lookup"><span data-stu-id="6010d-126">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>
  
<span data-ttu-id="6010d-127">当准备好在生产中部署单独的 SharePoint Online 团队网站后，请参阅[设计单独的 SharePoint Online 团队网站](design-an-isolated-sharepoint-online-team-site.md)中的分步设计注意事项。</span><span class="sxs-lookup"><span data-stu-id="6010d-127">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6010d-128">相关主题</span><span class="sxs-lookup"><span data-stu-id="6010d-128">Related topics</span></span>

[<span data-ttu-id="6010d-129">设计单独的 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="6010d-129">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="6010d-130">管理独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="6010d-130">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="6010d-131">部署独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="6010d-131">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)


