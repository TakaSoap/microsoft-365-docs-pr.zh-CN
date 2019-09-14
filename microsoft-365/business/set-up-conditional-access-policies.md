---
title: 为 Microsoft 365 活动设置条件访问策略
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何为 Microsoft 365 市场活动设置条件访问策略。
ms.openlocfilehash: 614e3a6e13a14114f40ecf87bf936d4165744503
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982373"
---
# <a name="set-up-conditional-access-policies"></a>设置条件访问策略

[条件访问](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)策略添加 substancial 其他安全性。 Microsoft 提供一组针对所有客户推荐的基准条件访问策略。 基准策略是一组预定义策略，可帮助组织抵御多种常见攻击。 这些常见攻击可能包括密码喷涂、重放和网络钓鱼。

这些策略要求管理员和用户在满足特定条件时输入第二种形式的身份验证（称为 "多重身份验证" 或 "MFA"）。 例如，如果用户从不同的国家/地区登录，则可能会认为登录是危险的，并且用户必须提供另一种形式的身份验证。 

目前，基准策略包括以下各项：
- **需要对管理员进行 MFA** -对最具特权的管理员角色（包括全局管理员）要求进行多重身份验证。
- **最终用户保护**—仅当登录存在风险时，才需要对用户进行多重身份验证。 
- **阻止旧版身份验证**—较旧的客户端应用和一些新的应用程序不使用较新的、更安全的身份验证协议。 这些较旧的应用程序可以绕过条件访问策略，并对您的环境进行未经授权的访问。 此策略阻止来自不支持条件访问的客户端的访问。 
- **需要对服务管理进行 MFA** -需要多重身份验证以访问管理工具，包括 Azure 门户（在其中配置基准策略）。 

Microsoft 建议您启用所有这些基准策略。 启用这些策略后，系统将提示管理员和用户注册 Azure Multii 身份验证。

有关这些策略的详细信息，请参阅[什么是基准策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)？


## <a name="set-up-baseline-policies"></a>设置基准策略

1. 转到 " [azure 门户](https://portal.azure.com)"，然后导航到 " **azure Active Directory** \> **条件访问**"。
    
    页面上列出了基准策略。 <br/> <br/>
    ![列出用于条件访问的基准策略的页面。](media/baslinepolicies.png)
1. 请参阅以下针对每个策略的特定说明：

  - [要求对管理员进行 MFA](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [要求对用户进行 MFA](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [阻止旧版身份验证](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [需要进行服务管理的 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

您可以设置许多其他策略，如要求批准的客户端应用程序。 有关详细信息，请参阅[条件访问文档](https://docs.microsoft.com/azure/active-directory/conditional-access/)。