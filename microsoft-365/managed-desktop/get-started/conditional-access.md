---
title: 注册后调整设置
description: 如何排除某些 Microsoft 帐户
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 86e2645891afef2523fb8dc80ec0d9a59b094fc4
ms.sourcegitcommit: d4797cfc15c732f1a7ef21e4f944e672a7170f9a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2022
ms.locfileid: "62444529"
---
# <a name="adjust-settings-after-enrollment"></a>注册后调整设置

完成注册后，可能需要Microsoft 托管桌面一些管理设置。 若要检查并根据需要进行调整，请按照以下步骤操作：

1. 查看Microsoft Intune一Azure Active Directory部分中介绍的自定义设置和自定义设置。
2. 如果任何项目适用于您的环境，请根据说明进行调整。
3. 如果要仔细检查所有设置是否正确，可以重新运行准备情况评估工具，以确保不会与Microsoft 托管桌面[](https://aka.ms/mmdart)。

> [!NOTE]
> 由于操作将在几个月后继续，如果在注册 Microsoft Intune、Azure Active Directory 或 Microsoft 365 中的策略后对影响 Microsoft 托管桌面 的策略进行更改，则可能会Microsoft 托管桌面 可能会停止正常运行。 若要避免服务问题，请在更改就绪情况评估工具发现的问题[](../get-ready/readiness-assessment-fix.md)前检查修复工具发现的问题中描述的特定设置，然后再更改它中列出的策略。 您还可以随时重新运行准备情况评估工具。

## <a name="microsoft-intune-settings"></a>Microsoft Intune设置

| 设置 | 说明 |
| ------ | ------ |
| Autopilot 部署配置文件 | 如果你使用任意 Autopilot 策略，请更新每个策略以排除现代 **工作区设备 -所有** Azure AD组。 <br><br> **若要更新 Autopilot 策略，请执行以下操作：** <br><br> 在 **"分配**"下的"已排除"组中，选择"新式 **工作区设备 -** Azure AD注册期间创建的"所有Microsoft 托管桌面组。 <br><br> Microsoft 托管桌面还将创建一个 Autopilot 配置文件，该配置文件的名称将为" (**工作区 Autopilot 配置文件**") 。 更新你自己的 Autopilot 配置文件时，请确保不要从由 Microsoft 托管桌面  创建的现代 **工作区 Autopilot** 配置文件中排除现代工作区设备 -**所有 Azure AD 组**。 |
| 条件访问策略 | 如果在注册 Microsoft 托管桌面 后为 Endpoint 创建与 Azure AD、Microsoft Intune 或 Microsoft 365 Defender 相关的任何新条件访问策略，则从它们Azure AD **"新式工作区** 服务帐户"组。 有关详细信息，请参阅条件 [访问：用户和组](/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。 Microsoft 托管桌面维护单独的条件访问策略来限制访问这些帐户。 <br><br> **若要查看新式Microsoft 托管桌面安全工作站 (访问策略，请执行) ：** <br><br> 转到"Microsoft Endpoint Manager"，然后导航到"**终结点安全性"中的"****条件访问"**。 不要修改由Azure AD"新式工作区"Microsoft 托管桌面创建的任何条件访问策略。 |
| 多重身份验证 | 如果在注册 Microsoft 托管桌面 后在与 endpoint 的 Azure AD、Intune 或 Microsoft 365 Defender 相关的条件访问策略中创建新的多重身份验证要求，请从它们中排除"新式工作区服务 **帐户Azure AD"** 组。 有关详细信息，请参阅条件 [访问：用户和组](/azure/active-directory/conditional-access/concept-conditional-access-users-groups)。 Microsoft 托管桌面维护单独的条件访问策略，以限制对此组的成员的访问。 <br><br> **若要查看Microsoft 托管桌面工作区 - (访问策略，) ：** <br><br> 转到"Microsoft Endpoint Manager"，然后导航到"**终结点安全性"中的"****条件访问"**。
| Windows 10更新圈 | 对于你Windows 10的任何更新圈策略，从每个策略中排除现代工作区设备 **-** Azure AD组。 有关详细信息，请参阅创建 [和分配更新圈](/mem/intune/protect/windows-10-update-rings#create-and-assign-update-rings)。 <br><br> Microsoft 托管桌面还会创建一些更新圈策略，所有这些策略的名称中都将有"现代工作区"。 例如： <ul><li>现代工作区更新策略 [广泛]</li><li>现代工作区更新策略 [快速]</li><li>现代工作区更新策略 [第一]</li><li>现代工作区更新策略 [测试]</li></ul> <br>更新自己的策略时，请确保不要将"现代 **工作区** 设备 -所有Azure AD"组从已创建Microsoft 托管桌面组。 |

## <a name="azure-active-directory-settings"></a>Azure Active Directory设置

自助服务密码重置：如果对所有用户使用自助密码重置，请调整分配以排除Microsoft 托管桌面帐户。

**要调整此分配，请：**

1. 为除Azure AD帐户以外的 *所有用户创建Microsoft 托管桌面* 动态组
1. 将该组用于分配，而不是"所有用户"。

为了帮助您查找和排除服务帐户，下面是可以使用的动态查询示例：

```Console
(user.objectID -ne null) and (user.userPrincipalName -ne "MSADMIN@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSADMININT@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_SOC_RO@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MWAAS_WDGSOC@TENANT.onmicrosoft.com") and (user.userPrincipalName -ne "MSTEST@TENANT.onmicrosoft.com")
```

在此查询中，将 替换为 `@TENANT` 租户域名。

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>开始使用 Microsoft 托管桌面

1. 访问 [管理员门户](access-admin-portal.md)。
1. [在管理门户中添加和验证管理员联系人](add-admin-contacts.md)。
1. 在注册后调整 (本文) 。
1. 部署并分配 [Intune 公司门户](company-portal.md)。
1. [分配许可证](assign-licenses.md)。
1. [部署应用](deploy-apps.md)。
1. [设置设备](set-up-devices.md)。
1. 设置 [使用 Autopilot 和注册状态页的首次运行体验](esp-first-run.md)。
1. [启用用户支持功能](enable-support.md)。
1. [让用户做好使用设备的准备](get-started-devices.md)。
1. [开始使用应用控制](get-started-app-control.md)。
