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
description: 本文介绍如何从 Skype for Business 和 Exchange 中删除或禁用混合新式身份验证。
ms.openlocfilehash: da0887936f5def69ad80c8f04381bcb3a85c2349
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687658"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>从 Skype for Business 和 Exchange 删除或禁用混合新式验证

*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* 

如果已启用混合新式身份验证 (HMA) 仅在找不到适合您的当前环境的情况下，您可以禁用 HMA。 本文介绍如何操作。
  
## <a name="who-is-this-article-for"></a>本文的目标是什么？

如果已在 Skype for Business Online 或内部部署中启用新式验证，以及/或 Exchange Online 或本地，并且发现您需要禁用 HMA，则这些步骤适用于您。

> [!IMPORTANT]
> 如果你在 Skype for Business Online 或内部部署中，请参阅 "[使用新式身份验证支持的 Skype For business 拓扑](https://technet.microsoft.com/library/mt803262.aspx)" 一文具有混合拓扑 HMA，在开始之前，需要查看受支持的拓扑。
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>如何在 Exchange) 中禁用混合新式身份验证 (

1. **Exchange 本地**：打开 Exchange 命令行管理程序并运行以下命令： 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange online**：使用远程 PowerShell [连接到 Exchange online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 。 运行以下命令，将您的  *OAuth2ClientProfileEnabled*  标志转换为 "false"：

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>如何禁用 (Skype for business) 的混合新式身份验证

1. **Skype**for business 本地：在 Skype For Business 命令行管理程序中运行以下命令：

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype for Business online**：使用远程 PowerShell [连接到 Skype for business online](manage-skype-for-business-online-with-microsoft-365-powershell.md) 。 运行以下命令以禁用新式验证：

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[链接回新式验证概述](hybrid-modern-auth-overview.md) 。 
  

