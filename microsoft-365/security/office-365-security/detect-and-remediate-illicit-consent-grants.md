---
title: 检测和修正 Office 365 中的非法授权
ms.author: chrfox
author: chrfox
manager: laurawi
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
description: 了解如何识别和修正在 Office 365 中的非法许可授予攻击。
ms.openlocfilehash: 10c03fe0370732e9cb1a10a55767648ae0ddb80b
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971720"
---
# <a name="detect-and-remediate-illicit-consent-grants-in-office-365"></a><span data-ttu-id="35a16-103">检测和修正 Office 365 中的非法授权</span><span class="sxs-lookup"><span data-stu-id="35a16-103">Detect and Remediate Illicit Consent Grants in Office 365</span></span>

<span data-ttu-id="35a16-104">**摘要** 了解如何识别和修正在 Office 365 中的非法许可授予攻击。</span><span class="sxs-lookup"><span data-stu-id="35a16-104">**Summary**  Learn how to recognize and remediate the illicit consent grants attack in Office 365.</span></span>

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a><span data-ttu-id="35a16-105">什么是 Office 365 中的非法同意授权攻击？</span><span class="sxs-lookup"><span data-stu-id="35a16-105">What is the illicit consent grant attack in Office 365?</span></span>

<span data-ttu-id="35a16-106">在违法许可授予攻击中，攻击者将创建一个 Azure 注册的应用程序，该应用程序请求对联系人信息、电子邮件或文档等数据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="35a16-106">In an illicit consent grant attack, the attacker creates an Azure-registered application that requests access to data such as contact information, email, or documents.</span></span> <span data-ttu-id="35a16-107">然后，攻击者向最终用户授予权限，允许该应用程序通过网络钓鱼攻击或将非法代码注入到受信任的网站来访问其数据。</span><span class="sxs-lookup"><span data-stu-id="35a16-107">The attacker then tricks an end user into granting that application consent to access their data either through a phishing attack, or by injecting illicit code into a trusted website.</span></span> <span data-ttu-id="35a16-108">在违法应用程序被授予同意后，它将具有对数据的帐户级别访问权限，而无需组织帐户。</span><span class="sxs-lookup"><span data-stu-id="35a16-108">After the illicit application has been granted consent, it has account-level access to data without the need for an organizational account.</span></span> <span data-ttu-id="35a16-109">常规修正步骤（如重置已违例帐户的密码或要求对帐户进行多重身份验证（MFA））不会对此类型的攻击有效，因为它们是第三方应用程序，并且是组织外部的。</span><span class="sxs-lookup"><span data-stu-id="35a16-109">Normal remediation steps, like resetting passwords for breached accounts or requiring Multi-Factor Authentication (MFA) on accounts, are not effective against this type of attack, since these are third-party applications and are external to the organization.</span></span> <span data-ttu-id="35a16-110">这些攻击利用交互模型，该模型假定调用信息的实体是自动化的，而不是人工。</span><span class="sxs-lookup"><span data-stu-id="35a16-110">These attacks leverage an interaction model which presumes the entity that is calling the information is automation and not a human.</span></span>

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a><span data-ttu-id="35a16-111">非法同意在 Office 365 中授予攻击外观？</span><span class="sxs-lookup"><span data-stu-id="35a16-111">What does an illicit consent grant attack look like in Office 365?</span></span>

<span data-ttu-id="35a16-112">您需要搜索 Office 365**审核日志**，以查找该攻击的标志（也称为 "泄露" （IOC）标记）。</span><span class="sxs-lookup"><span data-stu-id="35a16-112">You need to search the Office 365 **audit log** to find signs, also called Indicators of Compromise (IOC) of this attack.</span></span> <span data-ttu-id="35a16-113">对于具有许多 Azure 注册应用程序和大型用户群的组织，最佳做法是在每周的基础上查看您的组织同意授予。</span><span class="sxs-lookup"><span data-stu-id="35a16-113">For organizations with many Azure-registered applications and a large user base, the best practice is to review your organizations consent grants on a weekly basis.</span></span>
### <a name="steps-for-finding-signs-of-this-attack"></a><span data-ttu-id="35a16-114">查找此攻击的迹象的步骤</span><span class="sxs-lookup"><span data-stu-id="35a16-114">Steps for finding signs of this attack</span></span>

