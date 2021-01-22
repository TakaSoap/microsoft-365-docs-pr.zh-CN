---
title: 评估 Microsoft 365 Defender
description: 设置 Microsoft 365 Defender 试用实验室或试验环境，以试用并体验旨在保护组织中设备、标识、数据和应用程序的安全解决方案。
keywords: Microsoft 威胁防护试用版， 试用 Microsoft 威胁防护， 评估 Microsoft 威胁防护， Microsoft 威胁防护评估实验室， Microsoft 威胁防护试点， 网络安全， 高级永久性威胁， 企业安全， 设备， 设备， 标识， 用户， 数据， 应用程序， 事件， 自动调查和修正， 高级搜寻
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6735817a71f9fb50843acad3a13596ec247aa407
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930206"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>创建 Microsoft 365 Defender 试用实验室或试验环境 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender


本指南可帮助你使用用户和组设置实验室环境，然后指导你完成 Microsoft 365 Defender 中的功能配置，以便你可以模拟威胁攻击并获取有意义的试验结果。 

创建此试用实验室或试验环境的目的是说明全面且集成的 Microsoft 365 Defender 功能。 体验此智能安全解决方案如何检测、阻止、自动调查和响应组织的高级威胁。 


将指导你完成基于推荐的部署路径启动 Microsoft 365 Defender 评估的步骤。 目标是帮助你使用试用帐户在实验室环境中或在具有完整许可证的生产试验环境中设置安全解决方案。 准备试验实验室或试验环境可以帮助您向贵组织的决策者呈现安全操作用例。 运行完攻击模拟并满意结果后，可以在组织中完全部署和运行它，同时获得 Microsoft 技术销售专业人员或组织中专家的帮助。 

本指南将帮助你：
- 设置实验室服务器和计算机
- 使用用户和组配置 Active Directory
- 设置和配置 Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Endpoint 和 Microsoft Cloud App Security
- 为服务器和计算机设置本地策略
- 模拟威胁攻击以在 Microsoft 365 Defender 中生成测试事件或警报

>[!IMPORTANT]
>为获得最佳结果，请尽可能遵循实验室设置说明。


## <a name="deployment-phases"></a>部署阶段

创建 Microsoft 365 Defender 试用实验室环境有三个阶段。

![部署阶段：准备、设置、载入](../../media/evaluation-guide-phases.png)

|阶段 | 说明 | 
|:-------|:-----|
|[阶段 1：准备](prepare-mtpeval.md)| 了解在试用实验室或试验环境中部署 Microsoft 365 Defender 时需要考虑的问题： <br><br>- 利益干系人并注销 <br> - 环境注意事项 <br>- Access <br>- Azure Active Directory 设置 <br> - 配置顺序
|[阶段 2：设置](setup-mtpeval.md)|  执行初始步骤以访问 Microsoft 365 安全中心，以设置 Microsoft 365 Defender 试用实验室或试验环境。 将指导你：<br><br>- 注册 Microsoft 365 E5 试用版 <br>  - 配置域<br>- 分配 Microsoft 365 E5 许可证<br>- 在门户中完成安装向导|
|[第 3 阶段：配置&载入](config-mtpeval.md) | 配置每个 Microsoft 365 Defender 支柱和载入终结点。 将指导你：<br><br>- 配置 Microsoft Defender for Office 365<br>- 配置 Microsoft Cloud App Security<br>- 为标识配置 Microsoft Defender<br>- 配置适用于终结点的 Microsoft Defender


完成本指南后，你已确定所涉及的利益干系人以及所需的审批，拥有适当的访问权限，注册试用版、配置的域和每个 Microsoft 365 Defender 支柱，你的终结点将载入服务。

## <a name="key-capabilities"></a>主要功能

虽然 Microsoft 365 Defender 提供了许多功能，但此部署指南的主要目的是通过载入设备入门。 除了载入之外，本指南还让你开始使用以下功能。


功能 | 说明 
:---|:---
Microsoft Defender for Office 365 | 帮助保护整个 Office 365 环境免受当前的威胁
Microsoft Defender for Identity | 标识并检测对遭到入侵的身份和恶意内部操作的威胁。
Microsoft Cloud App Security | 提供丰富的可见性、控制数据传输和跨云服务检测网络威胁。
Microsoft Defender for Endpoint | 通过全面的终结点安全性，阻止、检测和提供对高级威胁的响应功能。


## <a name="in-scope"></a>在作用域内

本指南包括以下任务：
-   设置 Azure Active Directory
-   设置 Microsoft 365 Defender
    -   注册 Microsoft 365 E5 试用版，或在运行试点时使用完整许可证
    -   配置域
    -   分配 Microsoft 365 E5 许可证
    -   在门户中完成安装向导
-   根据最佳做法配置所有 Microsoft 365 Defender 支柱
    -   Microsoft Defender for Office 365
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App Security
    -   Microsoft Defender for Endpoint

## <a name="out-of-scope"></a>超出范围

以下超出了此部署指南的范围：

-   可能会与 Microsoft 365 Defender 集成的第三方解决方案的配置
-   生产环境中的渗透测试

## <a name="next-step"></a>后续步骤
[第 1 阶段：准备](prepare-mtpeval.md) 
<br> 准备 Microsoft 365 Defender 试用实验室或试验环境
