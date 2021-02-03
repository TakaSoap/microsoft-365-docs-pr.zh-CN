---
title: 在 Outlook 中将通讯组列表升级到 Microsoft 365 组
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: 了解如何在 Outlook 中将一个或多个通讯组列表升级到 Microsoft 365 组，以及如何使用 PowerShell 同时升级多个通讯组列表。
ms.openlocfilehash: 95f887b4386b349dc9d8bb471deab19b5425f6f5
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080523"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>在 Outlook 中将通讯组列表升级到 Microsoft 365 组

可以使用 Outlook 将通讯组列表升级到 Microsoft 365 组。 这是为组织的通讯组列表提供 Microsoft 365 组的所有特性和功能很好的方法。 [为什么应将通讯组列表升级至 Outlook 中的组](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

可以一次升级一个 DLS，也可以同时升级多个 DLS。

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a>在 Outlook 中将一个或多个通讯组列表升级到 Microsoft 365 组

您必须是全局管理员或 Exchange 管理员才能升级通讯组列表。 若要升级到 Microsoft 365 组，通讯组必须具有具有邮箱的所有者。

1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。

2. 在 Exchange 管理中心，转到 **"收件人** \> **组"。**<br/>你将看到一条通知，指示你拥有一个 (也称为通讯组) 有资格升级到Microsoft 365 组。<br/> ![选择"开始"按钮](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. Select one or more distribution lists (called a **distribution group )** from the **groups** page.<br/>![选择通讯组](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. 选择升级图标。<br/>![升级到 Microsoft 365 组图标](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. 在信息对话框中，选择 **"是** "以确认升级。 该过程立即开始。 根据要升级的 DLL 的大小和数量，此过程可能需要几分钟或数小时。<br/>如果通讯组列表无法升级，则会显示一个对话框， 查看[哪些通讯组列表无法升级？。](#which-distribution-lists-cant-be-upgraded)

6. 如果要升级多个通讯组列表，请使用下拉列表筛选已升级的通讯组列表。 如果列表不完整，请稍等一会，然后选择"刷新"以查看已成功升级哪些项。<br/>系统不会通知你已完成所选所有 DLS 的升级过程。 可以通过查看"可用于升级或升级的 DLS"下列出的项来 **了解这一点**。

7. 如果选择了 DL 进行升级，但仍在页面上显示为"可供升级"，则升级失败。 请参阅 [升级不起作用时要执行哪些操作](#what-to-do-if-the-upgrade-doesnt-work)。

> [!NOTE]
> 如果你收到组摘要电子邮件，你可能会在底部注意到，有时它将提供，让你升级你作为所有者的任何符合条件的通讯组列表。 有关 [摘要电子邮件详细信息](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) ，请参阅 Outlook 中的组对话。

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>如果升级不起作用，该怎么办

无法升级的通讯组列表保持不变。

如果一个或多个符合条件的 **通讯** 组列表无法升级，请打开支持 [票证](../contact-support-for-business-products.md)。 需要将问题上报给组工程团队，让他们找出问题。

由于服务中断，通讯组列表可能不会升级，但不太可能升级。 如果需要，请稍等一下，然后再次尝试升级 DL。

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>如何使用 PowerShell 同时升级多个通讯组列表

如果你在使用 PowerShell 方面有经验的，你可能希望转到此路由，而不是使用 UI。 我们具有一组 cmdlet，可帮助您升级通讯组列表。 请参阅下文。

### <a name="upgrade-a-single-dl"></a>升级单个 DL

若要升级单个 DL，请运行以下命令：

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
```

例如，如果要升级 SMTP 地址为 dl1@contoso.com的 DLS，请运行以下命令：

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
```

> [!NOTE]
> 您还可以使用 [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet 将单个通讯组列表升级到 Microsoft 365 组

### <a name="upgrade-multiple-dls-in-a-batch"></a>批量升级多个 DLL

还可以将多个 DLL 作为批处理传递并一起升级：

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

例如，如果要升级五个 SMTP 地址为 AND 的 DLS，并运行 `dl1@contoso.com` `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` 以下命令：

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>升级所有符合条件的 DLS

有两种方法可以升级所有符合条件的 DLS。

> [!NOTE]
> Upgrade-DistributionGroup cmdlet 不会从管道接收数据，因此，需要使用"foreach-object"运算符才能 {} 成功运行。

1. 获取租户中的符合条件的 DLL，然后使用升级命令进行升级：

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. 获取所有 DLL 的列表，并仅升级符合条件的 DLS：

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>有关在 Outlook 中将通讯组列表升级到 Microsoft 365 组的常见问题解答

### <a name="which-distribution-lists-cant-be-upgraded"></a>哪些通讯组列表无法升级？

只能升级云托管的简单非嵌套通讯组列表。 下表列出了无法 **升级的** 通讯组列表。

|**属性**|**符合条件的？**|
|:-----|:-----|
|本地托管通讯组列表。  <br/> |否  <br/> |
|嵌套通讯组列表。 通讯组列表有子组，或者是另一个组的成员。  <br/> |否  <br/> |
|具有 **UserMailbox、SharedMailbox、TeamMailbox** **、MailUser** 的成员 **RecipientTypeDetails** 的通讯组列表  <br/> |否  <br/> |
|拥有 100 多个所有者的通讯组列表  <br/> |否  <br/> |
|仅包含成员但没有所有者的通讯组列表  <br/> |否  <br/> |
|别名包含特殊字符的通讯组列表  <br/> |否  <br/> |
|如果通讯组列表配置为共享邮箱的转发地址  <br/> |否  <br/> |
|如果 DL 是其他 DL **中的发件人限制的** 一部分。  <br/> |否  <br/> |
|安全组  <br/> |否  <br/> |
|动态通讯组列表  <br/> |否  <br/> |
|已转换为 **RoomLists 的通讯组列表**  <br/> |否  <br/> |
|**MemberJoinRestriction** 和/或 **MemberDepartRestriction** 已关闭的 **通讯组列表**  <br/> |否  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a>检查哪些 DLL 符合升级条件

如果要检查 DL 是否符合条件，可以运行以下命令：

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

如果要检查哪些 DLL 符合升级条件，只需运行以下命令：

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>谁可以运行升级脚本？

具有全局管理员或 Exchange 管理员权限的用户。

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>为什么联系人卡片仍显示通讯组列表？ 我应该如何阻止升级的通讯组列表显示在我的自动建议列表中？

- 对于 Outlook：当有人尝试在 Outlook 中发送电子邮件时，在迁移后键入 Microsoft 365 组名称，收件人将解析为通讯组列表而不是组。 收件人的联系人卡片将是通讯组列表联系人卡片。 这是因为 Outlook 中的收件人缓存或昵称缓存。 电子邮件将成功发送到组，但可能会导致发件人混淆。<br/>可以执行本主题（Outlook 自动完成列表[](https://go.microsoft.com/fwlink/?LinkID=798736)信息）中的步骤来重置缓存，这将修复此问题。

- 对于 Outlook 网页：对于 Web 上的 Outlook，通讯组列表收件人仍将保留在缓存中。 可以按照"从自动完成[](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58)列表中删除建议的名称或电子邮件地址"中的步骤刷新缓存以查看组联系人卡片。

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>新组的成员是否收到收件箱中的欢迎电子邮件？

否。 默认情况下，启用欢迎消息的设置设置为 false。 此设置会影响迁移完成后可加入的现有和新的组的成员。 如果组所有者稍后允许来宾用户，来宾用户不会在收件箱中收到欢迎电子邮件。 来宾成员可以继续使用组。

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>如果未升级一个或多个 DLL，将如何？

在某些情况下，虽然 DL 符合条件，但无法升级。 DL 不会升级并保留为 DL。

- 如果 **管理员为组织中** 各组应用了组电子邮件地址策略，并且他们尝试升级不满足条件的 DLS，则 DL 将不会升级

- **MemberJoinRestriction 或** **MemberDepartRestriction** 设置为 **Closed** 的 DLS 无法升级

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>如果从 EAC 升级失败，DL 会发生什么情况？

只有在将呼叫提交到服务器时，才能进行升级。 如果升级失败，则 DLL 将保持不变。 他们将像以前一样工作。
