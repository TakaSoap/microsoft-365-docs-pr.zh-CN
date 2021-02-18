---
title: Azure 信息保护中的保护功能向现有租户推出
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 本文介绍了对 Azure 信息保护中的保护功能所做的更改
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fe85a46e3f20cda62cd8a52bd5df92257f8fee57
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286665"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Azure 信息保护中的保护功能向现有租户推出

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [适用于 Office 365 计划 2 的 Microsoft Defender](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

为了帮助执行保护信息的初始步骤，从 2018 年 7 月开始，所有符合条件的 Azure 信息保护租户将默认启用 Azure 信息保护中的保护功能。 Azure 信息保护中的保护功能以前在 Office 365 中称为权限管理或 Azure RMS。 如果你的组织具有 Office E3 服务计划或更高的服务计划，那么现在，当我们推出这些功能时，你将开始通过 Azure 信息保护来保护信息。

## <a name="changes-beginning-july-1-2018"></a>从 2018 年 7 月 1 日开始的更改

从 2018 年 7 月 1 日开始，Microsoft 将为具有以下订阅计划之一的所有组织启用 Azure 信息保护中的保护功能：

- Office 365 邮件加密作为 Office 365 E3 和 E5、Microsoft E3 和 E5、Office 365 A1、A3 和 A5 以及 Office 365 G3 和 G5 的一部分提供。 无需其他许可证，就无需其他许可证来接收由 Azure 信息保护支持的新保护功能。

- 还可以将 Azure 信息保护计划 1 添加到以下计划，以接收新的 Office 365 邮件加密功能：Exchange Online 计划 1、Exchange Online 计划 2、Office 365 F1、Microsoft 365 Business Basic、Microsoft 365 商业标准版或 Office 365 企业版 E1。

- 从 Office 365 邮件加密受益的每个用户都需要获得许可，以涵盖此功能。

- 有关完整列表，请参阅 Office 365 邮件加密的 [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) 服务说明。

租户管理员可以在 Office 365 管理员门户中检查保护状态。

![显示 Office 365 中权限管理已激活的屏幕截图。](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a>我们为什么要进行此更改？

Office 365 邮件加密利用 Azure 信息保护中的保护功能。 最近对 Office 365 邮件加密的改进以及我们对 Microsoft 365 信息保护的更广泛投资的核心是，我们正在使组织能够更轻松地启用和使用我们的保护功能，就像以往一样，加密技术一直难以设置。 默认情况下，通过打开 Azure 信息保护中的保护功能，可以快速开始保护敏感数据。

## <a name="does-this-impact-me"></a>这是否影响我？

如果你的组织已购买符合条件的 Office 365 许可证，则你的租户将受此更改的影响。

> [!IMPORTANT]
> 如果你在本地环境中使用 Active Directory Rights Management Services (AD RMS) ，则必须选择立即退出此更改或迁移到 Azure 信息保护，然后才能在接下来 30 天内推出此更改。 若要了解如何选择退出，请参阅"我使用 AD RMS，如何选择退出？" ”中所述的过程安装本地化文件。 如果你希望迁移，请参阅"从[AD RMS 迁移到 Azure 信息保护"。](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>能否将 Azure 信息保护与 Active Directory Rights Management Services (AD RMS) ？

否。 这不是受支持的部署方案。 如果不执行其他选择退出步骤，某些计算机可能会自动开始使用 Azure 权限管理服务，并连接到 AD RMS 群集。 此方案不受支持，且结果不可靠，因此，在推出这些新功能之前，必须选择在 30 天内退出此更改。 若要了解如何选择退出，请参阅"我使用 AD RMS，如何选择退出？" ”中所述的过程安装本地化文件。 如果你希望迁移，请参阅"从 [AD RMS 迁移到 Azure 信息保护"。](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>我如何知道是否正在使用 AD RMS？

如果还具有用于检查是否部署了 [AD RMS Active Directory Rights Management Services (AD RMS ](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms)) ，请使用准备 Azure 权限管理环境中的以下说明：

1. 尽管是可选的，但大多数 AD RMS 部署将服务连接点 (SCP) 发布到 Active Directory，以便域计算机可以发现 AD RMS 群集。

   使用 ADSI 编辑查看是否在 Active Directory 中发布了 SCP：CN=Configuration [server name]、CN=Services、CN=RightsManagementServices、CN=SCP

2. 如果不使用 SCP，则必须使用 Windows 注册表为客户端服务发现或许可重定向配置连接到 AD RMS 群集的 Windows `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation` 计算机：

有关这些注册表配置的信息，请参阅使用 [Windows](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) 注册表和重定向许可服务器流量启用客户端 [服务发现](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)。

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>我使用 AD RMS，如何选择退出？

若要选择退出即将进行的更改，请完成以下步骤：

1. 使用组织中具有全局管理员权限的工作或学校帐户，启动Windows PowerShell会话并连接到 Exchange Online。 有关说明，请参阅[连接 PowerShell Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

2. 使用Set-IRMConfiguration运行该 cmdlet：

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>进行此更改后，我期望得到什么？

启用此功能后，如果你尚未选择退出，你可以开始使用 Microsoft [Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) 上宣布的 Office 365 邮件加密的新版本，并利用 Azure 信息保护的加密和保护功能。

![Screenshot that shows an OME protected message in Outlook on the web.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

有关新增强功能的信息，请参阅 [Office 365 邮件加密](../../compliance/ome.md)。
