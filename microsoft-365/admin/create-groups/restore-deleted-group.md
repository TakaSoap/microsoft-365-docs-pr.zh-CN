---
title: 还原已删除的 Office 365 组
ms.reviewer: arvaradh
f1.keywords:
- CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: '了解如何使用 Exchange 管理中心还原已删除的 Office 365 组。 '
ms.openlocfilehash: c88f10df27e5f3a0af79c93c7d0e347c5646abc9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352433"
---
# <a name="restore-a-deleted-office-365-group"></a>还原已删除的 Office 365 组

如果您是 Office 365 组的所有者，则可以通过执行以下步骤自己还原组。

1. 在 "[已删除的组" 页](https://outlook.office.com/people/group/deleted)上，选择 "**组**" 节点下的 "**管理组**" 选项，然后选择 "**已删除**"。
2. 单击要还原的组旁边的 "**还原**" 选项卡。

如果此处未显示已删除的组，请与管理员联系。
  
如果您是要还原 Office 365 组的用户，请管理员为您执行这些步骤或与您的技术支持人员联系。  
   
如果已删除某个组，默认情况下它将保留30天。 这30天的期限被视为 "软删除"，因为您仍可以还原组。 30天后，该组及其关联的内容将被永久删除且无法还原。
  
在 "软删除" 时间段内，如果用户尝试访问该网站，将获得 404_禁止_访问的消息。 在此时间段后，如果用户尝试访问该网站，将收到 404_未找到_的消息。
  
还原组时，还可还原以下内容：
  
- Azure Active Directory （AD） Office 365 组对象、属性和成员。
    
- 组的电子邮件地址。
    
- Exchange Online 共享的收件箱和日历。
    
- SharePoint Online 团队网站和文件。
    
- OneNote 笔记本
    
- Planner
    
- Teams

- Yammer 组和组内容（如果已从 Yammer 创建了 Office 365 组）
    
如果等不及在 30 天的保留期过期后再删除内容，也可选择[永久删除 Office 365 组](#permanently-delete-an-office-365-group)。 

> [!NOTE]
> 已删除的 Office 365 组的所有者也能够还原该组。 若要在不具有管理员权限的情况下使用 owner 权限还原 office 365 组，请参阅[使用 PowerShell 还原 office 365 组](#restore-an-office-365-group-using-powershell)。

## <a name="restore-an-office-365-group-using-the-exchange-admin-center"></a>使用 Exchange 管理中心还原 Office 365 组

您必须拥有 Office 365 全局管理员权限。

1. 转到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理中心</a>。
    
2. 在 Exchange 管理中心，选择" **收件人**"，然后选择" **组**"。 您可以查看该组是否处于活动状态或软删除。 如果该组已被永久删除，则不会将其列出。
  
3. 若要查看软删除该组的确切时间，请选择该组并在右侧窗格中查看信息。
      
4. 选择要还原的组，然后选择 "还原" 图标。
    
    ![选择要还原的组，然后选择 "还原" 图标。](../../media/restore-group.png)
  
5. 选择 "刷新" !['刷新'图标](../../media/6464df90-2a91-4c1f-92a6-9a38c7696ac3.gif) 以更新页面上的信息。 组将显示为活动状态。 与您的组关联的任何窗体和窗体数据也将还原。
    
## <a name="restore-an-office-365-group-using-powershell"></a>使用 PowerShell 还原 Office 365 组

您必须拥有 Office 365 全局管理员权限，或者是已删除的 Office 365 组的前一个所有者。

> [!IMPORTANT]
> 如果使用 PowerShell 中的 MsolGroup 删除组，这将永久删除该组。 使用 PowerShell 删除组时，最佳做法是使用" **Remove-AzureADMSGroup**"软删除 Office 365 组。 这样可在需要时对其进行还原。 
  
### <a name="install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a>安装预览版的 Azure Active Directory PowerShell Graph

> [!IMPORTANT]
> 无法同时在同一台计算机上安装预览版本和 GA 版本。
  
作为一种最佳做法，我们建议*始终*保持最新，即卸载旧的 AzureADPreview 或旧的 AzureAD 版本并获取最新版本。 
  
 
1. 在搜索栏中，键入 Windows PowerShell。
    
2. 右键单击 **Windows PowerShell**，然后选择" **以管理员身份运行**"。
  
2. 查看已安装的模块：
    
  ```
  Get-InstalledModule -Name "AzureAD*"
  ```

3. 3.要卸载早期版本的 AzureADPreview 或 AzureAD，请运行以下命令：
  
```
   Uninstall-Module AzureADPreview
```

或者
  
```
   Uninstall-Module AzureAD
```

4. To install the latest version of AzureADPreview, run this command:
  
```
   Install-Module AzureADPreview
```



At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install. 
  
### <a name="restore-the-deleted-group"></a>还原已删除的组
  
1. 您是否按照 previoius 部分 "安装用于 Windows PowerShell 的 Azure Active Directory 模块的预览版本" 中的说明，安装了**AzureADPreview**模块？  这些步骤不起作用的首要原因是未安装最新的 **预览** 版。 
    
2. 如果尚未执行此操作，打开计算机上的 Windows PowerShell 窗口（可以是普通 Windows PowerShell 窗口，也可以是通过选择" **以管理员身份运行**"打开的窗口）。
    
3. 在每个命令后按**enter** ，以运行以下命令： 
    
  ```
  Import-Module AzureADPreview
  ```

  ```
  Connect-AzureAD
  ```



  在打开的 "**登录到帐户**" 屏幕中，输入您的管理帐户的用户名和密码以连接到 Azure AD 服务，并选择 "**登录**"。
  
4. 运行此命令可显示组织中所有软删除的 Office 365 组，这些组仍在30天软删除时段内：
    
  ```
  Get-AzureADMSDeletedGroup
  ```

5. 记下要还原的一个或多个组的对象 ID。 如果在此列表中看不到您要查找的组，则它可能已永久清除。
    
    > [!CAUTION]
    > 如果使用与被删除组相同的别名或 SMTP 地址创建了新组，则必须先删除该新组才能还原已删除的组。 
  
6. 若要还原该组，请运行以下命令：
    
  ```
  Restore-AzureADMSDeletedDirectoryObject -Id <objectId>
  ```

7. 此过程通常只需要几分钟时间，但在极少数情况下，可能需要长达24小时才能完全还原。 若要验证是否已成功还原组，请在 PowerShell 中运行此命令：
    
  ```
  Get-AzureADGroup -ObjectId <objectId>
  ```

成功还原后，该组会重新出现在 Outlook 和 Outlook 网页版的导航窗格上，且组成员应该可再次使用还原的所有内容，包括 SharePoint 和 Planner。
  
## <a name="permanently-delete-an-office-365-group"></a>永久删除 Office 365 组

有时，您可能希望永久清除组，而无需等待30天软删除期过期。 若要执行此操作，启动 PowerShell 并运行此命令，获取组的对象 ID：
  
```
Get-AzureADMSDeletedGroup
```

记下要永久删除的一个或几个组的对象 ID。
  
> [!CAUTION]
> 清除组后可永久删除该组及其数据。 
  
若要清除组，请在 PowerShell 中运行此命令：
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

若要确认是否成功清除该组，请再次运行  *Get-AzureADMSDeletedGroup*  cmdlet 以确认该组不再出现在软删除的组列表中。某些情况下，要永久删除该组及其所有数据可能需要长达 24 小时。 
  
## <a name="got-questions-about-office-365-groups"></a>对 Office 365 组有疑问？

访问[Microsoft 技术社区](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups)以发布问题并参与有关 Office 365 组的对话。 
  
## <a name="related-articles"></a>相关文章

[使用 PowerShell 管理 Office 365 组](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[使用 Remove-UnifiedGroup cmdlet 删除组](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[管理连接了组的团队网站设置](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[在 Outlook 中删除组](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
