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
ms.openlocfilehash: 8018c18e976d0e6f9904923471bb07c8bb3cbc40
ms.sourcegitcommit: 7d07e7ec84390a8f05034d3639fa5db912809585
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42091295"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a>创建和配置敏感度标签及其策略

若要创建并发布 [敏感度标签](sensitivity-labels.md)，请转到你的标签管理中心，如 [Microsoft 365 合规性中心](https://compliance.microsoft.com/)。 此外，还可使用 Microsoft 365 安全中心，或 Office 365 安全与合规中心。

首先，创建和配置你想要在 Office 应用和服务中使用的敏感度标签。 然后，创建一个或多个包含标签和你配置的策略设置的标签策略。 这是用于发布所选用户和位置的标签和设置的标签策略。

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a>创建和管理敏感度标签所需的权限

将要创建敏感度标签的合规团队成员需要 Microsoft 365 合规中心、Microsoft 365 安全中心或 Office 365 安全与合规中心的访问权限。 

默认情况下，你的租户管理员有权访问这些管理中心，并且可以向合规专员和其他人提供访问权限，而不为其提供租户管理员的所有权限。要获得这一委派的受限管理员访问权限，请转到其中一个管理中心的“权限”**** 页面，然后将成员添加到**合规性数据管理员**、**合规性管理员**或**安全管理员**角色组。

如果不使用角色，可以创建新的角色组，然后将“**敏感度标签管理员**”或“**组织配置**”角色添加到此组。 有关说明，请参阅[向用户授予对 Office 365 安全与合规中心的访问权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)。

只有在创建和配置灵敏度标签及其标签策略时才需要这些权限。 在应用或服务中应用标这些签时不需要这些权限。

## <a name="create-and-configure-sensitivity-labels"></a>创建和配置敏感度标签

1. 在标签管理中心中，导航到“灵敏度”标签：
    
    - Microsoft 365 合规中心： 
        - **解决方案** > **信息保护**
        
        如果看不到此选项，请先选择“**全部显示**”。 
    
    - Microsoft 365 安全中心： 
        - **分类** > **灵敏度标签**
    
    - Office 365 安全与合规中心：
        - **分类** > **灵敏度标签**

2. 在“**标签**”选项卡上，选择“**+ 创建标签**”，以启动“**新建灵敏度标签**”向导 。

3. 按照提示进行操作以设置标签。
    
    有关标签设置的详细信息，请参阅概述信息中的“[敏感度标签可以做什么](sensitivity-labels.md#what-sensitivity-labels-can-do)”。

4. 重复这些步骤以创建更多标签。 但是，如果想要创建子标签，请先选择父标签，然后点击“**...**”并选择“**更多操作**”，然后选择“**添加子标签**”。

5. 创建所需的所有标签后，请查看其顺序，如有必要，请向上或向下移动它们。 若要更改标签的顺序，请选择“**...**”进行**更多操作**”，然后选择 “**上移 **”或 “**下移**”。 有关详细信息，请参阅概述信息中的“[标签优先级（顺序非常重要）](sensitivity-labels.md#label-priority-order-matters)”。

若要编辑现有标签，请将其选中，然后选择“**编辑标签**”。 这将启动“**编辑敏感度标签**”向导，可用于更改步骤 3 中的所有标签设置。 

> [!NOTE]
> 如果要编辑已使用标签策略发布的标签，则在完成该向导时不需要执行额外步骤。 例如，不需要将其添加到新的标签策略，即可对相同用户提供所做的更改。 但是，可允许在 24 小时内将所做的更改复制到用户和服务。

发布标签之前，无法在应用程序或服务中使用。 若要发布标签，必须将其[添加到标签策略](#publish-sensitivity-labels-by-creating-a-label-policy)。

> [!IMPORTANT]
> 在此“**标签**”选项卡上，不要选择“**发布标签**”选项卡（或在编辑标签时的“**发布标签**”按钮），除非你需要创建新的标签策略。 仅当用户需要不同的标签或不同的策略设置时，才需要多个标签策略。 旨在创建尽可能少的标签策略 - 组织只有一个标签策略的情况并不少见。

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a>附加标签设置在 Office 365 安全与合规中心 PowerShell 中可用

附加标签设置可在 “[Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)”中的“[设置标签](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps)“中使用。

使用 *LocaleSettings* 参数来进行跨国部署，以便用户可查看使用本地语言的标签名称和工具提示。 有关配置示例，请参阅下面的部分。 

使用此 cmdlet，还可为 Azure 信息保护统一标签客户端指定[“高级设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)”。 这些高级设置包括应用标签时设定标签颜色，应用自定义属性。 如需完整的列表，请参阅“[可用的高级标签策略设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)”。 

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a>配置不同语言的灵敏度标签的配置示例

下面的示例显示了名为“Public”的标签的 PowerShell 配置以及工具提示的占位符文本。 在此示例中，将为法语、意大利语和德语配置标签名称和工具提示文本。

进行此配置后，如果用户拥有使用这些显示语言的 Office 应用，则会看到他们的标签名称和工具提示使用相同的语言。 类似地，当你已安装 Azure 信息保护统一标签客户端以标记文件资源管理器中的文件时，如果用户具有这些语言版本的 Windows，则他们在使用右键单击来进行标记时将会看到其标签名称和工具提示以本地语言显示。

对于需要支持的语言，请使用 Office [语言标识符](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers)（也称为语言标记），并指定你自己的标签名称和工具提示翻译。

在 PowerShell 中运行命令之前，必须先[连接到 Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。


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

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a>通过创建标签策略来发布敏感度标签

1. 在标签管理中心中，导航到“灵敏度”标签：
    
    - Microsoft 365 合规中心： 
        - **解决方案** > **信息保护**
        
        如果看不到此选项，请先选择“**全部显示**”。 
    
    - Microsoft 365 安全中心： 
        - **分类** > **灵敏度标签**
    
    - Office 365 安全与合规中心：
        - **分类** > **灵敏度标签**

2. 选择“**标签策略**”选项卡。

3. 选择“**发布标签**”以启动“**创建策略向导**”。

4. 选择 “**选择要发布的敏感度标签**”。 选择可在应用和服务中可以使用的标签，随后选择“**添加**”。

5. 查看所选标签，若要进行任何更改，请选择“**编辑 **”。 否则选择“**下一步**”。

6. 按照提示配置策略设置。
    
    有关设置的详细信息，请参阅概述信息中的“[标签策略可以做什么](sensitivity-labels.md#what-label-policies-can-do)”。

7. 如果不同的用户或位置需要不同的策略设置，请重复这些步骤。 例如，希望为一组用户创建附加标签，或用户为子集创建不同的默认标签。

8. 如果创建多个可能导致用户或位置发生冲突的标签策略，请查看策略顺序，并根据需要向上或向下移动。 若要更改标签策略的顺序，请选择“**...**”进行**更多操作**”，然后选择 “**上移 **”或 “**下移**”。 有关详细信息，请参阅概述信息中的“[标签策略优先级（顺序非常重要）](sensitivity-labels.md#label-policy-priority-order-matters)”。

完成向导会自动发布标签策略。 若要更改已发布的策略，只需对其进行编辑。 没有特定发布或重新发布操作可供选择。

若要编辑现有标签策略，请将其选中，然后选择“**编辑策略**”。 这将启动“**创建策略**”向导，可用于编辑所包含的标签和标签设置。 完成向导后，所有更改都将自动复制到所选用户和服务。

通常情况下，用户会在几个小时内查看其 Office 应用中的标签。 但是，可允许在 24 小时内将标签策略及其任何更改复制到所有用户和服务。

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a>附加标签策略设置在 Office 365 安全与合规中心 PowerShell 中可用

附加标签策略设置可在 “[Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)”中的“[设置标签](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps)“中使用。

使用此 cmdlet，可为 Azure 信息保护统一标签客户端指定[“高级设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)”。 这些高级设置包括为 Outlook 设置不同的默认标签，并在 Outlook 中实现弹出消息，警告、两端对齐或阻止正在发送的电子邮件。 如需完整的列表，请参阅“[可用的高级标签设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)”。 

此外，还可使用此 cmdlet 在标签策略中添加和删除标签。


## <a name="next-steps"></a>后续步骤

若要根据具体情况配置和使用敏感度标签，请使用下列文章：

- [使用敏感度标签中的加密限制对内容的访问](encryption-sensitivity-labels.md)

- [将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md)

- [将灵敏度标签与团队、组和网站配合使用](sensitivity-labels-teams-groups-sites.md)

- [启用 SharePoint 和 OneDrive 中 Office 文件的灵敏度标签](sensitivity-labels-sharepoint-onedrive-files.md)

若要监视标签的使用情况，请参阅“[使用标签分析查看标签使用情况](label-analytics.md)”。
