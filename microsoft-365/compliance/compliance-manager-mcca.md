---
title: 适用于合规性管理器的 Microsoft 合规性配置分析器
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何使用 Microsoft 合规性配置分析器立即与 Microsoft 合规性管理器一起运行。
ms.openlocfilehash: 1f7d987262a7d390cb9efe2162ae9be9f56c8757
ms.sourcegitcommit: d333d82fd5e4f3265e8b9372094e85875bee6fe5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071992"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager"></a><span data-ttu-id="2540a-103">适用于合规性管理器的 Microsoft 合规性配置分析器</span><span class="sxs-lookup"><span data-stu-id="2540a-103">Microsoft Compliance Configuration Analyzer for Compliance Manager</span></span>

<span data-ttu-id="2540a-104">**本文内容：** 了解如何安装和运行 Microsoft 合规性配置分析器工具以快速开始使用 Microsoft 合规性管理器。</span><span class="sxs-lookup"><span data-stu-id="2540a-104">**In this article:** Learn how to install and run the Microsoft Compliance Configure Analyzer tool to get quickly started with Microsoft Compliance Manger.</span></span>

## <a name="microsoft-compliance-configuration-analyzer-mcca-overview"></a><span data-ttu-id="2540a-105">Microsoft MCCA 兼容性配置分析器 () 概述</span><span class="sxs-lookup"><span data-stu-id="2540a-105">Microsoft Compliance Configuration Analyzer (MCCA) overview</span></span>

<span data-ttu-id="2540a-106">Microsoft 合规性配置分析器 (MCCA) 是一种可帮助您开始使用 [Microsoft 合规性管理器](compliance-manager.md)的工具。</span><span class="sxs-lookup"><span data-stu-id="2540a-106">The Microsoft Compliance Configuration Analyzer (MCCA) is a tool that can help you get started with [Microsoft Compliance Manager](compliance-manager.md).</span></span> <span data-ttu-id="2540a-107">MCCA 是基于 PowerShell 的实用工具，它将获取组织的当前配置，并针对 Microsoft 365 建议的最佳实践对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="2540a-107">MCCA is a PowerShell-based utility that will fetch your organization’s current configurations and validate them against Microsoft 365 recommended best practices.</span></span> <span data-ttu-id="2540a-108">这些最佳做法基于一组控件，其中包括针对数据保护和数据管理的关键法规和标准。</span><span class="sxs-lookup"><span data-stu-id="2540a-108">These best practices are based on a set of controls that include key regulations and standards for data protection and data governance.</span></span>

<span data-ttu-id="2540a-109">MCCA 可帮助您快速查看合规性管理器中的哪些改进操作适用于您当前的 Microsoft 365 环境。</span><span class="sxs-lookup"><span data-stu-id="2540a-109">MCCA can help you quickly see which improvement actions in Compliance Manger apply to your current Microsoft 365 environment.</span></span> <span data-ttu-id="2540a-110">由 MCCA 标识的每个操作都将为您提供实施建议，其中包含指向合规性管理器的直接链接以及开始采取纠正措施的适用解决方案。</span><span class="sxs-lookup"><span data-stu-id="2540a-110">Each action identified by MCCA will give you recommendations for implementation, with direct links to Compliance Manager and the applicable solution to start taking corrective action.</span></span>

