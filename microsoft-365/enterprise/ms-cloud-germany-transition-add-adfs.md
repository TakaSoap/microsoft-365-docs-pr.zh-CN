---
title: 从德国 Microsoft 云迁移的 AD FS 迁移步骤
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：Active Directory 联合身份验证 (AD FS) Microsoft 云德国迁移的迁移步骤。
ms.openlocfilehash: 852fc8f93158d7b6080f1add5a05e7367539f889
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838409"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="ab143-103">从德国 Microsoft 云迁移的 AD FS 迁移步骤</span><span class="sxs-lookup"><span data-stu-id="ab143-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="ab143-104">此配置更改需要在阶段 2 启动之前随时应用。</span><span class="sxs-lookup"><span data-stu-id="ab143-104">This configuration change needs to be applied any time before phase 2 is starting.</span></span>
<span data-ttu-id="ab143-105">第 2 阶段完成后，配置更改将正常工作，并且你能够通过 Office 365 全局终结点（如 ）登录 `https://portal.office.com` 。</span><span class="sxs-lookup"><span data-stu-id="ab143-105">Once phase 2 is completed the configuration change will work and you are able to sign in via Office 365 Global endpoints such as `https://portal.office.com`.</span></span> <span data-ttu-id="ab143-106">如果在阶段 2 之前实现配置更改，Office 365 全局终结点将尚不起作用，但新的信赖方信任仍然是 Active Directory 联合身份验证服务 (AD FS) 配置的一部分。</span><span class="sxs-lookup"><span data-stu-id="ab143-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="ab143-107">将联合身份验证与 Active Directory 联合身份验证服务 (AD FS) 一同使用的客户不应更改在迁移期间用于本地 Active Directory 域服务 (AD DS) 的所有身份验证的颁发者 URI。</span><span class="sxs-lookup"><span data-stu-id="ab143-107">Customers who use federated authentication with Active Directory Federation Services (AD FS) shouldn't make changes to issuer URIs that are used for all authentications with on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="ab143-108">更改颁发者 URI 将导致域中用户的身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="ab143-108">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="ab143-109">可以在 AD FS 中直接更改颁发者 URI，或在将域从托管域转换为联合域时更改，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="ab143-109">Issuer URIs can be changed directly in AD FS or when a domain is converted from _managed_ to _federated_ and vice-versa.</span></span> <span data-ttu-id="ab143-110">建议不要添加、删除或转换已迁移的 Azure AD 租户中的联合域。</span><span class="sxs-lookup"><span data-stu-id="ab143-110">We recommend that you do not add, remove, or convert a federated domain in the Azure AD tenant that has been migrated.</span></span> <span data-ttu-id="ab143-111">完全完成迁移后，可更改颁发者 URI。</span><span class="sxs-lookup"><span data-stu-id="ab143-111">Issuer URIs can be changed after the migration is fully complete.</span></span>

<span data-ttu-id="ab143-112">若要准备 AD FS 场以从德国 Microsoft 云进行迁移，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ab143-112">To prepare your AD FS farm for the migration from Microsoft Cloud Deutschland perform the following steps:</span></span>

