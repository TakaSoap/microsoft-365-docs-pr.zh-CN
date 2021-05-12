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
ms.date: 03/18/2021
ms.openlocfilehash: 09161f69e72babe8270b339243d73444b93d9959
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333370"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="8bb44-103">将 AllowSelfServicePurchase 用于 MSCommerce PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="8bb44-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="8bb44-104">**MSCommerce** PowerShell 模块现已在 [PowerShell 库上提供](https://aka.ms/allowselfservicepurchase-powershell-gallery)。</span><span class="sxs-lookup"><span data-stu-id="8bb44-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="8bb44-105">该模块包括 **AllowSelfServicePurchase** 的 **PolicyID** 参数值，它允许您控制组织中用户是否可以进行自助购买。</span><span class="sxs-lookup"><span data-stu-id="8bb44-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="8bb44-106">您可以使用 **MSCommerce** PowerShell 模块：</span><span class="sxs-lookup"><span data-stu-id="8bb44-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="8bb44-107">查看 **AllowSelfServicePurchase** 参数值的默认状态 — 是启用还是禁用</span><span class="sxs-lookup"><span data-stu-id="8bb44-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="8bb44-108">查看适用产品的列表，以及自助服务购买是启用还是禁用</span><span class="sxs-lookup"><span data-stu-id="8bb44-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="8bb44-109">查看或修改特定产品的当前设置以启用或禁用它</span><span class="sxs-lookup"><span data-stu-id="8bb44-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="8bb44-110">要求</span><span class="sxs-lookup"><span data-stu-id="8bb44-110">Requirements</span></span>

<span data-ttu-id="8bb44-111">若要使用 **MSCommerce** PowerShell 模块，您需要：</span><span class="sxs-lookup"><span data-stu-id="8bb44-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="8bb44-112">Windows 10设备</span><span class="sxs-lookup"><span data-stu-id="8bb44-112">A Windows 10 device</span></span>
- <span data-ttu-id="8bb44-113">设备的管理员权限</span><span class="sxs-lookup"><span data-stu-id="8bb44-113">Administrator permission for the device</span></span>
- <span data-ttu-id="8bb44-114">租户的全局或帐单管理员角色</span><span class="sxs-lookup"><span data-stu-id="8bb44-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="8bb44-115">安装 MSCommerce PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="8bb44-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="8bb44-116">在设备上安装 **MSCommerce** PowerShell 模块一Windows 10，然后导入到您启动的每个 PowerShell 会话中。</span><span class="sxs-lookup"><span data-stu-id="8bb44-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="8bb44-117">从 [PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery)库下载 **MSCommerce** PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="8bb44-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="8bb44-118">若要使用 **PowerShellGet** 安装 **MSCommerce** PowerShell 模块，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8bb44-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="8bb44-119">将 MSCommerce 导入 PowerShell 会话</span><span class="sxs-lookup"><span data-stu-id="8bb44-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="8bb44-120">在设备上安装模块Windows 10，然后将其导入到您启动的每个 PowerShell 会话中。</span><span class="sxs-lookup"><span data-stu-id="8bb44-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="8bb44-121">若要将其导入 PowerShell 会话，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8bb44-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="8bb44-122">连接凭据访问 MSCommerce</span><span class="sxs-lookup"><span data-stu-id="8bb44-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="8bb44-123">若要使用凭据连接到 PowerShell 模块，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="8bb44-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="8bb44-124">此命令将当前 PowerShell 会话连接到 Azure Active Directory 租户。</span><span class="sxs-lookup"><span data-stu-id="8bb44-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="8bb44-125">该命令会提示你输入要连接到的租户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="8bb44-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="8bb44-126">如果为凭据启用了多重身份验证，则使用交互式选项登录。</span><span class="sxs-lookup"><span data-stu-id="8bb44-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="8bb44-127">查看 AllowSelfServicePurchase 的详细信息</span><span class="sxs-lookup"><span data-stu-id="8bb44-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="8bb44-128">若要查看 **AllowSelfServicePurchase** 参数值和默认状态的说明，请基于您的组织运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8bb44-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="8bb44-129">查看自助服务购买产品及其状态的列表</span><span class="sxs-lookup"><span data-stu-id="8bb44-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="8bb44-130">若要查看所有可用的自助式购买产品的列表以及每种产品的状态，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8bb44-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="8bb44-131">下表列出了可用的产品及其 **ProductId。**</span><span class="sxs-lookup"><span data-stu-id="8bb44-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="8bb44-132">产品</span><span class="sxs-lookup"><span data-stu-id="8bb44-132">Product</span></span> | <span data-ttu-id="8bb44-133">ProductId</span><span class="sxs-lookup"><span data-stu-id="8bb44-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="8bb44-134">Power Apps每个用户</span><span class="sxs-lookup"><span data-stu-id="8bb44-134">Power Apps per user</span></span> | <span data-ttu-id="8bb44-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="8bb44-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="8bb44-136">Power Automate每个用户</span><span class="sxs-lookup"><span data-stu-id="8bb44-136">Power Automate per user</span></span> | <span data-ttu-id="8bb44-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="8bb44-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="8bb44-138">Power AutomateRPA</span><span class="sxs-lookup"><span data-stu-id="8bb44-138">Power Automate RPA</span></span> | <span data-ttu-id="8bb44-139">CFQ7TTC0KXG6</span><span class="sxs-lookup"><span data-stu-id="8bb44-139">CFQ7TTC0KXG6</span></span>  |
| <span data-ttu-id="8bb44-140">Power BI Premium (独立) </span><span class="sxs-lookup"><span data-stu-id="8bb44-140">Power BI Premium (standalone)</span></span> | <span data-ttu-id="8bb44-141">CFQ7TTC0KXG7</span><span class="sxs-lookup"><span data-stu-id="8bb44-141">CFQ7TTC0KXG7</span></span>  |
| <span data-ttu-id="8bb44-142">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="8bb44-142">Power BI Pro</span></span> | <span data-ttu-id="8bb44-143">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="8bb44-143">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="8bb44-144">Project计划 1</span><span class="sxs-lookup"><span data-stu-id="8bb44-144">Project Plan 1</span></span> | <span data-ttu-id="8bb44-145">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="8bb44-145">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="8bb44-146">Project计划 3</span><span class="sxs-lookup"><span data-stu-id="8bb44-146">Project Plan 3</span></span> | <span data-ttu-id="8bb44-147">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="8bb44-147">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="8bb44-148">Visio计划 1</span><span class="sxs-lookup"><span data-stu-id="8bb44-148">Visio Plan 1</span></span> | <span data-ttu-id="8bb44-149">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="8bb44-149">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="8bb44-150">Visio计划 2</span><span class="sxs-lookup"><span data-stu-id="8bb44-150">Visio Plan 2</span></span> | <span data-ttu-id="8bb44-151">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="8bb44-151">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="8bb44-152">查看或设置 AllowSelfServicePurchase 的状态</span><span class="sxs-lookup"><span data-stu-id="8bb44-152">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="8bb44-153">查看可供自助购买的产品列表后，可以查看或修改特定产品的设置。</span><span class="sxs-lookup"><span data-stu-id="8bb44-153">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="8bb44-154">若要获取特定产品的策略设置，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8bb44-154">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="8bb44-155">若要为特定产品启用策略设置，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8bb44-155">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="8bb44-156">若要禁用特定产品的策略设置，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8bb44-156">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="8bb44-157">禁用 AllowSelfServicePurchase 的示例脚本</span><span class="sxs-lookup"><span data-stu-id="8bb44-157">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="8bb44-158">以下示例将引导您完成如何导入 **MSCommerce** 模块、使用您的帐户登录、获取 Power Automate 的 **ProductId，** 然后禁用该产品的 **AllowSelfServicePurchase。**</span><span class="sxs-lookup"><span data-stu-id="8bb44-158">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="8bb44-159">疑难解答</span><span class="sxs-lookup"><span data-stu-id="8bb44-159">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="8bb44-160">问题</span><span class="sxs-lookup"><span data-stu-id="8bb44-160">Problem</span></span>

<span data-ttu-id="8bb44-161">看到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="8bb44-161">You see the following error message:</span></span>

> <span data-ttu-id="8bb44-162">HandleError：未能检索 PolicyId 为"AllowSelfServicePurchase"的策略，ErrorMessage - 基础连接已关闭：发送时发生意外错误。</span><span class="sxs-lookup"><span data-stu-id="8bb44-162">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="8bb44-163">这可能是由于传输层安全性的较旧版本 (TLS) 。</span><span class="sxs-lookup"><span data-stu-id="8bb44-163">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="8bb44-164">若要连接此服务，你需要使用 TLS 1.2 或更大</span><span class="sxs-lookup"><span data-stu-id="8bb44-164">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="8bb44-165">解决方案</span><span class="sxs-lookup"><span data-stu-id="8bb44-165">Solution</span></span>

<span data-ttu-id="8bb44-166">升级到 TLS 1.2： [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="8bb44-166">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
