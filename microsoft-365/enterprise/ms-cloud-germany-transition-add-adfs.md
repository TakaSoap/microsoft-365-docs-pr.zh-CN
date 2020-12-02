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
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>从 Microsoft 云德国迁移的 AD FS 迁移步骤

若要从 Microsoft 云德国将 Active Directory 联合身份验证服务 (AD FS) 服务器场迁移，请执行以下操作：

1. 按照 [这些步骤](#backup)备份你的 AD FS 设置，包括 FF 信任信息。 将备份 **Microsoft 云** 命名为 "Deutschland_Only"，以指示它仅具有 Microsoft 云德国租户信息。
2. 使用 Microsoft 云 Deutschland_Only 备份测试还原，AD FS 服务器场应继续作为 Microsoft 云德国运行。
3. 从 **AD FS > Office 365 服务** 创建新的信赖方信任。
4. 在 AD FS 管理控制台中的 " **信赖方信任** " 中，选择 " **添加信赖方信任**"。
5. 在 "添加信赖方信任向导" 的 "**欢迎**" 页上选择 "**下一步**"。
6. 在 " **选择数据源** " 页上，选择 **"导入有关联机或在本地网络上发布的信赖方的数据**"。 **(主机名或 URL) 值的联合身份验证元数据地址** 设置为 `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 。 单击“**下一步**”。
7. 在 " **选择数据源** " 页上，键入显示名称。 Microsoft 建议 **全球范围内的 Microsoft Office 365 Identity Platform**。 单击“**下一步**”。
8. 在 "**现在配置多重身份验证"** 中单击 "**下一步**"，**选择 "颁发授权规则**"，并 **准备好添加信任** 页面。
9. 在 "**完成**" 页上单击 "**关闭**"。

通过关闭向导，将建立对 Office 365 services eSTS 的信赖方信任。 但是，不会建立任何颁发转换规则。

您可以使用 [AD FS 帮助](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 生成正确的颁发转换规则。 可以通过 AD FS 管理控制台或 PowerShell 手动添加通过 AD FS 帮助创建的生成的声明规则。 AD FS 帮助将生成需要运行的必要 PowerShell 脚本。  

1. 运行 "在 AD FS 帮助中 **生成声明** "，并使用脚本右侧的 " **复制** " 选项复制 PowerShell 声明转换脚本。
2. 将生成的 PowerShell 粘贴到以下内容中：

  ```powershell
  $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
  Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString;
  ```
3.  执行已完成的脚本。
4.  验证是否存在两个依赖方信任;一个用于全球，一个用于 BF。
5.  使用 [以下步骤](#backup)备份你的信任。 使用名称 **FFAndWorldwide** 保存它。
6.  完成后端迁移并验证 AD FS 在迁移过程中是否仍然有效。

## <a name="ad-fs-disaster-recovery-wid-database"></a> (WID 数据库) 的 AD FS 灾难恢复

若要在灾难 [AD Fs 快速还原工具](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) 中还原 AD fs 服务器场，需要利用此工具。 因此，必须下载该工具，并且在开始迁移之前，必须创建并安全地存储备份。 在此示例中 (TAT 环境) 已运行以下命令来备份服务器场：

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>备份 AD FS 服务器场

1. 在主 AD FS 服务器上安装 AD FS 快速还原工具。
2. 使用此命令在 PowerShell 会话中导入模块。

  ```powershell
  Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
  ```
3. 运行 "备份" 命令：

  ```powershell
  Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
  ```

4. 将备份安全地存储在所需的目标上。 

### <a name="restore-an-ad-fs-farm"></a>还原 AD FS 服务器场

如果您的服务器场完全失败，并且无法返回到旧的服务器场，请执行以下操作。 

1. 将以前生成和存储的备份移动到新的主 AD FS 服务器。
2. 运行以下 `Restore-ADFS` PowerShell 命令。 如有必要，请事先导入 AD FS SSL 证书。

  ```powershell
  Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
  ```

3. 将新的 DNS 记录或负载平衡器指向新的 AD FS 服务器。

## <a name="more-information"></a>详细信息

入门：

- [从 Microsoft 云德国迁移到新的德国数据中心区域中的 Office 365 服务](ms-cloud-germany-transition.md)
- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)
- [迁移过程中的客户体验](ms-cloud-germany-transition-experience.md)

在转换中移动：

- [迁移阶段的操作和影响](ms-cloud-germany-transition-phases.md)
- [其他预备工作](ms-cloud-germany-transition-add-pre-work.md)
- [服务](ms-cloud-germany-transition-add-general.md)、[设备](ms-cloud-germany-transition-add-devices.md)、[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS](ms-cloud-germany-transition-add-adfs.md)的其他信息。

云应用：

- [Dynamics 365 迁移计划信息](https://aka.ms/d365ceoptin)
- [Power BI 迁移计划信息](https://aka.ms/pbioptin)
- [开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)