<span data-ttu-id="2540a-111">要了解 MCCA 的其他资源，请访问 [GitHub 上的自述文件说明](https://github.com/OfficeDev/MCCA#overview)。</span><span class="sxs-lookup"><span data-stu-id="2540a-111">An additional resource for understanding MCCA is by visiting the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview).</span></span> <span data-ttu-id="2540a-112">此页面提供了有关先决条件的详细信息，并提供了完整的安装说明。</span><span class="sxs-lookup"><span data-stu-id="2540a-112">This page provides detailed information about prerequisites and gives full installation instructions.</span></span> <span data-ttu-id="2540a-113">您不需要 GitHub 帐户即可访问此页面。</span><span class="sxs-lookup"><span data-stu-id="2540a-113">You don’t need a GitHub account to access this page.</span></span>

## <a name="install-mcca-and-run-a-report"></a><span data-ttu-id="2540a-114">安装 MCCA 并运行报告</span><span class="sxs-lookup"><span data-stu-id="2540a-114">Install MCCA and run a report</span></span>

<span data-ttu-id="2540a-115">您可以使用 Windows PowerShell 安装 MCCA 工具。</span><span class="sxs-lookup"><span data-stu-id="2540a-115">You can install the MCCA tool using Windows PowerShell.</span></span> <span data-ttu-id="2540a-116">下载并安装该工具后，无需重复这些步骤即可运行报告。</span><span class="sxs-lookup"><span data-stu-id="2540a-116">Once you download and install the tool, you don’t need to repeat those steps in order to run reports.</span></span> <span data-ttu-id="2540a-117">每次打开 MCCA 时，它都会询问您登录凭据，并将生成一个新的更新的报告。</span><span class="sxs-lookup"><span data-stu-id="2540a-117">Each time you open MCCA, it will ask you for your login credentials, and it will generate a new, updated report.</span></span>

#### <a name="step-1-install-windows-powershell"></a><span data-ttu-id="2540a-118">步骤1：安装 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2540a-118">Step 1: Install Windows PowerShell</span></span>
<span data-ttu-id="2540a-119">若要开始，你将需要 Exchange Online PowerShell 模块 (v 2.0.3 或更高版本的 PowerShell 库中提供的) 。</span><span class="sxs-lookup"><span data-stu-id="2540a-119">To begin, you'll need the Exchange Online PowerShell module (v2.0.3 or higher) that's available in the PowerShell gallery.</span></span> <span data-ttu-id="2540a-120">[获取安装说明](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)。</span><span class="sxs-lookup"><span data-stu-id="2540a-120">[Get installation instructions](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).</span></span>

#### <a name="step-2-install-mcca"></a><span data-ttu-id="2540a-121">步骤2：安装 MCCA</span><span class="sxs-lookup"><span data-stu-id="2540a-121">Step 2: Install MCCA</span></span>

<span data-ttu-id="2540a-122">若要安装 MCCA，请首先在管理员模式下使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2540a-122">To install MCCA, start by using PowerShell in administrator mode.</span></span> <span data-ttu-id="2540a-123">请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="2540a-123">Follow the steps below:</span></span>

1. <span data-ttu-id="2540a-124">选择 "Windows **开始** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="2540a-124">Select the Windows **Start** button.</span></span>
2. <span data-ttu-id="2540a-125">键入 **PowerShell** ，右键单击 " **Windows PowerShell** "，然后选择 " **以管理员身份运行** "。</span><span class="sxs-lookup"><span data-stu-id="2540a-125">Type **PowerShell** , right-click on **Windows PowerShell** , then select **Run as administrator**.</span></span>
1. <span data-ttu-id="2540a-126">在命令提示符处，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="2540a-126">At the command prompt, type:</span></span>

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a><span data-ttu-id="2540a-127">步骤3：运行报告</span><span class="sxs-lookup"><span data-stu-id="2540a-127">Step 3: Run a report</span></span>

<span data-ttu-id="2540a-128">安装 MCCA 后，可以运行 MCCA 并生成报告。</span><span class="sxs-lookup"><span data-stu-id="2540a-128">After you install MCCA, you can run MCCA and generate a report.</span></span> <span data-ttu-id="2540a-129">运行报告：</span><span class="sxs-lookup"><span data-stu-id="2540a-129">To run a report:</span></span>

1. <span data-ttu-id="2540a-130">打开 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2540a-130">Open PowerShell</span></span>
2. <span data-ttu-id="2540a-131">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2540a-131">Run the cmdlet:</span></span>

    ```powershell
    Get-MCCAReport
    ```
3. <span data-ttu-id="2540a-132">在 MCCA 运行后，它会执行初始版本检查并要求提供凭据。</span><span class="sxs-lookup"><span data-stu-id="2540a-132">Once MCCA runs, it does an initial version check and ask for credentials.</span></span> <span data-ttu-id="2540a-133">在输入用户名提示符处，使用 Microsoft 365 帐户电子邮件地址登录 ([查看符合创建报告的角色](#role-based-reporting)) 。</span><span class="sxs-lookup"><span data-stu-id="2540a-133">At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)).</span></span> <span data-ttu-id="2540a-134">然后在密码提示符处输入您的密码。</span><span class="sxs-lookup"><span data-stu-id="2540a-134">Then enter your password at the password prompt.</span></span>

<span data-ttu-id="2540a-135">您的报告将需要大约2-5 分钟的时间来生成。</span><span class="sxs-lookup"><span data-stu-id="2540a-135">Your report will then take approximately 2-5 minutes to generate.</span></span> <span data-ttu-id="2540a-136">完成后，浏览器窗口将打开并显示您的 HTML 报告。</span><span class="sxs-lookup"><span data-stu-id="2540a-136">When it’s done, a browser window opens and displays your HTML report.</span></span> <span data-ttu-id="2540a-137">每次运行该工具时，它都会要求你提供凭据并生成新报告。</span><span class="sxs-lookup"><span data-stu-id="2540a-137">Every time you run the tool, it will ask for your credentials and generate a new report.</span></span> <span data-ttu-id="2540a-138">此报告在本地存储在以下目录中：</span><span class="sxs-lookup"><span data-stu-id="2540a-138">This report is stored locally in the following directory:</span></span>

<span data-ttu-id="2540a-139">C:\Users \<username> \AppData\Local\Microsoft\MCCA。</span><span class="sxs-lookup"><span data-stu-id="2540a-139">C:\Users\<username>\AppData\Local\Microsoft\MCCA.</span></span> 

<span data-ttu-id="2540a-140">您可以从此目录访问以前生成的报告。</span><span class="sxs-lookup"><span data-stu-id="2540a-140">You can access previously generated reports from this directory.</span></span>

## <a name="understanding-your-report"></a><span data-ttu-id="2540a-141">了解你的报告</span><span class="sxs-lookup"><span data-stu-id="2540a-141">Understanding your report</span></span>

<span data-ttu-id="2540a-142">您的报告将根据数据生成的日期和时间反映数据。</span><span class="sxs-lookup"><span data-stu-id="2540a-142">Your report reflects data based on the date and time at which it was generated.</span></span> <span data-ttu-id="2540a-143">上面的部分提供了有关何时生成、组织名称和租户 ID 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2540a-143">The top section provides details on when it was generated, your organization name, and tenant ID.</span></span>

#### <a name="geolocation-based-reporting"></a><span data-ttu-id="2540a-144">基于地理位置的报告</span><span class="sxs-lookup"><span data-stu-id="2540a-144">Geolocation-based reporting</span></span>

<span data-ttu-id="2540a-145">" **注释** " 部分显示您的报告根据租户的地理位置进行自定义。</span><span class="sxs-lookup"><span data-stu-id="2540a-145">The **Note** section shows that your report is customized based on the geographic location of your tenant.</span></span> <span data-ttu-id="2540a-146">工具中列出的建议将特定于您所在的国家或地区。</span><span class="sxs-lookup"><span data-stu-id="2540a-146">Recommendations listed in the tool will be specific to your country or region.</span></span>

<span data-ttu-id="2540a-147">您的地理位置选择用于评估与该地理位置相关 () 的敏感信息类型，并生成与您的国家或地区相符的报告。</span><span class="sxs-lookup"><span data-stu-id="2540a-147">Your geolocation selection is used to assess sensitive information types (SITs) which are relevant to that geolocation and generate a report that aligns to your country or region.</span></span> <span data-ttu-id="2540a-148">根据租户中的数据选择 "geolocations"。</span><span class="sxs-lookup"><span data-stu-id="2540a-148">Choose geolocations based on data you have in your tenant.</span></span>

<span data-ttu-id="2540a-149">若要更改报表的位置信息，您需要提供一个地理位置 ( Geo) 输入参数。</span><span class="sxs-lookup"><span data-stu-id="2540a-149">To change your report's location information, you need provide a geolocation (-Geo) input parameter.</span></span> <span data-ttu-id="2540a-150">你可以选择适用于你的租户的一个或多个 geolocations。</span><span class="sxs-lookup"><span data-stu-id="2540a-150">You can choose either one or multiple geolocations applicable for your tenant.</span></span>

<span data-ttu-id="2540a-151">按照以下说明运行基于特定位置的报表：</span><span class="sxs-lookup"><span data-stu-id="2540a-151">Follow these instructions to run a report based on a specific location:</span></span>

1. <span data-ttu-id="2540a-152">打开 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2540a-152">Open PowerShell</span></span>
2. <span data-ttu-id="2540a-153">若要指定某个区域，您将使用下表中与该国家或地区对应的编号运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2540a-153">To specify a certain region, you’ll run a cmdlet using the numbers from the table below that correspond to the country or region.</span></span> <span data-ttu-id="2540a-154">通过用逗号分隔来输入多个数字。</span><span class="sxs-lookup"><span data-stu-id="2540a-154">Enter multiple numbers by separating them with a comma.</span></span> <span data-ttu-id="2540a-155">例如，下面的 cmdlet 将为 Asia-Pacific 和日本运行自定义报告：</span><span class="sxs-lookup"><span data-stu-id="2540a-155">For example, the cmdlet below will run a customized report for Asia-Pacific and Japan:</span></span>

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | <span data-ttu-id="2540a-156">Input</span><span class="sxs-lookup"><span data-stu-id="2540a-156">Input</span></span> |  <span data-ttu-id="2540a-157">国家或地区</span><span class="sxs-lookup"><span data-stu-id="2540a-157">Country or Region</span></span> | 
  | :------------- | :------------: |
  | <span data-ttu-id="2540a-158">1 </span><span class="sxs-lookup"><span data-stu-id="2540a-158">1</span></span> | <span data-ttu-id="2540a-159">亚太地区</span><span class="sxs-lookup"><span data-stu-id="2540a-159">Asia-Pacific</span></span> |
  | <span data-ttu-id="2540a-160">2 </span><span class="sxs-lookup"><span data-stu-id="2540a-160">2</span></span> | <span data-ttu-id="2540a-161">澳大利亚</span><span class="sxs-lookup"><span data-stu-id="2540a-161">Australia</span></span> |
  | <span data-ttu-id="2540a-162">第三章</span><span class="sxs-lookup"><span data-stu-id="2540a-162">3</span></span> | <span data-ttu-id="2540a-163">加拿大</span><span class="sxs-lookup"><span data-stu-id="2540a-163">Canada</span></span> |
  | <span data-ttu-id="2540a-164">4 </span><span class="sxs-lookup"><span data-stu-id="2540a-164">4</span></span> | <span data-ttu-id="2540a-165">欧洲 (不包括法国) /中部东部/非洲</span><span class="sxs-lookup"><span data-stu-id="2540a-165">Europe (excluding France) / Middle East / Africa</span></span> |
  | <span data-ttu-id="2540a-166">5 </span><span class="sxs-lookup"><span data-stu-id="2540a-166">5</span></span> | <span data-ttu-id="2540a-167">法国</span><span class="sxs-lookup"><span data-stu-id="2540a-167">France</span></span> |
  | <span data-ttu-id="2540a-168">6 </span><span class="sxs-lookup"><span data-stu-id="2540a-168">6</span></span> | <span data-ttu-id="2540a-169">印度</span><span class="sxs-lookup"><span data-stu-id="2540a-169">India</span></span> |
  | <span data-ttu-id="2540a-170">7 </span><span class="sxs-lookup"><span data-stu-id="2540a-170">7</span></span> | <span data-ttu-id="2540a-171">日本</span><span class="sxs-lookup"><span data-stu-id="2540a-171">Japan</span></span> |
  | <span data-ttu-id="2540a-172">8 </span><span class="sxs-lookup"><span data-stu-id="2540a-172">8</span></span> | <span data-ttu-id="2540a-173">韩国</span><span class="sxs-lookup"><span data-stu-id="2540a-173">Korea</span></span> |
  | <span data-ttu-id="2540a-174">9 </span><span class="sxs-lookup"><span data-stu-id="2540a-174">9</span></span> | <span data-ttu-id="2540a-175">北美 (不包括加拿大) </span><span class="sxs-lookup"><span data-stu-id="2540a-175">North America (excluding Canada)</span></span> |
  | <span data-ttu-id="2540a-176">10  </span><span class="sxs-lookup"><span data-stu-id="2540a-176">10</span></span> | <span data-ttu-id="2540a-177">南美洲</span><span class="sxs-lookup"><span data-stu-id="2540a-177">South America</span></span> |
  | <span data-ttu-id="2540a-178">11 </span><span class="sxs-lookup"><span data-stu-id="2540a-178">11</span></span> | <span data-ttu-id="2540a-179">南非</span><span class="sxs-lookup"><span data-stu-id="2540a-179">South Africa</span></span> |
  | <span data-ttu-id="2540a-180">12 </span><span class="sxs-lookup"><span data-stu-id="2540a-180">12</span></span> | <span data-ttu-id="2540a-181">瑞士</span><span class="sxs-lookup"><span data-stu-id="2540a-181">Switzerland</span></span> |
  | <span data-ttu-id="2540a-182">13 </span><span class="sxs-lookup"><span data-stu-id="2540a-182">13</span></span> | <span data-ttu-id="2540a-183">阿拉伯联合酋长国</span><span class="sxs-lookup"><span data-stu-id="2540a-183">United Arab Emirates</span></span> |
  | <span data-ttu-id="2540a-184">14 </span><span class="sxs-lookup"><span data-stu-id="2540a-184">14</span></span> | <span data-ttu-id="2540a-185">英国</span><span class="sxs-lookup"><span data-stu-id="2540a-185">United Kingdom</span></span> |


 > [!NOTE]
> <span data-ttu-id="2540a-186">该报告将始终包含 MCCA 支持的国际敏感信息类型，如 SWIFT 代码、信用卡号等。</span><span class="sxs-lookup"><span data-stu-id="2540a-186">The report will always include MCCA supported international sensitive information types such as SWIFT code, credit card number, etc.</span></span>

#### <a name="role-based-reporting"></a><span data-ttu-id="2540a-187">基于角色的报告</span><span class="sxs-lookup"><span data-stu-id="2540a-187">Role-based reporting</span></span>

<span data-ttu-id="2540a-188">您的报告也将根据您的角色进行自定义。</span><span class="sxs-lookup"><span data-stu-id="2540a-188">Your report will also be customized based on your role.</span></span>

<span data-ttu-id="2540a-189">下表显示了哪些角色有权访问报表的哪些部分。</span><span class="sxs-lookup"><span data-stu-id="2540a-189">The table below shows which roles have access to which sections of the report.</span></span> <span data-ttu-id="2540a-190">组织中的其他角色 (下表中未列出) 可能无法运行该工具，也可能会运行该工具，并且对最终报告中的信息具有有限的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2540a-190">Other roles within your organization (not listed in the table below) may not be able to run the tool, or they may run the tool and have limited access to information in the final report.</span></span>

<span data-ttu-id="2540a-191">![MCCA-角色](../media/compliance-manager-mcca-roles.png "MCCA 角色")</span><span class="sxs-lookup"><span data-stu-id="2540a-191">![MCCA - roles](../media/compliance-manager-mcca-roles.png "MCCA roles")</span></span>

<span data-ttu-id="2540a-192">例外情况如下：</span><span class="sxs-lookup"><span data-stu-id="2540a-192">Exceptions:</span></span>
1. <span data-ttu-id="2540a-193">用户不能在 "使用 Exchange Online IRM" 部分生成 IP 报告。</span><span class="sxs-lookup"><span data-stu-id="2540a-193">User won't be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
2. <span data-ttu-id="2540a-194">用户将能够针对 "使用 Exchange Online IRM" 部分生成 IP 报告。</span><span class="sxs-lookup"><span data-stu-id="2540a-194">User will be able to generate report for IP apart from “Use IRM for Exchange Online” section.</span></span>
3. <span data-ttu-id="2540a-195">用户将能够生成 IP 报告，而不是 "在 O365 中启用通信合规性" 部分。</span><span class="sxs-lookup"><span data-stu-id="2540a-195">User will be able to generate report for IP apart from “Enable Communication Compliance in O365” section.</span></span>
4. <span data-ttu-id="2540a-196">用户将无法生成 IP 报告 "在 Office 365 中启用审核" 部分。</span><span class="sxs-lookup"><span data-stu-id="2540a-196">User won't be able to generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>
5. <span data-ttu-id="2540a-197">用户将能够生成 IP 报告 "在 Office 365 中启用审核" 部分。</span><span class="sxs-lookup"><span data-stu-id="2540a-197">User will be able generate report for IP apart from “Enable Auditing in Office 365” section.</span></span>

#### <a name="solutions-summary-section"></a><span data-ttu-id="2540a-198">"解决方案摘要" 部分</span><span class="sxs-lookup"><span data-stu-id="2540a-198">Solutions Summary section</span></span>

<span data-ttu-id="2540a-199">报告的 " **解决方案摘要** " 部分概述了贵组织可在合规性管理器中采取的改进措施，以帮助改进合规性状况。</span><span class="sxs-lookup"><span data-stu-id="2540a-199">The **Solutions Summary** section of the report gives an overview of improvement actions that your organization can take in Compliance Manager to help improve your compliance posture.</span></span>

<span data-ttu-id="2540a-200">![MCCA-解决方案摘要](../media/compliance-manager-mcca-solutions.png "MCCA 解决方案摘要屏幕")</span><span class="sxs-lookup"><span data-stu-id="2540a-200">![MCCA - solutions summary](../media/compliance-manager-mcca-solutions.png "MCCA Solutions Summary screen")</span></span>

<span data-ttu-id="2540a-201">MCCA 评估当前配置是否符合合规性管理器中建议的改进措施。</span><span class="sxs-lookup"><span data-stu-id="2540a-201">MCCA evaluates your current configurations against the recommended improvement actions in Compliance Manager.</span></span> <span data-ttu-id="2540a-202">此部分列出了由 MCCA 工具所做的任何改进操作（如有需要注意）。</span><span class="sxs-lookup"><span data-stu-id="2540a-202">Any improvement action identified by the MCCA tool as needing attention will be listed in this section.</span></span>

<span data-ttu-id="2540a-203">每个 Microsoft 解决方案旁边都有颜色编码框，指示合规性管理器中与改进操作对应的项目数。</span><span class="sxs-lookup"><span data-stu-id="2540a-203">Next to each Microsoft solution are color-coded boxes indicating the number of items that correspond to improvement actions in Compliance Manager.</span></span> <span data-ttu-id="2540a-204">这些操作分为三个状态状态：</span><span class="sxs-lookup"><span data-stu-id="2540a-204">The actions are broken down into three status states:</span></span>

- <span data-ttu-id="2540a-205">**确定** ：满足推荐条件并在此时间不需要注意的操作</span><span class="sxs-lookup"><span data-stu-id="2540a-205">**OK** : the actions that meet recommended conditions and need no attention at this time</span></span>
- <span data-ttu-id="2540a-206">**改进** ：需要注意的操作</span><span class="sxs-lookup"><span data-stu-id="2540a-206">**Improvement** : actions that need attention</span></span>
- <span data-ttu-id="2540a-207">**建议** ：不需要注意的操作，但我们建议的最佳做法</span><span class="sxs-lookup"><span data-stu-id="2540a-207">**Recommendation** : actions that don’t need attention, but for which we recommend best practices</span></span>
 
<span data-ttu-id="2540a-208">选择一个框以查看改进和建议。</span><span class="sxs-lookup"><span data-stu-id="2540a-208">Select a box to view improvements and recommendations.</span></span>

<span data-ttu-id="2540a-209">**具有改进状态的项目**</span><span class="sxs-lookup"><span data-stu-id="2540a-209">**Items with the Improvement status**</span></span>

<span data-ttu-id="2540a-210">选择 "改进" 操作右侧的 " **改善** " 标签旁边的下拉列表。</span><span class="sxs-lookup"><span data-stu-id="2540a-210">Select the dropdown next to the **Improvement** label to the right of the improvement action.</span></span> <span data-ttu-id="2540a-211">你将看到有关当前设置和建议的改进操作的快速摘要和详细信息。</span><span class="sxs-lookup"><span data-stu-id="2540a-211">You’ll see a quick summary and details about your current settings and the recommended improvement actions.</span></span> <span data-ttu-id="2540a-212">此摘要包括指向合规性管理器的直接链接、Microsoft 365 合规性中心中适用的解决方案以及相关文档。</span><span class="sxs-lookup"><span data-stu-id="2540a-212">The summary includes direct links into Compliance Manager, the applicable solution in the Microsoft 365 compliance center, and relevant documentation.</span></span>

<span data-ttu-id="2540a-213">单击 "合规性管理器" 链接将转到该解决方案中尚未实施的所有改进操作的筛选视图。</span><span class="sxs-lookup"><span data-stu-id="2540a-213">Clicking on the Compliance Manager link takes you to a filtered view of all the improvement actions within that solution that you have not yet implemented.</span></span> <span data-ttu-id="2540a-214">在这里，你可以看到可实现的点数，以增加 [合规性分数](compliance-score-calculation.md)、应用的评估以及适用的法规和证书。</span><span class="sxs-lookup"><span data-stu-id="2540a-214">From there, you can see the number of points you can achieve to increase your [compliance score](compliance-score-calculation.md), and the assessments they apply to, and the applicable regulations and certifications.</span></span>

<span data-ttu-id="2540a-215">对于 DLP，有一个 " **补救脚本** " 按钮，它根据建议的建议为您提供预生成的 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="2540a-215">For DLP, there’s a **Remediation Script** button that gives you a pre-generated PowerShell script based on what’s recommended.</span></span> <span data-ttu-id="2540a-216">您可以直接在 PowerShell 控制台中复制并粘贴它。</span><span class="sxs-lookup"><span data-stu-id="2540a-216">You can copy and paste it directly in your PowerShell console.</span></span> <span data-ttu-id="2540a-217">它将在测试模式下创建 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="2540a-217">It will create a DLP policy in test mode</span></span>

<span data-ttu-id="2540a-218">**具有建议状态的项目**</span><span class="sxs-lookup"><span data-stu-id="2540a-218">**Items with Recommendation status**</span></span>

<span data-ttu-id="2540a-219">选择 "改进" 操作右侧的 " **建议** " 标签旁边的下拉列表。</span><span class="sxs-lookup"><span data-stu-id="2540a-219">Select the dropdown next to the **Recommendation** label to the right of the improvement action.</span></span> <span data-ttu-id="2540a-220">你将看到组织的当前 Microsoft 365 环境与改进操作相关的摘要，以及建议的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="2540a-220">You’ll see a summary of your organization’s current Microsoft 365 environment related to the improvement action, along with recommended best practices.</span></span>

## <a name="resources"></a><span data-ttu-id="2540a-221">资源</span><span class="sxs-lookup"><span data-stu-id="2540a-221">Resources</span></span>

<span data-ttu-id="2540a-222">有关安装、设置和使用 MCCA 的更多详细信息，请参阅 [GitHub 上的自述文件说明](https://github.com/OfficeDev/MCCA#overview) (不需要 GitHub 帐户) 。</span><span class="sxs-lookup"><span data-stu-id="2540a-222">For more detailed information on installing, setting up, and using MCCA, see the [README instructions on GitHub](https://github.com/OfficeDev/MCCA#overview) (no GitHub account required).</span></span>

<span data-ttu-id="2540a-223">有关 Windows PowerShell 的详细信息，请从 [如何使用 PowerShell 文档](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7)入手。</span><span class="sxs-lookup"><span data-stu-id="2540a-223">For more information on Windows PowerShell, start at [How to use the PowerShell documentation](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7).</span></span> <span data-ttu-id="2540a-224">另请参阅 [启动 Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)。</span><span class="sxs-lookup"><span data-stu-id="2540a-224">See also [Starting Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).</span></span>
