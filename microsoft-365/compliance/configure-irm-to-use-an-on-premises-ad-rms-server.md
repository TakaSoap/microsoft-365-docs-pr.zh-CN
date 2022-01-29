---
title: 将 IRM 配置为使用本地 AD RMS 服务器
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: 了解如何在 Exchange Online 中配置信息权限 (IRM) ，以使用 AD RMS (Active Directory 权限管理服务) 服务器。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f87992fc9be676b9485d6ec7a7b7ff1f3a4d39d9
ms.sourcegitcommit: 99067d5eb1fa7b094e7cdb1f7be65acaaa235a54
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2022
ms.locfileid: "62271546"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a>将 IRM 配置为使用本地 AD RMS 服务器

为了与本地部署一同使用，Exchange Online 中的信息权限管理 (IRM) 使用 Active Directory Rights Management Services (AD RMS) ，这是 Windows Server 2008 及更高版本中的一种信息保护技术。 通过将 AD RMS 权限策略模板应用于电子邮件，可将 IRM 保护应用于电子邮件。 权限附加到邮件本身，以便联机和脱机以及组织防火墙内外进行保护。

本主题显示了如何将 IRM 配置为使用 AD RMS 服务器。 有关将新功能用于 Office 365 邮件加密 和 Azure Azure Active Directory的信息，请参阅 Office 365 邮件加密 [FAQ](./ome-faq.yml)。

有关 Exchange Online 中 IRM 的详细信息，请参阅[Exchange Online 中的信息权限管理](information-rights-management-in-exchange-online.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，您需要知道什么？

- 估计完成该任务的时间：30 分钟

- 您必须先获得权限，然后才能执行此过程或多个过程。若要查看所需的权限，请参阅 [Messaging policy and compliance permissions](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions)主题中的"信息权限管理"条目。

- AD RMS 服务器必须运行 Windows Server 2008 或更高版本。有关如何部署 AD RMS 的详细信息，请参阅[安装 AD RMS 群集](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11))。

