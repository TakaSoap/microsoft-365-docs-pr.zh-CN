---
title: 检测和修正 Outlook 规则和自定义窗体注入攻击。
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 04/23/2018
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: 了解如何识别和修正 Office 365 中的 Outlook 规则和自定义窗体注入攻击
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 30ddd5f57dee2156504211e76304d346a63e192d
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406696"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a><span data-ttu-id="11ad2-103">检测和修正 Outlook 规则和自定义窗体注入攻击</span><span class="sxs-lookup"><span data-stu-id="11ad2-103">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="11ad2-104">**摘要** 了解如何识别和修正 Office 365 中的 Outlook 规则和自定义窗体注入攻击。</span><span class="sxs-lookup"><span data-stu-id="11ad2-104">**Summary** Learn how to recognize and remediate the Outlook rules and custom Forms injections attacks in Office 365.</span></span>

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a><span data-ttu-id="11ad2-105">什么是 Outlook 规则和自定义窗体注入攻击？</span><span class="sxs-lookup"><span data-stu-id="11ad2-105">What is the Outlook Rules and Custom Forms injection attack?</span></span>

<span data-ttu-id="11ad2-106">攻击者获取对组织的访问权限后，将尝试建立一个保留或发现后重新进入的页脚。</span><span class="sxs-lookup"><span data-stu-id="11ad2-106">After an attacker gains access to your organization, they'll try to establish a foothold to stay in or get back in after they've been discovered.</span></span> <span data-ttu-id="11ad2-107">此活动称为 *建立持久性机制*。</span><span class="sxs-lookup"><span data-stu-id="11ad2-107">This activity is called *establishing a persistence mechanism*.</span></span> <span data-ttu-id="11ad2-108">攻击者可通过两种方法使用 Outlook 建立持久性机制：</span><span class="sxs-lookup"><span data-stu-id="11ad2-108">There are two ways that an attacker can use Outlook to establish a persistence mechanism:</span></span>

- <span data-ttu-id="11ad2-109">利用 Outlook 规则。</span><span class="sxs-lookup"><span data-stu-id="11ad2-109">By exploiting Outlook rules.</span></span>
- <span data-ttu-id="11ad2-110">通过向 Outlook 中注入自定义窗体。</span><span class="sxs-lookup"><span data-stu-id="11ad2-110">By injecting custom forms into Outlook.</span></span>

<span data-ttu-id="11ad2-111">重新安装 Outlook，甚至向受影响的人员提供一台新计算机将没有帮助。</span><span class="sxs-lookup"><span data-stu-id="11ad2-111">Reinstalling Outlook, or even giving the affected person a new computer won't help.</span></span> <span data-ttu-id="11ad2-112">当全新安装的 Outlook 连接到邮箱时，所有规则和表单都从云中同步。</span><span class="sxs-lookup"><span data-stu-id="11ad2-112">When the fresh installation of Outlook connects to the mailbox, all rules and forms are synchronized from the cloud.</span></span> <span data-ttu-id="11ad2-113">规则或表单通常设计为在本地计算机上运行远程代码和安装恶意软件。</span><span class="sxs-lookup"><span data-stu-id="11ad2-113">The rules or forms are typically designed to run remote code and install malware on the local machine.</span></span> <span data-ttu-id="11ad2-114">恶意软件窃取凭据或执行其他非法活动。</span><span class="sxs-lookup"><span data-stu-id="11ad2-114">The malware steals credentials or performs other illicit activity.</span></span>

<span data-ttu-id="11ad2-115">好消息是：如果你将 Outlook 客户端修补为最新版本，则你无法受到威胁，因为当前的 Outlook 客户端默认会阻止这两种机制。</span><span class="sxs-lookup"><span data-stu-id="11ad2-115">The good news is: if you keep your Outlook clients patched to the latest version, you aren't vulnerable to the threat as current Outlook client defaults block both mechanisms.</span></span>

<span data-ttu-id="11ad2-116">攻击通常遵循以下模式：</span><span class="sxs-lookup"><span data-stu-id="11ad2-116">The attacks typically follow these patterns:</span></span>

<span data-ttu-id="11ad2-117">**规则攻击**：</span><span class="sxs-lookup"><span data-stu-id="11ad2-117">**The Rules Exploit**:</span></span>

1. <span data-ttu-id="11ad2-118">攻击者窃取用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="11ad2-118">The attacker steals a user's credentials.</span></span>

2. <span data-ttu-id="11ad2-119">攻击者在 Exchange Online 或本地 Exchange (登录该用户的 Exchange) 。</span><span class="sxs-lookup"><span data-stu-id="11ad2-119">The attacker signs in to that user's Exchange mailbox (Exchange Online or on-premises Exchange).</span></span>

3. <span data-ttu-id="11ad2-120">攻击者在邮箱中创建转发收件箱规则。</span><span class="sxs-lookup"><span data-stu-id="11ad2-120">The attacker creates a forwarding Inbox rule in the mailbox.</span></span> <span data-ttu-id="11ad2-121">当邮箱从攻击者收到匹配规则条件的特定邮件时，将触发转发规则。</span><span class="sxs-lookup"><span data-stu-id="11ad2-121">The forwarding rule is triggered when the mailbox receives a specific message from the attacker that matches the conditions of the rule.</span></span> <span data-ttu-id="11ad2-122">规则条件和邮件格式是互为定制的。</span><span class="sxs-lookup"><span data-stu-id="11ad2-122">The rule conditions and message format are tailor-made for each other.</span></span>

