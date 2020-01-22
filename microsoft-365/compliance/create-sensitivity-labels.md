---
title: 创建和发布敏感度标签
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 有关创建、配置和发布敏感度标签以对组织的文档和电子邮件进行分类和保护的说明。
ms.openlocfilehash: 964fd20d6ada935d2a76ca0bffccc5bf46161c58
ms.sourcegitcommit: ce0651075aa7e3e1b189437f1990207dd10374b0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2020
ms.locfileid: "41247455"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="17732-103">创建和配置敏感度标签及其策略</span><span class="sxs-lookup"><span data-stu-id="17732-103">Create and configure sensitivity labels and their policies</span></span>

<span data-ttu-id="17732-104">若要创建并发布 [敏感度标签](sensitivity-labels.md)，请转到你的标签管理中心，如 [Microsoft 365 合规性中心](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="17732-104">To create and publish your [sensitivity labels](sensitivity-labels.md), go to your labeling admin center, such as the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="17732-105">此外，还可使用 Microsoft 365 安全中心，或 Office 365 安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="17732-105">You can also use the Microsoft 365 security center, or the Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="17732-106">首先，创建和配置你想要在 Office 应用和服务中使用的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="17732-106">First, create and configure the sensitivity labels that you want to make available in Office apps and for services.</span></span> <span data-ttu-id="17732-107">然后，创建一个或多个包含标签和你配置的策略设置的标签策略。</span><span class="sxs-lookup"><span data-stu-id="17732-107">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="17732-108">这是用于发布所选用户和位置的标签和设置的标签策略。</span><span class="sxs-lookup"><span data-stu-id="17732-108">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="17732-109">创建和配置敏感度标签</span><span class="sxs-lookup"><span data-stu-id="17732-109">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="17732-110">在标签管理中心中，导航到“灵敏度”标签：</span><span class="sxs-lookup"><span data-stu-id="17732-110">In your labeling admin center, navigate to ClassificationSensitivity labels.</span></span>
    
    - <span data-ttu-id="17732-111">Microsoft 365 合规中心：</span><span class="sxs-lookup"><span data-stu-id="17732-111">Microsoft 365 compliance center</span></span> 
        - <span data-ttu-id="17732-112">**解决方案** > **信息保护（预览版）**</span><span class="sxs-lookup"><span data-stu-id="17732-112">**Solutions** > **Information protection (preview)**</span></span>
        
        <span data-ttu-id="17732-113">如果看不到此选项，请先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="17732-113">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="17732-114">Microsoft 365 安全中心：</span><span class="sxs-lookup"><span data-stu-id="17732-114">Microsoft 365 security center</span></span> 
        - <span data-ttu-id="17732-115">**分类** > **灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="17732-115">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="17732-116">Office 365 安全与合规中心：</span><span class="sxs-lookup"><span data-stu-id="17732-116">Office 365 Security & Compliance Center</span></span>
        - <span data-ttu-id="17732-117">**分类** > **灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="17732-117">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="17732-118">在“**标签**”选项卡上，选择“**+ 创建标签**”，以启动“**新建灵敏度标签**”向导 。</span><span class="sxs-lookup"><span data-stu-id="17732-118">On the **Labels** tab, select **+ Create a label** to start the **New sensitivity label** wizard.</span></span>

3. <span data-ttu-id="17732-119">按照提示进行操作以设置标签。</span><span class="sxs-lookup"><span data-stu-id="17732-119">Follow the prompts for the label settings.</span></span>
    
    <span data-ttu-id="17732-120">有关标签设置的详细信息，请参阅概述信息中的“[敏感度标签可以做什么](sensitivity-labels.md#what-sensitivity-labels-can-do)”。</span><span class="sxs-lookup"><span data-stu-id="17732-120">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information.</span></span>

4. <span data-ttu-id="17732-121">重复这些步骤以创建更多标签。</span><span class="sxs-lookup"><span data-stu-id="17732-121">Repeat these steps to create more labels.</span></span> <span data-ttu-id="17732-122">但是，如果想要创建子标签，请先选择父标签，然后点击“**...**”并选择“**更多操作**”，然后选择“**添加子标签**”。</span><span class="sxs-lookup"><span data-stu-id="17732-122">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

5. <span data-ttu-id="17732-123">创建所需的所有标签后，请查看其顺序，如有必要，请向上或向下移动它们。</span><span class="sxs-lookup"><span data-stu-id="17732-123">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="17732-124">若要更改标签的顺序，请选择“**...**”进行**更多操作**”，然后选择 “**上移 **”或 “**下移**”。</span><span class="sxs-lookup"><span data-stu-id="17732-124">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="17732-125">有关详细信息，请参阅概述信息中的“[标签优先级（顺序非常重要）](sensitivity-labels.md#label-priority-order-matters)”。</span><span class="sxs-lookup"><span data-stu-id="17732-125">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="17732-126">若要编辑现有标签，请将其选中，然后选择“**编辑标签**”。</span><span class="sxs-lookup"><span data-stu-id="17732-126">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="17732-127">这将启动“**编辑敏感度标签**”向导，可用于更改步骤 3 中的所有标签设置。</span><span class="sxs-lookup"><span data-stu-id="17732-127">This starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 3.</span></span> 

> [!NOTE]
> <span data-ttu-id="17732-128">如果要编辑已使用标签策略发布的标签，则在完成该向导时不需要执行额外步骤。</span><span class="sxs-lookup"><span data-stu-id="17732-128">If you edit a label that's already published by using a label policy, no extra steps are needed when you finish the wizard.</span></span> <span data-ttu-id="17732-129">例如，不需要将其添加到新的标签策略。</span><span class="sxs-lookup"><span data-stu-id="17732-129">For example, you don't need to add it to a new label policy.</span></span> <span data-ttu-id="17732-130">但是，可允许在 24 小时内将所做的更改复制到用户和服务。</span><span class="sxs-lookup"><span data-stu-id="17732-130">However, allow up to 24 hours for the changes to replicate to users and services.</span></span>

<span data-ttu-id="17732-131">发布标签之前，无法在应用程序或服务中使用。</span><span class="sxs-lookup"><span data-stu-id="17732-131">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="17732-132">如果要发布标签，必须要添加至标签策略。</span><span class="sxs-lookup"><span data-stu-id="17732-132">To publish the labels, they must be added to a label policy.</span></span>

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="17732-133">附加标签设置在 Office 365 安全与合规中心 PowerShell 中可用</span><span class="sxs-lookup"><span data-stu-id="17732-133">Additional label settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="17732-134">附加标签设置可在 “[Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)”中的“[设置标签](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps)“中使用。</span><span class="sxs-lookup"><span data-stu-id="17732-134">Additional label settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="17732-135">例如，使用 *LocaleSettings* 参数为标签名称和工具提示指定不同的语言。</span><span class="sxs-lookup"><span data-stu-id="17732-135">For example, use the the *LocaleSettings* parameter to specify different languages for your label names and tooltips.</span></span> 

<span data-ttu-id="17732-136">使用此 cmdlet，还可为 Azure 信息保护统一标签客户端指定[“高级设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)”。</span><span class="sxs-lookup"><span data-stu-id="17732-136">Using this cmdlet, you can also specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="17732-137">这些高级设置包括应用标签时设定标签颜色，应用自定义属性。</span><span class="sxs-lookup"><span data-stu-id="17732-137">These advanced settings include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="17732-138">如需完整的列表，请参阅“[可用的高级标签策略设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)”。</span><span class="sxs-lookup"><span data-stu-id="17732-138">For the full list, see [Available advanced settings for label policies](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies).</span></span> 

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="17732-139">通过创建标签策略来发布敏感度标签</span><span class="sxs-lookup"><span data-stu-id="17732-139">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="17732-140">在标签管理中心中，导航到“灵敏度”标签：</span><span class="sxs-lookup"><span data-stu-id="17732-140">In your labeling admin center, navigate to ClassificationSensitivity labels.</span></span>
    
    - <span data-ttu-id="17732-141">Microsoft 365 合规中心：</span><span class="sxs-lookup"><span data-stu-id="17732-141">Microsoft 365 compliance center</span></span> 
        - <span data-ttu-id="17732-142">**解决方案** > **信息保护（预览版）**</span><span class="sxs-lookup"><span data-stu-id="17732-142">**Solutions** > **Information protection (preview)**</span></span>
        
        <span data-ttu-id="17732-143">如果看不到此选项，请先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="17732-143">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="17732-144">Microsoft 365 安全中心：</span><span class="sxs-lookup"><span data-stu-id="17732-144">Microsoft 365 security center</span></span> 
        - <span data-ttu-id="17732-145">**分类** > **灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="17732-145">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="17732-146">Office 365 安全与合规中心：</span><span class="sxs-lookup"><span data-stu-id="17732-146">Office 365 Security & Compliance Center</span></span>
        - <span data-ttu-id="17732-147">**分类** > **灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="17732-147">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="17732-148">选择“**标签策略**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="17732-148">Select the **Label policies** tab.</span></span>

3. <span data-ttu-id="17732-149">选择“**发布标签**”以启动“**创建策略向导**”。</span><span class="sxs-lookup"><span data-stu-id="17732-149">Select **Publish labels** to start the **Create policy wizard**.</span></span>

4. <span data-ttu-id="17732-150">选择 “**选择要发布的敏感度标签**”。</span><span class="sxs-lookup"><span data-stu-id="17732-150">Select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="17732-151">选择可在应用和服务中可以使用的标签，随后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="17732-151">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>

5. <span data-ttu-id="17732-152">查看所选标签，若要进行任何更改，请选择“\*\*编辑 \*\*”。</span><span class="sxs-lookup"><span data-stu-id="17732-152">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="17732-153">否则选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="17732-153">Otherwise, select **Next**.</span></span>

6. <span data-ttu-id="17732-154">按照提示配置策略设置。</span><span class="sxs-lookup"><span data-stu-id="17732-154">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="17732-155">有关设置的详细信息，请参阅概述信息中的“[标签策略可以做什么](sensitivity-labels.md#what-label-policies-can-do)”。</span><span class="sxs-lookup"><span data-stu-id="17732-155">For more information about the settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information.</span></span>

7. <span data-ttu-id="17732-156">如果不同的用户或位置需要不同的策略设置，请重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="17732-156">Repeat these steps if you need different policy settings for different users or locations.</span></span> <span data-ttu-id="17732-157">例如，希望为一组用户创建附加标签，或用户为子集创建不同的默认标签。</span><span class="sxs-lookup"><span data-stu-id="17732-157">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span>

8. <span data-ttu-id="17732-158">如果创建多个可能导致用户或位置发生冲突的标签策略，请查看策略顺序，并根据需要向上或向下移动。</span><span class="sxs-lookup"><span data-stu-id="17732-158">If you create more than one label policy that might result in a conflict for a user or location, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="17732-159">若要更改标签策略的顺序，请选择“**...**”进行**更多操作**”，然后选择 “**上移 **”或 “**下移**”。</span><span class="sxs-lookup"><span data-stu-id="17732-159">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="17732-160">有关详细信息，请参阅概述信息中的“[标签策略优先级（顺序非常重要）](sensitivity-labels.md#label-policy-priority-order-matters)”。</span><span class="sxs-lookup"><span data-stu-id="17732-160">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="17732-161">完成向导会自动发布标签策略。</span><span class="sxs-lookup"><span data-stu-id="17732-161">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="17732-162">若要更改已发布的策略，只需对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="17732-162">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="17732-163">没有特定发布或重新发布操作可供选择。</span><span class="sxs-lookup"><span data-stu-id="17732-163">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="17732-164">若要编辑现有标签策略，请将其选中，然后选择“**编辑策略**”。</span><span class="sxs-lookup"><span data-stu-id="17732-164">To edit an existing label policy, select it, and then select **Edit Policy**.</span></span> <span data-ttu-id="17732-165">这将启动“**创建策略**”向导，可用于编辑所包含的标签和标签设置。</span><span class="sxs-lookup"><span data-stu-id="17732-165">This starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="17732-166">完成向导后，所有更改都将自动复制到所选用户和服务。</span><span class="sxs-lookup"><span data-stu-id="17732-166">When you complete the wizard, any changes are automatically replicated to the selected users and locations.</span></span>

<span data-ttu-id="17732-167">通常情况下，用户会在几个小时内查看其 Office 应用中的标签。</span><span class="sxs-lookup"><span data-stu-id="17732-167">Typically, users see the labels in their Office apps within a couple of hours.</span></span> <span data-ttu-id="17732-168">但是，可允许在 24 小时内将标签策略及其任何更改复制到所有用户和服务。</span><span class="sxs-lookup"><span data-stu-id="17732-168">However, allow up to 24 hours for your label policies and any changes to them to replicate to all users and services.</span></span>

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="17732-169">附加标签策略设置在 Office 365 安全与合规中心 PowerShell 中可用</span><span class="sxs-lookup"><span data-stu-id="17732-169">Additional label policy settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="17732-170">附加标签策略设置可在 “[Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)”中的“[设置标签](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps)“中使用。</span><span class="sxs-lookup"><span data-stu-id="17732-170">Additional label policy settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="17732-171">使用此 cmdlet，可为 Azure 信息保护统一标签客户端指定[“高级设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)”。</span><span class="sxs-lookup"><span data-stu-id="17732-171">Using this cmdlet, you can specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="17732-172">这些高级设置包括为 Outlook 设置不同的默认标签，并在 Outlook 中实现弹出消息，警告、两端对齐或阻止正在发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="17732-172">These advanced settings include setting a different default label for Outlook, and implement pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="17732-173">如需完整的列表，请参阅“[可用的高级标签设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)”。</span><span class="sxs-lookup"><span data-stu-id="17732-173">For the full list, see [Available advanced settings for labels](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels).</span></span> 

<span data-ttu-id="17732-174">此外，还可使用此 cmdlet 在标签策略中添加和删除标签。</span><span class="sxs-lookup"><span data-stu-id="17732-174">You can also use this cmdlet to add and remove labels to and from a label policy.</span></span>


## <a name="next-steps"></a><span data-ttu-id="17732-175">后续步骤</span><span class="sxs-lookup"><span data-stu-id="17732-175">Next steps</span></span>

<span data-ttu-id="17732-176">若要根据具体情况配置和使用敏感度标签，请使用下列文章：</span><span class="sxs-lookup"><span data-stu-id="17732-176">To configure and use your sensitivity labels for specific scenarios, see the following articles:</span></span>

- [<span data-ttu-id="17732-177">使用敏感度标签中的加密限制对内容的访问</span><span class="sxs-lookup"><span data-stu-id="17732-177">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="17732-178">将敏感度标签自动应用于内容</span><span class="sxs-lookup"><span data-stu-id="17732-178">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="17732-179">将灵敏度标签与团队、组和网站配合使用</span><span class="sxs-lookup"><span data-stu-id="17732-179">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="17732-180">启用 SharePoint 和 OneDrive 中 Office 文件的灵敏度标签</span><span class="sxs-lookup"><span data-stu-id="17732-180">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="17732-181">若要监视标签的使用情况，请参阅“[使用标签分析查看标签使用情况](label-analytics.md)”。</span><span class="sxs-lookup"><span data-stu-id="17732-181">To monitor how your labels are being used, see [View label usage with label analytics](label-analytics.md).</span></span>