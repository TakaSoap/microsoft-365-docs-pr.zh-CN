---
title: 内幕风险管理通知模板
description: 了解 Microsoft 365 中的内部人员风险管理通知模板
keywords: Microsoft 365，内幕风险管理，风险管理，合规性
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 92844691cba4adf39c7b4eee30de97ccff9d0890
ms.sourcegitcommit: 87cc278ea2ddcd536ecfaa3dfae9a5ddaa502cf9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179083"
---
# <a name="insider-risk-management-notice-templates"></a><span data-ttu-id="3d30c-104">内幕风险管理通知模板</span><span class="sxs-lookup"><span data-stu-id="3d30c-104">Insider risk management notice templates</span></span>

<span data-ttu-id="3d30c-105">内幕风险管理通知模板允许你在其活动生成策略匹配和警报时向员工发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3d30c-105">Insider risk management notice templates allow you to send email messages to employees when their activities generate a policy match and alert.</span></span> <span data-ttu-id="3d30c-106">在大多数情况下，生成警报的员工操作在没有正确意图的情况下产生错误或无意活动。</span><span class="sxs-lookup"><span data-stu-id="3d30c-106">In most cases, employee actions that generate alerts are the result of mistakes or inadvertent activities without ill intent.</span></span> <span data-ttu-id="3d30c-107">通知为员工提供更小心的简单提醒，或者提供有关刷新器培训或公司策略资源的链接或信息。</span><span class="sxs-lookup"><span data-stu-id="3d30c-107">Notices serve as simple reminders to employees to be more careful or to provide links or information for refresher training or corporate policy resources.</span></span> <span data-ttu-id="3d30c-108">通知可能是内部合规性培训计划的重要组成部分，可帮助为具有定期风险活动的员工创建记录的审核跟踪。</span><span class="sxs-lookup"><span data-stu-id="3d30c-108">Notices can be an important part of your internal compliance training program and can help create a documented audit trail for employees with recurring risk activities.</span></span>

<span data-ttu-id="3d30c-109">如果要向用户发送有关策略匹配的电子邮件提醒通知（作为问题解决过程的一部分），请创建通知模板。</span><span class="sxs-lookup"><span data-stu-id="3d30c-109">Create notice templates if you want to send users an email reminder notice for policy matches as part of the issue resolution process.</span></span> <span data-ttu-id="3d30c-110">通知只能发送到与所审阅的特定警报关联的员工电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3d30c-110">Notices can only be sent to the employee email address associated with the specific alert being reviewed.</span></span> <span data-ttu-id="3d30c-111">选择要应用于策略匹配项的通知模板时，可以选择接受模板中定义的字段值，也可以根据需要覆盖这些字段。</span><span class="sxs-lookup"><span data-stu-id="3d30c-111">When selecting a notice template to apply to a policy match, you can choose to accept the field values defined in the template or overwrite the fields as needed.</span></span>

## <a name="notice-templates-dashboard"></a><span data-ttu-id="3d30c-112">通知模板仪表板</span><span class="sxs-lookup"><span data-stu-id="3d30c-112">Notice templates dashboard</span></span>

<span data-ttu-id="3d30c-113">"**通知模板" 仪表板**显示已配置的通知模板的列表，并允许您创建新的通知模板。</span><span class="sxs-lookup"><span data-stu-id="3d30c-113">The **Notices templates dashboard** displays a list of configured notice templates and allows you to create new notice templates.</span></span> <span data-ttu-id="3d30c-114">通知模板按相反的日期顺序列出，最新的声明模板最先列出。</span><span class="sxs-lookup"><span data-stu-id="3d30c-114">The notice templates are listed in reverse date order with the most recent notice template listed first.</span></span>

