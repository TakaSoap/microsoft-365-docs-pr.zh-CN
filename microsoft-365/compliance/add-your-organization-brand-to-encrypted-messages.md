---
title: 将组织品牌添加到加密邮件中
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
- admindeeplinkMAC
description: 了解Office 365管理员如何将组织的品牌应用于加密电子邮件&加密门户的内容。
ms.openlocfilehash: 063a46c94578cbd3cd01184d25086d5246da3fa8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195769"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a>向企业邮件加密加密邮件Microsoft 365组织品牌

你可以应用公司品牌来自定义组织的电子邮件和加密门户的外观。 你需要将全局管理员权限应用于工作或学校帐户，然后才能开始操作。 拥有这些权限后，使用 Get-OMEConfiguration 和 Set-OMEConfiguration Windows PowerShell cmdlet 自定义加密电子邮件的以下部分：
  
- 介绍性文本

- 免责声明文本

- 组织隐私声明的 URL

- OME 门户中的文本

- 显示在电子邮件和 OME 门户中的徽标，或者是否使用徽标

- 电子邮件和 OME 门户中的背景颜色

您也可以随时还原到默认的外观。

如果要进行更多控制，Office 365 高级邮件加密为来自组织的加密电子邮件创建多个模板。 使用这些模板来控制最终用户体验的某些部分。 例如，指定收件人是否可以使用 Google、Yahoo 和 Microsoft 帐户登录加密门户。 使用模板实现多个用例，例如：

- 各个部门，如财务、销售等。

- 不同产品

- 不同的地理区域或国家

- 是否允许吊销电子邮件

- 是否希望发送给外部收件人的电子邮件在指定的天数后过期。

创建模板后，可以使用自定义邮件流规则将其应用于加密Exchange电子邮件。 如果已Office 365 高级邮件加密，可以撤消使用这些模板打造品牌的任何电子邮件。

## <a name="work-with-ome-branding-templates"></a>使用 OME 品牌模板

可以在品牌模板中修改多个功能。 可以修改但不能删除默认模板。 如果您具有高级邮件加密，则还可以创建、修改和删除自定义模板。 使用Windows PowerShell一次使用一个品牌模板。

