---
title: 使用保留标签声明记录
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
description: 使用保留标签声明记录。
ms.openlocfilehash: 841c5197addff704016e344ba7ae44355c872f72
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "47817097"
---
# <a name="declare-records-by-using-retention-labels"></a>使用保留标签声明记录

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

若要将文档和电子邮件声明为记录，请使用将项目标记为记录的[保留标签](retention.md#retention-labels)。 你可以发布这些标签，以便用户和管理员可以将其应用于内容，或自动应用这些标签到你想标记为记录的内容。

## <a name="configuring-retention-labels-to-declare-records"></a>配置保留标签以声明记录

创建或配置保留标签时，请选择将项目标记为记录的选项。

>[!NOTE] 
> 从 Microsoft 365 合规中心的“**信息管理**”创建或配置保留标签时，将内容标记为记录的选项不可用。 此时，反而是必须使用“**记录管理**”。

若要创建将内容标记为记录的新保留标签，请执行以下操作：

1. 在 [Microsoft 365 合规中心](https://compliance.microsoft.com)中，转到“**记录管理**”\>“**文件计划**”。 在“文件计划”**** 页面上，选择“创建标签”****。

2. 在向导中的“**定义保留设置**”页面上，选择将项目标记为记录的选项：
    
   ![选择保留设置来将项目标记为记录](../media/recordversioning6.png)

3. 根据需要，将保留标签应用于 SharePoint 或 OneDrive 文档和 Exchange 电子邮件。 有关说明，请参阅以下内容：
    
    - [创建保留标签并在应用中应用它们](create-apply-retention-labels.md)
    
    - [自动向内容应用保留标签](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a>对内容应用已配置保留标签

当用户可对应用中的内容应用将内容标记为记录的保留标签时：

- 对于 Exchange，任何拥有邮箱写入权限的用户均可应用这些标签。 
- 对于 SharePoint 和 OneDrive，默认“成员”组（“参与”权限级别）中的任何用户均可应用这些标签。

使用保留标签标记为记录的文档示例：

![标记为记录的文档的详细信息窗格](../media/recordversioning7.png)

## <a name="next-steps"></a>后续步骤

有关记录管理支持的方案的列表，请参阅[记录管理常见方案](get-started-with-records-management.md#common-scenarios-for-records-management)。
