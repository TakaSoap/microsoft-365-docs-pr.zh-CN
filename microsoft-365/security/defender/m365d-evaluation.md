---
title: 评估 Microsoft 365 Defender
description: 设置你的Microsoft 365 Defender试验实验室或试验环境，以试用并体验旨在保护组织中设备、标识、数据和应用程序的安全解决方案。
keywords: Microsoft 365 Defender试用版， 试用 Microsoft 365 Defender， 评估 Microsoft 365 Defender， Microsoft 365 Defender 评估实验室， Microsoft 365 Defender 试点， 网络安全， 高级永久性威胁， 企业安全， 设备， 设备， 标识， 用户， 数据， 应用程序， 事件， 自动调查和修正， 高级搜寻
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c260588b80d8325567b74148a7a62586cfbc707
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2021
ms.locfileid: "53457711"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>创建Microsoft 365 Defender试验实验室或试验环境 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender


本指南可帮助你通过用户和组设置实验室环境，然后指导你完成 Microsoft 365 Defender 中的功能配置，以便你可以模拟威胁攻击并获得有意义的试验结果。 

创建此试验实验室或试验环境的目的是说明综合集成Microsoft 365 Defender功能。 体验此智能安全解决方案如何检测、阻止、自动调查和响应组织的高级威胁。 


将指导你完成这些步骤，以根据Microsoft 365 Defender部署路径开始评估。 目标是帮助您使用试用帐户在实验室环境中或在具有完整许可证的生产试验环境中设置安全解决方案。 准备试验实验室或试验环境有助于向贵组织的决策者介绍安全操作用例。 运行完攻击模拟并满意结果后，可以在组织中使用 Microsoft 技术销售专业人员或专家，在组织中全面部署和运行攻击模拟。 

本指南将帮助你：
- 设置实验室服务器和计算机
- 使用用户和组配置 Active Directory
- 设置和配置 Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Endpoint 和 Microsoft Cloud App Security
- 为服务器和计算机设置本地策略
- 模拟威胁攻击以在威胁中生成测试事件或Microsoft 365 Defender

>[!IMPORTANT]
>为了获得最佳结果，请尽可能遵循实验室设置说明。


## <a name="deployment-phases"></a>部署阶段

创建测试实验室环境有三Microsoft 365 Defender阶段。

![部署阶段：准备、设置、载入](../../media/evaluation-guide-phases.png)

|阶段 | 说明 | 
|:-------|:-----|
|[阶段 1：准备](prepare-m365d-eval.md)| 了解在试验实验室或试验环境中部署Microsoft 365 Defender需要考虑哪些内容： <br><br>- 利益干系人与签署 <br> - 环境注意事项 <br>- Access <br>- Azure Active Directory安装程序 <br> - 配置顺序
|[阶段 2：设置](setup-m365deval.md)|  执行初始步骤以访问安全Microsoft 365中心，以设置Microsoft 365 Defender试验实验室或试验环境。 将指导你：<br><br>- 注册Microsoft 365 E5试用版 <br>  - 配置域<br>- 分配Microsoft 365 E5许可证<br>- 在门户中完成安装向导|
|[阶段 3：配置&载入](config-m365d-eval.md) | 配置每个Microsoft 365 Defender和板载终结点。 将指导你：<br><br>- 配置 Microsoft Defender for Office 365<br>- 配置Microsoft Cloud App Security<br>- 为标识配置 Microsoft Defender<br>- 为终结点配置 Microsoft Defender


完成本指南后，你已标识所涉及的利益干系人以及所需的审批、具有正确的访问权限、注册试用、配置的域和每个 Microsoft 365 Defender 支柱，并且你的终结点将载入服务。

## <a name="key-capabilities"></a>关键功能

尽管 Microsoft 365 Defender提供了许多功能，但此部署指南的主要目的是通过载入设备来引导你入门。 除了载入之外，本指南还让你开始使用以下功能。


功能 | 说明 
:---|:---
Microsoft Defender for Office 365 | 帮助保护你的整个Office 365免受当前威胁的威胁
Microsoft Defender for Identity | 标识并检测对遭到入侵的身份和恶意内部操作的威胁。
Microsoft Cloud App Security | 提供丰富的可见性、控制数据传输，并检测云服务中的网络威胁。
Microsoft Defender for Endpoint | 通过全面的终结点安全性来预防、检测和提供对高级威胁的响应功能。


## <a name="in-scope"></a>在作用域内

本指南包括以下任务：
-   设置Azure Active Directory
-   设置Microsoft 365 Defender
    -   注册Microsoft 365 E5试用版，或者如果你正在运行试点，请使用完整许可证
    -   配置域
    -   分配Microsoft 365 E5许可证
    -   在门户中完成安装向导
-   根据Microsoft 365 Defender配置所有功能支柱
    -   Microsoft Defender for Office 365
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App Security
    -   Microsoft Defender for Endpoint

## <a name="out-of-scope"></a>超出范围

以下超出了此部署指南的范围：

-   可能与解决方案集成的第三方解决方案Microsoft 365 Defender
-   生产环境中的渗透测试

## <a name="next-step"></a>下一步
[阶段 1：准备](prepare-m365d-eval.md) 
<br> 准备Microsoft 365 Defender试验实验室或试验环境
