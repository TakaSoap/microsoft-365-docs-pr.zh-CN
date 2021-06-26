---
title: 适用于合规性管理器的 Microsoft 合规性配置分析器
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何使用 Microsoft 合规性配置分析器快速启动并运行 Microsoft 合规性管理器。
ms.openlocfilehash: 36f11597eac1837e3e18885f3c0a5d8dbc89a774
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2021
ms.locfileid: "53148958"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a><span data-ttu-id="c3a33-103">适用于合规性管理器的 Microsoft 合规性配置 (预览版) </span><span class="sxs-lookup"><span data-stu-id="c3a33-103">Microsoft Compliance Configuration Analyzer for Compliance Manager (preview)</span></span>

<span data-ttu-id="c3a33-104">**本文内容：** 了解如何安装和运行 Microsoft 合规性配置分析器工具，以快速开始使用 Microsoft 合规性经理。</span><span class="sxs-lookup"><span data-stu-id="c3a33-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a><span data-ttu-id="c3a33-105">Microsoft 合规性配置分析 (MCCA)  (预览) 概述</span><span class="sxs-lookup"><span data-stu-id="c3a33-105">Microsoft Compliance Configuration Analyzer (MCCA) (preview) overview</span></span>

<span data-ttu-id="c3a33-106">Microsoft 合规性配置 (MCCA) 是一个预览工具，可帮助你开始使用 [Microsoft 合规性管理器](compliance-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="c3a33-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a preview tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="c3a33-107">MCCA 是一个基于 PowerShell 的实用工具，它将提取组织的当前配置，并对照建议的最佳Microsoft 365验证这些配置。</span><span class="sxs-lookup"><span data-stu-id="c3a33-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="c3a33-108">这些最佳做法基于一组控制措施，其中包括数据保护和数据管理的关键法规和标准。</span><span class="sxs-lookup"><span data-stu-id="c3a33-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="c3a33-109">MCCA 可帮助你快速查看合规性管理器中的哪些改进操作适用于当前Microsoft 365环境。</span><span class="sxs-lookup"><span data-stu-id="c3a33-109">MCCA can help you quickly see which improvement actions in Compliance Manager apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="c3a33-110">MCCA 确定的每个操作都将提供实施建议，并直接链接到合规性管理器和适用的解决方案以开始采取纠正措施。</span><span class="sxs-lookup"><span data-stu-id="c3a33-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="c3a33-111">另一个了解 MCCA 的资源是访问上"自述文件["GitHub。](https://github.com/OfficeDev/MCCA#overview)</span><span class="sxs-lookup"><span data-stu-id="c3a33-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="c3a33-112">此页面提供有关必备组件的详细信息，并提供完整安装说明。</span><span class="sxs-lookup"><span data-stu-id="c3a33-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="c3a33-113">无需任何帐户GitHub访问此页面。</span><span class="sxs-lookup"><span data-stu-id="c3a33-113">You don’t need a GitHub account to access this page.</span></span>

<span data-ttu-id="c3a33-114">可用性：MCCA 可供所有拥有 Office 365 和 Microsoft 365 许可证的组织以及美国政府 Community (GCC) 中等、GCC 高和国防部 doD (客户) 使用。</span><span class="sxs-lookup"><span data-stu-id="c3a33-114">**Availability**: MCCA is available to all organizations with Office 365 and Microsoft 365 licenses and US Government Community (GCC) Moderate, GCC High, and Department of Defense (DoD) customers.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="c3a33-115">安装 MCCA 并运行报告</span><span class="sxs-lookup"><span data-stu-id="c3a33-115">Install MCCA and run a report</span></span>

<span data-ttu-id="c3a33-116">可以使用以下方法安装 MCCA Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c3a33-116">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="c3a33-117">下载并安装该工具后，无需重复这些步骤来运行报告。</span><span class="sxs-lookup"><span data-stu-id="c3a33-117">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="c3a33-118">每次打开 MCCA 时，它会要求你提供登录凭据，并且它将生成一个新的更新报告。</span><span class="sxs-lookup"><span data-stu-id="c3a33-118">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="c3a33-119">步骤 1：安装Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3a33-119">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="c3a33-120">首先，你需要 PowerShell 库中提供的 Exchange Online (v2.0.3) 或更高版本的 PowerShell 模块。</span><span class="sxs-lookup"><span data-stu-id="c3a33-120">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="c3a33-121">[获取安装说明](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)。</span><span class="sxs-lookup"><span data-stu-id="c3a33-121">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="c3a33-122">步骤 2：安装 MCCA</span><span class="sxs-lookup"><span data-stu-id="c3a33-122">Step 2: Install MCCA</span></span>

<span data-ttu-id="c3a33-123">若要安装 MCCA，请首先在管理员模式下使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c3a33-123">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="c3a33-124">请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="c3a33-124">Follow the steps below:</span></span>

1. <span data-ttu-id="c3a33-125">选择 **"Windows"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="c3a33-125">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="c3a33-126">键入 **PowerShell，** 右 **键单击**"Windows PowerShell"，然后选择"以 **管理员角色运行"。**</span><span class="sxs-lookup"><span data-stu-id="c3a33-126">Type **PowerShell**, right-click on **Windows PowerShell**, then select **Run as administrator**.</span></span>
1. <span data-ttu-id="c3a33-127">在命令提示符处，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="c3a33-127">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="c3a33-128">步骤 3：运行报告</span><span class="sxs-lookup"><span data-stu-id="c3a33-128">Step 3: Run a report</span></span>

<span data-ttu-id="c3a33-129">安装 MCCA 后，可以运行 MCCA 并生成报告。</span><span class="sxs-lookup"><span data-stu-id="c3a33-129">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="c3a33-130">运行报告：</span><span class="sxs-lookup"><span data-stu-id="c3a33-130">To run a report:</span></span>

1. <span data-ttu-id="c3a33-131">打开 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3a33-131">Open PowerShell</span></span>
2. <span data-ttu-id="c3a33-132">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c3a33-132">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```

   <span data-ttu-id="c3a33-133">如果你是高级GCC，则需要提供其他输入参数来运行报告：</span><span class="sxs-lookup"><span data-stu-id="c3a33-133">If you're a GCC High customer, you'll need to provide an additional input parameter to run the report:</span></span>

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. <span data-ttu-id="c3a33-134">MCCA 运行后，它将执行初始版本检查并请求凭据。</span><span class="sxs-lookup"><span data-stu-id="c3a33-134">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="c3a33-135">在"输入用户名"提示符下，使用Microsoft 365帐户电子邮件地址登录 ([查看](#role-based-reporting)有资格创建报告) 。</span><span class="sxs-lookup"><span data-stu-id="c3a33-135">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="c3a33-136">然后在密码提示符下输入密码。</span><span class="sxs-lookup"><span data-stu-id="c3a33-136">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="c3a33-137">然后，你的报告将大约需要 2-5 分钟生成。</span><span class="sxs-lookup"><span data-stu-id="c3a33-137">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="c3a33-138">完成后，浏览器窗口将打开并显示 HTML 报告。</span><span class="sxs-lookup"><span data-stu-id="c3a33-138">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="c3a33-139">每次运行该工具时，该工具都会要求提供凭据并生成一个新报告。</span><span class="sxs-lookup"><span data-stu-id="c3a33-139">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="c3a33-140">此报告本地存储在以下目录中：</span><span class="sxs-lookup"><span data-stu-id="c3a33-140">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="c3a33-141">C：\Users \<username> \AppData\Local\Microsoft\MCCA。</span><span class="sxs-lookup"><span data-stu-id="c3a33-141">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="c3a33-142">可以从此目录访问以前生成的报告。</span><span class="sxs-lookup"><span data-stu-id="c3a33-142">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="c3a33-143">了解报告</span><span class="sxs-lookup"><span data-stu-id="c3a33-143">Understanding your report</span></span>

<span data-ttu-id="c3a33-144">你的报告根据生成数据的日期和时间反映数据。</span><span class="sxs-lookup"><span data-stu-id="c3a33-144">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="c3a33-145">顶部部分提供了有关生成时间、组织名称和租户 ID 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c3a33-145">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="c3a33-146">基于地理位置的报告</span><span class="sxs-lookup"><span data-stu-id="c3a33-146">Geolocation-based reporting</span></span>

<span data-ttu-id="c3a33-147">" **注释** "部分显示根据租户的地理位置对报表进行自定义。</span><span class="sxs-lookup"><span data-stu-id="c3a33-147">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="c3a33-148">推荐列出的列表将特定于你的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="c3a33-148">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="c3a33-149">你的地理位置选择用于评估与该地理位置 (的敏感信息类型) 并生成与你的国家/地区或区域一致的报告。</span><span class="sxs-lookup"><span data-stu-id="c3a33-149">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="c3a33-150">根据租户中拥有的数据选择地理位置。</span><span class="sxs-lookup"><span data-stu-id="c3a33-150">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="c3a33-151">若要更改报告的位置信息，你需要提供地理位置 (地理位置) 输入参数。</span><span class="sxs-lookup"><span data-stu-id="c3a33-151">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="c3a33-152">可以选择一个或多个适用于租户的地理位置。</span><span class="sxs-lookup"><span data-stu-id="c3a33-152">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="c3a33-153">按照以下说明运行基于特定位置的报告：</span><span class="sxs-lookup"><span data-stu-id="c3a33-153">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="c3a33-154">打开 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3a33-154">Open PowerShell</span></span>
2. <span data-ttu-id="c3a33-155">若要指定特定区域，您需要使用下表中对应于该国家/地区的数字运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c3a33-155">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="c3a33-156">输入多个号码，用逗号分隔它们。</span><span class="sxs-lookup"><span data-stu-id="c3a33-156">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="c3a33-157">例如，以下 cmdlet 将针对日本Asia-Pacific自定义报告：</span><span class="sxs-lookup"><span data-stu-id="c3a33-157">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="c3a33-158">Input</span><span class="sxs-lookup"><span data-stu-id="c3a33-158">Input</span></span> |  <span data-ttu-id="c3a33-159">国家或地区</span><span class="sxs-lookup"><span data-stu-id="c3a33-159">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="c3a33-160">1 </span><span class="sxs-lookup"><span data-stu-id="c3a33-160">1</span></span> | <span data-ttu-id="c3a33-161">亚太地区</span><span class="sxs-lookup"><span data-stu-id="c3a33-161">Asia-Pacific</span></span> |
  | <span data-ttu-id="c3a33-162">2 </span><span class="sxs-lookup"><span data-stu-id="c3a33-162">2</span></span> | <span data-ttu-id="c3a33-163">澳大利亚</span><span class="sxs-lookup"><span data-stu-id="c3a33-163">Australia</span></span> |
  | <span data-ttu-id="c3a33-164">3 </span><span class="sxs-lookup"><span data-stu-id="c3a33-164">3</span></span> | <span data-ttu-id="c3a33-165">加拿大</span><span class="sxs-lookup"><span data-stu-id="c3a33-165">Canada</span></span> |
  | <span data-ttu-id="c3a33-166">4 </span><span class="sxs-lookup"><span data-stu-id="c3a33-166">4</span></span> | <span data-ttu-id="c3a33-167">欧洲 (（不包括法国) /中东/非洲）</span><span class="sxs-lookup"><span data-stu-id="c3a33-167">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="c3a33-168">5 </span><span class="sxs-lookup"><span data-stu-id="c3a33-168">5</span></span> | <span data-ttu-id="c3a33-169">法国</span><span class="sxs-lookup"><span data-stu-id="c3a33-169">France</span></span> |
  | <span data-ttu-id="c3a33-170">6 </span><span class="sxs-lookup"><span data-stu-id="c3a33-170">6</span></span> | <span data-ttu-id="c3a33-171">印度</span><span class="sxs-lookup"><span data-stu-id="c3a33-171">India</span></span> |
  | <span data-ttu-id="c3a33-172">7 </span><span class="sxs-lookup"><span data-stu-id="c3a33-172">7</span></span> | <span data-ttu-id="c3a33-173">日本</span><span class="sxs-lookup"><span data-stu-id="c3a33-173">Japan</span></span> |
  | <span data-ttu-id="c3a33-174">8 </span><span class="sxs-lookup"><span data-stu-id="c3a33-174">8</span></span> | <span data-ttu-id="c3a33-175">韩国</span><span class="sxs-lookup"><span data-stu-id="c3a33-175">Korea</span></span> |
  | <span data-ttu-id="c3a33-176">9 </span><span class="sxs-lookup"><span data-stu-id="c3a33-176">9</span></span> | <span data-ttu-id="c3a33-177">北美 (加拿大) </span><span class="sxs-lookup"><span data-stu-id="c3a33-177">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="c3a33-178">10 </span><span class="sxs-lookup"><span data-stu-id="c3a33-178">10</span></span> | <span data-ttu-id="c3a33-179">南美洲</span><span class="sxs-lookup"><span data-stu-id="c3a33-179">South America</span></span> |
  | <span data-ttu-id="c3a33-180">11 </span><span class="sxs-lookup"><span data-stu-id="c3a33-180">11</span></span> | <span data-ttu-id="c3a33-181">南非</span><span class="sxs-lookup"><span data-stu-id="c3a33-181">South Africa</span></span> |
  | <span data-ttu-id="c3a33-182">12 </span><span class="sxs-lookup"><span data-stu-id="c3a33-182">12</span></span> | <span data-ttu-id="c3a33-183">Switzerland（瑞士）</span><span class="sxs-lookup"><span data-stu-id="c3a33-183">Switzerland</span></span> |
  | <span data-ttu-id="c3a33-184">13 </span><span class="sxs-lookup"><span data-stu-id="c3a33-184">13</span></span> | <span data-ttu-id="c3a33-185">阿拉伯联合酋长国</span><span class="sxs-lookup"><span data-stu-id="c3a33-185">United Arab Emirates</span></span> |
  | <span data-ttu-id="c3a33-186">14 </span><span class="sxs-lookup"><span data-stu-id="c3a33-186">14</span></span> | <span data-ttu-id="c3a33-187">英国</span><span class="sxs-lookup"><span data-stu-id="c3a33-187">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="c3a33-188">报告将始终包括 MCCA 支持的国际敏感信息类型，如 SWIFT 代码、信用卡号等。</span><span class="sxs-lookup"><span data-stu-id="c3a33-188">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="c3a33-189">基于角色的报告</span><span class="sxs-lookup"><span data-stu-id="c3a33-189">Role-based reporting</span></span>

<span data-ttu-id="c3a33-190">你的报告也将基于你的角色进行自定义。</span><span class="sxs-lookup"><span data-stu-id="c3a33-190">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="c3a33-191">下表显示了哪些角色有权访问报告的哪些部分。</span><span class="sxs-lookup"><span data-stu-id="c3a33-191">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="c3a33-192">) 下表中未列出的 (组织内部的其他角色可能无法运行该工具，或者他们可能运行该工具，并且对最终报告中的信息具有有限的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c3a33-192">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="c3a33-193">![MCCA - 角色](../media/compliance-manager-mcca-roles.png "MCCA 角色")</span><span class="sxs-lookup"><span data-stu-id="c3a33-193">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="c3a33-194">例外情况如下：</span><span class="sxs-lookup"><span data-stu-id="c3a33-194">Exceptions:</span></span>
1. <span data-ttu-id="c3a33-195">用户无法生成除"使用 IRM for Exchange Online"部分的报告。</span><span class="sxs-lookup"><span data-stu-id="c3a33-195">Users won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="c3a33-196">用户将能够生成除"使用 IRM for Exchange Online"部分的报告。</span><span class="sxs-lookup"><span data-stu-id="c3a33-196">Users will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="c3a33-197">用户将能够生成除"在 O365 中启用通信合规性"部分之外 IP 的报告。</span><span class="sxs-lookup"><span data-stu-id="c3a33-197">Users will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="c3a33-198">用户无法生成除"启用审核功能中的审核"部分Office 365 IP 报告。</span><span class="sxs-lookup"><span data-stu-id="c3a33-198">Users won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="c3a33-199">用户将能够生成 IP 报告，除了"在 Office 365 中启用审核"部分。</span><span class="sxs-lookup"><span data-stu-id="c3a33-199">Users will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="c3a33-200">"解决方案摘要"部分</span><span class="sxs-lookup"><span data-stu-id="c3a33-200">Solutions Summary section</span></span>

<span data-ttu-id="c3a33-201">该报告 **的** "解决方案摘要"部分概述了贵组织可以在合规性管理器中采取的改进操作，以帮助改善合规性状态。</span><span class="sxs-lookup"><span data-stu-id="c3a33-201">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="c3a33-202">![MCCA - 解决方案摘要](../media/compliance-manager-mcca-solutions.png "MCCA 解决方案摘要屏幕")</span><span class="sxs-lookup"><span data-stu-id="c3a33-202">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="c3a33-203">MCCA 根据合规性管理器中建议的改进操作评估当前配置。</span><span class="sxs-lookup"><span data-stu-id="c3a33-203">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="c3a33-204">本节中将列出 MCCA 工具标识为需要关注的任何改进操作。</span><span class="sxs-lookup"><span data-stu-id="c3a33-204">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="c3a33-205">每个 Microsoft 解决方案旁边都有颜色编码框，用于指示合规性管理器中的改进操作对应的项目数。</span><span class="sxs-lookup"><span data-stu-id="c3a33-205">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="c3a33-206">操作分为三种状态：</span><span class="sxs-lookup"><span data-stu-id="c3a33-206">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="c3a33-207">**确定**：符合建议条件且此时无需关注的操作</span><span class="sxs-lookup"><span data-stu-id="c3a33-207">**OK**: the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="c3a33-208">**改进**：需要关注的操作</span><span class="sxs-lookup"><span data-stu-id="c3a33-208">**Improvement**: actions that need attention</span></span>
- <span data-ttu-id="c3a33-209">**建议**：不需要关注但我们建议采用最佳做法的操作</span><span class="sxs-lookup"><span data-stu-id="c3a33-209">**Recommendation**: actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="c3a33-210">选择一个框以查看改进和建议。</span><span class="sxs-lookup"><span data-stu-id="c3a33-210">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="c3a33-211">**具有"改进"状态的项目**</span><span class="sxs-lookup"><span data-stu-id="c3a33-211">**Items with the Improvement status**</span></span>

<span data-ttu-id="c3a33-212">选择改进操作右侧"改进"标签旁边的下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c3a33-212">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="c3a33-213">你将看到有关当前设置以及建议改进操作的快速摘要和详细信息。</span><span class="sxs-lookup"><span data-stu-id="c3a33-213">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="c3a33-214">摘要包括合规性管理器的直接链接、Microsoft 365 合规中心适用的解决方案和相关文档。</span><span class="sxs-lookup"><span data-stu-id="c3a33-214">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="c3a33-215">单击"合规性管理器"链接，可查看该解决方案中所有尚未实施的改进措施的筛选视图。</span><span class="sxs-lookup"><span data-stu-id="c3a33-215">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="c3a33-216">你可以从其中查看可达到的分数，以提升合规性分数、适用的评估[](compliance-score-calculation.md)以及适用的法规和认证。</span><span class="sxs-lookup"><span data-stu-id="c3a33-216">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="c3a33-217">对于 DLP，有一个 **修正** 脚本按钮，根据建议的内容为你提供预生成的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="c3a33-217">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="c3a33-218">可以直接在 PowerShell 控制台中复制并粘贴它。</span><span class="sxs-lookup"><span data-stu-id="c3a33-218">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="c3a33-219">它将在测试模式下创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="c3a33-219">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="c3a33-220">**具有"建议"状态的项目**</span><span class="sxs-lookup"><span data-stu-id="c3a33-220">**Items with Recommendation status**</span></span>

<span data-ttu-id="c3a33-221">选择改进操作右侧 **建议** 标签旁边的下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c3a33-221">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="c3a33-222">你将看到与改进操作相关的组织当前Microsoft 365环境摘要，以及建议的最佳方案。</span><span class="sxs-lookup"><span data-stu-id="c3a33-222">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="c3a33-223">资源</span><span class="sxs-lookup"><span data-stu-id="c3a33-223">Resources</span></span>

<span data-ttu-id="c3a33-224">有关安装、设置和使用 MCCA 的更多详细信息，请参阅[GitHub](https://github.com/OfficeDev/MCCA#overview) (上的自述GitHub无需) 。</span><span class="sxs-lookup"><span data-stu-id="c3a33-224">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="c3a33-225">有关此Windows PowerShell，请从如何使用[PowerShell 文档开始](/powershell/scripting/how-to-use-docs?view=powershell-7)。</span><span class="sxs-lookup"><span data-stu-id="c3a33-225">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="c3a33-226">另请参阅[Starting Windows PowerShell](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)。</span><span class="sxs-lookup"><span data-stu-id="c3a33-226">See also [Starting Windows PowerShell](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>
