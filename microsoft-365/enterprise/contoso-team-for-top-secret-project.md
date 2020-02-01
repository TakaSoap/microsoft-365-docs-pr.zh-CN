---
title: Contoso Corporation 的最高机密项目团队
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 摘要： Contoso 如何为首要项目的高管控数据使用团队开发一套新的产品和服务。
ms.openlocfilehash: 794fb5cfb6f3011724d37a6a3c42c39dacacc270
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597069"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a>Contoso Corporation 的最高机密项目团队

在执行异地异地工作时，Contoso 首席执行官订购了一系列新产品和服务，在接下来的五年中，这可能会导致 Contoso 的利润加倍。 开发业务、工程和市场计划的首要项目称为**Project 2x** ，而整个公司的主要员工均为 recruited。 

用于研究和开发的时间线是紧密的，这意味着协作必须高效，并提供安全会议、持续会话和文件存储。

项目2的结果可交付项是商业计划、产品和工程规范，以及 Word、Excel 和 PowerPoint 文件的格式的营销材料和计划。 

由于其敏感性，对这些文件的访问权限为：

- 限制为 Project 2X 工作组成员。
- 使用数据丢失防护（DLP）策略进行保护，以防止 Project 2X 工作组成员在团队外共享这些成员。
- 使用权限进行加密和保护，仅允许访问 Project 2X 团队成员，即使这些文件是在 Contoso 之外分发的也是如此。

Contoso IT 员工将团队用于项目2X 和这些步骤的[高管控数据](secure-teams-highly-regulated-data-scenario.md)。

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a>步骤1：创建了一个私有团队并锁定了基础 SharePoint 网站

若要保护对团队的基础 SharePoint 网站的访问，Contoso IT 管理员配置了[建议的 SharePoint 访问策略](sharepoint-file-access-policies.md)。

接下来，Contoso IT 管理员创建了一个名为 Project 2 的新私人团队，并将 Project 2X 员工的用户帐户添加为成员。

接下来，他们为网站配置了其他权限设置，以防止 Project 2 共享对网站的访问权限，并阻止其他人请求访问网站。

有关配置的详细信息，请参阅[适用于高度管控团队的 SharePoint 设置](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams)。

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a>步骤2：为保留标签配置了 DLP 策略和基础网站 

首先，Contoso 管理员将现有的**高度机密**Office 365 保留标签应用于项目2组基础 SharePoint 网站的 "**文档**" 部分。

接下来，他们创建了一个名为**Project 2x**的新 OFFICE 365 DLP 策略，其中：

- 使用 "高度机密" Office 365 保留标签。
- 当用户尝试在 Contoso 之外的 Project 2X 工作组中共享文件时，会阻止用户。

有关配置的详细信息，请参阅[使用保留标签和 DLP 保护团队中的文件](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp)。

## <a name="step-3-created-an-office-365-sensitivity-label-for-the-project-2x-team"></a>步骤3：为项目2团队创建 Office 365 灵敏度标签

Contoso admins 创建了一个名为**Project 2x**的新 Office 365 敏感度标签，其类型为：

- 需要加密。
- 允许 "Project 2X Office 365" 组的 "共同创作" 权限。

下面是项目2组的结果配置。

![项目2组的结果配置](./media/contoso-team-for-highly-confidential-assets/final-config.png)
 
受以下条件保护的基础 Project 2X SharePoint 网站的 "文档" 部分中的文件：

- 网站权限，仅允许访问 Project 2X Office 365 组的成员。
- 高度机密的保留标签，将自动分配给新文件。
- 一种 DLP 策略，它使用阻止文件与外部用户共享的高度机密保留标签和设置。
- Project 2-2 敏感度标签，带有文件移动或复制到网站时携带的加密和权限。

下面的示例展示了存储在基础项目2X 网站中的文件，该文件具有高度管控的保留标签和分配的 Project 2/2 敏感度标签。

![存储在基础项目2X 网站中的文件的示例](./media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a>步骤4：训练有素的项目2组成员

Contoso 安全员工在强制性课程中培训了 Project 2X 团队成员，其中包括：

- 如何：访问新的 Project 2X 团队、使用会议和聊天以及如何在团队文件中进行协作。
- 如何：在团队中创建新文件并上载本地创建的新文件。
- 有关 DLP 策略如何阻止在外部共享文件的演示。
- 如何使用 Project 2X 敏感度标签标记文件。
- 演示 Project 2X 标签如何保护文件（即使是在离开团队时）。

最终结果是一个安全的环境，在此环境中，Project 2X 团队成员在安全环境中共同参与聊天、会议和文件。

在几个实例中，Project 2X 工作组成员将受 Project 2X 标签保护的文件下载到本地驱动器以供脱机工作。 但是，在打开凭据后收到凭据提示时，他们会意识到它们的错误并将其删除。

由于团队的协作环境和 Microsoft 365 的安全功能，project 2X 的详细信息在项目的持续时间内保持秘密。 Contoso 宣布了其计划，正在将新产品和服务推出给其客户和投资者的欣喜及其竞争对手的 chagrin 的过程。

## <a name="next-step"></a>后续步骤

[部署](deploy-microsoft-365-enterprise.md)组织中的 Microsoft 365 企业。

## <a name="see-also"></a>另请参阅

[Microsoft 365 工作效率库](https://aka.ms/productivitylibrary) https://aka.ms/productivitylibrary)
