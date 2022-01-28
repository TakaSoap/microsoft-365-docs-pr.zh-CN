---
title: 为保留策略的例外创建保留标签
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 为信息管理的保留策略创建例外的保留标签的说明，以便你可以保留所需内容并删除不需要的内容。
ms.openlocfilehash: 6676840285ef94f2c3b4fd3e15bfc0b074833849
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2022
ms.locfileid: "62242141"
---
# <a name="create-retention-labels-for-exceptions-to-your-retention-policies"></a>为保留策略的例外创建保留标签

>*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

作为管理信息策略的一部分来保留所需内容并删除不需要的内容，可能需要为需要保留策略例外的项目创建一些保留标签。 

保留策略会自动应用于容器级别的所有项目（如 SharePoint 网站、用户邮箱等），而保留标签则应用于单个项目，例如 SharePoint 文档或电子邮件。

出于[保留的原则](retention.md#the-principles-of-retention-or-what-takes-precedence)，可以使用保留标签来补充需要保留更长的特定 SharePoint、OneDrive 或 Exchange 项目的保留策略，或早于同一位置的保留策略中的指定设置删除。

例如：SharePoint 网站上的大部分内容需要保留 3 年，保留策略对此进行了介绍。 但有些合同文档必须保留七年。 可以使用保留标签来解决这些例外。 将保留策略分配到所有 SharePoint 网站后，可将保留标签应用于合同文档。 所有 SharePoint 项目将保留三年，仅合同文档保留七年。

与保留策略相比，保留标签还支持更多功能。 有关详细信息，请参阅[比较保留策略和保留标签的功能](retention.md#compare-capabilities-for-retention-policies-and-retention-labels)。

通过以下信息来帮助你创建保留标签，以在信息管理策略中补充保留策略。

> [!NOTE]
> 如果需要使用保留标签来管理业务、法律或法规记录保留要求的高价值项目的生命周期管理，请从 **记录管理** 解决方案中创建保留标签，而不是 **格式管理**。 例如，你想要使用基于事件的保留或处置评审。 有关说明，请参阅[使用文件计划创建和管理保留标签](file-plan-manager.md)。

## <a name="before-you-begin"></a>准备工作

组织的全局管理员拥有创建和编辑保留标签及其策略的完全权限。 如果未以全局管理员身份登录，请参阅[保留策略和保留标签的权限](get-started-with-information-governance.md#permissions-for-retention-policies-and-retention-labels)。

## <a name="how-to-create-retention-labels-for-information-governance"></a>如何为信息管理创建保留标签

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com/)内，转至：**解决方案** > **信息治理** > **标签** 选项卡 > + **创建标签**
    
    无法立即看到 **信息治理** 解决方案？ 首先选择“**全部显示**”。 

2. 按照提示创建保留标签。 请注意你选择的名称，因为在保存标签后无法更改此名称。
    
    有关保留设置的详细信息，请参阅 [用于保留和删除内容的设置](retention-settings.md#settings-for-retaining-and-deleting-content)。

3. 创建标签后，你会看到发布标签、自动应用标签或仅保存标签的选项，请选择“**现在仅保存标签**”，然后选择“**完成**”。

4. 重复这些步骤以创建其他保留设置所需的更多保留标签。

若要编辑现有标签，请将其选中，然后选择“**编辑标签**”选项来启动“编辑保留标签”配置，你将能够更改标签说明和任何符合条件的设置。

创建和保存标签后，大多数设置无法更改，其中包括：
- 保留标签名称和保留期除外。 但是，如果保留期基于项目的标记时间，则不能更改保留期。

## <a name="next-steps"></a>后续步骤

现在，你已创建保留标签，可以通过发布标签或自动应用这些标签将其添加到项目中：
- [发布保留标签并将其应用到应用](create-apply-retention-labels.md)
- [自动向内容应用保留标签](apply-retention-labels-automatically.md)