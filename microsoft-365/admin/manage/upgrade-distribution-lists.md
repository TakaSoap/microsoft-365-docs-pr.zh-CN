---
title: 在 Outlook 中将通讯组列表升级为 Microsoft 365 组
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkEXCHANGE
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: 了解如何将一个或多个分发列表升级到Outlook中Microsoft 365 组，以及如何使用 PowerShell 同时升级多个分发列表。
ms.openlocfilehash: 832d65854a6a18ad28e3d9fca6d1d11c17146c80
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64782250"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a>在 Outlook 中将通讯组列表升级为 Microsoft 365 组

可以在Outlook中将通讯组列表升级到Microsoft 365 组。 这是一种绝佳的方法，可让组织的通讯组列出Microsoft 365 组的所有功能。 [为什么应将通讯组列表升级至 Outlook 中的组](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

可以一次升级一个 DLL，也可以同时升级多个 DLL。

## <a name="upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>将一个或多个通讯组升级到Microsoft 365 组Outlook

必须是全局管理员或Exchange管理员才能升级通讯组列表组。 若要升级到Microsoft 365 组，通讯组列表组必须具有具有邮箱的所有者。

### <a name="use-the-new-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>使用新的 EAC 升级一个或多个通讯组列表组以Microsoft 365 组Outlook

1. 转到新的Exchange管理中心>**收件人** \> <a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank">组</a>。

2. 选择通讯组列表组 (也称为要从“**组**”页升级到Microsoft 365组的 **通讯** 组) 。

3. 从工具栏中选择 **升级分发组** 。

4. 在“ **准备升级？”** 对话框中，单击“ **升级**”。 该过程立即开始。 根据要升级的分发列表组的大小和数量，此过程可能需要数分钟或数小时。

> [!NOTE]
> 顶部的横幅指示升级，例如，*已升级分发组 () 。反映更改需要 5 分钟。按Microsoft 365组进行筛选，查看已升级的通讯组 ()*。

### <a name="use-the-classic-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a>使用经典 EAC 升级一个或多个分发列表组以Microsoft 365 组Outlook

1. 转到Exchange管理中心>**收件人** \> <a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank">**组**</a>。<br/>你将看到一个通知，指示您有通讯组列表 (也称为 **分发组**，) 有资格升级到Microsoft 365 组。<br/> ![选择开始按钮。](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)

1. 从组页中选择一个或多个通讯组列表 (也称为 **通讯****组**) 。<br/>![选择通讯组。](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)

1. 选择升级图标。<br/>![升级到Microsoft 365 组图标。](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

1. 在信息对话框中，选择 **“是** ”以确认升级。 该过程立即开始。 根据要升级的 DLL 的大小和数量，此过程可能需要数分钟或数小时。<br/>如果无法升级分发列表，则会显示一个对话框。 查看[哪些分发列表无法升级？](#which-distribution-lists-cant-be-upgraded)

1. 如果要升级多个分发列表，请使用下拉列表来筛选哪些分发列表已升级。 如果列表未完成，请等待一段时间，然后选择 **“刷新** ”以查看已成功升级的内容。<br/>没有通知告知你何时已完成所选所有 DLL 的升级过程。 可以通过查看“ **可用于升级** ”或“ **升级的 DLL**”下列出的内容来找出这一点。

1. 如果选择了 DL 进行升级，但页面上仍显示为“可以升级”，则无法升级。 如果 [升级不起作用，](#what-to-do-if-the-upgrade-doesnt-work)请参阅该怎么办。

> [!NOTE]
> 如果你收到组摘要电子邮件，你可能会在底部注意到，有时它会提供，让你升级任何符合条件的通讯组列表，你是其所有者。 有关摘要电子邮件的详细信息，请参阅[Outlook中的群组对话](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22)。

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a>如果升级不起作用，该怎么办

无法升级的分发列表保持不变。

如果一个或多个 **符合条件** 的通讯组列表无法升级， 

1. 使用[此脚本](https://aka.ms/DLToM365Group)扫描可能阻止将分发列表升级到Microsoft 365组的问题，修复脚本报告的任何问题，并尝试再次升级分发列表。 

2. 如果上述脚本没有帮助，或者问题仍然存在，请开具 [支持票证](../../business-video/get-help-support.md)。 需要将问题上报给组工程团队，以便他们找出问题。

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a>如何使用 PowerShell 同时升级多个分发列表

如果在使用 PowerShell 方面经验丰富，则可能需要转到此路由，而不是使用 UI。 我们有一组 cmdlet，可帮助你升级通讯组列表。 请参阅下文。

### <a name="upgrade-a-single-dl"></a>升级单个 DL

若要升级单个 DL，请运行以下命令：

```PowerShell
Upgrade-DistributionGroup -DlIdentities <Dl SMTP address>
```

例如，如果要使用 SMTP 地址 dl1@contoso.com 升级 DL，请运行以下命令：

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com
```

> [!NOTE]
> 还可以使用 [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell cmdlet 将单个分发列表升级到Microsoft 365组

### <a name="upgrade-multiple-dls-in-a-batch"></a>升级批处理中的多个 DLL

还可以将多个 DLL 作为批处理传递并一起升级：

```PowerShell
Upgrade-DistributionGroup -DlIdentities <DL SMTP address1>, <DL SMTP address2>,
<DL SMTP address3>, <DL SMTP address4>
```

例如，如果想要使用 SMTP 地址`dl1@contoso.com`升级五个 DLL，`dl3@contoso.com``dl4@contoso.com`并`dl2@contoso.com``dl5@contoso.com`运行以下命令：

```powershell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com
```

### <a name="upgrade-all-eligible-dls"></a>升级所有符合条件的 DLL

有两种方法可以升级所有符合条件的 DLL。

> [!NOTE]
> Upgrade-DistributionGroup cmdlet 不会从管道接收数据，因此需要使用“foreach-object{}”运算符才能成功运行。

1. 获取租户中符合条件的 DLL，然后使用升级命令升级它们：

   ```PowerShell
   Get-EligibleDistributionGroupForMigration | Foreach-Object{
       Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
   }
   ```

2. 获取所有 DLL 的列表，并仅升级符合条件的 DLL：

   ```PowerShell
   Get-DistributionGroup| Foreach-Object{
       Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
   }
   ```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a>有关在Outlook中将分发列表升级到Microsoft 365 组的常见问题解答

### <a name="which-distribution-lists-cant-be-upgraded"></a>哪些分发列表无法升级？

只能升级云托管的简单非嵌套分发列表。 下表列出了 **无法** 升级的通讯组列表。

|属性|是否符合条件？|
|---|---|
|本地托管通讯组列表。|否|
|嵌套通讯组列表。 通讯组列表有子组，或者是另一个组的成员。|否|
|包含 **UserMailbox、SharedMailbox**、**TeamMailbox**、**MailUser** 以外的成员 **RecipientTypeDetails** 的通讯组列表 |否|
|拥有 100 个以上所有者的通讯组列表|否|
|仅具有成员但没有所有者的分发列表|否|
|具有包含特殊字符的别名的分发列表|否|
|如果将通讯组列表配置为共享邮箱的转发地址|否|
|如果 DL 是其他 DL 中的 **发件人限制** 的一部分。|否|
|安全组|否|
|动态分发列表|否|
|转换为 **RoomLists 的** 通讯组列表|否|

### <a name="check-which-dls-are-eligible-for-upgrade"></a>检查哪些 DLL 符合升级条件

如果要检查 DL 是否符合条件，可以运行以下命令：

```PowerShell
Get-DistributionGroup <DL SMTP address> | Get-EligibleDistributionGroupForMigration
```

如果要检查哪些 DLL 符合升级条件，只需运行以下命令：

```PowerShell
Get-EligibleDistributionGroupForMigration
```

### <a name="who-can-run-the-upgrade-scripts"></a>Who可以运行升级脚本？

具有全局管理员或Exchange管理员权限的人员。

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-an-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a>为什么联系人卡片仍然显示通讯组列表？ 应采取哪些措施来防止升级的分发列表显示在我的自动建议列表中？

- 对于Outlook：当某人尝试通过在迁移后键入Microsoft 365组名称在Outlook中发送电子邮件时，收件人将解析为通讯组列表而不是组。 收件人的联系人卡片将是通讯组列表联系人卡片。 这是因为Outlook中的收件人缓存或刻号缓存。 电子邮件将成功发送到组，但可能会给发件人造成混淆。<br/>可以执行本文中的步骤，[即有关 Outlook AutoComplete 列表的信息](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list)，以重置缓存，这将解决此问题。

- 对于Outlook 网页版：如果Outlook 网页版，分发列表收件人仍将保留在缓存中。 可以按照 [“自动完成列表中删除建议的姓名或电子邮件地址](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) ”中的步骤刷新缓存以查看组联系人卡片。

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a>新组成员是否在其收件箱中收到欢迎电子邮件？

不是。 默认情况下，启用欢迎消息的设置设置为 false。 此设置会影响迁移完成后可能加入的现有组成员和新组成员。 如果组所有者以后允许来宾用户，则来宾用户的收件箱中不会收到欢迎电子邮件。 来宾成员可以继续使用该组。

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a>如果一个或部分 DLL 未升级，该怎么办？

在某些情况下，DL 虽然符合条件但无法升级。 DL 不会升级并保留为 DL。

- 如果管理员为组织中的组应用了 **组电子邮件地址策略** ，并且他们尝试升级不符合条件的 DLL，则 DL 不会升级

- **MemberJoinRestriction** 或 **MemberDepartRestriction** 设置为 **“已关闭**”的 DLS 无法升级

- 仅允许使用[本文](/microsoft-365/solutions/manage-creation-of-groups)中的步骤创建Microsoft 365组。 在这种情况下，如果不允许分发列表的所有者创建Microsoft 365组，则分发列表将不会升级到Microsoft 365组。
解决方法：对上述方案使用以下解决方法之一：

1. 确保允许作为 DL 所有者的所有用户创建 M365 组，即是允许进入 M365 组的安全组的成员。

   或

2. 暂时将不允许创建 M365 组的 DL 所有者替换为允许创建 M365 组的用户。

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a>如果从 EAC 升级失败，DL 会发生什么情况？

仅当调用提交到服务器时，才会进行升级。 如果升级失败，DLL 将保持不变。 他们会像以前一样工作。

### <a name="what-happens-to-message-approval-moderation-settings-on-distribution-groups-after-upgrading"></a>升级后，消息审批 (审查) 分发组设置会发生什么情况？

消息审批 (审查) 设置将保留，并在分发组升级到Microsoft 365组后继续正常工作。

## <a name="related-content"></a>相关内容

[比较 (](../create-groups/compare-groups.md) 文章) \ 中的组
[向用户解释Microsoft 365 组](../create-groups/explain-groups-knowledge-worker.md) (文章) \
[使用管理中心从Microsoft 365组添加或删除成员](../create-groups/add-or-remove-members-from-groups.md)
