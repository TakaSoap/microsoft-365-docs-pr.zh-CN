---
title: 设置条件访问策略
f1.keywords:
- NOCSH
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
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何要求进行 MFA 并为 Microsoft 365 for business 设置条件访问策略。
ms.openlocfilehash: 3caca685d9a96434a0daa2736c322ac1a68b7feb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635608"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>需要多重身份验证并设置条件访问策略

使用多重身份验证和条件访问策略来保护对数据的访问。 这些都增加了额外的安全性。 Microsoft 提供一组针对所有客户推荐的基准条件访问策略。 基准策略是一组预定义策略，可帮助组织抵御多种常见攻击。 这些常见攻击可能包括密码喷涂、重放和网络钓鱼。

这些策略要求管理员和用户在满足特定条件时输入第二种形式的身份验证（称为多重身份验证或 MFA）。 例如，如果组织中的某个用户尝试从不同的国家/地区或从未知设备登录到 Microsoft 365，则可能会认为该登录是危险的。 用户必须提供另一种形式的身份验证（如指纹或代码）来证明其身份。 

目前，基准策略包括以下各项：
- 在 Microsoft 365 管理中心中设置：
    - **需要对管理员进行 MFA** -对最具特权的管理员角色（包括全局管理员）要求进行多重身份验证。
    - **最终用户保护**—仅当登录存在风险时，才需要对用户进行多重身份验证。 
- 在 Azure Active Directory 门户中设置：
    - **阻止旧版身份验证**—较旧的客户端应用和一些新的应用程序不使用较新的、更安全的身份验证协议。 这些较旧的应用程序可以绕过条件访问策略，并对您的环境进行未经授权的访问。 此策略阻止来自不支持条件访问的客户端的访问。 
    - **需要对服务管理进行 MFA** -需要多重身份验证以访问管理工具，包括 Azure 门户（在其中配置基准策略）。 

Microsoft 建议您启用所有这些基准策略。 启用这些策略后，系统将提示管理员和用户注册 Azure 多重身份验证。

有关这些策略的详细信息，请参阅[什么是基准策略](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)？


## <a name="require-mfa"></a>需要使用 MFA

若要要求所有用户使用第二种 ID 登录，请执行以下操作：

1. 转到管理中心<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> ，并选择 "**设置**"。

2. 在 "安装程序" 页上，选择 "**创建登录更安全**的卡片" 中的 "**查看**"。


    ![制作登录更安全的卡。](../media/setupmfa.png)
3. 在 "使登录更安全" 页上，选择 "**已启动**"。
 
4. 在 "加强登录安全" 窗格中，选中 "**要求对管理员启用多重身份验证**" 旁边的复选框，并**要求用户注册多重身份验证，并在检测到风险时阻止访问**。
    确保在 "**查找用户**" 框中排除了来自 MFA 要求的[紧急](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account)或 "中断玻璃" 管理帐户。
    
    ![增强 "在安全中的安全" 页。](../media/requiremfa.png)

5. 在页面底部选择 "**创建策略**"。

## <a name="set-up-baseline-policies"></a>设置基准策略

1. 转到 " [azure 门户](https://portal.azure.com)"，然后导航到 " **azure Active Directory** \> **条件访问**"。
    
    基准策略在页面上列出，您可以看到，在完成 "[需要 mfa](#require-mfa)" 中的步骤后，"**需要对管理员**和**最终用户**进行 mfa" 功能已启用。

    ![列出用于条件访问的基准策略的页面。](../media/casettings.png)
2. 请参阅以下针对每个策略的特定说明：

    - [要求对管理员进行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
    - [要求对用户进行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [阻止旧版身份验证](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
    - [需要进行服务管理的 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

您可以设置额外的策略，如要求批准的客户端应用程序。 有关详细信息，请参阅[条件访问文档](https://docs.microsoft.com/azure/active-directory/conditional-access/)。
