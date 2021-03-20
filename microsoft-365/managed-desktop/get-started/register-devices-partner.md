---
title: 合作伙伴注册设备的步骤
description: 合作伙伴如何注册设备，以便由 Microsoft 托管桌面管理设备
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: be314b20573cecfdb020caf778e51a684a9b6df8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909066"
---
# <a name="steps-for-partners-to-register-devices"></a>合作伙伴注册设备的步骤


本主题介绍合作伙伴注册设备要遵循的步骤。 为自己注册设备的过程记录在"在 Microsoft 托管桌面中注册设备 ["中](register-devices-self.md)。



## <a name="prepare-for-registration"></a>准备注册 
完成客户注册之前，你必须先在合作伙伴中心与它们 [建立关系](https://partner.microsoft.com/dashboard)。 有关 [该过程的更多详细信息](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) ，请参阅许可文档。 只要客户同意，任何云解决方案提供商合作伙伴都可以代表任何客户添加设备。 还可以在合作伙伴中心帮助 中了解有关合作伙伴关系和 Autopilot [权限的更多信息](/partner-center/customers_revoke_admin_privileges#windows-autopilot)。


> [!NOTE]
> 本文档仅适用于合作伙伴和 OEM。 自行注册的过程记录在自行注册 Microsoft [托管桌面中的设备中](register-devices-self.md)。


## <a name="register-devices-by-using-partner-center"></a>使用合作伙伴中心注册设备

在与客户建立关系后，你可以按照以下步骤利用合作伙伴中心为有关系的任何客户将设备添加到 Autopilot：

1. 导航到 [合作伙伴中心](https://partner.microsoft.com/dashboard)
2. 从 **合作伙伴** 中心菜单中选择客户，然后选择你想要管理其设备的客户。
3. 在客户的详细信息页面上，选择 **设备**。
4. 在 **"将配置文件** 应用到设备"下，选择 **"添加设备"。**
5. Enter **Microsoft365Managed_Autopilot** for the Group Name and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.


> [!IMPORTANT]
> 组名称 **必须完全** Microsoft365Managed_Autopilot，包括大写字符和特殊字符。 这将允许使用 Microsoft 托管桌面 Autopilot 配置文件分配新注册的设备。

>[!NOTE]
> 你应该已使用设备购买收到此 .csv 文件。 如果未收到 .csv 文件，可以按照将设备添加到 Windows Autopilot 中的步骤操作 [，自己创建一个文件](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)。 the Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash). 合作伙伴应在合作伙伴 [中心使用 Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 为 Microsoft 托管桌面设备注册设备。

如果在尝试上载 .csv 文件时收到错误消息，请检查该文件的格式。 确保列顺序与使用新设备的 [Windows Autopilot](/partner-center/autopilot#add-devices-to-a-customers-account)配置文件自定义客户的全新体验中所述相匹配。 您还可以使用添加设备旁边的链接中提供的示例 .csv **文件** 来创建设备列表。 

有关合作伙伴方案中的 Autopilot 详细信息，请参阅 [将设备添加到客户的帐户](/partner-center/autopilot#add-devices-to-a-customers-account)。


## <a name="register-devices-by-using-the-oem-api"></a>使用 OEM API 注册设备

完成客户注册之前，必须先与客户建立关系。 你应该有一个唯一的链接来向各自的客户提供。 请参阅 [如何建立 OEM 关系](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)。

建立关系后，可以使用组标记属性开始为客户注册 **Microsoft365Managed_Autopilot。**

> [!IMPORTANT]
> 组名称 **必须完全** Microsoft365Managed_Autopilot，包括大写字符和特殊字符。 这将允许使用 Microsoft 托管桌面 Autopilot 配置文件分配新注册的设备。