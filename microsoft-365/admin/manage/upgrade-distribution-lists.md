---
title: 将通讯组列表升级到 Outlook 中的 Microsoft 365 组
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
description: 了解如何将一个或多个通讯组列表升级到 Outlook 中的 Microsoft 365 组，以及如何使用 PowerShell 同时升级多个通讯组列表。
ms.openlocfilehash: cac0232b721c07ce8e07c7b101e0313eb9cd91df
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399490"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>将通讯组列表升级到 Outlook 中的 Microsoft 365 组

您可以使用 Outlook 将通讯组列表升级到 Microsoft 365 组。 这是为组织的通讯组提供 Microsoft 365 组的所有特性和功能的好方法。 [为什么应将通讯组列表升级至 Outlook 中的组](https://support.microsoft.com/en-us/office/why-you-should-upgrade-your-distribution-lists-to-groups-in-outlook-7fb3d880-593b-4909-aafa-950dd50ce188)

您可以一次升级一个 DLs，也可以同时升级多个。

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a>在 Outlook 中将一个或多个通讯组列表升级到 Microsoft 365 组

您必须是全局管理员或 Exchange 管理员才能升级通讯组列表。 若要升级到 Microsoft 365 组，通讯组必须具有邮箱所有者。 

1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。

2. 在 Exchange 管理中心中，转到 "**收件人** \> **组**"。<br/>你将看到一则通知，指示你具有可升级到 Microsoft 365 组的通讯组列表（也称为**通讯组**）。<br/> ![选择 "开始入门" 按钮](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

3. 从 "**组**" 页面中选择一个或多个通讯组列表（也称为**通讯组**）。<br/>![选择通讯组](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

4. 选择 "升级" 图标。<br/>!["升级到 Microsoft 365 组" 图标](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. 在 "信息" 对话框中，选择 **"是"** 以确认升级。 该过程将立即开始。 此过程可能需要几分钟或几小时，具体取决于您要升级的 Dl 的大小和数量。<br/>如果无法升级通讯组列表，则会显示一个对话框。 查看[哪些通讯组列表无法升级？](#which-distribution-lists-cannot-be-upgraded)。

6. 如果要升级多个通讯组列表，请使用下拉列表筛选已升级的通讯组列表。 如果列表未完成，请等待一段时间，然后选择 "**刷新**" 以查看已成功升级的内容。<br/>不会通知你选择的所有 Dl 的升级过程完成后。 您可以通过查看 "**可用于升级**或**升级的 dl**" 下列出的内容来完成此操作。

7. 如果选择了 DL 进行升级，但它在页面上仍显示为可升级，则升级失败。 [如果升级不起作用，请查看要执行的操作](#what-to-do-if-the-upgrade-doesnt-work)。

> [!NOTE]
> 如果你正在获取组摘要电子邮件，你可能会注意到，有时会通过它来升级你是其所有者的任何符合条件的通讯组列表。 有关摘要电子邮件的详细信息，请参阅[在 Outlook 中有组对话](https://support.microsoft.com/en-us/office/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22)。


## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>如果升级不起作用，该怎么办

无法升级的通讯组列表保持不变。

如果一个或多个**符合条件**的通讯组列表升级失败，请打开[支持票证](../contact-support-for-business-products.md)。 需要将问题升级至组工程团队，以确定问题所在。

由于服务中断，通讯组列表可能未升级，但很少出现。 如果需要，请等待一段时间，然后再次尝试升级 DL。

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>如何使用 PowerShell 同时升级多个通讯组列表

如果您在使用 PowerShell 时遇到了经验，您可能希望转而不是使用 UI 来转到此路由。 我们有一组 cmdlet，可帮助您升级通讯组列表。 请参阅下文。

### <a name="upgrade-a-single-dl"></a>升级单个 DL

若要升级单个 DL，请运行以下命令：

`Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`

例如，如果您想要使用 SMTP 地址 dl1@contoso.com 升级 Dl，请运行以下命令：

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`

> [!NOTE]
> 您还可以使用[Remove-unifiedgroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet 将单个通讯组列表升级到 Microsoft 365 组

### <a name="upgrade-multiple-dls-in-a-batch"></a>在批处理中升级多个 Dl

您还可以将多个 Dl 作为批处理传递，并将它们升级到一起：

```
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,

\< DL SMTP address3\>, \< DL SMTP address 4\>
```

例如，如果要升级5个使用 SMTP 地址的 dl， `dl1@contoso.com` 和、和，请 `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` 运行以下命令：

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a>升级所有符合条件的 Dl

可以通过两种方式升级所有符合条件的 Dl。

> [!NOTE]
> New-distributiongroup cmdlet 不接收管道中的数据，因此，必须使用 "foreach-object {} " 运算符才能成功运行。

1. 在租户中获取符合条件的 Dl 并使用升级命令对其进行升级：

```
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. 获取所有 Dl 的列表并仅升级符合条件的 Dl：

```
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>有关将通讯组列表升级到 Outlook 中的 Microsoft 365 组的常见问题解答

### <a name="which-distribution-lists-cannot-be-upgraded"></a>哪些通讯组列表无法升级？

您只能升级云管理、简单、非嵌套的通讯组列表。 下表列出了**无法**升级的通讯组列表。

|**Property**|**退税?**|
|:-----|:-----|
|内部部署管理通讯组列表。  <br/> |否  <br/> |
|嵌套的通讯组列表。 通讯组列表具有子组或是另一个组的成员。  <br/> |否  <br/> |
|具有除**UserMailbox**、 **SharedMailbox**、 **TeamMailbox**、 **MailUser**之外的 member **RecipientTypeDetails**的通讯组列表  <br/> |否  <br/> |
|包含超过100个所有者的通讯组列表  <br/> |否  <br/> |
|仅包含成员但没有所有者的通讯组列表  <br/> |否  <br/> |
|包含特殊字符别名的通讯组列表  <br/> |否  <br/> |
|如果将通讯组列表配置为共享邮箱的转发地址  <br/> |否  <br/> |
|如果 DL 是另一个 DL 中的**发件人限制**的一部分。  <br/> |否  <br/> |
|安全组  <br/> |否  <br/> |
|动态通讯组列表  <br/> |否  <br/> |
|转换为**RoomLists**的通讯组列表  <br/> |否  <br/> |
|**MemberJoinRestriction**和/或**MemberDepartRestriction** **关闭**的通讯组列表  <br/> |否  <br/> |

### <a name="how-do-i-check-which-dls-are-eligible-for-upgrade"></a>如何检查哪些 Dl 有资格进行升级？

如果要检查 DL 是否符合条件，可以运行以下命令：

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

如果要检查哪些 Dl 有资格进行升级，只需运行以下命令：

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a>谁可以运行升级脚本？

具有全局管理员或 Exchange 管理员权限的人员。

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>为什么联系人卡片仍显示通讯组列表？ 若要阻止已升级的通讯组列表显示在我的自动建议列表中，我该怎么办？

- 对于 Outlook：如果有人尝试在迁移后键入 Microsoft 365 组名称来在 Outlook 中发送电子邮件，则收件人将解析为通讯组列表，而不是组。 收件人的联系人卡片将是通讯组列表联系人卡片。 这是因为 Outlook 中的收件人缓存或 nick 名称缓存。 电子邮件将成功发送到组，但可能会导致发件人混淆。<br/>您可以执行本主题中的步骤，[有关 Outlook 自动完成列表的信息](https://go.microsoft.com/fwlink/?LinkID=798736)，以重置缓存，这将修复此问题。

- 对于 web 上的 Outlook：在 Outlook 网页版中，通讯组列表收件人仍将保留在缓存中。 您可以按照 "[删除建议的名称" 或 "自动完成" 列表中的电子邮件地址](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx)中的步骤操作，以刷新缓存以查看组联系人卡片。

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>新组成员是否可在其收件箱中获取欢迎电子邮件？

否。 默认情况下，启用欢迎邮件的设置设置为 false。 此设置会影响在迁移完成后可能加入的现有和新组成员。 如果组所有者稍后允许来宾用户，则来宾用户不会在其收件箱中收到欢迎电子邮件。 来宾成员可以继续使用该组。

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>如果一个或多个 Dl 未升级，该怎么办？

在某些情况下，虽然 DL 符合条件，但无法升级。 DL 不会升级且仍保留为 DL。

- 在组织中，管理员已为组织中的组应用了**组电子邮件地址策略**，并尝试升级无法满足条件的 DLS，DL 不会进行升级

- 无法升级**MemberJoinRestriction**或**MemberDepartRestriction**设置为 "**已关闭**" 的 dl

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>如果从 EAC 升级失败，DL 会发生什么情况？

仅在将呼叫提交到服务器时，才会进行升级。 如果升级失败，你的 Dl 将保持不变。 它们的工作方式类似于使用它们。


