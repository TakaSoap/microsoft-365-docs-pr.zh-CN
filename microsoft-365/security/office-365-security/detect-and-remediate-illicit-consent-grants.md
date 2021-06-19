---
title: 检测和修正非法同意授予
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: 了解如何识别和修正非法同意授权攻击Microsoft Office 365。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4c3c3c06974feb2dab3985a60938fe7d543543c3
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028915"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a><span data-ttu-id="aecea-103">检测和修正非法同意授予</span><span class="sxs-lookup"><span data-stu-id="aecea-103">Detect and Remediate Illicit Consent Grants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="aecea-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="aecea-104">**Applies to**</span></span>
- [<span data-ttu-id="aecea-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="aecea-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="aecea-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aecea-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="aecea-107">**摘要** 了解如何识别和修正非法同意授权攻击Office 365。</span><span class="sxs-lookup"><span data-stu-id="aecea-107">**Summary**  Learn how to recognize and remediate the illicit consent grants attack in Office 365.</span></span>

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a><span data-ttu-id="aecea-108">什么是非法许可授予攻击Office 365？</span><span class="sxs-lookup"><span data-stu-id="aecea-108">What is the illicit consent grant attack in Office 365?</span></span>

<span data-ttu-id="aecea-109">在非法许可授予攻击中，攻击者创建 Azure 注册的应用程序，请求访问联系人信息、电子邮件或文档等数据。</span><span class="sxs-lookup"><span data-stu-id="aecea-109">In an illicit consent grant attack, the attacker creates an Azure-registered application that requests access to data such as contact information, email, or documents.</span></span> <span data-ttu-id="aecea-110">攻击者随后会通过网络钓鱼攻击或将非法代码注入受信任的网站，来欺骗最终用户授予该应用程序访问其数据的同意。</span><span class="sxs-lookup"><span data-stu-id="aecea-110">The attacker then tricks an end user into granting that application consent to access their data either through a phishing attack, or by injecting illicit code into a trusted website.</span></span> <span data-ttu-id="aecea-111">在非法应用程序获得同意后，它无需组织帐户即可对数据进行帐户级访问。</span><span class="sxs-lookup"><span data-stu-id="aecea-111">After the illicit application has been granted consent, it has account-level access to data without the need for an organizational account.</span></span> <span data-ttu-id="aecea-112">正常修正步骤（如重置泄露帐户的密码或要求帐户使用多重身份验证 (MFA) ）无法抵御此类攻击，因为此类攻击是第三方应用程序且位于组织外部。</span><span class="sxs-lookup"><span data-stu-id="aecea-112">Normal remediation steps, like resetting passwords for breached accounts or requiring Multi-Factor Authentication (MFA) on accounts, are not effective against this type of attack, since these are third-party applications and are external to the organization.</span></span>

<span data-ttu-id="aecea-113">这些攻击利用一个交互模型，该模型认为调用信息的实体是自动化的，而不是人为的。</span><span class="sxs-lookup"><span data-stu-id="aecea-113">These attacks leverage an interaction model which presumes the entity that is calling the information is automation and not a human.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aecea-114">你是否怀疑目前遇到来自应用的非法许可问题？</span><span class="sxs-lookup"><span data-stu-id="aecea-114">Do you suspect you're experiencing problems with illicit consent-grants from an app, right now?</span></span> <span data-ttu-id="aecea-115">Microsoft Cloud App Security (MCAS) 具有用于检测、调查和修正 OAuth 应用的工具。</span><span class="sxs-lookup"><span data-stu-id="aecea-115">Microsoft Cloud App Security (MCAS) has tools to detect, investigate, and remediate your OAuth apps.</span></span> <span data-ttu-id="aecea-116">本 MCAS 文章包含一个教程，概述了如何调查 [有风险的 OAuth 应用](/cloud-app-security/investigate-risky-oauth)。</span><span class="sxs-lookup"><span data-stu-id="aecea-116">This MCAS article has a tutorial that outlines how to go about [investigating risky OAuth apps](/cloud-app-security/investigate-risky-oauth).</span></span> <span data-ttu-id="aecea-117">还可以设置 [OAuth](/cloud-app-security/app-permission-policy) 应用策略以调查应用请求的权限（用户正在授权这些应用的权限）并广泛批准或禁止这些权限请求。</span><span class="sxs-lookup"><span data-stu-id="aecea-117">You can also set [OAuth app policies](/cloud-app-security/app-permission-policy) to investigate app-requested permissions, which users are authorizing these apps, and widely approve or ban these permissions requests.</span></span>

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a><span data-ttu-id="aecea-118">非法同意授予攻击在攻击中Office 365？</span><span class="sxs-lookup"><span data-stu-id="aecea-118">What does an illicit consent grant attack look like in Office 365?</span></span>

<span data-ttu-id="aecea-119">你需要搜索安全审核日志，也称为"泄露指示器" (IOC) 攻击。</span><span class="sxs-lookup"><span data-stu-id="aecea-119">You need to search the **audit log** to find signs, also called Indicators of Compromise (IOC) of this attack.</span></span> <span data-ttu-id="aecea-120">对于具有许多 Azure 注册应用程序和大型用户群的组织，最佳做法是每周查看一次组织同意授予。</span><span class="sxs-lookup"><span data-stu-id="aecea-120">For organizations with many Azure-registered applications and a large user base, the best practice is to review your organizations consent grants on a weekly basis.</span></span>

### <a name="steps-for-finding-signs-of-this-attack"></a><span data-ttu-id="aecea-121">查找此攻击的迹象的步骤</span><span class="sxs-lookup"><span data-stu-id="aecea-121">Steps for finding signs of this attack</span></span>

1. <span data-ttu-id="aecea-122">在 **打开 Microsoft 365 Defender** <https://security.microsoft.com> 门户。</span><span class="sxs-lookup"><span data-stu-id="aecea-122">Open the **Microsoft 365 Defender** portal at <https://security.microsoft.com>.</span></span>

2. <span data-ttu-id="aecea-123">导航到 **"搜索"，** 然后选择"**审核日志搜索"。**</span><span class="sxs-lookup"><span data-stu-id="aecea-123">Navigate to **Search** and select **Audit log search**.</span></span>

3. <span data-ttu-id="aecea-124">搜索 (所有活动和所有用户) 并输入开始日期和结束日期（如果需要）然后单击"搜索 **"。**</span><span class="sxs-lookup"><span data-stu-id="aecea-124">Search (all activities and all users) and enter the start date and end date if required and then click **Search**.</span></span>

4. <span data-ttu-id="aecea-125">单击 **"筛选结果** "，在"活动"字段中输入"同意 **应用程序** "。</span><span class="sxs-lookup"><span data-stu-id="aecea-125">Click **Filter results** and enter Consent to application in the **Activity** field.</span></span>

5. <span data-ttu-id="aecea-126">单击结果以查看活动的详细信息。</span><span class="sxs-lookup"><span data-stu-id="aecea-126">Click on the result to see the details of the activity.</span></span> <span data-ttu-id="aecea-127">单击 **"详细信息** "获取活动的详细信息。</span><span class="sxs-lookup"><span data-stu-id="aecea-127">Click **More Information** to get details of the activity.</span></span> <span data-ttu-id="aecea-128">检查 IsAdminContent 是否设置为 True。</span><span class="sxs-lookup"><span data-stu-id="aecea-128">Check to see if IsAdminContent is set to True.</span></span>

> [!NOTE]
>
> <span data-ttu-id="aecea-129">在事件发生后，可能需要 30 分钟到 24 小时审核日志相应的项目条目显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="aecea-129">It can take from 30 minutes up to 24 hours for the corresponding audit log entry to be displayed in the search results after an event occurs.</span></span>
>
> <span data-ttu-id="aecea-130">审核记录在 审核日志 中保留和搜索的时间长度取决于 Microsoft 365 订阅，特别是分配给特定用户的许可证类型。</span><span class="sxs-lookup"><span data-stu-id="aecea-130">The length of time that an audit record is retained and searchable in the audit log depends on your Microsoft 365 subscription, and specifically the type of the license that is assigned to a specific user.</span></span> <span data-ttu-id="aecea-131">有关详细信息，请参阅审核 [日志](../../compliance/search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="aecea-131">For more information, see [Audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>
>
> <span data-ttu-id="aecea-132">如果此值为 true，则表明具有全局管理员访问权限的某人可能授予了对数据的广泛访问权。</span><span class="sxs-lookup"><span data-stu-id="aecea-132">If this value is true, it indicates that someone with Global Administrator access may have granted broad access to data.</span></span> <span data-ttu-id="aecea-133">如果这是意外情况，请采取措施 [确认攻击](#how-to-confirm-an-attack)。</span><span class="sxs-lookup"><span data-stu-id="aecea-133">If this is unexpected, take steps to [confirm an attack](#how-to-confirm-an-attack).</span></span>

## <a name="how-to-confirm-an-attack"></a><span data-ttu-id="aecea-134">如何确认攻击</span><span class="sxs-lookup"><span data-stu-id="aecea-134">How to confirm an attack</span></span>

<span data-ttu-id="aecea-135">如果你有上面列出的一个或多个 ICS 实例，则需要进行进一步调查，以积极确认攻击已发生。</span><span class="sxs-lookup"><span data-stu-id="aecea-135">If you have one or more instances of the IOCs listed above, you need to do further investigation to positively confirm that the attack occurred.</span></span> <span data-ttu-id="aecea-136">可以使用以下三种方法之一确认攻击：</span><span class="sxs-lookup"><span data-stu-id="aecea-136">You can use any of these three methods to confirm the attack:</span></span>

- <span data-ttu-id="aecea-137">使用管理门户清点应用程序及其Azure Active Directory权限。</span><span class="sxs-lookup"><span data-stu-id="aecea-137">Inventory applications and their permissions using the Azure Active Directory portal.</span></span> <span data-ttu-id="aecea-138">此方法很全面，但一次只能检查一个用户，如果有许多用户要检查，则检查可能非常耗时。</span><span class="sxs-lookup"><span data-stu-id="aecea-138">This method is thorough, but you can only check one user at a time which can be very time consuming if you have many users to check.</span></span>

- <span data-ttu-id="aecea-139">使用 PowerShell 清点应用程序及其权限。</span><span class="sxs-lookup"><span data-stu-id="aecea-139">Inventory applications and their permissions using PowerShell.</span></span> <span data-ttu-id="aecea-140">这是最快、最彻底的方法，开销最少。</span><span class="sxs-lookup"><span data-stu-id="aecea-140">This is the fastest and most thorough method, with the least amount of overhead.</span></span>

- <span data-ttu-id="aecea-141">让用户单独检查其应用和权限，将结果报告回管理员进行修正。</span><span class="sxs-lookup"><span data-stu-id="aecea-141">Have your users individually check their apps and permissions and report the results back to the administrators for remediation.</span></span>

## <a name="inventory-apps-with-access-in-your-organization"></a><span data-ttu-id="aecea-142">清点组织中具有访问权限的应用</span><span class="sxs-lookup"><span data-stu-id="aecea-142">Inventory apps with access in your organization</span></span>

<span data-ttu-id="aecea-143">可以使用 Azure Active Directory 门户或 PowerShell 为用户执行此操作，也可以让用户单独枚举其应用程序访问权限。</span><span class="sxs-lookup"><span data-stu-id="aecea-143">You can do this for your users with either the Azure Active Directory Portal, or PowerShell or have your users individually enumerate their application access.</span></span>

### <a name="steps-for-using-the-azure-active-directory-portal"></a><span data-ttu-id="aecea-144">使用 Azure Active Directory 门户的步骤</span><span class="sxs-lookup"><span data-stu-id="aecea-144">Steps for using the Azure Active Directory Portal</span></span>

<span data-ttu-id="aecea-145">您可以通过使用管理门户 来查找任何单个用户已授予权限[Azure Active Directory应用程序](https://portal.azure.com/)。</span><span class="sxs-lookup"><span data-stu-id="aecea-145">You can look up the applications to which any individual user has granted permissions by using the [Azure Active Directory Portal](https://portal.azure.com/).</span></span>

1. <span data-ttu-id="aecea-146">使用管理权限登录到 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="aecea-146">Sign in to the Azure portal with administrative rights.</span></span>

2. <span data-ttu-id="aecea-147">选择"Azure Active Directory边栏选项卡。</span><span class="sxs-lookup"><span data-stu-id="aecea-147">Select the Azure Active Directory blade.</span></span>

3. <span data-ttu-id="aecea-148">选择 **用户**。</span><span class="sxs-lookup"><span data-stu-id="aecea-148">Select **Users**.</span></span>

4. <span data-ttu-id="aecea-149">选择要查看的用户。</span><span class="sxs-lookup"><span data-stu-id="aecea-149">Select the user that you want to review.</span></span>

5. <span data-ttu-id="aecea-150">选择 **"应用程序"。**</span><span class="sxs-lookup"><span data-stu-id="aecea-150">Select **Applications**.</span></span>

<span data-ttu-id="aecea-151">这将显示分配给用户的应用以及应用程序具有的权限。</span><span class="sxs-lookup"><span data-stu-id="aecea-151">This will show you the apps that are assigned to the user and what permissions the applications have.</span></span>

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a><span data-ttu-id="aecea-152">让用户枚举其应用程序访问权限的步骤</span><span class="sxs-lookup"><span data-stu-id="aecea-152">Steps for having your users enumerate their application access</span></span>

<span data-ttu-id="aecea-153">让用户转到 并 https://myapps.microsoft.com 查看自己的应用程序访问权限。</span><span class="sxs-lookup"><span data-stu-id="aecea-153">Have your users go to https://myapps.microsoft.com and review their own application access there.</span></span> <span data-ttu-id="aecea-154">他们应该能够查看所有具有访问权限的应用、查看有关它们的详细信息 (包括访问) 的范围，并能够撤消对可疑或非法应用的权限。</span><span class="sxs-lookup"><span data-stu-id="aecea-154">They should be able to see all the apps with access, view details about them (including the scope of access), and be able to revoke privileges to suspicious or illicit apps.</span></span>

### <a name="steps-for-doing-this-with-powershell"></a><span data-ttu-id="aecea-155">使用 PowerShell 执行此操作的步骤</span><span class="sxs-lookup"><span data-stu-id="aecea-155">Steps for doing this with PowerShell</span></span>

<span data-ttu-id="aecea-156">验证非法同意授予攻击的最简单方法就是运行 [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)，这将将租赁中所有用户的所有 OAuth 许可授权和 OAuth 应用转储到一个 .csv 文件中。</span><span class="sxs-lookup"><span data-stu-id="aecea-156">The simplest way to verify the Illicit Consent Grant attack is to run [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), which will dump all the OAuth consent grants and OAuth apps for all users in your tenancy into one .csv file.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="aecea-157">先决条件</span><span class="sxs-lookup"><span data-stu-id="aecea-157">Pre-requisites</span></span>

- <span data-ttu-id="aecea-158">安装的 Azure AD PowerShell 库。</span><span class="sxs-lookup"><span data-stu-id="aecea-158">The Azure AD PowerShell library installed.</span></span>

- <span data-ttu-id="aecea-159">将针对其运行脚本的租户的全局管理员权限。</span><span class="sxs-lookup"><span data-stu-id="aecea-159">Global administrator rights on the tenant that the script will be run against.</span></span>

- <span data-ttu-id="aecea-160">将运行脚本的计算机上的本地管理员。</span><span class="sxs-lookup"><span data-stu-id="aecea-160">Local Administrator on the computer from which will run the scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aecea-161">***强烈建议您*** 要求对管理帐户进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="aecea-161">We ***highly recommend*** that you require multi-factor authentication on your administrative account.</span></span> <span data-ttu-id="aecea-162">此脚本支持 MFA 身份验证。</span><span class="sxs-lookup"><span data-stu-id="aecea-162">This script supports MFA authentication.</span></span>

1. <span data-ttu-id="aecea-163">使用本地管理员权限登录到您将从中运行脚本的计算机。</span><span class="sxs-lookup"><span data-stu-id="aecea-163">Sign in to the computer that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="aecea-164">下载或复制[Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)脚本GitHub脚本的文件夹中运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="aecea-164">Download or copy the [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script from GitHub to a folder from which you will run the script.</span></span> <span data-ttu-id="aecea-165">这将是将输出"permissions.csv"文件写入的同一文件夹。</span><span class="sxs-lookup"><span data-stu-id="aecea-165">This will be the same folder to which the output "permissions.csv" file will be written.</span></span>

3. <span data-ttu-id="aecea-166">以管理员角色打开 PowerShell 实例，然后打开脚本保存到的文件夹。</span><span class="sxs-lookup"><span data-stu-id="aecea-166">Open a PowerShell instance as an administrator and open to the folder you saved the script to.</span></span>

4. <span data-ttu-id="aecea-167">[连接-AzureAD](/powershell/module/azuread/connect-azuread) cmdlet 连接目录。</span><span class="sxs-lookup"><span data-stu-id="aecea-167">Connect to your directory using the [Connect-AzureAD](/powershell/module/azuread/connect-azuread) cmdlet.</span></span>

5. <span data-ttu-id="aecea-168">运行此 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="aecea-168">Run this PowerShell command:</span></span>

   ```powershell
   .\Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

<span data-ttu-id="aecea-169">该脚本生成一个名为 Permissions.csv。</span><span class="sxs-lookup"><span data-stu-id="aecea-169">The script produces one file named Permissions.csv.</span></span> <span data-ttu-id="aecea-170">按照以下步骤查找非法应用程序权限授予：</span><span class="sxs-lookup"><span data-stu-id="aecea-170">Follow these steps to look for illicit application permission grants:</span></span>

1. <span data-ttu-id="aecea-171">在 ConsentType 列 (G 列) 搜索值"AllPrinciples"。</span><span class="sxs-lookup"><span data-stu-id="aecea-171">In the ConsentType column (column G) search for the value "AllPrinciples".</span></span> <span data-ttu-id="aecea-172">AllPrincipals 权限允许客户端应用程序访问租赁中每个人的内容。</span><span class="sxs-lookup"><span data-stu-id="aecea-172">The AllPrincipals permission allows the client application to access everyone's content in the tenancy.</span></span> <span data-ttu-id="aecea-173">本机Microsoft 365应用程序需要此权限才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="aecea-173">Native Microsoft 365 applications need this permission to work correctly.</span></span> <span data-ttu-id="aecea-174">应仔细查看每个具有此权限的非 Microsoft 应用程序。</span><span class="sxs-lookup"><span data-stu-id="aecea-174">Every non-Microsoft application with this permission should be reviewed carefully.</span></span>

2. <span data-ttu-id="aecea-175">在"权限 (列F) 查看每个委派应用程序对内容具有的权限。</span><span class="sxs-lookup"><span data-stu-id="aecea-175">In the Permission column (column F) review the permissions that each delegated application has to content.</span></span> <span data-ttu-id="aecea-176">查找"读取"和"写入"权限或"\*"。所有"权限，并仔细查看这些权限，因为它们可能不适合。</span><span class="sxs-lookup"><span data-stu-id="aecea-176">Look for "Read" and "Write" permission or "\*.All" permission, and review these carefully because they may not be appropriate.</span></span>

3. <span data-ttu-id="aecea-177">查看已授予同意的特定用户。</span><span class="sxs-lookup"><span data-stu-id="aecea-177">Review the specific users that have consents granted.</span></span> <span data-ttu-id="aecea-178">如果高配置文件或高影响力用户授予了不适当的同意，您应该进一步调查。</span><span class="sxs-lookup"><span data-stu-id="aecea-178">If high profile or high impact users have inappropriate consents granted, you should investigate further.</span></span>

4. <span data-ttu-id="aecea-179">在 ClientDisplayName 列 (列C#）查找看起来可疑的应用。</span><span class="sxs-lookup"><span data-stu-id="aecea-179">In the ClientDisplayName column (column C) look for apps that seem suspicious.</span></span> <span data-ttu-id="aecea-180">应仔细查看具有拼写错误的名称、超级名称或黑客攻击名称的应用。</span><span class="sxs-lookup"><span data-stu-id="aecea-180">Apps with misspelled names, super bland names, or hacker-sounding names should be reviewed carefully.</span></span>

## <a name="determine-the-scope-of-the-attack"></a><span data-ttu-id="aecea-181">确定攻击范围</span><span class="sxs-lookup"><span data-stu-id="aecea-181">Determine the scope of the attack</span></span>

<span data-ttu-id="aecea-182">完成清点应用程序访问后，请查看 **审核日志以确定泄露** 的完整范围。</span><span class="sxs-lookup"><span data-stu-id="aecea-182">After you have finished inventorying application access, review the **audit log** to determine the full scope of the breach.</span></span> <span data-ttu-id="aecea-183">搜索受影响的用户、非法应用程序有权访问您的组织的时间范围以及应用程序具有的权限。</span><span class="sxs-lookup"><span data-stu-id="aecea-183">Search on the affected users, the time frames that the illicit application had access to your organization, and the permissions the app had.</span></span> <span data-ttu-id="aecea-184">可以在 **搜索审核日志搜索**[Microsoft 365 Defender。](../../compliance/search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="aecea-184">You can search the **audit log** in the [Microsoft 365 Defender](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aecea-185">[在攻击](../../compliance/enable-mailbox-auditing.md)[之前，必须为](../../compliance/turn-audit-log-search-on-or-off.md)管理员和用户启用邮箱审核和活动审核才能获取此信息。</span><span class="sxs-lookup"><span data-stu-id="aecea-185">[Mailbox auditing](../../compliance/enable-mailbox-auditing.md) and [Activity auditing for admins and users](../../compliance/turn-audit-log-search-on-or-off.md) must have been enabled prior to the attack for you to get this information.</span></span>

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a><span data-ttu-id="aecea-186">如何停止和修正非法同意授予攻击</span><span class="sxs-lookup"><span data-stu-id="aecea-186">How to stop and remediate an illicit consent grant attack</span></span>

<span data-ttu-id="aecea-187">在标识具有非法权限的应用程序后，您具有几种删除该访问权限的方法。</span><span class="sxs-lookup"><span data-stu-id="aecea-187">After you have identified an application with illicit permissions, you have several ways to remove that access.</span></span>

- <span data-ttu-id="aecea-188">可以通过以下方法撤销应用程序在 Azure Active Directory 中的权限：</span><span class="sxs-lookup"><span data-stu-id="aecea-188">You can revoke the application's permission in the Azure Active Directory Portal by:</span></span>

  - <span data-ttu-id="aecea-189">在"用户"边栏选项卡中Azure Active Directory **受影响的** 用户。</span><span class="sxs-lookup"><span data-stu-id="aecea-189">Navigate to the affected user in the **Azure Active Directory User** blade.</span></span>

  - <span data-ttu-id="aecea-190">选择 **"应用程序"。**</span><span class="sxs-lookup"><span data-stu-id="aecea-190">Select **Applications**.</span></span>

  - <span data-ttu-id="aecea-191">选择非法应用程序。</span><span class="sxs-lookup"><span data-stu-id="aecea-191">Select the illicit application.</span></span>

  - <span data-ttu-id="aecea-192">在 **向下** 钻取中单击"删除"。</span><span class="sxs-lookup"><span data-stu-id="aecea-192">Click **Remove** in the drill down.</span></span>

- <span data-ttu-id="aecea-193">可以按照 [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)中的步骤撤销对 PowerShell 的 OAuth 许可授权。</span><span class="sxs-lookup"><span data-stu-id="aecea-193">You can revoke the OAuth consent grant with PowerShell by following the steps in [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span></span>

- <span data-ttu-id="aecea-194">你可以按照 [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)中的步骤使用 PowerShell 撤销服务应用角色分配。</span><span class="sxs-lookup"><span data-stu-id="aecea-194">You can revoke the Service App Role Assignment with PowerShell by following the steps in [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span></span>

- <span data-ttu-id="aecea-195">还可以完全禁用受影响帐户的登录，进而禁用应用访问该帐户的数据。</span><span class="sxs-lookup"><span data-stu-id="aecea-195">You can also disable sign-in for the affected account altogether, which will in turn disable app access to data in that account.</span></span> <span data-ttu-id="aecea-196">当然，这不适合于最终用户的工作效率，但如果您正在努力快速限制影响，它可以是一个可行的短期修正。</span><span class="sxs-lookup"><span data-stu-id="aecea-196">This isn't ideal for the end user's productivity, of course, but if you are working to limit impact quickly, it can be a viable short-term remediation.</span></span>

- <span data-ttu-id="aecea-197">您可以关闭租赁的集成应用程序。</span><span class="sxs-lookup"><span data-stu-id="aecea-197">You can turn integrated applications off for your tenancy.</span></span> <span data-ttu-id="aecea-198">这是一个重大步骤，禁用最终用户在租户范围内授予同意的能力。</span><span class="sxs-lookup"><span data-stu-id="aecea-198">This is a drastic step that disables the ability for end users to grant consent on a tenant-wide basis.</span></span> <span data-ttu-id="aecea-199">这可以防止用户无意中授予对恶意应用程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="aecea-199">This prevents your users from inadvertently granting access to a malicious application.</span></span> <span data-ttu-id="aecea-200">不建议这样做，因为它严重妨碍用户使用第三方应用程序提高工作效率的能力。</span><span class="sxs-lookup"><span data-stu-id="aecea-200">This isn't strongly recommended as it severely impairs your users' ability to be productive with third party applications.</span></span> <span data-ttu-id="aecea-201">为此，可以按照打开或关闭集成 [应用中的步骤操作](../../admin/misc/user-consent.md)。</span><span class="sxs-lookup"><span data-stu-id="aecea-201">You can do this by following the steps in [Turning Integrated Apps on or off](../../admin/misc/user-consent.md).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="aecea-202">像网络安全专家那样保护 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aecea-202">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="aecea-203">你的 Microsoft 365 订阅附带了一组强大的安全功能，可用于保护你的数据和用户。</span><span class="sxs-lookup"><span data-stu-id="aecea-203">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="aecea-204">使用“[Microsoft 365 安全路线图 - 前 30 天、90 天内以及之后的首要行动](security-roadmap.md)”，通过实施 Microsoft 建议的最佳做法来保护你的 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="aecea-204">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="aecea-205">需要在前 30 天完成的任务。</span><span class="sxs-lookup"><span data-stu-id="aecea-205">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="aecea-206">这些任务会对你的用户产生直接影响并且影响很小。</span><span class="sxs-lookup"><span data-stu-id="aecea-206">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="aecea-207">需要在 90 天内完成的任务。</span><span class="sxs-lookup"><span data-stu-id="aecea-207">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="aecea-208">这些任务需要花费更多时间来规划和实施，但会显著改善你的安全状况。</span><span class="sxs-lookup"><span data-stu-id="aecea-208">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="aecea-209">90 天后。</span><span class="sxs-lookup"><span data-stu-id="aecea-209">Beyond 90 days.</span></span> <span data-ttu-id="aecea-210">这些增强功能基于前 90 天的工作构建。</span><span class="sxs-lookup"><span data-stu-id="aecea-210">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="aecea-211">另请参阅：</span><span class="sxs-lookup"><span data-stu-id="aecea-211">See also:</span></span>

- <span data-ttu-id="aecea-212">["我的应用程序"列表中的"](/azure/active-directory/application-access-unexpected-application) 意外应用程序"将指导管理员完成在意识到存在具有数据访问权限的意外应用程序后可能想要执行的各种操作。</span><span class="sxs-lookup"><span data-stu-id="aecea-212">[Unexpected application in my applications list](/azure/active-directory/application-access-unexpected-application) walks administrators through various actions they may want to take after realizing there are unexpected applications with access to data.</span></span>

- <span data-ttu-id="aecea-213">[将应用程序Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent)应用程序是同意和权限的简要概述。</span><span class="sxs-lookup"><span data-stu-id="aecea-213">[Integrating applications with Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) is a high-level overview of consent and permissions.</span></span>

- <span data-ttu-id="aecea-214">[开发我的应用程序时](/azure/active-directory/active-directory-application-dev-development-content-map) 遇到问题提供了指向各种许可相关文章的链接。</span><span class="sxs-lookup"><span data-stu-id="aecea-214">[Problems developing my application](/azure/active-directory/active-directory-application-dev-development-content-map) provides links to various consent related articles.</span></span>

- <span data-ttu-id="aecea-215">[Azure AD Azure Active Directory (](/azure/active-directory/develop/active-directory-application-objects)中的应用程序和服务主体) 概述了应用程序模型的核心应用程序和服务主体对象。</span><span class="sxs-lookup"><span data-stu-id="aecea-215">[Application and service principal objects in Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span></span>

- <span data-ttu-id="aecea-216">[管理对应用](/azure/active-directory/active-directory-managing-access-to-apps) 的访问权限是管理员管理用户对应用的访问权限所必须的功能概述。</span><span class="sxs-lookup"><span data-stu-id="aecea-216">[Manage access to apps](/azure/active-directory/active-directory-managing-access-to-apps) is an overview of the capabilities that administrators have to manage user access to apps.</span></span>
