---
title: GDPR
description: Microsoft 技术指南 - 用于提交删除请求的 FASTTRACK 迁移工具集
keywords: FastTrack 迁移, Microsoft 365 教育版, Microsoft 365 文档, GDPR
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: mohitku
author: MohitKumar
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 10a983297640ac4b65aaf181ef35ac19918e74fe
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547373"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a><span data-ttu-id="6b313-104">用于提交删除请求的 FastTrack 迁移工具集</span><span class="sxs-lookup"><span data-stu-id="6b313-104">FastTrack Migration Toolset for Submitting Delete Request</span></span>

## <a name="toolset-purpose"></a><span data-ttu-id="6b313-105">工具集用途</span><span class="sxs-lookup"><span data-stu-id="6b313-105">Toolset purpose</span></span>

<span data-ttu-id="6b313-p101">如果你是目前正在使用 FastTrack 迁移的客户，那么删除用户帐户将不会删除由 Microsoft FastTrack 团队保留的数据副本（该副本仅保留用于完成迁移）。在迁移过程中，如果你希望 Microsoft FastTrack 团队同时删除数据副本，请通过此工具集提交请求。在正常业务过程中，Microsoft FastTrack 将在迁移完成后立即删除所有数据副本。</span><span class="sxs-lookup"><span data-stu-id="6b313-p101">In the event that you are a customer currently engaged in FastTrack migrations, deleting the user account will not delete the data copy held by the Microsoft FastTrack team, which is held for the sole purpose of completing the migration. If during the migration you would like the Microsoft FastTrack team to also delete the data copy, submit a request via this tool set. In the ordinary course of business, Microsoft FastTrack will delete all data copies once the migration is complete.</span></span>

### <a name="supported-platforms"></a><span data-ttu-id="6b313-109">支持的平台</span><span class="sxs-lookup"><span data-stu-id="6b313-109">Supported platforms</span></span>

<span data-ttu-id="6b313-p102">Microsoft 支持 Windows 平台和 PowerShell 控制台中此工具集的初始版本。此工具集支持以下已知平台：</span><span class="sxs-lookup"><span data-stu-id="6b313-p102">Microsoft supports the initial release of this  toolset in the Windows platform and PowerShell console. The following known platforms are supported by this toolset:</span></span>

<span data-ttu-id="6b313-112">***表 1 - 此工具集支持的平台***</span><span class="sxs-lookup"><span data-stu-id="6b313-112">***Table 1 — Platforms supported by this toolset***</span></span>

****

|<span data-ttu-id="6b313-113">PowerShell 版本</span><span class="sxs-lookup"><span data-stu-id="6b313-113">PowerShell version</span></span>|<span data-ttu-id="6b313-114">Windows 7</span><span class="sxs-lookup"><span data-stu-id="6b313-114">Windows 7</span></span>|<span data-ttu-id="6b313-115">Windows 8</span><span class="sxs-lookup"><span data-stu-id="6b313-115">Windows 8</span></span>|<span data-ttu-id="6b313-116">Windows 10</span><span class="sxs-lookup"><span data-stu-id="6b313-116">Windows 10</span></span>|<span data-ttu-id="6b313-117">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="6b313-117">Windows Server 2012</span></span>|<span data-ttu-id="6b313-118">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="6b313-118">Windows Server 2016</span></span>|
|:---:|:---:|:---:|:---:|:---:|:---:|
|<span data-ttu-id="6b313-119">5.0</span><span class="sxs-lookup"><span data-stu-id="6b313-119">5.0</span></span>|<span data-ttu-id="6b313-120">不支持</span><span class="sxs-lookup"><span data-stu-id="6b313-120">Not Supported</span></span>|<span data-ttu-id="6b313-121">支持</span><span class="sxs-lookup"><span data-stu-id="6b313-121">Supported</span></span>|<span data-ttu-id="6b313-122">支持</span><span class="sxs-lookup"><span data-stu-id="6b313-122">Supported</span></span>|<span data-ttu-id="6b313-123">支持</span><span class="sxs-lookup"><span data-stu-id="6b313-123">Supported</span></span>|<span data-ttu-id="6b313-124">支持</span><span class="sxs-lookup"><span data-stu-id="6b313-124">Supported</span></span>|
|<span data-ttu-id="6b313-125">5.1</span><span class="sxs-lookup"><span data-stu-id="6b313-125">5.1</span></span>|<span data-ttu-id="6b313-126">不支持</span><span class="sxs-lookup"><span data-stu-id="6b313-126">Not Supported</span></span>|<span data-ttu-id="6b313-127">支持</span><span class="sxs-lookup"><span data-stu-id="6b313-127">Supported</span></span>|<span data-ttu-id="6b313-128">支持</span><span class="sxs-lookup"><span data-stu-id="6b313-128">Supported</span></span>|<span data-ttu-id="6b313-129">支持</span><span class="sxs-lookup"><span data-stu-id="6b313-129">Supported</span></span>|<span data-ttu-id="6b313-130">支持</span><span class="sxs-lookup"><span data-stu-id="6b313-130">Supported</span></span>|
|

