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
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a>创建和配置敏感度标签及其策略

若要创建并发布 [敏感度标签](sensitivity-labels.md)，请转到你的标签管理中心，如 [Microsoft 365 合规性中心](https://compliance.microsoft.com/)。 此外，还可使用 Microsoft 365 安全中心，或 Office 365 安全与合规中心。

首先，创建和配置你想要在 Office 应用和服务中使用的敏感度标签。 然后，创建一个或多个包含标签和你配置的策略设置的标签策略。 这是用于发布所选用户和位置的标签和设置的标签策略。

## <a name="create-and-configure-sensitivity-labels"></a>创建和配置敏感度标签

1. 在标签管理中心中，导航到“**分类** > **敏感度标签**”。

2. 在“**标签**”选项卡上，选择“**+ 创建标签**”，以启动 “**新建敏感度标签**”向导。

3. 按照提示进行操作以设置标签。
    
    有关标签设置的详细信息，请参阅概述信息中的“[敏感度标签可以做什么](sensitivity-labels.md#what-sensitivity-labels-can-do)”。

4. 重复这些步骤以创建更多标签。 但是，如果想要创建子标签，请先选择父标签，然后点击“**...**”并选择“**更多操作**”，然后选择“**添加子标签**”。

5. 创建所需的所有标签后，请查看其顺序，如有必要，请向上或向下移动它们。 若要更改标签的顺序，请选择“**...**”进行**更多操作**”，然后选择 “**上移 **”或 “**下移**”。 有关详细信息，请参阅概述信息中的“[标签优先级（顺序非常重要）](sensitivity-labels.md#label-priority-order-matters)”。

若要编辑现有标签，请将其选中，然后选择“**编辑标签**”。 这将启动“**编辑敏感度标签**”向导，可用于更改步骤 3 中的所有标签设置。 如果已使用标签策略发布了标签，则无需额外的步骤，但最长可允许24 小时将所做的更改复制到用户和位置。

发布标签之前，无法在应用程序或服务中使用。 如果要发布标签，必须要添加至标签策略。

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a>附加标签设置在 Office 365 安全与合规中心 PowerShell 中可用

附加标签设置可在 “[Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)”中的“[设置标签](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps)“中使用。

例如，使用 *LocaleSettings* 参数为标签名称和工具提示指定不同的语言。 

使用此 cmdlet，还可为 Azure 信息保护统一标签客户端指定[“高级设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)”。 这些高级设置包括应用标签时设定标签颜色，应用自定义属性。 如需完整的列表，请参阅“[可用的高级标签策略设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)”。 

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a>通过创建标签策略来发布敏感度标签

1. 在标签管理中心中，导航到“**分类** > **敏感度标签**”。

2. 选择“**标签策略**”选项卡。

3. 选择“**发布标签**”以启动“**创建策略向导**”。

4. 选择 “**选择要发布的敏感度标签**”。 选择可在应用和服务中可以使用的标签，随后选择“**添加**”。

5. 查看所选标签，若要进行任何更改，请选择“**编辑 **”。 否则选择“**下一步**”。

6. 按照提示配置策略设置。
    
    有关设置的详细信息，请参阅概述信息中的“[标签策略可以做什么](sensitivity-labels.md#what-label-policies-can-do)”。

7. 如果不同的用户或位置需要不同的策略设置，请重复这些步骤。 例如，希望为一组用户创建附加标签，或用户为子集创建不同的默认标签。

8. 如果创建多个可能导致用户或位置发生冲突的标签策略，请查看策略顺序，并根据需要向上或向下移动。 若要更改标签策略的顺序，请选择“**...**”进行**更多操作**”，然后选择 “**上移 **”或 “**下移**”。 有关详细信息，请参阅概述信息中的“[标签策略优先级（顺序非常重要）](sensitivity-labels.md#label-policy-priority-order-matters)”。

完成向导会自动发布标签策略。 若要更改已发布的策略，只需对其进行编辑。 没有特定发布或重新发布操作可供选择。

若要编辑现有标签策略，请将其选中，然后选择“**编辑策略**”。 这将启动“**创建策略**”向导，可用于编辑所包含的标签和标签设置。 完成向导后，所有更改都将自动复制到所选用户和位置。 最长允许24小时完成复制。

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a>附加标签策略设置在 Office 365 安全与合规中心 PowerShell 中可用

附加标签策略设置可在 “[Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps)”中的“[设置标签](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps)“中使用。

使用此 cmdlet，可为 Azure 信息保护统一标签客户端指定[“高级设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)”。 这些高级设置包括为 Outlook 设置不同的默认标签，并在 Outlook 中实现弹出消息，警告、两端对齐或阻止正在发送的电子邮件。 如需完整的列表，请参阅“[可用的高级标签设置](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)”。 

此外，还可使用此 cmdlet 在标签策略中添加和删除标签。


## <a name="next-steps"></a>后续步骤

若要针对特定的方案配置和使用敏感度标签，参见下列文章：

- [使用敏感度标签中的加密限制对内容的访问](encryption-sensitivity-labels.md)

- [将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md)

- [将灵敏度标签与团队、组和网站配合使用](sensitivity-labels-teams-groups-sites.md)

- [启用 SharePoint 和 OneDrive 中 Office 文件的灵敏度标签](sensitivity-labels-sharepoint-onedrive-files.md)

若要监视标签的使用情况，请参阅“[使用标签分析查看标签使用情况](label-analytics.md)”。