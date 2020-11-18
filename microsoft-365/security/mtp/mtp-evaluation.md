---
title: 评估 Microsoft 365 Defender
description: 设置 Microsoft 365 Defender 试用版实验室或试点环境，以试用并体验用于保护组织中的设备、标识、数据和应用程序的安全解决方案。
keywords: Microsoft 威胁防护试用版，试用 Microsoft 威胁防护，评估 Microsoft 威胁防护，Microsoft 威胁防护评估实验室，Microsoft 威胁防护试验，网络安全，高级持久威胁，企业安全性，设备，设备，身份，用户，数据，应用程序，事件，自动调查和修正，高级搜寻
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: fe0a06dd104f0f0532363ee046f4bad1c03c5400
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130873"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>创建 Microsoft 365 Defender 试用版实验室或试点环境 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

创建此试用版实验室或试点环境的目的是为了说明全面且集成的 Microsoft 365 Defender 功能。 体验此智能安全解决方案如何检测、阻止、自动调查和响应组织的高级威胁。 

本指南将指导您完成基于建议的部署路径启动 Microsoft 365 Defender 评估的步骤。 目标是帮助您在实验室环境中使用试用帐户设置安全解决方案，或使用完整许可证在生产的试点环境中设置安全解决方案。 准备试用版实验室或试点环境可帮助您在组织中向决策者提供安全操作用例。 当您完成攻击模拟并对结果感到满意时，您可以在组织中使用 Microsoft 技术销售专业人员或专家的帮助，在组织中完全部署和 operationalize 它。 

本指南将帮助您：
- 设置实验室服务器和计算机
- 使用用户和组配置 Active Directory
- 设置和配置 Microsoft Defender for Identity、Microsoft Defender for Office 365、Microsoft Defender for Endpoint 和 Microsoft 云应用安全性
- 为您的服务器和计算机设置本地策略
- 在 Microsoft 365 Defender 中模拟威胁攻击以生成测试事件或警报

>[!IMPORTANT]
>为获得最佳结果，请尽可能严格地遵循实验室设置说明。


## <a name="deployment-phases"></a>部署阶段

创建 Microsoft 365 Defender 试用版环境并部署它时有三个阶段：

![部署阶段：准备、设置、板载](../../media/phase-diagrams/deployment-phases.png)

|阶段 | 说明 | 
|:-------|:-----|
|[第1阶段：准备](prepare-mtpeval.md)| 了解在试用实验室或试点环境中部署 Microsoft 365 Defender 时需要考虑的事项： <br><br>-利益干系人和签署 <br> -环境注意事项 <br>-Access <br>-Azure Active Directory 安装程序 <br> -配置顺序
|[阶段2：安装程序](setup-mtpeval.md)|  执行访问 Microsoft 365 安全中心的初始步骤，以设置你的 Microsoft 365 Defender 试用版实验室或试点环境。 你将指导你执行以下操作：<br><br>-注册 Microsoft 365 E5 试用版 <br>  -配置域<br>-分配 Microsoft 365 E5 许可证<br>-完成门户中的安装向导|
|[第3阶段： Configure & 板载](config-mtpeval.md) | 配置每个 Microsoft 365 Defender 支柱和板载终结点。 你将指导你执行以下操作：<br><br>-配置 Microsoft Defender for Office 365<br>-配置 Microsoft 云应用安全<br>-将 Microsoft Defender 配置为标识<br>-为终结点配置 Microsoft Defender


## <a name="in-scope"></a>在范围内

本指南的作用域中包括以下任务：
-   设置 Azure Active Directory
-   设置 Microsoft 365 Defender
    -   注册 Microsoft 365 E5 试用版，如果你正在运行试点，请使用你的完整许可证
    -   配置域
    -   分配 Microsoft 365 E5 许可证
    -   完成门户中的设置向导
-   根据最佳实践配置所有 Microsoft 365 Defender 支柱
    -   Microsoft Defender for Office 365
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App Security
    -   Microsoft Defender for Endpoint

## <a name="out-of-scope"></a>超出范围

以下内容超出了本部署指南的范围：

-   可能与 Microsoft 365 Defender 集成的第三方解决方案的配置
-   生产环境中的渗透测试

## <a name="next-step"></a>后续步骤
[第1阶段：准备](prepare-mtpeval.md) 
<br> 准备 Microsoft 365 Defender 试用版实验室或试点环境