1. <span data-ttu-id="ab143-113">按照以下步骤备份 AD FS 设置，包括现有的德国 Microsoft 云信赖 [方信任](#backup)。</span><span class="sxs-lookup"><span data-stu-id="ab143-113">Back up your AD FS settings, including the existing Microsoft Cloud Deutschland Relying Party trust, with [these steps](#backup).</span></span> <span data-ttu-id="ab143-114">将备份 **名称为 MicrosoftCloudDeutschlandOnly** 以指示它仅包含 Microsoft 云德国租户信息。</span><span class="sxs-lookup"><span data-stu-id="ab143-114">Name the backup **MicrosoftCloudDeutschlandOnly** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ab143-115">备份将不仅包含 Microsoft 云德国的现有 Office 365 信赖方信任，还包含各个 AD FS 场上存在的所有其他信赖方信任。</span><span class="sxs-lookup"><span data-stu-id="ab143-115">The backup will not only contain the existing Office 365 Relying Party Trust for Microsoft Cloud Deutschland, but also all other Relying Party Trusts present on the respective AD FS farm.</span></span>

2. <span data-ttu-id="ab143-116">使用 MicrosoftCloudDeutschlandOnly 备份测试还原，AD FS 场应继续仅作为德国 Microsoft 云运行。</span><span class="sxs-lookup"><span data-stu-id="ab143-116">Test the restore using the MicrosoftCloudDeutschlandOnly backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="ab143-117">完成和测试 AD FS 备份后，执行以下步骤以向 ADFS 配置添加新的信赖方信任：</span><span class="sxs-lookup"><span data-stu-id="ab143-117">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="ab143-118">打开 AD FS 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ab143-118">Open the AD FS management console.</span></span>

2. <span data-ttu-id="ab143-119">在 ADFS 管理控制台的左侧窗格中，导航到" **信赖方信任"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="ab143-119">In the left pane of the ADFS management console navigate to the **Relying Party Trusts** menu.</span></span>

3. <span data-ttu-id="ab143-120">在右侧窗格中，选择" **添加信赖方信任..."。**</span><span class="sxs-lookup"><span data-stu-id="ab143-120">In the right pane, select **Add Relying Party Trust...**</span></span>

4. <span data-ttu-id="ab143-121">在 **"** 添加信赖 **方信任** "向导的"欢迎"页上选择"开始"。</span><span class="sxs-lookup"><span data-stu-id="ab143-121">Select **Start** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>

5. <span data-ttu-id="ab143-122">在"**选择数据源"** 页上，选择"导入有关联机发布的信赖方或本地 **网络的数据"。**</span><span class="sxs-lookup"><span data-stu-id="ab143-122">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="ab143-123">联合 **元数据地址 (主机名或 URL**) 的值必须设置为 `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 。</span><span class="sxs-lookup"><span data-stu-id="ab143-123">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="ab143-124">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="ab143-124">Click **Next**.</span></span>

6. <span data-ttu-id="ab143-125">在" **指定显示名称** "页上，键入 显示名称，Microsoft Office **365 Identity Platform WorldWide**。</span><span class="sxs-lookup"><span data-stu-id="ab143-125">On the **Specify Display Name** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="ab143-126">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="ab143-126">Click **Next**.</span></span>

7. <span data-ttu-id="ab143-127">如果你使用的是 Windows Server 2012 中的 ADFS，请在向导页面"现在配置多重身份验证？"上，根据你的身份验证要求选择合适的选项。</span><span class="sxs-lookup"><span data-stu-id="ab143-127">If you are using ADFS in Windows Server 2012, on the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="ab143-128">如果坚持使用默认值，请选择"我目前不想为此信赖方信任配置多重 **身份验证设置"。**</span><span class="sxs-lookup"><span data-stu-id="ab143-128">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="ab143-129">如果需要，可以在以后更改此设置。</span><span class="sxs-lookup"><span data-stu-id="ab143-129">You can change this setting later if you want to.</span></span>

8. <span data-ttu-id="ab143-130">对于 AD FS 2012：在"**选择颁发授权** 规则"上，保留选中"允许所有用户访问此 **信赖** 方"，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="ab143-130">For AD FS 2012: On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected and click **Next**.</span></span>

8. <span data-ttu-id="ab143-131">对于 AD FS 2016 和 AD FS 2019：在"**选择访问控制** 策略"页上，选择相应的访问控制策略，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="ab143-131">For AD FS 2016 and AD FS 2019: On the **Choose Access Control Policy** page, select the appropriate access control policy and click **Next**.</span></span> <span data-ttu-id="ab143-132">如果未选择任何选项，则信赖方信任 **将不起作用** 。</span><span class="sxs-lookup"><span data-stu-id="ab143-132">If none is chosen, the Relying Party Trust will **NOT** work.</span></span>

9. <span data-ttu-id="ab143-133">单击 **"** 准备添加 **信任"页上** 的"下一步"以完成向导。</span><span class="sxs-lookup"><span data-stu-id="ab143-133">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>

10. <span data-ttu-id="ab143-134">单击 **"完成** " **页上的"关闭** "。</span><span class="sxs-lookup"><span data-stu-id="ab143-134">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="ab143-135">通过关闭向导，可建立与 Office 365 全局服务之间的信赖方信任。</span><span class="sxs-lookup"><span data-stu-id="ab143-135">By closing the wizard, the Relying Party Trust with the Office 365 Global service is established.</span></span> <span data-ttu-id="ab143-136">但是，尚未配置任何颁发转换规则。</span><span class="sxs-lookup"><span data-stu-id="ab143-136">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="ab143-137">可以使用 [AD FS 帮助](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 生成正确的颁发转换规则。</span><span class="sxs-lookup"><span data-stu-id="ab143-137">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="ab143-138">使用 AD FS 帮助创建的生成的声明规则可通过 AD FS 管理控制台手动添加，也可通过 PowerShell 手动添加。</span><span class="sxs-lookup"><span data-stu-id="ab143-138">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="ab143-139">AD FS 帮助将生成需要执行的必要 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="ab143-139">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

> [!NOTE]
> <span data-ttu-id="ab143-140">[AD FS 帮助](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 将生成随产品一起提供的标准发布转换规则。</span><span class="sxs-lookup"><span data-stu-id="ab143-140">[AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) will generate the standard issuance transform rules that ship with the product.</span></span> <span data-ttu-id="ab143-141">但是，如果 Microsoft 云德国信赖方信任 (（例如，自定义颁发者 URI、非标准不可变的 ID 或任何其他自定义项) ）中已制定自定义颁发转换规则，则必须修改 AD FS 生成的规则，以适合 Microsoft 云德国信赖方信任当前就地的自定义逻辑。</span><span class="sxs-lookup"><span data-stu-id="ab143-141">However, if custom issuance transform rules are in place in the Microsoft Cloud Deutschland Relying Party Trust (for example, custom issuer URIs, non-standard immutable IDs, or any other customizations), the rules generated by AD FS help must be modified in a way that they fit the custom logic currently in place for the Microsoft Cloud Deutschland relying party trust.</span></span> <span data-ttu-id="ab143-142">如果这些自定义项未集成到通过 [AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)帮助生成的规则中，则对 **Microsoft Office 365 Identity Platform WorldWide** 进行身份验证很可能对联合身份不起作用。 </span><span class="sxs-lookup"><span data-stu-id="ab143-142">If these customizations are not integrated in the rules generated via [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator), authentication to **Microsoft Office 365 Identity Platform WorldWide** will most likely **not** work for your federated identities.</span></span>

1. <span data-ttu-id="ab143-143">在 [AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)帮助上运行"生成声明"，然后使用脚本右上角的"复制"选项复制 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="ab143-143">Run **Generate Claims** on [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) and copy the PowerShell script using the **Copy** option on the right upper corner of the script.</span></span>

2. <span data-ttu-id="ab143-144">按照 [AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 帮助中概述的步骤操作，了解如何在 AD FS 场中运行 PowerShell 脚本以生成全局信赖方信任。</span><span class="sxs-lookup"><span data-stu-id="ab143-144">Follow the steps outlined at [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) on how to run the PowerShell script in your AD FS farm to generate the global Relying Party Trust.</span></span>

3. <span data-ttu-id="ab143-145">确认存在两个信赖方Ttrusts;一个适用于德国 Microsoft 云，另一个适用于 Office 365 全球服务。</span><span class="sxs-lookup"><span data-stu-id="ab143-145">Verify that two Relying PartyTtrusts are present; one for Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span> <span data-ttu-id="ab143-146">以下命令可用于检查。</span><span class="sxs-lookup"><span data-stu-id="ab143-146">The following command can be leveraged for the check.</span></span> <span data-ttu-id="ab143-147">它应返回两行以及各自的名称和标识符。</span><span class="sxs-lookup"><span data-stu-id="ab143-147">It should return two rows and the respective names and identifiers.</span></span>

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. <span data-ttu-id="ab143-148">使用以下步骤备份完整迁移配置，包括信赖方 [信任](#backup)。</span><span class="sxs-lookup"><span data-stu-id="ab143-148">Backup your full migration configuration, including both Relying Party trusts, using [these steps](#backup).</span></span> <span data-ttu-id="ab143-149">将其保存为 **MicrosoftCloudDeutschlandAndWorldwide** 名称。</span><span class="sxs-lookup"><span data-stu-id="ab143-149">Save it with the name **MicrosoftCloudDeutschlandAndWorldwide**.</span></span>

5. <span data-ttu-id="ab143-150">当你的租户进行迁移时，请定期验证在各种支持的迁移步骤中 AD FS 身份验证是否与德国 Microsoft 云和 Microsoft 全球云一起运行。</span><span class="sxs-lookup"><span data-stu-id="ab143-150">While your tenant is in migration, regularly verify that AD FS authentication is working with Microsoft Cloud Deutschland and Microsoft Global cloud in the various supported migration steps.</span></span>


## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="ab143-151">AD FS 灾难恢复 (WID 数据库) </span><span class="sxs-lookup"><span data-stu-id="ab143-151">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="ab143-152">若要在灾难中还原 AD FS 场，需使用 [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) 快速还原工具。</span><span class="sxs-lookup"><span data-stu-id="ab143-152">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="ab143-153">因此，必须下载该工具，并且必须在开始迁移之前创建并安全地存储备份。</span><span class="sxs-lookup"><span data-stu-id="ab143-153">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="ab143-154">本示例中，已运行以下命令来备份在 WID 数据库上运行的服务器场：</span><span class="sxs-lookup"><span data-stu-id="ab143-154">In this example, the following commands have been run to back up a farm running on a WID database:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="ab143-155">备份 AD FS 场</span><span class="sxs-lookup"><span data-stu-id="ab143-155">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="ab143-156">在主 AD FS 服务器上安装 AD FS 快速还原工具。</span><span class="sxs-lookup"><span data-stu-id="ab143-156">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>

2. <span data-ttu-id="ab143-157">使用此命令在 PowerShell 会话中导入模块。</span><span class="sxs-lookup"><span data-stu-id="ab143-157">Import the module in a PowerShell session with this command.</span></span>

   ```powershell
   Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
   ```

3. <span data-ttu-id="ab143-158">运行备份命令：</span><span class="sxs-lookup"><span data-stu-id="ab143-158">Run the backup command:</span></span>

   ```powershell
   Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
   ```

4. <span data-ttu-id="ab143-159">将备份安全地存储在所需目标上。</span><span class="sxs-lookup"><span data-stu-id="ab143-159">Store the backup safely on a desired destination.</span></span>


### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="ab143-160">还原 AD FS 场</span><span class="sxs-lookup"><span data-stu-id="ab143-160">Restore an AD FS Farm</span></span>

<span data-ttu-id="ab143-161">如果服务器场完全失败，并且无法返回到旧服务器场，请执行下列操作。</span><span class="sxs-lookup"><span data-stu-id="ab143-161">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="ab143-162">将以前生成的和存储的备份移动到新的主 AD FS 服务器。</span><span class="sxs-lookup"><span data-stu-id="ab143-162">Move the previously generated and stored backup to the new primary AD FS server.</span></span>

2. <span data-ttu-id="ab143-163">运行以下 `Restore-ADFS` PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="ab143-163">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="ab143-164">如有必要，请事先导入 AD FS SSL 证书。</span><span class="sxs-lookup"><span data-stu-id="ab143-164">If necessary, import the AD FS SSL certificate beforehand.</span></span>

   ```powershell
   Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
   ```

3. <span data-ttu-id="ab143-165">将新的 DNS 记录或负载平衡器指向新的 AD FS 服务器。</span><span class="sxs-lookup"><span data-stu-id="ab143-165">Point your new DNS records or load balancer to the new AD FS servers.</span></span>


## <a name="more-information"></a><span data-ttu-id="ab143-166">详细信息</span><span class="sxs-lookup"><span data-stu-id="ab143-166">More information</span></span>

<span data-ttu-id="ab143-167">入门：</span><span class="sxs-lookup"><span data-stu-id="ab143-167">Getting started:</span></span>

- [<span data-ttu-id="ab143-168">从德国 Microsoft 云迁移到新的德国数据中心区域的 Office 365 服务</span><span class="sxs-lookup"><span data-stu-id="ab143-168">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="ab143-169">德国 Microsoft 云迁移助手</span><span class="sxs-lookup"><span data-stu-id="ab143-169">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="ab143-170">如何选择加入迁移</span><span class="sxs-lookup"><span data-stu-id="ab143-170">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="ab143-171">迁移期间客户体验</span><span class="sxs-lookup"><span data-stu-id="ab143-171">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="ab143-172">在转换过程中移动：</span><span class="sxs-lookup"><span data-stu-id="ab143-172">Moving through the transition:</span></span>

- [<span data-ttu-id="ab143-173">迁移阶段操作和影响</span><span class="sxs-lookup"><span data-stu-id="ab143-173">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="ab143-174">其他前期工作</span><span class="sxs-lookup"><span data-stu-id="ab143-174">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="ab143-175">Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。</span><span class="sxs-lookup"><span data-stu-id="ab143-175">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="ab143-176">云应用：</span><span class="sxs-lookup"><span data-stu-id="ab143-176">Cloud apps:</span></span>

- [<span data-ttu-id="ab143-177">Dynamics 365 迁移计划信息</span><span class="sxs-lookup"><span data-stu-id="ab143-177">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="ab143-178">Power BI 迁移计划信息</span><span class="sxs-lookup"><span data-stu-id="ab143-178">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="ab143-179">开始 Microsoft Teams 升级</span><span class="sxs-lookup"><span data-stu-id="ab143-179">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
