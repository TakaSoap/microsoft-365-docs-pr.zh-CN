---
title: 适用于由世纪互联运营的 Office 365 的 Azure 信息保护支持
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: 深入了解适用于由世纪互联运营的 Office 365 的 Azure 信息保护 （AIP） 以及如何为中国客户进行配置。
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535838"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>适用于由世纪互联运营的 Office 365 的 Azure 信息保护支持

本文介绍了 Azure 信息保护 （AIP） 对由世纪互联运营的 Office 365 和商业产品/服务之间的差异，以及为中国&mdash;客户配置 AIP 的详细说明，包括如何安装 AIP 本地扫描仪和管理内容扫描作业。

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>由世纪互联运营的 Office 365 的 AIP 与商业产品之间的差异

我们的目标是通过针对由世纪互联运营的 Office 365 的 AIP 产品，为中国客户提供所有商业特性和功能，但是我们要强调的一些缺失功能。

以下列表包含世纪互联运营的 Office 365 的 AIP 与 2021 年 1 月前的商业产品之间的现有缺陷：

- 仅 Microsoft 365 企业版应用（内部版本 11731.10000 或更高版本）支持信息权限管理 （IRM）。 不支持 Office 2010、Office 2013 和其他 Office 2016 版本。

- 目前无法从 Active Directory 权限管理服务 （AD RMS） 迁移到 AIP。
  
- 支持在商业云中与用户共享受保护的电子邮件。
  
- 目前，不可在商业云中与用户共享文档和电子邮件附件。 这包括商业云中由世纪互联络用户运营的 Office 365、在商业云中由世纪互联用户运营的非 Office 365 用户，以及拥有个人版 RMS 许可证的用户。
  
- 具有 SharePoint（受 IRM 保护的网站和库）的 IRM 当前不可用。
  
- AD RMS 的移动设备扩展当前不可用。

- Azure 中国世纪互联不支持该[手机阅读器](/azure/information-protection/rms-client/mobile-app-faq)。

