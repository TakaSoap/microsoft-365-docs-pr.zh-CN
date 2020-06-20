---
title: 将组织品牌添加到加密邮件
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
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
description: 了解 Office 365 全局管理员如何将组织的品牌打造给加密的电子邮件 & 加密门户的内容。
ms.openlocfilehash: 6ec13a9d986019e6eb91d1b7a395f1c6199fe12a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818655"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>在加密的邮件中添加组织的品牌

作为 Exchange Online 或 Exchange Online Protection 管理员，您可以应用公司品牌，以自定义组织的 Microsoft 365 商业邮件加密电子邮件的外观以及加密门户的内容。 通过使用 Set-omeconfiguration 和 Set-omeconfiguration Windows PowerShell cmdlet，您可以自定义加密电子邮件的收件人的查看体验的以下方面：
  
- 包含加密邮件的电子邮件介绍性文本

- 包含加密邮件的电子邮件免责声明文本

- 您的组织的隐私声明的 URL

- 显示在 OME 门户中的文本

- 显示在电子邮件和 OME 门户中的徽标，或者是否使用徽标

- 电子邮件和 OME 门户中的背景色

您也可以随时还原到默认的外观。

如果您想要进行更多控制，可以使用 Office 365 高级邮件加密并为来自您的组织的加密电子邮件创建多个模板。 使用这些模板，不仅可以控制电子邮件的外观，还可以控制最终用户体验的各个部分。 例如，您可以指定应用了此模板的邮件收件人以及使用 Google、Yahoo 和 Microsoft 帐户的用户是否可以使用这些帐户登录到 Office 365 邮件加密门户。 您可以使用模板来实现几个用例，例如：

- 每个部门的模板，如财务、销售等。

- 不同产品的模板

- 不同地理区域或国家/地区的模板

- 是否要允许对电子邮件进行吊销

- 您是否希望发送给外部收件人的电子邮件在指定天数后过期。

创建模板后，可以通过使用 Exchange 邮件流规则将它们应用于加密电子邮件。 如果您具有 Office 365 高级邮件加密，则可以使用这些模板吊销任何已标记的电子邮件。

## <a name="work-with-ome-branding-templates"></a>使用 OME 品牌打造模板

您可以修改品牌模板中的多个功能。 您可以修改但不能删除默认模板。 如果您具有高级邮件加密，则还可以创建、修改和删除自定义模板。 使用 Windows PowerShell 一次处理一个品牌模板。 您需要在组织中具有全局管理员权限的工作或学校帐户使用这些 cmdlet。

- [Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) -修改默认品牌模板或您创建的自定义品牌模板。
- [Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) -创建新的品牌打造模板（仅限高级邮件加密）。
- [Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) -删除自定义品牌打造模板（仅限高级邮件加密）。 您不能删除默认品牌模板。
  
## <a name="modify-an-ome-branding-template"></a>修改 OME 品牌模板

使用 Windows PowerShell 一次修改一个品牌模板。 如果您具有高级邮件加密，则还可以创建、修改和删除自定义模板。

