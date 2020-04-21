---
title: 由世纪互联运营的 Office 365
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- MET150
- GEU150
- GEA150
description: 了解有关由世纪互联运营的 Office 365 的 Azure 信息保护以及如何为中国的客户配置它的详细信息。
monikerRange: o365-21vianet
ms.openlocfilehash: 3d24b450cc9ba9a6427732d408e35af1394b4a34
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627650"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>由世纪互联运营的 Office 365 的 Azure 信息保护与商业产品之间的奇偶校验

虽然我们的目标是使用由世纪互联运营的 Office 365 的 Azure 信息保护为中国的客户提供所有商业特性和功能，但我们仍需要突出显示一些缺少的功能。

这些是由世纪互联运营的 Office 365 的 Azure 信息保护与年7月2019的商业产品的现有差距：

- 仅适用于企业版（内部版本11731.10000 或更高版本）的 Microsoft 365 应用程序支持信息权限管理（IRM）。 Office 2010、Office 2013 和其他 Office 2016 版本不受支持。

- 从 Active Directory 权限管理服务（AD RMS）到 Azure 信息保护的迁移目前不可用。
  
- 支持将受保护的电子邮件共享到商业云中的用户。
  
- 商业云中用户的文档和电子邮件附件共享目前不可用。 这包括由商业云中由世纪互联用户运营的 Office 365、商业云中由世纪互联用户运营的非 Office 365 以及拥有 RMS for 个人许可证的用户。
  
- 具有 SharePoint 的 IRM （受 IRM 保护的网站和库）当前不可用。
  
- 权限管理连接器当前不可用。
  
- AD RMS 的移动设备扩展目前不可用。

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>为中国的客户配置 Azure 信息保护

### <a name="enable-rights-management-for-the-tenant"></a>为租户启用权限管理

为使加密正常工作，必须为租户启用 RMS。

- 检查是否已启用 RMS：
  1. 以管理员身份启动 PowerShell。
  2. 如果未安装 AIPService 模块，请运行 `Install-Module AipService`。
  3. 使用`Import-Module AipService`导入模块。
  4. 使用 `Connect-AipService -environmentname azurechinacloud`连接到服务。
  5. 运行 `(Get-AipServiceConfiguration).FunctionalState` 并检查状态是否为 `Enabled`。

- 如果功能状态为 `Disabled`，则运行 `Enable-AipService`。

### <a name="dns-configuration-for-encryption-windows"></a>用于加密的 DNS 配置（Windows）

若要使加密正常工作，Office 客户端应用程序必须连接到服务的中国实例，并从那里启动引导。 若要将客户端应用程序重定向到正确的服务实例，租户管理员必须使用有关 Azure RMS URL 的信息配置 DNS SRV 记录。 如果没有 DNS SRV 记录，客户端应用程序将在默认情况下尝试连接到公共云实例，并将失败。

此外，假定用户将使用基于租户拥有的域的用户名登录（例如， `joe@contoso.cn`），而不是`onmschina`用户名（例如， `joe@contoso.onmschina.cn`）。 用户名中的域名用于将 DNS 重定向到正确的服务实例。

- 获取 RMS ID：
  1. 以管理员身份启动 PowerShell。
  2. 如果未安装 AIPService 模块，请运行 `Install-Module AipService`。
  3. 使用 `Connect-AipService -environmentname azurechinacloud`连接到服务。
  4. 运行 `(Get-AipServiceConfiguration).RightsManagementServiceId` 以获取 RMS ID。

- 登录到您的 DNS 提供商，导航到域的 DNS 设置，然后添加新的 SRV 记录。
  - 服务 = `_rmsredir`
  - 协议 = `_http`
  - 名称 = `_tcp`
  - Target = `[GUID].rms.aadrm.cn` （其中 GUID 是 RMS ID）
  - 优先级、权重、秒、TTL = 默认值

- 将自定义域与 [Azure 门户](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains)中的租户相关联。 这将在 DNS 中添加一个条目，在将值添加到 DNS 设置后，可能需要几分钟的时间来进行验证。

- 使用相应的全局管理员凭据登录到 Microsoft 365 管理中心，并添加域（例如， `contoso.cn`）以供用户创建。 在验证过程中，可能需要进行其他 DNS 更改。 验证完成后，可以创建用户。

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>用于加密的 DNS 配置（Mac、iOS、Android）

- 登录到您的 DNS 提供商，导航到域的 DNS 设置，然后添加新的 SRV 记录。
  - 服务 = `_rmsdisco`
  - 协议 = `_http`
  - 名称 = `_tcp`
  - 目标 = `api.aadrm.cn`
  - 端口 = `80`
  - 优先级、权重、秒、TTL = 默认值