- 有关如何安装和配置 Windows PowerShell 以及连接到服务的详细信息，请参阅[使用远程 PowerShell 连接到 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。

- 有关可能适用于本主题中的过程的键盘快捷方式的信息，请参阅 Exchange 管理中心的键盘[Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。

## <a name="how-do-you-do-this"></a>您该如何做？
<a name="sectionSection1"> </a>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a>步骤 1：使用 AD RMS 控制台从 AD RMS 服务器导出受信任发布域 (TPD)

第一步是从内部部署 AD RMS 服务器将受信任发布域 (TPD) 导出到 XML 文件。TPD 包含以下使用 RMS 功能所需的设置：

- 用于对证书和许可证进行签名和加密的服务器许可方证书 (SLC)

- 用于许可和发布的 URL

- 使用该 TPD 的特定 SLC 创建的 AD RMS 权限策略模板

导入 TPD 时，它在 Exchange Online 中进行存储并受保护。

1. 打开 Active Directory Rights Management Services 控制台，然后展开 AD RMS 群集。

2. 在控制台树中，展开“信任策略”，然后单击“受信任的发布域”。

3. 在结果窗格中，选择要导出的域的证书。

4. 在“操作”窗格中，单击“导出受信任的发布域”。

5. 在“发布域文件”框中，单击“另存为”将文件保存到本地计算机上的特定位置。 键入文件名，确保指定 `.xml` 文件扩展名，然后单击"保存 **"**。

6. 在“密码”和“确认密码”框中，键入将用于对受信任的发布域文件加密的强密码。在将 TPD 导入到基于云的电子邮件组织时，必须指定此密码。

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a>步骤 2：使用 Exchange 命令行管理程序 将 TPD 导入到 Exchange Online

将 TPD 导出到 XML 文件之后，必须将其导入到 Exchange Online。 导入 TPD 之后，还将导入组织的 AD RMS 模板。 导入第一个 TPD 时，该 TPD 会成为基于云的组织的默认 TPD。 如果导入另一个 TPD，则可以使用 **Default** 开关使其成为可供用户使用的默认 TPD。

若要导入 TPD，请在 Windows PowerShell 中运行以下命令：

```powershell
Import-RMSTrustedPublishingDomain -FileData ([System.IO.File]::ReadAllBytes('<path to exported TPD file>')) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

可以在控制台中获取 _ExtranetLicensingUrl_ 和 _IntranetLicensingUrl_ Active Directory Rights Management Services值。 在控制台树中选择 AD RMS 群集。 许可 URL 显示在结果窗格中。 当必须对内容进行解密时以及 Exchange Online 需要确定要使用的 TPD 时，电子邮件客户端会使用这些 URL。

当运行此命令时，系统会提示您输入密码。输入您在从 AD RMS 服务器导出 TPD 时指定的密码。

例如，以下命令使用您从 AD RMS 服务器导出并保存到管理员帐户桌面的 XML 文件来导入名为 Exported TPD 的 TPD。Name 参数用于为 TPD 指定名称。

```powershell
Import-RMSTrustedPublishingDomain -FileData ([System.IO.File]::ReadAllBytes('C:\Users\Administrator\Desktop\ExportTPD.xml')) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

有关语法和参数的详细信息，请参阅 [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain)。

#### <a name="how-do-you-know-that-you-successfully-imported-the-tpd"></a>您如何知道已成功导入 TPD？

若要验证是否成功导入了 TPD，请运行 **Get-RMSTrustedPublishingDomain** cmdlet 检索 Exchange Online 中的 TPD。 有关详细信息，请参阅 [Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain) 中的示例。

### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a>步骤 3：使用 Exchange 命令行管理程序 来分发 AD RMS 权限策略模板

导入 TPD 之后，必须确保已分发 AD RMS 权限策略模板。 分布式模板对之前Outlook 网页版 (称为Outlook Web App) 用户可见，然后用户可以将模板应用到电子邮件。

若要返回默认 TPD 中包含的所有模板的列表，请运行以下命令：

```powershell
Get-RMSTemplate -Type All | fl
```

如果 _Type_ 参数的值为 ， `Archived`则模板对用户不可见。 只有默认 TPD 中的分布式模板在 Outlook 网页版。

若要分发模板，请运行以下命令：

```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

例如，以下命令导入 Company Confidential 模板。

```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

有关语法和参数的详细信息，请参阅 [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) 和 [Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate)。

#### <a name="the-do-not-forward-template"></a>"不要转发"模板

将默认 TPD 从内部部署组织导入到 Exchange Online 时，会导入一个名为“不要转发”的 AD RMS 权限策略模板。 默认情况下，导入默认 TPD 时将分发此模板。 使用 **Set-RMSTemplate** cmdlet 不能修改" **不要转发"** 模板。

将“不要转发”模板应用于邮件时，只有邮件的收件人可读取该邮件。另外，收件人不能执行以下操作：

- 将邮件转发给其他人。
- 复制邮件的内容。
- 打印邮件。

> [!IMPORTANT]
> “不要转发”模板无法阻止通过第三方屏幕捕获程序、照相机复制邮件中的信息或阻止用户手动转录这些信息。

您可在内部部署组织中的 AD RMS 服务器上创建其他 AD RMS 权限策略模板，以满足 IRM 保护要求。如果创建其他 AD RMS 权限策略模板，则必须再次从内部部署 AD RMS 服务器导出 TPD，并刷新基于云的电子邮件组织中的 TPD。

#### <a name="how-do-you-know-that-you-successfully-distributed-the-ad-rms-rights-policy-template"></a>您如何知道已成功分发 AD RMS 权限策略模板？

若要验证是否成功分发了 AD RMS 权限策略模板，请运行 **Get-RMSTemplate** cmdlet 检查模板的属性。 有关详细信息，请参阅 [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) 中的示例。

### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a>步骤 4：使用 Exchange 命令行管理程序 启用 IRM

导入 TPD 并分发 AD RMS 权限策略模板之后，请运行以下命令来为基于云的电子邮件组织启用 IRM。

```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

有关语法和参数的详细信息，请参阅 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration)。

#### <a name="how-do-you-know-that-you-successfully-enabled-irm"></a>您如何知道已成功启用 IRM？

若要验证是否已成功启用 IRM，请运行 [Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) cmdlet 来检查 Exchange Online 组织中的 IRM 配置。

## <a name="how-do-you-know-this-task-worked"></a>如何判断此任务生效？
<a name="sectionSection2"> </a>

若要验证是否已成功导入 TPD 并启用 IRM，执行以下操作：

- 使用 **Test-IRMConfiguration** cmdlet 测试 IRM 功能。 有关详细信息，请参阅 [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) 中的"示例 1"。

- 在"更多选项"图标Outlook 网页版扩展菜单中选择"设置权限"选项，在  Outlook 网页版 中撰写新邮件，然后使用 I (![](../media/ITPro-EAC-MoreOptionsIcon.gif) RM 进行) 。
