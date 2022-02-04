---
title: 为实现到 Microsoft 365 的目录同步做好准备
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
  - CSH
ms.custom:
  - Adm_O365
  - O365p_AddUsersWithDirSync
  - O365M_AddUsersWithDirSync
  - O365E_HRCSetupAADConnectAboutLM617031
  - O365E_AddUsersWithDirSync
ms.collection:
  - Ent_O365
  - M365-identity-device-management
search.appverid:
  - MET150
  - MOP150
  - MOE150
  - MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: 介绍如何准备通过使用目录同步Microsoft 365设置用户，以及使用此方法的长期好处。
---

# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a>为实现到 Microsoft 365 的目录同步做好准备

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

如果已在此解决方案的步骤 [2](protect-your-global-administrator-accounts.md) 和用户帐户的步骤 [3](microsoft-365-secure-sign-in.md) 中选择了混合标识模型并配置了对管理员帐户的保护，则下一个任务是部署目录同步。 组织目录同步的好处包括：

- 减少贵组织的管理程序
- （可选）启用单一登录方案
- 自动执行帐户中的帐户Microsoft 365

有关使用目录同步的优势详细信息，请参阅混合标识[与](/azure/active-directory/hybrid/whatis-hybrid-identity)Azure Active Directory (Azure AD) 。

但是，目录同步需要规划和准备，以确保 Active Directory 域服务 (AD DS) 与 Microsoft 365 订阅的 Azure AD 租户同步，并且最少出现错误。

请按照以下步骤操作，以便获得最佳结果。

> [!NOTE]
> 对于 AD DS 用户帐户上的任何属性，非 ASCII 字符不会同步。

## <a name="ad-ds-preparation"></a>AD DS 准备

为了帮助确保使用同步无缝Microsoft 365，必须在开始部署目录同步Microsoft 365准备 AD DS 林。
  
目录准备应专注于以下任务：

