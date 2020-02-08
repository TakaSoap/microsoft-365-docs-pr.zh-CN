---
title: GDPR
description: Microsoft 技术指南 - 用于提交删除请求的 FASTTRACK 迁移工具集
keywords: FastTrack 迁移, Microsoft 365 教育版, Microsoft 365 文档, GDPR
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
ms.prod: Microsoft-365-enterprise
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
ms.openlocfilehash: 89ddb00045e2a17821ef2e841ad9a9b4c38d2219
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596459"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a><span data-ttu-id="924f4-104">用于提交删除请求的 FastTrack 迁移工具集</span><span class="sxs-lookup"><span data-stu-id="924f4-104">FastTrack Migration Toolset for Submitting Delete Request</span></span>

## <a name="toolset-purpose"></a><span data-ttu-id="924f4-105">工具集用途</span><span class="sxs-lookup"><span data-stu-id="924f4-105">Toolset purpose</span></span>

<span data-ttu-id="924f4-p101">如果你是目前正在使用 FastTrack 迁移的客户，那么删除 Office 365 用户帐户将不会删除由 Microsoft FastTrack 团队保留的数据副本（该副本仅保留用于完成迁移）。在迁移过程中，如果你希望 Microsoft FastTrack 团队同时删除数据副本，请通过此工具集提交请求。在正常业务过程中，Microsoft FastTrack 将在迁移完成后立即删除所有数据副本。</span><span class="sxs-lookup"><span data-stu-id="924f4-p101">In the event that you are a customer currently engaged in FastTrack migrations, deleting the Office 365 user account will not delete the data copy held by the Microsoft FastTrack team, which is held for the sole purpose of completing the migration. If during the migration you would like the Microsoft FastTrack team to also delete the data copy, submit a request via this tool set. In the ordinary course of business, Microsoft FastTrack will delete all data copies once the migration is complete.</span></span>

### <a name="supported-platforms"></a><span data-ttu-id="924f4-109">支持的平台</span><span class="sxs-lookup"><span data-stu-id="924f4-109">Supported platforms</span></span>
<span data-ttu-id="924f4-p102">Microsoft 支持 Windows 平台和 PowerShell 控制台中此工具集的初始版本。此工具集支持以下已知平台：</span><span class="sxs-lookup"><span data-stu-id="924f4-p102">Microsoft supports the initial release of this  toolset in the Windows platform and PowerShell console. The following known platforms are supported by this toolset:</span></span>
 
<span data-ttu-id="924f4-112">***表 1 - 此工具集支持的平台***</span><span class="sxs-lookup"><span data-stu-id="924f4-112">***Table 1 — Platforms supported by this toolset***</span></span>
 
<!--start table here HEADER -->
 
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
| |<span data-ttu-id="924f4-113">**Windows 7**</span><span class="sxs-lookup"><span data-stu-id="924f4-113">**Windows 7**</span></span>|<span data-ttu-id="924f4-114">**Windows 8**</span><span class="sxs-lookup"><span data-stu-id="924f4-114">**Windows 8**</span></span>|<span data-ttu-id="924f4-115">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="924f4-115">**Windows 10**</span></span>|<span data-ttu-id="924f4-116">**Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="924f4-116">**Windows Server 2012**</span></span>|<span data-ttu-id="924f4-117">**Windows Server 2016**</span><span class="sxs-lookup"><span data-stu-id="924f4-117">**Windows Server 2016**</span></span>|
|<span data-ttu-id="924f4-118">PS 5.0</span><span class="sxs-lookup"><span data-stu-id="924f4-118">PS 5.0</span></span>|<span data-ttu-id="924f4-119">不</span><span class="sxs-lookup"><span data-stu-id="924f4-119">Not</span></span><br/><span data-ttu-id="924f4-120">支持</span><span class="sxs-lookup"><span data-stu-id="924f4-120">Supported</span></span>|<span data-ttu-id="924f4-121">支持</span><span class="sxs-lookup"><span data-stu-id="924f4-121">Supported</span></span>|<span data-ttu-id="924f4-122">支持</span><span class="sxs-lookup"><span data-stu-id="924f4-122">Supported</span></span>|<span data-ttu-id="924f4-123">支持</span><span class="sxs-lookup"><span data-stu-id="924f4-123">Supported</span></span>|<span data-ttu-id="924f4-124">支持</span><span class="sxs-lookup"><span data-stu-id="924f4-124">Supported</span></span>|
|<span data-ttu-id="924f4-125">PS 5.1</span><span class="sxs-lookup"><span data-stu-id="924f4-125">PS 5.1</span></span>|<span data-ttu-id="924f4-126">不</span><span class="sxs-lookup"><span data-stu-id="924f4-126">Not</span></span><br/><span data-ttu-id="924f4-127">支持</span><span class="sxs-lookup"><span data-stu-id="924f4-127">Supported</span></span>|<span data-ttu-id="924f4-128">支持</span><span class="sxs-lookup"><span data-stu-id="924f4-128">Supported</span></span>|<span data-ttu-id="924f4-129">支持</span><span class="sxs-lookup"><span data-stu-id="924f4-129">Supported</span></span>|<span data-ttu-id="924f4-130">支持</span><span class="sxs-lookup"><span data-stu-id="924f4-130">Supported</span></span>|<span data-ttu-id="924f4-131">支持</span><span class="sxs-lookup"><span data-stu-id="924f4-131">Supported</span></span>|
|||
 
