---
title: 使用 PowerShell 分步迁移到 Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: a20f9dbd-6102-4ffa-b72c-ff813e700930
description: 了解如何使用 PowerShell 随着时间的推移，使用分步迁移将内容从源电子邮件系统Microsoft 365。
ms.openlocfilehash: 6a458f6164a842394ec87f59df11939a8c435ea2
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229643"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a><span data-ttu-id="0a166-103">使用 PowerShell 分步迁移到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0a166-103">Use PowerShell to perform a staged migration to Microsoft 365</span></span>

<span data-ttu-id="0a166-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="0a166-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0a166-105">您可以使用分步迁移将源电子邮件系统中用户邮箱的内容Microsoft 365迁移迁移。</span><span class="sxs-lookup"><span data-stu-id="0a166-105">You can migrate the contents of user mailboxes from a source email system to Microsoft 365 over time using a staged migration.</span></span>

<span data-ttu-id="0a166-106">本文将指导你完成使用 PowerShell 进行分步电子邮件迁移Exchange Online任务。</span><span class="sxs-lookup"><span data-stu-id="0a166-106">This article walks you through the tasks involved with for a staged email migration using Exchange Online PowerShell.</span></span> <span data-ttu-id="0a166-107">有关分 [步电子邮件迁移](/Exchange/mailbox-migration/what-to-know-about-a-staged-migration)您需要了解的内容主题概述了迁移过程。</span><span class="sxs-lookup"><span data-stu-id="0a166-107">The topic, [What you need to know about a staged email migration](/Exchange/mailbox-migration/what-to-know-about-a-staged-migration), gives you an overview of the migration process.</span></span> <span data-ttu-id="0a166-108">当您了解本文的内容之后，则可以借此机会开始将一个电子邮件系统中的邮箱迁移到另一个电子邮件系统。</span><span class="sxs-lookup"><span data-stu-id="0a166-108">When you're comfortable with the contents of that article, use this one to begin migrating mailboxes from one email system to another.</span></span>

> [!NOTE]
> <span data-ttu-id="0a166-109">您还可以使用 Exchange 管理中心来执行暂存迁移。</span><span class="sxs-lookup"><span data-stu-id="0a166-109">You can also use the Exchange admin center to perform staged migration.</span></span> <span data-ttu-id="0a166-110">请参阅[执行电子邮件到电子邮件的Microsoft 365。](/Exchange/mailbox-migration/perform-a-staged-migration/perform-a-staged-migration)</span><span class="sxs-lookup"><span data-stu-id="0a166-110">See [Perform a staged migration of email to Microsoft 365](/Exchange/mailbox-migration/perform-a-staged-migration/perform-a-staged-migration).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0a166-111">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="0a166-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="0a166-112">估计完成该任务的时间：2-5 分钟，用于创建迁移批处理。</span><span class="sxs-lookup"><span data-stu-id="0a166-112">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="0a166-113">迁移批处理启动后，迁移的持续时间会有所不同，具体取决于批处理中邮箱的数量、每个邮箱的大小和可用网络容量。</span><span class="sxs-lookup"><span data-stu-id="0a166-113">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="0a166-114">有关影响将邮箱迁移到邮箱服务器所花费时间的其他Microsoft 365，请参阅迁移[性能](/Exchange/mailbox-migration/office-365-migration-best-practices)。</span><span class="sxs-lookup"><span data-stu-id="0a166-114">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).</span></span>

<span data-ttu-id="0a166-p104">您必须先获得权限，然后才能执行此过程。要查看您需要哪些权限，请参阅[收件人权限](/exchange/recipients-permissions-exchange-2013-help)主题中的"迁移"条目。</span><span class="sxs-lookup"><span data-stu-id="0a166-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in the [Recipients Permissions](/exchange/recipients-permissions-exchange-2013-help) topic.</span></span>

