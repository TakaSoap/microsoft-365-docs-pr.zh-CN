---
title: Microsoft 托管桌面和 Windows 11
description: 服务中Windows 11 及何时可用
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: f0ab88b647b3fb7311d9adfdc6e9dc6758755b30
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60198297"
---
# <a name="microsoft-managed-desktop-and-windows-11"></a>Microsoft 托管桌面和 Windows 11

在 11 Windows公告后，你可能已开始规划 Windows 11 迁移，作为使 Windows 10 设备保持最新工作的一部分。 本文概述了重要注意事项，Microsoft 托管桌面如何支持环境中平稳过渡。 有关 11 Windows的信息，请参阅 Windows [11 概述](/windows/whats-new/windows-11)。

有关在 Microsoft 托管桌面 设备上安装 Windows 11 的具体步骤，请参阅预览和测试 Windows [11 Microsoft 托管桌面。](../working-with-managed-desktop/test-win11-mmd.md)

## <a name="timeline-for-windows-11"></a>Windows 11 的日程表

Windows 11 个预览版本从 2021 年 6 月 28 日开始通过预览体验计划Windows[提供](/windows-insider/)。 我们希望在 2021 日历年结束时发布版本。

欢迎在设备上安装预览版本，无论它们是否由Microsoft 托管桌面管理。 我们将继续并行支持Windows 10，直到它获得企业支持结束。 有关[生命周期Windows 10，](/windows/release-health/release-information)请参阅发布信息。

当 Windows 11 已普遍可用时，我们将执行更多验证测试。 我们希望 2022 年 1 月是Windows部署组向Microsoft 托管桌面设备提供 11 的最早时间。

我们将根据技术准备情况和业务注意事项，向管理员咨询并实施每个租户的迁移计划。

## <a name="assessing-pre-release-versions-of-windows-11"></a>评估版本 11 的预Windows版本

超过 95% Microsoft 托管桌面设备符合 Windows 11 条件，因此你可能想要在生产部署之前在测试设备上预览升级。 有关 11 Windows要求，请参阅 Windows [11 要求](/windows/whats-new/windows-11-requirements)。 你可以请求有关设备资格状态的详细信息，具体Microsoft 托管桌面。

对于Microsoft 托管桌面，你可以请求将测试设备添加到现代 **工作区 - Windows 11** 预发布测试设备组。 此组会收到Windows 11 个预览版本以及Microsoft 托管桌面配置。 Microsoft 托管桌面版本 11 Windows版本发布频率，因此此设备组的成员接收更新的频率可能高于Windows 10组。

对于不由 Microsoft 托管桌面 管理的设备，你可以加入[Windows 预览](/windows-insider/)体验计划，下载预览版本并获取有关自己部署 Windows 11 的指导。 如果你的设备在 11 Windows版本中运行，并且稍后在 Microsoft 托管桌面 中注册它们，它们将不会恢复为Windows 10。

## <a name="support-for-pre-release-windows-11-devices"></a>支持 11 Windows预发布

任何平台的预发布版本应包含缺陷和应用程序兼容性问题，这些问题可在通用版本之前进行标识和解决。 因此，我们将运行 Windows 11 预发布版本的设备视为测试设备，但我们会随环境的其余部分一起监视它们，以受到与其他 Microsoft 托管桌面 设备相同的安全警报响应。

由于我们致力于帮助你迁移到 Windows 11，同时保持工作效率，我们鼓励你报告在预发布版本中遇到的缺陷。 我们优先处理在广泛部署 Windows 11 时阻止用户工作效率的缺陷，以及阻止用户在 Windows 10 工作效率的缺陷。

## <a name="testing-application-compatibility"></a>测试应用程序兼容性

应用程序兼容性是任何平台迁移中最常见的问题之一，因为可能会中断工作效率。 我们正在使用几个主动和被动措施，帮助你对顺利过渡到 11 Windows放心。

### <a name="proactive-measures"></a>主动措施

**常见应用：** Microsoft 正在广泛测试在版本 11 内部版本上部署的最常见的Windows和套件。 我们与外部软件发布者和内部产品团队合作，以解决在测试过程中发现的任何问题。 有关主动兼容性测试工作的详细信息，请参阅 [应用程序兼容性博客](https://blogs.windows.com/windowsexperience/2019/01/15/application-compatibility-in-the-windows-ecosystem/)。

[](https://www.microsoft.com/en-us/testbase)业务线应用：测试库是应用发布者和 IT 管理员可用于提交应用和测试用例的资源，Microsoft 可以在安全 Azure 环境中运行 Windows 11 内部版本上的虚拟机上运行。 每次测试执行的结果、测试见解和回归分析都可供你在专用 Azure 门户上使用。 Microsoft 托管桌面将帮助你根据应用使用情况和可靠性数据确定业务线应用的优先级进行验证。 有关测试基础的信息，请参阅测试[基础Microsoft 365。](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/test-base-for-microsoft-365-microsoft-ignite-2021-updates/ba-p/2185566)

### <a name="reactive-measures"></a>反应措施
如果你在测试或生产环境中遇到应用兼容性问题，你可以根据情况通过吸引应用保证或FastTrack获得免费支持[](/fasttrack/products-and-capabilities#app-assure)。 对于 Windows 11，这包括运行在最新操作系统内部版本上的 Office、Microsoft Edge、Teams 和业务线应用程序的任何功能。 应用保证直接与应用发布者合作，以优先处理和解决应用兼容性问题。

