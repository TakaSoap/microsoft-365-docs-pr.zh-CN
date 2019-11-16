---
title: 使用 AllowSelfServicePurchase 启用或禁用自助购买
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: 了解如何使用 AllowSelfServicePurchase PowerShell cmdlet 启用或禁用自助购买。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9093e018ed24a9e9735f5b6b71084246967cb59d
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "38676261"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>将 AllowSelfServicePurchase 用于 MSCommerce PowerShell 模块

**MSCommerce** powershell 模块现在在[powershell 库](https://aka.ms/allowselfservicepurchase-powershell-gallery)中可用。 该模块包含**AllowSelfServicePurchase**的**PolicyID**参数值，可让您控制组织中的用户是否可以进行自助服务购买。

您可以使用**MSCommerce** PowerShell 模块执行以下操作：

- 查看**AllowSelfServicePurchase**参数值的默认状态-无论是已启用还是已禁用
- 查看适用产品的列表以及是否启用或禁用自助式购买
- 查看或修改特定产品的当前设置以启用或禁用该产品

## <a name="requirements"></a>Requirements

若要使用**MSCommerce** PowerShell 模块，需要具备以下条件：

- Windows 10 设备
- 对设备的管理员权限
- 租户的全局或帐单管理员角色

## <a name="install-the-mscommerce-powershell-module"></a>安装 MSCommerce PowerShell 模块

您在 Windows 10 设备上安装**MSCommerce** PowerShell 模块后，再将其导入到每个启动的 PowerShell 会话中。 从[PowerShell 库](https://aka.ms/allowselfservicepurchase-powershell-gallery)下载**MSCommerce** PowerShell 模块。

若要使用**PowerShellGet**安装**MSCommerce** PowerShell 模块，请运行以下命令：

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>将 MSCommerce 导入 PowerShell 会话

在 Windows 10 设备上安装该模块后，再将其导入到每个启动的 PowerShell 会话中。 若要将其导入 PowerShell 会话，请运行以下命令：

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>使用你的凭据连接到 MSCommerce

若要使用你的凭据连接到 PowerShell 模块，请运行以下命令。

```powershell
Connect-MSCommerce
```

此命令将当前 PowerShell 会话连接到 Azure Active Directory 租户。 该命令将提示您输入要连接到的租户的用户名和密码。 如果为您的凭据启用了多重身份验证，则可以使用交互式选项登录。

## <a name="view-details-for-allowselfservicepurchase"></a>查看 AllowSelfServicePurchase 的详细信息

若要查看**AllowSelfServicePurchase**参数值的说明以及基于您的组织的默认状态，请运行以下命令：

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>查看自助服务购买产品的列表及其状态

若要查看所有可用的自助服务购买产品的列表以及每个产品的状态，请运行以下命令：

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

下表列出了可用的产品及其**产品 id**。

| 产品 | Id |
|-----------------------------|--------------|
| 每个用户的电源应用程序 | CFQ7TTC0KP0P |
| 每个用户的电源自动化 | CFQ7TTC0KP0N |
| Power BI Pro | CFQ7TTC0L3PB |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>查看或设置 AllowSelfServicePurchase 的状态

查看可用于自助购买的产品列表后，可以查看或修改特定产品的设置。

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

下面的示例演示如何导入**MSCommerce**模块，使用你的帐户登录，获取产品**Id**为 "自动执行" 功能，然后禁用该产品的 " **AllowSelfServicePurchase** "。

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->