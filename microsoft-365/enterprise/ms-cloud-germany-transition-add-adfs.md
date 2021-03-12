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
ms.openlocfilehash: 030515227f3abdae82736807a01d1691d2d45552
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727463"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a>从德国 Microsoft 云迁移的 AD FS 迁移步骤

可以在阶段 4 开始之前随时应用此配置更改。
阶段 2 完成后，配置更改将正常工作，并且你可以登录到 Office 365 全局终结点，例如 `https://portal.office.com` 。 如果在阶段 2 之前实现配置更改，Office 365 全局终结点将尚不起作用，但新的信赖方信任仍然是 Active Directory 联合身份验证服务 (AD FS) 配置的一部分。

若要从德国 Microsoft 云迁移 AD FS 场，请运行：

1. 按照以下步骤备份 AD FS 设置，包括 FF [信任信息](#backup)。 将备份 **Microsoft 云Deutschland_Only，** 以指示它仅包含德国 Microsoft 云租户信息。
2. 使用 Microsoft 云备份Deutschland_Only还原，AD FS 场应继续仅作为德国 Microsoft 云运行。

完成和测试 AD FS 备份后，执行以下步骤以向 ADFS 配置添加新的信赖方信任：

1. 打开 AD FS 管理控制台
2. 在 ADFS 管理控制台的左侧窗格中，展开 **"ADFS"，** 然后" **信任** 关系"，然后" **信赖方信任"**
3. 在右侧窗格中，选择" **添加信赖方信任..."。**
4. 在 **"** 添加信赖 **方信任"** 向导的"欢迎"页上选择"下一步"。
5. 在"**选择数据源"** 页上，选择"导入有关联机发布的信赖方或本地 **网络的数据"。** 联合 **元数据地址 (主机名或 URL**) 的值必须设置为 `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` 。 然后单击“**下一步**”。
6. 在" **选择数据源"** 页上，键入 显示名称，Microsoft Office **365 Identity Platform WorldWide**。 然后单击“**下一步**”。
7. 在向导页面" **现在配置多重** 身份验证？"上，根据你的身份验证要求选择相应的选项。 如果坚持使用默认值，请选择"我目前不想为此信赖方信任配置多重 **身份验证设置"。** 如果需要，可以在以后更改此设置。
8. 在" **选择颁发授权规则**"上，保留 **"允许所有用户访问此信赖方** "选中"下一步 **"**
9. 单击 **"** 准备添加 **信任"页上** 的"下一步"以完成向导。
10. 单击 **"完成** " **页上的"关闭** "。

通过关闭向导，将建立与 Office 365 全局服务之间的信赖方信任。 但是，尚未配置任何颁发转换规则。

可以使用 [AD FS 帮助](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) 生成正确的颁发转换规则。 使用 AD FS 帮助创建的生成的声明规则可通过 AD FS 管理控制台手动添加，也可通过 PowerShell 手动添加。 AD FS 帮助将生成需要执行的必要 PowerShell 脚本。  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. 在 AD FS 上运行"生成声明"帮助，然后使用脚本右上角的"复制"选项复制 PowerShell 声明转换脚本。
2. 打开首选文本编辑器，将 PowerShell 脚本粘贴到新的文本窗口中。
3. 将以下 PowerShell 行添加到步骤 2 中粘贴脚本的末尾
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. 安全并执行 PowerShell 脚本。
5. 验证存在两个信赖方信任;一个适用于德国 Microsoft 云，另一个适用于 Office 365 全球服务。
6. 使用以下步骤备份 [信任](#backup)。 将其保存为 **FFAndWorldwide** 名称。
7. 完成后端迁移并验证 AD FS 在迁移过程中是否仍正常工作。

## <a name="ad-fs-disaster-recovery-wid-database"></a>AD FS 灾难恢复 (WID 数据库) 

若要在灾难中还原 AD FS 场，需使用 [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) 快速还原工具。 因此，必须下载该工具，并且必须在开始迁移之前创建并安全地存储备份。 此示例中 (运行) 运行以下命令来备份服务器场的 TAT 环境：

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

- [从德国 Microsoft 云迁移到新的德国数据中心区域的 Office 365 服务](ms-cloud-germany-transition.md)
- [德国 Microsoft 云迁移助手](https://aka.ms/germanymigrateassist)
- [如何选择加入迁移](ms-cloud-germany-migration-opt-in.md)
- [迁移期间客户体验](ms-cloud-germany-transition-experience.md)

在转换过程中移动：

- [迁移阶段操作和影响](ms-cloud-germany-transition-phases.md)
- [其他前期工作](ms-cloud-germany-transition-add-pre-work.md)
- Azure [AD、](ms-cloud-germany-transition-azure-ad.md)[设备、](ms-cloud-germany-transition-add-devices.md)[体验](ms-cloud-germany-transition-add-experience.md)和[AD FS 的其他信息](ms-cloud-germany-transition-add-adfs.md)。

云应用：

- [Dynamics 365 迁移计划信息](https://aka.ms/d365ceoptin)
- [Power BI 迁移计划信息](https://aka.ms/pbioptin)
- [开始 Microsoft Teams 升级](https://aka.ms/SkypeToTeams-Home)
