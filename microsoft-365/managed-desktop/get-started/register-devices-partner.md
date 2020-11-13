---
title: 合作伙伴注册设备的步骤
description: 合作伙伴如何注册设备以便 Microsoft 托管桌面可以管理它们
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 7e40a5eb7144fef3d330e0e8fc3c711af15d4c49
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071439"
---
# <a name="steps-for-partners-to-register-devices"></a>合作伙伴注册设备的步骤


本主题介绍了合作伙伴在注册设备时应遵循的步骤。 您自己注册设备的过程记录在 [Microsoft 托管桌面的注册设备](register-devices-self.md)中。



## <a name="prepare-for-registration"></a>准备注册 
在完成客户注册之前，必须首先在 [合作伙伴中心](https://partner.microsoft.com/dashboard)建立与它们的关系。 有关该过程的更多详细信息，请参阅 [许可文档](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) 。 任何 CSP 合作伙伴都可以代表任何客户添加设备，只要客户同意。 您还可以在 [合作伙伴中心帮助](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot)中了解有关合作伙伴关系和 Autopilot 权限的详细信息。


> [!NOTE]
> 本文档仅适用于合作伙伴和 Oem。 自行注册的过程在 [Microsoft 托管桌面的注册设备](register-devices-self.md)中进行了记录。


## <a name="register-devices-by-using-partner-center"></a>使用合作伙伴中心注册设备

建立与客户的关系后，您可以通过执行以下步骤，利用合作伙伴中心将设备添加到与您有关系的任何客户的 Autopilot 中。

1. 导航到 "[合作伙伴中心](https://partner.microsoft.com/dashboard)"
2. 从 "合作伙伴中心" 菜单中选择 " **客户** "，然后选择要管理其设备的客户。
3. 在客户的详细信息页上，选择 " **设备** "。
4. 在 " **将配置文件应用** 到设备" 下，选择 " **添加设备** "。
5. 输入组名称 **Microsoft365Managed_Autopilot** ，然后选择 " **浏览** " 将客户列表 (以 .csv 文件格式上传) 到合作伙伴中心。


> [!IMPORTANT]
> 组名称必须完全匹配 **Microsoft365Managed_Autopilot** ，包括大小写和特殊字符。 这将允许将新注册的设备分配给 Microsoft 托管桌面 Autopilot 配置文件。

>[!NOTE]
> 你应该已收到此 .csv 文件并购买了你的设备。 如果您没有收到 .csv 文件，则可以按照 [向 Windows Autopilot 中添加设备](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)中的步骤创建一个。 Windows PowerShell 脚本与用于 [Microsoft 托管桌面管理门户](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash)的脚本不同。 合作伙伴应使用 [g-et-windowsautopilotinfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) 在合作伙伴中心为 Microsoft 托管桌面设备注册设备。

如果在尝试上载 .csv 文件时收到错误消息，请检查该文件的格式。 请确保列顺序与在 [新设备上使用 Windows Autopilot 配置文件中描述的内容相匹配，以自定义客户的全新体验](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)。 您还可以使用 " **添加设备** " 下的链接中提供的示例 .csv 文件来创建设备列表。 

有关合作伙伴应用场景中的 Autopilot 的详细信息，请参阅 [将设备添加到客户的帐户](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)。


## <a name="register-devices-by-using-the-oem-api"></a>使用 OEM API 注册设备

在完成客户注册之前，必须首先建立与他们的关系。 你应具有可向你的各个客户提供的唯一链接。 请参阅 [如何建立 OEM 关系](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization)。

建立关系后，即可开始使用 Group 标记 **Microsoft365Managed_Autopilot** 为客户注册设备。

> [!IMPORTANT]
> 组名称必须完全匹配 **Microsoft365Managed_Autopilot** ，包括大小写和特殊字符。 这将允许将新注册的设备分配给 Microsoft 托管桌面 Autopilot 配置文件。
