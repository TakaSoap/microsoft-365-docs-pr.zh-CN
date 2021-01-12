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
ms.openlocfilehash: 88a832f6c4e17756bfb25ef5cb7c4c5ecedaf2c0
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794384"
---
# <a name="adjust-settings-after-enrollment"></a>注册后调整设置

在 Microsoft 托管桌面中完成注册后，可能需要调整某些管理设置。 若要检查和调整（如果需要），请按照以下步骤操作：

1. 查看下一部分中介绍的 Microsoft Intune 和 Azure Active Directory 设置。
2. 如果任何项目适用于您的环境，请进行所述的调整。
3. 如果要仔细检查所有设置是否正确，可以重新运行准备情况评估工具，以确保没有任何与[](https://aka.ms/mmdart)Microsoft 托管桌面冲突的情况。

> [!NOTE]
> 由于操作将在几个月后继续，如果在 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中注册影响 Microsoft 托管桌面的策略后进行更改，Microsoft 托管桌面可能会停止正常运行。 为避免服务出现问题，请在更改该服务中列出的策略之前，检查"[](../get-ready/readiness-assessment-fix.md)修复准备情况评估工具发现的问题"中所述的特定设置。 您还可以随时重新运行准备情况评估工具。


## <a name="microsoft-intune-settings"></a>Microsoft Intune 设置

- Autopilot 部署配置文件：如果你使用任何 Autopilot 策略，请更新每个策略以排除 **现代工作区设备 -所有** Azure AD 组。 若要更新它们，请在"分配"下的"已排除组"部分中，选择在 Microsoft 托管桌面注册期间创建的新式工作区设备 **-** 所有 Azure AD 组。 Microsoft 托管桌面还将创建 Autopilot 配置文件，其名称将为"新式工作区" (**Modern Workplace Autopilot 配置文件**) 。 更新自己的 Autopilot 配置文件时，请确保不要从Microsoft 托管桌面创建的新式 **工作区 Autopilot** 配置文件中排除新式工作区设备 **-** 所有 Azure AD 组。

- 条件访问策略：对于已创建的条件访问策略，排除 **新式工作区服务帐户** Azure AD 组。 有关步骤，请参阅 [条件访问：用户和组](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。 Microsoft 托管桌面还将创建一些条件访问策略，所有这些策略的名称都将具有"新式工作区" (例如， **新式工作区** 安全工作站) 。 更新自己的条件访问策略时，请确保不要从 Microsoft托管桌面创建的任何策略中排除现代工作区设备 **-** 所有 Azure AD 组。

- 多重身份验证：确保任何需要多重身份验证的条件访问策略都排除 **新式工作区服务帐户** Azure AD 组。 有关详细信息，请参阅条件[访问策略](../get-ready/readiness-assessment-fix.md#conditional-access-policies)和[条件访问：要求所有用户使用 MFA。](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)

- Windows 10 更新圈：对于你创建的任何 Windows 10 更新圈策略，从每个策略中排除 **现代工作区设备 -所有** Azure AD 组。 有关步骤，请参阅["创建并分配更新圈"。](https://docs.microsoft.com/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings) Microsoft 托管桌面还将创建一些更新圈策略，所有更新圈策略的名称为 (例如，现代工作区更新策略 **[广泛]**、 现代工作区更新策略 **[快速]**、 现代工作区更新策略 **[第一]** 和现代工作场所更新策略 **[测试]**) 。 更新自己的策略时，请确保不会将新式工作区设备 **-所有** Azure AD 组从 Microsoft 托管桌面创建的组中排除。


## <a name="azure-active-directory-settings"></a>Azure Active Directory 设置

自助服务密码重置：如果使用所有用户的自助密码重置，请调整分配以排除 Microsoft 托管桌面服务帐户。 若要调整此分配，请为除 *Microsoft* 托管桌面服务帐户以外的所有用户创建 Azure AD 动态组，然后将该组用于分配，而不是"所有用户"。

为了帮助您查找和排除服务帐户，下面是一个可以使用的动态查询示例：

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

在此查询中，将@TENANT替换为租户域名。



## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft 托管桌面入门的步骤

1. [在管理门户中添加和验证管理员联系人](add-admin-contacts.md)
2. 在本文 (后调整) 
3. [分配许可证](assign-licenses.md)
4. [部署 Intune 公司门户](company-portal.md)
5. [启用企业状态漫游](enterprise-state-roaming.md)
6. [设置设备](set-up-devices.md)
7. [让用户做好使用设备的准备](get-started-devices.md)
8. [部署应用](deploy-apps.md)
