---
title: Office 365 邮件加密的旧信息
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 05/22/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解如何为组织将旧文件转换为 Office 365 (OME) OME 加密。
ms.openlocfilehash: 23f287fd01949d710c5cc5c65f0c36c6055d3a57
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688429"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Office 365 邮件加密的旧信息

如果尚未将组织移动到新的 OME 功能，但已部署 OME，则本文中的信息适用于您的组织。 Microsoft 建议在组织合理时制定移动到新 OME 功能的计划。 有关说明，请参阅设置基于 Azure 信息保护构建的新 [Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。 若要详细了解新功能首先如何工作，请参阅 [Office 365 邮件加密](ome.md)。 本文的其余部分将介绍 OME 在发布新 OME 功能之前的行为。
  
借助 Office 365 邮件加密，组织可以在组织内外人员之间发送和接收加密的电子邮件。 Office 365 邮件加密适用于 Outlook.com、Yahoo、Gmail 和其他电子邮件服务。 电子邮件加密有助于确保只有预期收件人才能查看邮件内容。
  
下面是一些示例：
  
- 银行员工将信用卡对帐单发送给客户

- 保险公司代表为客户提供策略详细信息

- 贷款代理从客户请求贷款申请的财务信息

- 医疗保健提供商向患者发送医疗保健信息

- 律师将机密信息发送给客户或其他律师

## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>Office 365 邮件加密在没有新功能的情况下的工作方式

Office 365 邮件加密是一种基于 Microsoft Azure 权限管理或 Azure RMS (的联机) 。 使用 Azure RMS，管理员可以定义邮件流规则以确定加密条件。 例如，规则可以要求对发送给特定收件人的所有邮件进行加密。
  
观看此简短视频，了解 Office 365 邮件加密在没有新功能的情况下的工作方式。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c55540e7-f7f0-42f5-b254-4b2d2fbb1d63?autoplay=false]
  
当某人在 Exchange Online 中发送与加密规则匹配的电子邮件时，该邮件会随 HTML 附件一起发送。 收件人打开 HTML 附件，然后按照说明查看 Office 365 邮件加密门户上的加密邮件。 收件人可以选择通过使用 Microsoft 帐户或与 Office 365 关联的工作或学校登录，或者使用一次通过代码查看邮件。 两个选项均可以确保只有目标收件人可以查看加密邮件。 对于新的 OME 功能，此过程非常不同。
  
下方的图表总结了电子邮件是如何通过加密和解密过程的。
  
![显示加密电子邮件路径的图表](../media/O365-Office365MessageEncryption-Concept.png)
  
