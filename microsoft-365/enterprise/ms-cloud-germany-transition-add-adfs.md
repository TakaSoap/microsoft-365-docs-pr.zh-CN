---
title: 从德国 Microsoft 云迁移的 AD FS 迁移步骤
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：Active Directory 联合身份验证 (AD FS) 德国 Microsoft 云迁移的迁移步骤。
ms.openlocfilehash: e2e3d6c80175dc961f65e8f1ce83acce8708c982
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60200001"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>从德国 Microsoft 云迁移的 AD FS 迁移步骤

此配置更改需要在阶段 2 启动之前随时应用。
第 2 阶段完成后，配置更改将正常工作，并且你能够通过全局终结点Office 365登录，例如 `https://admin.microsoft.com` 。 如果在阶段 2 之前实现配置更改，Office 365 全局终结点将不起作用，但新的信赖方信任仍然是 Active Directory 联合身份验证服务 (AD FS) 配置的一部分。

将联合身份验证与 Active Directory 联合身份验证服务 (AD FS) 一同使用的客户不应更改在迁移期间用于本地 Active Directory 域服务 (AD DS) 的所有身份验证的颁发者 URI。 更改颁发者 URI 将导致域中用户的身份验证失败。 可以在 AD FS 中直接更改颁发者 URI，或在将域从托管域转换为联盟域时更改，反之亦然。 建议不要添加、删除或转换已迁移的 Azure AD 租户中的联合域。 完全完成迁移后，可更改颁发者 URI。

若要准备 AD FS 场以从德国 Microsoft 云进行迁移，请执行以下步骤：

