---
title: 步骤 7. 将你的Microsoft 365 Defender环境推广到生产环境
description: 使用本文将 MDI、MDO、MDE 和 Defender for Cloud Apps 的系列推广到 Microsoft 365 Defender 或 M365D 中的实时环境。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 47f36d965c9b2b6ef5f106c590e47fe0251163d8
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63323971"
---
# <a name="step-7-promote-your-microsoft-365-defender-evaluation-environment-to-production"></a>步骤 7. 将Microsoft 365 Defender环境推广到生产环境

**适用于：**
- Microsoft 365 Defender

若要将Microsoft 365 Defender环境推广到生产环境，请首先购买必要的许可证。 按照创建 [eval 环境并](eval-create-eval-environment.md)购买 Office 365 E5许可证中的步骤 (而不是选择"开始免费试用") 。

接下来，完成任何其他配置并展开试点组，直到这些试点组进入完全生产阶段。

## <a name="microsoft-defender-for-identity"></a>Microsoft Defender for Identity

Defender for Identity 不需要任何其他配置。 只需确保你已购买必要的许可证，并且在所有 Active Directory 域控制器和 Active Directory 联合身份验证服务 (AD FS 服务器上安装了) 。

## <a name="microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

成功评估或试用 MDO 后，可以提升至整个生产环境。

1. 购买和预配必要的许可证，并将其分配给生产用户。
2. 针对生产电子邮件域或 (用户组重新) 标准或严格策略配置。
3. （可选）针对生产电子邮件域或用户组创建和配置任何自定义 MDO 策略。  但是，请记住，任何分配的基线策略将始终优先于自定义策略。
4. 将生产电子邮件域的公共 MX 记录更新为直接解析为 EOP。
5. 停用任何第三方 SMTP 网关，并禁用或删除与此中继关联的任何 EXO 连接器。

## <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint

若要将 Microsoft Defender for Endpoint 评估环境从试点推广到生产环境，只需使用任何受支持的工具和方法将更多终结点[载入服务。](../defender-endpoint/onboard-configure.md)

使用以下一般准则将更多设备载入到 Microsoft Defender for Endpoint。

1. 验证设备是否满足最低 [要求](../defender-endpoint/minimum-requirements.md)。
2. 根据设备，请按照 Defender for Endpoint 门户的载入部分中提供的配置步骤操作。
3. 为设备使用适当的管理工具和部署方法。
4. 运行检测测试，验证设备是否正确载入并报告给服务。

## <a name="microsoft-defender-for-cloud-apps"></a>Microsoft Defender for Cloud Apps

Microsoft Defender for Cloud Apps 不需要任何其他配置。 只需确保你已购买必要的许可证。 如果将部署范围缩小到某些用户组，请增加这些组的范围，直到达到生产规模。
