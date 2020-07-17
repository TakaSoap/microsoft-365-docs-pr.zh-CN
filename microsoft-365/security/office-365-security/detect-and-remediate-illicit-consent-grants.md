---
title: 检测并修正违法许可授予
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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 了解如何识别和修正 Microsoft Office 365 中的非法许可授予攻击。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a324c4427046480fe81f58fc810f020c87247032
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726803"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a><span data-ttu-id="c3d7c-103">检测并修正违法许可授予</span><span class="sxs-lookup"><span data-stu-id="c3d7c-103">Detect and Remediate Illicit Consent Grants</span></span>

<span data-ttu-id="c3d7c-104">**摘要** 了解如何识别和修正在 Office 365 中的非法许可授予攻击。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-104">**Summary**  Learn how to recognize and remediate the illicit consent grants attack in Office 365.</span></span>

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a><span data-ttu-id="c3d7c-105">什么是 Office 365 中的非法同意授权攻击？</span><span class="sxs-lookup"><span data-stu-id="c3d7c-105">What is the illicit consent grant attack in Office 365?</span></span>

<span data-ttu-id="c3d7c-106">在违法许可授予攻击中，攻击者将创建一个 Azure 注册的应用程序，该应用程序请求对联系人信息、电子邮件或文档等数据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-106">In an illicit consent grant attack, the attacker creates an Azure-registered application that requests access to data such as contact information, email, or documents.</span></span> <span data-ttu-id="c3d7c-107">然后，攻击者向最终用户授予权限，允许该应用程序通过网络钓鱼攻击或将非法代码注入到受信任的网站来访问其数据。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-107">The attacker then tricks an end user into granting that application consent to access their data either through a phishing attack, or by injecting illicit code into a trusted website.</span></span> <span data-ttu-id="c3d7c-108">在违法应用程序被授予同意后，它将具有对数据的帐户级别访问权限，而无需组织帐户。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-108">After the illicit application has been granted consent, it has account-level access to data without the need for an organizational account.</span></span> <span data-ttu-id="c3d7c-109">常规修正步骤（如重置已违例帐户的密码或要求对帐户进行多重身份验证（MFA））不会对此类型的攻击有效，因为它们是第三方应用程序，并且是组织外部的。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-109">Normal remediation steps, like resetting passwords for breached accounts or requiring Multi-Factor Authentication (MFA) on accounts, are not effective against this type of attack, since these are third-party applications and are external to the organization.</span></span>

<span data-ttu-id="c3d7c-110">这些攻击利用交互模型，该模型假定调用信息的实体是自动化的，而不是人工。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-110">These attacks leverage an interaction model which presumes the entity that is calling the information is automation and not a human.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3d7c-111">您是否怀疑在违法许可的情况下遇到问题-从应用程序中立即授予权限？</span><span class="sxs-lookup"><span data-stu-id="c3d7c-111">Do you suspect you're experiencing problems with illicit consent-grants from an app, right now?</span></span> <span data-ttu-id="c3d7c-112">Microsoft 云应用安全性（MCAS）具有用于检测、调查和修正 OAuth 应用程序的工具。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-112">Microsoft Cloud App Security (MCAS) has tools to detect, investigate, and remediate your OAuth apps.</span></span> <span data-ttu-id="c3d7c-113">本 MCAS 文章中有一个教程，概述了如何[调查有风险的 OAuth 应用程序](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth)。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-113">This MCAS article has a tutorial that outlines how to go about [investigating risky OAuth apps](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth).</span></span> <span data-ttu-id="c3d7c-114">您还可以设置[OAuth 应用策略](https://docs.microsoft.com/cloud-app-security/app-permission-policy)以调查应用程序请求的权限，这些权限是用户授权这些应用程序，并广泛批准或禁止这些权限请求。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-114">You can also set [OAuth app policies](https://docs.microsoft.com/cloud-app-security/app-permission-policy) to investigate app-requested permissions, which users are authorizing these apps, and widely approve or ban these permissions requests.</span></span>

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a><span data-ttu-id="c3d7c-115">非法同意在 Office 365 中授予攻击外观？</span><span class="sxs-lookup"><span data-stu-id="c3d7c-115">What does an illicit consent grant attack look like in Office 365?</span></span>

