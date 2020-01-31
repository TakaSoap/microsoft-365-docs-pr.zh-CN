---
title: 一般数据保护条例
description: 有关一般数据保护条例 (GDPR) 的 Microsoft 技术指南
keywords: Microsoft 365, Microsoft 365 教育版, Microsoft 365 文档, GDPR
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: d64d9b98fe3cf24a14b3f3126ff3f38b1d84087d
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2020
ms.locfileid: "41557979"
---
# <a name="general-data-protection-regulation-summary"></a>一般数据保护条例摘要

一般数据保护条例 (GDPR) 引入了新规定，适用于向欧盟 (EU) 民众提供商品和服务或收集并分析欧盟居民相关数据的组织。无论你或你的企业位于何处，都要遵守该规定。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrOQI] 

本文档指导用户如何在使用 Microsoft 产品和服务时帮助用户根据 GDPR 遵守权限和履行义务。 [适用于 GDPR 的建议操作计划](gdpr-action-plan.md)和[责任就绪清单](gdpr-arc.md)提供用于评估和实施 GDPR 合规性提供了额外资源。

## <a name="terminology"></a>术语

本文档中使用的 GDPR 术语的有用定义：

- *数据控制者（控制者）*：单独或与他人共同确定个人数据处理目的和方法的法人、公共机关、机构或其他团体。  
- *个人数据*和*数据主体*：与已识别或可识别的自然人（数据主体）相关的任何信息；可识别的自然人是可以直接或间接识别的自然人。  
- *处理者*：代表控制者处理个人数据的自然人或法人、公共机关、机构或其他团队。  
- *客户数据*：在运营业务的日常运营中生成和存储的数据。

## <a name="what-is-the-gdpr"></a>什么是 GDPR？

GDPR 授予人们管理组织收集的个人数据的权限。 可通过数据主体请求 (DSR) 来行使这些权限。 组织需要及时提供有关 DSR 和数据泄露的信息，并执行数据保护影响评估 (DPIA)。

在实施或评估 GDPR 要求时应考虑以下几点。

- 制定或评估 GDPR 合规性数据隐私政策。
- 评估组织的数据安全性。
- 谁是数据控制者？
- 你可能需要执行哪些数据安全流程？

[适用于 GDPR 的建议操作计划](gdpr-action-plan.md)和[责任就绪清单](gdpr-arc.md)可能会提示额外的思路。

为满足 GDPR 标准，需要完成以下任务。 请按照列表中的链接获取有关实施的详细信息。  

- **[数据主体请求 (DSR)](gdpr-data-subject-requests.md)**。 数据主体正式要求控制者对其个人数据采取行动（更改、限制、访问）。
- **[违反通知](gdpr-breach-notification.md)**。 根据 GDPR，个人数据泄露是“违反安全规定，导致已传输、存储或以其他方式处理的个人数据意外或非法损毁、丢失、更改，或者未经授权披露或访问。”
- **[数据保护影响评估 (DPIA)](gdpr-data-protection-impact-assessments.md)**。 要求数据控制者按照 GDPR 为‘可能对自然人的权限和自由造成高风险’的数据操作准备 DPIA。

如上所述，GDPR 的建议操作计划和责任就绪清单提供了使用 Microsoft 产品和服务实施或评估 GDPR 一致性的指南。

## <a name="the-gdpr-in-action"></a>现行的 GDPR

本节提供了完成上述 GDPR 任务的大纲和思路。 这些任务的完成情况可能因 Microsoft 配置而异。

### <a name="data-subject-request-dsr"></a>数据主体请求 (DSR)

数据主体请求为数据主体提供了一种根据 GDPR 行使其权限的方法。 控制者负责提供及时的 GDPR 一致回复。 我们将在下面解决你应该考虑的问题。 有关技术详细信息，请参阅[数据主体请求](gdpr-data-subject-requests.md)。  

- **完成 DSR 将需要采取哪些操作？**：DSR 涉及六项活动：发现、访问、校正、限制、导出和删除。
- **数据源是什么？**：组织的很大一部分数据是在 [Office 应用程序](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)（如 Excel 和 Outlook）中生成的。 还可以在 Microsoft 产品和服务生成的[见解](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365)以及[系统生成的日志](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-3-responding-to-dsrs-for-system-generated-logs)中找到与 DSR 相关的数据。
- **需要搜索哪些类型的数据？**：可以在客户数据、Microsoft 产品和服务生成的见解以及系统生成的日志中找到个人数据。
- **如何搜索个人数据？**：搜索个人数据可能因 Microsoft 产品和服务的不同而异。 搜索工具包括[内容搜索](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-the-content-search-ediscovery-tool-to-respond-to-dsrs)或[应用内搜索](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-in-app-functionality-to-respond-to-dsrs)容量。 管理员可以访问与用户活动关联的[系统生成的日志](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-3-responding-to-dsrs-for-system-generated-logs)。  
- **个人数据应以何种格式提供？**：GDPR“数据移植权限”允许数据主体请求“常用的计算机可读结构化格式”个人数据副本，还可请求组织将这些文件传输给另一数据控制者。

### <a name="data-protection-impact-assessment"></a>数据保护影响评估

根据 GDPR，数据控制者需要为“可能对自然人的权限和自由造成高风险’的处理操作准备[数据保护影响评估](gdpr-data-protection-impact-assessments.md) (DPIA)。 Microsoft 产品和服务不需要创建 DPIA。 相反，它取决于 Microsoft 配置的详细信息。

下面给出了有关 DPIA 的一些注意事项。 可在 [DPIA 内容](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia)中找到必须在 Office 中考虑的详细信息列表。

- 组织中的哪些数据活动可能会危及个人数据安全？
- 你对 Microsoft 产品和服务的配置是否容易遭受数据泄露？
- 何时应该执行 DPIA？

    - 控制者需要执行 DPIA 来解决个人数据安全风险或因数据泄露导致的风险。 在[确定是否需要 DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed) 中解决 Office 中风险因素的具体示例。  

- 完成 DPIA 需要执行哪些操作？

    DPIA 包含的 GDPR 要求：  
    - 评估与 DPIA 目的相关的数据处理的必要性和相称性。
    - 评估数据主体的权限和自由风险。
    - 旨在处理风险、保障措施、安全措施和机制的预期措施，以确保保护个人数据并证明其符合 GDPR。

### <a name="breach-notification"></a>违反通知

作为数据处理者，Microsoft 确保客户能够满足 GDPR 的违反通知要求。 数据控制者负责评估数据隐私风险并确定违反是否需要通知客户的 DPA。 Microsoft 提供进行评估所需的信息。 有关 Microsoft 如何检测和响应 [GDPR 下的数据违反通知](gdpr-breach-notification.md)中的违反个人数据的详细信息。 一些违反通知问题包括：

- 应将哪些有关违反的信息传达给数据主体
- 如何与数据主体沟通（电子邮件、书面通知等）？

### <a name="accountability-readiness-checklists-for-the-gdpr"></a>GDPR 的责任就绪清单

这些[清单](gdpr-arc.md)提供了一种方便的方法来访问使用 Microsoft 产品支持 GDPR 所需的信息。 可以使用 [Microsoft 合规性分数](compliance-score.md)来管理清单项目，具体方法是引用 GDPR 磁贴中的“客户托管控制”下的“控制 ID”和“控制标题”。

## <a name="learn-more"></a>了解详细信息

- [Microsoft 信任中心](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
