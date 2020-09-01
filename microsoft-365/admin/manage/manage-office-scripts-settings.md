---
title: 管理 Office 脚本设置
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: 了解如何管理组织中用户的 Office 脚本设置。
ms.openlocfilehash: 44e2a5c0e0577db344fdbb00a110674df3e71bdc
ms.sourcegitcommit: 04f196528a7a91b404478553433af3fa94d7eee7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "47317489"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="5657b-103">管理 Office 脚本设置</span><span class="sxs-lookup"><span data-stu-id="5657b-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="5657b-104">通过 Office 脚本，用户可以通过在 web 上的 Excel 中录制、编辑和运行脚本来自动执行任务。</span><span class="sxs-lookup"><span data-stu-id="5657b-104">Office Scripts‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="5657b-105">Office 脚本使用 Power 自动功能，并且用户通过使用 Excel Online (Business) 连接器在工作簿上运行脚本。</span><span class="sxs-lookup"><span data-stu-id="5657b-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="5657b-106">Microsoft 365 管理员可以从 Microsoft 365 管理中心管理 Office 脚本设置。</span><span class="sxs-lookup"><span data-stu-id="5657b-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5657b-107">准备工作</span><span class="sxs-lookup"><span data-stu-id="5657b-107">Before you begin</span></span>

