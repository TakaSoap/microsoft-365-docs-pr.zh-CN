---
title: 了解应用威胁检测和修正
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: 了解应用威胁检测和修正。
ms.openlocfilehash: 90cddc1ffc386a2f691b27e77765a42f46778c82
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60171011"
---
# <a name="learn-about-app-threat-detection-and-remediation"></a>了解应用威胁检测和修正

>*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*

通过 Microsoft 应用治理，你可以：

- 轻松监控内置应用治理检测方法针对恶意应用活动生成的威胁警报，以及你创建的活动应用策略生成的基于策略的警报。 这些警报可以指示应用活动中的异常情况以及何时使用了不合规、恶意或有风险的应用。  你还可以在警报中使用模式来创建新的应用策略，或者修改现有策略的设置以执行更严格的操作。
- 在调查后手动或通过活动应用策略上的操作设置自动修正警报。


>[!Note]
>来自未授予 Microsoft 365 资源访问权限的仅 Azure 应用的异常活动不包括在应用治理检测和警报中。
>

请参阅[管理员角色](app-governance-get-started.md#administrator-roles)，了解哪些角色可以访问应用治理页面。


## <a name="app-governance-integration-with-azure-active-directory-and-microsoft-cloud-app-security"></a>应用治理与 Azure Active Directory 和 Microsoft Cloud App Security 的集成

应用治理、Azure Active Directory (Azure AD) 和 Microsoft Cloud App Security 收集和提供不同的数据集：

- 应用治理提供有关 API 级别应用活动的详细信息。
- Azure AD 提供基础应用元数据和有关登录应用的详细信息。
- Microsoft Cloud App Security 提供应用风险信息。

通过跨应用治理、Azure AD 和 Microsoft Cloud App Security 共享信息，可以在一个门户中显示汇总信息，并轻松链接到另一个门户以获取更多信息。以下是一些示例:

- 应用治理中的应用登录信息：

  从应用治理门户，你可以查看每个应用的聚合登录活动，并链接回 Azure Active Directory 管理中心以获取登录事件的详细信息。

- Microsoft Cloud App Security 门户中的 API 使用信息： 

  从 Microsoft Cloud App Security 门户，你可以查看 API 使用级别和聚合数据传输，并链接到应用治理门户以获取详细信息。

以下是该集成的摘要。

![应用治理与 Azure AD 和 Microsoft Cloud App Security 的集成。](..\media\manage-app-protection-governance\mapg-integration.png)

此外，应用治理会将其警报作为信号发送给 Microsoft Cloud App Security 和 Microsoft 365 Defender，以便对基于应用的安全事件进行更详细的分析。

<!--

CFA #3 Scenario 1:  As an admin, I can investigate alerts associated to my M365 apps through MAPG.
CFA #3 Scenario 2: As an admin, I can manually remediate 
CFA #3 Scenario 3: As an admin, I can configure policies to perform automatic 
--> 

## <a name="next-step"></a>后续步骤

[开始使用应用威胁检测和修正。](app-governance-detect-remediate-get-started.md)
