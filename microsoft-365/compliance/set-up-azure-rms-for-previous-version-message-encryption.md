---
title: 为以前版本的邮件加密设置 Azure 权限管理
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 早期版本的 Office 365 邮件加密依赖于Microsoft Azure权限 (以前称为Windows Azure Active Directory权限管理) 。
ms.openlocfilehash: c94497069d929dd3819e3ced915c8e778e983c10
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159600"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a>为以前版本的邮件加密设置 Azure 权限管理

本主题介绍激活 Azure 权限管理 (RMS) （Azure 信息保护的一部分）以与以前版本的 Office 365 邮件加密 (OME) 一起使用时需要执行的步骤。

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>本文仅适用于以前版本的 OME

如果尚未将组织移动到新的 OME 功能，但已部署 OME，则本文中的信息适用于您的组织。 Microsoft 建议你在组织合理时制定移动到新 OME 功能的计划。 有关说明，请参阅[设置新的Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。 若要详细了解新功能如何首先工作，[请参阅Office 365 邮件加密。](ome.md) 本文的其余部分将介绍新的 OME 功能发布之前 OME 的行为。

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>使用早期版本的 Office 365 邮件加密
<a name="warmprereqs"> </a>

Office 365 邮件加密 (OME) （包括 IRM）取决于 Azure RMS (Azure 权限) 。 Azure RMS 是 Azure 信息保护使用的保护技术。 若要使用 OME，组织必须包含 Exchange Online 或 Exchange Online Protection 订阅，而订阅又包括 Azure 权限管理订阅。
  
- 如果不确定订阅包含哪些内容，请参阅邮件Exchange Online、恢复和合规性[的订阅服务说明](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)。

- 如果你拥有 Azure 权限管理，但没有为 Exchange Online 或 Exchange Online Protection 进行设置，本文将介绍如何激活 Azure 权限管理，然后介绍设置 OME 以使用 Azure 权限管理的最佳方法。

- 如果你已设置 OME 以使用 Exchange Online 或 Exchange Online Protection 的 Azure 权限管理，则根据设置方式，你可能已准备好立即开始使用 OME 及其新功能。 本文介绍如何确定是否正确设置了 OME、需要更改设置时应执行哪些操作，以及选择不更改设置时会发生什么情况。 例如，若要使用新功能，必须将 Azure RMS 与 OME 一同使用。 不能将新功能与本地 Active Directory RMS 一同使用。

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>在 Office 365 中激活以前版本的 OME 的 Azure 权限Office 365

你需要激活 Azure 权限管理，以便你的组织用户可以将信息保护应用于他们发送的邮件，并打开受 Azure 权限管理服务保护的邮件和文件。 有关说明，请参阅 [激活 Azure 权限管理](/azure/information-protection/activate-service)。 完成激活后，返回此处并继续执行本文中的任务。
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>将以前版本的 OME 设置为使用 Azure RMS，方法为将受信任的发布域 (TPD) 

TPD 是一个 XML 文件，其中包含有关您组织权限管理设置的信息。 例如，TPD 包含有关用于签署和加密证书和许可证的服务器 (SLC) 、用于许可和发布等的 URL 的信息。 使用 TPD 将 TPD 导入Windows PowerShell。
  
> [!IMPORTANT]
> 以前，您可以选择将 TPD 从 Active Directory 权限管理服务 (AD RMS) 组织。 但是，这样做将阻止你使用新的 OME 功能，不建议这样做。 如果组织当前已按此方式配置，Microsoft 建议创建从本地 Active Directory RMS 迁移到基于云的 Azure 信息保护的计划。 有关详细信息，请参阅从 [AD RMS 迁移到 Azure 信息保护](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。 在迁移到 Azure 信息保护之前，你将不能使用新的 OME 功能。
  
 **从 Azure RMS 导入 TPD**
  
1. [连接远程Exchange Online PowerShell 进行连接](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 选择与组织的地理位置对应的密钥共享 URL：

|**位置**|**密钥共享位置 URL**|
|:-----|:-----|
|北美  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|欧盟  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|亚洲  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|南美洲  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|政府用 Office 365（政府社区云）  <br/> 此 RMS 密钥共享位置为已购买政府 SK Office 365保留。  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. 通过运行 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet 配置密钥共享位置，如下所示： 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   例如，如果组织位于北美，则配置关键共享位置：

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. 使用 [-RMSOnline 开关运行 Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) cmdlet 以从 Azure 权限管理导入 TPD： 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   其中  *TPDName*  是你想要用于 TPD 的名称。 例如，"Contoso 北美 TPD"。 

5. 若要验证您是否已成功将组织配置为使用 Azure 权限管理服务，请运行带 -RMSOnline 开关的 [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) cmdlet，如下所示：

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   此外，此 cmdlet 还检查与 Azure 权限管理服务的连接、下载 TPD 并检查其有效性。

6. 运行[Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet，以禁止 Azure 权限管理模板在 Outlook 网页版 和 Outlook： 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. 按如下所示[运行 Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet，为基于云的电子邮件组织启用 Azure 权限管理，并配置为使用 Azure 权限管理进行Office 365 邮件加密：

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. 若要验证您是否已成功导入 TPD 并启用 Azure 权限管理，请使用 Test-IRMConfiguration cmdlet 测试 Azure 权限管理功能。 有关详细信息，请参阅 [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) 中的"示例 1"。

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>我使用 Active Directory 权限管理而非 Azure 信息保护设置了以前版本的 OME，我该怎么办？
<a name="importTPDs"> </a>

您可以继续使用现有的邮件流Office 365 邮件加密 Active Directory 权限管理，但无法配置或使用新的 OME 功能。 相反，你需要迁移到 Azure 信息保护。 有关迁移以及这对组织的含义的信息，请参阅从 [AD RMS](/information-protection/deploy-use/prepare-environment-adrms)迁移到 Azure 信息保护。
  
## <a name="next-steps"></a>后续步骤
<a name="importTPDs"> </a>

完成 Azure 权限管理设置后，如果要启用新的 OME 功能，请参阅设置基于 Azure 信息保护构建的新 Office 365 邮件加密[功能。](./set-up-new-message-encryption-capabilities.md)
  
将组织设置为使用新的 OME 功能后，即可定义邮件流规则，以使用新的 [OME 功能保护电子邮件](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="related-topics"></a>相关主题
<a name="importTPDs"> </a>

[Office 365 中的加密](encryption.md)
  
[有关 Office 365 加密的技术参考详情](technical-reference-details-about-encryption.md)
  
[什么是 Azure 权限管理？](/information-protection/understand-explore/what-is-azure-rms)