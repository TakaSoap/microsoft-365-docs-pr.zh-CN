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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 了解如何识别和修正 Office 365 中的 Outlook 规则和自定义窗体注入攻击
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cbdc41315d64d341248d6900147aabc5a0b9877c
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663639"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a><span data-ttu-id="351eb-103">检测和修正 Outlook 规则和自定义窗体注入攻击</span><span class="sxs-lookup"><span data-stu-id="351eb-103">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="351eb-104">**摘要** 了解如何识别和修正 Office 365 中的 Outlook 规则和自定义窗体注入攻击。</span><span class="sxs-lookup"><span data-stu-id="351eb-104">**Summary** Learn how to recognize and remediate the Outlook rules and custom Forms injections attacks in Office 365.</span></span>

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a><span data-ttu-id="351eb-105">什么是 Outlook 规则和自定义窗体注入攻击？</span><span class="sxs-lookup"><span data-stu-id="351eb-105">What is the Outlook Rules and Custom Forms injection attack?</span></span>

<span data-ttu-id="351eb-106">在攻击者入侵租户中的帐户并进入后，将尝试建立一种留在该租户中的方法，或在发现并删除帐户后重新进入。</span><span class="sxs-lookup"><span data-stu-id="351eb-106">After an attacker has breached an account in your tenancy and gets in, they're are going to try and establish a way to stay in or a way to get back in after they are discovered and removed.</span></span> <span data-ttu-id="351eb-107">这称为建立持久性机制。</span><span class="sxs-lookup"><span data-stu-id="351eb-107">This is called establishing a persistence mechanism.</span></span> <span data-ttu-id="351eb-108">他们可通过两种方式实现此要求：利用 Outlook 规则或将自定义窗体注入 Outlook。</span><span class="sxs-lookup"><span data-stu-id="351eb-108">Two ways that they can do this are by exploiting Outlook rules or by injecting custom forms into Outlook.</span></span>
<span data-ttu-id="351eb-109">在这两种情况下，规则或表单从云服务向下同步到桌面客户端，因此客户端软件的完整格式和重新安装不会消除注入机制。</span><span class="sxs-lookup"><span data-stu-id="351eb-109">In both cases, the rule or form is synced from the cloud service down to the desktop client, so a full format and re-install of the client software doesn't eliminate the injection mechanism.</span></span> <span data-ttu-id="351eb-110">这是因为当 Outlook 客户端软件重新连接到云中的邮箱时，它将从云中重新下载规则和表单。</span><span class="sxs-lookup"><span data-stu-id="351eb-110">This is because when the Outlook client software reconnects to the mailbox in the cloud it will re-download the rules and forms from the cloud.</span></span> <span data-ttu-id="351eb-111">一旦规则和表单就位，攻击者会使用它们执行远程或自定义代码，通常在本地计算机上安装恶意软件。</span><span class="sxs-lookup"><span data-stu-id="351eb-111">Once the rules and forms are in place, the attacker uses them to execute remote or custom code, usually to install malware on the local machine.</span></span> <span data-ttu-id="351eb-112">恶意软件随后会重新窃取凭据或执行其他非法活动。</span><span class="sxs-lookup"><span data-stu-id="351eb-112">The malware then re-steals credentials or performs other illicit activity.</span></span>
<span data-ttu-id="351eb-113">此处的好消息是，如果你将客户端修补为最新版本，则你无法受到威胁的影响，因为当前的 Outlook 客户端默认会阻止这两种机制。</span><span class="sxs-lookup"><span data-stu-id="351eb-113">The good news here is that if you keep your clients patched to the latest version, you are not vulnerable to the threat as current Outlook client defaults block both mechanisms.</span></span>

<span data-ttu-id="351eb-114">攻击通常遵循以下模式：</span><span class="sxs-lookup"><span data-stu-id="351eb-114">The attacks typically follow these patterns:</span></span>

<span data-ttu-id="351eb-115">**规则攻击**：</span><span class="sxs-lookup"><span data-stu-id="351eb-115">**The Rules Exploit**:</span></span>

1. <span data-ttu-id="351eb-116">攻击者窃取你的一个用户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="351eb-116">The attacker steals the username and password of one of your users.</span></span>

2. <span data-ttu-id="351eb-117">攻击者随后登录用户 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="351eb-117">The attacker then signs in to that users Exchange mailbox.</span></span> <span data-ttu-id="351eb-118">邮箱可以位于 Exchange Online 中，也可以位于 Exchange 本地。</span><span class="sxs-lookup"><span data-stu-id="351eb-118">The mailbox can either be in Exchange online or in Exchange on-premises.</span></span>

3. <span data-ttu-id="351eb-119">然后，攻击者在邮箱中创建一个转发规则，该规则在邮箱收到符合规则条件的电子邮件时触发。</span><span class="sxs-lookup"><span data-stu-id="351eb-119">The attacker then creates a forwarding rule in the mailbox that is triggered when the mailbox receives an email that matches the criteria of the rule.</span></span> <span data-ttu-id="351eb-120">规则的条件和触发电子邮件的内容是相互定制。</span><span class="sxs-lookup"><span data-stu-id="351eb-120">The criteria of rule and the contents of the trigger email are tailor-made for each other.</span></span>

4. <span data-ttu-id="351eb-121">攻击者向正常使用其邮箱的用户发送触发电子邮件。</span><span class="sxs-lookup"><span data-stu-id="351eb-121">The attacker sends the trigger email to the user who is using their mailbox normally.</span></span>

