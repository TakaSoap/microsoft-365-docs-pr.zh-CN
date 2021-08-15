---
title: 将 AllowSelfServicePurchase 用于 MSCommerce PowerShell 模块
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_ssp
search.appverid:
- MET150
description: 了解如何使用 AllowSelfServicePurchase PowerShell cmdlet 打开或关闭自助服务购买。
ROBOTS: NOINDEX, NOFOLLOW
ms.date: 07/16/2021
ms.openlocfilehash: 8714334d2c05d312d8a7895c943e21816e31c9297e879b9681639efb92aec426
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53900275"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>将 AllowSelfServicePurchase 用于 MSCommerce PowerShell 模块

**MSCommerce** PowerShell 模块现已在 [PowerShell 库上提供](https://aka.ms/allowselfservicepurchase-powershell-gallery)。 该模块包括 **AllowSelfServicePurchase** 的 **PolicyID** 参数值，它允许您控制组织中用户是否可以进行自助购买。

您可以使用 **MSCommerce** PowerShell 模块：

- 查看 **AllowSelfServicePurchase** 参数值的默认状态 — 是启用还是禁用
- 查看适用产品的列表，以及自助服务购买是启用还是禁用
- 查看或修改特定产品的当前设置以启用或禁用它

## <a name="requirements"></a>Requirements

若要使用 **MSCommerce** PowerShell 模块，您需要：

- Windows 10设备
- PowerShell 5 或以下产品。 当前，此模块不支持 PowerShell 6.x/7.x。
- 设备的管理员权限
- 租户的全局或帐单管理员角色

## <a name="install-the-mscommerce-powershell-module"></a>安装 MSCommerce PowerShell 模块

在设备上安装 **MSCommerce** PowerShell 模块一Windows 10，然后导入到您启动的每个 PowerShell 会话中。 从 [PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery)库下载 **MSCommerce** PowerShell 模块。

若要使用 **PowerShellGet** 安装 **MSCommerce** PowerShell 模块，请运行以下命令：

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>将 MSCommerce 导入 PowerShell 会话

在设备上安装模块Windows 10，然后将其导入到您启动的每个 PowerShell 会话中。 若要将其导入 PowerShell 会话，请运行以下命令：

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>连接凭据访问 MSCommerce

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

若要查看所有可用的自助式购买产品的列表以及每种产品的状态，请运行以下命令：

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

下表列出了可用的产品及其 **ProductId。**

| 产品 | ProductId |
|-----------------------------|--------------|
| Power Apps每个用户 | CFQ7TTC0KP0P |
| Power Automate每个用户 | CFQ7TTC0KP0N |
| Power AutomateRPA | CFQ7TTC0KXG6  |
| Power BI Premium (独立)  | CFQ7TTC0KXG7  |
| Power BI Pro | CFQ7TTC0L3PB |
| Project 计划 1 | CFQ7TTC0KXND |
| Project 计划 3 | CFQ7TTC0KXNC |
| Visio 计划 1 | CFQ7TTC0KXN9 |
| Visio 计划 2 | CFQ7TTC0KXN8 |
| Windows 365 Enterprise | CFQ7TTC0HTC9 |
| Windows 365 商业版 | CFQ7TTC0J203 |
| Windows混合权益的 Windows 365 商业版 | CFQ7TTC0HX99 |
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

以下示例将引导您完成如何导入 **MSCommerce** 模块、使用您的帐户登录、获取 Power Automate 的 **ProductId，** 然后禁用该产品的 **AllowSelfServicePurchase。**

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>疑难解答

### <a name="problem"></a>问题

看到以下错误消息：

> HandleError：未能检索 PolicyId 为"AllowSelfServicePurchase"的策略，ErrorMessage - 基础连接已关闭：发送时发生意外错误。

这可能是由于传输层安全性的较旧版本 (TLS) 。 若要连接此服务，你需要使用 TLS 1.2 或更大

### <a name="solution"></a>解决方案

升级到 TLS 1.2： (/mem/configmgr/core/plan-design/security/enable-tls-1-2) 

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
