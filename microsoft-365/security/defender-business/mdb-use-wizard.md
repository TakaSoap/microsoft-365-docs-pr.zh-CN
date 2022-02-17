---
title: '使用向导设置 Microsoft Defender for Business (预览) '
description: Defender for Business 包括类似向导的安装和配置过程。 使用向导可以节省时间和精力。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/16/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.custom: intro-get-started
ms.openlocfilehash: 26bf8e46ba79094f74fe542f932921d4f1c2a50d
ms.sourcegitcommit: 007822d16e332522546e948f5c216327254a4d49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2022
ms.locfileid: "62879128"
---
# <a name="use-the-wizard-to-set-up-microsoft-defender-for-business-preview"></a>使用向导设置 Microsoft Defender for Business (预览) 

> [!IMPORTANT]
> Microsoft Defender for Business 现在为预览版，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 我们将于未来几周内载入一组初始客户和合作伙伴，并扩大预览版本，从而一般可用。 请注意，预览将启动 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

Microsoft Defender for Business (预览) 旨在通过类似向导的体验为中小型企业节省时间和精力，实现初始安装和配置。 本文介绍了向导的步骤以及手动设置和配置 Defender for Business 的选项。

:::image type="content" source="media/mdb-wizard-start.png" alt-text="用于设置 Defender for Business 的向导主屏幕屏幕截图。":::

## <a name="overview-of-the-wizard"></a>向导概述

该向导旨在帮助你快速高效地设置和配置 Defender for Business。 向导将指导你完成以下步骤：

1. **分配用户权限**。 在此步骤中，将授予安全团队对 Microsoft 365 Defender 门户 () [https://security.microsoft.com](https://security.microsoft.com) 。 门户访问权限通过表示特定权限的角色授予。 [详细了解角色和权限](mdb-roles-permissions.md)。

   - 全局管理员可以查看和编辑整个租户Microsoft 365设置。 
   - 安全管理员可以查看和编辑安全设置。 
   - 安全读者只能查看报告中的信息。 

2. **设置电子邮件通知**。 在此步骤中，确定在检测到漏洞或新警报时应接收电子邮件通知的人。 电子邮件通知可帮助你的安全团队随时了解情况，即使他们离开办公室。 [详细了解电子邮件通知](mdb-email-notifications.md)。 

3. **载入和配置Windows设备**。 在此步骤中，你可以将组织的 Windows快速载入 Defender for Business。 从第一天起，载入设备有助于保护这些设备。 

   - 如果你已在 Microsoft Endpoint Manager) 的 Microsoft Intune (部分使用，并且你的组织已在 Endpoint Manager 中注册了设备，则系统将会询问你是否希望对部分或所有注册的 Windows 设备使用自动载入。 自动载入可设置 Endpoint Manager 和 Defender for Business 之间的连接，然后Windows设备无缝载入到 Defender for Business。

   - 如果你尚未使用 Endpoint Manager，或者如果你在 Endpoint Manager 中注册了非 Windows 设备，你可以手动将设备载入 Defender for Business (预览版) 。 

   - 请参阅 [将设备载入到 Microsoft Defender for Business (预览) ](mdb-onboard-devices.md)。
   
4. **配置安全策略**。 Defender for Business 包括可应用于组织设备的默认安全策略。 这些默认策略使用推荐设置，旨在为设备提供强大的保护。 但是，如果需要，还可以创建自己的安全策略。 此外，如果你已在使用Endpoint Manager，可以继续使用它来管理安全策略。 

   - [详细了解简化的配置](mdb-simplified-configuration.md)。
   - [选择在何处管理安全策略和设备](mdb-configure-security-settings.md#choose-where-to-manage-security-policies-and-devices)。

## <a name="what-happens-if-i-dont-use-the-wizard"></a>如果不使用向导，会发生什么情况？

如果选择不使用向导，或者如果在安装过程完成之前退出向导，则仍可自行完成安装和配置过程。 请参阅 [设置和配置 Microsoft Defender for Business (预览) ](mdb-setup-configuration.md) 演练这些步骤。

## <a name="next-steps"></a>后续步骤

- [开始使用 Microsoft 365 Defender 门户](mdb-get-started.md)

- [使用威胁&漏洞管理仪表板](mdb-view-tvm-dashboard.md)