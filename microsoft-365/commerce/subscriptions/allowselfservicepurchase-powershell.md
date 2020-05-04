---
title: 将 AllowSelfServicePurchase 用于 MSCommerce PowerShell 模块
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 6c0bcec70eab4266674ca2a22f1b2054807a26e8
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011671"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="469f2-103">将 AllowSelfServicePurchase 用于 MSCommerce PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="469f2-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="469f2-104">**MSCommerce** powershell 模块现在在[powershell 库](https://aka.ms/allowselfservicepurchase-powershell-gallery)中可用。</span><span class="sxs-lookup"><span data-stu-id="469f2-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="469f2-105">该模块包含**AllowSelfServicePurchase**的**PolicyID**参数值，可让您控制组织中的用户是否可以进行自助服务购买。</span><span class="sxs-lookup"><span data-stu-id="469f2-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="469f2-106">您可以使用**MSCommerce** PowerShell 模块执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="469f2-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="469f2-107">查看**AllowSelfServicePurchase**参数值的默认状态-无论是已启用还是已禁用</span><span class="sxs-lookup"><span data-stu-id="469f2-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="469f2-108">查看适用产品的列表以及是否启用或禁用自助式购买</span><span class="sxs-lookup"><span data-stu-id="469f2-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="469f2-109">查看或修改特定产品的当前设置以启用或禁用该产品</span><span class="sxs-lookup"><span data-stu-id="469f2-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="469f2-110">要求</span><span class="sxs-lookup"><span data-stu-id="469f2-110">Requirements</span></span>

<span data-ttu-id="469f2-111">若要使用**MSCommerce** PowerShell 模块，需要具备以下条件：</span><span class="sxs-lookup"><span data-stu-id="469f2-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="469f2-112">Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="469f2-112">A Windows 10 device</span></span>
- <span data-ttu-id="469f2-113">对设备的管理员权限</span><span class="sxs-lookup"><span data-stu-id="469f2-113">Administrator permission for the device</span></span>
- <span data-ttu-id="469f2-114">租户的全局或帐单管理员角色</span><span class="sxs-lookup"><span data-stu-id="469f2-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="469f2-115">安装 MSCommerce PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="469f2-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="469f2-116">您在 Windows 10 设备上安装**MSCommerce** PowerShell 模块后，再将其导入到每个启动的 PowerShell 会话中。</span><span class="sxs-lookup"><span data-stu-id="469f2-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="469f2-117">从[PowerShell 库](https://aka.ms/allowselfservicepurchase-powershell-gallery)下载**MSCommerce** PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="469f2-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="469f2-118">若要使用**PowerShellGet**安装**MSCommerce** PowerShell 模块，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="469f2-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="469f2-119">将 MSCommerce 导入 PowerShell 会话</span><span class="sxs-lookup"><span data-stu-id="469f2-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="469f2-120">在 Windows 10 设备上安装该模块后，再将其导入到每个启动的 PowerShell 会话中。</span><span class="sxs-lookup"><span data-stu-id="469f2-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="469f2-121">若要将其导入 PowerShell 会话，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="469f2-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="469f2-122">使用你的凭据连接到 MSCommerce</span><span class="sxs-lookup"><span data-stu-id="469f2-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="469f2-123">若要使用你的凭据连接到 PowerShell 模块，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="469f2-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="469f2-124">此命令将当前 PowerShell 会话连接到 Azure Active Directory 租户。</span><span class="sxs-lookup"><span data-stu-id="469f2-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="469f2-125">该命令将提示您输入要连接到的租户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="469f2-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="469f2-126">如果为您的凭据启用了多重身份验证，则可以使用交互式选项登录。</span><span class="sxs-lookup"><span data-stu-id="469f2-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="469f2-127">查看 AllowSelfServicePurchase 的详细信息</span><span class="sxs-lookup"><span data-stu-id="469f2-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="469f2-128">若要查看**AllowSelfServicePurchase**参数值的说明以及基于您的组织的默认状态，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="469f2-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="469f2-129">查看自助服务购买产品的列表及其状态</span><span class="sxs-lookup"><span data-stu-id="469f2-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="469f2-130">若要查看所有可用的自助服务购买产品的列表以及每个产品的状态，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="469f2-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="469f2-131">下表列出了可用的产品及其**产品 id**。</span><span class="sxs-lookup"><span data-stu-id="469f2-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="469f2-132">产品</span><span class="sxs-lookup"><span data-stu-id="469f2-132">Product</span></span> | <span data-ttu-id="469f2-133">Id</span><span class="sxs-lookup"><span data-stu-id="469f2-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="469f2-134">每个用户的电源应用程序</span><span class="sxs-lookup"><span data-stu-id="469f2-134">Power Apps per user</span></span> | <span data-ttu-id="469f2-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="469f2-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="469f2-136">每个用户的电源自动化</span><span class="sxs-lookup"><span data-stu-id="469f2-136">Power Automate per user</span></span> | <span data-ttu-id="469f2-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="469f2-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="469f2-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="469f2-138">Power BI Pro</span></span> | <span data-ttu-id="469f2-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="469f2-139">CFQ7TTC0L3PB</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="469f2-140">查看或设置 AllowSelfServicePurchase 的状态</span><span class="sxs-lookup"><span data-stu-id="469f2-140">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="469f2-141">查看可用于自助购买的产品列表后，可以查看或修改特定产品的设置。</span><span class="sxs-lookup"><span data-stu-id="469f2-141">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="469f2-142">若要获取特定产品的策略设置，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="469f2-142">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="469f2-143">若要为特定产品启用策略设置，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="469f2-143">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="469f2-144">若要禁用特定产品的策略设置，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="469f2-144">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="469f2-145">禁用 AllowSelfServicePurchase 的示例脚本</span><span class="sxs-lookup"><span data-stu-id="469f2-145">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="469f2-146">下面的示例演示如何导入**MSCommerce**模块，使用你的帐户登录，获取产品**Id**为 "自动执行" 功能，然后禁用该产品的 " **AllowSelfServicePurchase** "。</span><span class="sxs-lookup"><span data-stu-id="469f2-146">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="469f2-147">问题排查</span><span class="sxs-lookup"><span data-stu-id="469f2-147">Troubleshooting</span></span>

<span data-ttu-id="469f2-148">**问题**</span><span class="sxs-lookup"><span data-stu-id="469f2-148">**Problem**</span></span>

<span data-ttu-id="469f2-149">您会看到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="469f2-149">You see the following error message:</span></span>

    HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying
    connection was closed: An unexpected error occurred on a send.

<span data-ttu-id="469f2-150">这可能是由于较旧版本的传输层安全性（TLS）造成的。</span><span class="sxs-lookup"><span data-stu-id="469f2-150">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="469f2-151">若要连接此服务，您需要使用 TLS 1.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="469f2-151">To connect this service you need to use TLS 1.2 or greater</span></span>

<span data-ttu-id="469f2-152">**解决方案**</span><span class="sxs-lookup"><span data-stu-id="469f2-152">**Solution**</span></span>

<span data-ttu-id="469f2-153">升级到 TLS 1.2：[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="469f2-153">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
