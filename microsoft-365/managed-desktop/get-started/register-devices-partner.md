---
title: 合作伙伴注册设备的步骤
description: 合作伙伴如何注册设备以便 Microsoft 托管桌面可以管理它们
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: a9a2a0ccb1e0830d674f4b1b1ef5495fafb38ca3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596549"
---
# <a name="steps-for-partners-to-register-devices"></a>合作伙伴注册设备的步骤


本主题介绍了合作伙伴在注册设备时应遵循的步骤。 您自己注册设备的过程记录在[Microsoft 托管桌面的注册设备](register-devices-self.md)中。



## <a name="prepare-for-registration"></a>准备注册 
在完成客户注册之前，必须首先在[合作伙伴中心](https://partner.microsoft.com/dashboard)建立与它们的关系。 请务必选择 "**包括 Azure Active Directory 和 Office 365 的委派管理权限**"。 有关详细信息，请参阅[合作伙伴中心帮助](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)。

若要完成对客户的注册，请首先创建 CSV 文件。

>[!NOTE]
>为方便起见，可以为此*合作伙伴版本*下载一个[示例 CSV 文件](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv)。

您的文件需要包含与示例1（制造商、模型等）**完全相同的列标题**，但您自己的数据用于其他行。 如果使用模板，请在文本编辑工具（如记事本）中打开它，并考虑仅保留第1行中的所有数据，仅在第2行和更低的行中输入数据。 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```




>[!NOTE]
>此格式仅适用于合作伙伴流程。 自行注册的过程在[Microsoft 托管桌面的注册设备](register-devices-self.md)中进行了记录。

>[!IMPORTANT]
>这些值必须与 SMBIOS 中的制造商值完全匹配，包括大小写和特殊字符。 

- 设备制造商（示例： SpiralOrbit） 
- 设备模型（示例： ContosoABC）
- 设备序列号

## <a name="register-devices-by-using-the-azure-portal"></a>使用 Azure 门户注册设备

使用 Azure 门户注册与自助服务相同，不同之处在于，访问门户的方式不同。 请按以下步骤操作：

1. 导航到 "[合作伙伴中心](https://partner.microsoft.com/dashboard)"
2. 选择 "**客户**"。
3. 选择要管理的客户。
4. 选择 "**服务管理**"。
5. 选择 " **Intune**"。
6. 在 Azure 门户的顶部搜索框中搜索 "mmd"。
7. 选择 "**设备**"。
8. 在 "**文件上载**" 中，提供以前创建的 CSV 文件的路径。
9. （可选）可以出于自己的跟踪目的添加**订单 id**或**购买 ID** 。 这些值没有格式要求。
10. 选择 "**注册设备**"。 系统会将设备添加到**设备边栏**上的设备列表中，并标记为 "**注册挂起**"。 注册通常需要不到10分钟的时间，如果成功，设备将显示为 "已**准备就绪**，以供用户使用"，表示它已准备就绪，正在等待最终用户开始使用。


你可以在主**Microsoft 托管台式机-设备**页面上监视设备注册的进度。 可能报告的状态包括：

| 状态 | 说明 |
|---------------|-------------|
| 注册挂起 | 注册尚未完成。 稍后再次查看。 |
| 注册失败 | 无法完成注册。 有关详细信息，请参阅[设备注册故障排除](register-devices-self.md#troubleshooting-device-registration)。 |
| 为用户准备就绪 | 注册成功，现在设备已准备好传递给最终用户。 Microsoft 托管桌面将在首次设置时引导他们，因此无需执行任何进一步的准备。 |
| 活动 | 设备已传递给最终用户，并且已向其注册了你的租户。 这也表明它们是定期使用设备的。 |
| 不再 | 设备已传递给最终用户，并且已向其注册了你的租户。 但是，他们最近未使用设备（最近7天）。  |



## <a name="troubleshooting"></a>故障排除

| 错误消息 | 详细信息 |
|---------------|-------------|
| 找不到设备 | 无法注册此设备，因为我们找不到提供的制造商、型号或序列号的匹配项。 请与设备供应商确认这些值。 |
| 硬件哈希无效 | 为此设备提供的硬件哈希格式不正确。 仔细检查硬件哈希，然后重新提交。 |
| 已注册设备 | 此设备已注册到你的组织。 无需执行进一步操作。 |
| 其他组织声明的设备 | 此设备已由其他组织声明。 请与设备供应商联系。 |
| 意外错误 | 无法自动处理你的请求。 联系支持人员<support link>（）并提供请求 ID：<requestId> |
