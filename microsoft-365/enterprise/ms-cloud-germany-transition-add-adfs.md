---
title: 从 Microsoft 云德国迁移的 AD FS 迁移步骤
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
description: 摘要： Active Directory 联合身份验证服务 (AD FS) 从 Microsoft 云德国迁移的迁移步骤。
ms.openlocfilehash: 175734851c2838eb2e224a9afb57a600d4ed9523
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49554786"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="f2751-103">从 Microsoft 云德国迁移的 AD FS 迁移步骤</span><span class="sxs-lookup"><span data-stu-id="f2751-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="f2751-104">若要从 Microsoft 云德国将 Active Directory 联合身份验证服务 (AD FS) 服务器场迁移，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f2751-104">To migrate your Active Directory Federation Services (AD FS) farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="f2751-105">按照 [这些步骤](#backup)备份你的 AD FS 设置，包括 FF 信任信息。</span><span class="sxs-lookup"><span data-stu-id="f2751-105">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="f2751-106">将备份 **Microsoft 云** 命名为 "Deutschland_Only"，以指示它仅具有 Microsoft 云德国租户信息。</span><span class="sxs-lookup"><span data-stu-id="f2751-106">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="f2751-107">使用 Microsoft 云 Deutschland_Only 备份测试还原，AD FS 服务器场应继续作为 Microsoft 云德国运行。</span><span class="sxs-lookup"><span data-stu-id="f2751-107">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>
3. <span data-ttu-id="f2751-108">从 **AD FS > Office 365 服务** 创建新的信赖方信任。</span><span class="sxs-lookup"><span data-stu-id="f2751-108">Create a new Relying Party trust from **AD FS >  Office 365 services**.</span></span>
4. <span data-ttu-id="f2751-109">在 AD FS 管理控制台中的 " **信赖方信任** " 中，选择 " **添加信赖方信任**"。</span><span class="sxs-lookup"><span data-stu-id="f2751-109">In **Relying Party Trusts** in the AD FS management console, select **Add Relying Party Trust**.</span></span>
5. <span data-ttu-id="f2751-110">在 "添加信赖方信任向导" 的 "**欢迎**" 页上选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f2751-110">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
6. <span data-ttu-id="f2751-111">在 " **选择数据源** " 页上，选择 **"导入有关联机或在本地网络上发布的信赖方的数据**"。</span><span class="sxs-lookup"><span data-stu-id="f2751-111">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="f2751-112">**(主机名或 URL) 值的联合身份验证元数据地址** 设置为 `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 。</span><span class="sxs-lookup"><span data-stu-id="f2751-112">The **Federation metadata address (host name or URL)** value is set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="f2751-113">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="f2751-113">Click **Next**.</span></span>
7. <span data-ttu-id="f2751-114">在 " **选择数据源** " 页上，键入显示名称。</span><span class="sxs-lookup"><span data-stu-id="f2751-114">On the **Select Data Source** page, type the display name.</span></span> <span data-ttu-id="f2751-115">Microsoft 建议 **全球范围内的 Microsoft Office 365 Identity Platform**。</span><span class="sxs-lookup"><span data-stu-id="f2751-115">Microsoft recommends **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="f2751-116">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="f2751-116">Click **Next**.</span></span>
8. <span data-ttu-id="f2751-117">在 "**现在配置多重身份验证"** 中单击 "**下一步**"，**选择 "颁发授权规则**"，并 **准备好添加信任** 页面。</span><span class="sxs-lookup"><span data-stu-id="f2751-117">Click **Next** on the **Configure Multi-factor Authentication Now?**, **Choose Issuance Authorization Rules**, and **Ready to Add Trust** pages.</span></span>
9. <span data-ttu-id="f2751-118">在 "**完成**" 页上单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="f2751-118">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="f2751-119">通过关闭向导，将建立对 Office 365 services eSTS 的信赖方信任。</span><span class="sxs-lookup"><span data-stu-id="f2751-119">By closing the wizard, the Relying Party Trust to the Office 365 services eSTS is established.</span></span> <span data-ttu-id="f2751-120">但是，不会建立任何颁发转换规则。</span><span class="sxs-lookup"><span data-stu-id="f2751-120">However, no Issuance Transform rules are established.</span></span>

<span data-ttu-id="f2751-121">您可以使用 [AD FS 帮助](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 生成正确的颁发转换规则。</span><span class="sxs-lookup"><span data-stu-id="f2751-121">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="f2751-122">可以通过 AD FS 管理控制台或 PowerShell 手动添加通过 AD FS 帮助创建的生成的声明规则。</span><span class="sxs-lookup"><span data-stu-id="f2751-122">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="f2751-123">AD FS 帮助将生成需要运行的必要 PowerShell 脚本。</span><span class="sxs-lookup"><span data-stu-id="f2751-123">AD FS Help will generate the necessary PowerShell scripts that need to be run.</span></span>  

1. <span data-ttu-id="f2751-124">运行 "在 AD FS 帮助中 **生成声明** "，并使用脚本右侧的 " **复制** " 选项复制 PowerShell 声明转换脚本。</span><span class="sxs-lookup"><span data-stu-id="f2751-124">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="f2751-125">将生成的 PowerShell 粘贴到以下内容中：</span><span class="sxs-lookup"><span data-stu-id="f2751-125">Paste the generated PowerShell into the following:</span></span>

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  <span data-ttu-id="f2751-126">执行已完成的脚本。</span><span class="sxs-lookup"><span data-stu-id="f2751-126">Execute the completed script.</span></span>
4.  <span data-ttu-id="f2751-127">验证是否存在两个依赖方信任;一个用于全球，一个用于 BF。</span><span class="sxs-lookup"><span data-stu-id="f2751-127">Verify that two Relying Party trusts are present; one for worldwide and one for BF.</span></span>
5.  <span data-ttu-id="f2751-128">使用 [以下步骤](#backup)备份你的信任。</span><span class="sxs-lookup"><span data-stu-id="f2751-128">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="f2751-129">使用名称 **FFAndWorldwide** 保存它。</span><span class="sxs-lookup"><span data-stu-id="f2751-129">Save it with the name **FFAndWorldwide**.</span></span>
6.  <span data-ttu-id="f2751-130">完成后端迁移并验证 AD FS 在迁移过程中是否仍然有效。</span><span class="sxs-lookup"><span data-stu-id="f2751-130">Complete your backend migration and verify that AD FS still works during migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="f2751-131"> (WID 数据库) 的 AD FS 灾难恢复</span><span class="sxs-lookup"><span data-stu-id="f2751-131">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="f2751-132">若要在灾难 [AD Fs 快速还原工具](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) 中还原 AD fs 服务器场，需要利用此工具。</span><span class="sxs-lookup"><span data-stu-id="f2751-132">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="f2751-133">因此，必须下载该工具，并且在开始迁移之前，必须创建并安全地存储备份。</span><span class="sxs-lookup"><span data-stu-id="f2751-133">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="f2751-134">在此示例中 (TAT 环境) 已运行以下命令来备份服务器场：</span><span class="sxs-lookup"><span data-stu-id="f2751-134">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="f2751-135">备份 AD FS 服务器场</span><span class="sxs-lookup"><span data-stu-id="f2751-135">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="f2751-136">在主 AD FS 服务器上安装 AD FS 快速还原工具。</span><span class="sxs-lookup"><span data-stu-id="f2751-136">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="f2751-137">使用此命令在 PowerShell 会话中导入模块。</span><span class="sxs-lookup"><span data-stu-id="f2751-137">Import the module in a PowerShell session with this command.</span></span>

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. <span data-ttu-id="f2751-138">运行 "备份" 命令：</span><span class="sxs-lookup"><span data-stu-id="f2751-138">Run the backup command:</span></span>

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. <span data-ttu-id="f2751-139">将备份安全地存储在所需的目标上。</span><span class="sxs-lookup"><span data-stu-id="f2751-139">Store the backup safely on a desired destination.</span></span> 

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="f2751-140">还原 AD FS 服务器场</span><span class="sxs-lookup"><span data-stu-id="f2751-140">Restore an AD FS Farm</span></span>

<span data-ttu-id="f2751-141">如果您的服务器场完全失败，并且无法返回到旧的服务器场，请执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="f2751-141">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="f2751-142">将以前生成和存储的备份移动到新的主 AD FS 服务器。</span><span class="sxs-lookup"><span data-stu-id="f2751-142">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="f2751-143">运行以下 `Restore-ADFS` PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="f2751-143">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="f2751-144">如有必要，请事先导入 AD FS SSL 证书。</span><span class="sxs-lookup"><span data-stu-id="f2751-144">If necessary, import the AD FS SSL certificate beforehand.</span></span>

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. <span data-ttu-id="f2751-145">将新的 DNS 记录或负载平衡器指向新的 AD FS 服务器。</span><span class="sxs-lookup"><span data-stu-id="f2751-145">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="f2751-146">详细信息</span><span class="sxs-lookup"><span data-stu-id="f2751-146">More information</span></span>

<span data-ttu-id="f2751-147">入门：</span><span class="sxs-lookup"><span data-stu-id="f2751-147">Getting started:</span></span>

- [<span data-ttu-id="f2751-148">从 Microsoft 云德国迁移到新的德国数据中心区域中的 Office 365 服务</span><span class="sxs-lookup"><span data-stu-id="f2751-148">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="f2751-149">德国 Microsoft 云迁移助手</span><span class="sxs-lookup"><span data-stu-id="f2751-149">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="f2751-150">如何选择加入迁移</span><span class="sxs-lookup"><span data-stu-id="f2751-150">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="f2751-151">迁移过程中的客户体验</span><span class="sxs-lookup"><span data-stu-id="f2751-151">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="f2751-152">在转换中移动：</span><span class="sxs-lookup"><span data-stu-id="f2751-152">Moving through the transition:</span></span>

- [<span data-ttu-id="f2751-153">迁移阶段的操作和影响</span><span class="sxs-lookup"><span data-stu-id="f2751-153">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="f2751-154">其他预备工作</span><span class="sxs-lookup"><span data-stu-id="f2751-154">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="f2751-155">[服务](ms-cloud-germany-transition-add-general.md)、[设备](ms-cloud-germany-transition-add-devices.md)、[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他信息。</span><span class="sxs-lookup"><span data-stu-id="f2751-155">Additional information for [services](ms-cloud-germany-transition-add-general.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="f2751-156">云应用：</span><span class="sxs-lookup"><span data-stu-id="f2751-156">Cloud apps:</span></span>

- [<span data-ttu-id="f2751-157">Dynamics 365 迁移计划信息</span><span class="sxs-lookup"><span data-stu-id="f2751-157">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="f2751-158">Power BI 迁移计划信息</span><span class="sxs-lookup"><span data-stu-id="f2751-158">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="f2751-159">开始 Microsoft Teams 升级</span><span class="sxs-lookup"><span data-stu-id="f2751-159">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
