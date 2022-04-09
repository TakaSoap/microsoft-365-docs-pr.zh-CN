---
title: 在Microsoft Defender 商业版中使用安装向导
description: Defender for Business 包括类似向导的设置和配置过程。 使用向导可节省时间和精力。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 04/08/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.custom: intro-get-started
ms.openlocfilehash: ad070273567d350973037f1ac5a0192036d22187
ms.sourcegitcommit: dd5fc139affb4cba4089cbdb2c478968b680699a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2022
ms.locfileid: "64746636"
---
# <a name="use-the-setup-wizard-in-microsoft-defender-for-business"></a>在Microsoft Defender 商业版中使用安装向导

> [!IMPORTANT]
> Microsoft Defender 商业版从 2022 年 3 月 1 日开始向[Microsoft 365 商业高级版](../../business-premium/index.md)客户推出。 Defender for Business 作为独立订阅处于预览状态，将逐步推出给 [在此处注册](https://aka.ms/mdb-preview) 以请求该订阅的客户和 IT 合作伙伴。 预览版包括 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的一些信息涉及到预租产品/服务，这些产品/服务在商业发布之前可能会进行重大修改。 Microsoft 不会对此处提供的信息作出明示或暗示的保证。 

Microsoft Defender 商业版旨在为中小型企业节省时间和精力，并提供类似向导的初始设置和配置体验。 安装向导将指导你完成授予安全团队访问权限、为安全团队设置电子邮件通知以及载入公司Windows设备。

:::image type="content" source="media/mdb-wizard-start.png" alt-text="用于设置 Defender for Business 的向导主屏幕的屏幕截图。":::

>
> **有空吗？**
> 请对<a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender 商业版进行简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="overview-of-the-setup-wizard"></a>安装向导概述

> [!IMPORTANT]
> 在开始之前，请确保已将用户添加到Microsoft 365订阅。 若要获取有关此任务的帮助，请参阅 [“添加用户”并同时分配许可证](../../admin/add-users/add-users.md)。

该向导旨在帮助你快速高效地设置和配置 Defender for Business。 向导将引导你完成以下步骤：

1. **分配用户权限**。 在此步骤中，将授予安全团队访问Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 。 在此门户中，你和安全团队将管理安全功能、查看警报，并针对检测到的威胁执行任何所需的操作。 门户访问权限是通过表示某些权限的角色授予的。

   在 Defender for Business 中，可以为安全团队的成员分配三个角色之一：<br/>
   
      - **全局管理员**：全局管理员可以查看和编辑Microsoft 365租户中的所有设置。 全局管理员为公司的Microsoft 365订阅执行初始设置和配置。 
      - **安全管理员**：安全管理员可以查看和编辑安全设置，并在检测到威胁时采取措施。
      - **安全读取者**：安全读取器可以查看报表中的信息，但不能更改任何安全设置。 
      
      [详细了解角色和权限](mdb-roles-permissions.md)。 

2. **设置电子邮件通知**。 在此步骤中，可以为安全团队设置电子邮件通知。 然后，当生成警报或发现新漏洞时，即使安全团队离开办公桌，也不会对此进行处理。 

   [详细了解电子邮件通知](mdb-email-notifications.md)。 

3. **载入和配置Windows设备**。 在此步骤中，可以快速将公司Windows设备加入 Defender for Business。 立即载入设备有助于从第一天起保护这些设备。 

   - **如果已使用包括Microsoft Intune) 的Microsoft Endpoint Manager** (，并且公司已在Endpoint Manager中注册了设备，系统会询问是要对某些设备还是所有已注册的Windows设备使用 [自动载入](mdb-onboard-devices.md#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)。 自动载入可在 Endpoint Manager 和 Defender for Business 之间建立连接，然后将Windows设备无缝载入到 Defender for Business。 
   - **如果尚未使用Endpoint Manager**，则可以 [使用本地脚本将设备载入 Defender for Business](mdb-onboard-devices.md#local-script-in-defender-for-business)。 
   
   请参阅[详细了解如何载入设备以Microsoft Defender 商业版](mdb-onboard-devices.md)。
   
4. **配置安全策略**。 Defender for Business 包含可应用于公司设备的下一代保护和防火墙保护的默认安全策略。 这些默认策略使用建议的设置，旨在为设备提供强大的保护。 还可以创建自己的安全策略。 而且，如果已在使用Endpoint Manager，则可以继续使用它来管理安全策略。

   若要了解详细信息，请 [参阅“查看”并编辑安全策略和设置](mdb-configure-security-settings.md)。 |

## <a name="what-happens-if-i-dont-use-the-wizard"></a>如果不使用向导，会发生什么情况？

使用安装向导是可选的。 如果选择不使用向导，或者在安装过程完成之前关闭向导，则可以自行完成设置和配置过程。 请参阅[设置和配置Microsoft Defender 商业版](mdb-setup-configuration.md)以逐步完成以下步骤：

1. **[分配角色和权限](mdb-roles-permissions.md)**，以便安全团队可以访问和使用Microsoft 365 Defender门户 ([https://security.microsoft.com](https://security.microsoft.com)) 。

2. **[为安全团队设置电子邮件通知](mdb-email-notifications.md)** ，使其处于有关新警报或漏洞的循环中。

3. **[载入设备](mdb-onboard-devices.md)** ，以便受 Defender for Business 保护。

4. **[管理安全策略](mdb-configure-security-settings.md)**，其中包括下一代保护、防火墙保护和 Web 内容筛选。

## <a name="next-steps"></a>后续步骤

- [为安全团队设置电子邮件通知](mdb-email-notifications.md)

- [使用Microsoft 365 Defender门户开始](mdb-get-started.md)

- [使用威胁&漏洞管理仪表板](mdb-view-tvm-dashboard.md)