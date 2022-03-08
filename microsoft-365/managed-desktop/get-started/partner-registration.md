---
title: 合作伙伴注册
description: 合作伙伴可以注册由合作伙伴管理Microsoft 托管桌面
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: af1e187c77acde257fa3458709fae50616cf810d
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330724"
---
# <a name="partner-registration"></a>合作伙伴注册

本文介绍了合作伙伴注册设备的步骤。 手动注册中记录了自己注册 [设备的过程](manual-registration.md)。

## <a name="prepare-for-registration"></a>准备注册

完成客户注册之前，你必须先在合作伙伴中心与它们 [建立关系](https://partner.microsoft.com/dashboard)。 有关该过程详细信息，请参阅同意 [文档](/windows/deployment/windows-autopilot/registration-auth#csp-authorization)。 只要客户同意，任何云解决方案提供商合作伙伴都可以代表任何客户添加设备。 还可以在合作伙伴中心帮助中了解有关合作伙伴关系和 Autopilot [权限的更多信息](/partner-center/customers_revoke_admin_privileges#windows-autopilot)。

> [!NOTE]
> 本文档仅适用于合作伙伴和 OEM。 手动注册中记录了自 [注册过程](manual-registration.md)。

## <a name="register-devices-using-the-partner-center"></a>使用合作伙伴中心注册设备

与客户建立关系后，可以使用合作伙伴中心为任意客户将设备添加到 Autopilot。

**若要使用合作伙伴中心注册设备：**

1. 导航到 [合作伙伴中心](https://partner.microsoft.com/dashboard)。
2. 从 **合作伙伴** 中心菜单中选择客户，然后选择你想要管理其设备的客户。
3. 在客户的详细信息页面上，选择 **设备**。
4. 在 **"将配置文件** 应用到设备"下，选择 **"添加设备"**。
5. 为所选的设备配置文件输入相应的组标记 (如下表) 所示，然后选择"浏览"以将 .csv 文件格式的客户列表 (上载到合作伙伴中心) 。

| [设备配置文件](../service-description/profiles.md) | 组标记 |
| ----- | -----|
| 敏感数据 | **Microsoft365ManagedSensitiveData\_** |
| Power user | **Microsoft365ManagedPowerUser\_** |
| Standard | **Microsoft365ManagedStandard\_** |

> [!IMPORTANT]
> 组名称必须与表中列出的名称完全匹配，包括大写和特殊字符。 这将允许新注册的设备与 Autopilot 配置文件Microsoft 托管桌面分配。

>[!NOTE]
> 你应该已经收到此.csv购买的文件。 如果未收到任何.csv文件，可以按照向 [Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell) 添加设备中的步骤Windows文件。 要求： <ul><li>不支持其他列。</li> <li>不支持引号。</li> <li>只有 ANSI 格式的文本文件才能用于 unicode (Unicode) 。</li> <li>标头区分大小写。</li></ul> 由于这些要求，Excel文件并另存为 CSV 文件不会生成可用文件。 请确保在设备序列号中保留任何前导零。 合作伙伴应在合作伙伴中心[使用 Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 为Microsoft 托管桌面设备注册设备。

如果在尝试上载文件时收到.csv错误消息，请检查该文件的格式。 确保列顺序与使用新Windows [Autopilot 配置文件](/partner-center/autopilot#add-devices-to-a-customers-account)自定义客户的全新体验中所述相匹配。 您还可以使用添加.csv旁边的链接提供的示例文件来创建设备列表。

有关合作伙伴方案中的 Autopilot 详细信息，请参阅 [将设备添加到客户帐户](/partner-center/autopilot#add-devices-to-a-customers-account)。

## <a name="register-devices-by-using-the-oem-api"></a>使用 OEM API 注册设备

完成客户注册之前，必须先与客户建立关系。 你应该有一个唯一的链接来向各自的客户提供。 请参阅 [如何建立 OEM 关系](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)。

建立关系后，你可以开始为已选择的每个设备配置文件使用适当的组标记为客户注册设备：

| 设备配置文件 | 组标记 |
| ----- | ----- |
| 敏感数据 | **Microsoft365ManagedSensitiveData\_** |
| Power user | **Microsoft365ManagedPowerUser\_** |
| Standard | **Microsoft365ManagedStandard\_** |

> [!IMPORTANT]
> 组标记必须与表中列出的标记完全匹配，包括大写字符和特殊字符。 这将允许新注册的设备与 Autopilot 配置文件Microsoft 托管桌面分配。
