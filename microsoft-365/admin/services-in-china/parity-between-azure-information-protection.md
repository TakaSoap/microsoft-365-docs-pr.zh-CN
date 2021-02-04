---
title: 由世纪银行运营的 Office 365 的 Azure 信息保护支持
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
description: 了解有关由世纪 (运营的 Office 365 的 Azure 信息保护) AIP 服务以及如何为中国客户配置它。
monikerRange: o365-21vianet
ms.openlocfilehash: 300e7633237511fb9de64199ae7cf54594f2239e
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099674"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>由世纪银行运营的 Office 365 的 Azure 信息保护支持

本文介绍了 Azure 信息保护 (AIP) 对由世纪银行运营的 Office 365 和商业产品/服务的支持之间的差异，以及为中国客户配置 AIP 的详细说明，包括如何安装 AIP 本地扫描程序和管理内容扫描作业。 &mdash;

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>由世纪银行运营的 Office 365 的 AIP 与商业产品/服务之间的差异

虽然我们的目标是通过由世纪银行运营的 Office 365 的 AIP 产品/服务，为中国客户提供所有商业特性和功能，但还有一些缺少的功能需要我们重点介绍。

以下列表包括世纪银行运营的 Office 365 的 AIP 与自 2021 年 1 月开始的商业产品/服务之间的现有差异：

- 信息权限 (IRM) 仅适用于 Microsoft 365 企业应用版 (版本 11731.10000 或更高版本) 。 不支持 Office 2010、Office 2013 和其他 Office 2016 版本。

- 目前Active Directory Rights Management Services (AD RMS) AIP 的迁移不可用。
  
- 支持与商业云中的用户共享受保护的电子邮件。
  
- 目前，无法与商业云中的用户共享文档和电子邮件附件。 这包括由商业云中的世纪版用户运营的 Office 365、由商业云中的世纪银行运营的非 Office 365 用户和拥有 RMS 个人版许可证的用户。
  
- SharePoint 的 IRM (受 IRM 保护的网站和) 目前不可用。
  
- AD RMS 的移动设备扩展当前不可用。

- Azure [China](/azure/information-protection/rms-client/mobile-app-faq) 21Vianet 不支持移动查看器。

