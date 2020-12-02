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
ms.openlocfilehash: 76a73372cc7517c3241390e58c28b0b02bffd664
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527693"
---
# <a name="adjust-settings-after-enrollment"></a>注册后调整设置

在 Microsoft 托管桌面中完成注册后，需要调整某些 Microsoft Intune 和 Azure Active Directory (Azure AD) 设置，以允许管理和维护安全性。 设置以下设置以排除包含 Microsoft 托管桌面设备和用户的 Azure AD 组。 有关排除组的步骤，请参阅 [条件访问：用户和组](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups#exclude-users)。

## <a name="microsoft-intune-settings"></a>Microsoft Intune 设置

- Autopilot 部署配置文件：排除 **新式工作区设备-所有**  Azure AD 组。 有关步骤，请参阅 [使用 Windows Autopilot 在 Intune 中注册 Windows 设备](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)。
- 条件访问策略：排除 **新式的 Workplace Service 帐户** Azure AD 组。 有关步骤，请参阅 [条件访问：用户和组](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。
- 多重身份验证：确保需要多重身份验证的任何条件访问策略排除 **新式 Workplace Service 帐户** Azure AD 组。 有关详细信息，请参阅 [条件访问策略](../get-ready/readiness-assessment-fix.md#conditional-access-policies) 和 [条件访问：要求对所有用户进行 MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)。
- 安全基准：排除 **新式工作区设备-所有**  Azure AD 组。 有关步骤，请参阅 [使用安全基准在 Intune 中配置 Windows 10 设备](https://docs.microsoft.com/mem/intune/protect/security-baselines)。
- Windows 10 更新环：排除 **新式工作区设备-所有**  Azure AD 组。 有关步骤，请参阅 [在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。


## <a name="azure-active-directory-settings"></a>Azure Active Directory 设置

自助密码重置：选择 " **选择设置"，然后选择 "** **新式工作区设备-所有** Azure AD 组"。 有关详细信息，请参阅 [教程：使用户能够解锁其帐户或使用 Azure Active Directory 自助服务密码重置重置密码](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)。



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft 托管桌面入门步骤

1. [在管理门户中添加和验证管理员联系人](add-admin-contacts.md)
2.  (本文注册后调整设置) 
3. [分配许可证](assign-licenses.md)
4. [部署 Intune 公司门户](company-portal.md)
5. [启用企业状态漫游](enterprise-state-roaming.md)
6. [设置设备](set-up-devices.md)
7. [让用户做好使用设备的准备](get-started-devices.md)
8. [部署应用](deploy-apps.md)