- 删除重复 **的 proxyAddress** 和 **userPrincipalName** 属性。
- 使用有效的 **userPrincipalName** 属性更新空和无效 **的 userPrincipalName** 属性。
- 删除 **givenName**、surname **( sn** ) 、 **sAMAccountName**、 **displayName**、 **mail**、 **proxyAddresses**、 **mailNickname** 和 **userPrincipalName** 属性中的无效和问题字符。 有关准备属性的详细信息，请参阅由同步工具同步Azure Active Directory[列表](https://go.microsoft.com/fwlink/p/?LinkId=396719)。

    > [!NOTE]
    > 这些属性与要同步Azure AD 连接相同。 
  
## <a name="multi-forest-deployment-considerations"></a>多林部署注意事项

对于多个林和 SSO 选项，请使用[自定义 Azure AD 连接](/azure/active-directory/hybrid/how-to-connect-install-custom)。
  
如果您的组织具有多个用于身份验证的林 (登录) ，我们强烈建议您执行以下操作：
  
- **请考虑合并林。** 通常，维护多个林需要更多开销。 除非贵组织的安全约束规定需要单独的林，否则请考虑简化您的本地环境。
- **仅在主登录林中使用。** 请考虑仅在Microsoft 365登录林中部署客户端，以初始部署Microsoft 365。 

如果无法合并多林 AD DS 部署或正在使用其他目录服务来管理标识，则可以通过 Microsoft 或合作伙伴的帮助来同步这些部署。
  
有关详细信息[，请参阅Azure AD 连接](/azure/active-directory/hybrid/plan-connect-topologies)拓扑。
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a>依赖于目录同步的功能
  
以下特性和功能需要目录同步：
  
- Azure AD无缝单Sign-On (SSO) 
- Skype共存
- Exchange混合部署，包括：
  - 在内部部署环境与 (环境) 之间使用 GAL Exchange全局地址Microsoft 365。
  - 同步不同邮件系统中的 GAL 信息。
  - 在服务产品中添加用户以及从服务Microsoft 365删除用户的能力。 这要求：
  - 在目录同步设置过程中必须配置双向同步。 默认情况下，目录同步工具仅将目录信息写入云。 配置双向同步时，将启用写回功能，以便从云中复制有限数量的对象属性，然后将这些属性写回本地 AD DS。 回写也称为混合Exchange模式。 
  - 内部部署Exchange混合部署
  - 将一些用户邮箱移动到 Microsoft 365将其他用户邮箱保留在本地的能力。
  - 保险箱将本地发件人和阻止的发件人复制到Microsoft 365。
  - 基本委托和代表发送电子邮件功能。
  - 你拥有集成的本地智能卡或多重身份验证解决方案。
- 同步照片、缩略图、会议室和安全组

## <a name="1-directory-cleanup-tasks"></a>1. 目录清理任务

在将 AD DS 同步到 Azure AD租户之前，需要清理 AD DS。

> [!IMPORTANT]
> 如果在同步之前不执行 AD DS 清理，则会导致对部署过程产生显著负面影响。 可能需要数天甚至数周的时间才能经历目录同步、识别错误和重新同步的周期。

在 AD DS 中，为每个将分配有许可证的用户帐户完成以下Microsoft 365任务：

1. 确保 **proxyAddresses 属性中具有有效且唯一** 的电子邮件地址。

2. 删除 **proxyAddresses 属性中任何重复** 的值。

3. 如果可能，请确保用户用户对象中的 **userPrincipalName** 属性具有有效且 **唯** 一的值。 为了获得最佳同步体验，请确保 AD DS UPN 与 UPN Azure AD匹配。 如果用户没有 **userPrincipalName** 属性的值，则用户对象必须包含 **sAMAccountName 属性的有效唯一** 值。 删除 **userPrincipalName 属性中任何重复** 的值。

4. 为了充分利用全局地址列表 (GAL) ，请确保 AD DS 用户帐户的以下属性中的信息正确：

   - givenName
   - surname
   - displayName
   - 职务
   - 部门
   - 办公室
   - 办公室电话
   - 移动电话
   - 传真号码
   - 街道地址
   - 市/县
   - 省/自治区/直辖市
   - 邮政编码
   - 国家或地区

## <a name="2-directory-object-and-attribute-preparation"></a>2. 目录对象和属性准备

AD DS 和 Microsoft 365之间的成功目录同步要求正确准备 AD DS 属性。 例如，您需要确保特定字符不用于与 Microsoft 365 环境同步的某些属性。 意外字符不会导致目录同步失败，但可能会返回警告。 无效字符将导致目录同步失败。

如果某些 AD DS 用户具有一个或多个重复属性，目录同步也将失败。 每个用户都必须具有唯一的属性。

下面列出了需要准备的属性：

- **displayName**

  - 如果属性存在于 user 对象中，它将与Microsoft 365。
  - 如果此属性存在于用户对象中，则必须有一个值。 也就是说，属性不得为空。
  - 最大字符数：256

- **givenName**

  - 如果属性存在于用户对象中，它将与Microsoft 365同步，Microsoft 365不需要也不使用它。
  - 最大字符数：64

- **mail**

  - 属性值在目录中必须是唯一的。

    > [!NOTE]
    > 如果存在重复值，则同步具有值的第一个用户。 后续用户将不会显示在Microsoft 365。 必须修改 AD DS 中的Microsoft 365或修改这两个值，以便两个用户都显示在Microsoft 365。

- **mailNickname** (Exchange别名) 

  - 属性值不能以 (.) 开头。
  - 属性值在目录中必须是唯一的。

    > [!NOTE]
    > 同步 ("_") 中的下划线表示此属性的原始值包含无效字符。 有关此属性详细信息，请参阅Exchange[别名属性](/powershell/module/exchange/set-mailbox)。
    >

- **proxyAddresses**

  - 多值属性
  - 每个值的最大字符数：256
  - 属性值不能包含空格。
  - 属性值在目录中必须是唯一的。
  - 无效字符： \< \> ( ) ; ， [ ] "
  - 带音调符号的字母（如 umlauts、accents 和 tildes）是无效字符。

    请注意，无效字符适用于类型分隔符和"："后的字符，SMTP:User@contso.com，SMTP:user:M@contoso.com 无效。

    > [!IMPORTANT]
    > 所有简单邮件传输协议 (SMTP) 地址应符合电子邮件标准。 删除重复或不需要的地址（如果存在）。

- **sAMAccountName**

  - 最大字符数：20
  - 属性值在目录中必须是唯一的。
  - 无效字符： [ \ " | ， / ： \< \> + = ; ？ \* ']
  - 如果用户具有无效 **的 sAMAccountName** 属性，但具有有效的 **userPrincipalName** 属性，则用户帐户是在 Microsoft 365。
  - 如果 **sAMAccountName** 和 **userPrincipalName** 均无效，则必须更新 AD DS **userPrincipalName** 属性。

- **sn** (surname) 

  - 如果属性存在于用户对象中，它将与Microsoft 365同步，Microsoft 365不需要也不使用它。

- **targetAddress**

    例如，**targetAddress** 属性必须 (，SMTP:tom@contoso.com) 填充的用户属性必须显示在 Microsoft 365 GAL 中。 在第三方邮件迁移方案中，这Microsoft 365 AD DS 的架构扩展。 该Microsoft 365架构扩展还将添加其他有用的属性，以Microsoft 365 AD DS 中的目录同步工具填充的对象。 例如，将添加用于管理隐藏邮箱或通讯组的 **msExchHideFromAddressLists** 属性。

  - 最大字符数：256
  - 属性值不能包含空格。
  - 属性值在目录中必须是唯一的。
  - 无效字符： \ \< \> ( ) ; ， [ ] "
  - 所有简单邮件传输协议 (SMTP) 地址应符合电子邮件标准。

- **userPrincipalName**

  - **userPrincipalName** 属性必须是 Internet 样式的登录格式，其中用户名后跟 at 符号 (@) 和域名：例如 user@contoso.com。 所有简单邮件传输协议 (SMTP) 地址应符合电子邮件标准。
  - **userPrincipalName** 属性的最大字符数为 113。 a specific number of characters are permitted before and after the at sign (@) ， as follows：
  - 位于 at 符号前面的用户名的最大字符数 (@) ：64
  - @ (@) 符号后面的域名的最大字符数：48
  - 无效字符： \ % &amp; \* + / = ？ { } | \< \> ( ) ; : , [ ] "
  - 允许的字符：A – Z、a - z、0 – 9、' 。 - _ ! # ^ ~
  - 带音调符号的字母（如 umlauts、accents 和 tildes）是无效字符。
  - 每个 **userPrincipalName** 值中都需要 @ 字符。
  - @ 符在每个 **userPrincipalName** 值中不能作为第一个字符。
  - 用户名不得以带符号 (.) &amp; 、与号 () 、空格或 at 符号 (@) 。
  - 用户名不能包含任何空格。
  - 必须使用可路由域;例如，不能使用本地或内部域。
  - Unicode 将转换为下划线字符。
  - **userPrincipalName** 不能包含目录中的任何重复值。

## <a name="3-prepare-the-userprincipalname-attribute"></a>3. 准备 userPrincipalName 属性

Active Directory 旨在允许贵组织的最终用户使用 **sAMAccountName** 或 **userPrincipalName 登录目录**。 同样，最终用户可以使用用户主体名称Microsoft 365工作或学校帐户的 UPN (登录到) 。 目录同步尝试使用 AD DS Azure Active Directory UPN 在目录中创建新用户。 UPN 的格式与电子邮件地址类似。

在Microsoft 365中，UPN 是用于生成电子邮件地址的默认属性。 很容易在 AD DS 和 (获取 **userPrincipalName** Azure AD) ，**proxyAddresses** 中的主电子邮件地址将设置为不同的值。 当它们设置为不同的值时，管理员和最终用户可能会混淆。

最好对齐这些属性以减少混淆。 若要满足使用 Active Directory 联合身份验证服务 (AD FS) 2.0 单一登录的要求，您需要确保 Azure Active Directory 中的 UPN 与 AD DS 匹配且正在使用有效的域命名空间。

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. 向 AD DS 添加备用 UPN 后缀

您可能需要添加备用 UPN 后缀，以将用户的公司凭据与Microsoft 365关联。 UPN 后缀是 @ 字符右侧的 UPN 的一部分。 用于单一登录的 UPN 可能包含字母、数字、句点、短划线和下划线，但不包含任何其他类型的字符。

若要详细了解如何将备用 UPN 后缀添加到 Active Directory，请参阅准备 [目录同步](https://go.microsoft.com/fwlink/p/?LinkId=525430)。

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. 将 AD DS UPN 与 UPN Microsoft 365匹配

如果已设置目录同步，则用户的 Microsoft 365 UPN 可能与在 AD DS 中定义的用户的 AD DS UPN 不匹配。 如果在验证域前已为用户分配了许可证，则可能发生这种情况。 若要解决此问题，请使用 [PowerShell 修复重复 UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730)，以更新用户的 UPN，以确保 Microsoft 365 UPN 与公司用户名和域匹配。 如果要在 AD DS 中更新 UPN，并且希望它与 Azure Active Directory 标识同步，则需要在 Microsoft 365 中删除用户的许可证，然后在 AD DS 中进行更改。

另 [请参阅如何准备不可路由的域 (.local domain) 进行目录同步](prepare-a-non-routable-domain-for-directory-synchronization.md)。

## <a name="next-steps"></a>后续步骤

完成上述 1 到 5 操作后，请参阅 [设置目录同步](set-up-directory-synchronization.md)。