- Azure 门户的 AIP 区域在中国客户无法使用。 使用 [PowerShell](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 命令，而不是在门户中执行诸如安装本地扫描程序和管理内容扫描作业等操作。

## <a name="configure-aip-for-customers-in-china"></a>为中国客户配置 AIP

为中国客户配置 AIP：
1. [为租户启用权限管理](#step-1-enable-rights-management-for-the-tenant)。

2. [配置 DNS 加密](#step-2-configure-dns-encryption)。

3. [安装和配置 AIP 统一标签客户端](#step-3-install-and-configure-the-aip-unified-labeling-client)。

4. [在 Windows 上配置 AIP 应用](#step-4-configure-aip-apps-on-windows)。

5. [安装 AIP 本地扫描程序并管理内容扫描作业](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs)。 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>步骤 1：为租户启用权限管理

若要使加密正常工作，必须为租户启用 RMS。

1. 检查 RMS 是否已启用：

    1. 以管理员角色启动 PowerShell。
    2. 如果未安装 AIPService 模块，请运行 `Install-Module AipService` 。
    3. 使用 导入模块 `Import-Module AipService` 。
    4. 使用 连接到服务 `Connect-AipService -environmentname azurechinacloud` 。
    5. 运行 `(Get-AipServiceConfiguration).FunctionalState` 并检查状态是否 `Enabled` 。

2. 如果功能状态为 `Disabled` ，则运行 `Enable-AipService` 。

### <a name="step-2-configure-dns-encryption"></a>步骤 2：配置 DNS 加密

若要使加密正常工作，Office 客户端应用程序必须连接到服务的中国实例，然后从该实例启动。 若要将客户端应用程序重定向到正确的服务实例，租户管理员必须使用有关 Azure RMS URL 的信息配置 DNS SRV 记录。 如果没有 DNS SRV 记录，客户端应用程序将默认尝试连接到公共云实例，并且将失败。

此外，假定用户使用基于租户拥有域的用户名登录 (例如，) ，而不是用户名 (`joe@contoso.cn` `onmschina` 例如 `joe@contoso.onmschina.cn` ，) 。 用户名中的域名用于将 DNS 重定向到正确的服务实例。

#### <a name="configure-dns-encryption---windows"></a>配置 DNS 加密 - Windows

1. 获取 RMS ID：

    1. 以管理员角色启动 PowerShell。
    2. 如果未安装 AIPService 模块，请运行 `Install-Module AipService` 。
    3. 使用 连接到服务 `Connect-AipService -environmentname azurechinacloud` 。
    4. 运行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 以获取 RMS ID。

2. 登录到 DNS 提供程序，导航到域的 DNS 设置，然后添加新的 SRV 记录。

    - 服务 = `_rmsredir`
    - 协议 = `_http`
    - Name = `_tcp`
    - 目标 = `[GUID].rms.aadrm.cn` (GUID 是 RMS ID) 
    - Priority、Weight、Seconds、TTL = 默认值

3. 将自定义域与 Azure 门户中的 [租户关联](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)。 这会在 DNS 中添加条目，在将值添加到 DNS 设置后，可能需要几分钟时间才能进行验证。

4. 使用相应的全局管理员凭据登录到 Microsoft 365 管理中心，并添加域 (例如，) `contoso.cn` 用户创建。 在验证过程中，可能需要进行其他 DNS 更改。 验证完成后，可创建用户。

#### <a name="configure-dns-encryption---mac-ios-android"></a>配置 DNS 加密 - Mac、iOS、Android

登录到 DNS 提供程序，导航到域的 DNS 设置，然后添加新的 SRV 记录。

- 服务 = `_rmsdisco`
- 协议 = `_http`
- Name = `_tcp`
- 目标 = `api.aadrm.cn`
- 端口 = `80`
- Priority、Weight、Seconds、TTL = 默认值

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>步骤 3：安装和配置 AIP 统一标记客户端

从 Microsoft 下载中心下载 AIP 统一标签 [客户端](https://www.microsoft.com/download/details.aspx?id=53018)。

有关详细信息，请参阅：

- [AIP 文档](/azure/information-protection/)
- [AIP 版本历史记录和支持策略](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [AIP 系统要求](/azure/information-protection/requirements)
- [AIP 快速入门：部署 AIP 客户端](/azure/information-protection/quickstart-deploy-client)
- [AIP 管理员指南](/azure/information-protection/rms-client/clientv2-admin-guide)
- [AIP 用户指南](/azure/information-protection/rms-client/clientv2-user-guide)
- [了解 Microsoft 365 敏感度标签](/microsoft-365/compliance/sensitivity-labels)

### <a name="step-4-configure-aip-apps-on-windows"></a>步骤 4：在 Windows 上配置 AIP 应用

Windows 上的 AIP 应用需要以下注册表项来将它们指向适用于 Azure China 的正确主云：

- 注册表节点 = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Name = `CloudEnvType`
- 值 = `6` (默认值 = 0) 
- Type = `REG_DWORD`

> [!IMPORTANT]
> 确保在卸载后不删除注册表项。 如果密钥为空、不正确或不存在，则该功能的行为将为默认值 (默认值 = 0，用于商业云) 。 如果键为空或不正确，也会向日志中添加打印错误。

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>步骤 5：安装 AIP 本地扫描程序和管理内容扫描作业

安装 AIP 本地扫描程序以扫描网络和内容共享中的敏感数据，并应用组织策略中配置的分类和保护标签。

安装扫描程序和管理内容扫描作业时，请使用以下 cmdlet，而不是商业产品/服务使用的 Azure 门户界面：<br><br>

| Cmdlet | 说明 |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | 向内容扫描作业添加新存储库。 |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | 获取有关内容扫描作业的详细信息。 |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | 获取为内容扫描作业定义的存储库的详细信息。 |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | 删除内容扫描作业。 |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | 从内容扫描作业中删除存储库。 |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | 定义内容扫描作业的设置。 |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | 定义内容扫描作业中现有存储库的设置。 |

有关详细信息，请参阅什么是 [Azure 信息保护统一标签扫描程序？](/azure/information-protection/deploy-aip-scanner) 以及仅使用 [PowerShell 管理内容扫描作业](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)。
