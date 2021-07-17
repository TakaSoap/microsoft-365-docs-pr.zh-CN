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
ms.openlocfilehash: 77cb1c753db22929ea2c3d14226a3927e6406b89
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461359"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="f5b59-103">将 AllowSelfServicePurchase 用于 MSCommerce PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="f5b59-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="f5b59-104">**MSCommerce** PowerShell 模块现已在 [PowerShell 库上提供](https://aka.ms/allowselfservicepurchase-powershell-gallery)。</span><span class="sxs-lookup"><span data-stu-id="f5b59-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="f5b59-105">该模块包括 **AllowSelfServicePurchase** 的 **PolicyID** 参数值，它允许您控制组织中用户是否可以进行自助购买。</span><span class="sxs-lookup"><span data-stu-id="f5b59-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="f5b59-106">您可以使用 **MSCommerce** PowerShell 模块：</span><span class="sxs-lookup"><span data-stu-id="f5b59-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="f5b59-107">查看 **AllowSelfServicePurchase** 参数值的默认状态 — 是启用还是禁用</span><span class="sxs-lookup"><span data-stu-id="f5b59-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="f5b59-108">查看适用产品的列表，以及自助服务购买是启用还是禁用</span><span class="sxs-lookup"><span data-stu-id="f5b59-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="f5b59-109">查看或修改特定产品的当前设置以启用或禁用它</span><span class="sxs-lookup"><span data-stu-id="f5b59-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="f5b59-110">Requirements</span><span class="sxs-lookup"><span data-stu-id="f5b59-110">Requirements</span></span>

<span data-ttu-id="f5b59-111">若要使用 **MSCommerce** PowerShell 模块，您需要：</span><span class="sxs-lookup"><span data-stu-id="f5b59-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="f5b59-112">Windows 10设备</span><span class="sxs-lookup"><span data-stu-id="f5b59-112">A Windows 10 device</span></span>
- <span data-ttu-id="f5b59-113">PowerShell 5 或以下产品。</span><span class="sxs-lookup"><span data-stu-id="f5b59-113">PowerShell 5 or below.</span></span> <span data-ttu-id="f5b59-114">当前，此模块不支持 PowerShell 6.x/7.x。</span><span class="sxs-lookup"><span data-stu-id="f5b59-114">Currently, PowerShell 6.x/7.x isn't supported with this module.</span></span>
- <span data-ttu-id="f5b59-115">设备的管理员权限</span><span class="sxs-lookup"><span data-stu-id="f5b59-115">Administrator permission for the device</span></span>
- <span data-ttu-id="f5b59-116">租户的全局或帐单管理员角色</span><span class="sxs-lookup"><span data-stu-id="f5b59-116">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="f5b59-117">安装 MSCommerce PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="f5b59-117">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="f5b59-118">在设备上安装 **MSCommerce** PowerShell 模块一Windows 10，然后导入到您启动的每个 PowerShell 会话中。</span><span class="sxs-lookup"><span data-stu-id="f5b59-118">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="f5b59-119">从 [PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery)库下载 **MSCommerce** PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="f5b59-119">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="f5b59-120">若要使用 **PowerShellGet** 安装 **MSCommerce** PowerShell 模块，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f5b59-120">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="f5b59-121">将 MSCommerce 导入 PowerShell 会话</span><span class="sxs-lookup"><span data-stu-id="f5b59-121">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="f5b59-122">在设备上安装模块Windows 10，然后将其导入到您启动的每个 PowerShell 会话中。</span><span class="sxs-lookup"><span data-stu-id="f5b59-122">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="f5b59-123">若要将其导入 PowerShell 会话，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f5b59-123">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="f5b59-124">连接凭据访问 MSCommerce</span><span class="sxs-lookup"><span data-stu-id="f5b59-124">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="f5b59-125">若要使用凭据连接到 PowerShell 模块，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="f5b59-125">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="f5b59-126">此命令将当前 PowerShell 会话连接到 Azure Active Directory 租户。</span><span class="sxs-lookup"><span data-stu-id="f5b59-126">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="f5b59-127">该命令会提示你输入要连接到的租户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="f5b59-127">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="f5b59-128">如果为凭据启用了多重身份验证，则使用交互式选项登录。</span><span class="sxs-lookup"><span data-stu-id="f5b59-128">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="f5b59-129">查看 AllowSelfServicePurchase 的详细信息</span><span class="sxs-lookup"><span data-stu-id="f5b59-129">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="f5b59-130">若要查看 **AllowSelfServicePurchase** 参数值和默认状态的说明，请基于您的组织运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f5b59-130">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="f5b59-131">查看自助服务购买产品及其状态的列表</span><span class="sxs-lookup"><span data-stu-id="f5b59-131">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="f5b59-132">若要查看所有可用的自助式购买产品的列表以及每种产品的状态，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f5b59-132">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="f5b59-133">下表列出了可用的产品及其 **ProductId。**</span><span class="sxs-lookup"><span data-stu-id="f5b59-133">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="f5b59-134">产品</span><span class="sxs-lookup"><span data-stu-id="f5b59-134">Product</span></span> | <span data-ttu-id="f5b59-135">ProductId</span><span class="sxs-lookup"><span data-stu-id="f5b59-135">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="f5b59-136">Power Apps每个用户</span><span class="sxs-lookup"><span data-stu-id="f5b59-136">Power Apps per user</span></span> | <span data-ttu-id="f5b59-137">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="f5b59-137">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="f5b59-138">Power Automate每个用户</span><span class="sxs-lookup"><span data-stu-id="f5b59-138">Power Automate per user</span></span> | <span data-ttu-id="f5b59-139">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="f5b59-139">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="f5b59-140">Power AutomateRPA</span><span class="sxs-lookup"><span data-stu-id="f5b59-140">Power Automate RPA</span></span> | <span data-ttu-id="f5b59-141">CFQ7TTC0KXG6</span><span class="sxs-lookup"><span data-stu-id="f5b59-141">CFQ7TTC0KXG6</span></span>  |
| <span data-ttu-id="f5b59-142">Power BI Premium (独立) </span><span class="sxs-lookup"><span data-stu-id="f5b59-142">Power BI Premium (standalone)</span></span> | <span data-ttu-id="f5b59-143">CFQ7TTC0KXG7</span><span class="sxs-lookup"><span data-stu-id="f5b59-143">CFQ7TTC0KXG7</span></span>  |
| <span data-ttu-id="f5b59-144">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="f5b59-144">Power BI Pro</span></span> | <span data-ttu-id="f5b59-145">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="f5b59-145">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="f5b59-146">Project 计划 1</span><span class="sxs-lookup"><span data-stu-id="f5b59-146">Project Plan 1</span></span> | <span data-ttu-id="f5b59-147">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="f5b59-147">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="f5b59-148">Project 计划 3</span><span class="sxs-lookup"><span data-stu-id="f5b59-148">Project Plan 3</span></span> | <span data-ttu-id="f5b59-149">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="f5b59-149">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="f5b59-150">Visio 计划 1</span><span class="sxs-lookup"><span data-stu-id="f5b59-150">Visio Plan 1</span></span> | <span data-ttu-id="f5b59-151">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="f5b59-151">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="f5b59-152">Visio 计划 2</span><span class="sxs-lookup"><span data-stu-id="f5b59-152">Visio Plan 2</span></span> | <span data-ttu-id="f5b59-153">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="f5b59-153">CFQ7TTC0KXN8</span></span> |
| <span data-ttu-id="f5b59-154">Windows 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f5b59-154">Windows 365 Enterprise</span></span> | <span data-ttu-id="f5b59-155">CFQ7TTC0HTC9</span><span class="sxs-lookup"><span data-stu-id="f5b59-155">CFQ7TTC0HHS9</span></span> |
| <span data-ttu-id="f5b59-156">Windows 365 商业版</span><span class="sxs-lookup"><span data-stu-id="f5b59-156">Windows 365 Business</span></span> | <span data-ttu-id="f5b59-157">CFQ7TTC0J203</span><span class="sxs-lookup"><span data-stu-id="f5b59-157">CFQ7TTC0J203</span></span> |
| <span data-ttu-id="f5b59-158">Windows混合权益的 Windows 365 商业版</span><span class="sxs-lookup"><span data-stu-id="f5b59-158">Windows 365 Business with Windows Hybrid Benefit</span></span> | <span data-ttu-id="f5b59-159">CFQ7TTC0HX99</span><span class="sxs-lookup"><span data-stu-id="f5b59-159">CFQ7TTC0HX99</span></span> |
## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="f5b59-160">查看或设置 AllowSelfServicePurchase 的状态</span><span class="sxs-lookup"><span data-stu-id="f5b59-160">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="f5b59-161">查看可供自助购买的产品列表后，可以查看或修改特定产品的设置。</span><span class="sxs-lookup"><span data-stu-id="f5b59-161">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="f5b59-162">若要获取特定产品的策略设置，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f5b59-162">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="f5b59-163">若要为特定产品启用策略设置，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f5b59-163">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="f5b59-164">若要禁用特定产品的策略设置，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f5b59-164">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="f5b59-165">禁用 AllowSelfServicePurchase 的示例脚本</span><span class="sxs-lookup"><span data-stu-id="f5b59-165">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="f5b59-166">以下示例将引导您完成如何导入 **MSCommerce** 模块、使用您的帐户登录、获取 Power Automate 的 **ProductId，** 然后禁用该产品的 **AllowSelfServicePurchase。**</span><span class="sxs-lookup"><span data-stu-id="f5b59-166">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="f5b59-167">疑难解答</span><span class="sxs-lookup"><span data-stu-id="f5b59-167">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="f5b59-168">问题</span><span class="sxs-lookup"><span data-stu-id="f5b59-168">Problem</span></span>

<span data-ttu-id="f5b59-169">看到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="f5b59-169">You see the following error message:</span></span>

> <span data-ttu-id="f5b59-170">HandleError：未能检索 PolicyId 为"AllowSelfServicePurchase"的策略，ErrorMessage - 基础连接已关闭：发送时发生意外错误。</span><span class="sxs-lookup"><span data-stu-id="f5b59-170">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="f5b59-171">这可能是由于传输层安全性的较旧版本 (TLS) 。</span><span class="sxs-lookup"><span data-stu-id="f5b59-171">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="f5b59-172">若要连接此服务，你需要使用 TLS 1.2 或更大</span><span class="sxs-lookup"><span data-stu-id="f5b59-172">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="f5b59-173">解决方案</span><span class="sxs-lookup"><span data-stu-id="f5b59-173">Solution</span></span>

<span data-ttu-id="f5b59-174">升级到 TLS 1.2： (/mem/configmgr/core/plan-design/security/enable-tls-1-2) </span><span class="sxs-lookup"><span data-stu-id="f5b59-174">Upgrade to TLS 1.2: (/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->

## <a name="related-content"></a><span data-ttu-id="f5b59-175">相关内容</span><span class="sxs-lookup"><span data-stu-id="f5b59-175">Related content</span></span>

<span data-ttu-id="f5b59-176">[管理自助服务购买 (管理)  (](manage-self-service-purchases-admins.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="f5b59-176">[Manage self-service purchases (Admin)](manage-self-service-purchases-admins.md) (article)</span></span>

<span data-ttu-id="f5b59-177">[自助服务购买常见问题 (](self-service-purchase-faq.yml) 文章) </span><span class="sxs-lookup"><span data-stu-id="f5b59-177">[Self-service purchase FAQ](self-service-purchase-faq.yml) (article)</span></span>
