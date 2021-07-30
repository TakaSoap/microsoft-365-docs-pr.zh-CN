---
title: 合作伙伴注册设备的步骤
description: 合作伙伴如何注册设备，以便由合作伙伴Microsoft 托管桌面
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 64686f84d8e4cc7dca40a875d8b54508ea9a1fc9
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2021
ms.locfileid: "53648467"
---
# <a name="steps-for-partners-to-register-devices"></a>合作伙伴注册设备的步骤


本文介绍了合作伙伴注册设备要遵循的步骤。 为自己注册设备的过程记录在注册Microsoft 托管桌面[中](register-devices-self.md)。



## <a name="prepare-for-registration"></a>准备注册 
完成客户注册之前，你必须先在合作伙伴中心与它们 [建立关系](https://partner.microsoft.com/dashboard)。 有关 [该过程的更多详细信息](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) ，请参阅许可文档。 只要客户同意，任何云解决方案提供商合作伙伴都可以代表任何客户添加设备。 还可以在合作伙伴中心帮助 中了解有关合作伙伴关系和 Autopilot [权限的更多信息](/partner-center/customers_revoke_admin_privileges#windows-autopilot)。


> [!NOTE]
> 本文档仅适用于合作伙伴和 OEM。 自行注册过程记录在自行注册Microsoft 托管桌面[中](register-devices-self.md)。


## <a name="register-devices-by-using-partner-center"></a>使用合作伙伴中心注册设备

在与客户建立关系后，可以通过执行以下步骤，使用合作伙伴中心为有关系的任何客户将设备添加到 Autopilot：

1. 导航到 [合作伙伴中心](https://partner.microsoft.com/dashboard)
2. 从 **合作伙伴** 中心菜单中选择客户，然后选择你想要管理其设备的客户。
3. 在客户的详细信息页面上，选择 **设备**。
4. 在 **"将配置文件** 应用到设备"下，选择 **"添加设备"。**
5. 为所选的设备配置文件输入相应的组标记 (如下表) 所示，然后选择"浏览"将 .csv) 文件格式的客户列表 (上载到合作伙伴中心。

|[设备配置文件](../service-description/profiles.md)  |组标记  |
|---------|---------|
|敏感数据     |**Microsoft365Managed \_ SensitiveData**    |
|Power user     | **Microsoft365Managed \_ PowerUser**          |
|标准     | **Microsoft365Managed \_ Standard**        |

> [!IMPORTANT]
> 组名称必须与表中列出的名称完全匹配，包括大写和特殊字符。 这将允许新注册的设备与 Autopilot 配置文件Microsoft 托管桌面分配。

>[!NOTE]
> 你应该已经收到此.csv购买的文件。 如果你未收到.csv文件，你可以按照将设备添加到[Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)中的步骤操作Windows文件。 不支持其他列。 不支持引号。 只有 ANSI 格式的文本文件才能用于 unicode (Unicode) 。 标头区分大小写。 由于这些要求，Excel文件并另存为 CSV 文件不会生成可用文件。 请确保在设备序列号中保留任何前导零。 合作伙伴应在合作伙伴中心[使用 Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)为Microsoft 托管桌面设备注册设备。

如果在尝试上载文件时收到.csv错误消息，请检查该文件的格式。 确保列顺序与使用新Windows [Autopilot 配置文件](/partner-center/autopilot#add-devices-to-a-customers-account)自定义客户的全新体验中所述相匹配。 您还可以使用添加设备.csv旁边链接提供的示例文件创建设备列表。  

有关合作伙伴方案中的 Autopilot 详细信息，请参阅 [将设备添加到客户的帐户](/partner-center/autopilot#add-devices-to-a-customers-account)。


## <a name="register-devices-by-using-the-oem-api"></a>使用 OEM API 注册设备

完成客户注册之前，必须先与客户建立关系。 你应该有一个唯一的链接来向各自的客户提供。 请参阅 [如何建立 OEM 关系](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)。

建立关系后，你可以开始为已选择的每个设备配置文件使用相应的组标记为客户注册设备：


|设备配置文件  |组标记  |
|---------|---------|
|敏感数据     | **Microsoft365Managed \_ SensitiveData**     |
|Power user     | **Microsoft365Managed \_ PowerUser**          |
|标准     | **Microsoft365Managed \_ Standard**      |

> [!IMPORTANT]
> 组标记必须与表中列出的标记完全匹配，包括大写字符和特殊字符。 这将允许新注册的设备与 Autopilot 配置文件Microsoft 托管桌面分配。