<!-- end of table -->

### <a name="obtaining-the-toolset"></a><span data-ttu-id="924f4-132">获取工具集</span><span class="sxs-lookup"><span data-stu-id="924f4-132">Obtaining the toolset</span></span>

<span data-ttu-id="924f4-p103">PowerShell 控制台应用程序上的 PowerShell 库中提供此工具集。若要查找和加载此 cmdlet 模块，首先在管理员模式下打开 PowerShell，以使其具有安装模块的相应权限。如果以前未使用过 PowerShell，请转到 Windows 任务栏，并在搜索框中键入“PowerShell”。右键单击并选择控制台应用，然后选择“以管理员身份运行”\*\*\*\*，单击“是”\*\*\*\* 运行 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="924f4-p103">This toolset is available in the PowerShell Gallery on the PowerShell console application.  To locate and load this cmdlet module, first open PowerShell in administrator mode so it has the appropriate permissions to install the module. If you have not used PowerShell previously go to your Windows Task Bar and in the search box type “PowerShell”. Select the console app using right-click and choose **Run as administrator**, then click **Yes** to run Windows PowerShell.</span></span>

![PowerShell - 以管理员身份运行](media/fasttrack-powershell_image.png)

![PowerShell - 允许应用进行更改](media/fasttrack-run-powershell_image.png)

<span data-ttu-id="924f4-p104">打开控制台后，需要设置用于脚本执行的权限。键入以下命令以允许脚本运行：“Set-ExecutionPolicy - ExecutionPolicy: Bypass - Scope:Process”</span><span class="sxs-lookup"><span data-stu-id="924f4-p104">Now that the console is open, you need to set permissions for script execution. Type the following command to allow the scripts to run: ‘Set-ExecutionPolicy — ExecutionPolicy: Bypass — Scope: Process’</span></span>

<span data-ttu-id="924f4-141">系统将提示你确认此操作，因为管理员可以自行决定更改范围。</span><span class="sxs-lookup"><span data-stu-id="924f4-141">You will be prompted to confirm this action, as the administrator can change the scope at their discretion.</span></span>

<span data-ttu-id="924f4-142">***设置执行策略***</span><span class="sxs-lookup"><span data-stu-id="924f4-142">***Set Execution Policy***</span></span>

![在 PowerShell 中设置执行策略更改](media/powershell-set-execution-policy_image.png)

<span data-ttu-id="924f4-144">现在，已将控制台设置为允许脚本，运行下一个命令以安装模块：</span><span class="sxs-lookup"><span data-stu-id="924f4-144">Now that the console is set to allow the script,  run this next command to install the module:</span></span>

><span data-ttu-id="924f4-145">`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery \`</span><span class="sxs-lookup"><span data-stu-id="924f4-145">`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery \`</span></span>
>        
>               -WarningAction: SilentlyContinue `
>               -Force’

### <a name="prerequisites-for-module"></a><span data-ttu-id="924f4-146">模块的先决条件</span><span class="sxs-lookup"><span data-stu-id="924f4-146">Prerequisites for module</span></span>
<span data-ttu-id="924f4-p105">若要成功执行此模块，可能需要安装独立模块以供使用（如果尚未安装）。可能需要重启 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="924f4-p105">To successfully execute this module, you may need to install dependent modules for use if they are not already installed. You may need to restart PowerShell.</span></span>  

<span data-ttu-id="924f4-149">为了提交 DSR，必须首先使用你的 Office 365 凭据登录：输入正确的凭据将验证你的全局管理员状态并收集租户信息。</span><span class="sxs-lookup"><span data-stu-id="924f4-149">In order to submit a DSR, you must first log in using your Office 365 credentials — entering the proper credentials will validate your global administrator status and collect tenant information.</span></span> 

<span data-ttu-id="924f4-150">**Login-FastTrackAccount -ApiKey：\<由 FastTrack MVM 提供的 API 密钥\>**</span><span class="sxs-lookup"><span data-stu-id="924f4-150">**Login-FastTrackAccount -ApiKey: \<API Key provided by FastTrack MVM\>**</span></span>

