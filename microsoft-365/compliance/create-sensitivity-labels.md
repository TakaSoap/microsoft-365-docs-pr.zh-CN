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
description: 所有 Microsoft 信息保护解决方案的相关要求：创建、配置和发布敏感度标签以对组织的数据进行分类和保护。
ms.openlocfilehash: c34025d2b68eb0ee179c98ce9c97a59193f782e3
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994949"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="438ce-103">创建和配置敏感度标签及其策略</span><span class="sxs-lookup"><span data-stu-id="438ce-103">Create and configure sensitivity labels and their policies</span></span>

><span data-ttu-id="438ce-104">*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="438ce-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="438ce-105">所有 Microsoft 信息保护解决方案（有时缩写为 MIP）通过使用 [敏感度标签](sensitivity-labels.md)实现。</span><span class="sxs-lookup"><span data-stu-id="438ce-105">All Microsoft Information Protection solutions (sometimes abbreviated to MIP) are implemented by using [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="438ce-106">要创建并发布这些标签，请转到[Microsoft 365 合规中心](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="438ce-106">To create and publish these labels, go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="438ce-107">还可以使用旧门户 Office 365 安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="438ce-107">You can also use the older portal, Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="438ce-108">首先，创建和配置要在应用和其他服务中使用的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="438ce-108">First, create and configure the sensitivity labels that you want to make available for apps and other services.</span></span> <span data-ttu-id="438ce-109">例如，希望用户在 Office 应用中看到和采用的标签。</span><span class="sxs-lookup"><span data-stu-id="438ce-109">For example, the labels you want users to see and apply from Office apps.</span></span> 

<span data-ttu-id="438ce-110">然后，创建一个或多个包含标签和你配置的策略设置的标签策略。</span><span class="sxs-lookup"><span data-stu-id="438ce-110">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="438ce-111">这是用于发布所选用户和位置的标签和设置的标签策略。</span><span class="sxs-lookup"><span data-stu-id="438ce-111">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="438ce-112">准备工作</span><span class="sxs-lookup"><span data-stu-id="438ce-112">Before you begin</span></span>