4. <span data-ttu-id="11ad2-123">攻击者将触发器电子邮件发送到遭到入侵的邮箱，不知情的用户仍正常使用该邮箱。</span><span class="sxs-lookup"><span data-stu-id="11ad2-123">The attacker sends the trigger email to the compromised mailbox, which is still being used as normal by the unsuspecting user.</span></span>

5. <span data-ttu-id="11ad2-124">当邮箱收到与规则条件匹配的邮件时，将应用规则的操作。</span><span class="sxs-lookup"><span data-stu-id="11ad2-124">When the mailbox receives a message that matches the conditions of rule, the action of the rule is applied.</span></span> <span data-ttu-id="11ad2-125">通常，规则操作是在远程 WebDAV (启动) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="11ad2-125">Typically, the rule action is to launch an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="11ad2-126">通常，应用程序在用户计算机上安装恶意软件 (例如 [PowerShell 高级](https://www.powershellempire.com/)) 。</span><span class="sxs-lookup"><span data-stu-id="11ad2-126">Typically, the application installs malware on the user's machine (for example, [PowerShell Empire](https://www.powershellempire.com/)).</span></span>

7. <span data-ttu-id="11ad2-127">恶意软件允许攻击者从本地计算机 (或) 用户用户名和密码或其他凭据，或者执行其他恶意活动。</span><span class="sxs-lookup"><span data-stu-id="11ad2-127">The malware allows the attacker to steal (or steal again) the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

<span data-ttu-id="11ad2-128">**表单攻击**：</span><span class="sxs-lookup"><span data-stu-id="11ad2-128">**The Forms Exploit**:</span></span>

1. <span data-ttu-id="11ad2-129">攻击者窃取用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="11ad2-129">The attacker steals a user's credentials.</span></span>

2. <span data-ttu-id="11ad2-130">攻击者在 Exchange Online 或本地 Exchange (登录该用户的 Exchange) 。</span><span class="sxs-lookup"><span data-stu-id="11ad2-130">The attacker signs in to that user's Exchange mailbox (Exchange Online or on-premises Exchange).</span></span>

3. <span data-ttu-id="11ad2-131">攻击者将自定义邮件表单模板用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="11ad2-131">The attacker inserts a custom mail form template into the user's mailbox.</span></span> <span data-ttu-id="11ad2-132">当邮箱收到来自攻击者的特定邮件（要求邮箱加载自定义表单）时，将触发自定义表单。</span><span class="sxs-lookup"><span data-stu-id="11ad2-132">The custom form is triggered when the mailbox receives a specific message from the attacker that requires the mailbox to load the custom form.</span></span> <span data-ttu-id="11ad2-133">自定义窗体和邮件格式是互为定制的。</span><span class="sxs-lookup"><span data-stu-id="11ad2-133">The custom form and the message format are tailor-made for each other.</span></span>

4. <span data-ttu-id="11ad2-134">攻击者将触发器电子邮件发送到遭到入侵的邮箱，不知情的用户仍正常使用该邮箱。</span><span class="sxs-lookup"><span data-stu-id="11ad2-134">The attacker sends the trigger email to the compromised mailbox, which is still being used as normal by the unsuspecting user.</span></span>

5. <span data-ttu-id="11ad2-135">当邮箱收到邮件时，邮箱将加载所需的表单。</span><span class="sxs-lookup"><span data-stu-id="11ad2-135">When the mailbox receives the message, the mailbox loads the required form.</span></span> <span data-ttu-id="11ad2-136">表单将在远程 WebDAV (启动) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="11ad2-136">The form launches an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="11ad2-137">通常，应用程序在用户计算机上安装恶意软件 (例如 [PowerShell 管理](https://www.powershellempire.com/) 中心) 。</span><span class="sxs-lookup"><span data-stu-id="11ad2-137">Typically, the application installs malware on the user's machine (for example, [PowerShell Empire](https://www.powershellempire.com/)).</span></span>

7. <span data-ttu-id="11ad2-138">恶意软件允许攻击者从本地计算机 (或) 用户用户名和密码或其他凭据，或者执行其他恶意活动。</span><span class="sxs-lookup"><span data-stu-id="11ad2-138">The malware allows the attacker to steal (or steal again) the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a><span data-ttu-id="11ad2-139">规则和自定义表单注入攻击可能看起来像 Office 365？</span><span class="sxs-lookup"><span data-stu-id="11ad2-139">What a Rules and Custom Forms Injection attack might look like Office 365?</span></span>

<span data-ttu-id="11ad2-140">这些持久性机制不太可能被用户注意到，并且在某些情况下甚至对用户不可见。</span><span class="sxs-lookup"><span data-stu-id="11ad2-140">These persistence mechanisms are unlikely to be noticed by your users and may in some cases even be invisible to them.</span></span> <span data-ttu-id="11ad2-141">本文将告诉你如何查找下面列出的七 (泄露指示器) 中的任意一个。</span><span class="sxs-lookup"><span data-stu-id="11ad2-141">This article tells you how to look for any of the seven signs (Indicators of Compromise) listed below.</span></span> <span data-ttu-id="11ad2-142">如果找到其中任何一个，则需要执行修正步骤。</span><span class="sxs-lookup"><span data-stu-id="11ad2-142">If you find any of these, you need to take remediation steps.</span></span>

- <span data-ttu-id="11ad2-143">**规则泄露指示器**：</span><span class="sxs-lookup"><span data-stu-id="11ad2-143">**Indicators of the Rules compromise**:</span></span>
  - <span data-ttu-id="11ad2-144">规则操作是启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="11ad2-144">Rule Action is to start an application.</span></span>
  - <span data-ttu-id="11ad2-145">规则引用 EXE、ZIP 或 URL。</span><span class="sxs-lookup"><span data-stu-id="11ad2-145">Rule References an EXE, ZIP, or URL.</span></span>
  - <span data-ttu-id="11ad2-146">在本地计算机上，查找源自 Outlook PID 的新进程启动。</span><span class="sxs-lookup"><span data-stu-id="11ad2-146">On the local machine, look for new process starts that originate from the Outlook PID.</span></span>

- <span data-ttu-id="11ad2-147">**自定义表单泄露指示器**：</span><span class="sxs-lookup"><span data-stu-id="11ad2-147">**Indicators of the Custom forms compromise**:</span></span>
  - <span data-ttu-id="11ad2-148">呈现为其自己的邮件类的自定义窗体。</span><span class="sxs-lookup"><span data-stu-id="11ad2-148">Custom forms present saved as their own message class.</span></span>
  - <span data-ttu-id="11ad2-149">邮件类包含可执行代码。</span><span class="sxs-lookup"><span data-stu-id="11ad2-149">Message class contains executable code.</span></span>
  - <span data-ttu-id="11ad2-150">通常，恶意表单存储在个人窗体库或收件箱文件夹中。</span><span class="sxs-lookup"><span data-stu-id="11ad2-150">Typically, malicious forms are stored in Personal Forms Library or Inbox folders.</span></span>
  - <span data-ttu-id="11ad2-151">窗体名为 IPM。请注意。[自定义名称]。</span><span class="sxs-lookup"><span data-stu-id="11ad2-151">Form is named IPM.Note.[custom name].</span></span>

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a><span data-ttu-id="11ad2-152">查找此攻击的迹象并确认它的步骤</span><span class="sxs-lookup"><span data-stu-id="11ad2-152">Steps for finding signs of this attack and confirming it</span></span>

<span data-ttu-id="11ad2-153">可以使用以下任一方法确认攻击：</span><span class="sxs-lookup"><span data-stu-id="11ad2-153">You can use either of the following methods to confirm the attack:</span></span>

- <span data-ttu-id="11ad2-154">使用 Outlook 客户端手动检查每个邮箱的规则和表单。</span><span class="sxs-lookup"><span data-stu-id="11ad2-154">Manually examine the rules and forms for each mailbox using the Outlook client.</span></span> <span data-ttu-id="11ad2-155">此方法非常彻底，但一次只能检查一个邮箱。</span><span class="sxs-lookup"><span data-stu-id="11ad2-155">This method is thorough, but you can only check one mailbox at a time.</span></span> <span data-ttu-id="11ad2-156">如果有许多用户要检查，此方法可能非常耗时，并且还可能会感染你使用的计算机。</span><span class="sxs-lookup"><span data-stu-id="11ad2-156">This method can be very time consuming if you have many users to check, and might also infect the computer that you're using.</span></span>

- <span data-ttu-id="11ad2-157">使用 [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 脚本自动转储租赁中所有用户的所有邮件转发规则和自定义表单。</span><span class="sxs-lookup"><span data-stu-id="11ad2-157">Use the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script to automatically dump all the mail forwarding rules and custom forms for all the users in your tenancy.</span></span> <span data-ttu-id="11ad2-158">这是最快、最安全的方法，开销最少。</span><span class="sxs-lookup"><span data-stu-id="11ad2-158">This is the fastest and safest method with the least amount of overhead.</span></span>

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a><span data-ttu-id="11ad2-159">使用 Outlook 客户端确认规则攻击</span><span class="sxs-lookup"><span data-stu-id="11ad2-159">Confirm the Rules Attack Using the Outlook client</span></span>

1. <span data-ttu-id="11ad2-160">以用户状态打开用户 Outlook 客户端。</span><span class="sxs-lookup"><span data-stu-id="11ad2-160">Open the users Outlook client as the user.</span></span> <span data-ttu-id="11ad2-161">用户可能需要你的帮助来检查其邮箱上的规则。</span><span class="sxs-lookup"><span data-stu-id="11ad2-161">The user may need your help in examining the rules on their mailbox.</span></span>

2. <span data-ttu-id="11ad2-162">有关在 Outlook [中打开](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) 规则界面的过程，请参阅"使用规则文章管理电子邮件"。</span><span class="sxs-lookup"><span data-stu-id="11ad2-162">Refer to [Manage email messages by using rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) article for the procedures on how to open the rules interface in Outlook.</span></span>

3. <span data-ttu-id="11ad2-163">查找用户未创建的规则，或任何具有可疑名称的意外规则或规则。</span><span class="sxs-lookup"><span data-stu-id="11ad2-163">Look for rules that the user did not create, or any unexpected rules or rules with suspicious names.</span></span>

4. <span data-ttu-id="11ad2-164">查看规则说明，了解启动和应用程序的规则操作或引用 。EXE， .ZIP 文件或启动 URL。</span><span class="sxs-lookup"><span data-stu-id="11ad2-164">Look in the rule description for rule actions that start and application or refer to an .EXE, .ZIP file or to launching a URL.</span></span>

5. <span data-ttu-id="11ad2-165">查找开始使用 Outlook 进程 ID 的任何新进程。</span><span class="sxs-lookup"><span data-stu-id="11ad2-165">Look for any new processes that start using the Outlook process ID.</span></span> <span data-ttu-id="11ad2-166">请参阅["查找进程 ID"。](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)</span><span class="sxs-lookup"><span data-stu-id="11ad2-166">Refer to [Find the Process ID](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id).</span></span>

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a><span data-ttu-id="11ad2-167">使用 Outlook 客户端确认表单攻击的步骤</span><span class="sxs-lookup"><span data-stu-id="11ad2-167">Steps to confirm the Forms attack using the Outlook client</span></span>

1. <span data-ttu-id="11ad2-168">以用户状态打开用户 Outlook 客户端。</span><span class="sxs-lookup"><span data-stu-id="11ad2-168">Open the user Outlook client as the user.</span></span>

2. <span data-ttu-id="11ad2-169">按照用户版本的 Outlook [的"](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) 显示开发人员"选项卡中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="11ad2-169">Follow the steps in, [Show the Developer tab](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) for the user's version of Outlook.</span></span>

3. <span data-ttu-id="11ad2-170">在 Outlook 中打开现在可见的开发人员选项卡，然后单击 **设计窗体**。</span><span class="sxs-lookup"><span data-stu-id="11ad2-170">Open the now visible developer tab in Outlook and click **design a form**.</span></span>

4. <span data-ttu-id="11ad2-171">从 **"查找** " **列表中选择收件箱** 。</span><span class="sxs-lookup"><span data-stu-id="11ad2-171">Select the **Inbox** from the **Look In** list.</span></span> <span data-ttu-id="11ad2-172">查找任何自定义窗体。</span><span class="sxs-lookup"><span data-stu-id="11ad2-172">Look for any custom forms.</span></span> <span data-ttu-id="11ad2-173">自定义窗体很少见，因此，如果有任何自定义窗体，则值得更深入地查看。</span><span class="sxs-lookup"><span data-stu-id="11ad2-173">Custom forms are rare enough that if you have any custom forms at all, it is worth a deeper look.</span></span>

5. <span data-ttu-id="11ad2-174">调查任何自定义表单，尤其是标记为隐藏的自定义表单。</span><span class="sxs-lookup"><span data-stu-id="11ad2-174">Investigate any custom forms, especially those marked as hidden.</span></span>

6. <span data-ttu-id="11ad2-175">打开任何自定义窗体，在 **"窗体** "组中单击 **"查看** 代码"以查看在加载窗体时运行哪些内容。</span><span class="sxs-lookup"><span data-stu-id="11ad2-175">Open any custom forms and in the **Form** group click **View Code** to see what runs when the form is loaded.</span></span>

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a><span data-ttu-id="11ad2-176">使用 PowerShell 确认规则和表单攻击的步骤</span><span class="sxs-lookup"><span data-stu-id="11ad2-176">Steps to confirm the Rules and Forms attack using PowerShell</span></span>

<span data-ttu-id="11ad2-177">验证规则或自定义表单攻击的最简单方法就是运行 [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="11ad2-177">The simplest way to verify a rules or custom forms attack is to run the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script.</span></span> <span data-ttu-id="11ad2-178">此脚本连接到租户中的每个邮箱，将所有规则和表单转储到两个 .csv 文件中。</span><span class="sxs-lookup"><span data-stu-id="11ad2-178">This script connects to every mailbox in your tenant and dumps all the rules and forms into two .csv files.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="11ad2-179">先决条件</span><span class="sxs-lookup"><span data-stu-id="11ad2-179">Pre-requisites</span></span>

<span data-ttu-id="11ad2-180">您需要具有全局管理员权限才能运行脚本，因为脚本连接到租赁中的每个邮箱以读取规则和表单。</span><span class="sxs-lookup"><span data-stu-id="11ad2-180">You will need to have global administrator rights to run the script because the script connects to every mailbox in the tenancy to read the rules and forms.</span></span>

1. <span data-ttu-id="11ad2-181">使用本地管理员权限登录到您将从中运行脚本计算机。</span><span class="sxs-lookup"><span data-stu-id="11ad2-181">Sign in to the machine that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="11ad2-182">从 GitHub 下载Get-AllTenantRulesAndForms.ps1脚本，或将其复制到运行脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="11ad2-182">Download or copy the Get-AllTenantRulesAndForms.ps1 script from GitHub to a folder from which you will run it.</span></span> <span data-ttu-id="11ad2-183">脚本将为此文件夹创建两个日期标记文件，即MailboxFormsExport-yyyy-mm-dd.csv和MailboxRulesExport-yyyy-mm-dd.csv。</span><span class="sxs-lookup"><span data-stu-id="11ad2-183">The script will create two date stamped files to this folder, MailboxFormsExport-yyyy-mm-dd.csv, and MailboxRulesExport-yyyy-mm-dd.csv.</span></span>

3. <span data-ttu-id="11ad2-184">以管理员角色打开 PowerShell 实例，然后打开将脚本保存到的文件夹。</span><span class="sxs-lookup"><span data-stu-id="11ad2-184">Open a PowerShell instance as an administrator and open the folder you saved the script to.</span></span>

4. <span data-ttu-id="11ad2-185">运行此 PowerShell 命令行， `.\Get-AllTenantRulesAndForms.ps1` 如下所示.\Get-AllTenantRulesAndForms.ps1</span><span class="sxs-lookup"><span data-stu-id="11ad2-185">Run this PowerShell command line as follows `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1</span></span>

#### <a name="interpreting-the-output"></a><span data-ttu-id="11ad2-186">解释输出</span><span class="sxs-lookup"><span data-stu-id="11ad2-186">Interpreting the output</span></span>

- <span data-ttu-id="11ad2-187">**MailboxRulesExport-*yyyy-mm-dd*.csv：** 检查每行 (一个规则) 检查包含应用程序或可执行文件的操作条件：</span><span class="sxs-lookup"><span data-stu-id="11ad2-187">**MailboxRulesExport-*yyyy-mm-dd*.csv**: Examine the rules (one per row) for action conditions that include applications or executables:</span></span>

  - <span data-ttu-id="11ad2-188">**ActionType (A 列) ：** 如果看到值"ID_ACTION_CUSTOM"，则规则可能是恶意的。</span><span class="sxs-lookup"><span data-stu-id="11ad2-188">**ActionType (column A)**: If you see the value "ID_ACTION_CUSTOM", the rule is likely malicious.</span></span>

  - <span data-ttu-id="11ad2-189">**IsPotentiallyMalicious (D)**： 如果此值为"TRUE"，则规则可能是恶意的。</span><span class="sxs-lookup"><span data-stu-id="11ad2-189">**IsPotentiallyMalicious (column D)**: If this value is "TRUE", the rule is likely malicious.</span></span>

  - <span data-ttu-id="11ad2-190">**ActionCommand (列 G) ：** 如果此列列出具有 .exe 或 .zip 扩展名的应用程序或任何文件，或者引用 URL 的未知条目，则规则可能是恶意的。</span><span class="sxs-lookup"><span data-stu-id="11ad2-190">**ActionCommand (column G)**: If this column lists an application or any file with .exe or .zip extensions, or an unknown entry that refers to a URL, the rule is likely malicious.</span></span>

- <span data-ttu-id="11ad2-191">**MailboxFormsExport-*yyyy-mm-dd*.csv：** 通常，很少使用自定义窗体。</span><span class="sxs-lookup"><span data-stu-id="11ad2-191">**MailboxFormsExport-*yyyy-mm-dd*.csv**: In general, the use of custom forms is rare.</span></span> <span data-ttu-id="11ad2-192">如果在此工作簿中发现任何内容，则打开该用户的邮箱并检查表单本身。</span><span class="sxs-lookup"><span data-stu-id="11ad2-192">If you find any in this workbook, you open that user's mailbox and examine the form itself.</span></span> <span data-ttu-id="11ad2-193">如果组织没有有意将文件放在该站点，则可能是恶意的。</span><span class="sxs-lookup"><span data-stu-id="11ad2-193">If your organization did not put it there intentionally, it is likely malicious.</span></span>

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a><span data-ttu-id="11ad2-194">如何停止和修正 Outlook 规则和窗体攻击</span><span class="sxs-lookup"><span data-stu-id="11ad2-194">How to stop and remediate the Outlook Rules and Forms attack</span></span>

<span data-ttu-id="11ad2-195">如果找到这些攻击的任何证据，修正非常简单，只需从邮箱中删除规则或表单。</span><span class="sxs-lookup"><span data-stu-id="11ad2-195">If you find any evidence of either of these attacks, remediation is simple, just delete the rule or form from the mailbox.</span></span> <span data-ttu-id="11ad2-196">可以使用 Outlook 客户端或远程 PowerShell 来删除规则。</span><span class="sxs-lookup"><span data-stu-id="11ad2-196">You can do this with the Outlook client or using remote PowerShell to remove rules.</span></span>

### <a name="using-outlook"></a><span data-ttu-id="11ad2-197">使用 Outlook</span><span class="sxs-lookup"><span data-stu-id="11ad2-197">Using Outlook</span></span>

1. <span data-ttu-id="11ad2-198">标识用户用于 Outlook 的所有设备。</span><span class="sxs-lookup"><span data-stu-id="11ad2-198">Identify all the devices that the user has used with Outlook.</span></span> <span data-ttu-id="11ad2-199">它们都需要清除潜在恶意软件。</span><span class="sxs-lookup"><span data-stu-id="11ad2-199">They will all need to be cleaned of potential malware.</span></span> <span data-ttu-id="11ad2-200">在清理所有设备之前，不允许用户登录和使用电子邮件。</span><span class="sxs-lookup"><span data-stu-id="11ad2-200">Do not allow the user to sign on and use email until all the devices are cleaned.</span></span>

2. <span data-ttu-id="11ad2-201">按照" [删除每个设备的规则](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) "中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="11ad2-201">Follow the steps in [Delete a rule](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) for each device.</span></span>

3. <span data-ttu-id="11ad2-202">如果你不确定是否存在其他恶意软件，你可以格式化并重新安装设备上的所有软件。</span><span class="sxs-lookup"><span data-stu-id="11ad2-202">If you are unsure about the presence of other malware, you can format and reinstall all the software on the device.</span></span> <span data-ttu-id="11ad2-203">对于移动设备，你可以按照制造商步骤将设备重置为出厂映像。</span><span class="sxs-lookup"><span data-stu-id="11ad2-203">For mobile devices, you can follow the manufacturers steps to reset the device to the factory image.</span></span>

4. <span data-ttu-id="11ad2-204">安装最新版本的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="11ad2-204">Install the most up-to-date versions of Outlook.</span></span> <span data-ttu-id="11ad2-205">请记住，默认情况下，当前版本的 Outlook 会阻止这两种类型的攻击。</span><span class="sxs-lookup"><span data-stu-id="11ad2-205">Remember that the current version of Outlook blocks both types of this attack by default.</span></span>

5. <span data-ttu-id="11ad2-206">删除邮箱的所有脱机副本后，请重置用户密码 (请使用一个高质量) ，如果尚未启用 MFA，请按照用户安装程序多重身份验证中的步骤操作[](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="11ad2-206">Once all offline copies of the mailbox have been removed, reset the user's password (use a high quality one) and follow the steps in [Setup multi-factor authentication for users](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) if MFA has not already been enabled.</span></span> <span data-ttu-id="11ad2-207">这将确保用户凭据不会通过其他方式公开， (例如钓鱼或密码重新使用) 。</span><span class="sxs-lookup"><span data-stu-id="11ad2-207">This ensures that the user's credentials are not exposed via other means (such as phishing or password re-use).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="11ad2-208">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="11ad2-208">Using PowerShell</span></span>

<span data-ttu-id="11ad2-209">有两个远程 PowerShell cmdlet 可用于删除或禁用危险规则。</span><span class="sxs-lookup"><span data-stu-id="11ad2-209">There are two remote PowerShell cmdlets you can use to remove or disable dangerous rules.</span></span> <span data-ttu-id="11ad2-210">只需按照步骤操作。</span><span class="sxs-lookup"><span data-stu-id="11ad2-210">Just follow the steps.</span></span>

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a><span data-ttu-id="11ad2-211">Exchange 服务器上邮箱的步骤</span><span class="sxs-lookup"><span data-stu-id="11ad2-211">Steps for mailboxes that are on an Exchange server</span></span>

1. <span data-ttu-id="11ad2-212">使用远程 PowerShell 连接到 Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="11ad2-212">Connect to the Exchange server using remote PowerShell.</span></span> <span data-ttu-id="11ad2-213">按照使用远程 [PowerShell 连接到 Exchange 服务器中的步骤操作](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)。</span><span class="sxs-lookup"><span data-stu-id="11ad2-213">Follow the steps in [Connect to Exchange servers using remote PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="11ad2-214">如果要从邮箱中完全删除单个规则、多个规则或所有规则，请使用 [Remove-InboxRule](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="11ad2-214">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-InboxRule](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="11ad2-215">如果要保留规则及其内容以进一步调查，请使用 [Disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="11ad2-215">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) cmdlet.</span></span>

#### <a name="steps-for-mailboxes-in-exchange-online"></a><span data-ttu-id="11ad2-216">Exchange Online 中邮箱的步骤</span><span class="sxs-lookup"><span data-stu-id="11ad2-216">Steps for mailboxes in Exchange Online</span></span>

1. <span data-ttu-id="11ad2-217">按照使用 [PowerShell 连接到 Exchange Online 中的步骤操作](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="11ad2-217">Follow the steps in [Connect to Exchange Online using PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="11ad2-218">如果要从邮箱中完全删除单个规则、多个规则或所有规则，请使用 [Remove-Inbox 规则](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="11ad2-218">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-Inbox Rule](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="11ad2-219">如果要保留规则及其内容以进一步调查，请使用 [Disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="11ad2-219">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) cmdlet.</span></span>

## <a name="how-to-minimize-future-attacks"></a><span data-ttu-id="11ad2-220">如何最大程度地减少未来攻击</span><span class="sxs-lookup"><span data-stu-id="11ad2-220">How to minimize future attacks</span></span>

### <a name="first-protect-your-accounts"></a><span data-ttu-id="11ad2-221">首先：保护帐户</span><span class="sxs-lookup"><span data-stu-id="11ad2-221">First: protect your accounts</span></span>

<span data-ttu-id="11ad2-222">规则和表单漏洞仅在攻击者窃取或破坏用户帐户之一后使用。</span><span class="sxs-lookup"><span data-stu-id="11ad2-222">The Rules and Forms exploits are only used by an attacker after they have stolen or breached one of your user's accounts.</span></span> <span data-ttu-id="11ad2-223">因此，阻止对组织使用这些攻击的第一步是主动保护你的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="11ad2-223">So, your first step to preventing the use of these exploits against your organization is to aggressively protect your user accounts.</span></span> <span data-ttu-id="11ad2-224">帐户遭到入侵的一些最常见方式是通过网络钓鱼或密码 [攻击](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/)。</span><span class="sxs-lookup"><span data-stu-id="11ad2-224">Some of the most common ways that accounts are breached are through phishing or [password spray attacks](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/).</span></span>

<span data-ttu-id="11ad2-225">保护用户帐户（尤其是管理员帐户）的最佳方法就是为用户设置 [多重身份验证](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="11ad2-225">The best way to protect your user accounts, and especially your administrator accounts, is to [set up multi-factor authentication for users](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span> <span data-ttu-id="11ad2-226">您还应：</span><span class="sxs-lookup"><span data-stu-id="11ad2-226">You should also:</span></span>

- <span data-ttu-id="11ad2-227">监视如何访问 [和使用用户帐户](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports)。</span><span class="sxs-lookup"><span data-stu-id="11ad2-227">Monitor how your user accounts are [accessed and used](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports).</span></span> <span data-ttu-id="11ad2-228">虽然无法阻止初始泄露，但通过提前检测，可以缩短泄露的持续时间和影响。</span><span class="sxs-lookup"><span data-stu-id="11ad2-228">You may not prevent the initial breach, but you will shorten the duration and the impact of the breach by detecting it sooner.</span></span> <span data-ttu-id="11ad2-229">可以使用以下 [Office 365 云应用安全策略](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) 监视帐户，并提醒异常活动：</span><span class="sxs-lookup"><span data-stu-id="11ad2-229">You can use these [Office 365 Cloud App Security policies](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) to monitor you accounts and alert on unusual activity:</span></span>

  - <span data-ttu-id="11ad2-230">**多次失败的登录** 尝试：此策略会配置文件您的环境，当用户在一个会话中执行多个与已了解的基线有关失败登录活动时触发警报，这可能表示已尝试泄露。</span><span class="sxs-lookup"><span data-stu-id="11ad2-230">**Multiple failed login attempts**: This policy profiles your environment and triggers alerts when users perform multiple failed login activities in a single session with respect to the learned baseline, which could indicate an attempted breach.</span></span>

  - <span data-ttu-id="11ad2-231">**不可能旅行**：此策略将配置文件您的环境，当在两个位置之间的预期旅行时间短于预期旅行时间的不同位置检测到同一用户时，将触发警报。</span><span class="sxs-lookup"><span data-stu-id="11ad2-231">**Impossible travel**: This policy profiles your environment and triggers alerts when activities are detected from the same user in different locations within a time period that is shorter than the expected travel time between the two locations.</span></span> <span data-ttu-id="11ad2-232">这可能表示其他用户使用相同的凭据。</span><span class="sxs-lookup"><span data-stu-id="11ad2-232">This could indicate that a different user is using the same credentials.</span></span> <span data-ttu-id="11ad2-233">检测此异常行为需要初始学习期 7 天，在此期间它将了解新用户的活动模式。</span><span class="sxs-lookup"><span data-stu-id="11ad2-233">Detecting this anomalous behavior necessitates an initial learning period of seven days during which it learns a new user's activity pattern.</span></span>

  - <span data-ttu-id="11ad2-234">用户 (执行的异常模拟 **活动) ：** 此策略将配置文件您的环境，并触发警报，当用户在一个会话中执行与所了解的基线有关的多个模拟活动，这可能表示已尝试泄露。</span><span class="sxs-lookup"><span data-stu-id="11ad2-234">**Unusual impersonated activity (by user)**: This policy profiles your environment and triggers alerts when users perform multiple impersonated activities in a single session with respect to the baseline learned, which could indicate an attempted breach.</span></span>

- <span data-ttu-id="11ad2-235">使用 Office [365 安全分数等](https://securescore.office.com/) 工具管理帐户安全配置和行为。</span><span class="sxs-lookup"><span data-stu-id="11ad2-235">Use a tool like [Office 365 Secure Score](https://securescore.office.com/) to manage account security configurations and behaviors.</span></span>

### <a name="second-keep-your-outlook-clients-current"></a><span data-ttu-id="11ad2-236">Second： Keep your Outlook clients current</span><span class="sxs-lookup"><span data-stu-id="11ad2-236">Second: Keep your Outlook clients current</span></span>

<span data-ttu-id="11ad2-237">Outlook 2013 和 2016 的完全更新和修补版本默认情况下禁用"启动应用程序"规则/窗体操作。</span><span class="sxs-lookup"><span data-stu-id="11ad2-237">Fully updated and patched versions of Outlook 2013, and 2016 disable the "Start Application" rule/form action by default.</span></span> <span data-ttu-id="11ad2-238">这将确保即使攻击者违反帐户，也会阻止该规则及表单操作。</span><span class="sxs-lookup"><span data-stu-id="11ad2-238">This will ensure that even if an attacker breaches the account, the rule and form actions will be blocked.</span></span> <span data-ttu-id="11ad2-239">可以按照安装 Office 更新中的步骤安装最新更新 [和安全修补程序](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)。</span><span class="sxs-lookup"><span data-stu-id="11ad2-239">You can install the latest updates and security patches by following the steps in [Install Office updates](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5).</span></span>

<span data-ttu-id="11ad2-240">以下是 Outlook 2013 和 2016 客户端的修补程序版本：</span><span class="sxs-lookup"><span data-stu-id="11ad2-240">Here are the patch versions for your Outlook 2013 and 2016 clients:</span></span>

- <span data-ttu-id="11ad2-241">**Outlook 2016**：16.0.4534.1001 或更大。</span><span class="sxs-lookup"><span data-stu-id="11ad2-241">**Outlook 2016**: 16.0.4534.1001 or greater.</span></span>

- <span data-ttu-id="11ad2-242">**Outlook** 2013：15.0.4937.1000 或更大。</span><span class="sxs-lookup"><span data-stu-id="11ad2-242">**Outlook 2013**: 15.0.4937.1000 or greater.</span></span>

<span data-ttu-id="11ad2-243">有关各个安全修补程序详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="11ad2-243">For more information on the individual security patches, see:</span></span>

- [<span data-ttu-id="11ad2-244">Outlook 2016 安全修补程序</span><span class="sxs-lookup"><span data-stu-id="11ad2-244">Outlook 2016 Security Patch</span></span>](https://support.microsoft.com/help/3191883)

- [<span data-ttu-id="11ad2-245">Outlook 2013 安全修补程序</span><span class="sxs-lookup"><span data-stu-id="11ad2-245">Outlook 2013 Security Patch</span></span>](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a><span data-ttu-id="11ad2-246">第三：监视 Outlook 客户端</span><span class="sxs-lookup"><span data-stu-id="11ad2-246">Third: Monitor your Outlook clients</span></span>

<span data-ttu-id="11ad2-247">请注意，即使安装了修补程序和更新，攻击者也可以更改本地计算机配置以重新启用"启动应用程序"行为。</span><span class="sxs-lookup"><span data-stu-id="11ad2-247">Note that even with the patches and updates installed, it is possible for an attacker to change the local machine configuration to re-enable the "Start Application" behavior.</span></span> <span data-ttu-id="11ad2-248">可以使用高级 [组策略管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) 监视和强制执行客户端上的本地计算机策略。</span><span class="sxs-lookup"><span data-stu-id="11ad2-248">You can use [Advanced Group Policy Management](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) to monitor and enforce local machine policies on your clients.</span></span>

<span data-ttu-id="11ad2-249">通过使用如何使用 [64](https://support.microsoft.com/help/305097)位版本的 Windows 查看系统注册表，你可以看到"启动应用程序"是否通过注册表中的覆盖重新启用。</span><span class="sxs-lookup"><span data-stu-id="11ad2-249">You can see if "Start Application" has been re-enabled through an override in the registry by using the information in [How to view the system registry by using 64-bit versions of Windows](https://support.microsoft.com/help/305097).</span></span> <span data-ttu-id="11ad2-250">检查以下子项：</span><span class="sxs-lookup"><span data-stu-id="11ad2-250">Check these subkeys:</span></span>

- <span data-ttu-id="11ad2-251">**Outlook 2016：**`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="11ad2-251">**Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span></span>

- <span data-ttu-id="11ad2-252">**Outlook 2013：**`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="11ad2-252">**Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span></span>

<span data-ttu-id="11ad2-253">查找 EnableUnsafeClientMailRules 密钥。</span><span class="sxs-lookup"><span data-stu-id="11ad2-253">Look for the key EnableUnsafeClientMailRules.</span></span> <span data-ttu-id="11ad2-254">如果该修补程序存在且设置为 1，则 Outlook 安全修补程序已被覆盖，并且计算机易受窗体/规则攻击。</span><span class="sxs-lookup"><span data-stu-id="11ad2-254">If it is there and is set to 1, the Outlook security patch has been overridden and the computer is vulnerable to the Form/Rules attack.</span></span> <span data-ttu-id="11ad2-255">如果值为 0，则禁用"启动应用程序"操作。</span><span class="sxs-lookup"><span data-stu-id="11ad2-255">If the value is 0, the "Start Application" action is disabled.</span></span> <span data-ttu-id="11ad2-256">如果已安装更新和修补版本的 Outlook，但此注册表项不存在，则系统不会易受这些攻击。</span><span class="sxs-lookup"><span data-stu-id="11ad2-256">If the updated and patched version of Outlook is installed and this registry key is not present, then a system is not vulnerable to these attacks.</span></span>

<span data-ttu-id="11ad2-257">具有本地 Exchange 安装的客户应考虑阻止没有修补程序的较旧版本的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="11ad2-257">Customers with on-premises Exchange installations should consider blocking older versions of Outlook that do not have patches available.</span></span> <span data-ttu-id="11ad2-258">有关此过程的详细信息，请参阅"配置 Outlook 客户端阻止 ["一文](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help)。</span><span class="sxs-lookup"><span data-stu-id="11ad2-258">Details on this process can be found in the article [Configure Outlook client blocking](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="11ad2-259">像网络安全专家那样保护 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="11ad2-259">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="11ad2-260">你的 Microsoft 365 订阅附带了一组强大的安全功能，可用于保护你的数据和用户。</span><span class="sxs-lookup"><span data-stu-id="11ad2-260">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="11ad2-261">使用“[Microsoft 365 安全路线图 - 前 30 天、90 天内以及之后的首要行动](security-roadmap.md)”，通过实施 Microsoft 建议的最佳做法来保护你的 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="11ad2-261">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="11ad2-262">需要在前 30 天完成的任务。</span><span class="sxs-lookup"><span data-stu-id="11ad2-262">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="11ad2-263">它们立即生效，并且对用户影响较低。</span><span class="sxs-lookup"><span data-stu-id="11ad2-263">These have immediate effect and are low-impact to your users.</span></span>

- <span data-ttu-id="11ad2-264">需要在 90 天内完成的任务。</span><span class="sxs-lookup"><span data-stu-id="11ad2-264">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="11ad2-265">这些任务需要花费更多时间来规划和实施，但会显著改善你的安全状况。</span><span class="sxs-lookup"><span data-stu-id="11ad2-265">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="11ad2-266">90 天后。</span><span class="sxs-lookup"><span data-stu-id="11ad2-266">Beyond 90 days.</span></span> <span data-ttu-id="11ad2-267">这些增强功能基于前 90 天的工作构建。</span><span class="sxs-lookup"><span data-stu-id="11ad2-267">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="11ad2-268">另请参阅：</span><span class="sxs-lookup"><span data-stu-id="11ad2-268">See also:</span></span>

- <span data-ttu-id="11ad2-269">[有关规则矢量](https://silentbreaksecurity.com/malicious-outlook-rules/) 的 SilentBreak 安全文章提供的恶意 Outlook 规则详细概述了 Outlook 规则。</span><span class="sxs-lookup"><span data-stu-id="11ad2-269">[Malicious Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post about Rules Vector provides a detailed review of how the Outlook Rules.</span></span>

- <span data-ttu-id="11ad2-270">[有关 Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) 的 Sensepost 博客上的 MAPI over HTTP 和 Mailrule Pwnage 讨论了一种称为 Ruler 的工具，该工具允许您通过 Outlook 规则利用邮箱。</span><span class="sxs-lookup"><span data-stu-id="11ad2-270">[MAPI over HTTP and Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) on the Sensepost blog about Mailrule Pwnage discusses a tool called Ruler that lets you exploit mailboxes through Outlook rules.</span></span>

- <span data-ttu-id="11ad2-271">[有关 Forms 威胁矢量](https://sensepost.com/blog/2017/outlook-forms-and-shells/) 的 Sensepost 博客上的 Outlook 窗体和 Shell。</span><span class="sxs-lookup"><span data-stu-id="11ad2-271">[Outlook forms and shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) on the Sensepost blog about Forms Threat Vector.</span></span>

- [<span data-ttu-id="11ad2-272">标尺代码库</span><span class="sxs-lookup"><span data-stu-id="11ad2-272">Ruler Codebase</span></span>](https://github.com/sensepost/ruler)

- [<span data-ttu-id="11ad2-273">泄露标尺指示器</span><span class="sxs-lookup"><span data-stu-id="11ad2-273">Ruler Indicators of Compromise</span></span>](https://github.com/sensepost/notruler/blob/master/iocs.md)