- Azure 门户的 AIP 区域不可用于中国客户。 使用 [PowerShell](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 命令，而不是在门户中执行操作，如管理和运行内容扫描作业。

## <a name="configure-aip-for-customers-in-china"></a>为中国的客户配置 AIP

为中国的客户配置 AIP：
1. [为租户启用权限](#step-1-enable-rights-management-for-the-tenant)。

1. [添加 Microsoft 信息保护同步服务服务主体](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)。

1. [配置 DNS 加密](#step-3-configure-dns-encryption)。

1. [安装和配置 AIP 统一标签客户端](#step-4-install-and-configure-the-aip-unified-labeling-client)。

1. [在 Windows 桌面应用中配置 AIP](#step-5-configure-aip-apps-on-windows)。

1. [安装 AIP 本地扫描仪和管理内容扫描作业](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>步骤 1：为租户启用权限管理

若要使加密能正常工作，必须为租户启用 RMS。

1. 检查是否已启用 RMS：

    1. 以管理员角色启动 PowerShell。
    2. 如果未安装 AIPService 模块，请运行 `Install-Module AipService`。
    3. 使用 `Import-Module AipService`。
    4. 使用 `Connect-AipService -environmentname azurechinacloud`连接到服务。
    5. 运行 `(Get-AipServiceConfiguration).FunctionalState` ，检查状态是否 `Enabled`。

2. 如果功能状态为 `Disabled`，请运行 `Enable-AipService`。

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a>步骤 2：添加 Microsoft 信息保护同步服务服务主体

默认情况下 **，Microsoft 信息保护同步** 服务服务主体在 Azure 中国租户中不可用，它是 Azure 信息保护的必需项。

1. 使用 [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) cmdlet 和 Microsoft 信息保护同步服务的应用程序 ID 手动创建 `870c4f2e-85b6-4d43-bdda-6ed9a579b725` 此服务主体。 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. 添加服务主体后，向服务添加所需的相关权限。

### <a name="step-3-configure-dns-encryption"></a>步骤 3：配置 DNS 加密

为使加密能正常工作，Office 客户端应用程序必须连接到服务的中国实例并请从其中启动。 若要将客户端应用程序重定向到正确的服务实例，租户管理员必须配置包含 Azure RMS URL 相关信息的 DNS SRV 记录。 如果没有 DNS SRV 记录，客户端应用程序将默认尝试连接到公共云实例，且将失败。

此外，假设用户将会使用基于租户拥有的域（例如 `joe@contoso.cn`）而不是 `onmschina` 用户名（例如 `joe@contoso.onmschina.cn`）登录。 用户名中的域名用于 DNS 重定向到正确的服务实例。

#### <a name="configure-dns-encryption---windows"></a>配置 DNS 加密 - Windows

1. 获取 RMS ID：

    1. 以管理员角色启动 PowerShell。
    2. 如果未安装 AIPService 模块，请运行 `Install-Module AipService`。
    3. 使用 `Connect-AipService -environmentname azurechinacloud`连接到服务。
    4. 运行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 获得 RMS ID。

2. 登录到您的 DNS 提供商，导航到域的 DNS 设置，然后添加新的 SRV 记录。

    - 服务 = `_rmsredir`
    - 协议 = `_http`
    - 名称 = `_tcp`
    - 目标 = `[GUID].rms.aadrm.cn`（其中 GUID 为 RMS ID）
    - 优先级、权重、秒数、TTL = 默认值

3. 将自定义域与 [门户中的租户](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)。 这将在 DNS 中添加条目，这可能需要几分钟时间才能在向 DNS 设置添加该值后进行验证。

4. 使用相应的全局管理员凭据登录 Microsoft 365 管理中心，并添加域（例如， `contoso.cn`）供用户创建。 在验证过程中，可能需要其他 DNS 更改。 验证完成后，可创建用户。

#### <a name="configure-dns-encryption---mac-ios-android"></a>配置 DNS 加密 - Mac、iOS、Android

登录到您的 DNS 提供商，导航到域的 DNS 设置，然后添加新的 SRV 记录。

- 服务 = `_rmsdisco`
- 协议 = `_http`
- 名称 = `_tcp`
- 目标 = `api.aadrm.cn`
- 端口 = `80`
- 优先级、权重、秒数、TTL = 默认值


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a>步骤 4：安装和配置 AIP 统一标记客户端

从 Microsoft 下载中心下载并安装 AIP 统一标签 [客户端](https://www.microsoft.com/download/details.aspx?id=53018)。

有关详细信息，请参阅：

- [AIP 文档](/azure/information-protection/)
- [AIP 版本历史记录和支持策略](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP 系统要求](/azure/information-protection/requirements)
- [AIP 快速入门：部署 AIP 客户端](/azure/information-protection/quickstart-deploy-client)
- [AIP 管理员指南](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP 用户指南](/azure/information-protection/rms-client/clientv2-user-guide)
- [了解 Microsoft 365 敏感度标签](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a>步骤 5：在应用程序上配置 AIP Windows

Windows 上的 AIP 应用需要以下注册表项，用于指向 Azure China 的正确主权云：

- 注册表节点 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- 名称 = `CloudEnvType`
- 值 = `6`（默认 = 0）
- 类型 = `REG_DWORD`

> [!IMPORTANT]
> 请确保卸载后不会删除注册表项。 如果密钥为空、不正确或不存在，则功能将按默认值（商业云的默认值 = 0）运行。 如果密钥为空或不正确，也会向日志添加打印错误。

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>步骤 6：安装 AIP 本地扫描程序并管理内容扫描作业

安装 AIP 本地扫描仪扫描网络和内容共享以访问敏感数据，并按组织策略中配置应用分类和保护标签。

配置和管理内容扫描作业时，请使用以下过程，而不是商业产品/服务使用的 [Azure](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) 门户界面。

有关详细信息，请参阅 [什么是 Azure 信息保护统一标签扫描仪？](/azure/information-protection/deploy-aip-scanner) [PowerShell 管理内容扫描作业](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。

**安装和配置扫描程序**：

1. 登录到将Windows扫描程序的服务器计算机。 使用具有本地管理员权限且有权写入主数据库SQL Server帐户。

1. 从关闭 PowerShell 开始。 如果之前已安装 AIP 客户端和扫描程序，请确保 **AIPScanner** 服务已停止。

1. 使用"Windows PowerShell **管理员"选项打开一个安全会话**。

1. 运行[Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) cmdlet，指定要SQL Server Azure 信息保护扫描程序的数据库的 SQL Server 实例，为扫描程序群集指定有意义的名称。

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > 可以在 [Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) 命令中使用相同的群集名称将多个扫描程序节点关联到同一群集。 通过为多个扫描仪节点使用同一群集，多个扫描仪可协作执行扫描。
    > 

1. 验证现在是否使用管理工具服务 **安装了**  >  **该服务**。

    已安装的服务名为 **Azure 信息保护扫描** 程序，并配置为使用你创建的扫描程序服务帐户运行。

1. 获取 Azure 令牌以与扫描程序一同使用。 Azure AD 令牌允许扫描程序对 Azure 信息保护服务进行身份验证，从而使扫描程序以非交互方式运行。 

    1. 打开 Azure 门户并创建 Azure AD 应用程序以指定用于身份验证的访问令牌。 有关详细信息，请参阅如何针对 Azure 信息保护以非 [交互方式标记文件](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)。
    
        > [!TIP]
        > 为 [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) 命令创建和配置 Azure AD 应用程序时，"**请求 API 权限**"窗格显示 **我的组织使用的API** 选项卡，而不是 **Microsoft API** 选项卡。选择 **使用** 的 API，然后选择 **Azure Rights Management Services 中的**。 
        >

    1. 从 Windows 服务器计算机中，如果扫描程序服务帐户已被授予安装的本地登录权限，请通过此帐户登录并启动 PowerShell 会话。 
    
        如果无法授予扫描程序服务帐户本地登录权限进行安装，请通过 [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)使用 *OnBehalfOf* 参数，如如何为 [Azure](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)信息保护以非交互方式标记文件中所述。

    1. 运行 [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication)，指定从 Azure AD 应用程序复制的值：

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      例如：

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    扫描程序现在具有向 Azure AD 进行身份验证的令牌。 根据 Azure AD 中 Web 应用 **/API** 客户端密码的配置，此令牌的有效期为一年、两年或从不。 当令牌过期时，必须重复此过程。

1. 运行 [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) cmdlet 将扫描程序设置为在脱机模式下运行。 运行：

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. 运行 [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) cmdlet 以创建默认内容扫描作业。

    **Set-AIPScannerContentScanJob** cmdlet 中唯一必需的参数是 **Enforce**。 但是，此时可能需要为内容扫描作业定义其他设置。 例如：

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    上述语法将配置以下设置，同时继续配置：

    - 将扫描程序运行计划保持 *为手动*
    - 设置基于敏感度标签策略要发现的信息类型
    - *不* 强制执行敏感度标签策略
    - 使用为敏感度标签策略定义的默认标签，根据内容自动为文件添加标签
    - *不允许* 重新标记文件
    - 在扫描和自动标记时保留文件详细信息，包括日期修改、上次修改和 *由值修改*
    - 设置扫描程序以在运行时排除 .msg 和 .tmp 文件
    - 将默认所有者设置为运行扫描程序时想要使用的帐户

1. 使用 [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) cmdlet 定义内容扫描作业中要扫描的存储库。 例如，运行：

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    根据要添加的存储库类型，使用以下语法之一：

    - 对于网络共享，请使用 `\\Server\Folder` 。
    - 对于SharePoint库，请使用 `http://sharepoint.contoso.com/Shared%20Documents/Folder` 。
    - 对于本地路径： `C:\Folder`
    - 对于 UNC 路径： `\\Server\Folder`

    > [!NOTE]
    > 不支持通配符，并且不支持 WebDav 位置。
    >
    > 若要稍后修改存储库，请改为使用 [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) cmdlet。 


根据需要继续执行以下步骤：

- [运行发现周期并查看扫描仪报告](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [使用 PowerShell 配置扫描程序以应用分类和保护](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [使用 PowerShell 使用扫描程序配置 DLP 策略](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

下表列出了与安装扫描程序和管理内容扫描作业相关的 PowerShell cmdlet：

| Cmdlet | 说明 |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | 将新的存储库添加到内容扫描作业。 |
| [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|返回有关群集的详细信息。 |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | 获取内容扫描作业的详细信息。 |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | 获取定义用于内容扫描作业的存储库的详细信息。 |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | 删除内容扫描作业。 |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | 从内容扫描作业中删除存储库。 |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | 定义内容扫描作业的设置。 |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | 定义内容扫描作业中现有存储库的设置。 |
| | |

有关详细信息，请参阅：

- [什么是 Azure 信息保护统一标签扫描程序？](/azure/information-protection/deploy-aip-scanner)
- [使用统一标签扫描程序配置 (AIP) Azure 信息保护](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- [仅使用 PowerShell 管理内容扫描作业](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。