- <span data-ttu-id="5657b-108">若要管理 Office 脚本设置，您必须是全局管理员。有关详细信息，请参阅 [关于管理员角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="5657b-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="5657b-109">确保组织中的用户具有有效的 Microsoft 365 或 Office 365 商业版或 EDU 计划的许可证，包括对 Office 桌面应用程序的访问权限，例如以下计划之一：</span><span class="sxs-lookup"><span data-stu-id="5657b-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="5657b-110">Microsoft 365 商业标准版</span><span class="sxs-lookup"><span data-stu-id="5657b-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="5657b-111">Microsoft 365 商业应用版</span><span class="sxs-lookup"><span data-stu-id="5657b-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="5657b-112">适用于企业的 Microsoft 365 应用</span><span class="sxs-lookup"><span data-stu-id="5657b-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="5657b-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="5657b-113">Office 365 E3</span></span>
    - <span data-ttu-id="5657b-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="5657b-114">Office 365 E5</span></span>
    - <span data-ttu-id="5657b-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="5657b-115">Office 365 A3</span></span>
    - <span data-ttu-id="5657b-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="5657b-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="5657b-117">管理 Office 脚本的可用性和脚本的共享</span><span class="sxs-lookup"><span data-stu-id="5657b-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="5657b-118">在 Microsoft 365 管理中心，转到 " **设置** \> **组织设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">服务</a> " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="5657b-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="5657b-119">选择 " **Office 脚本**"。</span><span class="sxs-lookup"><span data-stu-id="5657b-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="5657b-120">默认情况下，Office 脚本处于打开状态，组织中的所有人都可以访问和使用功能并共享脚本。</span><span class="sxs-lookup"><span data-stu-id="5657b-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="5657b-121">若要关闭组织的 Office 脚本，请清除 " **让用户在 Excel 中自动处理其任务"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="5657b-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="5657b-122">如果您以前关闭了组织的 Office 脚本，并且想要将其重新打开，请选择 **"让用户在 Excel 中自动执行其任务**"，然后指定可以访问和使用该功能的用户：</span><span class="sxs-lookup"><span data-stu-id="5657b-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="5657b-123">若要允许组织中的所有用户访问和使用 Office 脚本，请让 **每个人** (选中默认) 。</span><span class="sxs-lookup"><span data-stu-id="5657b-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span> 

    - <span data-ttu-id="5657b-124">若要仅允许特定组的成员访问和使用 Office 脚本，请选择 " **特定组**"，然后输入要将其添加到允许列表中的组的名称或电子邮件别名。</span><span class="sxs-lookup"><span data-stu-id="5657b-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="5657b-125">您只能将一个组添加到允许列表中，并且必须是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="5657b-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="5657b-126">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="5657b-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="5657b-127">通讯组</span><span class="sxs-lookup"><span data-stu-id="5657b-127">Distribution group</span></span>
        - <span data-ttu-id="5657b-128">安全组</span><span class="sxs-lookup"><span data-stu-id="5657b-128">Security group</span></span>
        - <span data-ttu-id="5657b-129">启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="5657b-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="5657b-130">若要了解有关不同类型的组的详细信息，请参阅 [比较组](../create-groups/compare-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="5657b-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="5657b-131">若要允许有权访问 Office 脚本的用户与组织中的其他人共享其脚本，请选择 " **允许访问 Office 脚本的用户与组织中的其他人共享其脚本**。</span><span class="sxs-lookup"><span data-stu-id="5657b-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="5657b-132">不允许在组织外部共享脚本。</span><span class="sxs-lookup"><span data-stu-id="5657b-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="5657b-133">如果稍后关闭组织的脚本共享，用户将仍能运行以前共享的脚本。</span><span class="sxs-lookup"><span data-stu-id="5657b-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="5657b-134">指定有权访问 Office 脚本的用户可以共享其脚本：</span><span class="sxs-lookup"><span data-stu-id="5657b-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="5657b-135">若要允许具有 Office 脚本访问权限的所有用户共享其脚本，请将 **每个人** (保留) 选择的默认值。</span><span class="sxs-lookup"><span data-stu-id="5657b-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="5657b-136">若要仅允许具有 Office 脚本访问权限的特定组的成员共享其脚本，请选择 " **特定组**"，然后输入要将其添加到允许列表中的组的名称或电子邮件别名。</span><span class="sxs-lookup"><span data-stu-id="5657b-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="5657b-137">您只能将一个组添加到允许列表中，并且必须是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="5657b-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="5657b-138">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="5657b-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="5657b-139">通讯组</span><span class="sxs-lookup"><span data-stu-id="5657b-139">Distribution group</span></span>
        - <span data-ttu-id="5657b-140">安全组</span><span class="sxs-lookup"><span data-stu-id="5657b-140">Security group</span></span>
        - <span data-ttu-id="5657b-141">启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="5657b-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="5657b-142">若要了解有关不同类型的组的详细信息，请参阅 [比较组](../create-groups/compare-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="5657b-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="5657b-143">选择 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="5657b-143">Select **Save**.</span></span>

    <span data-ttu-id="5657b-144">最长可能需要48小时才能使 Office 脚本设置的更改生效。</span><span class="sxs-lookup"><span data-stu-id="5657b-144">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5657b-145">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5657b-145">Next steps</span></span>

<span data-ttu-id="5657b-146">由于 Office 脚本与电源自动配合使用，因此我们建议您查看现有的数据丢失防护 (DLP) 策略，以确保组织的数据在用户使用 Office 脚本时保持受保护状态。</span><span class="sxs-lookup"><span data-stu-id="5657b-146">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="5657b-147">有关详细信息，请参阅 [数据丢失防护 (DLP) 策略](/power-automate/prevent-data-loss)。</span><span class="sxs-lookup"><span data-stu-id="5657b-147">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="5657b-148">相关内容</span><span class="sxs-lookup"><span data-stu-id="5657b-148">Related content</span></span>

<span data-ttu-id="5657b-149">[Office 脚本技术文档](/office/dev/scripts/) (链接页面) </span><span class="sxs-lookup"><span data-stu-id="5657b-149">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="5657b-150">Excel (文章) [中的 Office 脚本简介](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a)</span><span class="sxs-lookup"><span data-stu-id="5657b-150">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="5657b-151">[在 Excel For Web 中共享 Office 脚本](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (文章) </span><span class="sxs-lookup"><span data-stu-id="5657b-151">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="5657b-152">[在 Excel 的 web (文章) 中记录、编辑和创建 Office 脚本](/office/dev/scripts/tutorials/excel-tutorial)</span><span class="sxs-lookup"><span data-stu-id="5657b-152">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>