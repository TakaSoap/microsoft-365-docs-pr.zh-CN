---
title: 在独立 EOP 中管理邮件用户
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: 了解 Exchange Online Protection (EOP) （包括使用目录同步、EAC 和 PowerShell 管理用户）中的邮件用户。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64b7effadd96b6dc025677139c4303acd538dadb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827071"
---
# <a name="manage-mail-users-in-standalone-eop"></a>在独立 EOP 中管理邮件用户

在没有 Exchange Online 邮箱 (独立的 Exchange Online Protection) 组织上，邮件用户是用户帐户的基本类型。 邮件用户在独立 EOP 组织中拥有帐户凭据，并且可访问资源 (分配) 。 邮件用户的电子邮件地址是外部 (例如，在您的内部部署电子邮件环境中) 。

> [!NOTE]
> 创建邮件用户时，Microsoft 365 管理中心会提供相应的用户帐户。 在 Microsoft 365 管理中心创建用户帐户时，无法使用该帐户来创建邮件用户。

建议的在独立 EOP 中创建和管理邮件用户的方法是使用目录同步，如本主题 [后面的"使用目录同步管理邮件用户](#use-directory-synchronization-to-manage-mail-users) "部分所述。

对于具有少量用户的独立 EOP 组织，您可以在 Exchange 管理中心 (EAC 或独立 EOP PowerShell 中添加) 和管理邮件用户，如本主题中所述。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 要打开 Exchange 管理中心 (EAC) ，请参阅 [在独立 EOP 中部署 Exchange 管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 当您在 EOP PowerShell 中创建邮件用户时，可能会遇到限制。 此外，EOP PowerShell cmdlet 还使用批处理方法，在显示命令结果之前，有几分钟的传播延迟。

- 必须先分配有权限，然后才能执行这些过程。 具体而说，需要"邮件收件人创建 (创建) 和 Mail Recipients (修改) 角色，默认情况下这些角色分配给 OrganizationManagement (全局管理员) 和 RecipientManagement 角色组。 有关详细信息，请参阅独立[EOP 中的"权限](feature-permissions-in-eop.md)["和"使用 EAC 修改角色组中的成员列表"。](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- 若要了解可能适用于此主题中过程的键盘快捷键，请参阅 [Exchange Online 中 Exchange 管理中心的键盘快捷键](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 是否有任何疑问？ 在 Exchange 论坛中寻求帮助。 访问 [Exchange Online Protection 论](https://go.microsoft.com/fwlink/p/?linkId=285351) 坛。

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>使用 Exchange 管理中心管理邮件用户

### <a name="use-the-eac-to-create-mail-users"></a>使用 EAC 创建邮件用户

1. 在 EAC 中， **转到收件人** \> **联系人**

2. 单击 **"新建** ![ "图标 ](../../media/ITPro-EAC-AddIcon.png) 。 在打开 **的"新建** 邮件用户"页中，配置以下设置。 标记有需要的 <sup>\*</sup> 设置。

   - **名**：使用此框可以键入用户的名。

   - **缩**写：人员的中间名首字母。

   - **姓**：使用此框可以键入用户的姓。

   - <sup>\*</sup>**显示名称**：默认情况下，此框显示"名字、**缩写****"和"** 姓氏 **"框中**的值。 可以接受此值或更改该值。 该值应唯一，并且最大长度为 64 个字符。

   - <sup>\*</sup>**别名**：为用户输入唯一别名，最多 64 个字符

   - **外部电子邮件地址**：输入用户的电子邮件地址。 该域应位于基于云的组织外部。

   - <sup>\*</sup>**用户 ID：** 输入用户将用于登录服务的帐户。 用户 ID 由 (@) 符号 (@) 左侧的用户名和右侧的域和右侧的域所包含。

   - <sup>\*</sup>**新密码**和 <sup>\*</sup> **确认密码**：输入并重新输入帐户密码。 验证密码是否符合您组织的密码长度、复杂性和历史要求。

3. 完成后，请单击“保存”**** 来创建邮件用户。

### <a name="use-the-eac-to-modify-mail-users"></a>使用 EAC 修改邮件用户

1. 在 EAC 中，转到"**收件人联系人** \> **"。**

2. 选择要修改的邮件用户，然后单击" **编辑"** ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。

3. 在打开的邮件用户属性页中，单击以下选项卡之一以查看或更改属性。

   完成时，请单击“保存”****。

#### <a name="general"></a>常规

使用" **常规** "选项卡可以查看或更改有关邮件用户的基本信息。

- **名**

- **缩写**

- **姓**

- **显示名称**：此名称将会出现在组织通讯簿中的"收件人："和"发件人："电子邮件和 EAC 的联系人列表中的行。 此姓名不能在显示姓名之前或之后包含空格。

- **用户 ID：** 这是 Microsoft 365 中的用户帐户。 你无法在此处修改该值。

#### <a name="contact-information"></a>联系人信息

使用 **"联系人信息** "选项卡来查看或更改用户联系信息。 该页上的信息显示在通讯簿中。

- **Street**
- **市/县**
- **省/市/自治区**
- **邮政编码**
- **国家/地区**
- **工作电话**
- **移动电话**
- **Fax**
- **更多选项**

  - **Office**
  - **住宅电话**
  - **网页**
  - **备注**

#### <a name="organization"></a>组织

使用 **"** 组织"选项卡可以记录有关组织中用户的角色的详细信息。

- **Title**
- **Department**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>使用 EAC 删除邮件用户

1. 在 EAC 中，转到"**收件人联系人** \> **"。**

2. 选择要删除的邮件用户，然后单击 **"删除"** ![ 图标 ](../../media/ITPro-EAC-RemoveIcon.gif) 。

## <a name="use-powershell-to-manage-mail-users"></a>使用 PowerShell 管理邮件用户

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>使用独立 EOP PowerShell 查看邮件用户

若要返回独立 EOP PowerShell 中所有邮件用户的摘要列表，请运行以下命令：

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

若要查看特定邮件用户的详细信息，请 \<MailUserIdentity\> 将其替换为邮件用户的名称、别名或帐户名，然后运行以下命令：

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

有关语法和参数的详细信息，请参阅[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient)和[Get-User。](https://docs.microsoft.com/powershell/module/exchange/get-user)

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>使用独立 EOP PowerShell 创建邮件用户

若要在独立 EOP PowerShell 中创建邮件用户，请使用以下语法：

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**注意**：

- _Name 参数_必需，最大长度为 64 个字符，并且必须是唯一的。 如果您不使用 _DisplayName_ 参数，_Name_ 参数的值可用于显示名称。
- 如果您不使用 Alias 参数 _，_ 则会将 _MicrosoftOnlineServicesID 参数_ 左侧用于别名。
- 如果您不使用 _ExternalEmailAddress 参数_ ， _则将 MicrosoftOnlineServicesID_ 值用于外部电子邮件地址。

此示例创建具有下列设置的邮件用户：

- 名为 JeffreyZeng，显示显示名称 Jeffrey Zeng。
- 名是 Jeffrey，姓是 Zeng。
- 别名是 jeffreyz。
- 外部电子邮件地址是 jzeng@tailspintoys.com。
- 帐户名称为"jeffreyz@contoso.onmicrosoft.com。
- 密码为 Pa$$word1。

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

有关语法和参数的详细信息，请参阅[New-EOPMailUser。](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser)

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>使用独立 EOP PowerShell 修改邮件用户

若要修改独立 EOP PowerShell 中的现有邮件用户，请使用以下语法：

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

此示例将设置 Pilar Pinilla 的外部电子邮件地址。

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

此示例将所有邮件用户的"公司"属性设置为 Contoso。

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

有关语法和参数的详细信息，请参阅[Set-EOPMailUser。](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser)

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>使用独立 EOP PowerShell 删除邮件用户

若要删除独立 EOP PowerShell 中的邮件用户，请 \<MailUserIdentity\> 替换为邮件用户的名称、别名或帐户名，并运行以下命令：

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

本示例删除 Jeffrey Zeng 的邮件用户。

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

有关语法和参数的详细信息，请参阅[Remove-EOPMailUser。](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser)

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证是否已在独立 EOP 中成功创建、修改或删除邮件用户，请使用以下任一过程：

- 在 EAC 中，转到"**收件人联系人** \> **"。** 验证邮件用户是否在 (或未列出) 。 选择邮件用户并在"详细信息"窗格中查看信息，或单击"编辑 **"** ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 查看设置。

- 在独立 EOP PowerShell 中，运行以下命令来验证邮件用户是否在未 (邮箱用户或未在) ：

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- 使用 \<MailUserIdentity\> 邮件用户的名称、别名或帐户名称替代，并运行以下命令来验证设置：

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>使用目录同步管理邮件用户

在独立 EOP 中，目录同步适用于具有本地 Active Directory 的客户。 你可以将这些帐户同步到 Azure AD (应用程序中的 Azure Active Directory) ，其中，帐户的副本存储在云中。 将现有用户帐户同步到 Azure Active Directory 后，您可在 Exchange 管理中心 (EAC 网站的 **"收件人** "窗格中或独立 EOP PowerShell) 中查看这些用户。

**注意**：

- 如果您使用目录同步来管理收件人，则您仍然可以在 Microsoft 365 管理中心中添加和管理用户，但是他们无法与您的本地 Active Directory 同步。 这是因为目录同步只能将来自本地 Active Directory 的收件人同步到云。

- 建议将目录同步用于以下功能：

  - **Outlook 安全发件人列表和阻止发件人列表**：当同步到服务时，这些列表将优先于服务中的垃圾邮件筛选。 这允许用户使用单个发件人和域条目管理他们自己的安全发件人列表和阻止发件人列表。 有关详细信息，请参阅[配置 Exchange Online 邮箱上的垃圾邮件设置](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes)。

  - **基于目录的边缘 (DBEB) ： **有关 DBEB 的详细信息，请参阅 [使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。

  - **最终用户有权访问隔离**：若要访问隔离邮件，收件人必须在服务中具有有效的用户 ID 和密码。 有关隔离的详细信息，请参阅以用户 [身份查找并释放隔离邮件](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user)。

  - **邮件流规则 (也称为传输规则) ： **使用目录同步时，现有的 Active Directory 用户和组将自动上传到云，而且你可以随后创建面向特定用户和/或组的邮件流规则，无需在服务中手动添加它们。 请注意， [动态通讯组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups)无法通过目录同步进行同步。

按 Azure Active Directory 混合标识的混合标识中所述，获取所需权限 [，并准备进行目录同步](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)。

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>使用 Azure Active Directory Connect (AAD Connect 同步) 

1. 按 Azure AD Connect 同步中所述 [激活目录同步：了解和自定义同步](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)。

2. 安装和配置本地计算机以运行 AAD Connect，如 Azure AD Connect 系统必 [备中的所述](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)。

3. [选择要用于 Azure AD Connect 的安装类型](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)：

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [自定义](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [传递身份验证](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> 完成 Azure Active Directory 同步工具配置向导后 **，MSOL_AD_SYNC** Active Directory 林中创建成员帐户。 此帐户用于读取和同步您的本地 Active Directory 信息。 为了使目录同步正常工作，请确保本地目录同步服务器上的 TCP 443 处于打开状态。

配置同步后，请务必验证 AAD Connect 是否已正确同步。 在 EAC 中， **转到** \> **"收件人** 联系人"并查看用户列表是否已从本地环境中正确同步。