![内幕风险管理通知模板仪表板](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a><span data-ttu-id="3d30c-116">用于通知的 HTML</span><span class="sxs-lookup"><span data-stu-id="3d30c-116">HTML for notices</span></span>

<span data-ttu-id="3d30c-117">如果要创建多个简单的基于文本的电子邮件通知，可以通过使用通知模板的邮件正文字段中的 HTML 来创建更详细的消息。</span><span class="sxs-lookup"><span data-stu-id="3d30c-117">If you'd like to create more than a simple text-based email message for notifications, you can create a more detailed message by using HTML in the message body field of a notice template.</span></span> <span data-ttu-id="3d30c-118">下面的示例提供基于 HTML 的基本电子邮件通知模板的邮件正文格式：</span><span class="sxs-lookup"><span data-stu-id="3d30c-118">The following example provides the message body format for a basic HTML-based email notification template:</span></span>

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso Employee Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso Employee <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso Employee Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> <span data-ttu-id="3d30c-119">内幕风险管理通知模板中的 HTML href 属性实现目前仅支持为单引号（而不是双引号）提供 URL 引用。</span><span class="sxs-lookup"><span data-stu-id="3d30c-119">HTML href attribute implementation in the insider risk management notice templates currently support only single quotation marks instead of double quotation marks for URL references.</span></span>

## <a name="create-a-new-notice-template"></a><span data-ttu-id="3d30c-120">创建新的通知模板</span><span class="sxs-lookup"><span data-stu-id="3d30c-120">Create a new notice template</span></span>

<span data-ttu-id="3d30c-121">若要创建新的内幕风险管理通知模板，请使用 Microsoft 365 合规性中心内的**内幕风险管理**解决方案中的 "通知向导"。</span><span class="sxs-lookup"><span data-stu-id="3d30c-121">To create a new insider risk management notice template, you'll use the notice wizard in **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="3d30c-122">完成以下步骤以创建新的内幕风险管理通知模板：</span><span class="sxs-lookup"><span data-stu-id="3d30c-122">Complete the following steps to create a new insider risk management notice template:</span></span>

1. <span data-ttu-id="3d30c-123">在[Microsoft 365 合规性中心](https://compliance.microsoft.com)中，转到 "**内幕风险管理**"，然后选择 "**通知模板**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3d30c-123">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="3d30c-124">选择 "**创建通知模板**" 以打开 "通知向导"。</span><span class="sxs-lookup"><span data-stu-id="3d30c-124">Select **Create notice template** to open the notice wizard.</span></span>
3. <span data-ttu-id="3d30c-125">在 "**创建新的通知模板**" 页上，填写下列字段：</span><span class="sxs-lookup"><span data-stu-id="3d30c-125">On the **Create a new notice template** page, complete the following fields:</span></span>
    - <span data-ttu-id="3d30c-126">**模板名称**：输入通知的友好名称。</span><span class="sxs-lookup"><span data-stu-id="3d30c-126">**Template name**: Enter a friendly name for the notice.</span></span> <span data-ttu-id="3d30c-127">此名称显示在通知仪表板上的通知列表中，以及从案例发送通知时的通知选择列表中。</span><span class="sxs-lookup"><span data-stu-id="3d30c-127">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="3d30c-128">**发件人：输入**通知的发件人电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3d30c-128">**Send from**: Enter the sender email address for the notice.</span></span> <span data-ttu-id="3d30c-129">此地址将显示在发送给员工的所有通知的 "**发件人：** " 字段中，除非在从案例发送通知时进行了更改。</span><span class="sxs-lookup"><span data-stu-id="3d30c-129">This address will appear in the **From:** field in all notices sent to employees unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="3d30c-130">**"抄送" 和 "密件抄送"** 字段：要向其通知策略匹配的可选用户或组，从 Active Directory 为你的订阅进行了选择。</span><span class="sxs-lookup"><span data-stu-id="3d30c-130">**Cc and Bcc** fields: Optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="3d30c-131">**Subject**：邮件的主题行中显示的信息支持文本字符。</span><span class="sxs-lookup"><span data-stu-id="3d30c-131">**Subject**: Information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="3d30c-132">**邮件正文**：显示在邮件正文中的信息支持文本或 HTML 值。</span><span class="sxs-lookup"><span data-stu-id="3d30c-132">**Message body**: Information that appears in the message body, supports text or HTML values.</span></span>
4. <span data-ttu-id="3d30c-133">选择 "**创建**" 以创建并保存通知模板，或选择 "**取消**" 关闭而不保存通知模板。</span><span class="sxs-lookup"><span data-stu-id="3d30c-133">Select **Create** to create and save the notice template or select **Cancel** to close without saving the notice template.</span></span>

## <a name="update-a-notice-template"></a><span data-ttu-id="3d30c-134">更新通知模板</span><span class="sxs-lookup"><span data-stu-id="3d30c-134">Update a notice template</span></span>

<span data-ttu-id="3d30c-135">若要更新现有的内幕风险管理通知模板，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3d30c-135">To update an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="3d30c-136">在[Microsoft 365 合规性中心](https://compliance.microsoft.com)中，转到 "**内幕风险管理**"，然后选择 "**通知模板**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3d30c-136">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="3d30c-137">在 "通知" 仪表板上，选择要管理的通知模板。</span><span class="sxs-lookup"><span data-stu-id="3d30c-137">On the notice dashboard, select the notice template you want to manage.</span></span>
3. <span data-ttu-id="3d30c-138">在 "通知详细信息" 页上，选择 "**编辑**"</span><span class="sxs-lookup"><span data-stu-id="3d30c-138">On the notice details page, select **Edit**</span></span>
4. <span data-ttu-id="3d30c-139">在 "**编辑**" 页上，您可以编辑以下字段：</span><span class="sxs-lookup"><span data-stu-id="3d30c-139">On the **Edit** page, you can edit the following fields:</span></span>
    - <span data-ttu-id="3d30c-140">**模板名称**：为通知输入新的友好名称。</span><span class="sxs-lookup"><span data-stu-id="3d30c-140">**Template name**: Enter a new friendly name for the notice.</span></span> <span data-ttu-id="3d30c-141">此名称显示在通知仪表板上的通知列表中，以及从案例发送通知时的通知选择列表中。</span><span class="sxs-lookup"><span data-stu-id="3d30c-141">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="3d30c-142">**发**件人：更新通知的发件人电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="3d30c-142">**Send from**: Update the sender email address for the notice.</span></span> <span data-ttu-id="3d30c-143">此地址将显示在发送给员工的所有通知的 "**发件人：** " 字段中，除非在从案例发送通知时进行了更改。</span><span class="sxs-lookup"><span data-stu-id="3d30c-143">This address will appear in the **From:** field in all notices sent to employees unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="3d30c-144">**"抄送" 和 "密件抄送**" 字段：更新要向订阅的 Active Directory 中选择的策略匹配项通知的可选用户或组。</span><span class="sxs-lookup"><span data-stu-id="3d30c-144">**Cc and Bcc** fields: Update optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="3d30c-145">**主题**：在邮件的主题行中显示的更新信息支持文本字符。</span><span class="sxs-lookup"><span data-stu-id="3d30c-145">**Subject**: Update information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="3d30c-146">**邮件正文**：更新邮件正文中显示的信息，支持文本或 HTML 值。</span><span class="sxs-lookup"><span data-stu-id="3d30c-146">**Message body**: Update information that appears in the message body, supports text or HTML values.</span></span>
5. <span data-ttu-id="3d30c-147">选择 "**保存**" 以更新并保存通知，或选择 "**取消**" 关闭而不保存通知模板。</span><span class="sxs-lookup"><span data-stu-id="3d30c-147">Select **Save** to update and save the notice or select **Cancel** to close without saving the notice template.</span></span>

## <a name="delete-a-notice-template"></a><span data-ttu-id="3d30c-148">删除通知模板</span><span class="sxs-lookup"><span data-stu-id="3d30c-148">Delete a notice template</span></span>

<span data-ttu-id="3d30c-149">若要删除现有的内幕风险管理通知模板，请完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3d30c-149">To delete an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="3d30c-150">在[Microsoft 365 合规性中心](https://compliance.microsoft.com)中，转到 "**内幕风险管理**"，然后选择 "**通知模板**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3d30c-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="3d30c-151">在 "通知" 仪表板上，选择要删除的通知模板。</span><span class="sxs-lookup"><span data-stu-id="3d30c-151">On the notice dashboard, select the notice template you want to delete.</span></span>
3. <span data-ttu-id="3d30c-152">在工具栏上选择 "**删除**" 图标。</span><span class="sxs-lookup"><span data-stu-id="3d30c-152">Select the **Delete** icon on the toolbar.</span></span>
4. <span data-ttu-id="3d30c-153">若要删除通知模板，请在 "删除" 对话框中选择 **"是"** 。</span><span class="sxs-lookup"><span data-stu-id="3d30c-153">To delete the notice template, select **Yes** in the delete dialog.</span></span> <span data-ttu-id="3d30c-154">若要取消删除，请选择 "**取消**"。</span><span class="sxs-lookup"><span data-stu-id="3d30c-154">To cancel the deletion, select **Cancel**.</span></span>
