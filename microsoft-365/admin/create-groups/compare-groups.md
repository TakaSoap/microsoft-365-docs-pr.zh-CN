---
title: 比较组
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Microsoft 365 组成员将获得组电子邮件和用于对话、文件和日历事件的共享工作区，以及 Stream 和 Planner。
ms.openlocfilehash: 3e4fa36520247179b653f799f7b2a061b9d9f4a9
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635590"
---
# <a name="compare-groups"></a><span data-ttu-id="afa13-103">比较组</span><span class="sxs-lookup"><span data-stu-id="afa13-103">Compare groups</span></span>

<span data-ttu-id="afa13-104">在 Microsoft 365 管理中心的 **组** 部分中，可创建和管理以下类型的组：</span><span class="sxs-lookup"><span data-stu-id="afa13-104">In the **Groups** section of the Microsoft 365 admin center, you can create and manage these types of groups:</span></span> 

- <span data-ttu-id="afa13-105">**Microsoft 365 组** （之前称为 Office 365 组）用于公司内部和外部用户之间的协作。</span><span class="sxs-lookup"><span data-stu-id="afa13-105">**Microsoft 365 groups** (formerly Office 365 groups) are used for collaboration between users, both inside and outside your company.</span></span>
- <span data-ttu-id="afa13-106">**通讯组** 用于向一组人员发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="afa13-106">**Distribution groups** are used for sending email notifications to a group of people.</span></span>
- <span data-ttu-id="afa13-107">**安全组** 用于授予对资源（如 SharePoint 网站）的访问权限。</span><span class="sxs-lookup"><span data-stu-id="afa13-107">**Security groups** are used for granting access to resources such as SharePoint sites.</span></span>
- <span data-ttu-id="afa13-108">**启用邮件的安全组** 用于授予对资源（如 SharePoint）的访问权限，并向这些用户发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="afa13-108">**Mail-enabled security groups** are used for granting access to resources such as SharePoint, and emailing notifications to those users.</span></span>
- <span data-ttu-id="afa13-109">当多个用户需要访问同一邮箱（例如公司信息或支持电子邮件地址）时，将使用 **共享邮箱**。</span><span class="sxs-lookup"><span data-stu-id="afa13-109">**Shared mailboxes** are used when multiple people need access to the same mailbox, such as a company information or support email address.</span></span>

## <a name="microsoft-365-groups"></a><span data-ttu-id="afa13-110">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="afa13-110">Microsoft 365 groups</span></span>

<span data-ttu-id="afa13-111">Microsoft 365 组用于公司内部和外部用户之间的协作。</span><span class="sxs-lookup"><span data-stu-id="afa13-111">Microsoft 365 groups are used for collaboration between users, both inside and outside your company.</span></span> <span data-ttu-id="afa13-112">对于每个 Microsoft 365 组，成员将获得组电子邮件和用于对话、文件和日历事件的共享工作区、流和规划器。</span><span class="sxs-lookup"><span data-stu-id="afa13-112">With each Microsoft 365 group, members get a group email and shared workspace for conversations, files, and calendar events, Stream and a Planner.</span></span>

<span data-ttu-id="afa13-113">只要[管理员启用](manage-guest-access-in-groups.md)了此功能，你就可以将组织外部的人员添加到组中。</span><span class="sxs-lookup"><span data-stu-id="afa13-113">You can add people from outside your organization to a group as long as this has been [enabled by the administrator](manage-guest-access-in-groups.md).</span></span> <span data-ttu-id="afa13-114">还可以允许外部发件人向组电子邮件地址发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="afa13-114">You can also allow external senders to send email to the group email address.</span></span>

<span data-ttu-id="afa13-115">可[为 Azure Active Directory中的动态成员身份](/azure/active-directory/users-groups-roles/groups-change-type)配置 Microsoft 365 组，以便根据部门、位置、职衔等等用户属性自动添加或删除组成员。</span><span class="sxs-lookup"><span data-stu-id="afa13-115">Microsoft 365 groups can be [configured for dynamic membership in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), allowing group members to be added or removed automatically based on user attributes such as department, location, title, etc.</span></span>

