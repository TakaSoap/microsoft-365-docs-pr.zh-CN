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
ms.openlocfilehash: 300e7633237511fb9de64199ae7cf54594f2239e
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099674"
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

- Azure 门户的 AIP 区域不可用于中国客户。 使用 [PowerShell 命令](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) ，而不在门户中执行操作，如安装本地扫描仪和管理内容扫描作业。

## <a name="configure-aip-for-customers-in-china"></a>为中国的客户配置 AIP

为中国的客户配置 AIP：
1. [为租户启用权限](#step-1-enable-rights-management-for-the-tenant)。

2. [配置 DNS 加密](#step-2-configure-dns-encryption)。

3. [安装和配置 AIP 统一标签客户端](#step-3-install-and-configure-the-aip-unified-labeling-client)。

4. [在 Windows 桌面应用中配置 AIP](#step-4-configure-aip-apps-on-windows)。

5. [安装 AIP 本地扫描仪和管理内容扫描作业](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>步骤 1：为租户启用权限管理

若要使加密能正常工作，必须为租户启用 RMS。

1. 检查是否已启用 RMS：

    1. 以管理员角色启动 PowerShell。
    2. 如果未安装 AIPService 模块，请运行 `Install-Module AipService`。
    3. 使用 `Import-Module AipService`。
    4. 使用 `Connect-AipService -environmentname azurechinacloud`连接到服务。
    5. 运行 `(Get-AipServiceConfiguration).FunctionalState` ，检查状态是否 `Enabled`。

2. 如果功能状态为 `Disabled`，请运行 `Enable-AipService`。

### <a name="step-2-configure-dns-encryption"></a>步骤 2：配置 DNS 加密

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

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>步骤 3：安装和配置 AIP 统一标签客户端

从 Microsoft 下载中心或 [AIP 统一标签](https://www.microsoft.com/download/details.aspx?id=53018)。

有关详细信息，请参阅：

- [AIP 文档](/azure/information-protection/)
- [AIP 版本历史记录和支持策略](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP 系统要求](/azure/information-protection/requirements)
- [AIP 快速入门：部署 AIP 客户端](/azure/information-protection/quickstart-deploy-client)
- [AIP 管理员指南](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP 用户指南](/azure/information-protection/rms-client/clientv2-user-guide)
- [了解 Microsoft 365 敏感度标签](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a>步骤 4：在 Windows 上配置 AIP 应用

Windows 上的 AIP 应用需要以下注册表项，用于指向 Azure China 的正确主权云：

- 注册表节点 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- 名称 = `CloudEnvType`
- 值 = `6`（默认 = 0）
- 类型 = `REG_DWORD`

> [!IMPORTANT]
> 请确保卸载后不会删除注册表项。 如果密钥为空、不正确或不存在，则功能将按默认值（商业云的默认值 = 0）运行。 如果密钥为空或不正确，也会向日志添加打印错误。

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>步骤 5：安装 AIP 本地扫描仪和管理内容扫描作业

安装 AIP 本地扫描仪扫描网络和内容共享以访问敏感数据，并按组织策略中配置应用分类和保护标签。

安装扫描仪和管理内容扫描作业时，请使用以下 cmdlet，而不是商业产品使用的 Azure 门户界面：<br><br>

| Cmdlet | 说明 |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | 将新的存储库添加到内容扫描作业。 |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | 获取内容扫描作业的详细信息。 |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | 获取定义用于内容扫描作业的存储库的详细信息。 |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | 删除内容扫描作业。 |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | 从内容扫描作业中删除存储库。 |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | 定义内容扫描作业的设置。 |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | 定义内容扫描作业中现有存储库的设置。 |

有关详细信息，请参阅 [什么是 Azure 信息保护统一标签扫描仪？](/azure/information-protection/deploy-aip-scanner) [PowerShell 管理内容扫描作业](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。
