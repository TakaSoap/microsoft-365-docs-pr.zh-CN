---
title: 了解 Microsoft 365 中的信息治理
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
- m365initiative-compliance
description: 了解如何使用 Microsoft 365 来管理组织的数据。
ms.openlocfilehash: c9661aadcef5d70b4099cb44e0fa054ab27e5562
ms.sourcegitcommit: 400ef9ac34247978e3de7ecc0b376c4abb6c99d8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/27/2022
ms.locfileid: "62242145"
---
# <a name="learn-about-information-governance"></a>了解信息治理

>*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

作为 [Microsoft 信息治理](manage-information-governance.md)的一部分，它还包括[记录管理](records-management.md)和[数据连接器](archiving-third-party-data.md)，Microsoft 365 的信息管理为你提供工具和功能来保留需要保留的内容，并删除你不使用的内容。 合规性和法规要求通常需要保留和删除内容，但删除不再具有业务价值的内容也有助于管理风险和责任。 例如，它会减少攻击面。

**保留策略** 是信息治理的基石。 将其用于 Microsoft 365 工作负载，包括 Exchange、SharePoint、OneDrive、Teams、Yammer。 配置这些服务的内容是需要无限期保留，还是在用户编辑或删除时保留特定时段。 或者，可以将策略配置为在指定时间段后自动永久删除内容（如果尚未删除）。 还可以将这两个操作合并为保留，然后删除，这是一个非常典型的配置。 例如，将电子邮件保留三年，然后将其删除。

配置保留策略时，可以将组织中的所有实例（如所有邮箱和所有 SharePoint 网站）或单个实例（例如仅针对特定部门或区域的邮箱或仅选定的 SharePoint 网站）作为目标。

如果需要单个电子邮件或文档的例外，例如法定文档的更长保留期，请使用 **声明标签** 发布到应用，以便用户可以应用它们，或通过检查内容自动应用它们。

若要深入了解保留策略、保留标签以及 Microsoft 365 中保留的工作原理，请参阅[详细了解保留策略和保留标签](retention.md)。 

> [!NOTE]
> 如果需要对高价值项目进行生命周期管理以满足业务、法律或法规上的记录保持要求：将保留标签与[记录管理](records-management.md)（而非信息治理）结合使用。

其他信息管理功能，可帮助你保留所需内容并删除不需要的内容：

- **邮箱存档** 为用户提供额外的邮箱存储空间，并为需要超过 100 GB 存储的邮箱自动扩展存档。 默认存档策略会自动将电子邮件移动到存档邮箱，如果需要，可以自定义此策略。 有关邮箱存档的详细信息，请参阅[了解存档邮箱](archive-mailboxes.md)。
    
- 在员工离开组织后保留邮箱内容的 **非活动邮箱**。 有关非活动邮箱的详细信息，请参阅[了解非活动邮箱](inactive-mailboxes-in-office-365.md)。

- 使用网络上传或驱动器传送 **适用于 PST 文件的导入服务**。 有关详细信息，请参阅[了解如何导入组织的 PST 文件](importing-pst-files-to-office-365.md)。

## <a name="deployment-guidance"></a>部署指南

有关信息治理的部署指南（包括建议的部署路线图、许可信息、权限、支持的方案列表和最终用户文档），请参阅[信息治理入门](get-started-with-information-governance.md)。

正在寻找用于保护数据的部署指南？ 参阅[部署 Microsoft 信息保护解决方案](information-protection-solution.md)。