<span data-ttu-id="afa13-116">可通过移动应用（如 Outlook for iOS 和 Outlook for Android）访问 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="afa13-116">Microsoft 365 groups can be accessed through mobile apps such as Outlook for iOS and Outlook for Android.</span></span>

<span data-ttu-id="afa13-117">如果[管理员启用了](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)此功能，则组成员可以作为组或代表组发送电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="afa13-117">Group members can send as or send on behalf of the group email address if this has been [enabled by the administrator](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md).</span></span>

## <a name="distribution-groups"></a><span data-ttu-id="afa13-118">通讯组</span><span class="sxs-lookup"><span data-stu-id="afa13-118">Distribution groups</span></span>

<span data-ttu-id="afa13-119">[通讯组](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) 用于向一组人员发送通知。</span><span class="sxs-lookup"><span data-stu-id="afa13-119">[Distribution groups](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) are used for sending notifications to a group of people.</span></span> <span data-ttu-id="afa13-120">如果管理员启用，则可以接收外部电子邮件。</span><span class="sxs-lookup"><span data-stu-id="afa13-120">They can receive external email if enabled by the administrator.</span></span>

<span data-ttu-id="afa13-121">通讯组最适用于需要将信息广播给一组人员的情况，例如 "构建 A 中的人" 或 "Contoso 中的每个人"。</span><span class="sxs-lookup"><span data-stu-id="afa13-121">Distribution groups are best for situations where you need to broadcast information to a set group of people, such as "People in Building A" or "Everyone at Contoso."</span></span>

<span data-ttu-id="afa13-122">通讯组可[升级到 Microsoft 365 组](../manage/upgrade-distribution-lists.md)。</span><span class="sxs-lookup"><span data-stu-id="afa13-122">Distribution groups can be [upgraded to Microsoft 365 groups](../manage/upgrade-distribution-lists.md).</span></span>

<span data-ttu-id="afa13-123">通讯组可添加到 Microsoft Teams 中的团队中。</span><span class="sxs-lookup"><span data-stu-id="afa13-123">Distribution groups can be added to a team in Microsoft Teams.</span></span>

## <a name="security-groups"></a><span data-ttu-id="afa13-124">安全组</span><span class="sxs-lookup"><span data-stu-id="afa13-124">Security groups</span></span>

<span data-ttu-id="afa13-125">[安全组](../email/create-edit-or-delete-a-security-group.md) 用于授予对 Microsoft 365 资源（如 SharePoint）的访问权限。</span><span class="sxs-lookup"><span data-stu-id="afa13-125">[Security groups](../email/create-edit-or-delete-a-security-group.md) are used for granting access to Microsoft 365 resources, such as SharePoint.</span></span> <span data-ttu-id="afa13-126">它们可以简化管理，因为只需管理组，而不是单独将用户添加到每个资源。</span><span class="sxs-lookup"><span data-stu-id="afa13-126">They can make administration easier because you need only administer the group rather than adding users to each resource individually.</span></span>

<span data-ttu-id="afa13-p105">安全组可以包含用户或设备。可将创建设备安全组用于移动设备管理服务（如 Intune）。</span><span class="sxs-lookup"><span data-stu-id="afa13-p105">Security groups can contain users or devices. Creating a security group for devices can be used with mobile device management services, such as Intune.</span></span>

<span data-ttu-id="afa13-129">可为[ Azure Active Directory 中的动态成员身份配置](/azure/active-directory/users-groups-roles/groups-change-type)安全组，以便根据部门、位置或职衔等用户属性自动添加或删除组成员或设备；或设备属性（如操作系统版本）。</span><span class="sxs-lookup"><span data-stu-id="afa13-129">Security groups can be [configured for dynamic membership in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), allowing group members or devices to be added or removed automatically based on user attributes such as department, location, or title; or device attributes such as operating system version.</span></span>

<span data-ttu-id="afa13-130">可以将安全组添加到团队中。</span><span class="sxs-lookup"><span data-stu-id="afa13-130">Security groups can be added to a team.</span></span>