<span data-ttu-id="c3d7c-116">您需要搜索**审核日志**，以查找该攻击的标志（也称为 "泄露" （IOC）标记）。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-116">You need to search the **audit log** to find signs, also called Indicators of Compromise (IOC) of this attack.</span></span> <span data-ttu-id="c3d7c-117">对于具有许多 Azure 注册应用程序和大型用户群的组织，最佳做法是在每周的基础上查看您的组织同意授予。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-117">For organizations with many Azure-registered applications and a large user base, the best practice is to review your organizations consent grants on a weekly basis.</span></span>

### <a name="steps-for-finding-signs-of-this-attack"></a><span data-ttu-id="c3d7c-118">查找此攻击的迹象的步骤</span><span class="sxs-lookup"><span data-stu-id="c3d7c-118">Steps for finding signs of this attack</span></span>

1. <span data-ttu-id="c3d7c-119">在上打开**安全 & 合规性中心** <https://protection.office.com> 。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-119">Open the **Security & Compliance Center** at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="c3d7c-120">导航到 "**搜索**"，然后选择 "**审核日志搜索**"。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-120">Navigate to **Search** and select **Audit log search**.</span></span>

3. <span data-ttu-id="c3d7c-121">搜索（所有活动和所有用户）并输入开始日期和结束日期（如果需要），然后单击 "**搜索**"。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-121">Search (all activities and all users) and enter the start date and end date if required and then click **Search**.</span></span>

4. <span data-ttu-id="c3d7c-122">单击 "**筛选结果**" 并在 "**活动**" 字段中输入应用同意。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-122">Click **Filter results** and enter Consent to application in the **Activity** field.</span></span>

5. <span data-ttu-id="c3d7c-123">单击结果以查看活动的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-123">Click on the result to see the details of the activity.</span></span> <span data-ttu-id="c3d7c-124">若要获取活动的详细信息，请单击 "**详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-124">Click **More Information** to get details of the activity.</span></span> <span data-ttu-id="c3d7c-125">查看 "IsAdminContent" 是否设置为 True。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-125">Check to see if IsAdminContent is set to True.</span></span>

