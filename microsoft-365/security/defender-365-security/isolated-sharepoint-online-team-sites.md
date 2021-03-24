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
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: 了解独立的 SharePoint Online 团队网站，包括其用途、要求和功能。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2def876989e692633472a911afa743d9f5b6afd1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055698"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="647d6-103">单独的 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="647d6-103">Isolated SharePoint Online team sites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="647d6-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="647d6-104">**Applies to**</span></span>
- [<span data-ttu-id="647d6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="647d6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="647d6-106">适用于 Office 365 计划 1 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="647d6-106">Microsoft Defender for Office 365 plan 1</span></span>](defender-for-office-365.md)
- <span data-ttu-id="647d6-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="647d6-107">SharePoint Online</span></span> 

 <span data-ttu-id="647d6-108">**摘要：** 了解有关单独的 SharePoint Online 团队网站的用法。</span><span class="sxs-lookup"><span data-stu-id="647d6-108">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="647d6-p101">SharePoint Online团队网站是快速创建协作空间的简便方法。用户可在 Microsoft Office 365 中的笔记、文档、文章、日历和其他资源协同工作。SharePoint Online 团队网站基于 Microsoft 365 组，它具有一个简化的管理模型，允许与一组私有组成员或整个组织展开开放式协作。默认 SharePoint Online 团队网站允许 Microsoft 365 组的成员邀请其他用户并控制权限设置。</span><span class="sxs-lookup"><span data-stu-id="647d6-p101">SharePoint Online team sites are an easy way to quickly create a space for collaboration. Users can work together on notes, documents, articles, a calendar, and other resources in Microsoft Office 365. SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization. A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span></span>

<span data-ttu-id="647d6-113">但是，有时需要由组成员身份控制的网站访问权限以及由 SharePoint 管理员管理的 SharePoint Online 权限级别。</span><span class="sxs-lookup"><span data-stu-id="647d6-113">However, you'll sometimes need site access to be controlled by group memberships, and SharePoint Online permission levels managed by SharePoint administrators.</span></span> <span data-ttu-id="647d6-114">我们将其称为隔离站点，此站点与正在协作、查看其内容或管理此站点的一组用户隔离。</span><span class="sxs-lookup"><span data-stu-id="647d6-114">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span></span> <span data-ttu-id="647d6-115">可能需要隔离的网站，如下所示：</span><span class="sxs-lookup"><span data-stu-id="647d6-115">You might need an isolated site for the following:</span></span>

- <span data-ttu-id="647d6-116">组织内的一个机密项目。</span><span class="sxs-lookup"><span data-stu-id="647d6-116">A secret project within your organization.</span></span>

- <span data-ttu-id="647d6-117">对于组织高度敏感或宝贵的知识产权的位置。</span><span class="sxs-lookup"><span data-stu-id="647d6-117">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>

- <span data-ttu-id="647d6-118">组织所采取的法律行动的资源或组织受约束的资源。</span><span class="sxs-lookup"><span data-stu-id="647d6-118">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>

- <span data-ttu-id="647d6-119">在具有某些重叠的多个组织之间共享 Microsoft 365 订阅，但大多数情况下都作为单独业务实体存在。</span><span class="sxs-lookup"><span data-stu-id="647d6-119">To share a Microsoft 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>

<span data-ttu-id="647d6-120">下面是单独网站的要求：</span><span class="sxs-lookup"><span data-stu-id="647d6-120">Here are the requirements of an isolated site:</span></span>

- <span data-ttu-id="647d6-121">只有 SharePoint Online 管理员可以执行网站管理，其中包括访问网站和配置自定义权限的组成员身份。</span><span class="sxs-lookup"><span data-stu-id="647d6-121">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>

- <span data-ttu-id="647d6-122">网站成员不能邀请其他成员到团队网站。</span><span class="sxs-lookup"><span data-stu-id="647d6-122">Members of the site cannot invite other members to the team site.</span></span>

- <span data-ttu-id="647d6-p103">不是单独网站成员的用户不能请求对该网站的访问。当他们尝试访问与该网站相关联的任何 URL 时，将会收到拒绝访问网页的消息。</span><span class="sxs-lookup"><span data-stu-id="647d6-p103">Users who are not members of the isolated site cannot request access to the site. They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>

<span data-ttu-id="647d6-p104">通过 SharePoint Online 管理员要求进行集中式访问控制和自定义权限的折衷方案是，随着时间的推移，该网站仍然保持独立。例如，当前成员不能以有意或无意的方式在 Microsoft 365 订阅中邀请不是该网站成员的其他用户或为其配置自定义权限。</span><span class="sxs-lookup"><span data-stu-id="647d6-p104">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time. For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span></span>

<span data-ttu-id="647d6-127">单独网站可以与其他功能结合使用，例如：</span><span class="sxs-lookup"><span data-stu-id="647d6-127">An isolated site can be used with other features, such as:</span></span>

- <span data-ttu-id="647d6-128">信息权限管理，用于确保网站上的资源保持加密，即使在本地下载资源并将其上传到在整个组织中可用的其他站点。</span><span class="sxs-lookup"><span data-stu-id="647d6-128">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>

- <span data-ttu-id="647d6-129">数据丢失防护，用于防止用户发送该网站的资源（如文件、电子邮件）。</span><span class="sxs-lookup"><span data-stu-id="647d6-129">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>

## <a name="next-steps"></a><span data-ttu-id="647d6-130">后续步骤</span><span class="sxs-lookup"><span data-stu-id="647d6-130">Next steps</span></span>

<span data-ttu-id="647d6-131">若要在试用版订阅中尝试创建单独的 SharePoint Online 团队网站，请参阅[单独的 SharePoint Online 团队网站开发/测试环境](/microsoft-365/solutions/team-security-isolation-dev-test)中的分步说明。</span><span class="sxs-lookup"><span data-stu-id="647d6-131">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](/microsoft-365/solutions/team-security-isolation-dev-test).</span></span>

## <a name="related-topic"></a><span data-ttu-id="647d6-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="647d6-132">Related topic</span></span>

[<span data-ttu-id="647d6-133">配置具有安全隔离的团队</span><span class="sxs-lookup"><span data-stu-id="647d6-133">Configure a team with security isolation</span></span>](/microsoft-365/solutions/secure-teams-security-isolation)