有关详细信息，请参阅新 OME 功能发布之前旧版 [Office 365](legacy-information-for-message-encryption.md#LegacyServiceInfo)邮件加密的服务信息。
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>定义不使用新 OME 功能的 Office 365 邮件加密的邮件流规则

若要在没有新功能的情况下启用 Office 365 邮件加密，Exchange Online 和 Exchange Online Protection 管理员定义 Exchange 邮件流规则。 这些规则确定应在哪些条件下加密电子邮件，以及删除邮件加密的条件。 为规则设置加密操作时，该服务在发送邮件之前对符合规则条件的任何邮件执行该操作。

邮件流规则非常灵活，可让你组合条件，以便可以在单个规则中满足特定安全要求。 例如，您可以创建一个规则，对包含特定关键字且发送给外部收件人的所有邮件进行加密。 Office 365 邮件加密还对加密邮件的收件人的回复进行加密；您可以创建一个规则来对这些回复进行解密，为您的电子邮件用户提供方便。 这样，您组织的用户就不需要登录加密门户来查看回复。
  
若要详细了解如何创建 Exchange 邮件流规则，请参阅["定义 Office 365 邮件加密的规则"。](define-mail-flow-rules-to-encrypt-email.md)
  
### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>使用 EAC 创建用于加密电子邮件的邮件流规则，而不使用新的 OME 功能

1. 在 Web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户登录[Office 365。](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. 选择" **管理"** 磁贴。

3. 在 Microsoft 365 管理中心中，选择 **管理中心** \> **Exchange。**

4. 在 EAC 中，转到"**邮件流** \> **规则**"，然后选择 **"新建** ![ "图标 ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **"创建新规则"。** 有关使用 EAC 的信息，请参阅 Exchange Online 中的 [Exchange 管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 **"名称**"中，键入规则的名称，例如加密邮件DrToniRamos@hotmail.com。

6. 在“在以下情况应用此规则”中，选择一个条件，并根据需要输入值。例如，若要加密发送到 DrToniRamos@hotmail.com 的邮件：

   1. 在“在以下情况应用此规则”中，选择“收件人为”。

   2. 从联系人列表中选择一个现有名称，或在“检查名称”框中键入一个新的电子邮件地址。

      - 若要选择一个现有名称，可以从列表中进行选择，然后单击“确定”。

      - 若要输入新名称，请在复选框名称框中键入电子邮件地址，然后选择 **"确定"检查** \> **名称**。

7. 若要添加更多条件，请选择 **"更多选项** "，然后选择 **"添加条件** "，然后从列表中选择。

   例如，若要仅在收件人在组织外部应用规则，请选择"添加条件"，然后选择"收件人在组织外部 **/** 内部 \> **正常** \> "。

8. 若要启用加密而不使用新的 OME 功能，请在"执行以下操作"中，选择"修改邮件安全性 \> **应用以前版本的 OME"，** 然后选择"**保存"。**

   如果您收到 IRM 许可未启用的错误，则表明您没有使用旧版 OME。

9.  (可选) **选择添加操作以** 指定其他操作。

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>使用 Exchange Online PowerShell 创建用于加密电子邮件的邮件流规则，而不使用新的 OME 功能

1. 连接到 Exchange Online PowerShell。 有关详细信息，请参阅[使用远程 PowerShell 连接到 Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

2. 使用 **New-TransportRule** cmdlet 创建规则，将 _ApplyOME_ 参数设置为 `$true` 。

   本示例要求发送到该邮箱的所有DrToniRamos@hotmail.com必须加密。

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   其中：

   - 新规则的唯一名称是"Encrypt rule for Dr Toni Ramos"。
   - _SentTo_ 参数指定由 (电子邮件地址、可分辨名称等标识的邮件) 。 本示例中，收件人由电子邮件地址"DrToniRamos@hotmail.com"标识。
   - _SentToScope_ 参数指定邮件收件人的位置。 本示例中，收件人的邮箱位于 hotmail 中，并且不是组织的一部分，因此使用 `NotInOrganization` 该值。

   有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule)。

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>从加密的电子邮件回复中删除加密，而无需新的 OME 功能

您的电子邮件用户发送加密邮件后，这些邮件的收件人可以使用加密答复回复。 您可以创建邮件流规则，以自动从回复中删除加密，以便您的组织中的电子邮件用户不必登录加密门户来查看它们。 可以使用 EAC 或 Windows PowerShell cmdlet 定义这些规则。 您可以解密从组织内部发送的邮件，或对从组织内部发送的邮件的答复邮件。 无法解密来自组织外部的加密邮件。

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>使用 EAC 创建一个规则，用于从加密的电子邮件回复中删除加密，而无需新的 OME 功能

1. 在 Web 浏览器中，使用已被授予管理员权限的工作或学校帐户登录[Office 365。](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. 选择" **管理"** 磁贴。

3. 在 Microsoft 365 管理中心中，选择 **管理中心** \> **Exchange。**

4. 在 EAC 中，转到"**邮件流** \> **规则**"，然后选择 **"新建** ![ "图标 ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **"创建新规则"。** 有关使用 EAC 的信息，请参阅 Exchange Online 中的 [Exchange 管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 **"名称**"中，键入规则的名称，例如从传入邮件中删除加密。

6. 在 **"应用此规则"中** ，选择应从邮件中删除加密的条件，例如收件人 **位于** \> **组织内部**。

7. 在 **"执行以下操作"** 中，**选择"修改邮件安全性** \> **"删除以前版本的 OME。**

8. 选择“**保存**”。

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>使用 Exchange Online PowerShell 创建一个规则，以从加密的电子邮件回复中删除加密，而无需新的 OME 功能

1. 连接到 Exchange Online PowerShell。 有关详细信息，请参阅[使用远程 PowerShell 连接到 Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

2. 使用 **New-TransportRule** cmdlet 创建规则，将 _RemoveOME_ 参数设置为 `$true` 。

   本示例从发送给组织收件人的所有邮件中删除加密。

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   其中：

   - 新规则的唯一名称是"从传入邮件中删除加密"。
   - _SentToScope_ 参数指定邮件收件人的位置。 此示例使用值 `InOrganization` 值，该值指示下列值之一：
     - 收件人是组织中邮箱、邮件用户、组或已启用邮件的公用文件夹。
     - 收件人的电子邮件地址位于组织中配置为权威域或内部中继域的接受域中，并且邮件已通过身份验证的连接发送或接收。 

有关语法和参数的详细信息，请参阅 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule)。

## <a name="sending-viewing-and-replying-to-messages-encrypted-without-the-new-capabilities"></a>发送、查看和答复未新功能加密的邮件

使用 Office 365 邮件加密，电子邮件根据管理员定义的规则自动加密。 包含加密邮件的电子邮件会通过附加的 HTML 文件到达收件人的收件箱。
  
收件人按照邮件中的说明打开附件，然后使用 Microsoft 帐户或与 Office 365 关联的工作或学校进行身份验证。 如果收件人没有任一帐户，则指示他们创建一个 Microsoft 帐户，以便他们登录以查看加密邮件。 或者，收件人可以选择获取一次传递代码来查看邮件。 登录或使用一次传递代码后，收件人可以查看解密的邮件并发送加密回复。
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>使用 Office 365 邮件加密自定义加密邮件

作为 Exchange Online 和 Exchange Online Protection 管理员，您可以自定义加密的邮件。 例如，您可以添加公司的品牌和徽标，指定简介，并添加加密邮件和收件人查看加密邮件的门户中的免责声明文本。 您可以使用 Windows PowerShell cmdlet 为加密的电子邮件的收件人自定义视觉体验的以下方面：

- 包含加密邮件的电子邮件介绍性文本

- 包含加密邮件的电子邮件免责声明文本

- 显示在邮件查看门户中的门户文本

- 显示在电子邮件和查看门户中的徽标

您也可以随时还原到默认的外观。
  
以下示例显示电子邮件附件中的 ContosoPharma 的自定义徽标：
  
![查看加密消息页面的示例](../media/TA-OME-3attachment2.jpg)
  
**使用组织的品牌自定义加密电子邮件和加密门户**
  
1. 使用远程 PowerShell 连接到 Exchange Online，如使用远程 [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)连接到 Exchange Online 中所述。

2. 使用 Set-OMEConfiguration cmdlet，如下所述 [：Set-OMEConfiguration](https://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b) 或使用下表提供指导。

   **加密自定义选项**

**自定义加密体验的这一功能**|**使用这些 Windows PowerShell 命令**|
|:-----|:-----|
|加密电子邮件随附的默认文本  <br/> 默认文本显示在说明的上方，以查看加密邮件  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **示例：** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"` <br/> |
|包含加密邮件的电子邮件中的免责声明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **示例：** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"` <br/> |
|显示在加密邮件查看门户顶部的文本  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **示例：** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"` <br/> |
|徽标  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **示例：** `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 支持的文件格式：.png、.jpg、.bmp 或 .tiff  <br/> 徽标文件的最佳大小：小于 40 KB  <br/> 徽标图像的最佳大小：170x70 像素  <br/> |

**从加密电子邮件和加密门户中删除品牌自定义**
  
1. 使用远程 PowerShell 连接到 Exchange Online，如使用远程 [PowerShell 连接到 Exchange Online 中所述](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。

2. 使用 Set-OMEConfiguration cmdlet，如下所述 [：Set-OMEConfiguration](https://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b)。 若要从 DisclaimerText、EmailText 和 PortalText 值中删除组织的品牌自定义项，请将其设置为空字符串  `""` 。 对于所有图像值（如徽标），将值设置为  `"$null"` 。

   **加密自定义选项**

|**将加密体验的此功能还原到默认的文本和图片**|**使用这些 Windows PowerShell 命令**|
|:-----|:-----|
|加密电子邮件随附的默认文本  <br/> 默认文本显示在说明的上方，以查看加密邮件  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **示例：** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|包含加密邮件的电子邮件中的免责声明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **示例：** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|显示在加密邮件查看门户顶部的文本  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **恢复为默认值的示例：**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|徽标  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **恢复为默认值的示例：**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |

## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>新 OME 功能发布之前旧版 Office 365 邮件加密的服务信息
<a name="LegacyServiceInfo"> </a>

下表提供了新 OME 功能发布之前 Office 365 邮件加密服务的技术详细信息。
  
|**服务详细信息**|**说明**|
|:-----|:-----|
|客户端设备要求  <br/> |只要 HTML 附件可以在支持窗体发布的现代浏览器中打开，就可以在任何客户端设备上查看加密邮件。  <br/> |
|加密算法和美国联邦信息处理标准 (FIPS) 合规性  <br/> |Office 365 邮件加密使用与 Windows Azure 信息权限管理 (IRM) 相同的加密密钥，并支持加密模式 2（对于 RSA 是 2K 密钥，对于 SHA-1 系统是 256 位密钥）。 有关基础 IRM 加密模式的信息，请参阅 [AD RMS 加密模式](https://technet.microsoft.com/library/hh867439%28WS.10%29.aspx)。  <br/> |
|支持的邮件类型  <br/> |如果是针对那些具有 **IPM.Note** 的邮件类 ID 项，才支持使用 Office 365 邮件加密。 有关详细信息，请参阅 [项目类型和邮件类](https://msdn.microsoft.com/library/office/ff861573.aspx)。  <br/> |
|邮件大小限制  <br/> |Office 365 邮件加密可以加密最多 25 兆字节的邮件。 有关邮件大小限制的更多详细信息，请参阅 [Exchange Online 限制](https://technet.microsoft.com/library/exchange-online-limits.aspx)。  <br/> |
|Exchange Online 电子邮件保留策略  <br/> |Exchange Online 不存储加密的邮件。  <br/> |
|Office 365 邮件加密的语言支持  <br/> | Office 365 邮件加密支持 Microsoft 365 语言，如下所示：  <br/>  传入电子邮件和附加的 HTML 文件根据发件人的语言设置进行本地化。  <br/>  查看门户根据收件人的浏览器设置进行本地化。  <br/>  加密邮件的正文（内容）不进行本地化。  <br/> |
|OME 门户和 OME 查看器应用的隐私信息  <br/> |[Office 365 Messaging Encryption Portal privacy statement](https://privacy.microsoft.com/privacystatement)提供了有关 Microsoft 如何处理您的隐私信息的详细信息。  <br/> |

## <a name="frequently-asked-questions-about-legacy-ome"></a>有关旧 OME 的常见问题
<a name="LegacyServiceInfo"> </a>

对 Office 365 邮件加密有疑问？ 下面对一些问题进行了解答。 如果找不到所需的信息，请查看 [Office 365 的 Microsoft 技术社区论坛](https://techcommunity.microsoft.com/t5/Office-365/ct-p/Office365)。
  
 **问：我的用户向组织外部的收件人发送加密的电子邮件。外部收件人是否必须执行任何操作才能读取和答复使用 Office 365 邮件加密加密的电子邮件？**
  
组织外部接收 Microsoft 365 加密邮件的收件人可以通过两种方式之一查看：
  
- 通过使用 Microsoft 帐户或与 Office 365 关联的工作或学校帐户登录。

- 通过使用一次传递代码。

 **问：Microsoft 365 加密邮件是否存储在云中或 Microsoft 服务器上？**
  
否，加密的邮件保留在收件人的电子邮件系统中，当收件人打开邮件时，会临时发布邮件，以便查看 Microsoft 服务器。 邮件并不存储在其中。
  
 **问：能否使用我的品牌自定义加密电子邮件？**
  
是。 您可以使用 Windows PowerShell cmdlet 自定义显示在加密电子邮件顶部的默认文本、免责声明文本以及要用于电子邮件和加密门户的徽标。 此功能现已在 OMEv2 中提供。 有关详细信息，请参阅["向加密邮件添加品牌"。](add-your-organization-brand-to-encrypted-messages.md)
  
 **问：该服务是否要求我的组织中的每个用户都有许可证？**
  
组织中发送加密电子邮件的每个用户都必须有许可证。
  
 **问：外部收件人是否需要订阅？**
  
否，外部收件人不需要订阅即可阅读或回复加密邮件。
  
 **问：Office 365 邮件加密与权限管理服务与 RMS (之间) ？**
  
RMS 通过提供内置模板（例如：不要转发和公司机密）为组织的内部电子邮件提供信息权限保护功能。 Office 365 邮件加密支持对发送给外部以及内部收件人的邮件进行加密。
  
 **问：Office 365 邮件加密与 S/MIME 如何不同？**
  
S/MIME 实质上是一种客户端加密技术，需要复杂的证书管理和发布基础结构。 Office 365 邮件加密使用邮件流规则 (也称为传输) 规则，不依赖于证书发布。
  
 **问：能否通过移动设备阅读加密邮件？**
  
可以，可以通过从 Google Play 应用商店和 Apple App Store 下载 OME 查看器应用，在 Android 和 iOS 上查看消息。 在 OME 查看器应用中打开 HTML 附件，然后按照说明打开加密邮件。 对于其他移动设备，您可以打开 HTML 附件，只要您的邮件客户端支持表单发布。
  
 **问：是否对回复和转发的邮件进行加密？**
  
是，在整个线程期限内，响应都会继续进行加密。
  
 **问：Office 365 邮件加密是否提供本地化？**
  
传入电子邮件和 HTML 内容会进行本地化，具体取决于发件人电子邮件设置。查看门户根据收件人的浏览器设置进行本地化。不过，加密邮件的实际正文（内容）不会进行本地化。
  
 **问：Office 365 邮件加密使用哪种加密方法？**
  
Office 365 邮件加密使用权限管理服务 (RMS) 作为加密基础结构。 所使用的加密方法取决于从何处获取用来加密和解密邮件的 RMS 密钥。
  
- 如果使用 Microsoft Azure RMS 获取密钥，则使用加密模式 2。 加密模式 2 是更新和增强的 AD RMS 加密实现。 它支持 RSA 2048 签名和加密，并支持 sha-256 签名。

- 如果您使用 Active Directory (AD) RMS 获取这些密钥，则可以使用加密模式 1，也可以使用加密模式 2。使用的方法取决于您的本地 AD RMS 部署。加密模式 1 是原始的 AD RMS 加密实现。它支持 RSA 1024 签名和加密，并支持 sha-1 签名。该模式继续支持 RMS 的所有当前版本。

有关详细信息，请参阅 [AD RMS 加密模式](https://go.microsoft.com/fwlink/p/?LinkId=398616)。
  
**问：为什么有些加密邮件说它们来自Office365@messaging.microsoft.com？**
  
当加密回复从加密门户或通过 OME 查看器应用发送时，发送电子邮件地址将设为 Office365@messaging.microsoft.com，因为该加密邮件是通过 Microsoft 终结点发送的。这有助于防止加密邮件被标记为垃圾邮件。电子邮件上显示的名称和加密门户内的地址不会因为这个标签而更改。此外，该标签仅适用于通过门户而不是通过任何其他电子邮件客户端发送的邮件。
  
 **问：我是 EHE 订阅者 (Exchange) 加密。在哪里可以了解有关升级到 Office 365 邮件加密的信息？**
  
所有 EHE 客户已升级为 Office 365 邮件加密客户。 有关详细信息，请访问 Exchange [托管加密升级中心](https://go.microsoft.com/fwlink/p/?LinkID=511077)。
  
 **问：是否需要打开组织防火墙中任何 URL、IP 地址或端口以支持 Office 365 邮件加密？**
  
是。 您必须将 Exchange Online 的 URL 添加到组织的允许列表中，才能对由 Office 365 邮件加密加密的邮件启用身份验证。 有关 Exchange Online URL 的列表，请参阅 [Microsoft 365 URL 和 IP 地址范围](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)。
  
 **问：我可以向多少个收件人发送 Microsoft 365 加密邮件？**
  
收件人限制为每封邮件 500 个收件人，或在通讯组列表展开后合并时，邮件的"收件人"字段中包含 11，980 个字符，以先发生者为准。 
  
 **问：是否可以取消发送给特定收件人的邮件？**
  
否。 在邮件发送后，无法撤消发送给特定人员的邮件。
  
 **问：是否可以查看已接收和阅读的加密邮件报告吗？**
  
没有显示是否查看过加密邮件的报告，但可以使用 Microsoft 365 报告来确定匹配特定邮件流规则 (也称为传输规则) （例如）的邮件数量。
  
 **问：Microsoft 会如何处理我通过 OME 门户和 OME 查看器应用提供的信息？**
  
[Office 365](https://privacy.microsoft.com/privacystatement)邮件加密门户隐私声明提供有关 Microsoft 对专用信息执行哪些操作和不执行哪些操作的详细信息。

**问：如果我在请求一次传递代码后没有收到该代码，该怎么办？**

首先，检查电子邮件客户端中的垃圾邮件文件夹。 组织的 DKIM 和 DMARC 设置可能会导致这些电子邮件最终被筛选为垃圾邮件。

接下来，在安全与合规中心&隔离。 通常，包含一次传递代码的邮件（尤其是组织收到的第一批邮件）最终被隔离。
