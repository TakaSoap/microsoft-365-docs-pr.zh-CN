---
title: 为 Microsoft 365 中敏感度标签加密的文档启用共同创作
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
ms.topic: article
description: 打开对 SharePoint 和 OneDrive 中标记和加密的文档启用共同创作和自动保存的设置。
ms.openlocfilehash: a5c3e84e4ca8874f99a07294dccfd2e4ad7ed81f
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "50417351"
---
# <a name="enable-co-authoring-for-files-encrypted-with-sensitivity-labels"></a>为使用敏感度标签加密的文件启用共同创作

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

> [!NOTE]
> 此功能暂处于预览阶段，可能会发生变更。 
>
> 在测试租户中（而不是生产租户）中启用此功能，原因：
> - 此功能将更改标记元数据，并非所有平台上的所有应用当前都支持此更改
> - 启用此功能后，无法自己禁用此功能

启用此设置以支持 Office 桌面应用的 [共同创作](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) ，以便当通过 [敏感度标签](sensitivity-labels.md)标记和加密文档时，多个用户可以同时编辑这些文档。

如果不为租户启用此设置，用户必须在使用 Office 桌面应用时签出存储在 SharePoint 或 OneDrive 中的加密文档。 因此，他们无法实时协作。 或者，当为 SharePoint 和 OneDrive 中的 Office [启用敏感度标签时，必须使用 Office 网页](sensitivity-labels-sharepoint-onedrive-files.md)。

此外，启用此功能可实现 [和](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) 的文件都支持自动保存和自动保存功能。

## <a name="metadata-changes-for-sensitivity-labels"></a>敏感度标签的元数据更改

> [!IMPORTANT]
> 启用共同创作的设置后，未加密文件的标签信息不再保存在自定义属性中。
> 
> 如果组织中具有用于将标签元数据读或写到旧位置的任何应用、服务、脚本或工具，请不要启用此设置。

启用此设置以支持 Office 桌面应用共同创作之前，了解此操作对保存到 Office 文件并读取的标签元数据的更改非常重要。

标签元数据包含标识租户和应用敏感度标签的信息。 此设置更改为 Word、Excel 和 PowerPoint 未加密文件的元数据格式和位置。 加密文件或电子邮件没有标记元数据的更改。

此更改将影响新标签的文件和已标记的文件。 使用支持共同创作设置的应用和服务时：
- 对于新标记的文件，仅将新格式和位置用于标签元数据。
- 对于已标记的文件，如果文件具有旧格式和位置的元数据，则下次打开和保存该文件时，该格式将复制到新格式和位置。

可以从以下资源中阅读有关此元数据更改更多内容：