## <a name="mail-enabled-security-groups"></a><span data-ttu-id="afa13-131">启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="afa13-131">Mail-enabled security groups</span></span>

<span data-ttu-id="afa13-132">启用邮件的安全组的功能与常规安全组相同，不同之处在于它们无法通过 Azure Active Directory 动态管理，并且不能包含设备。</span><span class="sxs-lookup"><span data-stu-id="afa13-132">Mail-enabled security groups function the same as regular security groups, except that they cannot be dynamically managed through Azure Active Directory and cannot contain devices.</span></span>

<span data-ttu-id="afa13-133">它们包括向组中的所有成员发送邮件的功能。</span><span class="sxs-lookup"><span data-stu-id="afa13-133">They include the ability to send mail to all the members of the group.</span></span>

<span data-ttu-id="afa13-134">可以将启用邮件的安全组添加到团队中。</span><span class="sxs-lookup"><span data-stu-id="afa13-134">Mail-enabled security groups can be added to a team.</span></span>

## <a name="shared-mailboxes"></a><span data-ttu-id="afa13-135">共享邮箱</span><span class="sxs-lookup"><span data-stu-id="afa13-135">Shared mailboxes</span></span>

<span data-ttu-id="afa13-136">当多个用户需要访问同一邮箱（例如公司信息或支持电子邮件地址、接待台或其他可能由多个用户共享的其他功能）时，将使用[共享邮箱](../email/create-a-shared-mailbox.md)。</span><span class="sxs-lookup"><span data-stu-id="afa13-136">[Shared mailboxes](../email/create-a-shared-mailbox.md) are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.</span></span>

<span data-ttu-id="afa13-137">如果管理员已启用共享邮箱，则共享邮箱可以接收外部电子邮件。</span><span class="sxs-lookup"><span data-stu-id="afa13-137">Shared mailboxes can receive external emails if the administrator has enabled this.</span></span>

<span data-ttu-id="afa13-138">共享邮箱包括可用于协作的日历。</span><span class="sxs-lookup"><span data-stu-id="afa13-138">Shared mailboxes include a calendar that can be used for collaboration.</span></span>

<span data-ttu-id="afa13-139">如果管理员已授予用户执行该操作的权限，具有组邮箱权限的用户可以作为或代表邮箱电子邮件地址发送。</span><span class="sxs-lookup"><span data-stu-id="afa13-139">Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that.</span></span> <span data-ttu-id="afa13-140">这对帮助和支持邮箱尤其有用，因为用户可从 "Contoso 支持" 或 "构建 A 接待台" 发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="afa13-140">This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk."</span></span>

<span data-ttu-id="afa13-141">暂无法将共享邮箱迁移到 Microsoft 365 组中。</span><span class="sxs-lookup"><span data-stu-id="afa13-141">Currently it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="afa13-142">所需内容是什么？</span><span class="sxs-lookup"><span data-stu-id="afa13-142">Is this something you want?</span></span> <span data-ttu-id="afa13-143">请告知我们。</span><span class="sxs-lookup"><span data-stu-id="afa13-143">Let us know.</span></span> <span data-ttu-id="afa13-144">**[在此处投票](https://go.microsoft.com/fwlink/?linkid=871518)**。</span><span class="sxs-lookup"><span data-stu-id="afa13-144">**[Vote here](https://go.microsoft.com/fwlink/?linkid=871518)**.</span></span>

## <a name="related-content"></a><span data-ttu-id="afa13-145">相关内容</span><span class="sxs-lookup"><span data-stu-id="afa13-145">Related content</span></span>

<span data-ttu-id="afa13-146">[了解 Microsoft 365 组](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)（文章）</span><span class="sxs-lookup"><span data-stu-id="afa13-146">[Learn about Microsoft 365 groups](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) (article)</span></span>\
<span data-ttu-id="afa13-147">[为什么应将通讯组列表升级至 Outlook 中的组](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)</span><span class="sxs-lookup"><span data-stu-id="afa13-147">[Why you should upgrade your distribution lists to groups in Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188) (article)</span></span>