<span data-ttu-id="438ce-113">组织的全局管理员具有创建和管理敏感度标签各方面的完全权限。</span><span class="sxs-lookup"><span data-stu-id="438ce-113">The global admin for your organization has full permissions to create and manage all aspects of sensitivity labels.</span></span> <span data-ttu-id="438ce-114">如果你未以全局管理员的身份登录，请参阅[创建和管理敏感度标签所需的权限](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="438ce-114">If you aren't signing in as a global admin, see [Permissions required to create and manage sensitivity labels](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="438ce-115">创建和配置敏感度标签</span><span class="sxs-lookup"><span data-stu-id="438ce-115">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="438ce-116">在标签管理中心中，导航到“灵敏度”标签：</span><span class="sxs-lookup"><span data-stu-id="438ce-116">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="438ce-117">Microsoft 365 合规中心：</span><span class="sxs-lookup"><span data-stu-id="438ce-117">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="438ce-118">**解决方案** > **信息保护**</span><span class="sxs-lookup"><span data-stu-id="438ce-118">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="438ce-119">如果看不到此选项，请先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="438ce-119">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="438ce-120">安全与合规中心：</span><span class="sxs-lookup"><span data-stu-id="438ce-120">Security & Compliance Center:</span></span>
        - <span data-ttu-id="438ce-121">**分类** > **灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="438ce-121">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="438ce-122">在“**标签**”页面，选择“**+ 创建标签**”，以启动“新建灵敏度标签”向导。</span><span class="sxs-lookup"><span data-stu-id="438ce-122">On the **Labels** page, select **+ Create a label** to start the New sensitivity label wizard.</span></span> 
    
    <span data-ttu-id="438ce-123">例如，从 Microsoft 365 合规中心：</span><span class="sxs-lookup"><span data-stu-id="438ce-123">For example, from the Microsoft 365 compliance center:</span></span>
    
    ![创建敏感度标签](../media/create-sensitivity-label-full.png)
    
    > [!NOTE]
    > <span data-ttu-id="438ce-125">默认情况下，租户没有任何标签，并且必须由你创建。</span><span class="sxs-lookup"><span data-stu-id="438ce-125">By default, tenants don't have any labels and you must create them.</span></span> <span data-ttu-id="438ce-126">示例图片中的标签显示 [从 Azure 信息保护迁移](/azure/information-protection/configure-policy-migrate-labels)的默认标签。</span><span class="sxs-lookup"><span data-stu-id="438ce-126">The labels in the example picture show default labels that were [migrated from Azure Information Protection](/azure/information-protection/configure-policy-migrate-labels).</span></span>

3. <span data-ttu-id="438ce-127">在 **定义此标签的范围** 页面上，选择的选项将确定可以配置的设置的标签范围以及它们发布后的可见位置：</span><span class="sxs-lookup"><span data-stu-id="438ce-127">On the **Define the scope for this label** page, the options selected determine the label's scope for the settings that you can configure and where they will be visible when they are published:</span></span>
    
    ![敏感度标签的范围](../media/sensitivity-labels-scopes.png)
    
    - <span data-ttu-id="438ce-129">如果已选中 **“文件和 电子邮件”**，则可以在此向导中配置适用于支持敏感度标签的应用（如 Office Word 和 Outlook）的设置。</span><span class="sxs-lookup"><span data-stu-id="438ce-129">If **Files & emails** is selected, you can configure settings in this wizard that apply to apps that support sensitivity labels, such as Office Word and Outlook.</span></span> <span data-ttu-id="438ce-130">如果未选择此选项，向导将显示这些设置的第一页，但无法进行配置，用户无法在这些应用中选择标签。</span><span class="sxs-lookup"><span data-stu-id="438ce-130">If this option isn't selected, the wizard displays the first page of these settings but you can't configure them and the labels won't be available for users to select in these apps.</span></span>
    
    - <span data-ttu-id="438ce-131">如果已选中 **“组合网站”** ，则可以在此向导中配置适用于 Microsoft 365 组和网站（Teams 和 SharePoint）的设置。</span><span class="sxs-lookup"><span data-stu-id="438ce-131">If **Groups & sites** is selected, you can configure settings in this wizard that apply to Microsoft 365 groups, and sites for Teams and SharePoint.</span></span> <span data-ttu-id="438ce-132">如果未选择此选项，向导将显示这些设置的第一页，但无法进行配置，用户无法在组合网站中选择标签。</span><span class="sxs-lookup"><span data-stu-id="438ce-132">If this option isn't selected, the wizard displays the first page of these settings but you can't configure them and the labels won't be available for users to select for groups and site.</span></span>
    
    <span data-ttu-id="438ce-133">有关 **Azure Purview 素材（预览版）** 范围的详细信息，请参阅 [在 Azure Purview 中自动标记内容](/azure/purview/create-sensitivity-label)。</span><span class="sxs-lookup"><span data-stu-id="438ce-133">For information about the **Azure Purview assets (preview)** scope, see [Automatically label your content in Azure Purview](/azure/purview/create-sensitivity-label).</span></span>

4. <span data-ttu-id="438ce-134">在向导中按照提示进行标签设置。</span><span class="sxs-lookup"><span data-stu-id="438ce-134">Follow the prompts in the wizard for the label settings.</span></span>
    
    <span data-ttu-id="438ce-135">有关标签设置的详细信息，请参阅概述信息中的“[敏感度标签有何用途](sensitivity-labels.md#what-sensitivity-labels-can-do)”并使用向导中针对单个设置的帮助。</span><span class="sxs-lookup"><span data-stu-id="438ce-135">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information and use the help in the wizard for individual settings.</span></span>

5. <span data-ttu-id="438ce-136">重复这些步骤以创建更多标签。</span><span class="sxs-lookup"><span data-stu-id="438ce-136">Repeat these steps to create more labels.</span></span> <span data-ttu-id="438ce-137">但是，如果想要创建子标签，请先选择父标签，然后点击“**...**”并选择“**更多操作**”，然后选择“**添加子标签**”。</span><span class="sxs-lookup"><span data-stu-id="438ce-137">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

6. <span data-ttu-id="438ce-138">创建所需的所有标签后，请查看其顺序，如有必要，请向上或向下移动它们。</span><span class="sxs-lookup"><span data-stu-id="438ce-138">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="438ce-139">若要更改标签的顺序，请选择“**...**”进行 **更多操作**”，然后选择 “**上移**”或 “**下移**”。</span><span class="sxs-lookup"><span data-stu-id="438ce-139">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="438ce-140">有关详细信息，请参阅概述信息中的“[标签优先级（顺序非常重要）](sensitivity-labels.md#label-priority-order-matters)”。</span><span class="sxs-lookup"><span data-stu-id="438ce-140">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="438ce-141">若要编辑现有标签，请将其选中，然后选择“**编辑标签**”按钮：</span><span class="sxs-lookup"><span data-stu-id="438ce-141">To edit an existing label, select it, and then select the **Edit label** button:</span></span>

![编辑标签按钮以便编辑敏感度标签](../media/edit-sensitivity-label-full.png)

<span data-ttu-id="438ce-143">此按钮将启动“**编辑敏感度标签**”向导，可用于更改步骤 4 中的所有标签设置。</span><span class="sxs-lookup"><span data-stu-id="438ce-143">This button starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 4.</span></span>

<span data-ttu-id="438ce-144">除非你了解对用户的影响，否则不要删除标签。</span><span class="sxs-lookup"><span data-stu-id="438ce-144">Don't delete a label unless you understand the impact for users.</span></span> <span data-ttu-id="438ce-145">有关更多信息，请参阅[移除和删除标签](#removing-and-deleting-labels)部分。</span><span class="sxs-lookup"><span data-stu-id="438ce-145">For more information, see the [Removing and deleting labels](#removing-and-deleting-labels) section.</span></span> 

> [!NOTE]
> <span data-ttu-id="438ce-146">如果要编辑已使用标签策略发布的标签，则在完成该向导时不需要执行额外步骤。</span><span class="sxs-lookup"><span data-stu-id="438ce-146">If you edit a label that's already published by using a label policy, no extra steps are needed when you finish the wizard.</span></span> <span data-ttu-id="438ce-147">例如，不需要将其添加到新的标签策略，以便对相同用户提供所做的更改。</span><span class="sxs-lookup"><span data-stu-id="438ce-147">For example, you don't need to add it to a new label policy for the changes to become available to the same users.</span></span> <span data-ttu-id="438ce-148">但是，请留出长达 24 小时的时间将更改复制到所有应用和服务。</span><span class="sxs-lookup"><span data-stu-id="438ce-148">However, allow up to 24 hours for the changes to replicate to all apps and services.</span></span>

<span data-ttu-id="438ce-149">发布标签之前，无法在应用程序或服务中使用。</span><span class="sxs-lookup"><span data-stu-id="438ce-149">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="438ce-150">若要发布标签，必须将其[添加到标签策略](#publish-sensitivity-labels-by-creating-a-label-policy)。</span><span class="sxs-lookup"><span data-stu-id="438ce-150">To publish the labels, they must be [added to a label policy](#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="438ce-151">在此“**标签**”选项卡上，不要选择“**发布标签**”选项卡（或在编辑标签时的“**发布标签**”按钮），除非你需要创建新的标签策略。</span><span class="sxs-lookup"><span data-stu-id="438ce-151">On this **Labels** tab, do not select the **Publish labels** tab (or the **Publish label** button when you edit a label) unless you need to create a new label policy.</span></span> <span data-ttu-id="438ce-152">仅当用户需要不同的标签或不同的策略设置时，才需要多个标签策略。</span><span class="sxs-lookup"><span data-stu-id="438ce-152">You need multiple label policies only if users need different labels or different policy settings.</span></span> <span data-ttu-id="438ce-153">旨在创建尽可能少的标签策略 - 组织只有一个标签策略的情况并不少见。</span><span class="sxs-lookup"><span data-stu-id="438ce-153">Aim to have as few label policies as possible—it's not uncommon to have just one label policy for the organization.</span></span>

### <a name="additional-label-settings-with-security--compliance-center-powershell"></a><span data-ttu-id="438ce-154">附加标签设置在安全与合规中心 PowerShell 中可用</span><span class="sxs-lookup"><span data-stu-id="438ce-154">Additional label settings with Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="438ce-155">附加标签设置可在[安全与合规中心 PowerShell](/powershell/exchange/scc-powershell) 中的[设置标签](/powershell/module/exchange/set-label)中使用。</span><span class="sxs-lookup"><span data-stu-id="438ce-155">Additional label settings are available with the [Set-Label](/powershell/module/exchange/set-label) cmdlet from [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).</span></span>

<span data-ttu-id="438ce-156">例如：</span><span class="sxs-lookup"><span data-stu-id="438ce-156">For example:</span></span>

- <span data-ttu-id="438ce-157">使用 *LocaleSettings* 参数来进行跨国部署，以便用户可查看使用本地语言的标签名称和工具提示。</span><span class="sxs-lookup"><span data-stu-id="438ce-157">Use the *LocaleSettings* parameter for multinational deployments so that users see the label name and tooltip in their local language.</span></span> <span data-ttu-id="438ce-158">[下列部分](#example-configuration-to-configure-a-sensitivity-label-for-different-languages)有一个示例配置，用于为法语、意大利语和德语指定标签名称和工具提示文本。</span><span class="sxs-lookup"><span data-stu-id="438ce-158">The [following section](#example-configuration-to-configure-a-sensitivity-label-for-different-languages) has an example configuration that specifies the label name and tooltip text for French, Italian, and German.</span></span>

- <span data-ttu-id="438ce-159">仅限 Azure 信息保护统一标记客户端，指定包括设置标签颜色，以及在应用标签时应用自定义属性的[高级设置](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)。</span><span class="sxs-lookup"><span data-stu-id="438ce-159">For the Azure Information Protection unified labeling client only, specify [advanced settings](/azure/information-protection/rms-client/clientv2-admin-guide-customizations) that include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="438ce-160">有关完整列表，请参阅该客户端管理员指南的[标签 可用高级设置](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)。</span><span class="sxs-lookup"><span data-stu-id="438ce-160">For the full list, see [Available advanced settings for labels](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels) from this client's admin guide.</span></span>

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a><span data-ttu-id="438ce-161">配置不同语言的灵敏度标签的配置示例</span><span class="sxs-lookup"><span data-stu-id="438ce-161">Example configuration to configure a sensitivity label for different languages</span></span>

<span data-ttu-id="438ce-162">下面的示例显示了名为“Public”的标签的 PowerShell 配置以及工具提示的占位符文本。</span><span class="sxs-lookup"><span data-stu-id="438ce-162">The following example shows the PowerShell configuration for a label named "Public" with placeholder text for the tooltip.</span></span> <span data-ttu-id="438ce-163">在此示例中，将为法语、意大利语和德语配置标签名称和工具提示文本。</span><span class="sxs-lookup"><span data-stu-id="438ce-163">In this example, the label name and tooltip text are configured for French, Italian, and German.</span></span>

<span data-ttu-id="438ce-164">进行此配置后，如果用户拥有使用这些显示语言的 Office 应用，则会看到他们的标签名称和工具提示使用相同的语言。</span><span class="sxs-lookup"><span data-stu-id="438ce-164">As a result of this configuration, users who have Office apps that use those display languages see their label names and tooltips in the same language.</span></span> <span data-ttu-id="438ce-165">类似地，当你已安装 Azure 信息保护统一标签客户端以标记文件资源管理器中的文件时，如果用户具有这些语言版本的 Windows，则他们在使用右键单击来进行标记时将会看到其标签名称和工具提示以本地语言显示。</span><span class="sxs-lookup"><span data-stu-id="438ce-165">Similarly, if you have the Azure Information Protection unified labeling client installed to label files from File Explorer, users who have those language versions of Windows see their label names and tooltips in their local language when they use the right-click actions for labeling.</span></span>

<span data-ttu-id="438ce-166">对于需要支持的语言，请使用 Office [语言标识符](/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers)（也称为语言标记），并指定你自己的标签名称和工具提示翻译。</span><span class="sxs-lookup"><span data-stu-id="438ce-166">For the languages that you need to support, use the Office [language identifiers](/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (also known as language tags), and specify your own translation for the label name and tooltip.</span></span>

<span data-ttu-id="438ce-167">在 PowerShell 中运行命令之前，必须先[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="438ce-167">Before you run the commands in PowerShell, you must first [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>


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
$TooltipLocaleSettings = [PSCustomObject]@{LocaleKey='Tooltip';
Settings=@(
@{key=$Languages[0];Value=$Tooltips[0];}
@{key=$Languages[1];Value=$Tooltips[1];}
@{key=$Languages[2];Value=$Tooltips[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $DisplayNameLocaleSettings -Depth 3 -Compress),(ConvertTo-Json $TooltipLocaleSettings -Depth 3 -Compress)
```

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="438ce-168">通过创建标签策略来发布敏感度标签</span><span class="sxs-lookup"><span data-stu-id="438ce-168">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="438ce-169">在标签管理中心中，导航到“灵敏度”标签：</span><span class="sxs-lookup"><span data-stu-id="438ce-169">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="438ce-170">Microsoft 365 合规中心：</span><span class="sxs-lookup"><span data-stu-id="438ce-170">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="438ce-171">**解决方案** > **信息保护**</span><span class="sxs-lookup"><span data-stu-id="438ce-171">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="438ce-172">如果看不到此选项，请先选择“**全部显示**”。</span><span class="sxs-lookup"><span data-stu-id="438ce-172">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="438ce-173">安全与合规中心：</span><span class="sxs-lookup"><span data-stu-id="438ce-173">Security & Compliance Center:</span></span>
        - <span data-ttu-id="438ce-174">**分类** > **灵敏度标签**</span><span class="sxs-lookup"><span data-stu-id="438ce-174">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="438ce-175">依次选择“**标签策略**”选项卡和“**发布标签**”，以启动“创建策略”向导：</span><span class="sxs-lookup"><span data-stu-id="438ce-175">Select the **Label policies** tab, and then **Publish labels** to start the Create policy wizard:</span></span>
    
    <span data-ttu-id="438ce-176">例如，从 Microsoft 365 合规中心：</span><span class="sxs-lookup"><span data-stu-id="438ce-176">For example, from the Microsoft 365 compliance center:</span></span>
        
    ![发布标签](../media/publish-sensitivity-labels-full.png)
    
    > [!NOTE]
    > <span data-ttu-id="438ce-178">默认情况下，租户没有任何标签策略，且必须由你创建。</span><span class="sxs-lookup"><span data-stu-id="438ce-178">By default, tenants don't have any label policies and you must create them.</span></span> 

3. <span data-ttu-id="438ce-179">在想到中，选择“**选择要发布的敏感度标签**”。</span><span class="sxs-lookup"><span data-stu-id="438ce-179">In the wizard, select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="438ce-180">选择可在应用和服务中可以使用的标签，随后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="438ce-180">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="438ce-181">如果选择子标签，请确保也选择其父标签。</span><span class="sxs-lookup"><span data-stu-id="438ce-181">If you select a sublabel, make sure you also select its parent label.</span></span>
    
4. <span data-ttu-id="438ce-182">查看所选标签，若要进行任何更改，请选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="438ce-182">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="438ce-183">否则选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="438ce-183">Otherwise, select **Next**.</span></span>

5. <span data-ttu-id="438ce-184">按照提示配置策略设置。</span><span class="sxs-lookup"><span data-stu-id="438ce-184">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="438ce-185">所看到的策略设置会匹配你选择的标签的范围。</span><span class="sxs-lookup"><span data-stu-id="438ce-185">The policy settings that you see match the scope of the labels that you selected.</span></span> <span data-ttu-id="438ce-186">例如，如果选择了仅用于 **文件和电子邮件** 范围，则默认情况下看不到策略设置 **“”将此标签应用到组和网站”** 和 **“要求用户将标签应用到他们的组和网站”**。</span><span class="sxs-lookup"><span data-stu-id="438ce-186">For example, if you selected labels that have just the **Files & emails** scope, you don't see the policy settings **Apply this label by default to groups and sites** and **Require users to apply a label to their groups and sites**.</span></span>
    
    <span data-ttu-id="438ce-187">有关这些设置的详细信息，请参阅概述信息中的[标签策略有何用途](sensitivity-labels.md#what-label-policies-can-do)并使用向导中针对单个设置的帮助。</span><span class="sxs-lookup"><span data-stu-id="438ce-187">For more information about these settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information and use the help in the wizard for individual settings.</span></span>
    
    <span data-ttu-id="438ce-188">对于为 **Azure Purview 素材（预览版）** 配置的标签：这些标签没有任何关联的策略设置。</span><span class="sxs-lookup"><span data-stu-id="438ce-188">For labels configured for **Azure Purview assets (preview)**: These labels don't have any associated policy settings.</span></span>

7. <span data-ttu-id="438ce-189">如果不同的用户或范围需要不同的策略设置，请重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="438ce-189">Repeat these steps if you need different policy settings for different users or scopes.</span></span> <span data-ttu-id="438ce-190">例如，希望为一组用户创建附加标签，或用户为子集创建不同的默认标签。</span><span class="sxs-lookup"><span data-stu-id="438ce-190">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span> <span data-ttu-id="438ce-191">或者，如果你配置的标签具有不同的范围。</span><span class="sxs-lookup"><span data-stu-id="438ce-191">Or, if you have configured labels to have different scopes.</span></span>

8. <span data-ttu-id="438ce-192">如果创建多个可能导致用户发生冲突的标签策略，请查看策略顺序，并根据需要向上或向下移动。</span><span class="sxs-lookup"><span data-stu-id="438ce-192">If you create more than one label policy that might result in a conflict for a user, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="438ce-193">若要更改标签策略的顺序，请选择“**...**”进行 **更多操作**”，然后选择 “**上移**”或 “**下移**”。</span><span class="sxs-lookup"><span data-stu-id="438ce-193">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="438ce-194">有关详细信息，请参阅概述信息中的“[标签策略优先级（顺序非常重要）](sensitivity-labels.md#label-policy-priority-order-matters)”。</span><span class="sxs-lookup"><span data-stu-id="438ce-194">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="438ce-195">完成向导会自动发布标签策略。</span><span class="sxs-lookup"><span data-stu-id="438ce-195">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="438ce-196">若要更改已发布的策略，只需对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="438ce-196">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="438ce-197">没有特定发布或重新发布操作可供选择。</span><span class="sxs-lookup"><span data-stu-id="438ce-197">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="438ce-198">若要编辑现有标签策略，请将其选中，然后选择“**编辑策略**”按钮：</span><span class="sxs-lookup"><span data-stu-id="438ce-198">To edit an existing label policy, select it, and then select the **Edit Policy** button:</span></span> 

![编辑敏感度标签](../media/edit-sensitivity-label-policy-full.png)

<span data-ttu-id="438ce-200">此按钮将启动“**创建策略**”向导，可用于编辑所包含的标签和标签设置。</span><span class="sxs-lookup"><span data-stu-id="438ce-200">This button starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="438ce-201">完成向导后，所有更改都将自动复制到所选用户和服务。</span><span class="sxs-lookup"><span data-stu-id="438ce-201">When you complete the wizard, any changes are automatically replicated to the selected users and services.</span></span>

<span data-ttu-id="438ce-p125">对 Windows、macOS、iOS 和 Android 上的 Office 应用使用内置标签时，刷新浏览器时，用户会在 4 个小时内看到新标签，而在 Word、Excel 和 PowerPoint Web 版上，1 小时内就可以看到新标签。但是，请留出长达 24 小时的时间将更改复制到所有应用和服务。</span><span class="sxs-lookup"><span data-stu-id="438ce-p125">When you use built-in labeling for Office apps on Windows, macOS, iOS, and Android, users see new labels within four hours, and within one hour for Word, Excel, and PowerPoint on the web when you refresh the browser. However, allow up to 24 hours for changes to replicate to all apps and services.</span></span>

### <a name="additional-label-policy-settings-with-security--compliance-center-powershell"></a><span data-ttu-id="438ce-204">附加标签策略设置在安全与合规中心 PowerShell 中可用</span><span class="sxs-lookup"><span data-stu-id="438ce-204">Additional label policy settings with Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="438ce-205">附加标签策略设置可在[安全与合规中心 PowerShell](/powershell/exchange/scc-powershell) 中的[Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy) cmdlet 中使用。</span><span class="sxs-lookup"><span data-stu-id="438ce-205">Additional label policy settings are available with the [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy) cmdlet from [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).</span></span>

<span data-ttu-id="438ce-206">Azure 信息保护统一标记客户端支持许多[高级设置](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)，包括从其他标签解决方案进行迁移，以及在 Outlook 中弹出警告、证明或阻止发送电子邮件的消息。</span><span class="sxs-lookup"><span data-stu-id="438ce-206">The Azure Information Protection unified labeling client supports many [advanced settings](/azure/information-protection/rms-client/clientv2-admin-guide-customizations) that include migrating from other labeling solutions, and pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="438ce-207">有关完整列表，请参阅该客户端管理员指南的 “[适用于标签策略的高级设置](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)”。</span><span class="sxs-lookup"><span data-stu-id="438ce-207">For the full list, see [Available advanced settings for label policies](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies) from this client's admin guide.</span></span>

## <a name="use-powershell-for-sensitivity-labels-and-their-policies"></a><span data-ttu-id="438ce-208">为灵敏度标签及其策略使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="438ce-208">Use PowerShell for sensitivity labels and their policies</span></span>

<span data-ttu-id="438ce-209">现在，你可以使用 [安全性 & 合规性中心 PowerShell](/powershell/exchange/scc-powershell) 创建和配置你在标签管理中心里看到的所有设置。</span><span class="sxs-lookup"><span data-stu-id="438ce-209">You can now use [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell) to create and configure all the settings you see in your labeling admin center.</span></span> <span data-ttu-id="438ce-210">这意味着，除了将 PowerShell 用于标记管理中心里不可用的设置外，你现在还可以完全编写灵敏度标签和灵敏度标签策略的创建和维护脚本。</span><span class="sxs-lookup"><span data-stu-id="438ce-210">This means that in addition to using PowerShell for settings that aren't available in the labeling admin centers, you can now fully script the creation and maintenance of sensitivity labels and sensitivity label policies.</span></span> 

<span data-ttu-id="438ce-211">请参阅以下文档，获取受支持的参数和值：</span><span class="sxs-lookup"><span data-stu-id="438ce-211">See the following documentation for supported parameters and values:</span></span>

- [<span data-ttu-id="438ce-212">New-Label</span><span class="sxs-lookup"><span data-stu-id="438ce-212">New-Label</span></span>](/powershell/module/exchange/new-label)
- [<span data-ttu-id="438ce-213">New-LabelPolicy</span><span class="sxs-lookup"><span data-stu-id="438ce-213">New-LabelPolicy</span></span>](/powershell/module/exchange/new-labelpolicy)
- [<span data-ttu-id="438ce-214">Set-Label</span><span class="sxs-lookup"><span data-stu-id="438ce-214">Set-Label</span></span>](/powershell/module/exchange/set-label)
- [<span data-ttu-id="438ce-215">Set-LabelPolicy</span><span class="sxs-lookup"><span data-stu-id="438ce-215">Set-LabelPolicy</span></span>](/powershell/module/exchange/set-labelpolicy)

<span data-ttu-id="438ce-216">如果你需要编写对敏感度标签或灵敏度标签策略的删除脚本，则还可使用 [Remove-Label](/powershell/module/exchange/remove-label) 和 [Remove-LabelPolicy](/powershell/module/exchange/remove-labelpolicy)。</span><span class="sxs-lookup"><span data-stu-id="438ce-216">You can also use [Remove-Label](/powershell/module/exchange/remove-label) and [Remove-LabelPolicy](/powershell/module/exchange/remove-labelpolicy) if you need to script the deletion of sensitivity labels or sensitivity label policies.</span></span> <span data-ttu-id="438ce-217">但是，在你删除灵敏度标签前，请务必阅读以下部分。</span><span class="sxs-lookup"><span data-stu-id="438ce-217">However, before you delete sensitivity labels, make sure you read the following section.</span></span>

## <a name="removing-and-deleting-labels"></a><span data-ttu-id="438ce-218">移除和删除标签</span><span class="sxs-lookup"><span data-stu-id="438ce-218">Removing and deleting labels</span></span>

<span data-ttu-id="438ce-219">在生产环境中，不太可能需要从标签策略中移除敏感度标签，也不太可能需要删除敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="438ce-219">In a production environment, it's unlikely that you will need to remove sensitivity labels from a label policy, or delete sensitivity labels.</span></span> <span data-ttu-id="438ce-220">更有可能是在初始测试阶段需要执行这两项操作之一。</span><span class="sxs-lookup"><span data-stu-id="438ce-220">It's more likely that you might need to do one or either of these actions during an initial testing phase.</span></span> <span data-ttu-id="438ce-221">请务必了解执行这两项操作之一时所发生的情况。</span><span class="sxs-lookup"><span data-stu-id="438ce-221">Make sure you understand what happens when you do either of these actions.</span></span>

<span data-ttu-id="438ce-222">从标签策略中移除标签比删除标签的风险要小；如果需要，稍后始终可以将标签添加回标签策略中：</span><span class="sxs-lookup"><span data-stu-id="438ce-222">Removing a label from a label policy is less risky than deleting it, and you can always add it back to a label policy later if needed:</span></span>

- <span data-ttu-id="438ce-223">如果从标签策略中移除标签，让标签不再发布给最初指定的用户，那么当标签策略下次刷新时，标签就不再可供这些用户在 Office 应用程序中选择。</span><span class="sxs-lookup"><span data-stu-id="438ce-223">When you remove a label from a label policy so that the label is no longer published to the originally specified users, the next time the label policy is refreshed, users no longer see that label to select in their Office app.</span></span> <span data-ttu-id="438ce-224">不过，如果已将标签应用于文档或电子邮件，那么标签不会从此类内容中移除。</span><span class="sxs-lookup"><span data-stu-id="438ce-224">However, if the label has been applied to documents or emails, the label isn't removed from that content.</span></span> <span data-ttu-id="438ce-225">由标签应用的任何加密都会保留，且基础保护模板也会保持已发布状态不变。</span><span class="sxs-lookup"><span data-stu-id="438ce-225">Any encryption that was applied by the label remains and the underlying protection template remains published.</span></span> 

- <span data-ttu-id="438ce-226">对于已移除但以前应用于内容的标签，在 Word、Excel 和 PowerPoint 中使用内置标签的用户仍会在状态栏中看到已应用标签名称。</span><span class="sxs-lookup"><span data-stu-id="438ce-226">For labels that are removed but have previously been applied to content, users who are using built-in labeling for Word, Excel, and PowerPoint, still see the applied label name on the status bar.</span></span> <span data-ttu-id="438ce-227">同样，已移除但以前应用于 SharePoint 网站的标签仍会在“敏感度”列中显示标签名称。</span><span class="sxs-lookup"><span data-stu-id="438ce-227">Similarly, labels that are removed that were applied to SharePoint sites still display the label name in the **Sensitivity** column.</span></span>

<span data-ttu-id="438ce-228">相比之下，如果删除标签：</span><span class="sxs-lookup"><span data-stu-id="438ce-228">In comparison, when you delete a label:</span></span>

- <span data-ttu-id="438ce-229">如果标签应用了加密，则会存档基础保护模板，这样以前受保护的内容就仍能打开。</span><span class="sxs-lookup"><span data-stu-id="438ce-229">If the label applied encryption, the underlying protection template is archived so that previously protected content can still be opened.</span></span> <span data-ttu-id="438ce-230">因为有此已存档保护模板，所以无法创建同名的新标签。</span><span class="sxs-lookup"><span data-stu-id="438ce-230">Because of this archived protection template, you won't be able to create a new label with the same name.</span></span> <span data-ttu-id="438ce-231">虽然可以使用 [PowerShell](/powershell/module/aipservice/remove-aipservicetemplate) 删除保护模板，但请不要这样做，除非你确定无需打开使用已存档模板加密的内容。</span><span class="sxs-lookup"><span data-stu-id="438ce-231">Although it's possible to delete a protection template by using [PowerShell](/powershell/module/aipservice/remove-aipservicetemplate), don't do this unless you're sure you don't need to open content that was encrypted with the archived template.</span></span>

- <span data-ttu-id="438ce-232">对于桌面应用程序：元数据中的标签信息会保留，但由于无法再进行标签 ID 到名称的映射，导致用户看不到显示的已应用标签名称（例如，在状态栏中），因此用户会假定内容未标记。</span><span class="sxs-lookup"><span data-stu-id="438ce-232">For desktop apps: The label information in the metadata remains, but because a label ID to name mapping is no longer possible, users don't see the applied label name displayed (for example, on the status bar) so users will assume the content isn't labeled.</span></span> <span data-ttu-id="438ce-233">如果标签应用了加密，则会保留加密，且用户仍会在内容打开时看到当前已存档保护模板的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="438ce-233">If the label applied encryption, the encryption remains and when the content is opened, uses still see the name and description of the now archived protection template.</span></span>

- <span data-ttu-id="438ce-234">对于 Office 网页版：用户在状态栏或“敏感度”列中看不到标签名称。</span><span class="sxs-lookup"><span data-stu-id="438ce-234">For Office on the web: Users don't see the label name on status bar or in the **Sensitivity** column.</span></span> <span data-ttu-id="438ce-235">元数据中的标签信息仅在标签未应用加密的情况下保留。</span><span class="sxs-lookup"><span data-stu-id="438ce-235">The label information in the metadata remains only if the label didn't apply encryption.</span></span> <span data-ttu-id="438ce-236">如果标签应用了加密，且你已[为 SharePoint 和 OneDrive 启用敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)，那么元数据中的标签信息就会遭移除，且加密也会遭撤消。</span><span class="sxs-lookup"><span data-stu-id="438ce-236">If the label applied encryption, and you've enabled [sensitivity labels for SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md), the label information in the metadata is removed and the encryption is removed.</span></span> 

<span data-ttu-id="438ce-237">从标签策略中移除敏感度标签或删除敏感度标签时，这些更改最多可能需要 24 小时才能复制到所有用户和服务。</span><span class="sxs-lookup"><span data-stu-id="438ce-237">When you remove a sensitivity label from a label policy, or delete a sensitivity label, these changes can take up to 24 hours to replicate to all users and services.</span></span>

## <a name="next-steps"></a><span data-ttu-id="438ce-238">后续步骤</span><span class="sxs-lookup"><span data-stu-id="438ce-238">Next steps</span></span>

<span data-ttu-id="438ce-239">若要根据具体情况配置和使用敏感度标签，请使用下列文章：</span><span class="sxs-lookup"><span data-stu-id="438ce-239">To configure and use your sensitivity labels for specific scenarios, use the following articles:</span></span>

- [<span data-ttu-id="438ce-240">使用敏感度标签中的加密限制对内容的访问</span><span class="sxs-lookup"><span data-stu-id="438ce-240">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="438ce-241">将敏感度标签自动应用于内容</span><span class="sxs-lookup"><span data-stu-id="438ce-241">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="438ce-242">将灵敏度标签与团队、组和网站配合使用</span><span class="sxs-lookup"><span data-stu-id="438ce-242">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="438ce-243">启用 SharePoint 和 OneDrive 中 Office 文件的灵敏度标签</span><span class="sxs-lookup"><span data-stu-id="438ce-243">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="438ce-244">若要监视标签使用方式，请参阅 [数据分类入门](data-classification-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="438ce-244">To monitor how your labels are being used, see [Get started with data classification](data-classification-overview.md).</span></span>