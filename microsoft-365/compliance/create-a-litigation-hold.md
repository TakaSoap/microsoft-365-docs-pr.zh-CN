---
title: 创建诉讼保留
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
description: 了解如何将邮箱置于诉讼保留状态，在调查期间保留所有邮箱内容。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 046ee6fdc7c42026b1a69805883175982e3100b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908396"
---
# <a name="create-a-litigation-hold"></a>创建诉讼保留

可以将邮箱置于诉讼保留状态，以保留所有邮箱内容，包括已删除项目和已修改项目的原始版本。 当您将用户邮箱置于诉讼保留时，用户的存档邮箱中的内容 (如果已启用，) 内容也会保留。 创建保留时，您可以指定保留持续时间 *(也称为* 基于时间保留) 以便已删除和修改的项目保留指定的时间段，然后从邮箱中永久删除。 或者，您可以无限期地保留 (称为"无限期保留") 或删除诉讼保留。 如果您指定了保留持续时间，则从收到邮件或创建邮箱项目的日期开始计算。 
  
下面是创建诉讼保留时发生的情况。
  
- 在保留期间，用户永久删除的项目将保留在用户邮箱的"可恢复的项目"文件夹中。
    
- 用户从"可恢复的项目"文件夹中清除的项目将在保留期间保留。
    
- "可恢复的项目"文件夹的存储配额从 30 GB 增加到 110 GB。
    
- 用户的主邮箱和存档邮箱中的项目将保留
    
## <a name="assign-an-exchange-online-plan-2-license"></a>分配 Exchange Online 计划 2 许可证

- 若要将 Exchange Online 邮箱置于诉讼保留状态，必须为其分配 Exchange Online 计划 2 许可证。 如果为邮箱分配了 Exchange Online 计划 1 许可证，必须为其分配单独的 Exchange Online Archiving 许可证才能将其置于保留状态。
    

## <a name="place-a-mailbox-on-litigation-hold"></a>将邮箱置于诉讼保留

下面是使用 Exchange 管理中心将邮箱置于诉讼保留中的步骤。

1. 转到 [https://outlook.office.com/ecp](https://outlook.office.com/ecp) ，然后使用全局管理员帐户登录。

2. 单击 **左侧>窗格中的** "收件人""邮箱"。

3. 选择要置于诉讼保留的邮箱，然后单击"编辑 **"。**

4. 在"邮箱属性"页上，单击"**邮箱功能"。**
    
5. 在 **"诉讼保留： 已禁用"** 下，单击 **"启用** "将邮箱置于诉讼保留状态。
    
6. 在" **诉讼保留"** 页上，输入以下可选信息： 
    
    - **诉讼保留 (天)** - 使用此框可以创建基于时间保留，并指定邮箱项目在置于诉讼保留时保留的时间。 持续时间从接收或创建邮箱项目的日期开始计算。 当特定项目的保留期到期时，将不再保留该项目。 如果保留此框为空，项目将无限期保留或一直保留到删除保留。 使用天指定持续时间。
    
    - **注意** - 使用此框通知用户其邮箱已置于诉讼保留状态。 如果用户使用的是 Outlook 2010 或更高版本，则注释将显示在用户邮箱的"帐户信息"页上。 若要访问此页面，用户可以单击"Outlook **中的** 文件"。
    
    - **URL** - 使用此框将用户引导到网站，详细了解诉讼保留。 如果用户使用的是 Outlook 2010 或更高版本，则此 URL 将显示在用户邮箱的"帐户信息"页上。 若要访问此页面，用户可以 **单击"Outlook** 中的文件"。

7. 在 **"诉讼** 保留 **"** 页上单击"保存"，然后在 **邮箱属性页上** 单击"保存"。

### <a name="create-a-litigation-hold-using-powershell"></a>使用 PowerShell 创建诉讼保留

您还可以在 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中运行以下命令来创建诉讼保留：

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

上一个命令无限期保留项目，因为未指定保留持续时间。 若要创建基于时间保留，请运行以下命令：

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

有关详细信息，请参阅 [Set-Mailbox](/powershell/module/exchange/set-mailbox)。

## <a name="how-does-litigation-hold-work"></a>诉讼保留的工作原理是什么？

在正常的已删除邮件工作流中，当用户永久删除 (Shift + Delete) 或从已删除邮件文件夹中删除某个邮箱项目时，会将该项目移动到"可恢复的项目"文件夹中的"删除"子文件夹。 当保留期到期时，删除策略（这是使用删除保留操作配置的保留标记）也将项目移动到"删除"子文件夹。 当用户清除"可恢复的项目"文件夹中的某个项目时或者当某个项目的已删除邮件保留期到期时，该项目将被移动到"可恢复的项目"文件夹中的"清除"子文件夹并标记为永久删除。 下一次通过托管文件夹助理 (MFA) 处理邮箱时，将从 Exchange 中清除该邮箱。

如果邮箱置于诉讼保留状态，在由诉讼保留指定的保留期限内会保留"清除"子文件中的项目。保留期限自接收或创建项目的原始日期算起，并且定义了保留"清除"子文件中的项目的时长。"清除"子文件中的某个项目的保留期限到期时，将该项目标记为永久删除，并且下一次通过 MFA 处理邮箱时该项目将从 Exchange 中清除。如果邮箱中设置了无限期保留，则永远不会将项目从"清除"子文件中清除。

下图显示了"可恢复的项目"文件夹中的子文件夹和保留工作流程。

![诉讼保留生命周期](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> 如果邮箱上放置了与电子数据展示案例关联的保留，则清除的项目会从"删除"子文件夹移动到 DiscoveryHolds 子文件夹，并一直保留，直到邮箱从电子数据展示保留中释放。