1. 按照以下步骤备份 AD FS 设置，包括现有的德国 Microsoft 云信赖 [方信任](#backup)。 将备份 **名称为 MicrosoftCloudDeutschlandOnly** 以指示它仅包含 Microsoft 云德国租户信息。

   > [!NOTE]
   > 备份将不仅包含 Microsoft 云德国Office 365信赖方信任，还包含各自 AD FS 场上存在的所有其他信赖方信任。

2. 使用 MicrosoftCloudDeutschlandOnly 备份测试还原，AD FS 场应继续仅作为德国 Microsoft 云运行。

完成和测试 AD FS 备份后，执行以下步骤以向 ADFS 配置添加新的信赖方信任：

1. 打开 AD FS 管理控制台。

2. 在 ADFS 管理控制台的左侧窗格中，导航到" **信赖方信任"** 菜单。

3. 在右侧窗格中，选择" **添加信赖方信任..."。**

4. 在 **"** 添加信赖 **方信任** "向导的"欢迎"页上选择"开始"。

5. 在"**选择数据源"** 页上，选择"导入有关联机发布的信赖方或本地 **网络的数据"。** 联合 **元数据地址 (主机名或 URL)** 值必须设置为 `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 。 单击“下一步”。

6. 在"**指定显示名称**"页上，键入显示名称 Identity **Platform WorldWide** Microsoft Office 365名称" 。 单击“下一步”。

7. 如果你使用的是 Windows Server 2012 中的 ADFS，请在向导页面"现在配置多重身份验证？"上，根据你的身份验证要求选择相应的选项。 如果坚持使用默认值，请选择"我目前不想为此信赖方信任配置多重 **身份验证设置"。** 如果需要，可以在以后更改此设置。

8. 对于 AD FS 2012：在"**选择颁发授权** 规则"上，保留选中"允许所有用户访问此 **信赖** 方"，然后单击"下一 **步"。**

9. 对于 AD FS 2016 和 AD FS 2019：在"**选择访问控制** 策略"页上，选择相应的访问控制策略，然后单击"下一步 **"。** 如果未选择任何选项，则信赖方信任 **将不起作用** 。

10. 单击 **"** 准备添加 **信任"页上的** "下一步"以完成向导。

11. 单击 **"完成** " **页上的"关闭** "。

通过关闭向导，可建立与全局Office 365信赖方信任。 但是，尚未配置任何颁发转换规则。

可以使用 [AD FS 帮助](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 生成正确的颁发转换规则。 使用 AD FS 帮助创建的生成的声明规则可通过 AD FS 管理控制台手动添加，也可通过 PowerShell 手动添加。 AD FS 帮助将生成需要执行的必要 PowerShell 脚本。  

> [!NOTE]
> [AD FS 帮助](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 将生成随产品一起提供的标准发布转换规则。 但是，如果自定义发布转换规则已位于德国 Microsoft 云信赖方信任 (例如，自定义颁发者 URI、非标准不可变 ID 或其他任何自定义) 中，则必须修改 AD FS 帮助生成的规则，以适合 Microsoft 云德国信赖方信任当前已生成的自定义逻辑。 如果这些自定义项未集成到通过 [AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)帮助生成的规则中，Microsoft Office 365 **Identity Platform WorldWide** 的身份验证很可能对联合身份不起作用。

1. 在 [AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)帮助上运行"生成声明"，然后使用脚本右上角的"复制"选项复制 PowerShell 脚本。

2. 按照 [AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 帮助中概述的步骤操作，了解如何在 AD FS 场中运行 PowerShell 脚本以生成全局信赖方信任。 在运行脚本之前，请替换生成的脚本中的以下代码行，如下所示：

   ```powershell
   # AD FS Help generated value
   $claims = Get-AdfsRelyingPartyTrust -Identifier $(Get-RpIdentifier) | Select-Object IssuanceTransformRules;
   # replace with
   $claims = Get-AdfsRelyingPartyTrust -Identifier urn:federation:MicrosoftOnline | Select-Object IssuanceTransformRules;

   # AD FS Help generated value
   Set-AdfsRelyingPartyTrust -TargetIdentifier $(Get-RpIdentifier) -IssuanceTransformRules $RuleSet.ClaimRulesString;
   # replace with
   Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:MicrosoftOnline -IssuanceTransformRules $RuleSet.ClaimRulesString;
   ```

3. 确认存在两个信赖方Ttrusts;一个针对德国 Microsoft 云，另一个Office 365全球服务。 以下命令可用于检查。 它应返回两行以及各自的名称和标识符。

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. 使用以下步骤备份完整迁移配置，包括信赖方 [信任](#backup)。 将其保存为 **MicrosoftCloudDeutschlandAndWorldwide** 名称。

5. 当你的租户进行迁移时，请定期验证在各种支持的迁移步骤中 AD FS 身份验证是否与德国 Microsoft 云和 Microsoft 全球云一起工作。

## <a name="ad-fs-disaster-recovery-wid-database"></a>AD FS 灾难恢复 (WID 数据库) 

若要在灾难中还原 AD FS 场，需使用 [AD FS](/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) 快速还原工具。 因此，必须下载该工具，并且必须在开始迁移之前创建并安全地存储备份。 本示例中，已运行以下命令来备份在 WID 数据库上运行的服务器场：

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a>备份 AD FS 场

1. 在主 AD FS 服务器上安装 AD FS 快速还原工具。

2. 使用此命令在 PowerShell 会话中导入模块。

   ```powershell
   Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
   ```

3. 运行备份命令：

   ```powershell
   Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
   ```

4. 将备份安全地存储在所需目标上。

### <a name="restore-an-ad-fs-farm"></a>还原 AD FS 场

如果服务器场完全失败，并且无法返回到旧服务器场，请执行下列操作。 

1. 将以前生成的和存储的备份移动到新的主 AD FS 服务器。

2. 运行以下 `Restore-ADFS` PowerShell 命令。 如有必要，请事先导入 AD FS SSL 证书。

   ```powershell
   Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
   ```

3. 将新的 DNS 记录或负载平衡器指向新的 AD FS 服务器。

## <a name="more-information"></a>更多信息

入门：

- [从德国 Microsoft 云迁移到Office 365新的德国数据中心区域部署服务](ms-cloud-germany-transition.md)
- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)
- [迁移期间客户体验](ms-cloud-germany-transition-experience.md)

在转换过程中移动：

- [迁移阶段操作和影响](ms-cloud-germany-transition-phases.md)
- [其他前期工作](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。

云应用：

- [Dynamics 365 迁移计划信息](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 迁移计划信息](/power-bi/admin/service-admin-migrate-data-germany)
- [开始 Microsoft Teams 升级](/microsoftteams/upgrade-start-here)