> [!NOTE]
> 
> <span data-ttu-id="c3d7c-126">在事件发生后，在搜索结果中显示相应的审核日志条目可能需要30分钟到24小时的时间。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-126">It can take from 30 minutes up to 24 hours for the corresponding audit log entry to be displayed in the search results after an event occurs.</span></span>
> 
> <span data-ttu-id="c3d7c-127">审核记录的保留和可在审核日志中搜索的时间长度取决于您的 Microsoft 365 订阅，以及分配给特定用户的许可证类型。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-127">The length of time that an audit record is retained and searchable in the audit log depends on your Microsoft 365 subscription, and specifically the type of the license that is assigned to a specific user.</span></span> <span data-ttu-id="c3d7c-128">有关详细信息，请参阅[审核日志](../../compliance/search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-128">For more information, see [Audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>
> 
> <span data-ttu-id="c3d7c-129">如果此值为 true，则表示具有全局管理员访问权限的人员可能已授予对数据的广泛访问权限。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-129">If this value is true, it indicates that someone with Global Administrator access may have granted broad access to data.</span></span> <span data-ttu-id="c3d7c-130">如果这是意外情况，请执行相应的步骤来[确认攻击](#how-to-confirm-an-attack)。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-130">If this is unexpected, take steps to [confirm an attack](#how-to-confirm-an-attack).</span></span>

## <a name="how-to-confirm-an-attack"></a><span data-ttu-id="c3d7c-131">如何确认攻击</span><span class="sxs-lookup"><span data-stu-id="c3d7c-131">How to confirm an attack</span></span>

<span data-ttu-id="c3d7c-132">如果您有上面列出的 IOCs 的一个或多个实例，则需要进行进一步调查以确认攻击是否发生。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-132">If you have one or more instances of the IOCs listed above, you need to do further investigation to positively confirm that the attack occurred.</span></span> <span data-ttu-id="c3d7c-133">您可以使用以下三种方法中的任何一种来确认攻击：</span><span class="sxs-lookup"><span data-stu-id="c3d7c-133">You can use any of these three methods to confirm the attack:</span></span>

- <span data-ttu-id="c3d7c-134">使用 Azure Active Directory 门户列出应用程序及其权限。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-134">Inventory applications and their permissions using the Azure Active Directory portal.</span></span> <span data-ttu-id="c3d7c-135">这种方法是彻底的，但是，如果您有多个用户要检查，则一次只能检查一个用户，这可能会非常耗时。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-135">This method is thorough, but you can only check one user at a time which can be very time consuming if you have many users to check.</span></span>

- <span data-ttu-id="c3d7c-136">使用 PowerShell 清点应用程序及其权限。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-136">Inventory applications and their permissions using PowerShell.</span></span> <span data-ttu-id="c3d7c-137">这是最快且最彻底的方法，最少的开销。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-137">This is the fastest and most thorough method, with the least amount of overhead.</span></span>

- <span data-ttu-id="c3d7c-138">让您的用户单独检查其应用和权限，并将结果报告给管理员进行修正。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-138">Have your users individually check their apps and permissions and report the results back to the administrators for remediation.</span></span>

## <a name="inventory-apps-with-access-in-your-organization"></a><span data-ttu-id="c3d7c-139">在您的组织中列出具有访问权限的应用程序</span><span class="sxs-lookup"><span data-stu-id="c3d7c-139">Inventory apps with access in your organization</span></span>

<span data-ttu-id="c3d7c-140">您可以为使用 Azure Active Directory 门户或 PowerShell 的用户执行此操作，也可以让用户单独枚举其应用程序访问。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-140">You can do this for your users with either the Azure Active Directory Portal, or PowerShell or have your users individually enumerate their application access.</span></span>

### <a name="steps-for-using-the-azure-active-directory-portal"></a><span data-ttu-id="c3d7c-141">使用 Azure Active Directory 门户的步骤</span><span class="sxs-lookup"><span data-stu-id="c3d7c-141">Steps for using the Azure Active Directory Portal</span></span>

<span data-ttu-id="c3d7c-142">您可以通过使用[Azure Active Directory 门户](https://portal.azure.com/)来查找任何单个用户已向其授予权限的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-142">You can look up the applications to which any individual user has granted permissions by using the [Azure Active Directory Portal](https://portal.azure.com/).</span></span>

1. <span data-ttu-id="c3d7c-143">使用管理权限登录到 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-143">Sign in to the Azure Portal with administrative rights.</span></span>

2. <span data-ttu-id="c3d7c-144">选择 "Azure Active Directory" 边栏。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-144">Select the Azure Active Directory blade.</span></span>

3. <span data-ttu-id="c3d7c-145">选择“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-145">Select **Users**.</span></span>

4. <span data-ttu-id="c3d7c-146">选择要查看的用户。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-146">Select the user that you want to review.</span></span>

5. <span data-ttu-id="c3d7c-147">选择 "**应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-147">Select **Applications**.</span></span>

<span data-ttu-id="c3d7c-148">这将显示分配给用户的应用程序以及应用程序具有的权限。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-148">This will show you the apps that are assigned to the user and what permissions the applications have.</span></span>

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a><span data-ttu-id="c3d7c-149">让用户枚举其应用程序访问权限的步骤</span><span class="sxs-lookup"><span data-stu-id="c3d7c-149">Steps for having your users enumerate their application access</span></span>

<span data-ttu-id="c3d7c-150">让你的用户转到 https://myapps.microsoft.com 并查看其自己的应用程序访问权限。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-150">Have your users go to https://myapps.microsoft.com and review their own application access there.</span></span> <span data-ttu-id="c3d7c-151">他们应该能够查看具有访问权限的所有应用程序，查看有关这些应用程序的详细信息（包括访问范围），并能够撤销可疑或违法应用程序的权限。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-151">They should be able to see all the apps with access, view details about them (including the scope of access), and be able to revoke privileges to suspicious or illicit apps.</span></span>

### <a name="steps-for-doing-this-with-powershell"></a><span data-ttu-id="c3d7c-152">使用 PowerShell 执行此操作的步骤</span><span class="sxs-lookup"><span data-stu-id="c3d7c-152">Steps for doing this with PowerShell</span></span>

<span data-ttu-id="c3d7c-153">验证违法许可授予攻击的最简单方法是运行[Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)，这会将租赁中所有用户的所有 oauth 同意授权和 oauth 应用转储到一个 .csv 文件中。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-153">The simplest way to verify the Illicit Consent Grant attack is to run [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), which will dump all the OAuth consent grants and OAuth apps for all users in your tenancy into one .csv file.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="c3d7c-154">先决条件</span><span class="sxs-lookup"><span data-stu-id="c3d7c-154">Pre-requisites</span></span>

- <span data-ttu-id="c3d7c-155">安装了 Azure AD PowerShell 库。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-155">The Azure AD PowerShell library installed.</span></span>

- <span data-ttu-id="c3d7c-156">对将对其运行脚本的租户的全局管理员权限。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-156">Global administrator rights on the tenant that the script will be run against.</span></span>

- <span data-ttu-id="c3d7c-157">将运行脚本的计算机上的本地管理员。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-157">Local Administrator on the computer from which will run the scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3d7c-158">***强烈建议***您在管理帐户上要求进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-158">We ***highly recommend*** that you require multi-factor authentication on your administrative account.</span></span> <span data-ttu-id="c3d7c-159">此脚本支持 MFA 身份验证。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-159">This script supports MFA authentication.</span></span>

1. <span data-ttu-id="c3d7c-160">使用本地管理员权限登录到您将运行脚本的计算机。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-160">Sign in to the computer that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="c3d7c-161">将[Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)脚本从 GitHub 下载或复制到将从中运行脚本的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-161">Download or copy the [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script from GitHub to a folder from which you will run the script.</span></span> <span data-ttu-id="c3d7c-162">这将是将在其中写入输出 "permissions.csv" 文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-162">This will be the same folder to which the output "permissions.csv" file will be written.</span></span>

3. <span data-ttu-id="c3d7c-163">以管理员身份打开 PowerShell 实例，并打开将脚本保存到的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-163">Open a PowerShell instance as an administrator and open to the folder you saved the script to.</span></span>

4. <span data-ttu-id="c3d7c-164">使用[AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) cmdlet 连接到您的目录。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-164">Connect to your directory using the [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) cmdlet.</span></span>

5. <span data-ttu-id="c3d7c-165">运行此 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="c3d7c-165">Run this PowerShell command:</span></span>

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

<span data-ttu-id="c3d7c-166">该脚本将生成一个名为 Permissions.csv 的文件。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-166">The script produces one file named Permissions.csv.</span></span> <span data-ttu-id="c3d7c-167">按照以下步骤查找违法应用程序权限授予：</span><span class="sxs-lookup"><span data-stu-id="c3d7c-167">Follow these steps to look for illicit application permission grants:</span></span>

1. <span data-ttu-id="c3d7c-168">在 ConsentType 列（列 G）中搜索值 "AllPrinciples"。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-168">In the ConsentType column (column G) search for the value "AllPrinciples".</span></span> <span data-ttu-id="c3d7c-169">AllPrincipals 权限允许客户端应用程序访问租赁中的所有人的内容。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-169">The AllPrincipals permission allows the client application to access everyone's content in the tenancy.</span></span> <span data-ttu-id="c3d7c-170">本机 Microsoft 365 应用程序需要此权限才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-170">Native Microsoft 365 applications need this permission to work correctly.</span></span> <span data-ttu-id="c3d7c-171">应仔细查看具有此权限的每个非 Microsoft 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-171">Every non-Microsoft application with this permission should be reviewed carefully.</span></span>

2. <span data-ttu-id="c3d7c-172">在 "权限" 列（列 F）中，查看每个委派的应用程序对内容所拥有的权限。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-172">In the Permission column (column F) review the permissions that each delegated application has to content.</span></span> <span data-ttu-id="c3d7c-173">查找 "读取" 和 "写入" 权限或 "\*"。所有 "权限，并仔细审查这些权限，因为它们可能不合适。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-173">Look for "Read" and "Write" permission or "\*.All" permission, and review these carefully because they may not be appropriate.</span></span>

3. <span data-ttu-id="c3d7c-174">查看已授予同意的特定用户。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-174">Review the specific users that have consents granted.</span></span> <span data-ttu-id="c3d7c-175">如果高配置文件或高影响用户授予了不适当的同意，则应进一步调查。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-175">If high profile or high impact users have inappropriate consents granted, you should investigate further.</span></span>

4. <span data-ttu-id="c3d7c-176">在 "ClientDisplayName" 列（列 C）中，查找看起来可疑的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-176">In the ClientDisplayName column (column C) look for apps that seem suspicious.</span></span> <span data-ttu-id="c3d7c-177">应仔细查看具有拼写错误名称、超级 bland 名称或以黑客为名字的名称的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-177">Apps with misspelled names, super bland names, or hacker-sounding names should be reviewed carefully.</span></span>

## <a name="determine-the-scope-of-the-attack"></a><span data-ttu-id="c3d7c-178">确定攻击的范围</span><span class="sxs-lookup"><span data-stu-id="c3d7c-178">Determine the scope of the attack</span></span>

<span data-ttu-id="c3d7c-179">完成对应用程序访问的清查之后，请查看**审核日志**以确定泄露的全部范围。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-179">After you have finished inventorying application access, review the **audit log** to determine the full scope of the breach.</span></span> <span data-ttu-id="c3d7c-180">搜索受影响的用户、违法应用程序有权访问您组织的时间段以及应用程序的权限。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-180">Search on the affected users, the time frames that the illicit application had access to your organization, and the permissions the app had.</span></span> <span data-ttu-id="c3d7c-181">你可以在[Microsoft 365 安全与合规中心](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)中搜索**审核日志**。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-181">You can search the **audit log** in the [Microsoft 365 Security and Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3d7c-182">必须先启用[管理员和用户](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)的[邮箱审核](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing)和活动审核，然后才能获取此类信息。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-182">[Mailbox auditing](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) and [Activity auditing for admins and users](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) must have been enabled prior to the attack for you to get this information.</span></span>

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a><span data-ttu-id="c3d7c-183">如何停止和修正违法许可授予攻击</span><span class="sxs-lookup"><span data-stu-id="c3d7c-183">How to stop and remediate an illicit consent grant attack</span></span>

<span data-ttu-id="c3d7c-184">在识别出具有非法权限的应用程序之后，可以通过多种方式删除该访问。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-184">After you have identified an application with illicit permissions, you have several ways to remove that access.</span></span>

- <span data-ttu-id="c3d7c-185">您可以通过以下方式在 Azure Active Directory 门户中撤销应用程序的权限：</span><span class="sxs-lookup"><span data-stu-id="c3d7c-185">You can revoke the application's permission in the Azure Active Directory Portal by:</span></span>

  - <span data-ttu-id="c3d7c-186">导航到**Azure Active Directory 用户**边栏中受影响的用户。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-186">Navigate to the affected user in the **Azure Active Directory User** blade.</span></span>

  - <span data-ttu-id="c3d7c-187">选择 "**应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-187">Select **Applications**.</span></span>

  - <span data-ttu-id="c3d7c-188">选择违法应用程序。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-188">Select the illicit application.</span></span>

  - <span data-ttu-id="c3d7c-189">在深化中单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-189">Click **Remove** in the drill down.</span></span>

- <span data-ttu-id="c3d7c-190">您可以按照[AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)中的步骤撤销对 PowerShell 的 OAuth 同意授权。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-190">You can revoke the OAuth consent grant with PowerShell by following the steps in [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span></span>

- <span data-ttu-id="c3d7c-191">您可以按照[AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)中的步骤，通过 PowerShell 吊销服务应用程序角色分配。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-191">You can revoke the Service App Role Assignment with PowerShell by following the steps in [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span></span>

- <span data-ttu-id="c3d7c-192">您还可以完全禁用受影响帐户的登录，这将禁用对该帐户中的数据的应用程序访问。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-192">You can also disable sign-in for the affected account altogether, which will in turn disable app access to data in that account.</span></span> <span data-ttu-id="c3d7c-193">这并不是最终用户的工作效率的理想之处，但如果您正在努力快速限制影响，则它可能是一个可行的短期补救措施。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-193">This isn't ideal for the end user's productivity, of course, but if you are working to limit impact quickly, it can be a viable short-term remediation.</span></span>

- <span data-ttu-id="c3d7c-194">您可以为租赁启用集成的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-194">You can turn integrated applications off for your tenancy.</span></span> <span data-ttu-id="c3d7c-195">这是一项重大步骤，可禁用最终用户对租户范围授予许可的能力。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-195">This is a drastic step that disables the ability for end users to grant consent on a tenant-wide basis.</span></span> <span data-ttu-id="c3d7c-196">这样可以防止您的用户无意中授予对恶意应用程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-196">This prevents your users from inadvertently granting access to a malicious application.</span></span> <span data-ttu-id="c3d7c-197">强烈建议不要这样做，因为这会严重削弱用户在第三方应用程序中的工作效率。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-197">This isn't strongly recommended as it severely impairs your users' ability to be productive with third party applications.</span></span> <span data-ttu-id="c3d7c-198">为此，可以按照[启用或禁用集成应用程序](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps)中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-198">You can do this by following the steps in [Turning Integrated Apps on or off](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="c3d7c-199">像网络安全专家那样保护 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3d7c-199">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="c3d7c-200">你的 Microsoft 365 订阅附带了一组强大的安全功能，可用于保护你的数据和用户。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-200">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="c3d7c-201">使用“[Microsoft 365 安全路线图 - 前 30 天、90 天内以及之后的首要行动](security-roadmap.md)”，通过实施 Microsoft 建议的最佳做法来保护你的 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-201">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="c3d7c-202">需要在前 30 天完成的任务。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-202">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="c3d7c-203">这些任务会对你的用户产生直接影响并且影响很小。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-203">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="c3d7c-204">需要在 90 天内完成的任务。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-204">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="c3d7c-205">这些任务需要花费更多时间来规划和实施，但会显著改善你的安全状况。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-205">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="c3d7c-206">90 天后。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-206">Beyond 90 days.</span></span> <span data-ttu-id="c3d7c-207">这些增强功能基于前 90 天的工作构建。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-207">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3d7c-208">另请参阅：</span><span class="sxs-lookup"><span data-stu-id="c3d7c-208">See also:</span></span>

- <span data-ttu-id="c3d7c-209">[我的应用程序列表中的意外应用程序](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application)通过在实现时可能需要执行的各种操作来指导管理员。在遇到意外应用程序时，将对数据进行访问。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-209">[Unexpected application in my applications list](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) walks administrators through various actions they may want to take after realizing there are unexpected applications with access to data.</span></span>

- <span data-ttu-id="c3d7c-210">将[应用程序与 Azure Active Directory 集成](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent)是对同意和权限的高级概述。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-210">[Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) is a high-level overview of consent and permissions.</span></span>

- <span data-ttu-id="c3d7c-211">[开发应用程序时遇到的问题](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map)提供了指向各种同意相关文章的链接。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-211">[Problems developing my application](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) provides links to various consent related articles.</span></span>

- <span data-ttu-id="c3d7c-212">[Azure Active Directory （AZURE AD）中的应用程序和服务主体对象](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects)概述了应用程序和服务主体对象，这些对象是应用程序模型的核心。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-212">[Application and service principal objects in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span></span>

- <span data-ttu-id="c3d7c-213">"[管理对应用程序的访问](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps)" 是管理员管理用户对应用程序的访问权限所需的功能的概述。</span><span class="sxs-lookup"><span data-stu-id="c3d7c-213">[Manage access to apps](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) is an overview of the capabilities that administrators have to manage user access to apps.</span></span>
