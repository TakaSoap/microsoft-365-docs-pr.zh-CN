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
ms.openlocfilehash: 200b101b0083abbba90eaced9720db854ff02bbb
ms.sourcegitcommit: 48a45b0d2c60d4d79669174f462603a43f272875
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2020
ms.locfileid: "41233854"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="c8f7a-103">创建和配置敏感度标签及其策略</span><span class="sxs-lookup"><span data-stu-id="c8f7a-103">Create and configure sensitivity labels and their policies</span></span>

<span data-ttu-id="c8f7a-104">若要创建并发布 [敏感度标签](sensitivity-labels.md)，请转到你的标签管理中心，如 [Microsoft 365 合规性中心](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-104">To create and publish your [sensitivity labels](sensitivity-labels.md), go to your labeling admin center, such as the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="c8f7a-105">此外，还可使用 Microsoft 365 安全中心，或 Office 365 安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-105">You can also use the Microsoft 365 security center, or the Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="c8f7a-106">首先，创建和配置你想要在 Office 应用和服务中使用的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-106">First, create and configure the sensitivity labels that you want to make available in Office apps and for services.</span></span> <span data-ttu-id="c8f7a-107">然后，创建一个或多个包含标签和你配置的策略设置的标签策略。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-107">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="c8f7a-108">这是用于发布所选用户和位置的标签和设置的标签策略。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-108">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="c8f7a-109">创建和配置敏感度标签</span><span class="sxs-lookup"><span data-stu-id="c8f7a-109">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="c8f7a-110">在标签管理中心中，导航到“**分类** > **敏感度标签**”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-110">In your labeling admin center, navigate to **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="c8f7a-111">在“**标签**”选项卡上，选择“**+ 创建标签**”，以启动 “**新建敏感度标签**”向导。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-111">On the **Labels** tab, select **+ Create a label** to start the **New sensitivity label** wizard.</span></span>

3. <span data-ttu-id="c8f7a-112">按照提示进行操作以设置标签。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-112">Follow the prompts for the label settings.</span></span>
    
    <span data-ttu-id="c8f7a-113">有关标签设置的详细信息，请参阅概述信息中的“[敏感度标签可以做什么](sensitivity-labels.md#what-sensitivity-labels-can-do)”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-113">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information.</span></span>

4. <span data-ttu-id="c8f7a-114">重复这些步骤以创建更多标签。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-114">Repeat these steps to create more labels.</span></span> <span data-ttu-id="c8f7a-115">但是，如果想要创建子标签，请先选择父标签，然后点击“**...**”并选择“**更多操作**”，然后选择“**添加子标签**”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-115">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

5. <span data-ttu-id="c8f7a-116">创建所需的所有标签后，请查看其顺序，如有必要，请向上或向下移动它们。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-116">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="c8f7a-117">若要更改标签的顺序，请选择“**...**”进行**更多操作**”，然后选择 “**上移 **”或 “**下移**”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-117">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="c8f7a-118">有关详细信息，请参阅概述信息中的“[标签优先级（顺序非常重要）](sensitivity-labels.md#label-priority-order-matters)”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-118">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="c8f7a-119">若要编辑现有标签，请将其选中，然后选择“**编辑标签**”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-119">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="c8f7a-120">这将启动“**编辑敏感度标签**”向导，可用于更改步骤 3 中的所有标签设置。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-120">This starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 3.</span></span> <span data-ttu-id="c8f7a-121">如果已使用标签策略发布了标签，则无需额外的步骤，但最长可允许24 小时将所做的更改复制到用户和位置。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-121">If the label is already published by using a label policy, no extra steps are needed, but allow up to 24 hours for the changes to replicate to users and locations.</span></span>

<span data-ttu-id="c8f7a-122">发布标签之前，无法在应用程序或服务中使用。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-122">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="c8f7a-123">如果要发布标签，必须要添加至标签策略。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-123">To publish the labels, they must be added to a label policy.</span></span>

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="c8f7a-124">附加标签设置在 Office 365 安全与合规中心 PowerShell 中可用</span><span class="sxs-lookup"><span data-stu-id="c8f7a-124">Additional label settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="c8f7a-125">附加标签设置可在 “[Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)”中的“[设置标签](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps)“中使用。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-125">Additional label settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="c8f7a-126">例如，使用 *LocaleSettings* 参数为标签名称和工具提示指定不同的语言。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-126">For example, use the the *LocaleSettings* parameter to specify different languages for your label names and tooltips.</span></span> 

<span data-ttu-id="c8f7a-127">使用此 cmdlet，还可为 Azure 信息保护统一标签客户端指定[“高级设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-127">Using this cmdlet, you can also specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="c8f7a-128">这些高级设置包括应用标签时设定标签颜色，应用自定义属性。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-128">These advanced settings include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="c8f7a-129">如需完整的列表，请参阅“[可用的高级标签策略设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-129">For the full list, see [Available advanced settings for label policies](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies).</span></span> 

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="c8f7a-130">通过创建标签策略来发布敏感度标签</span><span class="sxs-lookup"><span data-stu-id="c8f7a-130">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="c8f7a-131">在标签管理中心中，导航到“**分类** > **敏感度标签**”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-131">In your labeling admin center, navigate to **Classification** > **Sensitivity labels**.</span></span>

2. <span data-ttu-id="c8f7a-132">选择“**标签策略**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-132">Select the **Label policies** tab.</span></span>

3. <span data-ttu-id="c8f7a-133">选择“**发布标签**”以启动“**创建策略向导**”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-133">Select **Publish labels** to start the **Create policy wizard**.</span></span>

4. <span data-ttu-id="c8f7a-134">选择 “**选择要发布的敏感度标签**”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-134">Select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="c8f7a-135">选择可在应用和服务中可以使用的标签，随后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-135">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>

5. <span data-ttu-id="c8f7a-136">查看所选标签，若要进行任何更改，请选择“\*\*编辑 \*\*”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-136">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="c8f7a-137">否则选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-137">Otherwise select Next.</span></span>

6. <span data-ttu-id="c8f7a-138">按照提示配置策略设置。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-138">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="c8f7a-139">有关设置的详细信息，请参阅概述信息中的“[标签策略可以做什么](sensitivity-labels.md#what-label-policies-can-do)”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-139">For more information about the settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information.</span></span>

7. <span data-ttu-id="c8f7a-140">如果不同的用户或位置需要不同的策略设置，请重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-140">Repeat these steps if you need different policy settings for different users or locations.</span></span> <span data-ttu-id="c8f7a-141">例如，希望为一组用户创建附加标签，或用户为子集创建不同的默认标签。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-141">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span>

8. <span data-ttu-id="c8f7a-142">如果创建多个可能导致用户或位置发生冲突的标签策略，请查看策略顺序，并根据需要向上或向下移动。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-142">If you create more than one label policy that might result in a conflict for a user or location, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="c8f7a-143">若要更改标签策略的顺序，请选择“**...**”进行**更多操作**”，然后选择 “**上移 **”或 “**下移**”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-143">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="c8f7a-144">有关详细信息，请参阅概述信息中的“[标签策略优先级（顺序非常重要）](sensitivity-labels.md#label-policy-priority-order-matters)”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-144">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="c8f7a-145">完成向导会自动发布标签策略。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-145">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="c8f7a-146">若要更改已发布的策略，只需对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-146">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="c8f7a-147">没有特定发布或重新发布操作可供选择。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-147">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="c8f7a-148">若要编辑现有标签策略，请将其选中，然后选择“**编辑策略**”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-148">To edit an existing label policy, select it, and then select **Edit Policy**.</span></span> <span data-ttu-id="c8f7a-149">这将启动“**创建策略**”向导，可用于编辑所包含的标签和标签设置。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-149">This starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="c8f7a-150">完成向导后，所有更改都将自动复制到所选用户和位置。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-150">When you complete the wizard, any changes are automatically replicated to the selected users and locations.</span></span> <span data-ttu-id="c8f7a-151">最长允许24小时完成复制。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-151">Allow up to 24 hours for the replication to complete.</span></span>

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="c8f7a-152">附加标签策略设置在 Office 365 安全与合规中心 PowerShell 中可用</span><span class="sxs-lookup"><span data-stu-id="c8f7a-152">Additional label policy settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="c8f7a-153">附加标签策略设置可在 “[Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)”中的“[设置标签](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps)“中使用。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-153">Additional label policy settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="c8f7a-154">使用此 cmdlet，可为 Azure 信息保护统一标签客户端指定[“高级设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-154">Using this cmdlet, you can specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="c8f7a-155">这些高级设置包括为 Outlook 设置不同的默认标签，并在 Outlook 中实现弹出消息，警告、两端对齐或阻止正在发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-155">These advanced settings include setting a different default label for Outlook, and implement pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="c8f7a-156">如需完整的列表，请参阅“[可用的高级标签设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-156">For the full list, see [Available advanced settings for labels](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels).</span></span> 

<span data-ttu-id="c8f7a-157">此外，还可使用此 cmdlet 在标签策略中添加和删除标签。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-157">You can also use this cmdlet to add and remove labels to and from a label policy.</span></span>


## <a name="next-steps"></a><span data-ttu-id="c8f7a-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c8f7a-158">Next steps</span></span>

<span data-ttu-id="c8f7a-159">若要针对特定的方案配置和使用敏感度标签，参见下列文章：</span><span class="sxs-lookup"><span data-stu-id="c8f7a-159">To configure and use your sensitivity labels for specific scenarios, see the following articles:</span></span>

- [<span data-ttu-id="c8f7a-160">使用敏感度标签中的加密限制对内容的访问</span><span class="sxs-lookup"><span data-stu-id="c8f7a-160">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="c8f7a-161">将敏感度标签自动应用于内容</span><span class="sxs-lookup"><span data-stu-id="c8f7a-161">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="c8f7a-162">将灵敏度标签与团队、组和网站配合使用</span><span class="sxs-lookup"><span data-stu-id="c8f7a-162">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="c8f7a-163">启用 SharePoint 和 OneDrive 中 Office 文件的灵敏度标签</span><span class="sxs-lookup"><span data-stu-id="c8f7a-163">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="c8f7a-164">若要监视标签的使用情况，请参阅“[使用标签分析查看标签使用情况](label-analytics.md)”。</span><span class="sxs-lookup"><span data-stu-id="c8f7a-164">To monitor how your labels are being used, see [View label usage with label analytics](label-analytics.md).</span></span>