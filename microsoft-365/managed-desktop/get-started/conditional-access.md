---
title: 注册后调整设置
description: 如何排除某些 Microsoft 帐户
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e78f0123c909c90ff90be913e8775cc1e5b30313
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777095"
---
# <a name="adjust-settings-after-enrollment"></a>注册后调整设置

完成 Microsoft 托管桌面的注册后，需要调整本文中指定的 Microsoft Intune 和 Azure Active Directory (Azure AD) 设置，以便进行管理和维护安全性。 设置以下设置以排除包含 Microsoft 托管桌面设备和用户的特定 Azure AD 组。 有关排除组的步骤，请参阅条件 [访问：用户和组](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users)。

> [!NOTE]
> 如果在注册 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的策略后做出任何更改，Microsoft 托管桌面可能会停止正常运行。 为避免 Microsoft 托管桌面操作出现问题，请在更改任何策略之前检查[](../get-ready/readiness-assessment-fix.md)修复准备情况评估工具发现的问题中描述的特定设置。


## <a name="microsoft-intune-settings"></a>Microsoft Intune 设置

- Autopilot 部署配置文件：对于由公司中的管理员创建的 Autopilot 配置文件，排除 **现代工作区设备 -所有** Azure AD 组。 有关步骤，请参阅 [使用 Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)在 Intune 中注册 Windows 设备。 不要将 **现代工作区设备 -所有** Azure AD 组从 Microsoft 托管桌面创建的任何部署策略中排除，这些策略的名称为 (例如 **，Modern Workplace Autopilot Profile**) 。 
- 条件访问策略：对于公司中的管理员创建的条件访问策略，排除 **Modern Workplace Service Accounts** Azure AD 组。 有关步骤，请参阅 [条件访问：用户和组](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。 不要将 **现代工作区设备 -所有** Azure AD 组从 Microsoft 托管桌面创建的任何策略中排除，这些策略的名称为 ("新式工作区"，例如， **新式工作区** 安全工作站) 。
- 多重身份验证：确保公司管理员创建的任何需要多重身份验证的条件访问策略都排除 **Modern Workplace Service Accounts** Azure AD 组。 有关详细信息，请参阅条件[访问策略](../get-ready/readiness-assessment-fix.md#conditional-access-policies)和[条件访问：要求所有用户使用 MFA。](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- 安全基线：对于公司中管理员创建的安全基线策略，不包括 **现代工作区设备 -所有**  Azure AD 组。 有关步骤，请参阅 [使用安全基线在 Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)中配置 Windows 10 设备。 不要将现代工作区设备 **-所有** Azure AD 组从 Microsoft 托管桌面创建的任何策略中排除，这些策略的名称为 ("新式工作区安全基线") 。 
- Windows 10 更新圈：对于公司中管理员创建的 Windows 10 更新圈策略，排除 **现代工作区设备 -所有**  Azure AD 组。 有关步骤，请参阅 [在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。 不要将 **现代工作区设备 -所有** Azure AD 组从 Microsoft 托管桌面创建的任何策略中排除，这些策略的名称为 (，例如，新式工作区更新策略) 。


## <a name="azure-active-directory-settings"></a>Azure Active Directory 设置

自助服务密码重置：选择 **"已选择** "设置，然后选择" **现代工作区设备 -所有** Azure AD 组"。 有关详细信息，请参阅 [教程：允许用户使用 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)自助服务密码重置解锁其帐户或重置密码。



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft 托管桌面入门的步骤

1. [在管理门户中添加和验证管理员联系人](add-admin-contacts.md)
2. 在本文 (后调整) 
3. [分配许可证](assign-licenses.md)
4. [部署 Intune 公司门户](company-portal.md)
5. [启用企业状态漫游](enterprise-state-roaming.md)
6. [设置设备](set-up-devices.md)
7. [让用户做好使用设备的准备](get-started-devices.md)
8. [部署应用](deploy-apps.md)