### <a name="obtaining-the-toolset"></a><span data-ttu-id="6b313-131">获取工具集</span><span class="sxs-lookup"><span data-stu-id="6b313-131">Obtaining the toolset</span></span>

<span data-ttu-id="6b313-p103">PowerShell 控制台应用程序上的 PowerShell 库中提供此工具集。若要查找和加载此 cmdlet 模块，首先在管理员模式下打开 PowerShell，以使其具有安装模块的相应权限。如果以前未使用过 PowerShell，请转到 Windows 任务栏，并在搜索框中键入“PowerShell”。右键单击并选择控制台应用，然后选择“以管理员身份运行”\*\*\*\*，单击“是”\*\*\*\* 运行 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6b313-p103">This toolset is available in the PowerShell Gallery on the PowerShell console application.  To locate and load this cmdlet module, first open PowerShell in administrator mode so it has the appropriate permissions to install the module. If you have not used PowerShell previously go to your Windows Task Bar and in the search box type “PowerShell”. Select the console app using right-click and choose **Run as administrator**, then click **Yes** to run Windows PowerShell.</span></span>

![PowerShell - 以管理员身份运行](../media/fasttrack-powershell_image.png)

![PowerShell - 允许应用进行更改](../media/fasttrack-run-powershell_image.png)

