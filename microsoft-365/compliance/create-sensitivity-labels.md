---
title: 创建和发布敏感度标签
f1.keywords:
- NOCSH
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
description: 所有 Microsoft 信息保护解决方案的相关要求：创建、配置和发布敏感度标签以对组织的文档和电子邮件进行分类和保护。
ms.openlocfilehash: d2300a54583c0b2d12de86e3dbb5f3116daf6460
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2020
ms.locfileid: "42543128"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="7631d-103">创建和配置敏感度标签及其策略</span><span class="sxs-lookup"><span data-stu-id="7631d-103">Create and configure sensitivity labels and their policies</span></span>

<span data-ttu-id="7631d-104">所有 Microsoft 信息保护解决方案（有时缩写为 MIP）通过使用 [敏感度标签](sensitivity-labels.md)实现。</span><span class="sxs-lookup"><span data-stu-id="7631d-104">All Microsoft Information Protection solutions (sometimes abbreviated to MIP) are implemented by using [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="7631d-105">要创建并发布这些标签，请转到标签管理中心，例如 [Microsoft 365 合规中心](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="7631d-105">To create and publish these labels, go to your labeling admin center, such as the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="7631d-106">此外，还可使用 Microsoft 365 安全中心或 Office 365 安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="7631d-106">You can also use the Microsoft 365 security center, or the Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="7631d-107">首先，创建和配置要在应用和其他服务中使用的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="7631d-107">First, create and configure the sensitivity labels that you want to make available for apps and other services.</span></span> <span data-ttu-id="7631d-108">例如，希望用户在 Office 应用中看到和采用的标签。</span><span class="sxs-lookup"><span data-stu-id="7631d-108">For example, the labels you want users to see and apply from Office apps.</span></span> 

<span data-ttu-id="7631d-109">然后，创建一个或多个包含标签和你配置的策略设置的标签策略。</span><span class="sxs-lookup"><span data-stu-id="7631d-109">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="7631d-110">这是用于发布所选用户和位置的标签和设置的标签策略。</span><span class="sxs-lookup"><span data-stu-id="7631d-110">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7631d-111">准备工作</span><span class="sxs-lookup"><span data-stu-id="7631d-111">Before you begin</span></span>

<span data-ttu-id="7631d-112">组织的全局管理员具有创建和管理敏感度标签各方面的完全权限。</span><span class="sxs-lookup"><span data-stu-id="7631d-112">The global admin for your organization has full permissions to create and manage all aspects of sensitivity labels.</span></span> <span data-ttu-id="7631d-113">如果你未以全局管理员的身份登录，请参阅[创建和管理敏感度标签所需的权限](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="7631d-113">If you aren't signing in as a global admin, see [Permissions required to create and manage sensitivity labels](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="7631d-114">创建和配置敏感度标签</span><span class="sxs-lookup"><span data-stu-id="7631d-114">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="7631d-115">在标签管理中心中，导航到“灵敏度”标签：</span><span class="sxs-lookup"><span data-stu-id="7631d-115">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="7631d-116">Microsoft 365 合规中心：</span><span class="sxs-lookup"><span data-stu-id="7631d-116">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="7631d-117">**解决方案** > **信息保护**</span><span class="sxs-lookup"><span data-stu-id="7631d-117">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="7631d-118">如果看不到此选项，请先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="7631d-118">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="7631d-119">Microsoft 365 安全中心：</span><span class="sxs-lookup"><span data-stu-id="7631d-119">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="7631d-120">**分类** > **灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="7631d-120">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="7631d-121">Office 365 安全与合规中心：</span><span class="sxs-lookup"><span data-stu-id="7631d-121">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="7631d-122">**分类** > **灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="7631d-122">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="7631d-123">在“**标签**”选项卡上，选择“**+ 创建标签**”，以启动“**新建灵敏度标签**”向导 。</span><span class="sxs-lookup"><span data-stu-id="7631d-123">On the **Labels** tab, select **+ Create a label** to start the **New sensitivity label** wizard.</span></span>

3. <span data-ttu-id="7631d-124">按照提示进行操作以设置标签。</span><span class="sxs-lookup"><span data-stu-id="7631d-124">Follow the prompts for the label settings.</span></span>
    
    <span data-ttu-id="7631d-125">有关标签设置的详细信息，请参阅概述信息中的“[敏感度标签可以做什么](sensitivity-labels.md#what-sensitivity-labels-can-do)”。</span><span class="sxs-lookup"><span data-stu-id="7631d-125">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information.</span></span>

4. <span data-ttu-id="7631d-126">重复这些步骤以创建更多标签。</span><span class="sxs-lookup"><span data-stu-id="7631d-126">Repeat these steps to create more labels.</span></span> <span data-ttu-id="7631d-127">但是，如果想要创建子标签，请先选择父标签，然后点击“**...**”并选择“**更多操作**”，然后选择“**添加子标签**”。</span><span class="sxs-lookup"><span data-stu-id="7631d-127">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

5. <span data-ttu-id="7631d-128">创建所需的所有标签后，请查看其顺序，如有必要，请向上或向下移动它们。</span><span class="sxs-lookup"><span data-stu-id="7631d-128">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="7631d-129">若要更改标签的顺序，请选择“**...**”进行**更多操作**”，然后选择 “**上移 **”或 “**下移**”。</span><span class="sxs-lookup"><span data-stu-id="7631d-129">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="7631d-130">有关详细信息，请参阅概述信息中的“[标签优先级（顺序非常重要）](sensitivity-labels.md#label-priority-order-matters)”。</span><span class="sxs-lookup"><span data-stu-id="7631d-130">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="7631d-131">若要编辑现有标签，请将其选中，然后选择“**编辑标签**”。</span><span class="sxs-lookup"><span data-stu-id="7631d-131">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="7631d-132">这将启动“**编辑敏感度标签**”向导，可用于更改步骤 3 中的所有标签设置。</span><span class="sxs-lookup"><span data-stu-id="7631d-132">This starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 3.</span></span> 

> [!NOTE]
> <span data-ttu-id="7631d-133">如果要编辑已使用标签策略发布的标签，则在完成该向导时不需要执行额外步骤。</span><span class="sxs-lookup"><span data-stu-id="7631d-133">If you edit a label that's already published by using a label policy, no extra steps are needed when you finish the wizard.</span></span> <span data-ttu-id="7631d-134">例如，不需要将其添加到新的标签策略，即可对相同用户提供所做的更改。</span><span class="sxs-lookup"><span data-stu-id="7631d-134">For example, you don't need to add it to a new label policy for the changes to become available to the same users.</span></span> <span data-ttu-id="7631d-135">但是，可允许在 24 小时内将所做的更改复制到用户和服务。</span><span class="sxs-lookup"><span data-stu-id="7631d-135">However, allow up to 24 hours for the changes to replicate to users and services.</span></span>

<span data-ttu-id="7631d-136">发布标签之前，无法在应用程序或服务中使用。</span><span class="sxs-lookup"><span data-stu-id="7631d-136">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="7631d-137">若要发布标签，必须将其[添加到标签策略](#publish-sensitivity-labels-by-creating-a-label-policy)。</span><span class="sxs-lookup"><span data-stu-id="7631d-137">To publish the labels, they must be [added to a label policy](#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7631d-138">在此“**标签**”选项卡上，不要选择“**发布标签**”选项卡（或在编辑标签时的“**发布标签**”按钮），除非你需要创建新的标签策略。</span><span class="sxs-lookup"><span data-stu-id="7631d-138">On this **Labels** tab, do not select the **Publish labels** tab (or the **Publish label** button when you edit a label) unless you need to create a new label policy.</span></span> <span data-ttu-id="7631d-139">仅当用户需要不同的标签或不同的策略设置时，才需要多个标签策略。</span><span class="sxs-lookup"><span data-stu-id="7631d-139">You need multiple label policies only if users need different labels or different policy settings.</span></span> <span data-ttu-id="7631d-140">旨在创建尽可能少的标签策略 - 组织只有一个标签策略的情况并不少见。</span><span class="sxs-lookup"><span data-stu-id="7631d-140">Aim to have as few label policies as possible — it's not uncommon to have just one label policy for the organization.</span></span>

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="7631d-141">附加标签设置在 Office 365 安全与合规中心 PowerShell 中可用</span><span class="sxs-lookup"><span data-stu-id="7631d-141">Additional label settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="7631d-142">附加标签设置可在 “[Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)”中的“[设置标签](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps)“中使用。</span><span class="sxs-lookup"><span data-stu-id="7631d-142">Additional label settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="7631d-143">使用 *LocaleSettings* 参数来进行跨国部署，以便用户可查看使用本地语言的标签名称和工具提示。</span><span class="sxs-lookup"><span data-stu-id="7631d-143">Use the *LocaleSettings* parameter for multinational deployments so that users see the label name and tooltip in their local language.</span></span> <span data-ttu-id="7631d-144">有关配置示例，请参阅下面的部分。</span><span class="sxs-lookup"><span data-stu-id="7631d-144">See the following section for an example configuration.</span></span> 

<span data-ttu-id="7631d-145">使用此 cmdlet，还可为 Azure 信息保护统一标签客户端指定[“高级设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)”。</span><span class="sxs-lookup"><span data-stu-id="7631d-145">Using this cmdlet, you can also specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="7631d-146">这些高级设置包括应用标签时设定标签颜色，应用自定义属性。</span><span class="sxs-lookup"><span data-stu-id="7631d-146">These advanced settings include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="7631d-147">如需完整的列表，请参阅“[可用的高级标签策略设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)”。</span><span class="sxs-lookup"><span data-stu-id="7631d-147">For the full list, see [Available advanced settings for label policies](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies).</span></span> 

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a><span data-ttu-id="7631d-148">配置不同语言的灵敏度标签的配置示例</span><span class="sxs-lookup"><span data-stu-id="7631d-148">Example configuration to configure a sensitivity label for different languages</span></span>

<span data-ttu-id="7631d-149">下面的示例显示了名为“Public”的标签的 PowerShell 配置以及工具提示的占位符文本。</span><span class="sxs-lookup"><span data-stu-id="7631d-149">The following example shows the PowerShell configuration for a label named "Public" with placeholder text for the tooltip.</span></span> <span data-ttu-id="7631d-150">在此示例中，将为法语、意大利语和德语配置标签名称和工具提示文本。</span><span class="sxs-lookup"><span data-stu-id="7631d-150">In this example, the label name and tooltip text is configured for French, Italian, and German.</span></span>

<span data-ttu-id="7631d-151">进行此配置后，如果用户拥有使用这些显示语言的 Office 应用，则会看到他们的标签名称和工具提示使用相同的语言。</span><span class="sxs-lookup"><span data-stu-id="7631d-151">As a result of this configuration, users who have Office apps that use those display languages see their label names and tooltips in the same language.</span></span> <span data-ttu-id="7631d-152">类似地，当你已安装 Azure 信息保护统一标签客户端以标记文件资源管理器中的文件时，如果用户具有这些语言版本的 Windows，则他们在使用右键单击来进行标记时将会看到其标签名称和工具提示以本地语言显示。</span><span class="sxs-lookup"><span data-stu-id="7631d-152">Similarly, if you have the Azure Information Protection unified labeling client installed to label files from File Explorer, users who have those language versions of Windows see their label names and tooltips in their local language when they use the right-click actions for labeling.</span></span>

<span data-ttu-id="7631d-153">对于需要支持的语言，请使用 Office [语言标识符](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers)（也称为语言标记），并指定你自己的标签名称和工具提示翻译。</span><span class="sxs-lookup"><span data-stu-id="7631d-153">For the languages that you need to support, use the Office [language identifiers](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (also known as language tags), and specify your own translation for the label name and tooltip.</span></span>

<span data-ttu-id="7631d-154">在 PowerShell 中运行命令之前，必须先[连接到 Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="7631d-154">Before you run the commands in PowerShell, you must first [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>


```powershell
$Languages = @("fr-fr","it-it","de-de")
$DisplayNames=@("Publique","Publico","Oeffentlich")
$Tooltips = @("Texte Français","Testo italiano","Deutscher text")
$label = "Public"
$DisplayNameLocaleSettings = [PSCustomObject]@{LocaleKey='DisplayName';
Settings=@(
@{key=$Languages[0];Value=$DisplayNames[0];}
@{key=$Languages[1];Value=$DisplayNames[1];}
@{key=$Languages[2];Value=$DisplayNames[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $DisplayNameLocaleSettings -Depth 3 -Compress)
$TooltipLocaleSettings = [PSCustomObject]@{LocaleKey='Tooltip';
Settings=@(
@{key=$Languages[0];Value=$Tooltips[0];}
@{key=$Languages[1];Value=$Tooltips[1];}
@{key=$Languages[2];Value=$Tooltips[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $TooltipLocaleSettings -Depth 3 -Compress)
```

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="7631d-155">通过创建标签策略来发布敏感度标签</span><span class="sxs-lookup"><span data-stu-id="7631d-155">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="7631d-156">在标签管理中心中，导航到“灵敏度”标签：</span><span class="sxs-lookup"><span data-stu-id="7631d-156">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="7631d-157">Microsoft 365 合规中心：</span><span class="sxs-lookup"><span data-stu-id="7631d-157">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="7631d-158">**解决方案** > **信息保护**</span><span class="sxs-lookup"><span data-stu-id="7631d-158">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="7631d-159">如果看不到此选项，请先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="7631d-159">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="7631d-160">Microsoft 365 安全中心：</span><span class="sxs-lookup"><span data-stu-id="7631d-160">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="7631d-161">**分类** > **灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="7631d-161">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="7631d-162">Office 365 安全与合规中心：</span><span class="sxs-lookup"><span data-stu-id="7631d-162">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="7631d-163">**分类** > **灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="7631d-163">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="7631d-164">选择“**标签策略**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="7631d-164">Select the **Label policies** tab.</span></span>

3. <span data-ttu-id="7631d-165">选择“**发布标签**”以启动“**创建策略向导**”。</span><span class="sxs-lookup"><span data-stu-id="7631d-165">Select **Publish labels** to start the **Create policy wizard**.</span></span>

4. <span data-ttu-id="7631d-166">选择 “**选择要发布的敏感度标签**”。</span><span class="sxs-lookup"><span data-stu-id="7631d-166">Select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="7631d-167">选择可在应用和服务中可以使用的标签，随后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="7631d-167">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>

5. <span data-ttu-id="7631d-168">查看所选标签，若要进行任何更改，请选择“\*\*编辑 \*\*”。</span><span class="sxs-lookup"><span data-stu-id="7631d-168">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="7631d-169">否则选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="7631d-169">Otherwise, select **Next**.</span></span>

6. <span data-ttu-id="7631d-170">按照提示配置策略设置。</span><span class="sxs-lookup"><span data-stu-id="7631d-170">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="7631d-171">有关设置的详细信息，请参阅概述信息中的“[标签策略可以做什么](sensitivity-labels.md#what-label-policies-can-do)”。</span><span class="sxs-lookup"><span data-stu-id="7631d-171">For more information about the settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information.</span></span>

7. <span data-ttu-id="7631d-172">如果不同的用户或位置需要不同的策略设置，请重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="7631d-172">Repeat these steps if you need different policy settings for different users or locations.</span></span> <span data-ttu-id="7631d-173">例如，希望为一组用户创建附加标签，或用户为子集创建不同的默认标签。</span><span class="sxs-lookup"><span data-stu-id="7631d-173">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span>

8. <span data-ttu-id="7631d-174">如果创建多个可能导致用户或位置发生冲突的标签策略，请查看策略顺序，并根据需要向上或向下移动。</span><span class="sxs-lookup"><span data-stu-id="7631d-174">If you create more than one label policy that might result in a conflict for a user or location, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="7631d-175">若要更改标签策略的顺序，请选择“**...**”进行**更多操作**”，然后选择 “**上移 **”或 “**下移**”。</span><span class="sxs-lookup"><span data-stu-id="7631d-175">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="7631d-176">有关详细信息，请参阅概述信息中的“[标签策略优先级（顺序非常重要）](sensitivity-labels.md#label-policy-priority-order-matters)”。</span><span class="sxs-lookup"><span data-stu-id="7631d-176">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="7631d-177">完成向导会自动发布标签策略。</span><span class="sxs-lookup"><span data-stu-id="7631d-177">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="7631d-178">若要更改已发布的策略，只需对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="7631d-178">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="7631d-179">没有特定发布或重新发布操作可供选择。</span><span class="sxs-lookup"><span data-stu-id="7631d-179">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="7631d-180">若要编辑现有标签策略，请将其选中，然后选择“**编辑策略**”。</span><span class="sxs-lookup"><span data-stu-id="7631d-180">To edit an existing label policy, select it, and then select **Edit Policy**.</span></span> <span data-ttu-id="7631d-181">这将启动“**创建策略**”向导，可用于编辑所包含的标签和标签设置。</span><span class="sxs-lookup"><span data-stu-id="7631d-181">This starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="7631d-182">完成向导后，所有更改都将自动复制到所选用户和服务。</span><span class="sxs-lookup"><span data-stu-id="7631d-182">When you complete the wizard, any changes are automatically replicated to the selected users and services.</span></span>

<span data-ttu-id="7631d-183">通常情况下，用户会在几个小时内查看其 Office 应用中的标签。</span><span class="sxs-lookup"><span data-stu-id="7631d-183">Typically, users see the labels in their Office apps within a couple of hours.</span></span> <span data-ttu-id="7631d-184">但是，可允许在 24 小时内将标签策略及其任何更改复制到所有用户和服务。</span><span class="sxs-lookup"><span data-stu-id="7631d-184">However, allow up to 24 hours for your label policies and any changes to them to replicate to all users and services.</span></span>

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="7631d-185">附加标签策略设置在 Office 365 安全与合规中心 PowerShell 中可用</span><span class="sxs-lookup"><span data-stu-id="7631d-185">Additional label policy settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="7631d-186">附加标签策略设置可在 “[Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)”中的“[设置标签](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps)“中使用。</span><span class="sxs-lookup"><span data-stu-id="7631d-186">Additional label policy settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="7631d-187">使用此 cmdlet，可为 Azure 信息保护统一标签客户端指定[“高级设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)”。</span><span class="sxs-lookup"><span data-stu-id="7631d-187">Using this cmdlet, you can specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="7631d-188">这些高级设置包括为 Outlook 设置不同的默认标签，并在 Outlook 中实现弹出消息，警告、两端对齐或阻止正在发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7631d-188">These advanced settings include setting a different default label for Outlook, and implement pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="7631d-189">如需完整的列表，请参阅“[可用的高级标签设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)”。</span><span class="sxs-lookup"><span data-stu-id="7631d-189">For the full list, see [Available advanced settings for labels](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels).</span></span> 

<span data-ttu-id="7631d-190">此外，还可使用此 cmdlet 在标签策略中添加和删除标签。</span><span class="sxs-lookup"><span data-stu-id="7631d-190">You can also use this cmdlet to add and remove labels to and from a label policy.</span></span>


## <a name="next-steps"></a><span data-ttu-id="7631d-191">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7631d-191">Next steps</span></span>

<span data-ttu-id="7631d-192">若要根据具体情况配置和使用敏感度标签，请使用下列文章：</span><span class="sxs-lookup"><span data-stu-id="7631d-192">To configure and use your sensitivity labels for specific scenarios, use the following articles:</span></span>

- [<span data-ttu-id="7631d-193">使用敏感度标签中的加密限制对内容的访问</span><span class="sxs-lookup"><span data-stu-id="7631d-193">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="7631d-194">将敏感度标签自动应用于内容</span><span class="sxs-lookup"><span data-stu-id="7631d-194">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="7631d-195">将灵敏度标签与团队、组和网站配合使用</span><span class="sxs-lookup"><span data-stu-id="7631d-195">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="7631d-196">启用 SharePoint 和 OneDrive 中 Office 文件的灵敏度标签</span><span class="sxs-lookup"><span data-stu-id="7631d-196">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="7631d-197">若要监视标签的使用情况，请参阅“[使用标签分析查看标签使用情况](label-analytics.md)”。</span><span class="sxs-lookup"><span data-stu-id="7631d-197">To monitor how your labels are being used, see [View label usage with label analytics](label-analytics.md).</span></span>
