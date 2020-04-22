---
title: 为数据调查分配权限（预览）
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文介绍如何在 Microsoft 365 中设置使用 "数据调查" 工具所需的权限。
ms.openlocfilehash: 47a7923d38cfa0ea3bad6c4c266f580f8104c429
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637754"
---
# <a name="assign-permissions-for-data-investigations-preview"></a><span data-ttu-id="2936b-103">为数据调查分配权限（预览）</span><span class="sxs-lookup"><span data-stu-id="2936b-103">Assign permissions for Data Investigations (Preview)</span></span>

<span data-ttu-id="2936b-104">若要访问 Office 365 或 Microsoft 365 合规性中心中的数据调查，您需要是 "数据调查人员" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="2936b-104">To access a data investigation in the Office 365 or Microsoft 365 compliance center, you need be a member of the Data Investigator role group.</span></span> <span data-ttu-id="2936b-105">若要将成员添加到角色组，您必须是 "组织管理" 角色组的成员，或者在安全 & 合规性中心中为其分配角色管理角色。</span><span class="sxs-lookup"><span data-stu-id="2936b-105">To add members to a role group, you must be a member of the Organization Management role group or assigned the Role Management role in the Security & Compliance Center.</span></span> <span data-ttu-id="2936b-106">在用户成为 "数据调查员" 角色组的成员后，他们可以在您所属的数据调查中创建、访问和执行调查。</span><span class="sxs-lookup"><span data-stu-id="2936b-106">After a user becomes a member of the Data Investigator role group, they can create, access, and conduct investigations in the data investigations that you are a member of.</span></span>

<span data-ttu-id="2936b-107">分配数据调查权限：</span><span class="sxs-lookup"><span data-stu-id="2936b-107">To assign data investigations permissions:</span></span>

1. <span data-ttu-id="2936b-108">转到[https://protection.office.com](https://protection.office.com)并使用组织中的管理员帐户的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="2936b-108">Go to [https://protection.office.com](https://protection.office.com) and sign in using the credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="2936b-109">在安全 & 合规中心中，单击 "**权限**"。</span><span class="sxs-lookup"><span data-stu-id="2936b-109">In the Security & Compliance Center, click **Permissions**.</span></span>

3. <span data-ttu-id="2936b-110">单击 "**数据调查**人员" 角色组，然后在弹出页面上的 "**成员**" 旁边，单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="2936b-110">Click the **Data Investigator** role group, and then next to **Members** on the flyout page, click **Edit**.</span></span>

4. <span data-ttu-id="2936b-111">单击 "**选择成员**"，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="2936b-111">Click **Choose members** and then click **Add**.</span></span> <span data-ttu-id="2936b-112">选择要添加为数据调查人员的用户，然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="2936b-112">Select the users that you want to add as data investigators, and then click **Add**.</span></span>

5. <span data-ttu-id="2936b-113">添加所有用户后，单击 "**完成**"，然后单击 "**保存**" 以保存对角色组所做的更改。</span><span class="sxs-lookup"><span data-stu-id="2936b-113">After you've added all the users, click **Done** and then click **Save** to save the changes to the role group.</span></span>

> [!NOTE]
> <span data-ttu-id="2936b-114">分配给 "数据调查人员" 角色组的数据调查管理角色提供了访问 Office 365 或 Microsoft 365 合规性中心中的数据调查工具所需的权限。</span><span class="sxs-lookup"><span data-stu-id="2936b-114">The Data Investigation Management role that is assigned to the Data Investigator role group provides the necessary permissions to access the Data Investigations tool in the Office 365 or Microsoft 365 compliance center.</span></span> <span data-ttu-id="2936b-115">默认情况下，此角色不会分配给 "组织管理" 角色组，这意味着组织中的全局管理员可能无法在默认情况下访问数据调查工具。</span><span class="sxs-lookup"><span data-stu-id="2936b-115">By default, this role is not assigned to the Organization Management role group, which means that global admins in your organization may not be able to access the Data Investigations tool by default.</span></span> <span data-ttu-id="2936b-116">若要解决此问题，可以将全局管理员添加到数据调查员角色组，或将数据调查管理角色添加到组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="2936b-116">To fix this, you can add global admins to the Data Investigator role group or add the Data Investigation Management role to the Organization Management role group.</span></span> <span data-ttu-id="2936b-117">第三个选项是创建自定义角色组，并分配数据调查管理角色（和其他角色），然后添加相应的成员。</span><span class="sxs-lookup"><span data-stu-id="2936b-117">A third option would be to create a custom role group and assign the Data Investigation Management role (and other roles) and then add appropriate members.</span></span> <span data-ttu-id="2936b-118">有关角色组和角色的详细信息，请参阅[安全性 & 合规性中心中的权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="2936b-118">For more information about role groups and roles, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>