<span data-ttu-id="6b313-138">现在控制台已打开，需要设置脚本执行的权限。</span><span class="sxs-lookup"><span data-stu-id="6b313-138">Now that the console is open, you need to set permissions for script execution.</span></span> <span data-ttu-id="6b313-139">键入以下命令以允许脚本运行：</span><span class="sxs-lookup"><span data-stu-id="6b313-139">Type the following command to allow the scripts to run:</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope Process
```

<span data-ttu-id="6b313-140">系统将提示你确认此操作，因为管理员可以自行决定更改范围。</span><span class="sxs-lookup"><span data-stu-id="6b313-140">You will be prompted to confirm this action, as the administrator can change the scope at their discretion.</span></span>

<span data-ttu-id="6b313-141">***设置执行策略***</span><span class="sxs-lookup"><span data-stu-id="6b313-141">***Set Execution Policy***</span></span>

![在 PowerShell 中设置执行策略更改](../media/powershell-set-execution-policy_image.png)

<span data-ttu-id="6b313-143">现在，已将控制台设置为允许脚本，运行下一个命令以安装模块：</span><span class="sxs-lookup"><span data-stu-id="6b313-143">Now that the console is set to allow the script, run this next command to install the module:</span></span>

```powershell
Install-Module -Name Microsoft.FastTrack -Repository PSGallery -WarningAction SilentlyContinue -Force
```

### <a name="prerequisites-for-module"></a><span data-ttu-id="6b313-144">模块的先决条件</span><span class="sxs-lookup"><span data-stu-id="6b313-144">Prerequisites for module</span></span>

<span data-ttu-id="6b313-p105">若要成功执行此模块，可能需要安装独立模块以供使用（如果尚未安装）。可能需要重启 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="6b313-p105">To successfully execute this module, you may need to install dependent modules for use if they are not already installed. You may need to restart PowerShell.</span></span>

<span data-ttu-id="6b313-147">若要提交 DSR，必须首先使用你的 Office 365 凭据登录。</span><span class="sxs-lookup"><span data-stu-id="6b313-147">In order to submit a DSR, you must first log in using your Office 365 credentials.</span></span> <span data-ttu-id="6b313-148">输入正确的凭据将验证全局管理员状态并收集租户信息。</span><span class="sxs-lookup"><span data-stu-id="6b313-148">Entering the proper credentials will validate your global administrator status and collect tenant information.</span></span>

```powershell
Login-FastTrackAccount -ApiKey <API Key provided by FastTrack MVM>
```

<span data-ttu-id="6b313-149">成功登录后，将存储凭据和密钥，以供 FastTrack 模块在当前 PowerShell 会话的其余部分使用。</span><span class="sxs-lookup"><span data-stu-id="6b313-149">Once successfully logged in, the credentials and key will be stored for use with FastTrack modules for the remainder of the current PowerShell session.</span></span>

<span data-ttu-id="6b313-150">如果需要连接到云环境（而非商业环境），在以下其中一个有效环境中，需要向 *Login* 命令添加 *-Environment*：</span><span class="sxs-lookup"><span data-stu-id="6b313-150">If you need to connect to a cloud environment, other than commercial, *-Environment* will need to be added to *Log in* command with one of the following valid environments:</span></span>

- <span data-ttu-id="6b313-151">AzureCloud</span><span class="sxs-lookup"><span data-stu-id="6b313-151">AzureCloud</span></span>
- <span data-ttu-id="6b313-152">AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="6b313-152">AzureChinaCloud</span></span>
- <span data-ttu-id="6b313-153">AzureGermanCloud</span><span class="sxs-lookup"><span data-stu-id="6b313-153">AzureGermanCloud</span></span>
- <span data-ttu-id="6b313-154">AzureUSGovernmentCloud</span><span class="sxs-lookup"><span data-stu-id="6b313-154">AzureUSGovernmentCloud</span></span>

```powershell
Login-FastTrackAccount -ApiKey <API Key provided by FastTrack MVM> -Environment <cloud environment>
```

<span data-ttu-id="6b313-155">若要提交 DSR 请求，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="6b313-155">To submit a DSR request, run the following command:</span></span>

```powershell
Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail SubjectUserEmail@mycompany.com
```

<span data-ttu-id="6b313-156">成功后，cmdlet 将返回事物 ID 对象。</span><span class="sxs-lookup"><span data-stu-id="6b313-156">On success, the cmdlet will return a Transaction ID object.</span></span> <span data-ttu-id="6b313-157">请保留事物 ID。</span><span class="sxs-lookup"><span data-stu-id="6b313-157">Please retain the Transaction ID.</span></span>

#### <a name="checking-the-status-of-a-request-transaction"></a><span data-ttu-id="6b313-158">检查请求事务的状态</span><span class="sxs-lookup"><span data-stu-id="6b313-158">Checking the status of a request transaction</span></span>

<span data-ttu-id="6b313-159">使用先前获取的事物 ID 运行以下函数：</span><span class="sxs-lookup"><span data-stu-id="6b313-159">Run the following function using the previously obtained Transaction ID:</span></span>

```powershell
Get-FastTrackGdprDsrRequest -TransactionID "YourTransactionID"
```

#### <a name="transaction-status-codes"></a><span data-ttu-id="6b313-160">事务状态代码</span><span class="sxs-lookup"><span data-stu-id="6b313-160">Transaction Status Codes</span></span>

|<span data-ttu-id="6b313-161">事务</span><span class="sxs-lookup"><span data-stu-id="6b313-161">Transaction</span></span>|<span data-ttu-id="6b313-162">状态</span><span class="sxs-lookup"><span data-stu-id="6b313-162">Status</span></span>|
|---|---|
|<span data-ttu-id="6b313-163">**创建时间**</span><span class="sxs-lookup"><span data-stu-id="6b313-163">**Created**</span></span>|<span data-ttu-id="6b313-164">已创建请求。</span><span class="sxs-lookup"><span data-stu-id="6b313-164">Request has been created.</span></span>|
|<span data-ttu-id="6b313-165">**失败**</span><span class="sxs-lookup"><span data-stu-id="6b313-165">**Failed**</span></span>|<span data-ttu-id="6b313-166">无法创建请求，请重新提交，或联系支持人员。</span><span class="sxs-lookup"><span data-stu-id="6b313-166">Request failed to create, please resubmit, or contact support.</span></span>|
|<span data-ttu-id="6b313-167">**已完成**</span><span class="sxs-lookup"><span data-stu-id="6b313-167">**Completed**</span></span>|<span data-ttu-id="6b313-168">请求已完成并已被清理。</span><span class="sxs-lookup"><span data-stu-id="6b313-168">Request has been completed and sanitized.</span></span>|
|

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->

## <a name="learn-more"></a><span data-ttu-id="6b313-169">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="6b313-169">Learn more</span></span>

[<span data-ttu-id="6b313-170">Microsoft 信任中心</span><span class="sxs-lookup"><span data-stu-id="6b313-170">Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