- [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - 修改默认品牌模板或您创建的自定义品牌模板。
- [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - 创建新的品牌模板，仅高级邮件加密。
- [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - 删除自定义品牌模板，仅高级邮件加密。 不能删除默认品牌模板。
  
## <a name="modify-an-ome-branding-template"></a>修改 OME 品牌模板

使用Windows PowerShell一次修改一个品牌模板。 如果您具有高级邮件加密，则还可以创建、修改和删除自定义模板。

1. 使用在组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 按照 [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) 中所述使用 Set-OMEConfiguration cmdlet，或使用以下图形和表作为指导。

![可自定义的电子邮件部件。](../media/ome-template-breakout.png)

|**自定义加密体验的这一功能**|**使用这些命令**|
|:-----|:-----|
|背景色|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> 有关背景颜色详细信息， [请参阅本文稍后](#background-color-reference) 介绍的"背景颜色"部分。|
|徽标|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 支持的文件格式：.png、.jpg、.bmp 或 .tiff  <br/> 徽标文件的最佳大小：小于 40 KB  <br/> 徽标图像的最佳大小：170x70 像素。 如果图像超过这些尺寸，服务会调整徽标大小，以在门户中显示。 该服务不会修改图形文件本身。 为了获得最佳结果，请使用最佳大小。|
|发件人姓名和电子邮件地址旁边的文本|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|"阅读邮件"按钮上显示的文本|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|显示在"阅读邮件"按钮下方的文本|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|隐私声明链接的 URL|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|包含加密邮件的电子邮件中的免责声明|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|显示在加密邮件查看门户顶部的文本|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|为此自定义模板启用或禁用一次传递代码的身份验证|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> **示例：** <br/>为此自定义模板启用一次密码 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> 为此自定义模板禁用一次密码 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|为此自定义模板启用或禁用 Microsoft、Google 或 Yahoo 标识的身份验证|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> **示例：** <br/>为此自定义模板启用社交 ID <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> 为此自定义模板禁用社交 ID <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>使用高级邮件加密 (OME 品牌模板) 

如果已Office 365 高级邮件加密，可以使用[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet 为组织创建自定义品牌模板。 创建模板后，使用 Set-OMEConfiguration cmdlet 修改模板，如修改 [OME 品牌模板 中所述](#modify-an-ome-branding-template)。 可以创建多个模板。

创建新的自定义品牌模板：

1. 使用在组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 使用 [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet 创建新模板。

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   例如，

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>将默认品牌模板返回到其原始值

若要从默认模板中删除所有修改（包括品牌自定义等），请完成以下步骤：
  
1. 使用在组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 使用 **Set-OMEConfiguration** cmdlet，如 [Set-OMEConfiguration 中所述](/powershell/module/exchange/Set-OMEConfiguration)。 若要从 DisclaimerText、EmailText 和 PortalText 值中删除组织的品牌自定义，请将其值设置为空字符串 `""` 。 对于所有图像值（如徽标），将值设置为  `"$null"` 。

   下表介绍了加密自定义选项默认值。

   |将加密体验的此功能还原到默认的文本和图片|使用这些命令|
   |:-----|:-----|
   |加密电子邮件随附的默认文本。  默认文本显示在说明的上方，以查看加密邮件|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |包含加密邮件的电子邮件中的免责声明|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |显示在加密邮件查看门户顶部的文本|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> **还原为默认值的示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |徽标|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> **还原为默认值的示例：** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |背景色|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> **还原为默认值的示例：** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>使用高级邮件加密 (自定义品牌模板) 

你只能删除你创建的品牌模板。 不能删除默认品牌模板。

若要删除自定义品牌模板：
  
1. 使用在组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 使用 **Remove-OMEConfiguration** cmdlet，如下所示：

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   例如，

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   有关详细信息，请参阅 [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration)。

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>创建Exchange自定义品牌应用于加密电子邮件的自定义邮件流规则

> [!IMPORTANT]
> 扫描和修改邮件的第三方应用程序可能会阻止正确应用 OME 品牌。

修改默认模板或创建新的品牌模板后，可以创建 Exchange 邮件流规则，以根据特定条件应用自定义品牌。 在下列情况下，此类规则将应用自定义品牌：

- 如果电子邮件是由最终用户使用 Outlook 或 Outlook 网页版手动加密的，则Outlook Web App

- 如果电子邮件是由邮件流规则或数据丢失Exchange自动加密的

若要了解如何创建应用加密Exchange邮件流规则，请参阅定义邮件流规则以加密电子邮件[Office 365。](define-mail-flow-rules-to-encrypt-email.md)

1. 在 Web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户登录[Office 365。](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. 选择" **管理"** 磁贴。

3. In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心，</a>choose **Admin centers** \> **Exchange**.

4. 在 EAC 中，**转到"邮件** 流 \> ""规则"，然后选择 **"新建"** ![ 图标。](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \>**创建新规则**。 有关使用 EAC 的信息，请参阅 Exchange[中的管理Exchange Online。](/exchange/exchange-admin-center)

5. 在 **"** 名称"中，键入规则的名称，例如销售部门的品牌。

6. 在 **"应用此规则的条件"** 中，从可用条件列表中选择条件"发件人位于组织内部"和您希望满足的其他条件。 例如，您可能需要将特定品牌模板应用于：

   - 从财务部门成员发送的所有加密电子邮件
   - 使用特定关键字（如"外部"或"合作伙伴"）发送的加密电子邮件
   - 发送到特定域的加密电子邮件

7. From **Do the following，** select **Modify the message security** Apply \> **custom branding to OME messages**. 接下来，从下拉列表中选择品牌模板。

8.  (可选) 您可以配置邮件流规则以应用加密和自定义品牌。 From **Do the following，** select **Modify the message security**， and then choose Apply Office 365 邮件加密 and **rights protection**. 从列表中选择 RMS 模板，选择"保存 **"，** 然后选择"确定 **"。**
  
   模板列表包括默认模板和选项以及您创建的任何自定义模板。 如果列表为空，请确保你已Office 365 邮件加密新功能进行设置。 有关说明，请参阅[设置新的Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。 有关默认模板的信息，请参阅 [配置和管理 Azure 信息保护的模板](/information-protection/deploy-use/configure-policy-templates)。 有关"不要转发 **"选项的信息** ，请参阅电子邮件 [的"不要转发"选项](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。 有关仅加密 **选项** 的信息，请参阅 [加密仅电子邮件选项](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

   如果要 **指定其他** 操作，请选择"添加操作"。

## <a name="background-color-reference"></a>背景色参考

可用于背景色的颜色名称有限。 可以使用十六进制代码值代替颜色名称 (#RRGGBB) 。 可以使用与颜色名称对应的十六进制代码值，或者可以使用自定义的十六进制代码值。 请务必将十六进制代码值括在引号中 (例如 `"#f0f8ff"` ，) 。

下表介绍了可用的背景色名称及其对应的十六进制代码值。

|**颜色名称**|**颜色代码**|
|---|---|
|`aliceblue`|#f0f8ff|
|`antiquewhite`|#faebd7|
|`aqua`|#00ffff|
|`aquamarine`|#7fffd4|
|`azure`|#f0ffff|
|`beige`|#f5f5dc|
|`bisque`|#ffe4c4|
|`black`|#000000|
|`blanchedalmond`|#ffebcd|
|`blue`|#0000ff|
|`blueviolet`|#8a2be2|
|`brown`|#a52a2a|
|`burlywood`|#deb887|
|`cadetblue`|#5f9ea0|
|`chartreuse`|#7fff00|
|`chocolate`|#d2691e|
|`coral`|#ff7f50|
|`cornflowerblue`|#6495ed|
|`cornsilk`|#fff8dc|
|`crimson`|#dc143c|
|`cyan`|#00ffff|
|`darkblue`|#00008b|
|`darkcyan`|#008b8b|
|`darkgoldenrod`|#b8860b|
|`darkgray`|#a9a9a9|
|`darkgreen`|#006400|
|`darkkhaki`|#bdb76b|
|`darkmagenta`|#8b008b|
|`darkolivegreen`|#556b2f|
|`darkorange`|#ff8c00|
|`darkorchid`|#9932cc|
|`darkred`|#8b0000|
|`darksalmon`|#e9967a|
|`darkseagreen`|#8fbc8f|
|`darkslateblue`|#483d8b|
|`darkslategray`|#2f4f4f|
|`darkturquoise`|#00ced1|
|`darkviolet`|#9400d3|
|`deeppink`|#ff1493|
|`deepskyblue`|#00bfff|
|`dimgray`|#696969|
|`dodgerblue`|#1e90ff|
|`firebrick`|#b22222|
|`floralwhite`|#fffaf0|
|`forestgreen`|#228b22|
|`fuchsia`|#ff00ff|
|`gainsboro`|#dcdcdc|
|`ghostwhite`|#f8f8ff|
|`gold`|#ffd700|
|`goldenrod`|#daa520|
|`gray`|#808080|
|`green`|#008000|
|`greenyellow`|#adff2f|
|`honeydew`|#f0fff0|
|`hotpink`|#ff69b4|
|`indianred`|#cd5c5c|
|`indigo`|#4b0082|
|`ivory`|#fffff0|
|`khaki`|#f0e68c|
|`lavender`|#e6e6fa|
|`lavenderblush`|#fff0f5|
|`lawngreen`|#7cfc00|
|`lemonchiffon`|#fffacd|
|`lightblue`|#add8e6|
|`lightcoral`|#f08080|
|`lightcyan`|#e0ffff|
|`lightgoldenrodyellow`|#fafad2|
|`lightgray`|#d3d3d3|
|`lightgrey`|#d3d3d3|
|`lightgreen`|#90ee90|
|`lightpink`|#ffb6c1|
|`lightsalmon`|#ffa07a|
|`lightseagreen`|#20b2aa|
|`lightskyblue`|#87cefa|
|`lightslategray`|#778899|
|`lightsteelblue`|#b0c4de|
|`lightyellow`|#ffffe0|
|`lime`|#00ff00|
|`limegreen`|#32cd32|
|`linen`|#faf0e6|
|`magenta`|#ff00ff|
|`maroon`|#800000|
|`mediumaquamarine`|#66cdaa|
|`mediumblue`|#0000cd|
|`mediumorchid`|#ba55d3|
|`mediumpurple`|#9370db|
|`mediumseagreen`|#3cb371|
|`mediumslateblue`|#7b68ee|
|`mediumspringgreen`|#00fa9a|
|`mediumturquoise`|#48d1cc|
|`mediumvioletred`|#c71585|
|`midnightblue`|#191970|
|`mintcream`|#f5fffa|
|`mistyrose`|#ffe4e1|
|`moccasin`|#ffe4b5|
|`navajowhite`|#ffdead|
|`navy`|#000080|
|`oldlace`|#fdf5e6|
|`olive`|#808000|
|`olivedrab`|#6b8e23|
|`orange`|#ffa500|
|`orangered`|#ff4500|
|`orchid`|#da70d6|
|`palegoldenrod`|#eee8aa|
|`palegreen`|#98fb98|
|`paleturquoise`|#afeeee|
|`palevioletred`|#db7093|
|`papayawhip`|#ffefd5|
|`peachpuff`|#ffdab9|
|`peru`|#cd853f|
|`pink`|#ffc0cb|
|`plum`|#dda0dd|
|`powderblue`|#b0e0e6|
|`purple`|#800080|
|`red`|#ff0000|
|`rosybrown`|#bc8f8f|
|`royalblue`|#4169e1|
|`saddlebrown`|#8b4513|
|`salmon`|#fa8072|
|`sandybrown`|#f4a460|
|`seagreen`|#00ff00|
|`seashell`|#fff5ee|
|`sienna`|#a0522d|
|`silver`|#c0c0c0|
|`skyblue`|#87ceeb|
|`slateblue`|#6a5acd|
|`slategray`|#708090|
|`snow`|#fffafa|
|`springgreen`|#00ff7f|
|`steelblue`|#4682b4|
|`tan`|#d2b48c|
|`teal`|#008080|
|`thistle`|#d8bfd8|
|`tomato`|#ff6347|
|`turquoise`|#40e0d0|
|`violet`|#ee82ee|
|`wheat`|#f5deb3|
|`white`|#ffffff|
|`whitesmoke`|#f5f5f5|
|`yellow`|#ffff00|
|`yellowgreen`|#9acd32|