<span data-ttu-id="0a166-p105">若要使用 Exchange Online PowerShell cmdlet，您需要登录并将 cmdlet 导入您的本地 Windows PowerShell 会话。有关说明，请参阅[使用远程 PowerShell 连接到 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0a166-p105">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for instructions.</span></span>

<span data-ttu-id="0a166-119">有关迁移命令的完整列表，请参阅[移动和迁移 cmdlet](/powershell/exchange/)。</span><span class="sxs-lookup"><span data-stu-id="0a166-119">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

## <a name="migration-steps"></a><span data-ttu-id="0a166-120">迁移步骤</span><span class="sxs-lookup"><span data-stu-id="0a166-120">Migration steps</span></span>

### <a name="step-1-prepare-for-a-staged-migration"></a><span data-ttu-id="0a166-121">步骤 1：准备暂存迁移</span><span class="sxs-lookup"><span data-stu-id="0a166-121">Step 1: Prepare for a staged migration</span></span>

<span data-ttu-id="0a166-122">在使用分步迁移将邮箱Microsoft 365迁移之前，必须对邮箱环境进行一些Exchange更改。</span><span class="sxs-lookup"><span data-stu-id="0a166-122">Before you migrate mailboxes to Microsoft 365 by using a staged migration, there are a few changes you must make to your Exchange environment.</span></span>

 <span data-ttu-id="0a166-p106">**在您的内部部署 Exchange Server 上配置 Outlook 无处不在** 电子邮件迁移服务使用 Outlook 无处不在（也称为 RPC over HTTP）连接到您的内部部署 Exchange Server。有关如何为 Exchange Server 2007 和 Exchange 2003 设置 Outlook 无处不在 设置的信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="0a166-p106">**Configure Outlook Anywhere on your on-premises Exchange Server** The email migration service uses Outlook Anywhere (also known as RPC over HTTP), to connect to your on-premises Exchange Server. For information about how to set up Outlook Anywhere for Exchange Server 2007, and Exchange 2003, see the following:</span></span>

- <span data-ttu-id="0a166-125">[Exchange 2007:如何启用 Outlook 无处不在](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="0a166-125">[Exchange 2007: How to Enable Outlook Anywhere](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))</span></span>

- <span data-ttu-id="0a166-126">[如何使用 Exchange 2003 配置 Outlook 无处不在](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="0a166-126">[How to configure Outlook Anywhere with Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0a166-p107">您必须在 Outlook 无处不在 配置中使用受信任的证书颁发机构 (CA) 颁发的证书。Outlook 无处不在 不能通过自签名的证书进行配置。有关详细信息，请参阅[如何为 Outlook 无处不在配置 SSL](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80))。</span><span class="sxs-lookup"><span data-stu-id="0a166-p107">You must use a certificate issued by a trusted certification authority (CA) with your Outlook Anywhere configuration. Outlook Anywhere can't be configured with a self-signed certificate. For more information, see [How to configure SSL for Outlook Anywhere](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)).</span></span>

 <span data-ttu-id="0a166-130">**可选：确认您是否可以使用 Outlook 无处不在 连接到 Exchange 组织** 使用下列方法之一来测试您的连接设置。</span><span class="sxs-lookup"><span data-stu-id="0a166-130">**Optional: Verify that you can connect to your Exchange organization using Outlook Anywhere** Try one of the following methods to test your connection settings.</span></span>

- <span data-ttu-id="0a166-131">使用公司网络外部的 Outlook 连接到您的内部部署 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="0a166-131">Use Outlook from outside your corporate network to connect to your on-premises Exchange mailbox.</span></span>

- <span data-ttu-id="0a166-132">使用 [Microsoft Remote Connectivity Analyzer](https://https://testconnectivity.microsoft.com/) 测试连接设置。</span><span class="sxs-lookup"><span data-stu-id="0a166-132">Use the [Microsoft Remote Connectivity Analyzer](https://https://testconnectivity.microsoft.com/) to test your connection settings.</span></span> <span data-ttu-id="0a166-133">使用 Outlook 无处不在 (RPC over HTTP) 或 Outlook 自动发现测试。</span><span class="sxs-lookup"><span data-stu-id="0a166-133">Use the Outlook Anywhere (RPC over HTTP) or Outlook Autodiscover tests.</span></span>

- <span data-ttu-id="0a166-134">在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0a166-134">Run the following commands in Exchange Online PowerShell:</span></span>

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 <span data-ttu-id="0a166-135">**设置权限** 用于连接到内部部署 Exchange 组织 (（也称为迁移管理员) ）的本地用户帐户必须具有必要的权限才能访问要迁移到 Microsoft 365 的本地邮箱。</span><span class="sxs-lookup"><span data-stu-id="0a166-135">**Set permissions** The on-premises user account that you use to connect to your on-premises Exchange organization (also called the migration administrator) must have the necessary permissions to access the on-premises mailboxes that you want to migrate to Microsoft 365.</span></span> <span data-ttu-id="0a166-136">当您在此过程的稍后步骤 [3：](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint) 创建迁移终结点 (创建迁移终结点来连接到您的电子邮件系统时，会) 。</span><span class="sxs-lookup"><span data-stu-id="0a166-136">This user account is used when you connect to your email system by creating a migration endpoint later in this procedure ([Step 3: Create a migration endpoint](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint)).</span></span>

<span data-ttu-id="0a166-137">要迁移邮箱，管理员必须拥有以下权限集之一：</span><span class="sxs-lookup"><span data-stu-id="0a166-137">To migrate the mailboxes, the admin must have one of the following permission sets:</span></span>

- <span data-ttu-id="0a166-138">内部部署组织中 Active Directory 中的 **Domain Admins** 组成员。</span><span class="sxs-lookup"><span data-stu-id="0a166-138">Be a member of the **Domain Admins** group in Active Directory in the on-premises organization.</span></span>

    <span data-ttu-id="0a166-139">或</span><span class="sxs-lookup"><span data-stu-id="0a166-139">or</span></span>

- <span data-ttu-id="0a166-140">分配了对每个内部部署邮箱的 **FullAccess** 权限以及可修改内部部署用户帐户上的 **TargetAddress** 属性的 **WriteProperty** 权限。</span><span class="sxs-lookup"><span data-stu-id="0a166-140">Be assigned the **FullAccess** permission for each on-premises mailbox and the **WriteProperty** permission to modify the **TargetAddress** property on the on-premises user accounts.</span></span>

    <span data-ttu-id="0a166-141">或</span><span class="sxs-lookup"><span data-stu-id="0a166-141">or</span></span>

- <span data-ttu-id="0a166-142">分配了对存储用户邮箱的内部部署邮箱数据库上的 **Receive As** 权限以及可修改内部部署用户帐户上的 **TargetAddress** 属性的 **WriteProperty** 权限。</span><span class="sxs-lookup"><span data-stu-id="0a166-142">Be assigned the **Receive As** permission on the on-premises mailbox database that stores user mailboxes and the **WriteProperty** permission to modify the **TargetAddress** property on the on-premises user accounts.</span></span>

<span data-ttu-id="0a166-143">有关如何设置这些权限的说明，请参阅分配将邮箱迁移到 Microsoft 365[的权限。](/Exchange/mailbox-migration/assign-permissions-for-migration)</span><span class="sxs-lookup"><span data-stu-id="0a166-143">For instructions about how to set these permissions, see [Assign permissions to migrate mailboxes to Microsoft 365](/Exchange/mailbox-migration/assign-permissions-for-migration).</span></span>

 <span data-ttu-id="0a166-p110">**禁用统一消息 (UM)** 如果您要迁移的内部部署邮箱上开启了 UM，请先将其关闭，然后再执行迁移。迁移完成以后，打开邮箱的 UM。有关具体的操作方法步骤，请参阅 [禁用统一消息](/previous-versions/office/exchange-server-2007/bb124691(v=exchg.80))。</span><span class="sxs-lookup"><span data-stu-id="0a166-p110">**Disable Unified Messaging (UM)** If UM is turned on for the on-premises mailboxes you're migrating, turn off UM before migration. Turn on UM for the mailboxes after migration is complete. For how-to steps, see[disable unified messaging](/previous-versions/office/exchange-server-2007/bb124691(v=exchg.80)).</span></span>

 <span data-ttu-id="0a166-147">**使用目录同步在网站中创建新Microsoft 365。**</span><span class="sxs-lookup"><span data-stu-id="0a166-147">**Use directory synchronization to create new users in Microsoft 365.**</span></span> <span data-ttu-id="0a166-148">使用目录同步创建组织内部部署Microsoft 365用户。</span><span class="sxs-lookup"><span data-stu-id="0a166-148">You use directory synchronization to create all the on-premises users in your Microsoft 365 organization.</span></span>

<span data-ttu-id="0a166-p112">创建用户以后，您需要对他们授予许可。您可以在创建用户之后的 30 天内添加许可证。有关添加许可证的步骤，请参阅[步骤 8：完成迁移后任务](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration)。</span><span class="sxs-lookup"><span data-stu-id="0a166-p112">You need to license the users after they're created. You have 30 days to add licenses after the users are created. For steps to add licenses, see [Step 8: Complete post-migration tasks](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration).</span></span>

 <span data-ttu-id="0a166-152">可以使用 Azure AD Microsoft Azure Active Directory (同步) 或 Microsoft Azure AD 同步服务在 Microsoft 365 中同步和创建本地Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0a166-152">You can use either the Microsoft Azure Active Directory (Azure AD) Synchronization Tool or the Microsoft Azure AD Sync Services  to synchronize and create your on-premises users in Microsoft 365.</span></span> <span data-ttu-id="0a166-153">将邮箱迁移到 Microsoft 365 后，您可以在内部部署组织中管理用户帐户，并且这些用户帐户将Microsoft 365组织。</span><span class="sxs-lookup"><span data-stu-id="0a166-153">After mailboxes are migrated to Microsoft 365, you manage user accounts in your on-premises organization, and they're synchronized with your Microsoft 365 organization.</span></span> <span data-ttu-id="0a166-154">有关更多信息，请参阅[目录集成](/previous-versions/azure/azure-services/jj573653(v=azure.100))。</span><span class="sxs-lookup"><span data-stu-id="0a166-154">For more information, see[Directory Integration](/previous-versions/azure/azure-services/jj573653(v=azure.100)) .</span></span>

### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a><span data-ttu-id="0a166-155">步骤 2：为暂存迁移批处理创建 CSV 文件</span><span class="sxs-lookup"><span data-stu-id="0a166-155">Step 2: Create a CSV file for a staged migration batch</span></span>

<span data-ttu-id="0a166-156">确定要迁移到 Microsoft 365 本地邮箱的用户后，可以使用逗号分隔值 (CSV) 文件创建迁移批处理。</span><span class="sxs-lookup"><span data-stu-id="0a166-156">After you identify the users whose on-premises mailboxes you want to migrate to Microsoft 365, you use a comma separated value (CSV) file to create a migration batch.</span></span> <span data-ttu-id="0a166-157">CSV 文件（由用户Microsoft 365运行迁移）的每一行都包含有关本地邮箱的信息。</span><span class="sxs-lookup"><span data-stu-id="0a166-157">Each row in the CSV file—used by Microsoft 365 to run the migration—contains information about an on-premises mailbox.</span></span>

> [!NOTE]
> <span data-ttu-id="0a166-158">对于可以使用分步迁移迁移到 Microsoft 365 的数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="0a166-158">There isn't a limit for the number of mailboxes that you can migrate to Microsoft 365 using a staged migration.</span></span> <span data-ttu-id="0a166-159">迁移批处理的 CSV 文件最多可包含 2,000 行。</span><span class="sxs-lookup"><span data-stu-id="0a166-159">The CSV file for a migration batch can contain a maximum of 2,000 rows.</span></span> <span data-ttu-id="0a166-160">若要迁移 2000 个以上邮箱，请创建额外的 CSV 文件并使用每个文件来创建新的迁移批处理。</span><span class="sxs-lookup"><span data-stu-id="0a166-160">To migrate more than 2,000 mailboxes, create additional CSV files and use each file to create a new migration batch.</span></span>

 <span data-ttu-id="0a166-161">**支持的属性**</span><span class="sxs-lookup"><span data-stu-id="0a166-161">**Supported attributes**</span></span>

<span data-ttu-id="0a166-p116">暂存迁移的 CSV 文件支持下列三个属性。CSV 文件中的每一行对应于一个邮箱并且必须包含属性的相应值。</span><span class="sxs-lookup"><span data-stu-id="0a166-p116">The CSV file for a staged migration supports the following three attributes. Each row in the CSV file corresponds to a mailbox and must contain a value for each of these attributes.</span></span>

|<span data-ttu-id="0a166-164">**属性**</span><span class="sxs-lookup"><span data-stu-id="0a166-164">**Attribute**</span></span>|<span data-ttu-id="0a166-165">**说明**</span><span class="sxs-lookup"><span data-stu-id="0a166-165">**Description**</span></span>|<span data-ttu-id="0a166-166">**是否必需？**</span><span class="sxs-lookup"><span data-stu-id="0a166-166">**Required?**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0a166-167">EmailAddress</span><span class="sxs-lookup"><span data-stu-id="0a166-167">EmailAddress</span></span>  <br/> |<span data-ttu-id="0a166-168">为内部部署邮箱指定一个主要的 SMTP 电子邮件地址，例如，pilarp@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="0a166-168">Specifies the primary SMTP email address, for example, pilarp@contoso.com, for on-premises mailboxes.</span></span>  <br/> <span data-ttu-id="0a166-169">对内部部署邮箱使用主 SMTP 地址，而不是本地邮箱Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0a166-169">Use the primary SMTP address for on-premises mailboxes and not user IDs from the Microsoft 365.</span></span> <span data-ttu-id="0a166-170">例如，如果本地域名为 contoso.com 但 Microsoft 365 电子邮件域名为 service.contoso.com，那么对于 CSV 文件中的电子邮件地址，可以使用 contoso.com 域名。</span><span class="sxs-lookup"><span data-stu-id="0a166-170">For example, if the on-premises domain is named contoso.com but the Microsoft 365 email domain is named service.contoso.com, you would use the contoso.com domain name for email addresses in the CSV file.</span></span>  <br/> |<span data-ttu-id="0a166-171">必需</span><span class="sxs-lookup"><span data-stu-id="0a166-171">Required</span></span>  <br/> |
|<span data-ttu-id="0a166-172">密码</span><span class="sxs-lookup"><span data-stu-id="0a166-172">Password</span></span>  <br/> |<span data-ttu-id="0a166-173">要设置的新邮箱Microsoft 365密码。</span><span class="sxs-lookup"><span data-stu-id="0a166-173">The password to be set for the new Microsoft 365 mailbox.</span></span> <span data-ttu-id="0a166-174">适用于组织的任何密码Microsoft 365也适用于 CSV 文件中包含的密码。</span><span class="sxs-lookup"><span data-stu-id="0a166-174">Any password restrictions that are applied to your Microsoft 365 organization also apply to the passwords included in the CSV file.</span></span>  <br/> |<span data-ttu-id="0a166-175">可选</span><span class="sxs-lookup"><span data-stu-id="0a166-175">Optional</span></span>  <br/> |
|<span data-ttu-id="0a166-176">ForceChangePassword</span><span class="sxs-lookup"><span data-stu-id="0a166-176">ForceChangePassword</span></span>  <br/> |<span data-ttu-id="0a166-177">指定用户是否必须在首次登录其新邮箱时更改Microsoft 365密码。</span><span class="sxs-lookup"><span data-stu-id="0a166-177">Specifies whether a user must change the password the first time they sign in to their new Microsoft 365 mailbox.</span></span> <span data-ttu-id="0a166-178">对此参数的值使用 **True** 或 **False** 。</span><span class="sxs-lookup"><span data-stu-id="0a166-178">Use **True** or **False** for the value of this parameter.</span></span> <br/> <span data-ttu-id="0a166-179">> [!NOTE]> 如果已通过在本地组织中部署 Active Directory 联合身份验证服务 (AD FS) 或更高版本来实现单一登录 (SSO) 解决方案，必须将 **ForceChangePassword** 属性值设为 **False**。</span><span class="sxs-lookup"><span data-stu-id="0a166-179">> [!NOTE]> If you've implemented a single sign-on (SSO) solution by deploying Active Directory Federation Services (AD FS) or greater in your on-premises organization, you must use **False** for the value of the **ForceChangePassword** attribute.</span></span>          |<span data-ttu-id="0a166-180">可选</span><span class="sxs-lookup"><span data-stu-id="0a166-180">Optional</span></span>  <br/> |

 <span data-ttu-id="0a166-181">**CSV 文件格式**</span><span class="sxs-lookup"><span data-stu-id="0a166-181">**CSV file format**</span></span>

<span data-ttu-id="0a166-182">以下是 CSV 文件格式的示例。</span><span class="sxs-lookup"><span data-stu-id="0a166-182">Here's an example of the format for the CSV file.</span></span> <span data-ttu-id="0a166-183">本示例中，将三个本地邮箱迁移到Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0a166-183">In this example, three on-premises mailboxes are migrated to Microsoft 365.</span></span>

<span data-ttu-id="0a166-p121">CSV 文件的第一行（即标题行）列出了在后续行中指定的属性（或字段）的名称。每个属性名称都用逗号分隔开。</span><span class="sxs-lookup"><span data-stu-id="0a166-p121">The first row, or header row, of the CSV file lists the names of the attributes, or fields, specified in the rows that follow. Each attribute name is separated by a comma.</span></span>

```powershell
EmailAddress,Password,ForceChangePassword
pilarp@contoso.com,Pa$$w0rd,False
tobyn@contoso.com,Pa$$w0rd,False
briant@contoso.com,Pa$$w0rd,False
```

<span data-ttu-id="0a166-p122">标题行下面的每行都表示一个用户，并提供将用于迁移该用户邮箱的信息。每行中属性值的顺序必须与标题行中属性名的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="0a166-p122">Each row under the header row represents one user and supplies the information that will be used to migrate the user's mailbox. The attribute values in each row must be in the same order as the attribute names in the header row.</span></span>

<span data-ttu-id="0a166-p123">使用任何文本编辑器或 Excel 等应用程序创建 CSV 文件。将该文件另存为 .csv 或 .txt 文件。</span><span class="sxs-lookup"><span data-stu-id="0a166-p123">Use any text editor, or an application like Excel , to create the CSV file. Save the file as a .csv or .txt file.</span></span>

> [!NOTE]
> <span data-ttu-id="0a166-p124">如果 CSV 文件包含非 ASCII 字符或特殊字符，请使用 UTF-8 或其他 Unicode 编码保存 CSV 文件。根据应用程序的不同，如果计算机的系统区域设置与 CSV 文件中使用的语言相匹配，则使用 UTF-8 或其他 Unicode 编码保存 CSV 文件可能会更容易。</span><span class="sxs-lookup"><span data-stu-id="0a166-p124">If the CSV file contains non-ASCII or special characters, save the CSV file with UTF-8 or other Unicode encoding. Depending on the application, saving the CSV file with UTF-8 or other Unicode encoding can be easier when the system locale of the computer matches the language used in the CSV file.</span></span>

### <a name="step-3-create-a-migration-endpoint"></a><span data-ttu-id="0a166-192">步骤 3：创建迁移终结点</span><span class="sxs-lookup"><span data-stu-id="0a166-192">Step 3: Create a migration endpoint</span></span>
<span data-ttu-id="0a166-193"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="0a166-193"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="0a166-194">若要成功迁移电子邮件，Microsoft 365需要与源电子邮件系统连接并进行通信。</span><span class="sxs-lookup"><span data-stu-id="0a166-194">To migrate email successfully, Microsoft 365 needs to connect and communicate with the source email system.</span></span> <span data-ttu-id="0a166-195">为此，Microsoft 365迁移终结点。</span><span class="sxs-lookup"><span data-stu-id="0a166-195">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="0a166-196">要使用 PowerShell 创建适用于暂存迁移的 Outlook 无处不在迁移终结点，首先[连接到 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="0a166-196">To create an Outlook Anywhere migration endpoint by using PowerShell, for staged migration, first [connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="0a166-197">有关迁移命令的完整列表，请参阅[移动和迁移 cmdlet](/powershell/exchange/)。</span><span class="sxs-lookup"><span data-stu-id="0a166-197">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

<span data-ttu-id="0a166-198">要在 Exchange Online PowerShell 中创建名为“StagedEndpoint”的 Outlook 无处不在迁移终结点，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0a166-198">To create an Outlook Anywhere migration endpoint called "StagedEndpoint" in Exchange Online PowerShell, run the following commands:</span></span>

```powershell
$Credentials = Get-Credential
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name StagedEndpoint -Autodiscover -EmailAddress administrator@contoso.com -Credentials $Credentials
```

<span data-ttu-id="0a166-199">有关 **New-MigrationEndpoint** cmdlet 的详细信息，请参阅 [New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint)。</span><span class="sxs-lookup"><span data-stu-id="0a166-199">For more information about the **New-MigrationEndpoint** cmdlet, see[New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint).</span></span>

> [!NOTE]
> <span data-ttu-id="0a166-p126">可以使用 **New-MigrationEndpoint** cmdlet 指定服务要通过 **-TargetDatabase** 选项使用的数据库。在其他情况下，系统会从管理邮箱所在的 Active Directory 联合身份验证服务 (AD FS) 2.0 站点中随机分配数据库。</span><span class="sxs-lookup"><span data-stu-id="0a166-p126">The **New-MigrationEndpoint** cmdlet can be used to specify a database for the service to use by using the **-TargetDatabase** option. Otherwise a database is randomly assigned from the Active Directory Federation Services (AD FS) 2.0 site where the management mailbox is located.</span></span>

#### <a name="verify-it-worked"></a><span data-ttu-id="0a166-202">验证它是否起作用</span><span class="sxs-lookup"><span data-stu-id="0a166-202">Verify it worked</span></span>

<span data-ttu-id="0a166-203">在 Exchange Online PowerShell 中，运行以下命令来显示有关“StagedEndpoint”迁移终结点的信息：</span><span class="sxs-lookup"><span data-stu-id="0a166-203">In Exchange Online PowerShell, run the following command to display information about the "StagedEndpoint" migration endpoint:</span></span>

```powershell
Get-MigrationEndpoint StagedEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*
```

### <a name="step-4-create-and-start-a-stage-migration-batch"></a><span data-ttu-id="0a166-204">步骤 4：创建并启动暂存迁移批处理</span><span class="sxs-lookup"><span data-stu-id="0a166-204">Step 4: Create and start a stage migration batch</span></span>
<span data-ttu-id="0a166-205"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="0a166-205"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="0a166-p127">您可以在 Exchange Online PowerShell 中使用 **New-MigrationBatch** cmdlet 为直接转换迁移创建迁移批处理。您可以通过包括 _AutoStart_ 参数来创建迁移批处理并自动启动。或者，您可以通过使用 **Start-MigrationBatch** cmdlet 创建迁移批处理，然后手动启动。此示例创建名为"StagedBatch1"的迁移批处理并使用之前步骤中创建的迁移终结点。</span><span class="sxs-lookup"><span data-stu-id="0a166-p127">You can use the **New-MigrationBatch** cmdlet in Exchange Online PowerShell to create a migration batch for a cutover migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then manually start it afterwards by using the **Start-MigrationBatch** cmdlet. This example creates a migration batch called "StagedBatch1" and uses the migration endpoint that was created in the previous step.</span></span>

```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint -AutoStart
```

<span data-ttu-id="0a166-p128">此示例还会创建名为"StagedBatch1"的迁移批处理并使用之前步骤中创建的迁移终结点。由于未包括  _AutoStart_ 参数，因此必须在迁移主控板中手动启动迁移批处理或者通过使用 **Start-MigrationBatch** cmdlet 手动启动迁移批处理。如前所述，一次只能存在一个直接转换迁移批处理。</span><span class="sxs-lookup"><span data-stu-id="0a166-p128">This example also creates a migration batch called "StagedBatch1" and uses the migration endpoint that was created in the previous step. Because the  _AutoStart_ parameter isn't included, the migration batch has to be manually started on the migration dashboard or by using **Start-MigrationBatch** cmdlet. As previously stated, only one cutover migration batch can exist at a time.</span></span>

```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint
```

#### <a name="verify-it-worked"></a><span data-ttu-id="0a166-213">验证它是否起作用</span><span class="sxs-lookup"><span data-stu-id="0a166-213">Verify it worked</span></span>

<span data-ttu-id="0a166-214">在 Exchange Online PowerShell 中运行以下命令来显示有关“StagedBatch1”的信息：</span><span class="sxs-lookup"><span data-stu-id="0a166-214">Run the following command in Exchange Online PowerShell to display information about the "StagedBatch1":</span></span>

```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List
```

<span data-ttu-id="0a166-215">您还可以通过运行以下命令，验证该批处理是否已启动：</span><span class="sxs-lookup"><span data-stu-id="0a166-215">You can also verify that the batch has started by running the following command:</span></span>

```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List Status
```

<span data-ttu-id="0a166-216">有关 **Get-MigrationBatch** cmdlet 的详细信息，请参阅 [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)。</span><span class="sxs-lookup"><span data-stu-id="0a166-216">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).</span></span>

### <a name="step-5-convert-on-premises-mailboxes-to-mail-enabled-users"></a><span data-ttu-id="0a166-217">步骤 5：将内部部署邮箱转换为启用邮件的用户</span><span class="sxs-lookup"><span data-stu-id="0a166-217">Step 5: Convert on-premises mailboxes to mail-enabled users</span></span>
<span data-ttu-id="0a166-218"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="0a166-218"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="0a166-219">成功迁移一批邮箱以后，您需要某种方法使用户可以访问他们的邮件。</span><span class="sxs-lookup"><span data-stu-id="0a166-219">After you have successfully migrated a batch of mailboxes, you need some way to let users get to their mail.</span></span> <span data-ttu-id="0a166-220">其邮箱已迁移的用户现在同时具有一个本地邮箱和一个Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="0a166-220">A user whose mailbox has been migrated now has both a mailbox on-premises and one in Microsoft 365.</span></span> <span data-ttu-id="0a166-221">拥有邮箱的用户Microsoft 365将停止接收其本地邮箱中的新邮件。</span><span class="sxs-lookup"><span data-stu-id="0a166-221">Users who have a mailbox in Microsoft 365 will stop receiving new mail in their on-premises mailbox.</span></span>

<span data-ttu-id="0a166-222">由于您尚未完成迁移，因此您尚未准备好指示所有用户Microsoft 365电子邮件。</span><span class="sxs-lookup"><span data-stu-id="0a166-222">Because you are not done with your migrations, you are not yet ready to direct all users to Microsoft 365 for their email.</span></span> <span data-ttu-id="0a166-223">那么，可以为这些拥有两个邮箱的用户做些什么呢？</span><span class="sxs-lookup"><span data-stu-id="0a166-223">So what do you do for those people who have both?</span></span> <span data-ttu-id="0a166-224">您可以做的是更改您已迁移到邮件启用的用户的内部部署邮箱。</span><span class="sxs-lookup"><span data-stu-id="0a166-224">What you can do is change the on-premises mailboxes that you've already migrated to mail-enabled users.</span></span> <span data-ttu-id="0a166-225">当您从邮箱更改为启用邮件的用户时，您可以指示用户Microsoft 365电子邮件，而不是访问其本地邮箱。</span><span class="sxs-lookup"><span data-stu-id="0a166-225">When you change from a mailbox to a mail-enabled user, you can direct the user to Microsoft 365 for their email instead of going to their on-premises mailbox.</span></span>

<span data-ttu-id="0a166-226">将本地邮箱转换为启用邮件的用户的另一个重要原因是，将代理地址复制到启用邮件的用户，以保留 Microsoft 365 邮箱中的代理地址。</span><span class="sxs-lookup"><span data-stu-id="0a166-226">Another important reason to convert on-premises mailboxes to mail-enabled users is to retain proxy addresses from the Microsoft 365 mailboxes by copying proxy addresses to the mail-enabled users.</span></span> <span data-ttu-id="0a166-227">这使您可以使用 Active Directory 管理来自内部部署组织的基于云的用户。</span><span class="sxs-lookup"><span data-stu-id="0a166-227">This lets you manage cloud-based users from your on-premises organization by using Active Directory.</span></span> <span data-ttu-id="0a166-228">此外，如果决定在所有邮箱迁移到 Microsoft 365 后停止使用内部部署 Exchange Server 组织，则已复制到启用邮件的用户的代理地址将保留在内部部署 Active Directory 中。</span><span class="sxs-lookup"><span data-stu-id="0a166-228">Also, if you decide to decommission your on-premises Exchange Server organization after all mailboxes are migrated to Microsoft 365, the proxy addresses you've copied to the mail-enabled users will remain in your on-premises Active Directory.</span></span>

### <a name="step-6-delete-a-staged-migration-batch"></a><span data-ttu-id="0a166-229">步骤 6：删除暂存迁移批处理</span><span class="sxs-lookup"><span data-stu-id="0a166-229">Step 6: Delete a staged migration batch</span></span>
<span data-ttu-id="0a166-230"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="0a166-230"><a name="BK_Endpoint"> </a></span></span>

 <span data-ttu-id="0a166-231">在迁移批处理中的所有邮箱都已成功迁移并且将批处理中的内部部署邮箱转换为启用邮件的用户之后，可以准备删除暂存迁移批处理。</span><span class="sxs-lookup"><span data-stu-id="0a166-231">After all mailboxes in a migration batch have been successfully migrated, and you've converted the on-premises mailboxes in the batch to mail-enabled users, you're ready to delete a staged migration batch.</span></span> <span data-ttu-id="0a166-232">请确保验证邮件是否正在转发到迁移批处理Microsoft 365邮箱。</span><span class="sxs-lookup"><span data-stu-id="0a166-232">Be sure to verify that mail is being forwarded to the Microsoft 365 mailboxes in the migration batch.</span></span> <span data-ttu-id="0a166-233">当您删除暂存迁移批处理时，迁移服务将清除任何与迁移批处理相关的记录，同时删除迁移批处理。</span><span class="sxs-lookup"><span data-stu-id="0a166-233">When you delete a staged migration batch, the migration service cleans up any records related to the migration batch and deletes the migration batch.</span></span>

<span data-ttu-id="0a166-234">要在 Exchange Online PowerShell 中删除“StagedBatch1”迁移批处理，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="0a166-234">To delete the "StagedBatch1" migration batch in Exchange Online PowerShell, run the following command.</span></span>

```powershell
Remove-MigrationBatch -Identity StagedBatch1
```

<span data-ttu-id="0a166-235">有关 **Remove-MigrationBatch** cmdlet 的详细信息，请参阅 [Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch)。</span><span class="sxs-lookup"><span data-stu-id="0a166-235">For more information about the **Remove-MigrationBatch** cmdlet, see[Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch).</span></span>

#### <a name="verify-it-worked"></a><span data-ttu-id="0a166-236">验证它是否起作用</span><span class="sxs-lookup"><span data-stu-id="0a166-236">Verify it worked</span></span>

<span data-ttu-id="0a166-237">在 Exchange Online PowerShell 中运行以下命令来显示有关“IMAPBatch1”的信息：</span><span class="sxs-lookup"><span data-stu-id="0a166-237">Run the following command in Exchange Online PowerShell to display information about the "IMAPBatch1":</span></span>

```powershell
Get-MigrationBatch StagedBatch1
```

<span data-ttu-id="0a166-238">此命令会返回状态为 **Removing** 的迁移批处理或返回错误消息，指出未找到该迁移批处理，验证该批处理已删除。</span><span class="sxs-lookup"><span data-stu-id="0a166-238">The command will return either the migration batch with a status of **Removing**, or it will return an error stating that migration batch couldn't be found, verifying that the batch was deleted.</span></span>

<span data-ttu-id="0a166-239">有关 **Get-MigrationBatch** cmdlet 的详细信息，请参阅 [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)。</span><span class="sxs-lookup"><span data-stu-id="0a166-239">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).</span></span>

### <a name="step7-assign-licenses-to-microsoft-365-users"></a><span data-ttu-id="0a166-240">步骤 7：向用户Microsoft 365许可证</span><span class="sxs-lookup"><span data-stu-id="0a166-240">Step7: Assign licenses to Microsoft 365 users</span></span>
<span data-ttu-id="0a166-241"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="0a166-241"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="0a166-242">通过Microsoft 365许可证激活迁移帐户的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0a166-242">Activate Microsoft 365 user accounts for the migrated accounts by assigning licenses.</span></span> <span data-ttu-id="0a166-243">如果您不分配许可证，则在宽限期（30 天）结束后将禁用该邮箱。</span><span class="sxs-lookup"><span data-stu-id="0a166-243">If you don't assign a license, the mailbox is disabled when the grace period (30 days) ends.</span></span> <span data-ttu-id="0a166-244">若要在许可证分配Microsoft 365 管理中心，请参阅[分配或取消分配许可证](../admin/manage/assign-licenses-to-users.md)。</span><span class="sxs-lookup"><span data-stu-id="0a166-244">To assign a license in the Microsoft 365 admin center, see [Assign or unassign licenses](../admin/manage/assign-licenses-to-users.md).</span></span>

### <a name="step-8-complete-post-migration-tasks"></a><span data-ttu-id="0a166-245">步骤 8：完成迁移后任务</span><span class="sxs-lookup"><span data-stu-id="0a166-245">Step 8: Complete post-migration tasks</span></span>
<span data-ttu-id="0a166-246"><a name="BK_Postmigration"> </a></span><span class="sxs-lookup"><span data-stu-id="0a166-246"><a name="BK_Postmigration"> </a></span></span>

- <span data-ttu-id="0a166-247">**创建自动发现 DNS 记录，以便用户可以轻松地访问他们的邮箱。**</span><span class="sxs-lookup"><span data-stu-id="0a166-247">**Create an Autodiscover DNS record so users can easily get to their mailboxes.**</span></span> <span data-ttu-id="0a166-248">在所有内部部署邮箱迁移到 Microsoft 365 之后，您可以为 Microsoft 365 组织配置自动发现 DNS 记录，以使用户能够使用 Outlook 和移动客户端轻松连接到其新的 Microsoft 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="0a166-248">After all on-premises mailboxes are migrated to Microsoft 365, you can configure an Autodiscover DNS record for your Microsoft 365 organization to enable users to easily connect to their new Microsoft 365 mailboxes with Outlook and mobile clients.</span></span> <span data-ttu-id="0a166-249">这一新的自动发现 DNS 记录必须使用相同的命名空间，该命名空间用于 Microsoft 365 组织。</span><span class="sxs-lookup"><span data-stu-id="0a166-249">This new Autodiscover DNS record has to use the same namespace that you're using for your Microsoft 365 organization.</span></span> <span data-ttu-id="0a166-250">例如，如果您的基于云的命名空间是 cloud.contoso.com，那么您需要创建的自动发现 DNS 记录是 autodiscover.cloud.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="0a166-250">For example, if your cloud-based namespace is cloud.contoso.com, the Autodiscover DNS record you need to create is autodiscover.cloud.contoso.com.</span></span>

    <span data-ttu-id="0a166-251">Microsoft 365使用 CNAME 记录为客户端和移动客户端Outlook自动发现服务。</span><span class="sxs-lookup"><span data-stu-id="0a166-251">Microsoft 365 uses a CNAME record to implement the Autodiscover service for Outlook and mobile clients.</span></span> <span data-ttu-id="0a166-252">自动发现 CNAME 记录必须包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="0a166-252">The Autodiscover CNAME record must contain the following information:</span></span>

  - <span data-ttu-id="0a166-253">**别名：** autodiscover</span><span class="sxs-lookup"><span data-stu-id="0a166-253">**Alias:** autodiscover</span></span>

  - <span data-ttu-id="0a166-254">**目标：** autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0a166-254">**Target:** autodiscover.outlook.com</span></span>

    <span data-ttu-id="0a166-255">有关详细信息，请参阅添加 [DNS 记录以连接你的域](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="0a166-255">For more information, see [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

- <span data-ttu-id="0a166-256">**停止使用内部部署 Exchange 服务器。**</span><span class="sxs-lookup"><span data-stu-id="0a166-256">**Decommission on-premises Exchange servers.**</span></span> <span data-ttu-id="0a166-257">在验证所有电子邮件是否直接路由到 Microsoft 365 邮箱，并且不再需要维护内部部署电子邮件组织或不用计划实施 SSO 解决方案后，可以从服务器中卸载 Exchange 并删除内部部署 Exchange 组织。</span><span class="sxs-lookup"><span data-stu-id="0a166-257">After you've verified that all email is being routed directly to the Microsoft 365 mailboxes, and you no longer need to maintain your on-premises email organization or don't plan on implementing an SSO solution, you can uninstall Exchange from your servers and remove your on-premises Exchange organization.</span></span>

    <span data-ttu-id="0a166-258">有关详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="0a166-258">For more information, see the following:</span></span>

  - <span data-ttu-id="0a166-259">[修改或删除 Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))</span><span class="sxs-lookup"><span data-stu-id="0a166-259">[Modify or Remove Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))</span></span>

  - <span data-ttu-id="0a166-260">[如何删除 Exchange 2007 组织](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="0a166-260">[How to Remove an Exchange 2007 Organization](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))</span></span>

  - <span data-ttu-id="0a166-261">[如何卸载 Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="0a166-261">[How to Uninstall Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))</span></span>
