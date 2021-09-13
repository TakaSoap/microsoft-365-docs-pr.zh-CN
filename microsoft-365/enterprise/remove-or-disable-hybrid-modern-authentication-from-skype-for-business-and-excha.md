---
title: 从 Skype for Business 和 Exchange 删除或禁用混合新式验证
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: 本文介绍了如何删除或禁用混合新式验证Skype for Business和Exchange。
ms.openlocfilehash: 9442ef3e19d0835bfd59f27ec425e36fd7dfcf7a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59196750"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>从 Skype for Business 和 Exchange 删除或禁用混合新式验证

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

如果已启用混合新式验证 (HMA) 发现它不适合当前环境，可以禁用 HMA。 本文介绍如何。
  
## <a name="who-is-this-article-for"></a>Who本文针对的是什么？

如果你在 Skype for Business Online 或本地、和/或 Exchange Online 或本地中启用了新式验证，并且发现你需要禁用 HMA，则这些步骤适合你。

> [!IMPORTANT]
> 如果你位于[](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)Skype for Business Online 或本地，拥有混合拓扑 HMA，并且需要在开始之前查看支持的拓扑，请参阅'新式验证支持的'Skype for Business拓扑'文章。
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>如何禁用混合新式验证 (Exchange) 

1. **Exchange本地：** 打开 Exchange 命令行管理程序 并运行以下命令： 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2.  [Exchange Online：连接Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) PowerShell 进行连接。 运行以下命令以将  *OAuth2ClientProfileEnabled*  标志变成"false"：

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>如何禁用混合新式验证 (Skype for Business) 

1. **Skype for Business本地：** 在命令行管理程序中Skype for Business以下命令：

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype for Business** [Online：连接远程Skype for Business PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)联机。 运行以下命令以禁用新式验证：

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[链接回新式验证概述](hybrid-modern-auth-overview.md) 。 
