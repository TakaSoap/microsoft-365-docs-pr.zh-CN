---
title: 将 AllowSelfServicePurchase 用于 MSCommerce PowerShell 模块
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: ''
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_ssp
- AdminSurgePortfolio
search.appverid:
- MET150
description: 了解如何使用 AllowSelfServicePurchase PowerShell cmdlet 打开或关闭自助服务购买。
ROBOTS: NOINDEX, NOFOLLOW
ms.date: 12/15/2021
ms.openlocfilehash: a3800f82386fafe509d9bdabb25cd91422cf058d
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63315717"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>将 AllowSelfServicePurchase 用于 MSCommerce PowerShell 模块

**MSCommerce** PowerShell 模块现已在 [PowerShell 库中可用](https://aka.ms/allowselfservicepurchase-powershell-gallery)。 该模块包含 **AllowSelfServicePurchase** 的 **PolicyID** 参数值，可用于控制贵组织的用户是否可以进行自助购买。

您可以使用 **MSCommerce** PowerShell 模块：

- 查看 **AllowSelfServicePurchase** 参数值的默认状态 — 是启用还是禁用
- 查看适用产品的列表以及自助服务购买是启用还是禁用
- 查看或修改特定产品的当前设置以启用或禁用它

## <a name="requirements"></a>要求

若要使用 **MSCommerce** PowerShell 模块，您需要：

- Windows 10 设备
- PowerShell 5 或以下产品。 当前，此模块不支持 PowerShell 6.x/7.x。
- 设备的管理员权限
- 租户的全局或帐单管理员角色

## <a name="install-the-mscommerce-powershell-module"></a>安装 MSCommerce PowerShell 模块

在 Windows 10 设备上安装 **MSCommerce** PowerShell 模块一次，然后导入到启动的每个 PowerShell 会话中。 从 PowerShell 库下载 **MSCommerce** [PowerShell 模块](https://aka.ms/allowselfservicepurchase-powershell-gallery)。

若要使用 **PowerShellGet** 安装 **MSCommerce** PowerShell 模块，请运行以下命令：

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>将 MSCommerce 导入 PowerShell 会话

在 Windows 10 设备上安装模块后，将其导入到启动的每个 PowerShell 会话中。 若要将其导入 PowerShell 会话，请运行以下命令：

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>使用凭据连接到 MSCommerce

若要使用凭据连接到 PowerShell 模块，请运行以下命令。

```powershell
Connect-MSCommerce
```

此命令将当前 PowerShell 会话连接到 Azure Active Directory 租户。 该命令会提示你输入要连接到的租户的用户名和密码。 如果为凭据启用了多重身份验证，则使用交互式选项登录。

## <a name="view-details-for-allowselfservicepurchase"></a>查看 AllowSelfServicePurchase 的详细信息

若要查看 **AllowSelfServicePurchase** 参数值和默认状态的说明，请基于您的组织运行以下命令：

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>查看自助服务购买产品及其状态的列表

若要查看所有可用自助式购买产品的列表以及每种产品的状态，请运行以下命令：

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

下表列出了可用产品及其 **ProductId**。

| 产品 | ProductId |
|-----------------------------|--------------|
| 每个用户的 Power Apps | CFQ7TTC0KP0P |
| 每个用户的 Power Automate | CFQ7TTC0KP0N |
| Power Automate RPA | CFQ7TTC0KXG6  |
| Power BI Premium (独立)  | CFQ7TTC0KXG7  |
| Power BI Pro | CFQ7TTC0L3PB |
| 项目计划 1* | CFQ7TTC0HDB1 |
| 项目计划 3* | CFQ7TTC0HDB0 |
| Visio 计划 1* | CFQ7TTC0HD33 |
| Visio 计划 2* | CFQ7TTC0HD32 |
| Windows 365 企业版 | CFQ7TTC0HTC9 |
| Windows 365 商业版 | CFQ7TTC0J203 |
| 具有 Windows 混合权益的 Windows 365 商业版 | CFQ7TTC0HX99 |

*这些 ID 已更改。 如果您之前使用旧 ID 阻止了产品，则会自动使用新 ID 阻止它们。 无需执行其他工作。

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>查看或设置 AllowSelfServicePurchase 的状态

查看可供自助购买的产品列表后，可以查看或修改特定产品的设置。

若要获取特定产品的策略设置，请运行以下命令：

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

若要为特定产品启用策略设置，请运行以下命令：

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

若要禁用特定产品的策略设置，请运行以下命令：

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>禁用 AllowSelfServicePurchase 的示例脚本

以下示例将指导您完成如何导入 **MSCommerce** 模块、使用帐户登录、获取 Power Automate 的 **ProductId** ，然后禁用 **该产品的 AllowSelfServicePurchase** 。

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

如果产品有多个值，您可以分别针对每个值运行命令，如以下示例所示：

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product[0].ProductID -Enabled $false
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product[1].ProductID -Enabled $false
```


## <a name="troubleshooting"></a>疑难解答

### <a name="problem"></a>问题

看到以下错误消息：

> HandleError：未能检索 PolicyId 为"AllowSelfServicePurchase"的策略，ErrorMessage - 基础连接已关闭：发送时发生意外错误。

这可能是由于传输层安全性的较旧版本 (TLS) 。 若要连接此服务，你需要使用 TLS 1.2 或更大

### <a name="solution"></a>解决方案

升级到 TLS 1.2。 以下语法将 ServicePointManager 安全协议更新为 TLS1.2：

```powershell
 [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.SecurityProtocolType]::Tls12
```

若要了解更多信息，请参阅 [如何启用 TLS 1.2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)。

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->

## <a name="related-content"></a>相关内容

[管理自助服务购买 (管理)  (](manage-self-service-purchases-admins.md) 文章) 

[自助服务购买常见问题 (](self-service-purchase-faq.yml) 文章) 
