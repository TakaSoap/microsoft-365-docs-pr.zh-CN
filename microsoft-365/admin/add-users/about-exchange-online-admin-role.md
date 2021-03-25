---
title: 关于 Exchange Online 管理员角色
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 097ae285-c4af-4319-9770-e2559d66e4c8
description: 'Exchange Online 管理员管理组织的电子邮件和邮箱。 例如，他们恢复用户邮箱中的已删除项目。 '
ms.openlocfilehash: 4dc1f435571650ae4a805198782c3c24a92024fb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197645"
---
# <a name="about-the-exchange-online-admin-role"></a><span data-ttu-id="4853f-104">关于 Exchange Online 管理员角色</span><span class="sxs-lookup"><span data-stu-id="4853f-104">About the Exchange Online admin role</span></span>

<span data-ttu-id="4853f-105">为了帮助你管理 Microsoft 365，可以从[](assign-admin-roles.md)Exchange 管理中心向用户分配管理组织的电子邮件和[邮箱的权限](/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="4853f-105">To help you administer Microsoft 365, you can [assign](assign-admin-roles.md) users permissions to manage your organization's email and mailboxes from the [Exchange admin center](/exchange/exchange-admin-center).</span></span> <span data-ttu-id="4853f-106">为此，请将其分配给 Exchange 管理员角色。</span><span class="sxs-lookup"><span data-stu-id="4853f-106">You do this by assigning them to the Exchange admin role.</span></span>
  
 <span data-ttu-id="4853f-107">**提示**：将某人分配到 Exchange 管理员角色时，还要将其分配到服务管理员角色。</span><span class="sxs-lookup"><span data-stu-id="4853f-107">**Tip**: When you assign someone to the Exchange admin role, also assign them to the Service admin role.</span></span> <span data-ttu-id="4853f-108">这样，他们就可以在 Microsoft 365 管理中心查看重要信息，如 Exchange Online 服务的运行状况，以及更改和发布通知。</span><span class="sxs-lookup"><span data-stu-id="4853f-108">This way they can see important information in the Microsoft 365 admin center, such as the health of the Exchange Online service, and change and release notifications.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="4853f-109">准备工作</span><span class="sxs-lookup"><span data-stu-id="4853f-109">Before you begin</span></span>

<span data-ttu-id="4853f-110">下面是用户在被分配到 Exchange 管理员角色时可以执行的主要任务：</span><span class="sxs-lookup"><span data-stu-id="4853f-110">Here are some of the key tasks users can do when they are assigned to the Exchange admin role:</span></span>
  
- [<span data-ttu-id="4853f-111">恢复用户邮箱中已删除的项目 - 管理员帮助</span><span class="sxs-lookup"><span data-stu-id="4853f-111">Recover deleted items in a user mailbox - Admin Help</span></span>](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- <span data-ttu-id="4853f-112">[为组织中邮箱设置存档和删除策略](../../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="4853f-112">[Set up an archive and deletion policy for mailboxes in your organization](../../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md).</span></span>

- <span data-ttu-id="4853f-113">设置邮箱功能，如邮箱共享策略：用户如何与组织外部的其他人共享日历和联系人信息。</span><span class="sxs-lookup"><span data-stu-id="4853f-113">Set up mailbox features such as the mailbox sharing policy: how users can share calendar and contacts information with others outside of your organization.</span></span>

- <span data-ttu-id="4853f-114">为某人[的邮箱](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)设置"代理发送[](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)"和"代表发送"代理。</span><span class="sxs-lookup"><span data-stu-id="4853f-114">Set up "[Send as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" and "[Send on behalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" delegates for someone's mailbox.</span></span> <span data-ttu-id="4853f-115">例如，主管人员可能希望其助理能够代表他们发送邮件。</span><span class="sxs-lookup"><span data-stu-id="4853f-115">For example, an executive may want their assistant to have the ability to send mail on their behalf.</span></span>

- <span data-ttu-id="4853f-116">[创建共享邮箱](../email/create-a-shared-mailbox.md) ，以便一组人员可以从公用电子邮件地址监视和发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="4853f-116">[Create a shared mailbox](../email/create-a-shared-mailbox.md) so a group of people can monitor and send email from a common email address.</span></span>

- <span data-ttu-id="4853f-117">[组织的电子邮件反垃圾邮件](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) 保护和恶意软件筛选器。</span><span class="sxs-lookup"><span data-stu-id="4853f-117">[Email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) and malware filters for the organization.</span></span>

- <span data-ttu-id="4853f-118">管理 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="4853f-118">Manage Microsoft 365 groups</span></span>

## <a name="exchange-online-role-groups"></a><span data-ttu-id="4853f-119">Exchange Online 角色组</span><span class="sxs-lookup"><span data-stu-id="4853f-119">Exchange Online role groups</span></span>

<span data-ttu-id="4853f-120">如果组织规模较大，Exchange 管理员可能需要将用户分配到 Exchange 角色组。</span><span class="sxs-lookup"><span data-stu-id="4853f-120">If you have a large organization, the Exchange admin might want to assign users to Exchange role groups.</span></span> <span data-ttu-id="4853f-121">当管理员向角色组添加用户时，该用户将获取执行某些业务功能的权限，只有该组的成员才能执行。</span><span class="sxs-lookup"><span data-stu-id="4853f-121">When an admin adds a user to a role group, the user gets permissions to perform certain business functions only members of that group can do.</span></span>
  
 <span data-ttu-id="4853f-122">例如，Exchange 管理员可能会将某人分配到发现管理角色组，以便他们可以在邮箱中搜索满足特定条件的数据。</span><span class="sxs-lookup"><span data-stu-id="4853f-122">For example, the Exchange admin might assign someone to the Discovery Management role group so they can perform searches of mailboxes for data that meets certain criteria.</span></span> <span data-ttu-id="4853f-123">若要了解更多信息，请参阅[Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo)和 Manage Role [Groups。](/exchange/manage-role-groups-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="4853f-123">To learn more, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Manage Role Groups](/exchange/manage-role-groups-exchange-2013-help).</span></span>
  
## <a name="learn-about-other-admin-roles"></a><span data-ttu-id="4853f-124">了解其他管理员角色</span><span class="sxs-lookup"><span data-stu-id="4853f-124">Learn about other admin roles</span></span>

- [<span data-ttu-id="4853f-125">关于 Microsoft 365 管理员角色</span><span class="sxs-lookup"><span data-stu-id="4853f-125">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

- [<span data-ttu-id="4853f-126">关于 SharePoint Online 管理员角色</span><span class="sxs-lookup"><span data-stu-id="4853f-126">About the SharePoint Online admin role</span></span>](/sharepoint/sharepoint-admin-role)

- [<span data-ttu-id="4853f-127">关于 Skype for Business 管理员角色</span><span class="sxs-lookup"><span data-stu-id="4853f-127">About the Skype for Business admin role</span></span>](/skypeforbusiness/skype-for-business-online)

- [<span data-ttu-id="4853f-128">使用 Microsoft Teams 管理员角色</span><span class="sxs-lookup"><span data-stu-id="4853f-128">Use Microsoft Teams admin role</span></span>](/MicrosoftTeams/using-admin-roles)