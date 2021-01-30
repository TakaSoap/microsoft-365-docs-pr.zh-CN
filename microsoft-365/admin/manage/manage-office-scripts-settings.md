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
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058419"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="e822d-103">管理 Office 脚本设置</span><span class="sxs-lookup"><span data-stu-id="e822d-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="e822d-104">Office 脚本允许用户通过录制、编辑和运行 Excel 网页中的脚本来自动执行任务。</span><span class="sxs-lookup"><span data-stu-id="e822d-104">Office Scripts‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="e822d-105">Office 脚本与 Power Automate 一起工作，用户通过使用 Excel Online (Business) 连接器对工作簿运行脚本。</span><span class="sxs-lookup"><span data-stu-id="e822d-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="e822d-106">Microsoft 365 管理员可以从 Microsoft 365 管理中心管理 Office 脚本设置。</span><span class="sxs-lookup"><span data-stu-id="e822d-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e822d-107">准备工作</span><span class="sxs-lookup"><span data-stu-id="e822d-107">Before you begin</span></span>

- <span data-ttu-id="e822d-108">若要管理 Office 脚本设置，您必须是全局管理员。有关详细信息，请参阅 [关于管理员角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="e822d-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="e822d-109">确保贵组织中用户具有 Microsoft 365 或 Office 365 商业版或 EDU 计划的有效许可证，该计划包括对 Office 桌面应用（如以下计划之一）的访问权限：</span><span class="sxs-lookup"><span data-stu-id="e822d-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="e822d-110">Microsoft 365 商业标准版</span><span class="sxs-lookup"><span data-stu-id="e822d-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="e822d-111">Microsoft 365 商业应用版</span><span class="sxs-lookup"><span data-stu-id="e822d-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="e822d-112">Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="e822d-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="e822d-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="e822d-113">Office 365 E3</span></span>
    - <span data-ttu-id="e822d-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="e822d-114">Office 365 E5</span></span>
    - <span data-ttu-id="e822d-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="e822d-115">Office 365 A3</span></span>
    - <span data-ttu-id="e822d-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="e822d-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="e822d-117">管理 Office 脚本的可用性和脚本共享</span><span class="sxs-lookup"><span data-stu-id="e822d-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="e822d-118">在 Microsoft 365 管理中心中，转到"设置 \> **组织设置** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">服务"</a>选项卡。</span><span class="sxs-lookup"><span data-stu-id="e822d-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="e822d-119">选择 **Office 脚本**。</span><span class="sxs-lookup"><span data-stu-id="e822d-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="e822d-120">默认情况下，Office 脚本已打开，您的组织中的每个人都可以访问和使用该功能并共享脚本。</span><span class="sxs-lookup"><span data-stu-id="e822d-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="e822d-121">若要为组织关闭 Office 脚本，请清除"允许用户在 **Excel 网页** 中自动执行任务"复选框。</span><span class="sxs-lookup"><span data-stu-id="e822d-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="e822d-122">如果之前为组织关闭 Office 脚本，并且希望将其重新启用，请选择"允许用户在 **Excel** 网页中自动执行任务"，然后指定可以访问和使用该功能的用户：</span><span class="sxs-lookup"><span data-stu-id="e822d-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="e822d-123">若要允许您组织中所有用户访问和使用 Office 脚本，请保留"任何人 (默认) 选中。</span><span class="sxs-lookup"><span data-stu-id="e822d-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="e822d-124">若要仅允许特定组的成员访问和使用 Office 脚本，请选择"特定组"，然后输入该组的名称或电子邮件别名以将其添加到允许列表中。</span><span class="sxs-lookup"><span data-stu-id="e822d-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="e822d-125">只能将一个组添加到允许列表中，并且它必须是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="e822d-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="e822d-126">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="e822d-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="e822d-127">通讯组</span><span class="sxs-lookup"><span data-stu-id="e822d-127">Distribution group</span></span>
        - <span data-ttu-id="e822d-128">安全组</span><span class="sxs-lookup"><span data-stu-id="e822d-128">Security group</span></span>
        - <span data-ttu-id="e822d-129">启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="e822d-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="e822d-130">若要详细了解不同类型的组，请参阅["比较组"。](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="e822d-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="e822d-131">若要允许有权访问 Office 脚本的用户与组织中其他人共享其脚本，请选择"允许有权访问 Office 脚本的用户与组织其他人共享其 **脚本"。**</span><span class="sxs-lookup"><span data-stu-id="e822d-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="e822d-132">不允许在组织外部共享脚本。</span><span class="sxs-lookup"><span data-stu-id="e822d-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="e822d-133">如果稍后为组织关闭脚本共享，用户仍可运行以前共享的脚本。</span><span class="sxs-lookup"><span data-stu-id="e822d-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="e822d-134">指定有权访问 Office 脚本的用户可以共享其脚本：</span><span class="sxs-lookup"><span data-stu-id="e822d-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="e822d-135">若要允许有权访问 Office 脚本的所有用户共享其脚本，请保留"任何人 (默认) 选中。</span><span class="sxs-lookup"><span data-stu-id="e822d-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="e822d-136">若要仅允许具有 Office 脚本访问权限的特定组的成员共享其脚本，请选择"特定组"，然后输入组的名称或电子邮件别名以将其添加到允许列表中。</span><span class="sxs-lookup"><span data-stu-id="e822d-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="e822d-137">只能将一个组添加到允许列表中，并且它必须是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="e822d-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="e822d-138">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="e822d-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="e822d-139">通讯组</span><span class="sxs-lookup"><span data-stu-id="e822d-139">Distribution group</span></span>
        - <span data-ttu-id="e822d-140">安全组</span><span class="sxs-lookup"><span data-stu-id="e822d-140">Security group</span></span>
        - <span data-ttu-id="e822d-141">启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="e822d-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="e822d-142">若要详细了解不同类型的组，请参阅["比较组"。](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="e822d-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="e822d-143">若要允许用户在 Power Automate 流中运行其 Office 脚本，请选择"允许有权访问 Office 脚本的用户使用 **Power Automate 运行其脚本"。**</span><span class="sxs-lookup"><span data-stu-id="e822d-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="e822d-144">这允许用户使用 Excel Online ([Business) 连接器的](/connectors/excelonlinebusiness)**"** 运行"脚本选项添加流步骤。</span><span class="sxs-lookup"><span data-stu-id="e822d-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="e822d-145">若要允许有权访问 Office 脚本的所有用户在流中使用其脚本，请保留"任何人 (默认) 选中。</span><span class="sxs-lookup"><span data-stu-id="e822d-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="e822d-146">若要仅允许具有 Office 脚本访问权限的特定组的成员在流中使用其脚本，请选择"特定组"，然后输入该组的名称或电子邮件别名以将其添加到允许列表中。</span><span class="sxs-lookup"><span data-stu-id="e822d-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="e822d-147">只能将一个组添加到允许列表中，并且必须是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="e822d-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="e822d-148">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="e822d-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="e822d-149">通讯组</span><span class="sxs-lookup"><span data-stu-id="e822d-149">Distribution group</span></span>
        - <span data-ttu-id="e822d-150">安全组</span><span class="sxs-lookup"><span data-stu-id="e822d-150">Security group</span></span>
        - <span data-ttu-id="e822d-151">启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="e822d-151">Mail-enabled security group</span></span>

        <span data-ttu-id="e822d-152">若要详细了解不同类型的组，请参阅["比较组"。](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="e822d-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="e822d-153">若要了解有关将 Office 脚本与 Power Automate 一同使用（包括数据丢失防护策略可能受到影响）的更多信息，请参阅"使用 Power Automate 运行[Office 脚本"。](/office/dev/scripts/develop/power-automate-integration)</span><span class="sxs-lookup"><span data-stu-id="e822d-153">To learn more about using Office Scripts with Power Automate, including how your data loss prevention policies may be impacted, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="e822d-154">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="e822d-154">Select **Save**.</span></span>

    <span data-ttu-id="e822d-155">更改 Office 脚本设置最多可能需要 48 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="e822d-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e822d-156">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e822d-156">Next steps</span></span>

<span data-ttu-id="e822d-157">由于 Office 脚本与 Power Automate 一起工作，因此建议您查看现有的数据丢失防护 (DLP) 策略，以确保组织的数据在用户使用 Office 脚本时保持受保护状态。</span><span class="sxs-lookup"><span data-stu-id="e822d-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="e822d-158">有关详细信息，请参阅 DLP 策略 [ (数据丢失) 保护](/power-automate/prevent-data-loss)。</span><span class="sxs-lookup"><span data-stu-id="e822d-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="e822d-159">相关内容</span><span class="sxs-lookup"><span data-stu-id="e822d-159">Related content</span></span>

<span data-ttu-id="e822d-160">[Office 脚本技术文档 (](/office/dev/scripts/) 链接页) </span><span class="sxs-lookup"><span data-stu-id="e822d-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="e822d-161">[Excel 中 Office 脚本](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) 简介 (文章) </span><span class="sxs-lookup"><span data-stu-id="e822d-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="e822d-162">[在 Excel 中共享 Office 脚本网页](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (文章) </span><span class="sxs-lookup"><span data-stu-id="e822d-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="e822d-163">[记录、编辑和创建 Excel](/office/dev/scripts/tutorials/excel-tutorial) 网页中的 Office 脚本 (文章) </span><span class="sxs-lookup"><span data-stu-id="e822d-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
