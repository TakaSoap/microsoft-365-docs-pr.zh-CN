---
title: 使用向导设置 Microsoft Defender for Business
description: Defender for Business 包括类似向导的安装和配置过程。 使用向导可以节省时间和精力。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 03/15/2022
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
ms.openlocfilehash: b55af496881489279a7a6f96ed386ab2a26c2fa5
ms.sourcegitcommit: a216617d6ff27fe7d3089a047fbeaac5d72fd25c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "63512596"
---
# <a name="use-the-wizard-to-set-up-microsoft-defender-for-business"></a>使用向导设置 Microsoft Defender for Business

> [!IMPORTANT]
> 从 2022 年 3 [月](../../business-premium/index.md) 1 Microsoft 365 商业高级版 Microsoft Defender for Business 将推出给客户。 作为独立订阅的 Defender for Business 在预览版中，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 预览 [包括一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

Microsoft Defender for Business 旨在通过类似向导的体验为中小型企业节省时间和精力，实现初始安装和配置。 本文介绍了向导的步骤以及手动设置和配置 Defender for Business 的选项。

:::image type="content" source="media/mdb-wizard-start.png" alt-text="用于设置 Defender for Business 的向导主屏幕屏幕截图。":::

>
> **有空吗？**
> 请参加有关 <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business 的简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="overview-of-the-wizard"></a>向导概述

该向导旨在帮助你快速高效地设置和配置 Defender for Business。 向导将指导你完成以下步骤：

1. **分配用户权限**。 在此步骤中，将授予安全团队对 Microsoft 365 Defender 门户 () [https://security.microsoft.com](https://security.microsoft.com) 。 门户访问权限通过表示特定权限的角色授予。 [详细了解角色和权限](mdb-roles-permissions.md)。

   - 全局管理员可以查看和编辑整个租户Microsoft 365设置。 
   - 安全管理员可以查看和编辑安全设置。 
   - 安全读者只能查看报告中的信息。 

2. **载入和配置Windows设备**。 在此步骤中，你可以将公司的 Windows快速载入 Defender for Business。 从第一天起，载入设备有助于保护这些设备。 有关详细信息 [，请参阅将设备载入 Microsoft Defender for Business](mdb-onboard-devices.md) 。

   - 如果你已在 Microsoft Endpoint Manager) 的 Microsoft Intune (部分使用，并且你的公司已在 Endpoint Manager 中注册了设备，则系统将会询问你是否希望对部分或所有注册的 Windows 设备使用自动载入。[](mdb-onboard-devices.md#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager) 自动载入可设置 Endpoint Manager 和 Defender for Business 之间的连接，然后将Windows设备无缝载入到 Defender for Business。

   - 如果你尚未使用 Endpoint Manager，或者如果你在 Endpoint Manager 中注册了非 Windows 设备，你可以手动将设备载入 [Defender for Business](mdb-onboard-devices.md#local-script-in-defender-for-business)。 
   
3. **配置安全策略**。 Defender for Business 包括适用于下一代保护和防火墙保护的默认安全策略，可应用于你的公司设备。 这些默认策略使用推荐设置，旨在为设备提供强大的保护。 

   如果需要，还可以创建自己的安全策略。 而且，如果你已在使用Endpoint Manager，可以继续使用它来管理安全策略。 

   若要了解更多信息，请参阅 [查看和编辑安全策略和设置](mdb-configure-security-settings.md)。

## <a name="what-happens-if-i-dont-use-the-wizard"></a>如果不使用向导，会发生什么情况？

如果选择不使用向导，或者向导在安装过程完成之前关闭，则仍可自行完成安装和配置过程。 

请参阅 [设置和配置 Microsoft Defender for Business](mdb-setup-configuration.md) 以完成以下步骤：

1. [分配角色和权限](mdb-roles-permissions.md)，以便安全团队可以访问和使用Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 。

2. [为安全团队设置电子邮件通知](mdb-email-notifications.md) ，以便他们了解新警报或漏洞。

3. [载入设备](mdb-onboard-devices.md) ，以便它们受 Defender for Business 保护。

4. [管理安全策略，](mdb-configure-security-settings.md)其中包括下一代保护、防火墙保护和 Web 内容筛选。

## <a name="next-steps"></a>后续步骤

- [为安全团队设置电子邮件通知](mdb-email-notifications.md)

- [开始使用 Microsoft 365 Defender 门户](mdb-get-started.md)

- [使用威胁&漏洞管理仪表板](mdb-view-tvm-dashboard.md)