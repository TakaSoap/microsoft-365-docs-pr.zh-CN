---
title: 评估 Microsoft 威胁防护
description: 设置您的 Microsoft 威胁防护试用实验室或试点环境，以试用旨在保护设备、标识、数据和应用程序的联合威胁防护解决方案如何帮助您的组织
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 3768937fc882fee8d6a744e4fb504095882c7e81
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2020
ms.locfileid: "48368055"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a>创建 Microsoft 威胁防护试用实验室或试点环境 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 威胁防护

创建此试用版实验室或试点环境的目的是说明 Microsoft 威胁防护在您的组织中可使用的检测、预防、调查和响应的全面、集成和智能功能。 

本指南将指导你完成基于建议的部署路径启动 Microsoft 威胁防护评估的步骤。 目标是帮助您在实验室环境中使用试用帐户或在使用完整许可证时在生产中的试点环境中设置集成 Microsoft 威胁防护服务。 在为组织中的安全解决方案决策者提供安全操作使用案例时，这些结果将非常有用。 当您完成攻击模拟并对结果感到满意时，您可以在组织中使用 Microsoft 技术销售专家或专家的帮助，在组织中完全部署和 operationalize 它。 

本指南将帮助您：
- 设置实验室服务器和计算机
- 使用用户和组配置 Active Directory
- 设置和配置 Azure ATP、Office ATP、Microsoft Defender ATP 和 Microsoft 云应用安全性
- 为您的服务器和计算机设置本地策略
- 模拟威胁攻击以在 Microsoft 威胁防护中生成测试事件或警报

>[!IMPORTANT]
>为获得最佳结果，请尽可能严格地遵循实验室设置说明。


## <a name="deployment-phases"></a>部署阶段

创建 Microsoft 威胁防护试用实验室环境并部署它时有三个阶段：

|阶段 | 说明 | 
|:-------|:-----|
| ![第1阶段：准备](../../media/prepare.png)<br>[第1阶段：准备](prepare-mtpeval.md)| 了解在试用实验室或试点环境中部署 Microsoft 威胁防护时需要考虑的事项： <br><br>-利益干系人和签署 <br> -环境注意事项 <br>-Access <br>-Azure Active Directory 安装程序 <br> -配置顺序
|  ![阶段2：安装程序](../../media/setup.png) <br>[阶段2：安装程序](setup-mtpeval.md)|  执行访问 Microsoft 365 安全中心的初始步骤，以设置你的 Microsoft 威胁防护试用实验室或试点环境。 你将指导你执行以下操作：<br><br>-注册 Microsoft 365 E5 试用版 <br>  -配置域<br>-分配 Microsoft 365 E5 许可证<br>-完成门户中的安装向导|
|  ![第3阶段： Configure & 板载](../../media/config-onboard.png) <br>[第3阶段： Configure & 板载](config-mtpeval.md) | 配置每个 Microsoft 威胁防护支柱和板载终结点。 你将指导你执行以下操作：<br><br>-配置 Office 365 高级威胁防护<br>-配置 Microsoft 云应用安全<br>-配置 Azure 高级威胁防护<br>-配置 Microsoft Defender 高级威胁防护 


## <a name="in-scope"></a>在范围内

本指南的作用域中包括以下任务：
-   设置 Azure Active Directory
-   设置 Microsoft 威胁防护
    -   注册 Microsoft 365 E5 试用版，如果你正在运行试点，请使用你的完整许可证
    -   配置域
    -   分配 Microsoft 365 E5 许可证
    -   完成门户中的设置向导
-   根据最佳实践配置所有 Microsoft 威胁防护支柱
    -   Office 365 高级威胁防护
    -   Azure 高级威胁防护
    -   Microsoft Cloud App Security
    -   Microsoft Defender 高级威胁防护

## <a name="out-of-scope"></a>超出范围

以下内容超出了本部署指南的范围：

-   可能与 Microsoft 威胁防护集成的第三方解决方案的配置
-   生产环境中的渗透测试

## <a name="next-step"></a>后续步骤
![第1阶段：准备](../../media/prepare.png) <br>[第1阶段：准备](prepare-mtpeval.md) 
<br> 准备你的 Microsoft 威胁防护试用实验室或试点环境
