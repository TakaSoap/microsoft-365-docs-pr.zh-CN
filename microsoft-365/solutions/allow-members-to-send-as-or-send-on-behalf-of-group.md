---
title: 允许成员以组的名义发送或代表组发送
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
ms.custom: admindeeplinkEXCHANGE
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
recommendations: false
description: 了解如何允许团队成员以组Microsoft 365或代表组发送电子邮件Microsoft 365发送电子邮件。
ms.openlocfilehash: 588008669359629f5b59498bb7dbf776112d5408
ms.sourcegitcommit: cdb90f28e59f36966f8751fa8ba352d233317fc1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2022
ms.locfileid: "63401002"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>允许成员以组的名义发送或代表组发送

已被授予Microsoft 365"代理发送"或"代表发送"权限的组的成员可以组或代表组发送电子邮件。  (组内来宾无法授予这些权限。) 

本文介绍全局管理员或Exchange管理员如何设置这些权限。
  
例如，如果 Megan Bowen 是 **Training** Microsoft 365 组的一部分，并且对该组具有"发送为"权限，那么如果她以组发送电子邮件，则看起来就像培训组已发送电子邮件一样。 
  
"**代表发送**"权限允许用户代表组Microsoft 365发送电子邮件。 例如，如果 Alex Wilber 是 **Marketing Microsoft 365 组的** 一部分，并且具有"代表发送"权限并作为组发送电子邮件，则电子邮件看起来好像是由 **Alex Wilber 代表 Marketing** 发送的。

> [!IMPORTANT]
> 您可以为 **给定用户配置****"** 代理发送"或"代表发送"，但不能同时配置这两者。 如果同时配置这两者，它将默认 **为"发送方式"**。

> [!NOTE]
> **在混合****和混合** 配置中，不支持以Outlook for Mac和代表Exchange发送。
    
## <a name="allow-members-to-send-email-as-a-group"></a>允许成员以组发送电子邮件

本部分介绍如何允许用户在 Exchange Online 中的 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">EAC Exchange管理</a>中心 () 组Exchange Online。
  
1. In the Exchange admin center， go to **Recipients** \> <a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank">**Groups**</a>.
    
2. 选择要允许用户发送的组。 
    
3. 选择 **设置** > **管理代理"**。
    
4. 在 **"添加代理** "部分，输入希望其具有"代理发送"访问权限 **的用户** 的电子邮件地址。
  
5. 从 **下拉列表中选择** "权限 **类型发送** 为"。

6.  选择“**保存更改**”。
    
    
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>允许成员代表组发送电子邮件

本部分介绍如何允许用户代表 Exchange 管理中心中的组发送电子邮件<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank"> (EAC </a>) Exchange Online。
  
1. In the Exchange admin center， go to **Recipients** \> <a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank">**Groups**</a>.
    
2. 选择要允许用户代表发送的组。 
    
3. 选择 **设置** > **管理代理"**。
    
4. 在 **"添加代理** "部分，输入希望其具有"代理发送"访问权限 **的用户** 的电子邮件地址。
  
5. 从 **下拉列表中选择****"权限类型** 为代表发送"。

6.  选择“**保存更改**”。

## <a name="related-articles"></a>相关文章

[从组或代表组发送电子邮件Microsoft 365发送电子邮件](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)

[协作治理规划建议](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[创建协作管理计划](collaboration-governance-first.md)

[了解有关组Microsoft 365信息](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission)

[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup)