1. <span data-ttu-id="35a16-115">打开 Office 365 租户中的 "**安全与合规中心**"。</span><span class="sxs-lookup"><span data-stu-id="35a16-115">Open the **Security and Compliance Center** in your Office 365 tenant.</span></span>

2. <span data-ttu-id="35a16-116">导航到 "**搜索 & 调查**" 节点，然后选择 "**审核日志**搜索"。</span><span class="sxs-lookup"><span data-stu-id="35a16-116">Navigate to the **Search & investigation** node and select **audit log** search.</span></span>

3. <span data-ttu-id="35a16-117">创建搜索（所有活动和所有用户）并筛选结果以同意应用程序，并添加 OAuth2PermissionGrant。</span><span class="sxs-lookup"><span data-stu-id="35a16-117">Create a search (all activities and all users) and filter the results for Consent to application, and Add OAuth2PermissionGrant.</span></span>

4. <span data-ttu-id="35a16-118">检查扩展属性，并查看 IsAdminContent 是否设置为 True。</span><span class="sxs-lookup"><span data-stu-id="35a16-118">Examine the Extended Properties and check to see if IsAdminContent is set to True.</span></span>

> [!NOTE]
> <span data-ttu-id="35a16-119">•在事件发生后，可能需要长达30分钟或最长24小时才能在搜索结果中显示相应的审核日志条目。</span><span class="sxs-lookup"><span data-stu-id="35a16-119">• It can take up to 30 minutes or up to 24 hours after an event occurs for the corresponding audit log entry to be displayed in the search results.</span></span> <br/><br/> <span data-ttu-id="35a16-120">•审核日志中保留和搜索的审核记录的时间长度取决于您的 Office 365 订阅，以及分配给特定用户的许可证的类型。</span><span class="sxs-lookup"><span data-stu-id="35a16-120">• The length of time that an audit record is retained and searchable in the audit log depends on your Office 365 subscription, and specifically the type of the license that is assigned to a specific user.</span></span> <span data-ttu-id="35a16-121">有关详细信息，请参阅[审核日志](../../compliance/search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="35a16-121">For more information, see [Audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>
<span data-ttu-id="35a16-122">如果此值为 true，则表示具有全局管理员访问权限的人员可能已授予对数据的广泛访问权限。</span><span class="sxs-lookup"><span data-stu-id="35a16-122">If this value is true, it indicates that someone with Global Administrator access may have granted broad access to data.</span></span> <span data-ttu-id="35a16-123">如果这是意外情况，请执行相应的步骤来[确认攻击](#how-to-confirm-an-attack)。</span><span class="sxs-lookup"><span data-stu-id="35a16-123">If this is unexpected, take steps to [confirm an attack](#how-to-confirm-an-attack).</span></span>

## <a name="how-to-confirm-an-attack"></a><span data-ttu-id="35a16-124">如何确认攻击</span><span class="sxs-lookup"><span data-stu-id="35a16-124">How to confirm an attack</span></span>

<span data-ttu-id="35a16-125">如果您有上面列出的 IOCs 的一个或多个实例，则需要进行进一步调查以确认攻击是否发生。</span><span class="sxs-lookup"><span data-stu-id="35a16-125">If you have one or more instances of the IOCs listed above, you need to do further investigation to positively confirm that the attack occurred.</span></span> <span data-ttu-id="35a16-126">您可以使用这三种方法中的任何一种来确认攻击。</span><span class="sxs-lookup"><span data-stu-id="35a16-126">You can use any of these three methods to confirm the attack.</span></span>

- <span data-ttu-id="35a16-127">使用 Azure Active Directory 门户列出应用程序及其权限。</span><span class="sxs-lookup"><span data-stu-id="35a16-127">Inventory applications and their permissions using the Azure Active Directory portal.</span></span> <span data-ttu-id="35a16-128">这种方法是彻底的，但是，如果您有多个用户要检查，则一次只能检查一个用户，这可能会非常耗时。</span><span class="sxs-lookup"><span data-stu-id="35a16-128">This method is thorough, but you can only check one user at a time which can be very time consuming if you have many users to check.</span></span>

- <span data-ttu-id="35a16-129">使用 PowerShell 清点应用程序及其权限。</span><span class="sxs-lookup"><span data-stu-id="35a16-129">Inventory applications and their permissions using PowerShell.</span></span> <span data-ttu-id="35a16-130">这是最快且最彻底的方法，最少的开销。</span><span class="sxs-lookup"><span data-stu-id="35a16-130">This is the fastest and most thorough method, with the least amount of overhead.</span></span>

- <span data-ttu-id="35a16-131">让您的用户单独检查其应用和权限，并将结果报告给管理员进行修正。</span><span class="sxs-lookup"><span data-stu-id="35a16-131">Have your users individually check their apps and permissions and report the results back to the administrators for remediation.</span></span>

## <a name="inventory-apps-with-access-in-your-organization"></a><span data-ttu-id="35a16-132">在您的组织中列出具有访问权限的应用程序</span><span class="sxs-lookup"><span data-stu-id="35a16-132">Inventory apps with access in your organization</span></span>

<span data-ttu-id="35a16-133">您可以为使用 Azure Active Directory 门户或 PowerShell 的用户执行此操作，也可以让用户单独枚举其应用程序访问。</span><span class="sxs-lookup"><span data-stu-id="35a16-133">You can do this for your users with either the Azure Active Directory Portal, or PowerShell or have your users individually enumerate their application access.</span></span>

### <a name="steps-for-using-the-azure-active-directory-portal"></a><span data-ttu-id="35a16-134">使用 Azure Active Directory 门户的步骤</span><span class="sxs-lookup"><span data-stu-id="35a16-134">Steps for using the Azure Active Directory Portal</span></span>

<span data-ttu-id="35a16-135">您可以通过使用[Azure Active Directory 门户](https://portal.azure.com/)来查找任何单个用户已向其授予权限的应用程序。</span><span class="sxs-lookup"><span data-stu-id="35a16-135">You can look up the applications to which any individual user has granted permissions by using the [Azure Active Directory Portal](https://portal.azure.com/).</span></span>

1. <span data-ttu-id="35a16-136">使用管理权限登录到 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="35a16-136">Sign in to the Azure Portal with administrative rights.</span></span>

2. <span data-ttu-id="35a16-137">选择 "Azure Active Directory" 边栏。</span><span class="sxs-lookup"><span data-stu-id="35a16-137">Select the Azure Active Directory blade.</span></span>

3. <span data-ttu-id="35a16-138">选择“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="35a16-138">Select **Users**.</span></span>

4. <span data-ttu-id="35a16-139">选择要查看的用户。</span><span class="sxs-lookup"><span data-stu-id="35a16-139">Select the user that you want to review.</span></span>

5. <span data-ttu-id="35a16-140">选择 "**应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="35a16-140">Select **Applications**.</span></span>

<span data-ttu-id="35a16-141">这将向您显示分配给用户的应用程序以及 applcations 具有的权限。</span><span class="sxs-lookup"><span data-stu-id="35a16-141">This will show you the apps that are assigned to the user and what permissions the applcations have.</span></span>

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a><span data-ttu-id="35a16-142">让用户枚举其应用程序访问权限的步骤</span><span class="sxs-lookup"><span data-stu-id="35a16-142">Steps for having your users enumerate their application access</span></span>

<span data-ttu-id="35a16-143">让你的用户转https://myapps.microsoft.com到并查看其自己的应用程序访问权限。</span><span class="sxs-lookup"><span data-stu-id="35a16-143">Have your users go to https://myapps.microsoft.com and review their own application access there.</span></span> <span data-ttu-id="35a16-144">他们应该能够查看具有访问权限的所有应用程序，查看有关这些应用程序的详细信息（包括访问范围），并能够撤销可疑或违法应用程序的权限。</span><span class="sxs-lookup"><span data-stu-id="35a16-144">They should be able to see all the apps with access, view details about them (including the scope of access), and be able to revoke privileges to suspicious or illicit apps.</span></span>

### <a name="steps-for-doing-this-with-powershell"></a><span data-ttu-id="35a16-145">使用 PowerShell 执行此操作的步骤</span><span class="sxs-lookup"><span data-stu-id="35a16-145">Steps for doing this with PowerShell</span></span>

<span data-ttu-id="35a16-146">验证非法同意授予攻击的最简单方法是运行[Get-AzureADPSPermissions](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)，这会将租赁中所有用户的所有 oauth 同意授权和 oauth 应用转储到一个 .csv 文件中。</span><span class="sxs-lookup"><span data-stu-id="35a16-146">The simplest way to verify the Illicit Consent Grant attack is to run [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), which will dump all the OAuth consent grants and OAuth apps for all users in your tenancy into one .csv file.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="35a16-147">先决条件</span><span class="sxs-lookup"><span data-stu-id="35a16-147">Pre-requisites</span></span>

- <span data-ttu-id="35a16-148">安装了 Azure AD PowerShell 库。</span><span class="sxs-lookup"><span data-stu-id="35a16-148">The Azure AD PowerShell library installed.</span></span>

- <span data-ttu-id="35a16-149">对将对其运行脚本的租户的全局管理员权限。</span><span class="sxs-lookup"><span data-stu-id="35a16-149">Global administrator rights on the tenant that the script will be run against.</span></span>

- <span data-ttu-id="35a16-150">将运行脚本的计算机上的本地管理员。</span><span class="sxs-lookup"><span data-stu-id="35a16-150">Local Administrator on the computer from which will run the scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35a16-151">强烈建议您在管理帐户上要求进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="35a16-151">We highly recommend that you require multi-factor authentication on your administrative account.</span></span> <span data-ttu-id="35a16-152">此脚本支持 MFA 身份验证。</span><span class="sxs-lookup"><span data-stu-id="35a16-152">This script supports MFA authentication.</span></span>

1. <span data-ttu-id="35a16-153">使用本地管理员权限登录到您将运行脚本的计算机。</span><span class="sxs-lookup"><span data-stu-id="35a16-153">Sign in to the computer that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="35a16-154">将[Get-AzureADPSPermissions](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)脚本从 GitHub 下载或复制到将从中运行 scruipt 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="35a16-154">Download or copy the [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script from GitHub to a folder from which you will run the scruipt.</span></span> <span data-ttu-id="35a16-155">这将是将写入输出 "权限 .csv" 文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="35a16-155">This will be the same folder to which the output "permissions.csv" file will be written.</span></span>

3. <span data-ttu-id="35a16-156">以管理员身份打开 PowerShell 实例，并打开将脚本保存到的文件夹。</span><span class="sxs-lookup"><span data-stu-id="35a16-156">Open a PowerShell instance as an administrator and open to the folder you saved the script to.</span></span>

4. <span data-ttu-id="35a16-157">使用[AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) cmdlet 连接到您的目录。</span><span class="sxs-lookup"><span data-stu-id="35a16-157">Connect to your directory using the [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) cmdlet.</span></span>

5. <span data-ttu-id="35a16-158">运行此 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="35a16-158">Run this PowerShell command:</span></span>

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

<span data-ttu-id="35a16-159">该脚本将生成一个名为 "权限 .csv" 的文件。</span><span class="sxs-lookup"><span data-stu-id="35a16-159">The script produces one file named Permissions.csv.</span></span> <span data-ttu-id="35a16-160">按照以下步骤查找违法应用程序权限授予：</span><span class="sxs-lookup"><span data-stu-id="35a16-160">Follow these steps to look for illicit application permission grants:</span></span>

1. <span data-ttu-id="35a16-161">在 ConsentType 列（列 G）中搜索值 "AllPrinciples"。</span><span class="sxs-lookup"><span data-stu-id="35a16-161">In the ConsentType column (column G) search for the value "AllPrinciples".</span></span> <span data-ttu-id="35a16-162">AllPrincipals 权限允许客户端应用程序访问租赁中的所有人的内容。</span><span class="sxs-lookup"><span data-stu-id="35a16-162">The AllPrincipals permission allows the client application to access everyone’s content in the tenancy.</span></span> <span data-ttu-id="35a16-163">本机 Office 365 应用程序需要此权限才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="35a16-163">Native Office 365 applications need this permission to work correctly.</span></span> <span data-ttu-id="35a16-164">应仔细查看具有此权限的每个非 Microsoft 应用程序。</span><span class="sxs-lookup"><span data-stu-id="35a16-164">Every non-Microsoft application with this permission should be reviewed carefully.</span></span>

2. <span data-ttu-id="35a16-165">在 "权限" 列（列 F）中，查看每个委派的应用程序对内容所拥有的权限。</span><span class="sxs-lookup"><span data-stu-id="35a16-165">In the Permission column (column F) review the permissions that each delegated application has to content.</span></span> <span data-ttu-id="35a16-166">查找 "读取" 和 "写入" 权限或 "\*"。所有 "权限，并仔细审查这些权限，因为它们可能不合适。</span><span class="sxs-lookup"><span data-stu-id="35a16-166">Look for "Read" and "Write" permission or "\*.All" permission, and review these carefully because they may not be appropriate.</span></span>

3. <span data-ttu-id="35a16-167">查看已授予同意的特定用户。</span><span class="sxs-lookup"><span data-stu-id="35a16-167">Review the specific users that have consents granted.</span></span> <span data-ttu-id="35a16-168">如果高配置文件或高影响用户授予了不适当的同意，则应进一步调查。</span><span class="sxs-lookup"><span data-stu-id="35a16-168">If high profile or high impact users have inappropriate consents granted, you should investigate further.</span></span>

4. <span data-ttu-id="35a16-169">在 "ClientDisplayName" 列（列 C）中，查找看起来可疑的应用程序。</span><span class="sxs-lookup"><span data-stu-id="35a16-169">In the ClientDisplayName column (column C) look for apps that seem suspicious.</span></span> <span data-ttu-id="35a16-170">应仔细查看具有拼写错误名称、超级 bland 名称或以黑客为名字的名称的应用程序。</span><span class="sxs-lookup"><span data-stu-id="35a16-170">Apps with misspelled names, super bland names, or hacker-sounding names should be reviewed carefully.</span></span>

## <a name="determine-the-scope-of-the-attack"></a><span data-ttu-id="35a16-171">确定攻击的范围</span><span class="sxs-lookup"><span data-stu-id="35a16-171">Determine the scope of the attack</span></span>

<span data-ttu-id="35a16-172">完成对应用程序访问的清点之后，请查看 Office 365**审核日志**以确定泄露的全部范围。</span><span class="sxs-lookup"><span data-stu-id="35a16-172">After you have finished inventorying application access, review the Office 365 **audit log** to determine the full scope of the breach.</span></span> <span data-ttu-id="35a16-173">搜索受影响的用户、违法应用程序有权访问您组织的时间段以及应用程序的权限。</span><span class="sxs-lookup"><span data-stu-id="35a16-173">Search on the affected users, the time frames that the illicit application had access to your organization, and the permissions the app had.</span></span> <span data-ttu-id="35a16-174">你可以在[Microsoft 365 安全与合规中心](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)中搜索**审核日志**。</span><span class="sxs-lookup"><span data-stu-id="35a16-174">You can search the **audit log** in the [Microsoft 365 Security and Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35a16-175">必须先启用[管理员和用户](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)的[邮箱审核](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing)和活动审核，然后才能获取此类信息。</span><span class="sxs-lookup"><span data-stu-id="35a16-175">[Mailbox auditing](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) and [Activity auditing for admins and users](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) must have been enabled prior to the attack for you to get this information.</span></span>

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a><span data-ttu-id="35a16-176">如何停止和修正违法许可授予攻击</span><span class="sxs-lookup"><span data-stu-id="35a16-176">How to stop and remediate an illicit consent grant attack</span></span>

<span data-ttu-id="35a16-177">在识别出具有非法权限的应用程序之后，可以通过多种方式删除该访问。</span><span class="sxs-lookup"><span data-stu-id="35a16-177">After you have identified an application with illicit permissions, you have several ways to remove that access.</span></span>

- <span data-ttu-id="35a16-178">您可以通过以下方式在 Azure Active Directory 门户中撤销应用程序的权限：</span><span class="sxs-lookup"><span data-stu-id="35a16-178">You can revoke the application's permission in the Azure Active Directory Portal by:</span></span>

  - <span data-ttu-id="35a16-179">导航到**Azure Active Directory 用户**边栏中受影响的用户。</span><span class="sxs-lookup"><span data-stu-id="35a16-179">Navigate to the affected user in the **Azure Active Directory User** blade.</span></span>

  - <span data-ttu-id="35a16-180">选择 "**应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="35a16-180">Select **Applications**.</span></span>

  - <span data-ttu-id="35a16-181">选择违法应用程序。</span><span class="sxs-lookup"><span data-stu-id="35a16-181">Select the illicit application.</span></span>

  - <span data-ttu-id="35a16-182">在深化中单击 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="35a16-182">Click **Remove** in the drill down.</span></span>

- <span data-ttu-id="35a16-183">您可以按照[AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant?view=azureadps-2.0)中的步骤撤销对 PowerShell 的 OAuth 同意授权。</span><span class="sxs-lookup"><span data-stu-id="35a16-183">You can revoke the OAuth consent grant with PowerShell by following the steps in [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant?view=azureadps-2.0).</span></span>

- <span data-ttu-id="35a16-184">您可以按照[AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment?view=azureadps-2.0)中的步骤，通过 PowerShell 吊销服务应用程序角色分配。</span><span class="sxs-lookup"><span data-stu-id="35a16-184">You can revoke the Service App Role Assignment with PowerShell by following the steps in [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment?view=azureadps-2.0).</span></span>

- <span data-ttu-id="35a16-185">您还可以完全禁用受影响帐户的登录，这将禁用对该帐户中的数据的应用程序访问。</span><span class="sxs-lookup"><span data-stu-id="35a16-185">You can also disable sign-in for the affected account altogether, which will in turn disable app access to data in that account.</span></span> <span data-ttu-id="35a16-186">这并不是最终用户的工作效率的理想之处，但如果您正在努力快速限制影响，则它可能是一个可行的短期补救措施。</span><span class="sxs-lookup"><span data-stu-id="35a16-186">This isn't ideal for the end user's productivity, of course, but if you are working to limit impact quickly, it can be a viable short-term remediation.</span></span>

- <span data-ttu-id="35a16-187">您可以为租赁启用集成的应用程序。</span><span class="sxs-lookup"><span data-stu-id="35a16-187">You can turn integrated applications off for your tenancy.</span></span> <span data-ttu-id="35a16-188">这是一项重大步骤，可禁用最终用户对租户范围授予许可的能力。</span><span class="sxs-lookup"><span data-stu-id="35a16-188">This is a drastic step that disables the ability for end users to grant consent on a tenant-wide basis.</span></span> <span data-ttu-id="35a16-189">这样可以防止您的用户无意中授予对恶意应用程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="35a16-189">This prevents your users from inadvertently granting access to a malicious application.</span></span> <span data-ttu-id="35a16-190">强烈建议不要这样做，因为这会严重削弱用户在第三方应用程序中的工作效率。</span><span class="sxs-lookup"><span data-stu-id="35a16-190">This isn't strongly recommended as it severely impairs your users' ability to be productive with third party applications.</span></span> <span data-ttu-id="35a16-191">为此，可以按照[启用或禁用集成应用程序](https://docs.microsoft.com/office365/admin/misc/integrated-apps)中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="35a16-191">You can do this by following the steps in [Turning Integrated Apps on or off](https://docs.microsoft.com/office365/admin/misc/integrated-apps).</span></span>

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="35a16-192">像网络安全专家那样保护 Office 365</span><span class="sxs-lookup"><span data-stu-id="35a16-192">Secure Office 365 like a cybersecurity pro</span></span>

<span data-ttu-id="35a16-193">你的 Office 365 订阅附带了一组强大的安全功能，可用于保护你的数据和用户。</span><span class="sxs-lookup"><span data-stu-id="35a16-193">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="35a16-194">使用[Office 365 安全路线图-前30天、90天和更高版本的首要优先级](security-roadmap.md)，以实现 Microsoft 建议的保护 Office 365 租户的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="35a16-194">Use the [Office 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>

- <span data-ttu-id="35a16-195">需要在前 30 天完成的任务。</span><span class="sxs-lookup"><span data-stu-id="35a16-195">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="35a16-196">这些任务会对你的用户产生直接影响并且影响很小。</span><span class="sxs-lookup"><span data-stu-id="35a16-196">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="35a16-197">需要在 90 天内完成的任务。</span><span class="sxs-lookup"><span data-stu-id="35a16-197">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="35a16-198">这些任务需要花费更多时间来规划和实施，但会显著改善你的安全状况。</span><span class="sxs-lookup"><span data-stu-id="35a16-198">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="35a16-199">90 天后。</span><span class="sxs-lookup"><span data-stu-id="35a16-199">Beyond 90 days.</span></span> <span data-ttu-id="35a16-200">这些增强功能基于前 90 天的工作构建。</span><span class="sxs-lookup"><span data-stu-id="35a16-200">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="35a16-201">另请参阅：</span><span class="sxs-lookup"><span data-stu-id="35a16-201">See also:</span></span>

- <span data-ttu-id="35a16-202">[我的应用程序列表中的意外应用程序](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application)通过在实现时可能需要执行的各种操作来指导管理员。在遇到意外应用程序时，将对数据进行访问。</span><span class="sxs-lookup"><span data-stu-id="35a16-202">[Unexpected application in my applications list](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) walks administrators through various actions they may want to take after realizing there are unexpected applications with access to data.</span></span>

- <span data-ttu-id="35a16-203">将[应用程序与 Azure Active Directory 集成](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent)是对同意和权限的高级概述。</span><span class="sxs-lookup"><span data-stu-id="35a16-203">[Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) is a high-level overview of consent and permissions.</span></span>

- <span data-ttu-id="35a16-204">[开发应用程序时遇到的问题](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map)提供了指向各种同意相关文章的链接。</span><span class="sxs-lookup"><span data-stu-id="35a16-204">[Problems developing my application](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) provides links to various consent related articles.</span></span>

- <span data-ttu-id="35a16-205">[Azure Active Directory （AZURE AD）中的应用程序和服务主体对象](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects)概述了应用程序和服务主体对象，这些对象是应用程序模型的核心。</span><span class="sxs-lookup"><span data-stu-id="35a16-205">[Application and service principal objects in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span></span>

- <span data-ttu-id="35a16-206">"[管理对应用程序的访问](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps)" 是管理员管理用户对应用程序的访问权限所需的功能的概述。</span><span class="sxs-lookup"><span data-stu-id="35a16-206">[Manage access to apps](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) is an overview of the capabilities that administrators have to manage user access to apps.</span></span>