1. 使用组织中具有全局管理员权限的工作或学校帐户，启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](https://aka.ms/exopowershell)。

2. 使用 Set-omeconfiguration cmdlet 修改模板，如[set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration)中所述，或使用下图中所述的图形和表进行指南。

![可自定义的电子邮件部件](../media/ome-template-breakout.png)

|**自定义加密体验的这一功能**|**使用这些命令**|
|:-----|:-----|
|背景色|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> 有关背景颜色的详细信息，请参阅本主题后面的 "[背景色](#background-color-reference)" 一节。|
|徽标|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 支持的文件格式：.png、.jpg、.bmp 或 .tiff  <br/> 徽标文件的最佳大小：小于 40 KB  <br/> 徽标图像的最佳大小：170x70 像素。 如果您的图像超过这些尺寸，服务将调整徽标大小以在门户中显示。 服务不会修改图形文件本身。 为获得最佳效果，请使用最佳大小。|
|发件人姓名和电子邮件地址旁边的文本|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|显示在 "阅读邮件" 按钮上的文本|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|显示在 "阅读邮件" 按钮下方的文本|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|隐私声明链接的 URL|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|包含加密邮件的电子邮件中的免责声明|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|显示在加密邮件查看门户顶部的文本|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|为此自定义模板启用或禁用一次性传递代码的身份验证|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> **示例：** <br/>为此自定义模板启用一次性密码 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> 禁用此自定义模板的一次性密码 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|为此自定义模板启用或禁用与 Microsoft、Google 或 Yahoo 身份的身份验证|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> **示例：** <br/>为此自定义模板启用社交 Id <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> 若要禁用此自定义模板的社交 Id <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>创建 OME 品牌打造模板（高级邮件加密）

如果您具有 Office 365 高级邮件加密，则可以使用[set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) cmdlet 为您的组织创建自定义品牌打造模板。 创建模板后，您可以使用 Set-omeconfiguration cmdlet 修改模板，如[修改 OME 品牌模板](#modify-an-ome-branding-template)中所述。 您可以创建多个模板。

若要创建新的自定义品牌模板：

1. 使用组织中具有全局管理员权限的工作或学校帐户，启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](https://aka.ms/exopowershell)。

2. 使用[set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) cmdlet 可以创建新的模板。

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   For example,

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>将默认品牌模板恢复为其原始值

若要从默认模板中删除所有修改，包括品牌自定义项等，请完成以下步骤：
  
1. 使用组织中具有全局管理员权限的工作或学校帐户，启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](https://aka.ms/exopowershell)。

2. 使用**set-omeconfiguration** cmdlet，如[set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration)中所述。 若要从 DisclaimerText、EmailText 和 PortalText 值中删除您的组织的标记自定义项，请将该值设置为一个空字符串 `""` 。 对于所有图像值（如 "徽标"），请将值设置为 `"$null"` 。

   下表介绍了加密自定义选项的默认设置。

   **将加密体验的此功能还原到默认的文本和图片**|**使用这些命令**|
   |:-----|:-----|
   |加密电子邮件随附的默认文本  <br/> 默认文本显示在说明的上方，以查看加密邮件|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |包含加密邮件的电子邮件中的免责声明|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |显示在加密邮件查看门户顶部的文本|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> **将恢复为默认值的示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |徽标|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> **将恢复为默认值的示例：** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |背景色|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> **将恢复为默认值的示例：** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>删除自定义品牌打造模板（高级邮件加密）

您只能删除或删除您所做的品牌模板。 无法删除默认品牌模板。

若要删除自定义品牌模板，请执行以下操作：
  
1. 使用组织中具有全局管理员权限的工作或学校帐户，启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](https://aka.ms/exopowershell)。

2. 使用**set-omeconfiguration** cmdlet，如下所示：

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   For example,

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   有关详细信息，请参阅[set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration)。

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>创建将自定义品牌打造应用于加密电子邮件的 Exchange 邮件流规则

在修改了默认模板或创建新的品牌打造模板之后，可以创建 Exchange 邮件流规则，以根据特定条件应用自定义品牌打造。 此类规则将在以下情况下应用自定义品牌打造：

- 如果最终用户从 Outlook 或 web 上的 Outlook （以前称为 Outlook Web App）客户端手动加密电子邮件

- 如果电子邮件是由 Exchange 邮件流规则或数据丢失防护策略自动加密的

有关如何创建适用于加密的 Exchange 邮件流规则的信息，请参阅[定义邮件流规则以在 Office 365 中加密电子邮件](define-mail-flow-rules-to-encrypt-email.md)。

1. 在 web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 选择 "**管理**" 磁贴。

3. 在 Microsoft 365 管理中心，选择 "**管理中心**" " \> **Exchange**"。

4. 在 EAC 中，转到 "**邮件流** \> **规则**"，然后选择 "**新建**" ![ 图标 ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **创建新规则**。 有关使用 EAC 的详细信息，请参阅 exchange [Online 中的 exchange 管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 "**名称**" 中，键入规则的名称，例如 "销售部门的品牌"。

6. 在 "在**以下情况应用此规则**" 中，选择**发件人位于组织内部**的条件以及在可用条件列表中所需的其他条件。 例如，您可能希望将特定品牌模板应用于：

   - 从财务部门的成员发送的所有加密电子邮件
   - 使用特定关键字（如 "外部" 或 "合作伙伴"）发送的加密电子邮件
   - 发送到特定域的加密电子邮件

7. 从**执行以下操作**，选择 **"修改邮件安全性**对  >  **OME 邮件应用自定义品牌打造**"。 接下来，从下拉菜单中选择您创建或修改的品牌模板。

8. Optional如果您希望邮件流规则应用除自定义品牌的加密之外的加密，请选择 **"****修改邮件安全性**"，然后选择 "**应用 Office 365 邮件加密和权限保护**"。 从列表中选择一个 RMS 模板，选择 "**保存**"，然后选择 **"确定"**。
  
   模板列表包含所有默认模板和选项，以及您创建的用于 Office 365 的任何自定义模板。 如果列表为空，请确保已使用新功能设置了 Office 365 邮件加密，如[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)中所述。 有关默认模板的信息，请参阅[配置和管理 Azure 信息保护的模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。 有关 "**不要转发**" 选项的信息，请参阅[电子邮件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)的 "不要转发" 选项。 有关**仅加密**选项的信息，请参阅[仅加密电子邮件选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

   如果要指定另一个操作，请选择 "**添加操作**"。

## <a name="background-color-reference"></a>背景色参考

可用于背景色的颜色名称将受到限制。 您可以使用十六进制代码值（#RRGGBB），而不是颜色名称。 您可以使用与颜色名称对应的十六进制代码值，也可以使用自定义十六进制代码值。 请务必将十六进制代码值放在引号中（例如， `"#f0f8ff"` ）。

下表介绍了可用的背景颜色名称及其对应的十六进制代码值。

|||
|---|---|
|**颜色名称**|**颜色代码**|
|aliceblue|#f0f8ff|
|antiquewhite|#faebd7|
|水绿色|#00ffff|
|aquamarine|#7fffd4|
|azure|#f0ffff|
|褐色|#f5f5dc|
|bisque|#ffe4c4|
|black|#000000|
|blanchedalmond|#ffebcd|
|蓝色|#0000ff|
|blueviolet|#8a2be2|
|褐色|#a52a2a|
|burlywood|#deb887|
|cadetblue|#5f9ea0|
|chartreuse|#7fff00|
|光临|#d2691e|
|红色|#ff7f50|
|cornflowerblue|#6495ed|
|cornsilk|#fff8dc|
|crimson|#dc143c|
|浅蓝|#00ffff|
|darkblue|#00008b|
|darkcyan|#008b8b|
|darkgoldenrod|#b8860b|
|darkgray|#a9a9a9|
|darkgreen|#006400|
|darkkhaki|#bdb76b|
|darkmagenta|#8b008b|
|darkolivegreen|#556b2f|
|darkorange|#ff8c00|
|darkorchid|#9932cc|
|darkred|#8b0000|
|darksalmon|#e9967a|
|darkseagreen|#8fbc8f|
|darkslateblue|#483d8b|
|darkslategray|#2f4f4f|
|darkturquoise|#00ced1|
|darkviolet|#9400d3|
|deeppink|#ff1493|
|deepskyblue|#00bfff|
|dimgray|#696969|
|dodgerblue|#1e90ff|
|firebrick|#b22222|
|floralwhite|#fffaf0|
|forestgreen|#228b22|
|紫红色|#ff00ff|
|gainsboro|#dcdcdc|
|ghostwhite|#f8f8ff|
|手指|#ffd700|
|金黄色|#daa520|
|底纹|#808080|
|绿色|#008000|
|greenyellow|#adff2f|
|honeydew|#f0fff0|
|hotpink|#ff69b4|
|indianred|#cd5c5c|
|靛蓝色|#4b0082|
|ivory|#fffff0|
|深褐色|#f0e68c|
|浅|#e6e6fa|
|lavenderblush|#fff0f5|
|lawngreen|#7cfc00|
|lemonchiffon|#fffacd|
|lightblue|#add8e6|
|lightcoral|#f08080|
|lightcyan|#e0ffff|
|lightgoldenrodyellow|#fafad2|
|lightgray|#d3d3d3|
|lightgrey|#d3d3d3|
|lightgreen|#90ee90|
|lightpink|#ffb6c1|
|lightsalmon|#ffa07a|
|lightseagreen|#20b2aa|
|lightskyblue|#87cefa|
|lightslategray|#778899|
|lightsteelblue|#b0c4de|
|lightyellow|#ffffe0|
|橙|#00ff00|
|limegreen|#32cd32|
|linen|#faf0e6|
|紫色|#ff00ff|
|紫红色|#800000|
|mediumaquamarine|#66cdaa|
|mediumblue|#0000cd|
|mediumorchid|#ba55d3|
|mediumpurple|#9370db|
|mediumseagreen|#3cb371|
|mediumslateblue|#7b68ee|
|mediumspringgreen|#00fa9a|
|mediumturquoise|#48d1cc|
|mediumvioletred|#c71585|
|midnightblue|#191970|
|mintcream|#f5fffa|
|mistyrose|#ffe4e1|
|moccasin|#ffe4b5|
|navajowhite|#ffdead|
|海军蓝|#000080|
|oldlace|#fdf5e6|
|色|#808000|
|olivedrab|#6b8e23|
|橙色|#ffa500|
|orangered|#ff4500|
|兰花色|#da70d6|
|palegoldenrod|#eee8aa|
|palegreen|#98fb98|
|paleturquoise|#afeeee|
|palevioletred|#db7093|
|papayawhip|#ffefd5|
|peachpuff|#ffdab9|
|秘鲁|#cd853f|
|粉色|#ffc0cb|
|梅红色|#dda0dd|
|powderblue|#b0e0e6|
|紫色|#800080|
|红色|#ff0000|
|rosybrown|#bc8f8f|
|royalblue|#4169e1|
|saddlebrown|#8b4513|
|橙红|#fa8072|
|sandybrown|#f4a460|
|seagreen|
|seashell|#fff5ee|
|sienna|#a0522d|
|优势|#c0c0c0|
|skyblue|#87ceeb|
|slateblue|#6a5acd|
|slategray|#708090|
|雪|#fffafa|
|springgreen|#00ff7f|
|steelblue|#4682b4|
|tan|#d2b48c|
|深|#008080|
|thistle|#d8bfd8|
|tomato|#ff6347|
|青|#40e0d0|
|色|#ee82ee|
|wheat|#f5deb3|
|white|#ffffff|
|whitesmoke|#f5f5f5|
|黄色|#ffff00|
|yellowgreen|#9acd32|
