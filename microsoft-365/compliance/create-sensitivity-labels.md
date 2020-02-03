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
description: 有关创建、配置和发布敏感度标签以对组织的文档和电子邮件进行分类和保护的说明。
ms.openlocfilehash: 73df1928a89218a419a9d774a7830ecad4aceb6d
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661858"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="6d5c5-103">创建和配置敏感度标签及其策略</span><span class="sxs-lookup"><span data-stu-id="6d5c5-103">Create and configure sensitivity labels and their policies</span></span>

<span data-ttu-id="6d5c5-104">若要创建并发布 [敏感度标签](sensitivity-labels.md)，请转到你的标签管理中心，如 [Microsoft 365 合规性中心](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-104">To create and publish your [sensitivity labels](sensitivity-labels.md), go to your labeling admin center, such as the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="6d5c5-105">此外，还可使用 Microsoft 365 安全中心，或 Office 365 安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-105">You can also use the Microsoft 365 security center, or the Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="6d5c5-106">首先，创建和配置你想要在 Office 应用和服务中使用的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-106">First, create and configure the sensitivity labels that you want to make available in Office apps and for services.</span></span> <span data-ttu-id="6d5c5-107">然后，创建一个或多个包含标签和你配置的策略设置的标签策略。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-107">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="6d5c5-108">这是用于发布所选用户和位置的标签和设置的标签策略。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-108">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a><span data-ttu-id="6d5c5-109">创建和管理敏感度标签所需的权限</span><span class="sxs-lookup"><span data-stu-id="6d5c5-109">Permissions required to create and manage sensitivity labels</span></span>

<span data-ttu-id="6d5c5-110">将要创建敏感度标签的合规团队成员需要 Microsoft 365 合规中心、Microsoft 365 安全中心或 Office 365 安全与合规中心的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-110">Members of your compliance team who will create sensitivity labels need permissions to the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center.</span></span> 

<span data-ttu-id="6d5c5-111">默认情况下，你的租户管理员有权访问这些管理中心，并且可以向合规专员和其他人提供访问权限，而不为其提供租户管理员的所有权限。要获得这一委派的受限管理员访问权限，请转到其中一个管理中心的“**权限**”页面，然后将成员添加到**合规性数据管理员**、**合规性管理员**或**安全管理员**角色组。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-111">By default, your tenant admin has access to these admin centers and can give compliance officers and other people access, without giving them all of the permissions of a tenant admin. For this delegated limited admin access, go to the **Permissions** page of one of these admin centers, and then add members to the **Compliance Data Administrator**, **Compliance Administrator** or **Security Administrator** role group.</span></span>

<span data-ttu-id="6d5c5-112">有关说明，请参阅[向用户授予对 Office 365 安全与合规中心的访问权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-112">For instructions, see [Give users access to the Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).</span></span>

<span data-ttu-id="6d5c5-113">只有在创建和配置灵敏度标签及其标签策略时才需要这些权限。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-113">These permissions are required only to create and configure sensitivity labels and their label policies.</span></span> <span data-ttu-id="6d5c5-114">在应用或服务中应用标这些签时不需要这些权限。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-114">They are not required to apply the labels in apps or services.</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="6d5c5-115">创建和配置敏感度标签</span><span class="sxs-lookup"><span data-stu-id="6d5c5-115">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="6d5c5-116">在标签管理中心中，导航到“灵敏度”标签：</span><span class="sxs-lookup"><span data-stu-id="6d5c5-116">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="6d5c5-117">Microsoft 365 合规中心：</span><span class="sxs-lookup"><span data-stu-id="6d5c5-117">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="6d5c5-118">**解决方案** > **信息保护**</span><span class="sxs-lookup"><span data-stu-id="6d5c5-118">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="6d5c5-119">如果看不到此选项，请先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-119">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="6d5c5-120">Microsoft 365 安全中心：</span><span class="sxs-lookup"><span data-stu-id="6d5c5-120">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="6d5c5-121">**分类** > **灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="6d5c5-121">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="6d5c5-122">Office 365 安全与合规中心：</span><span class="sxs-lookup"><span data-stu-id="6d5c5-122">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="6d5c5-123">**分类** > **灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="6d5c5-123">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="6d5c5-124">在“**标签**”选项卡上，选择“**+ 创建标签**”，以启动“**新建灵敏度标签**”向导 。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-124">On the **Labels** tab, select **+ Create a label** to start the **New sensitivity label** wizard.</span></span>

3. <span data-ttu-id="6d5c5-125">按照提示进行操作以设置标签。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-125">Follow the prompts for the label settings.</span></span>
    
    <span data-ttu-id="6d5c5-126">有关标签设置的详细信息，请参阅概述信息中的“[敏感度标签可以做什么](sensitivity-labels.md#what-sensitivity-labels-can-do)”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-126">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information.</span></span>

4. <span data-ttu-id="6d5c5-127">重复这些步骤以创建更多标签。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-127">Repeat these steps to create more labels.</span></span> <span data-ttu-id="6d5c5-128">但是，如果想要创建子标签，请先选择父标签，然后点击“**...**”并选择“**更多操作**”，然后选择“**添加子标签**”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-128">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

5. <span data-ttu-id="6d5c5-129">创建所需的所有标签后，请查看其顺序，如有必要，请向上或向下移动它们。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-129">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="6d5c5-130">若要更改标签的顺序，请选择“**...**”进行**更多操作**”，然后选择 “**上移 **”或 “**下移**”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-130">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="6d5c5-131">有关详细信息，请参阅概述信息中的“[标签优先级（顺序非常重要）](sensitivity-labels.md#label-priority-order-matters)”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-131">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="6d5c5-132">若要编辑现有标签，请将其选中，然后选择“**编辑标签**”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-132">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="6d5c5-133">这将启动“**编辑敏感度标签**”向导，可用于更改步骤 3 中的所有标签设置。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-133">This starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 3.</span></span> 

> [!NOTE]
> <span data-ttu-id="6d5c5-134">如果要编辑已使用标签策略发布的标签，则在完成该向导时不需要执行额外步骤。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-134">If you edit a label that's already published by using a label policy, no extra steps are needed when you finish the wizard.</span></span> <span data-ttu-id="6d5c5-135">例如，不需要将其添加到新的标签策略，以便对相同用户提供所做的更改。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-135">For example, you don't need to add it to a new label policy for the changes to become available to the same users.</span></span> <span data-ttu-id="6d5c5-136">但是，可允许在 24 小时内将所做的更改复制到用户和服务。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-136">However, allow up to 24 hours for the changes to replicate to users and services.</span></span>

<span data-ttu-id="6d5c5-137">发布标签之前，无法在应用程序或服务中使用。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-137">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="6d5c5-138">若要发布标签，必须将其[添加到标签策略](#publish-sensitivity-labels-by-creating-a-label-policy)。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-138">To publish the labels, they must be [added to a label policy](#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d5c5-139">在此“**标签**”选项卡上，不要选择“**发布标签**”选项卡（或在编辑标签时的“**发布标签**”按钮），除非你需要创建新的标签策略。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-139">On this **Labels** tab, do not select the **Publish labels** tab (or the **Publish label** button when you edit a label) unless you need to create a new label policy.</span></span> <span data-ttu-id="6d5c5-140">仅当用户需要不同的标签或不同的策略设置时，才需要多个标签策略。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-140">You need multiple label policies only if users need different labels or different policy settings.</span></span> <span data-ttu-id="6d5c5-141">旨在创建尽可能少的标签策略 - 组织只有一个标签策略的情况并不少见。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-141">Aim to have as few label policies as possible — it's not uncommon to have just one label policy for the organization.</span></span>

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="6d5c5-142">附加标签设置在 Office 365 安全与合规中心 PowerShell 中可用</span><span class="sxs-lookup"><span data-stu-id="6d5c5-142">Additional label settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="6d5c5-143">附加标签设置可在 “[Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)”中的“[设置标签](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps)“中使用。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-143">Additional label settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="6d5c5-144">使用 *LocaleSettings* 参数来进行跨国部署，以便用户可查看使用本地语言的标签名称和工具提示。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-144">Use the *LocaleSettings* parameter for multinational deployments so that users see the label name and tooltip in their local language.</span></span> <span data-ttu-id="6d5c5-145">有关配置示例，请参阅下面的部分。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-145">See the following section for an example configuration.</span></span> 

<span data-ttu-id="6d5c5-146">使用此 cmdlet，还可为 Azure 信息保护统一标签客户端指定[“高级设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-146">Using this cmdlet, you can also specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="6d5c5-147">这些高级设置包括应用标签时设定标签颜色，应用自定义属性。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-147">These advanced settings include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="6d5c5-148">如需完整的列表，请参阅“[可用的高级标签策略设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-148">For the full list, see [Available advanced settings for label policies](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies).</span></span> 

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a><span data-ttu-id="6d5c5-149">配置不同语言的灵敏度标签的配置示例</span><span class="sxs-lookup"><span data-stu-id="6d5c5-149">Example configuration to configure a sensitivity label for different languages</span></span>

<span data-ttu-id="6d5c5-150">下面的示例显示了名为“Public”的标签的 PowerShell 配置以及工具提示的占位符文本。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-150">The following example shows the PowerShell configuration for a label named "Public" with placeholder text for the tooltip.</span></span> <span data-ttu-id="6d5c5-151">在此示例中，将为法语、意大利语和德语配置标签名称和工具提示文本。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-151">In this example, the label name and tooltip text is configured for French, Italian, and German.</span></span>

<span data-ttu-id="6d5c5-152">进行此配置后，如果用户拥有使用这些显示语言的 Office 应用，则会看到他们的标签名称和工具提示使用相同的语言。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-152">As a result of this configuration, users who have Office apps that use those display languages see their label names and tooltips in the same language.</span></span> <span data-ttu-id="6d5c5-153">类似地，当你已安装 Azure 信息保护统一标签客户端以标记文件资源管理器中的文件时，如果用户具有这些语言版本的 Windows，则他们在使用右键单击来进行标记时将会看到其标签名称和工具提示以本地语言显示。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-153">Similarly, if you have the Azure Information Protection unified labeling client installed to label files from File Explorer, users who have those language versions of Windows see their label names and tooltips in their local language when they use the right-click actions for labeling.</span></span>

<span data-ttu-id="6d5c5-154">对于需要支持的语言，请使用 Office [语言标识符](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers)（也称为语言标记），并指定你自己的标签名称和工具提示翻译。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-154">For the languages that you need to support, use the Office [language identifiers](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (also known as language tags), and specify your own translation for the label name and tooltip.</span></span>

<span data-ttu-id="6d5c5-155">在 PowerShell 中运行命令之前，必须先[连接到 Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-155">Before you run the commands in PowerShell, you must first [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>


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

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="6d5c5-156">通过创建标签策略来发布敏感度标签</span><span class="sxs-lookup"><span data-stu-id="6d5c5-156">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="6d5c5-157">在标签管理中心中，导航到“灵敏度”标签：</span><span class="sxs-lookup"><span data-stu-id="6d5c5-157">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="6d5c5-158">Microsoft 365 合规中心：</span><span class="sxs-lookup"><span data-stu-id="6d5c5-158">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="6d5c5-159">**解决方案** > **信息保护**</span><span class="sxs-lookup"><span data-stu-id="6d5c5-159">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="6d5c5-160">如果看不到此选项，请先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-160">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="6d5c5-161">Microsoft 365 安全中心：</span><span class="sxs-lookup"><span data-stu-id="6d5c5-161">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="6d5c5-162">**分类** > **灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="6d5c5-162">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="6d5c5-163">Office 365 安全与合规中心：</span><span class="sxs-lookup"><span data-stu-id="6d5c5-163">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="6d5c5-164">**分类** > **灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="6d5c5-164">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="6d5c5-165">选择“**标签策略**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-165">Select the **Label policies** tab.</span></span>

3. <span data-ttu-id="6d5c5-166">选择“**发布标签**”以启动“**创建策略向导**”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-166">Select **Publish labels** to start the **Create policy wizard**.</span></span>

4. <span data-ttu-id="6d5c5-167">选择 “**选择要发布的敏感度标签**”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-167">Select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="6d5c5-168">选择可在应用和服务中可以使用的标签，随后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-168">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>

5. <span data-ttu-id="6d5c5-169">查看所选标签，若要进行任何更改，请选择“\*\*编辑 \*\*”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-169">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="6d5c5-170">否则选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-170">Otherwise, select **Next**.</span></span>

6. <span data-ttu-id="6d5c5-171">按照提示配置策略设置。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-171">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="6d5c5-172">有关设置的详细信息，请参阅概述信息中的“[标签策略可以做什么](sensitivity-labels.md#what-label-policies-can-do)”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-172">For more information about the settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information.</span></span>

7. <span data-ttu-id="6d5c5-173">如果不同的用户或位置需要不同的策略设置，请重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-173">Repeat these steps if you need different policy settings for different users or locations.</span></span> <span data-ttu-id="6d5c5-174">例如，希望为一组用户创建附加标签，或用户为子集创建不同的默认标签。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-174">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span>

8. <span data-ttu-id="6d5c5-175">如果创建多个可能导致用户或位置发生冲突的标签策略，请查看策略顺序，并根据需要向上或向下移动。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-175">If you create more than one label policy that might result in a conflict for a user or location, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="6d5c5-176">若要更改标签策略的顺序，请选择“**...**”进行**更多操作**”，然后选择 “**上移 **”或 “**下移**”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-176">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="6d5c5-177">有关详细信息，请参阅概述信息中的“[标签策略优先级（顺序非常重要）](sensitivity-labels.md#label-policy-priority-order-matters)”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-177">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="6d5c5-178">完成向导会自动发布标签策略。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-178">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="6d5c5-179">若要更改已发布的策略，只需对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-179">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="6d5c5-180">没有特定发布或重新发布操作可供选择。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-180">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="6d5c5-181">若要编辑现有标签策略，请将其选中，然后选择“**编辑策略**”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-181">To edit an existing label policy, select it, and then select **Edit Policy**.</span></span> <span data-ttu-id="6d5c5-182">这将启动“**创建策略**”向导，可用于编辑所包含的标签和标签设置。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-182">This starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="6d5c5-183">完成向导后，所有更改都将自动复制到所选用户和服务。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-183">When you complete the wizard, any changes are automatically replicated to the selected users and services.</span></span>

<span data-ttu-id="6d5c5-184">通常情况下，用户会在几个小时内查看其 Office 应用中的标签。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-184">Typically, users see the labels in their Office apps within a couple of hours.</span></span> <span data-ttu-id="6d5c5-185">但是，可允许在 24 小时内将标签策略及其任何更改复制到所有用户和服务。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-185">However, allow up to 24 hours for your label policies and any changes to them to replicate to all users and services.</span></span>

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="6d5c5-186">附加标签策略设置在 Office 365 安全与合规中心 PowerShell 中可用</span><span class="sxs-lookup"><span data-stu-id="6d5c5-186">Additional label policy settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="6d5c5-187">附加标签策略设置可在 “[Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)”中的“[设置标签](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps)“中使用。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-187">Additional label policy settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="6d5c5-188">使用此 cmdlet，可为 Azure 信息保护统一标签客户端指定[“高级设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-188">Using this cmdlet, you can specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="6d5c5-189">这些高级设置包括为 Outlook 设置不同的默认标签，并在 Outlook 中实现弹出消息，警告、两端对齐或阻止正在发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-189">These advanced settings include setting a different default label for Outlook, and implement pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="6d5c5-190">如需完整的列表，请参阅“[可用的高级标签设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-190">For the full list, see [Available advanced settings for labels](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels).</span></span> 

<span data-ttu-id="6d5c5-191">此外，还可使用此 cmdlet 在标签策略中添加和删除标签。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-191">You can also use this cmdlet to add and remove labels to and from a label policy.</span></span>


## <a name="next-steps"></a><span data-ttu-id="6d5c5-192">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6d5c5-192">Next steps</span></span>

<span data-ttu-id="6d5c5-193">若要根据具体情况配置和使用敏感度标签，请使用下列文章：</span><span class="sxs-lookup"><span data-stu-id="6d5c5-193">To configure and use your sensitivity labels for specific scenarios, use the following articles:</span></span>

- [<span data-ttu-id="6d5c5-194">使用敏感度标签中的加密限制对内容的访问</span><span class="sxs-lookup"><span data-stu-id="6d5c5-194">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="6d5c5-195">将敏感度标签自动应用于内容</span><span class="sxs-lookup"><span data-stu-id="6d5c5-195">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="6d5c5-196">将灵敏度标签与团队、组和网站配合使用</span><span class="sxs-lookup"><span data-stu-id="6d5c5-196">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="6d5c5-197">启用 SharePoint 和 OneDrive 中 Office 文件的灵敏度标签</span><span class="sxs-lookup"><span data-stu-id="6d5c5-197">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="6d5c5-198">若要监视标签的使用情况，请参阅“[使用标签分析查看标签使用情况](label-analytics.md)”。</span><span class="sxs-lookup"><span data-stu-id="6d5c5-198">To monitor how your labels are being used, see [View label usage with label analytics](label-analytics.md).</span></span>