- 博客文章： [即将推出的 Microsoft 信息保护元数据存储更改](https://techcommunity.microsoft.com/t5/microsoft-security-and/upcoming-changes-to-microsoft-information-protection-metadata/ba-p/1904418)

- 打开规范： [2.6.3 LabelInfo 与自定义文档属性对比](https://docs.microsoft.com/openspecs/office_file_formats/ms-offcrypto/13939de6-c833-44ab-b213-e0088bf02341)

由于这些更改，如果你的组织具有将标签元数据读或写到旧位置的任何应用、服务、脚本或工具，则不要启用此设置。 如果这样做，某些示例会产生什么影响：

- 标记的文档将出现在用户未标记

- 向用户显示过期标签的文档

- 如果其他用户在不支持新标签元数据的 Office 桌面应用中打开标签文档，则共同创作和自动保存将不起作用

- 将标签标识为 Office 附件中的自定义 [Exchange Online 邮件流规则](https://docs.microsoft.com/azure/information-protection/configure-exo-rules#example-2-rule-that-applies-the-encrypt-only-option-to-emails-when-they-have-attachments-that-are-labeled-confidential--partners-and-these-emails-are-sent-outside-the-organization) 无法加密电子邮件和附件，或错误地加密它们

查看下一部分，查看支持此设置以及标签元数据的更改的应用和服务列表。

## <a name="prerequisites"></a>先决条件

启用此功能前，请确保了解以下先决条件。

- 必须为此预览使用测试租户。

- 只有全局管理员才能启用此功能。

- 必须为租户启用 [SharePoint 和 OneDrive](sensitivity-labels-sharepoint-onedrive-files.md) 敏感度标签。 如果尚未启用此功能，则当选择为具有敏感度标签的文件启用共同创作的设置时，将自动启用此功能。

- 租户中所有应用、服务和操作工具必须支持用于标记元数据 [的新](#metadata-changes-for-sensitivity-labels)：
    
    - **适用于企业的 Microsoft 365 应用：**
        - Windows：最低版本为16.0.13801.20182的[当前频道（预览版）](https://office.com/insider)，或最低版本为16.0.13819.20006的[Beta频道](https://office.com/insider)
        - macOS： [版本](https://office.com/insider) 16.47.218.0 提供 Beta 频道版本
        - iOS：尚不支持
        - Android：尚不支持
    
    - **Azure 信息保护统一标签客户端和扫描仪：** 
        - 可从 [Microsoft 下载中心](https://aka.ms/aip-coauth-pp) 安装的公共预览版本（最低为 2.10.45.0）和上一项中所列的适用于 Windows 的 Microsoft 365 企业版应用之一版本。
    
    - **适用于 Windows 或 macOS 的 OneDrive 同步应用：**
        - 最低版本 19.002.0121.0008
    
    - **终结点数据丢失防护 （Endpoint DLP）：**
        - Windows 10 1809 KB 4601383
        - Windows 10 1903 和 1909，KB 4601380
        - Windows 10 2004 KB 4601382
    
    - **使用 Microsoft 信息保护 SDK 的应用和服务：** 
        - 最低版本 1.7 

启用此功能时，Microsoft 365 服务自动支持新的标签元数据。 例如：

- [自动标记策略](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)
- [使用敏感度标签作为条件的 DLP 策略](dlp-sensitivity-label-as-condition.md)
- [Microsoft 云应用安全性已配置为应用敏感度标签](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)

## <a name="limitations"></a>限制

为使用敏感度标签加密的文件启用租户设置进行共同创作之前，请确保了解此功能的下列限制。

- 由于标签 [元数据的更改](#metadata-changes-for-sensitivity-labels)，租户中的所有应用、服务和操作工具必须支持新的标签元数据，确保标签体验一致且可靠。
    
    特定于 Excel：如果某人使用不支持敏感度标签的元数据更改的 Excel 版本编辑并保存该文件，则不应用加密的敏感度标签的元数据可删除。

- 不支持共同创作和自动保存，并且不支持标签和加密的 Office 文档，这些文档使用下列任何 [配置加密](encryption-sensitivity-labels.md#configure-encryption-settings)：
    - **允许用户在应用标签权限** Word、PowerPoint 和 Excel **复选框时分配权限，提示用户** 权限。 此配置有时称为"用户定义的权限"。
    - **将内容的访问权限设置为** 一个值，则对内容 **从不**。
    - **选择了双** 加密技术。
    
    对于采用以上任何加密配置的标签，标签会显示在 Office 应用中。 但是，当用户选择这些标签，而其他人正在编辑文档时，你会警告他们共同创作且自动保存将不可用。 如果其他人正在编辑文档，用户会看到一条消息，指出标签无法应用。

## <a name="known-issues-for-this-preview"></a>此预览的已知问题

对于使用敏感度标签加密的文件，此预览版共同创作具有下列已知问题：

- 用户对于大于 300 MB 的 Word、Excel 和 PowerPoint 文件，不能对 Office 网页版应用任何标签。 对于这些文件，可以使用 Office 桌面应用应用标签，但只有你才能打开文件。

- 当你使用 [敏感标签作为条件](dlp-sensitivity-label-as-condition.md)DLP 策略时，不支持电子邮件的未加密附件。

- 不支持适用于 iOS 和 Android 的 Office 应用。

## <a name="how-to-enable-co-authoring-for-files-with-sensitivity-labels"></a>如何为具有敏感度标签的文件启用共同创作

> [!CAUTION]
> 打开此设置是一种单向操作。 此功能在预览版中，仅在非生产环境中进行测试，且仅在阅读和理解该页上记录的任何元数据更改、先决条件、限制和任何已知问题后才能进行测试。

在预览期间，必须使用特定 URL 访问 Microsoft 365 合规中心中的此设置。

1. 使用以下链接，以测试租户的全局管理员角色登录 Microsoft 365 合规中心：
    
    ````
    https://compliance.microsoft.com/co-authoring_for_files_with_sensitivity_labels
    ````
    此链接将直接进入租户设置，为具有敏感度标签 **创建共同**。

    > [!IMPORTANT]
    > 在继续之前，请检查是否登录到了对用户没有影响的测试租户： 
    >
    > 在合规中心右上方选择带帐户缩写的圆圈，然后确认租户名称是否显示预期测试租户。
    
2. 阅读摘要说明、先决条件、预期内容以及打开此设置后无法关闭此设置的警告。 然后选择 **针对具有敏感度标签的文件启用共同创作**， **应用**：
    
    ![为具有敏感度标签的文件启用共同创作的选项](../media/co-authoring-tenant-option-for-sensitivity-labels.png)

3. 请等待 24 小时，让此设置复制整个环境，然后再测试此新功能进行共同创作。

## <a name="contact-support-if-you-need-to-disable-this-feature"></a>如果需要禁用此功能，请联系支持人员

> [!IMPORTANT]
> 如果需要禁用此功能，请注意标签信息可能会丢失。

为具有租户的敏感度标签的文件启用共同创作后，无法自己禁用此设置。 因此，在启用此设置之前，必须检查并了解先决条件、结果和限制，这一点至关重要。 这也是建议使用测试租户（而不是生产租户）测试此功能的原因。

![显示针对敏感度标签开启共同创作的选项](../media/co-authoring-tenant-option-set-for-sensitivity-labels.png)

如在打开此设置时从屏幕截图中看到的，可联系 Microsoft [支持人员](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) 请求关闭此设置。 此请求可能需要几天时间，并且你需要证明你是租户的全局管理员。 通常需要支付支持费用。 

如果支持工程师为租户禁用此设置：

- 对于支持新的标签元数据的应用和服务，读取或保存标签时，它们现在将还原为原始元数据格式和位置。

- 启用设置时使用的 Office 文档的新元数据格式和位置不会复制到原始格式和位置。 因此，此未加密 Word、Excel 和 PowerPoint 文件的标记信息将会丢失。

- 共同创作和自动保存在租户中不再有效。

- 对 OneDrive 和 SharePoint 中的 Office 文件，敏感度标签保持启用状态。