5. <span data-ttu-id="351eb-122">收到电子邮件时，将触发规则。</span><span class="sxs-lookup"><span data-stu-id="351eb-122">When the email is received, the rule is triggered.</span></span> <span data-ttu-id="351eb-123">该规则的操作通常是在远程 WebDAV (启动) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="351eb-123">The action of the rule is usually to launch an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="351eb-124">应用程序通常会在用户计算机上本地安装恶意软件，如 [Powershell 管理](https://www.powershellempire.com/)程序。</span><span class="sxs-lookup"><span data-stu-id="351eb-124">The application typically installs malware, such as [Powershell Empire](https://www.powershellempire.com/), locally on the user's machine.</span></span>

7. <span data-ttu-id="351eb-125">恶意软件允许攻击者从本地计算机重新窃取用户的用户名和密码或其他凭据，并执行其他恶意活动。</span><span class="sxs-lookup"><span data-stu-id="351eb-125">The malware allows the attacker to re-steal the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

<span data-ttu-id="351eb-126">**表单攻击**：</span><span class="sxs-lookup"><span data-stu-id="351eb-126">**The Forms Exploit**:</span></span>

1. <span data-ttu-id="351eb-127">攻击者窃取你的一个用户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="351eb-127">The attacker steals the username and password of one of your users.</span></span>

2. <span data-ttu-id="351eb-128">攻击者随后登录到该用户的 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="351eb-128">The attacker then sign in to that users Exchange mailbox.</span></span> <span data-ttu-id="351eb-129">邮箱可以位于 Exchange Online 中，也可以位于 Exchange 本地。</span><span class="sxs-lookup"><span data-stu-id="351eb-129">The mailbox can either be in Exchange online or in Exchange on-premises.</span></span>

3. <span data-ttu-id="351eb-130">攻击者随后创建自定义邮件表单模板并将其插入到用户邮箱中。</span><span class="sxs-lookup"><span data-stu-id="351eb-130">The attacker then creates a custom mail form template and inserts it into the user's mailbox.</span></span> <span data-ttu-id="351eb-131">当邮箱收到要求邮箱加载自定义窗体的电子邮件时，将触发自定义窗体。</span><span class="sxs-lookup"><span data-stu-id="351eb-131">The custom form is triggered when the mailbox receives an email that requires the mailbox to load the custom form.</span></span> <span data-ttu-id="351eb-132">自定义窗体和电子邮件的格式是互为定制的。</span><span class="sxs-lookup"><span data-stu-id="351eb-132">The custom form and the format of email are tailor-made for each other.</span></span>
4. <span data-ttu-id="351eb-133">攻击者向正常使用其邮箱的用户发送触发电子邮件。</span><span class="sxs-lookup"><span data-stu-id="351eb-133">The attacker sends the trigger email to the user, who is using their mailbox normally.</span></span>

5. <span data-ttu-id="351eb-134">收到电子邮件时，将加载表单。</span><span class="sxs-lookup"><span data-stu-id="351eb-134">When the email is received, the form is loaded.</span></span> <span data-ttu-id="351eb-135">表单将在远程 WebDAV (启动) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="351eb-135">The form launches an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="351eb-136">应用程序通常会在用户计算机上本地安装恶意软件，如 [Powershell 管理](https://www.powershellempire.com/)程序。</span><span class="sxs-lookup"><span data-stu-id="351eb-136">The application typically installs malware, such as [Powershell Empire](https://www.powershellempire.com/), locally on the user's machine.</span></span>

7. <span data-ttu-id="351eb-137">恶意软件允许攻击者从本地计算机重新窃取用户的用户名和密码或其他凭据，并执行其他恶意活动。</span><span class="sxs-lookup"><span data-stu-id="351eb-137">The malware allows the attacker to re-steal the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a><span data-ttu-id="351eb-138">规则和自定义窗体注入攻击可能看起来像 Office 365？</span><span class="sxs-lookup"><span data-stu-id="351eb-138">What a Rules and Custom Forms Injection attack might look like Office 365?</span></span>

<span data-ttu-id="351eb-139">这些持久性机制不太可能被用户注意到，并且在某些情况下甚至对用户不可见。</span><span class="sxs-lookup"><span data-stu-id="351eb-139">These persistence mechanisms are unlikely to be noticed by your users and may in some cases even be invisible to them.</span></span> <span data-ttu-id="351eb-140">本文将告诉你如何查找下面列出的七 (泄露指示器) 中的任一。</span><span class="sxs-lookup"><span data-stu-id="351eb-140">This article tells you how to look for any of the seven signs (Indicators of Compromise) listed below.</span></span> <span data-ttu-id="351eb-141">如果找到其中任何一个，则需要采取修正步骤。</span><span class="sxs-lookup"><span data-stu-id="351eb-141">If you find any of these, you need to take remediation steps.</span></span>

- <span data-ttu-id="351eb-142">规则泄露指示器：</span><span class="sxs-lookup"><span data-stu-id="351eb-142">Indicators of the Rules compromise:</span></span>

  - <span data-ttu-id="351eb-143">规则操作是启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="351eb-143">Rule Action is to start an application.</span></span>

  - <span data-ttu-id="351eb-144">规则引用 EXE、ZIP 或 URL。</span><span class="sxs-lookup"><span data-stu-id="351eb-144">Rule References an EXE, ZIP, or URL.</span></span>

  - <span data-ttu-id="351eb-145">在本地计算机上，查找源自 Outlook PID 的新进程启动。</span><span class="sxs-lookup"><span data-stu-id="351eb-145">On the local machine, look for new process starts that originate from the Outlook PID.</span></span>

- <span data-ttu-id="351eb-146">自定义表单泄露指示器：</span><span class="sxs-lookup"><span data-stu-id="351eb-146">Indicators of the Custom forms compromise:</span></span>

  - <span data-ttu-id="351eb-147">呈现的自定义窗体保存为其自己的邮件类。</span><span class="sxs-lookup"><span data-stu-id="351eb-147">Custom form present saved as their own message class.</span></span>

  - <span data-ttu-id="351eb-148">邮件类包含可执行代码。</span><span class="sxs-lookup"><span data-stu-id="351eb-148">Message class contains executable code.</span></span>

  - <span data-ttu-id="351eb-149">通常存储在个人窗体库或收件箱文件夹中。</span><span class="sxs-lookup"><span data-stu-id="351eb-149">Usually stored in Personal Forms Library or Inbox folders.</span></span>

  - <span data-ttu-id="351eb-150">表单名为 IPM。注意。[自定义名称]。</span><span class="sxs-lookup"><span data-stu-id="351eb-150">Form is named IPM.Note.[custom name].</span></span>

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a><span data-ttu-id="351eb-151">查找此攻击的迹象并确认它的步骤</span><span class="sxs-lookup"><span data-stu-id="351eb-151">Steps for finding signs of this attack and confirming it</span></span>

<span data-ttu-id="351eb-152">可以使用以下两种方法之一确认攻击：</span><span class="sxs-lookup"><span data-stu-id="351eb-152">You can use either of these two methods to confirm the attack:</span></span>

- <span data-ttu-id="351eb-153">使用 Outlook 客户端手动检查每个邮箱的规则和表单。</span><span class="sxs-lookup"><span data-stu-id="351eb-153">Manually examine the rules and forms for each mailbox using the Outlook client.</span></span> <span data-ttu-id="351eb-154">此方法非常彻底，但是，如果您有许多用户要检查，则只能在非常耗时的时间检查邮箱用户。</span><span class="sxs-lookup"><span data-stu-id="351eb-154">This method is thorough, but you can only check mailbox user at a time which can be very time consuming if you have many users to check.</span></span> <span data-ttu-id="351eb-155">它还可能导致运行检查的计算机泄露。</span><span class="sxs-lookup"><span data-stu-id="351eb-155">It can also result in a breach of the computer that you are running the check from.</span></span>

- <span data-ttu-id="351eb-156">使用 [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 脚本自动转储租赁中所有用户的所有邮件转发规则和自定义表单。</span><span class="sxs-lookup"><span data-stu-id="351eb-156">Use the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script to automatically dump all the mail forwarding rules and custom forms for all the users in your tenancy.</span></span> <span data-ttu-id="351eb-157">这是开销最少的最快速、最安全的方法。</span><span class="sxs-lookup"><span data-stu-id="351eb-157">This is the fastest and safest method with the least amount of overhead.</span></span>

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a><span data-ttu-id="351eb-158">使用 Outlook 客户端确认规则攻击</span><span class="sxs-lookup"><span data-stu-id="351eb-158">Confirm the Rules Attack Using the Outlook client</span></span>

1. <span data-ttu-id="351eb-159">以用户状态打开用户 Outlook 客户端。</span><span class="sxs-lookup"><span data-stu-id="351eb-159">Open the users Outlook client as the user.</span></span> <span data-ttu-id="351eb-160">用户可能需要你的帮助来检查其邮箱上的规则。</span><span class="sxs-lookup"><span data-stu-id="351eb-160">The user may need your help in examining the rules on their mailbox.</span></span>

2. <span data-ttu-id="351eb-161">有关在 Outlook [中打开](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) 规则界面的过程，请参阅"使用规则文章管理电子邮件"。</span><span class="sxs-lookup"><span data-stu-id="351eb-161">Refer to [Manage email messages by using rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) article for the procedures on how to open the rules interface in Outlook.</span></span>

3. <span data-ttu-id="351eb-162">查找用户未创建的规则，或任何具有可疑名称的意外规则或规则。</span><span class="sxs-lookup"><span data-stu-id="351eb-162">Look for rules that the user did not create, or any unexpected rules or rules with suspicious names.</span></span>

4. <span data-ttu-id="351eb-163">在规则说明中查找启动和应用程序的规则操作或引用一个 。EXE。ZIP 文件或启动 URL。</span><span class="sxs-lookup"><span data-stu-id="351eb-163">Look in the rule description for rule actions that start and application or refer to an .EXE, .ZIP file or to launching a URL.</span></span>

5. <span data-ttu-id="351eb-164">查找开始使用 Outlook 进程 ID 的任何新进程。</span><span class="sxs-lookup"><span data-stu-id="351eb-164">Look for any new processes that start using the Outlook process ID.</span></span> <span data-ttu-id="351eb-165">请参阅["查找进程 ID"。](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)</span><span class="sxs-lookup"><span data-stu-id="351eb-165">Refer to [Find the Process ID](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id).</span></span>

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a><span data-ttu-id="351eb-166">使用 Outlook 客户端确认表单攻击的步骤</span><span class="sxs-lookup"><span data-stu-id="351eb-166">Steps to confirm the Forms attack using the Outlook client</span></span>

1. <span data-ttu-id="351eb-167">以用户状态打开用户 Outlook 客户端。</span><span class="sxs-lookup"><span data-stu-id="351eb-167">Open the user Outlook client as the user.</span></span>

2. <span data-ttu-id="351eb-168">按照用户版本的 Outlook [的"](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) 显示开发人员"选项卡中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="351eb-168">Follow the steps in, [Show the Developer tab](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) for the users version of Outlook.</span></span>

3. <span data-ttu-id="351eb-169">在 Outlook 中打开现在可见的开发人员选项卡，然后单击 **设计窗体**。</span><span class="sxs-lookup"><span data-stu-id="351eb-169">Open the now visible developer tab in Outlook and click **design a form**.</span></span>

4. <span data-ttu-id="351eb-170">从 **"查找** 中" **列表中选择收件箱** 。</span><span class="sxs-lookup"><span data-stu-id="351eb-170">Select the **Inbox** from the **Look In** list.</span></span> <span data-ttu-id="351eb-171">查找任何自定义窗体。</span><span class="sxs-lookup"><span data-stu-id="351eb-171">Look for any custom forms.</span></span> <span data-ttu-id="351eb-172">自定义窗体非常少见，因此，如果有任何自定义窗体，则值得更深入地查看。</span><span class="sxs-lookup"><span data-stu-id="351eb-172">Custom forms are rare enough that if you have any custom forms at all, it is worth a deeper look.</span></span>

5. <span data-ttu-id="351eb-173">调查任何自定义表单，尤其是标记为隐藏的自定义表单。</span><span class="sxs-lookup"><span data-stu-id="351eb-173">Investigate any custom forms, especially those marked as hidden.</span></span>

6. <span data-ttu-id="351eb-174">打开任何自定义窗体，在 **"** 窗体"组中单击 **"查看代码** "以查看在加载窗体时运行哪些窗体。</span><span class="sxs-lookup"><span data-stu-id="351eb-174">Open any custom forms and in the **Form** group click **View Code** to see what runs when the form is loaded.</span></span>

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a><span data-ttu-id="351eb-175">使用 PowerShell 确认规则和表单攻击的步骤</span><span class="sxs-lookup"><span data-stu-id="351eb-175">Steps to confirm the Rules and Forms attack using PowerShell</span></span>

<span data-ttu-id="351eb-176">验证规则或自定义表单攻击的最简单方法就是运行 [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="351eb-176">The simplest way to verify a rules or custom forms attack is to run the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script.</span></span> <span data-ttu-id="351eb-177">此脚本连接到租户中的每个邮箱，将所有规则和表单转储为两个 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="351eb-177">This script connects to every mailbox in your tenant and dumps all the rules and forms into two .csv files.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="351eb-178">先决条件</span><span class="sxs-lookup"><span data-stu-id="351eb-178">Pre-requisites</span></span>

<span data-ttu-id="351eb-179">您需要具有全局管理员权限才能运行脚本，因为脚本连接到租赁中的每个邮箱以读取规则和表单。</span><span class="sxs-lookup"><span data-stu-id="351eb-179">You will need to have a global administrator rights to run the script because the script connects to every mailbox in the tenancy to read the rules and forms.</span></span>

1. <span data-ttu-id="351eb-180">使用本地管理员权限登录到您将从中运行脚本的机器。</span><span class="sxs-lookup"><span data-stu-id="351eb-180">Sign in to the machine that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="351eb-181">将脚本从 GitHub Get-AllTenantRulesAndForms.ps1或复制到运行脚本的文件夹。</span><span class="sxs-lookup"><span data-stu-id="351eb-181">Download or copy the Get-AllTenantRulesAndForms.ps1 script from GitHub to a folder from which you will run it.</span></span> <span data-ttu-id="351eb-182">脚本将为此文件夹创建两个日期标记文件，MailboxFormsExport-yyyy-mm-dd.csv和MailboxRulesExport-yyyy-mm-dd.csv。</span><span class="sxs-lookup"><span data-stu-id="351eb-182">The script will create two date stamped files to this folder, MailboxFormsExport-yyyy-mm-dd.csv, and MailboxRulesExport-yyyy-mm-dd.csv.</span></span>

3. <span data-ttu-id="351eb-183">以管理员角色打开 PowerShell 实例，然后打开将脚本保存到的文件夹。</span><span class="sxs-lookup"><span data-stu-id="351eb-183">Open a PowerShell instance as an administrator and open the folder you saved the script to.</span></span>

4. <span data-ttu-id="351eb-184">运行此 PowerShell 命令行， `.\Get-AllTenantRulesAndForms.ps1` 如下所示.\Get-AllTenantRulesAndForms.ps1</span><span class="sxs-lookup"><span data-stu-id="351eb-184">Run this PowerShell command line as follows `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1</span></span>

#### <a name="interpreting-the-output"></a><span data-ttu-id="351eb-185">解释输出</span><span class="sxs-lookup"><span data-stu-id="351eb-185">Interpreting the output</span></span>

- <span data-ttu-id="351eb-186">**MailboxRulesExport-*yyyy-mm-dd*.csv：** 检查每 (一个规则) 检查包含应用程序或可执行文件的操作条件：</span><span class="sxs-lookup"><span data-stu-id="351eb-186">**MailboxRulesExport-*yyyy-mm-dd*.csv**: Examine the rules (one per row) for action conditions that include applications or executables:</span></span>

  - <span data-ttu-id="351eb-187">**ActionType (A 列) ：** 如果看到值"ID_ACTION_CUSTOM"，则规则可能是恶意规则。</span><span class="sxs-lookup"><span data-stu-id="351eb-187">**ActionType (column A)**: If you see the value "ID_ACTION_CUSTOM", the rule is likely malicious.</span></span>

  - <span data-ttu-id="351eb-188">**IsPotentiallyMalicious (D)**： 如果此值为"TRUE"，则规则可能是恶意的。</span><span class="sxs-lookup"><span data-stu-id="351eb-188">**IsPotentiallyMalicious (column D)**: If this value is "TRUE", the rule is likely malicious.</span></span>

  - <span data-ttu-id="351eb-189">**ActionCommand** (列 G) ： 如果其中列出了具有 .exe、.zip 扩展名或引用 URL 的条目（不应存在）的应用程序或任何文件，则规则可能是恶意的。</span><span class="sxs-lookup"><span data-stu-id="351eb-189">**ActionCommand (column G)**: If this lists an application or any file with a .exe, .zip extension or an entry that refers to a URL, that is not supposed to be there, the rule is likely malicious.</span></span>

- <span data-ttu-id="351eb-190">**MailboxFormsExport-*yyyy-mm-dd*.csv：** 通常，使用自定义窗体非常少见。</span><span class="sxs-lookup"><span data-stu-id="351eb-190">**MailboxFormsExport-*yyyy-mm-dd*.csv**: In general, the use of custom forms is very rare.</span></span> <span data-ttu-id="351eb-191">如果在此工作簿中发现任何内容，请打开该用户的邮箱并检查表单本身。</span><span class="sxs-lookup"><span data-stu-id="351eb-191">If you find any in this workbook, you open that user's mailbox and examine the form itself.</span></span> <span data-ttu-id="351eb-192">如果您的组织没有有意地将文件放在该站点中，则可能是恶意的。</span><span class="sxs-lookup"><span data-stu-id="351eb-192">If your organization did not put it there intentionally, it is likely malicious.</span></span>

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a><span data-ttu-id="351eb-193">如何停止和修正 Outlook 规则和窗体攻击</span><span class="sxs-lookup"><span data-stu-id="351eb-193">How to stop and remediate the Outlook Rules and Forms attack</span></span>

<span data-ttu-id="351eb-194">如果发现这些攻击的任何证据，修正非常简单，只需从邮箱中删除规则或表单。</span><span class="sxs-lookup"><span data-stu-id="351eb-194">If you find any evidence of either of these attacks, remediation is simple, just delete the rule or form from the mailbox.</span></span> <span data-ttu-id="351eb-195">可以使用 Outlook 客户端或远程 PowerShell 来删除规则。</span><span class="sxs-lookup"><span data-stu-id="351eb-195">You can do this with the Outlook client or using remote PowerShell to remove rules.</span></span>

### <a name="using-outlook"></a><span data-ttu-id="351eb-196">使用 Outlook</span><span class="sxs-lookup"><span data-stu-id="351eb-196">Using Outlook</span></span>

1. <span data-ttu-id="351eb-197">标识用户用于 Outlook 的所有设备。</span><span class="sxs-lookup"><span data-stu-id="351eb-197">Identify all the devices that the user has used with Outlook.</span></span> <span data-ttu-id="351eb-198">它们都需要清除潜在的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="351eb-198">They will all need to be cleaned of potential malware.</span></span> <span data-ttu-id="351eb-199">在清理所有设备之前，不允许用户登录和使用电子邮件。</span><span class="sxs-lookup"><span data-stu-id="351eb-199">Do not allow the user to sign on and use email until all the devices are cleaned.</span></span>

2. <span data-ttu-id="351eb-200">按照" [删除每个设备的规则](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) "中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="351eb-200">Follow the steps in [Delete a rule](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) for each device.</span></span>

3. <span data-ttu-id="351eb-201">如果你不确定存在其他恶意软件，可以在设备上格式化和重新安装所有软件。</span><span class="sxs-lookup"><span data-stu-id="351eb-201">If you are unsure about the presence of other malware, you can format and re-install all the software on the device.</span></span> <span data-ttu-id="351eb-202">对于移动设备，你可以按照制造商步骤将设备重置为出厂映像。</span><span class="sxs-lookup"><span data-stu-id="351eb-202">For mobile devices you can follow the manufacturers steps to reset the device to the factory image.</span></span>

4. <span data-ttu-id="351eb-203">安装最新版本的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="351eb-203">Install the most up-to-date versions of Outlook.</span></span> <span data-ttu-id="351eb-204">请记住，Outlook 的当前版本默认情况下会阻止这两种类型的攻击。</span><span class="sxs-lookup"><span data-stu-id="351eb-204">Remember that the current version of Outlook blocks both types of this attack by default.</span></span>

5. <span data-ttu-id="351eb-205">删除邮箱的所有脱机副本后，请重置用户密码 (使用高质量的) ，如果尚未启用 MFA，请按照"为用户设置多重身份验证"中的步骤操作。 [](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)</span><span class="sxs-lookup"><span data-stu-id="351eb-205">Once all offline copies of the mailbox have been removed, reset the user's password (use a high-quality one) and follow the steps in [Setup multi-factor authentication for users](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) if MFA has not already been enabled.</span></span> <span data-ttu-id="351eb-206">这可确保用户凭据不会通过其他方式公开， (例如钓鱼或密码重新) 。</span><span class="sxs-lookup"><span data-stu-id="351eb-206">This ensures that the user's credentials are not exposed via other means (such as phishing or password re-use).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="351eb-207">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="351eb-207">Using PowerShell</span></span>

<span data-ttu-id="351eb-208">有两个远程 PowerShell cmdlet 可用于删除或禁用危险规则。</span><span class="sxs-lookup"><span data-stu-id="351eb-208">There are two remote PowerShell cmdlets you can use to remove or disable dangerous rules.</span></span> <span data-ttu-id="351eb-209">只需按照步骤操作。</span><span class="sxs-lookup"><span data-stu-id="351eb-209">Just follow the steps.</span></span>

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a><span data-ttu-id="351eb-210">Exchange 服务器上邮箱的步骤</span><span class="sxs-lookup"><span data-stu-id="351eb-210">Steps for mailboxes that are on an Exchange server</span></span>

1. <span data-ttu-id="351eb-211">使用远程 PowerShell 连接到 Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="351eb-211">Connect to the Exchange server using remote PowerShell.</span></span> <span data-ttu-id="351eb-212">按照使用远程 [PowerShell 连接到 Exchange 服务器中的步骤操作](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)。</span><span class="sxs-lookup"><span data-stu-id="351eb-212">Follow the steps in [Connect to Exchange servers using remote PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="351eb-213">如果要从邮箱中完全删除单个规则、多个规则或所有规则，请使用 [Remove-InboxRule](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="351eb-213">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-InboxRule](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="351eb-214">如果要保留规则及其内容以进一步调查，请使用 [Disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="351eb-214">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) cmdlet.</span></span>

#### <a name="steps-for-mailboxes-in-exchange-online"></a><span data-ttu-id="351eb-215">Exchange Online 中邮箱的步骤</span><span class="sxs-lookup"><span data-stu-id="351eb-215">Steps for mailboxes in Exchange Online</span></span>

1. <span data-ttu-id="351eb-216">按照使用 [PowerShell 连接到 Exchange Online 中的步骤操作](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="351eb-216">Follow the steps in [Connect to Exchange Online using PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="351eb-217">如果要从邮箱中完全删除单个规则、多个规则或所有规则，请使用 [Remove-Inbox 规则](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="351eb-217">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-Inbox Rule](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="351eb-218">如果要保留规则及其内容以进一步调查，请使用 [Disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="351eb-218">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) cmdlet.</span></span>

## <a name="how-to-minimize-future-attacks"></a><span data-ttu-id="351eb-219">如何最大程度地减少未来攻击</span><span class="sxs-lookup"><span data-stu-id="351eb-219">How to minimize future attacks</span></span>

### <a name="first-protect-your-accounts"></a><span data-ttu-id="351eb-220">首先：保护帐户</span><span class="sxs-lookup"><span data-stu-id="351eb-220">First: protect your accounts</span></span>

<span data-ttu-id="351eb-221">规则和表单攻击仅在攻击者窃取或入侵你的用户帐户之一后使用。</span><span class="sxs-lookup"><span data-stu-id="351eb-221">The Rules and Forms exploits are only used by an attacker after they have stolen or breached one of your user's accounts.</span></span> <span data-ttu-id="351eb-222">因此，阻止对组织使用这些攻击的第一步是主动保护用户帐户。</span><span class="sxs-lookup"><span data-stu-id="351eb-222">So, your first step to preventing the use of these exploits against your organization is to aggressively protect your user accounts.</span></span> <span data-ttu-id="351eb-223">帐户遭到入侵的一些最常见方式是通过网络钓鱼或密码 [加密攻击](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) 。</span><span class="sxs-lookup"><span data-stu-id="351eb-223">Some of the most common ways that accounts are breached are through phishing or [password spraying](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) attacks.</span></span>

<span data-ttu-id="351eb-224">保护用户帐户（尤其是管理员帐户）的最佳方法就是为用户设置多重 [身份验证](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)。</span><span class="sxs-lookup"><span data-stu-id="351eb-224">The best way to protect your user accounts, and especially your administrator accounts, is to [set up multi-factor authentication for users](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span> <span data-ttu-id="351eb-225">您还应：</span><span class="sxs-lookup"><span data-stu-id="351eb-225">You should also:</span></span>

- <span data-ttu-id="351eb-226">监视如何访问 [和使用用户帐户](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports)。</span><span class="sxs-lookup"><span data-stu-id="351eb-226">Monitor how your user accounts are [accessed and used](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports).</span></span> <span data-ttu-id="351eb-227">虽然无法阻止初始泄露，但通过提前检测，可以缩短泄露的持续时间和影响。</span><span class="sxs-lookup"><span data-stu-id="351eb-227">You may not prevent the initial breach, but you will shorten the duration and the impact of the breach by detecting it sooner.</span></span> <span data-ttu-id="351eb-228">可以使用以下 [Office 365 云应用安全策略](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) 监视帐户，并提醒异常活动：</span><span class="sxs-lookup"><span data-stu-id="351eb-228">You can use these [Office 365 Cloud App Security policies](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) to monitor you accounts and alert on unusual activity:</span></span>

  - <span data-ttu-id="351eb-229">**多次登录** 尝试失败：此策略将配置文件您的环境，当用户在一个会话中执行多个与已了解的基线有关失败登录活动时触发警报，这可能指示尝试泄露。</span><span class="sxs-lookup"><span data-stu-id="351eb-229">**Multiple failed login attempts**: This policy profiles your environment and triggers alerts when users perform multiple failed login activities in a single session with respect to the learned baseline, which could indicate an attempted breach.</span></span>

  - <span data-ttu-id="351eb-230">**不可能旅行**：此策略将配置文件您的环境，当在一个时间段内从两个位置之间的预期旅行时间短于同一用户检测到活动时，将触发警报。</span><span class="sxs-lookup"><span data-stu-id="351eb-230">**Impossible travel**: This policy profiles your environment and triggers alerts when activities are detected from the same user in different locations within a time period that is shorter than the expected travel time between the two locations.</span></span> <span data-ttu-id="351eb-231">这可能表示其他用户使用相同的凭据。</span><span class="sxs-lookup"><span data-stu-id="351eb-231">This could indicate that a different user is using the same credentials.</span></span> <span data-ttu-id="351eb-232">检测此异常行为需要 7 天的初始学习期，在此期间它将了解新用户的活动模式。</span><span class="sxs-lookup"><span data-stu-id="351eb-232">Detecting this anomalous behavior necessitates an initial learning period of seven days during which it learns a new user's activity pattern.</span></span>

  - <span data-ttu-id="351eb-233">用户 (异常模拟 **) ：** 此策略将配置文件您的环境，当用户在一个会话中执行与所了解的基线有关的多个模拟活动时，将触发警报，这可能指示已尝试泄露。</span><span class="sxs-lookup"><span data-stu-id="351eb-233">**Unusual impersonated activity (by user)**: This policy profiles your environment and triggers alerts when users perform multiple impersonated activities in a single session with respect to the baseline learned, which could indicate an attempted breach.</span></span>

- <span data-ttu-id="351eb-234">利用 Office [365 安全分数](https://securescore.office.com/) 等工具管理帐户安全配置和行为。</span><span class="sxs-lookup"><span data-stu-id="351eb-234">Leverage a tool like [Office 365 Secure Score](https://securescore.office.com/) to manage account security configurations and behaviors.</span></span>

### <a name="second-keep-your-outlook-clients-current"></a><span data-ttu-id="351eb-235">Second： Keep your Outlook clients current</span><span class="sxs-lookup"><span data-stu-id="351eb-235">Second: Keep your Outlook clients current</span></span>

<span data-ttu-id="351eb-236">Outlook 2013 和 2016 的完全更新和修补版本默认禁用"启动应用程序"规则/窗体操作。</span><span class="sxs-lookup"><span data-stu-id="351eb-236">Fully-updated and patched versions of Outlook 2013, and 2016 disable the "Start Application" rule/form action by default.</span></span> <span data-ttu-id="351eb-237">这将确保即使攻击者违反帐户，也会阻止该规则及表单操作。</span><span class="sxs-lookup"><span data-stu-id="351eb-237">This will ensure that, even if an attacker breaches the account, the rule and form actions will be blocked.</span></span> <span data-ttu-id="351eb-238">可以按照安装 Office 更新中的步骤安装最新更新 [和安全修补程序](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)。</span><span class="sxs-lookup"><span data-stu-id="351eb-238">You can install the latest updates and security patches by following the steps in [Install Office updates](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5).</span></span>

<span data-ttu-id="351eb-239">以下是 Outlook 2013 和 2016 客户端的修补程序版本：</span><span class="sxs-lookup"><span data-stu-id="351eb-239">Here are the patch versions for your Outlook 2013 and 2016 clients:</span></span>

- <span data-ttu-id="351eb-240">**Outlook** 2016：16.0.4534.1001 或更大。</span><span class="sxs-lookup"><span data-stu-id="351eb-240">**Outlook 2016**: 16.0.4534.1001 or greater.</span></span>

- <span data-ttu-id="351eb-241">**Outlook** 2013：15.0.4937.1000 或更大。</span><span class="sxs-lookup"><span data-stu-id="351eb-241">**Outlook 2013**: 15.0.4937.1000 or greater.</span></span>

<span data-ttu-id="351eb-242">有关单个安全修补程序详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="351eb-242">For more information on the individual security patches, see:</span></span>

- [<span data-ttu-id="351eb-243">Outlook 2016 安全修补程序</span><span class="sxs-lookup"><span data-stu-id="351eb-243">Outlook 2016 Security Patch</span></span>](https://support.microsoft.com/help/3191883)

- [<span data-ttu-id="351eb-244">Outlook 2013 安全修补程序</span><span class="sxs-lookup"><span data-stu-id="351eb-244">Outlook 2013 Security Patch</span></span>](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a><span data-ttu-id="351eb-245">第三：监视 Outlook 客户端</span><span class="sxs-lookup"><span data-stu-id="351eb-245">Third: Monitor your Outlook clients</span></span>

<span data-ttu-id="351eb-246">请注意，即使安装了修补程序和更新，攻击者也可以更改本地计算机配置以重新启用"启动应用程序"行为。</span><span class="sxs-lookup"><span data-stu-id="351eb-246">Note that even with the patches and updates installed, it is possible for an attacker to change the local machine configuration to re-enable the "Start Application" behavior.</span></span> <span data-ttu-id="351eb-247">可以使用高级 [组策略管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) 来监视和强制执行客户端上的本地计算机策略。</span><span class="sxs-lookup"><span data-stu-id="351eb-247">You can use [Advanced Group Policy Management](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) to monitor and enforce local machine policies on your clients.</span></span>

<span data-ttu-id="351eb-248">通过使用如何使用 [64](https://support.microsoft.com/help/305097)位版本的 Windows 查看系统注册表的信息，可以查看"启动应用程序"是否通过注册表中的替代重新启用。</span><span class="sxs-lookup"><span data-stu-id="351eb-248">You can to see if "Start Application" has been re-enabled through an override in the registry by using the information in [How to view the system registry by using 64-bit versions of Windows](https://support.microsoft.com/help/305097).</span></span> <span data-ttu-id="351eb-249">检查以下子项：</span><span class="sxs-lookup"><span data-stu-id="351eb-249">Check these subkeys:</span></span>

- <span data-ttu-id="351eb-250">**Outlook 2016：**`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="351eb-250">**Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span></span>

- <span data-ttu-id="351eb-251">**Outlook 2013：**`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="351eb-251">**Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span></span>

<span data-ttu-id="351eb-252">查找 EnableUnsafeClientMailRules 密钥。</span><span class="sxs-lookup"><span data-stu-id="351eb-252">Look for the key EnableUnsafeClientMailRules.</span></span> <span data-ttu-id="351eb-253">如果此修补程序存在且设置为 1，则 Outlook 安全修补程序已被覆盖，并且计算机易受窗体/规则攻击。</span><span class="sxs-lookup"><span data-stu-id="351eb-253">If it is there and is set to 1, the Outlook security patch has been overridden and the computer is vulnerable to the Form/Rules attack.</span></span> <span data-ttu-id="351eb-254">如果值为 0，则禁用"启动应用程序"操作。</span><span class="sxs-lookup"><span data-stu-id="351eb-254">If the value is 0, the "Start Application" action is disabled.</span></span> <span data-ttu-id="351eb-255">如果安装了更新和修补版本的 Outlook，但此注册表项不存在，则系统不会受到这些攻击的攻击。</span><span class="sxs-lookup"><span data-stu-id="351eb-255">If the updated and patched version of Outlook is installed and this registry key is not present, then a system is not vulnerable to these attacks.</span></span>

<span data-ttu-id="351eb-256">具有本地 Exchange 安装的客户应考虑阻止没有修补程序的较旧版本的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="351eb-256">Customers with on-premises Exchange installations should consider blocking older versions of Outlook that do not have patches available.</span></span> <span data-ttu-id="351eb-257">有关此过程的详细信息，请参阅文章"配置[Outlook 客户端阻止"。](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="351eb-257">Details on this process can be found in the article [Configure Outlook client blocking](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="351eb-258">像网络安全专家那样保护 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="351eb-258">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="351eb-259">你的 Microsoft 365 订阅附带了一组强大的安全功能，可用于保护你的数据和用户。</span><span class="sxs-lookup"><span data-stu-id="351eb-259">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="351eb-260">使用“[Microsoft 365 安全路线图 - 前 30 天、90 天内以及之后的首要行动](security-roadmap.md)”，通过实施 Microsoft 建议的最佳做法来保护你的 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="351eb-260">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="351eb-261">需要在前 30 天完成的任务。</span><span class="sxs-lookup"><span data-stu-id="351eb-261">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="351eb-262">这些任务会对你的用户产生直接影响并且影响很小。</span><span class="sxs-lookup"><span data-stu-id="351eb-262">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="351eb-263">需要在 90 天内完成的任务。</span><span class="sxs-lookup"><span data-stu-id="351eb-263">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="351eb-264">这些任务需要花费更多时间来规划和实施，但会显著改善你的安全状况。</span><span class="sxs-lookup"><span data-stu-id="351eb-264">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="351eb-265">90 天后。</span><span class="sxs-lookup"><span data-stu-id="351eb-265">Beyond 90 days.</span></span> <span data-ttu-id="351eb-266">这些增强功能基于前 90 天的工作构建。</span><span class="sxs-lookup"><span data-stu-id="351eb-266">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="351eb-267">另请参阅：</span><span class="sxs-lookup"><span data-stu-id="351eb-267">See also:</span></span>

- <span data-ttu-id="351eb-268">[有关规则矢量](https://silentbreaksecurity.com/malicious-outlook-rules/) 的 SilentBreak Security Post 提供的恶意 Outlook 规则提供了 Outlook 规则方式的详细说明。</span><span class="sxs-lookup"><span data-stu-id="351eb-268">[Malicious Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post about Rules Vector provides a detailed review of how the Outlook Rules.</span></span>

- <span data-ttu-id="351eb-269">[有关 Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) 的 Sensepost 博客上的 MAPI over HTTP 和 Mailrule Pwnage 讨论了一种称为 Ruler 的工具，该工具允许您通过 Outlook 规则利用邮箱。</span><span class="sxs-lookup"><span data-stu-id="351eb-269">[MAPI over HTTP and Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) on the Sensepost blog about Mailrule Pwnage discusses a tool called Ruler that lets you exploit mailboxes through Outlook rules.</span></span>

- <span data-ttu-id="351eb-270">[关于 Forms 威胁矢量](https://sensepost.com/blog/2017/outlook-forms-and-shells/) 的 Sensepost 博客上的 Outlook 窗体和 Shell。</span><span class="sxs-lookup"><span data-stu-id="351eb-270">[Outlook forms and shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) on the Sensepost blog about Forms Threat Vector.</span></span>

- [<span data-ttu-id="351eb-271">标尺代码库</span><span class="sxs-lookup"><span data-stu-id="351eb-271">Ruler Codebase</span></span>](https://github.com/sensepost/ruler)

- [<span data-ttu-id="351eb-272">泄露的标尺指示器</span><span class="sxs-lookup"><span data-stu-id="351eb-272">Ruler Indicators of Compromise</span></span>](https://github.com/sensepost/notruler/blob/master/iocs.md)
