---
title: Microsoft 托管桌面和 Windows 11
description: 服务Windows 11和何时可用
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: 494f147dad24b8c668fcb8adfc9b8a845a5fbe8f
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63317173"
---
# <a name="microsoft-managed-desktop-and-windows-11"></a>Microsoft 托管桌面和 Windows 11

在通知Windows 11，你可能已开始规划Windows 11迁移，以作为使 Windows 10 设备保持最新状态的工作的一部分。

本文概述了重要注意事项，Microsoft 托管桌面如何支持环境中平稳过渡。 有关用户Windows 11的信息，请参阅Windows 11[概述](/windows/whats-new/windows-11)。

有关在 Windows 11 设备上Microsoft 托管桌面特定步骤，请参阅预览和测试Windows 11[测试](../working-with-managed-desktop/test-win11-mmd.md)Microsoft 托管桌面。

## <a name="timeline-for-windows-10-and-windows-11"></a>Windows 10 和 Windows 11

Windows 11 2021 年 10 月 4 日正式提供。 它适用于消费者和企业部署，并且它是一个完全支持的平台。

我们将从 2023 年 1 月开始计划Microsoft 托管桌面部署。 但是，我们将为希望更快部署Windows 11完全支持。 我们将根据技术准备情况和业务注意事项，向管理员咨询并实施每个租户的迁移计划。

Microsoft 托管桌面继续并行Windows 10，直到达到企业支持结束。 请参阅[Windows 10发布信息](/windows/release-health/release-information)了解生命周期信息。

## <a name="assessing-pre-release-versions-of-windows-11"></a>评估预发行版Windows 11

超过 95% Microsoft 托管桌面设备有资格使用Windows 11。 在生产部署之前，你可能想要尝试在测试设备上进行升级。 有关系统Windows 11要求，请参阅Windows 11[要求](/windows/whats-new/windows-11-requirements)。

对于Microsoft 托管桌面，你可以[将设备添加到测试Windows 11组](/microsoft-365/managed-desktop/working-with-managed-desktop/test-win11-mmd?view=o365-worldwide#add-devices-to-the-windows-11-test-group)。 此组接收常规Windows 11版本以及Microsoft 托管桌面配置。 添加到设备组后，允许设备在一到两天内选取新设置，并Windows 11。

对于不是由 Microsoft 托管桌面 管理的设备，Endpoint Manager[了解如何](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/endpoint-manager-simplifies-upgrades-to-windows-11/ba-p/2771886)部署 Windows 11。 如果你的设备在 Windows 11及更高版本中运行，Microsoft 托管桌面注册它们，它们将不会恢复为Windows 10。

## <a name="support-for-pre-release-windows-11-devices"></a>支持预发布Windows 11设备

对于在通用版本Windows 11选择进行测试的设备，设备可能安装了预览版本。

Microsoft 托管桌面此状态的设备不会向常规Windows 11版本提供。 但是，仍支持设备来解决遇到的问题。 Microsoft 托管桌面监视所有托管设备是否有安全威胁，并响应任何警报，无论设备是否运行 Windows 11预览版本。

由于我们致力于帮助你迁移到 Windows 11，同时保持工作效率，我们鼓励你报告在平台中遇到的缺陷。 我们确定优先级：

- 在广泛部署 Windows 11 时阻止用户工作效率Windows 11。
- 阻止用户对移动设备工作效率Windows 10缺陷。

## <a name="testing-application-compatibility"></a>测试应用程序兼容性

应用程序兼容性是任何平台迁移中最常见的问题之一，因为可能会中断工作效率。 我们正在使用几个主动和被动措施，帮助你确信应用能够顺利过渡到Windows 11。

### <a name="proactive-measures"></a>主动措施

下面是一些主动措施：

| 主动措施 | 说明 |
| ----- | ----- |
| 常见应用 | Microsoft 广泛测试在内部版本上部署的最常见企业Windows 11套件。 我们与外部软件发布者和内部产品团队合作，以解决在测试过程中发现的任何问题。 有关主动兼容性测试工作的详细信息，请参阅 [应用程序兼容性博客](https://blogs.windows.com/windowsexperience/2019/01/15/application-compatibility-in-the-windows-ecosystem/)。
| 业务线应用 | [测试](https://www.microsoft.com/en-us/testbase)库是应用发布者和 IT 管理员可用于提交应用和测试用例的资源，Microsoft 可以在安全 Azure 环境中运行 Windows 11 内部版本运行的虚拟机。<br><br>每次测试执行的结果、测试见解和回归分析都可供你在专用 Azure 门户上使用。 Microsoft 托管桌面将帮助你根据应用使用情况和可靠性数据确定业务线应用的优先级进行验证。 有关测试基础的信息，请参阅测试[基础Microsoft 365](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/test-base-for-microsoft-365-microsoft-ignite-2021-updates/ba-p/2185566)。 |

### <a name="reactive-measures"></a>反应措施

如果你在测试或生产环境中遇到应用兼容性问题，可以通过打开支持请求获得免费 [支持](/microsoft-365/managed-desktop/working-with-managed-desktop/test-win11-mmd?view=o365-worldwide#report-issues)。

For Windows 11， support includes any functionality with the following apps that run on the latest operating system builds：

- Office
- Microsoft Edge
- Teams
- 业务线应用程序

Microsoft 应用保证会直接与应用发布者合作，以根据需要确定应用兼容性问题的优先级并解决它们。
