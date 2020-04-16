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
ms.openlocfilehash: 196efe65eda1265d6f2c0578d1f444709dadb26c
ms.sourcegitcommit: d767c288ae34431fb046f4cfe36cec485881385f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2020
ms.locfileid: "43516817"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="71724-103">创建和配置敏感度标签及其策略</span><span class="sxs-lookup"><span data-stu-id="71724-103">Create and configure sensitivity labels and their policies</span></span>

><span data-ttu-id="71724-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="71724-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="71724-105">所有 Microsoft 信息保护解决方案（有时缩写为 MIP）通过使用 [敏感度标签](sensitivity-labels.md)实现。</span><span class="sxs-lookup"><span data-stu-id="71724-105">All Microsoft Information Protection solutions (sometimes abbreviated to MIP) are implemented by using [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="71724-106">要创建并发布这些标签，请转到标签管理中心，例如 [Microsoft 365 合规中心](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="71724-106">To create and publish these labels, go to your labeling admin center, such as the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="71724-107">此外，还可使用 Microsoft 365 安全中心或 Office 365 安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="71724-107">You can also use the Microsoft 365 security center, or the Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="71724-108">首先，创建和配置要在应用和其他服务中使用的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="71724-108">First, create and configure the sensitivity labels that you want to make available for apps and other services.</span></span> <span data-ttu-id="71724-109">例如，希望用户在 Office 应用中看到和采用的标签。</span><span class="sxs-lookup"><span data-stu-id="71724-109">For example, the labels you want users to see and apply from Office apps.</span></span> 

<span data-ttu-id="71724-110">然后，创建一个或多个包含标签和你配置的策略设置的标签策略。</span><span class="sxs-lookup"><span data-stu-id="71724-110">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="71724-111">这是用于发布所选用户和位置的标签和设置的标签策略。</span><span class="sxs-lookup"><span data-stu-id="71724-111">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="71724-112">准备工作</span><span class="sxs-lookup"><span data-stu-id="71724-112">Before you begin</span></span>

<span data-ttu-id="71724-113">组织的全局管理员具有创建和管理敏感度标签各方面的完全权限。</span><span class="sxs-lookup"><span data-stu-id="71724-113">The global admin for your organization has full permissions to create and manage all aspects of sensitivity labels.</span></span> <span data-ttu-id="71724-114">如果你未以全局管理员的身份登录，请参阅[创建和管理敏感度标签所需的权限](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="71724-114">If you aren't signing in as a global admin, see [Permissions required to create and manage sensitivity labels](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="71724-115">创建和配置敏感度标签</span><span class="sxs-lookup"><span data-stu-id="71724-115">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="71724-116">在标签管理中心中，导航到“灵敏度”标签：</span><span class="sxs-lookup"><span data-stu-id="71724-116">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="71724-117">Microsoft 365 合规中心：</span><span class="sxs-lookup"><span data-stu-id="71724-117">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="71724-118">**解决方案** > **信息保护**</span><span class="sxs-lookup"><span data-stu-id="71724-118">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="71724-119">如果看不到此选项，请先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="71724-119">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="71724-120">Microsoft 365 安全中心：</span><span class="sxs-lookup"><span data-stu-id="71724-120">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="71724-121">**分类** > **灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="71724-121">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="71724-122">Office 365 安全与合规中心：</span><span class="sxs-lookup"><span data-stu-id="71724-122">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="71724-123">**分类** > **灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="71724-123">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="71724-124">在“**标签**”选项卡上，选择“**+ 创建标签**”，以启动“**新建灵敏度标签**”向导 。</span><span class="sxs-lookup"><span data-stu-id="71724-124">On the **Labels** tab, select **+ Create a label** to start the **New sensitivity label** wizard.</span></span>

3. <span data-ttu-id="71724-125">按照提示进行操作以设置标签。</span><span class="sxs-lookup"><span data-stu-id="71724-125">Follow the prompts for the label settings.</span></span>
    
    <span data-ttu-id="71724-126">有关标签设置的详细信息，请参阅概述信息中的“[敏感度标签可以做什么](sensitivity-labels.md#what-sensitivity-labels-can-do)”。</span><span class="sxs-lookup"><span data-stu-id="71724-126">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information.</span></span>

4. <span data-ttu-id="71724-127">重复这些步骤以创建更多标签。</span><span class="sxs-lookup"><span data-stu-id="71724-127">Repeat these steps to create more labels.</span></span> <span data-ttu-id="71724-128">但是，如果想要创建子标签，请先选择父标签，然后点击“**...**”并选择“**更多操作**”，然后选择“**添加子标签**”。</span><span class="sxs-lookup"><span data-stu-id="71724-128">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

5. <span data-ttu-id="71724-129">创建所需的所有标签后，请查看其顺序，如有必要，请向上或向下移动它们。</span><span class="sxs-lookup"><span data-stu-id="71724-129">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="71724-130">若要更改标签的顺序，请选择“**...**”进行**更多操作**”，然后选择 “**上移 **”或 “**下移**”。</span><span class="sxs-lookup"><span data-stu-id="71724-130">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="71724-131">有关详细信息，请参阅概述信息中的“[标签优先级（顺序非常重要）](sensitivity-labels.md#label-priority-order-matters)”。</span><span class="sxs-lookup"><span data-stu-id="71724-131">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="71724-132">若要编辑现有标签，请将其选中，然后选择“**编辑标签**”。</span><span class="sxs-lookup"><span data-stu-id="71724-132">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="71724-133">这将启动“**编辑敏感度标签**”向导，可用于更改步骤 3 中的所有标签设置。</span><span class="sxs-lookup"><span data-stu-id="71724-133">This starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 3.</span></span> 

> [!NOTE]
> <span data-ttu-id="71724-134">如果要编辑已使用标签策略发布的标签，则在完成该向导时不需要执行额外步骤。</span><span class="sxs-lookup"><span data-stu-id="71724-134">If you edit a label that's already published by using a label policy, no extra steps are needed when you finish the wizard.</span></span> <span data-ttu-id="71724-135">例如，不需要将其添加到新的标签策略，即可对相同用户提供所做的更改。</span><span class="sxs-lookup"><span data-stu-id="71724-135">For example, you don't need to add it to a new label policy for the changes to become available to the same users.</span></span> <span data-ttu-id="71724-136">但是，可允许在 24 小时内将所做的更改复制到用户和服务。</span><span class="sxs-lookup"><span data-stu-id="71724-136">However, allow up to 24 hours for the changes to replicate to users and services.</span></span>

<span data-ttu-id="71724-137">发布标签之前，无法在应用程序或服务中使用。</span><span class="sxs-lookup"><span data-stu-id="71724-137">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="71724-138">若要发布标签，必须将其[添加到标签策略](#publish-sensitivity-labels-by-creating-a-label-policy)。</span><span class="sxs-lookup"><span data-stu-id="71724-138">To publish the labels, they must be [added to a label policy](#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71724-139">在此“**标签**”选项卡上，不要选择“**发布标签**”选项卡（或在编辑标签时的“**发布标签**”按钮），除非你需要创建新的标签策略。</span><span class="sxs-lookup"><span data-stu-id="71724-139">On this **Labels** tab, do not select the **Publish labels** tab (or the **Publish label** button when you edit a label) unless you need to create a new label policy.</span></span> <span data-ttu-id="71724-140">仅当用户需要不同的标签或不同的策略设置时，才需要多个标签策略。</span><span class="sxs-lookup"><span data-stu-id="71724-140">You need multiple label policies only if users need different labels or different policy settings.</span></span> <span data-ttu-id="71724-141">旨在创建尽可能少的标签策略 - 组织只有一个标签策略的情况并不少见。</span><span class="sxs-lookup"><span data-stu-id="71724-141">Aim to have as few label policies as possible — it's not uncommon to have just one label policy for the organization.</span></span>

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="71724-142">附加标签设置在 Office 365 安全与合规中心 PowerShell 中可用</span><span class="sxs-lookup"><span data-stu-id="71724-142">Additional label settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="71724-143">附加标签设置可在 “[Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)”中的“[设置标签](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps)“中使用。</span><span class="sxs-lookup"><span data-stu-id="71724-143">Additional label settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="71724-144">使用 *LocaleSettings* 参数来进行跨国部署，以便用户可查看使用本地语言的标签名称和工具提示。</span><span class="sxs-lookup"><span data-stu-id="71724-144">Use the *LocaleSettings* parameter for multinational deployments so that users see the label name and tooltip in their local language.</span></span> <span data-ttu-id="71724-145">有关配置示例，请参阅下面的部分。</span><span class="sxs-lookup"><span data-stu-id="71724-145">See the following section for an example configuration.</span></span> 

<span data-ttu-id="71724-146">使用此 cmdlet，还可为 Azure 信息保护统一标签客户端指定[“高级设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)”。</span><span class="sxs-lookup"><span data-stu-id="71724-146">Using this cmdlet, you can also specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="71724-147">这些高级设置包括应用标签时设定标签颜色，应用自定义属性。</span><span class="sxs-lookup"><span data-stu-id="71724-147">These advanced settings include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="71724-148">如需完整的列表，请参阅“[可用的高级标签策略设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)”。</span><span class="sxs-lookup"><span data-stu-id="71724-148">For the full list, see [Available advanced settings for label policies](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies).</span></span> 

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a><span data-ttu-id="71724-149">配置不同语言的灵敏度标签的配置示例</span><span class="sxs-lookup"><span data-stu-id="71724-149">Example configuration to configure a sensitivity label for different languages</span></span>

<span data-ttu-id="71724-150">下面的示例显示了名为“Public”的标签的 PowerShell 配置以及工具提示的占位符文本。</span><span class="sxs-lookup"><span data-stu-id="71724-150">The following example shows the PowerShell configuration for a label named "Public" with placeholder text for the tooltip.</span></span> <span data-ttu-id="71724-151">在此示例中，将为法语、意大利语和德语配置标签名称和工具提示文本。</span><span class="sxs-lookup"><span data-stu-id="71724-151">In this example, the label name and tooltip text is configured for French, Italian, and German.</span></span>

<span data-ttu-id="71724-152">进行此配置后，如果用户拥有使用这些显示语言的 Office 应用，则会看到他们的标签名称和工具提示使用相同的语言。</span><span class="sxs-lookup"><span data-stu-id="71724-152">As a result of this configuration, users who have Office apps that use those display languages see their label names and tooltips in the same language.</span></span> <span data-ttu-id="71724-153">类似地，当你已安装 Azure 信息保护统一标签客户端以标记文件资源管理器中的文件时，如果用户具有这些语言版本的 Windows，则他们在使用右键单击来进行标记时将会看到其标签名称和工具提示以本地语言显示。</span><span class="sxs-lookup"><span data-stu-id="71724-153">Similarly, if you have the Azure Information Protection unified labeling client installed to label files from File Explorer, users who have those language versions of Windows see their label names and tooltips in their local language when they use the right-click actions for labeling.</span></span>

<span data-ttu-id="71724-154">对于需要支持的语言，请使用 Office [语言标识符](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers)（也称为语言标记），并指定你自己的标签名称和工具提示翻译。</span><span class="sxs-lookup"><span data-stu-id="71724-154">For the languages that you need to support, use the Office [language identifiers](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (also known as language tags), and specify your own translation for the label name and tooltip.</span></span>

<span data-ttu-id="71724-155">在 PowerShell 中运行命令之前，必须先[连接到 Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="71724-155">Before you run the commands in PowerShell, you must first [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>


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

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="71724-156">通过创建标签策略来发布敏感度标签</span><span class="sxs-lookup"><span data-stu-id="71724-156">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="71724-157">在标签管理中心中，导航到“灵敏度”标签：</span><span class="sxs-lookup"><span data-stu-id="71724-157">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="71724-158">Microsoft 365 合规中心：</span><span class="sxs-lookup"><span data-stu-id="71724-158">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="71724-159">**解决方案** > **信息保护**</span><span class="sxs-lookup"><span data-stu-id="71724-159">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="71724-160">如果看不到此选项，请先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="71724-160">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="71724-161">Microsoft 365 安全中心：</span><span class="sxs-lookup"><span data-stu-id="71724-161">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="71724-162">**分类** > **灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="71724-162">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="71724-163">Office 365 安全与合规中心：</span><span class="sxs-lookup"><span data-stu-id="71724-163">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="71724-164">**分类** > **灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="71724-164">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="71724-165">选择“**标签策略**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="71724-165">Select the **Label policies** tab.</span></span>

3. <span data-ttu-id="71724-166">选择“**发布标签**”以启动“**创建策略向导**”。</span><span class="sxs-lookup"><span data-stu-id="71724-166">Select **Publish labels** to start the **Create policy wizard**.</span></span>

4. <span data-ttu-id="71724-167">选择 “**选择要发布的敏感度标签**”。</span><span class="sxs-lookup"><span data-stu-id="71724-167">Select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="71724-168">选择可在应用和服务中可以使用的标签，随后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="71724-168">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>
    
    <span data-ttu-id="71724-169">如果选择子标签，请确保也选择其父标签。</span><span class="sxs-lookup"><span data-stu-id="71724-169">If you select a sublabel, make sure you also select its parent label.</span></span>
    
5. <span data-ttu-id="71724-170">查看所选标签，若要进行任何更改，请选择“\*\*编辑 \*\*”。</span><span class="sxs-lookup"><span data-stu-id="71724-170">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="71724-171">否则选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="71724-171">Otherwise, select **Next**.</span></span>

6. <span data-ttu-id="71724-172">按照提示配置策略设置。</span><span class="sxs-lookup"><span data-stu-id="71724-172">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="71724-173">有关设置的详细信息，请参阅概述信息中的“[标签策略可以做什么](sensitivity-labels.md#what-label-policies-can-do)”。</span><span class="sxs-lookup"><span data-stu-id="71724-173">For more information about the settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information.</span></span>

7. <span data-ttu-id="71724-174">如果不同的用户或位置需要不同的策略设置，请重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="71724-174">Repeat these steps if you need different policy settings for different users or locations.</span></span> <span data-ttu-id="71724-175">例如，希望为一组用户创建附加标签，或用户为子集创建不同的默认标签。</span><span class="sxs-lookup"><span data-stu-id="71724-175">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span>

8. <span data-ttu-id="71724-176">如果创建多个可能导致用户或位置发生冲突的标签策略，请查看策略顺序，并根据需要向上或向下移动。</span><span class="sxs-lookup"><span data-stu-id="71724-176">If you create more than one label policy that might result in a conflict for a user or location, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="71724-177">若要更改标签策略的顺序，请选择“**...**”进行**更多操作**”，然后选择 “**上移 **”或 “**下移**”。</span><span class="sxs-lookup"><span data-stu-id="71724-177">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="71724-178">有关详细信息，请参阅概述信息中的“[标签策略优先级（顺序非常重要）](sensitivity-labels.md#label-policy-priority-order-matters)”。</span><span class="sxs-lookup"><span data-stu-id="71724-178">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="71724-179">完成向导会自动发布标签策略。</span><span class="sxs-lookup"><span data-stu-id="71724-179">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="71724-180">若要更改已发布的策略，只需对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="71724-180">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="71724-181">没有特定发布或重新发布操作可供选择。</span><span class="sxs-lookup"><span data-stu-id="71724-181">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="71724-182">若要编辑现有标签策略，请将其选中，然后选择“**编辑策略**”。</span><span class="sxs-lookup"><span data-stu-id="71724-182">To edit an existing label policy, select it, and then select **Edit Policy**.</span></span> <span data-ttu-id="71724-183">这将启动“**创建策略**”向导，可用于编辑所包含的标签和标签设置。</span><span class="sxs-lookup"><span data-stu-id="71724-183">This starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="71724-184">完成向导后，所有更改都将自动复制到所选用户和服务。</span><span class="sxs-lookup"><span data-stu-id="71724-184">When you complete the wizard, any changes are automatically replicated to the selected users and services.</span></span>

<span data-ttu-id="71724-185">通常情况下，用户会在几个小时内查看其 Office 应用中的标签。</span><span class="sxs-lookup"><span data-stu-id="71724-185">Typically, users see the labels in their Office apps within a couple of hours.</span></span> <span data-ttu-id="71724-186">但是，可允许在 24 小时内将标签策略及其任何更改复制到所有用户和服务。</span><span class="sxs-lookup"><span data-stu-id="71724-186">However, allow up to 24 hours for your label policies and any changes to them to replicate to all users and services.</span></span>

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="71724-187">附加标签策略设置在 Office 365 安全与合规中心 PowerShell 中可用</span><span class="sxs-lookup"><span data-stu-id="71724-187">Additional label policy settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="71724-188">附加标签策略设置可在 “[Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)”中的“[设置标签](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps)“中使用。</span><span class="sxs-lookup"><span data-stu-id="71724-188">Additional label policy settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="71724-189">使用此 cmdlet，可为 Azure 信息保护统一标签客户端指定[“高级设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)”。</span><span class="sxs-lookup"><span data-stu-id="71724-189">Using this cmdlet, you can specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="71724-190">这些高级设置包括为 Outlook 设置不同的默认标签，并在 Outlook 中实现弹出消息，警告、两端对齐或阻止正在发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="71724-190">These advanced settings include setting a different default label for Outlook, and implement pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="71724-191">如需完整的列表，请参阅“[可用的高级标签设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)”。</span><span class="sxs-lookup"><span data-stu-id="71724-191">For the full list, see [Available advanced settings for labels](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels).</span></span> 

<span data-ttu-id="71724-192">此外，还可使用此 cmdlet 在标签策略中添加和删除标签。</span><span class="sxs-lookup"><span data-stu-id="71724-192">You can also use this cmdlet to add and remove labels to and from a label policy.</span></span>

## <a name="removing-and-deleting-labels"></a><span data-ttu-id="71724-193">移除和删除标签</span><span class="sxs-lookup"><span data-stu-id="71724-193">Removing and deleting labels</span></span>

<span data-ttu-id="71724-194">在生产环境中，不太可能需要从标签策略中移除敏感度标签，也不太可能需要删除敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="71724-194">In a production environment, it's unlikely that you will need to remove sensitivity labels from a label policy, or delete sensitivity labels.</span></span> <span data-ttu-id="71724-195">更有可能是在初始测试阶段需要执行这两项操作之一。</span><span class="sxs-lookup"><span data-stu-id="71724-195">It's more likely that you might need to do one or either of these actions during an initial testing phase.</span></span> <span data-ttu-id="71724-196">请务必了解执行这两项操作之一时所发生的情况。</span><span class="sxs-lookup"><span data-stu-id="71724-196">Make sure you understand what happens when you do either of these actions.</span></span>

<span data-ttu-id="71724-197">从标签策略中移除标签比删除标签的风险要小；如果需要，稍后始终可以将标签添加回标签策略中：</span><span class="sxs-lookup"><span data-stu-id="71724-197">Removing a label from a label policy is less risky than deleting it, and you can always add it back to a label policy later if needed:</span></span>

- <span data-ttu-id="71724-198">如果从标签策略中移除标签，让标签不再发布给最初指定的用户，那么当标签策略下次刷新时，标签就不再可供这些用户在 Office 应用程序中选择。</span><span class="sxs-lookup"><span data-stu-id="71724-198">When you remove a label from a label policy so that the label is no longer published to the originally specified users, the next time the label policy is refreshed, users no longer see that label to select in their Office app.</span></span> <span data-ttu-id="71724-199">不过，如果已将标签应用于文档或电子邮件，那么标签不会从此类内容中移除。</span><span class="sxs-lookup"><span data-stu-id="71724-199">However, if the label has been applied to documents or emails, the label isn't removed from that content.</span></span> <span data-ttu-id="71724-200">由标签应用的任何加密都会保留，且基础保护模板也会保持已发布状态不变。</span><span class="sxs-lookup"><span data-stu-id="71724-200">Any encryption that was applied by the label remains and the underlying protection template remains published.</span></span> 

- <span data-ttu-id="71724-201">对于已移除但以前应用于内容的标签，在 Word、Excel 和 PowerPoint 中使用内置标签的用户仍会在状态栏中看到已应用标签名称。</span><span class="sxs-lookup"><span data-stu-id="71724-201">For labels that are removed but have previously been applied to content, users who are using built-in labeling for Word, Excel, and PowerPoint, still see the applied label name on the status bar.</span></span> <span data-ttu-id="71724-202">同样，已移除但以前应用于 SharePoint 网站的标签仍会在“敏感度”\*\*\*\* 列中显示标签名称。</span><span class="sxs-lookup"><span data-stu-id="71724-202">Similarly, labels that are removed that were applied to SharePoint sites still display the label name in the **Sensitivity** column.</span></span>

<span data-ttu-id="71724-203">相比之下，如果删除标签：</span><span class="sxs-lookup"><span data-stu-id="71724-203">In comparison, when you delete a label:</span></span>

- <span data-ttu-id="71724-204">如果标签应用了加密，则会存档基础保护模板，这样以前受保护的内容就仍能打开。</span><span class="sxs-lookup"><span data-stu-id="71724-204">If the label applied encryption, the underlying protection template is archived so that previously protected content can still be opened.</span></span> <span data-ttu-id="71724-205">因为有此已存档保护模板，所以无法创建同名的新标签。</span><span class="sxs-lookup"><span data-stu-id="71724-205">Because of this archived protection template, you won't be able to create a new label with the same name.</span></span> <span data-ttu-id="71724-206">虽然可以使用 [PowerShell](https://docs.microsoft.com/powershell/module/aipservice/remove-aipservicetemplate) 删除保护模板，但请不要这样做，除非你确定无需打开使用已存档模板加密的内容。</span><span class="sxs-lookup"><span data-stu-id="71724-206">Although it's possible to delete a protection template by using [PowerShell](https://docs.microsoft.com/powershell/module/aipservice/remove-aipservicetemplate), don't do this unless you're sure you don't need to open content that was encrypted with the archived template.</span></span>

- <span data-ttu-id="71724-207">对于桌面应用程序：元数据中的标签信息会保留，但由于无法再进行标签 ID 到名称的映射，导致用户看不到显示的已应用标签名称（例如，在状态栏中），因此用户会假定内容未标记。</span><span class="sxs-lookup"><span data-stu-id="71724-207">For desktop apps: The label information in the metadata remains, but because a label ID to name mapping is no longer possible, users don't see the applied label name displayed (for example, on the status bar) so users will assume the content isn't labeled.</span></span> <span data-ttu-id="71724-208">如果标签应用了加密，则会保留加密，且用户仍会在内容打开时看到当前已存档保护模板的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="71724-208">If the label applied encryption, the encryption remains and when the content is opened, uses still see the name and description of the now archived protection template.</span></span>

- <span data-ttu-id="71724-209">对于 Office 网页版：用户在状态栏或“敏感度”\*\*\*\* 列中看不到标签名称。</span><span class="sxs-lookup"><span data-stu-id="71724-209">For Office on the web: Users don't see the label name on status bar or in the **Sensitivity** column.</span></span> <span data-ttu-id="71724-210">元数据中的标签信息仅在标签未应用加密的情况下保留。</span><span class="sxs-lookup"><span data-stu-id="71724-210">The label information in the metadata remains only if the label didn't apply encryption.</span></span> <span data-ttu-id="71724-211">如果标签应用了加密，且你已[为 SharePoint 和 Onedrive 启用敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)，那么元数据中的标签信息就会遭移除，且加密也会遭撤消。</span><span class="sxs-lookup"><span data-stu-id="71724-211">If the label applied encryption, and you've enabled [sensitivity labels for SharePoint and Onedrive](sensitivity-labels-sharepoint-onedrive-files.md), the label information in the metadata is removed and the encryption is removed.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="71724-212">后续步骤</span><span class="sxs-lookup"><span data-stu-id="71724-212">Next steps</span></span>

<span data-ttu-id="71724-213">若要根据具体情况配置和使用敏感度标签，请使用下列文章：</span><span class="sxs-lookup"><span data-stu-id="71724-213">To configure and use your sensitivity labels for specific scenarios, use the following articles:</span></span>

- [<span data-ttu-id="71724-214">使用敏感度标签中的加密限制对内容的访问</span><span class="sxs-lookup"><span data-stu-id="71724-214">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="71724-215">将敏感度标签自动应用于内容</span><span class="sxs-lookup"><span data-stu-id="71724-215">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="71724-216">将灵敏度标签与团队、组和网站配合使用</span><span class="sxs-lookup"><span data-stu-id="71724-216">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="71724-217">启用 SharePoint 和 OneDrive 中 Office 文件的灵敏度标签</span><span class="sxs-lookup"><span data-stu-id="71724-217">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="71724-218">若要监视标签的使用情况，请参阅“[使用标签分析查看标签使用情况](label-analytics.md)”。</span><span class="sxs-lookup"><span data-stu-id="71724-218">To monitor how your labels are being used, see [View label usage with label analytics](label-analytics.md).</span></span>