<span data-ttu-id="924f4-151">成功登录后，将存储凭据和密钥，以供 FastTrack 模块在当前 PowerShell 会话的其余部分使用。</span><span class="sxs-lookup"><span data-stu-id="924f4-151">Once successfully logged in, the credentials and key will be stored for use with FastTrack modules for the remainder of the current PowerShell session.</span></span>

<span data-ttu-id="924f4-152">如果需要连接到云环境（而非商业环境），在以下其中一个有效环境中，需要向 *Login* 命令添加 *-Environment*：</span><span class="sxs-lookup"><span data-stu-id="924f4-152">If you need to connect to a cloud environment, other than commercial, *-Environment* will need to be added to *Log in* command with one of the following valid environments:</span></span>
- <span data-ttu-id="924f4-153">AzureCloud</span><span class="sxs-lookup"><span data-stu-id="924f4-153">AzureCloud</span></span>
- <span data-ttu-id="924f4-154">AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="924f4-154">AzureChinaCloud</span></span>
- <span data-ttu-id="924f4-155">AzureGermanCloud</span><span class="sxs-lookup"><span data-stu-id="924f4-155">AzureGermanCloud</span></span>
- <span data-ttu-id="924f4-156">AzureUSGovernmentCloud</span><span class="sxs-lookup"><span data-stu-id="924f4-156">AzureUSGovernmentCloud</span></span>

<span data-ttu-id="924f4-157">**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <cloud environment\>**</span><span class="sxs-lookup"><span data-stu-id="924f4-157">**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <cloud environment\>**</span></span>

<span data-ttu-id="924f4-158">若要提交 DSR 请求，请运行以下命令：Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com</span><span class="sxs-lookup"><span data-stu-id="924f4-158">To submit a DSR request, run the following command: Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com</span></span>

<span data-ttu-id="924f4-p106">成功后，cmdlet 将返回事务 ID 对象。请保留此事务 ID。</span><span class="sxs-lookup"><span data-stu-id="924f4-p106">On success — the cmdlet will return a Transaction ID object. Please retain the Transaction ID.</span></span>


#### <a name="checking-the-status-of-a-request-transaction"></a><span data-ttu-id="924f4-161">检查请求事务的状态</span><span class="sxs-lookup"><span data-stu-id="924f4-161">Checking the status of a request transaction</span></span>

<span data-ttu-id="924f4-162">使用以前获取的事务 ID 运行以下函数：Get-FastTrackGdprDsrRequest -TransactionID: “YourTransactionID”</span><span class="sxs-lookup"><span data-stu-id="924f4-162">Run the following function using the previously obtained Transaction ID: Get-FastTrackGdprDsrRequest -TransactionID: “YourTransactionID”</span></span>

#### <a name="transaction-status-codes"></a><span data-ttu-id="924f4-163">事务状态代码</span><span class="sxs-lookup"><span data-stu-id="924f4-163">Transaction Status Codes</span></span>
<!--start table here no header -->

|||
|:-----|:-----|:-----|
|<span data-ttu-id="924f4-164">**事务**</span><span class="sxs-lookup"><span data-stu-id="924f4-164">**Transaction**</span></span> |<span data-ttu-id="924f4-165">**状态**</span><span class="sxs-lookup"><span data-stu-id="924f4-165">**Status**</span></span>|
|<span data-ttu-id="924f4-166">**已创建**</span><span class="sxs-lookup"><span data-stu-id="924f4-166">**Created**</span></span> |<span data-ttu-id="924f4-167">已创建请求</span><span class="sxs-lookup"><span data-stu-id="924f4-167">Request has been created</span></span>|
|<span data-ttu-id="924f4-168">**失败**</span><span class="sxs-lookup"><span data-stu-id="924f4-168">**Failed**</span></span>|<span data-ttu-id="924f4-169">无法创建请求，请重新提交，或联系支持人员</span><span class="sxs-lookup"><span data-stu-id="924f4-169">Request failed to create, please resubmit, or contact support</span></span>|
|<span data-ttu-id="924f4-170">**已完成**</span><span class="sxs-lookup"><span data-stu-id="924f4-170">**Completed**</span></span>|<span data-ttu-id="924f4-171">请求已完成并已被清理</span><span class="sxs-lookup"><span data-stu-id="924f4-171">Request has been completed and sanitized</span></span>|
|||

<!-- end of table -->

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->


## <a name="learn-more"></a><span data-ttu-id="924f4-172">了解更多</span><span class="sxs-lookup"><span data-stu-id="924f4-172">Learn more</span></span>
[<span data-ttu-id="924f4-173">Microsoft 信任中心</span><span class="sxs-lookup"><span data-stu-id="924f4-173">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)