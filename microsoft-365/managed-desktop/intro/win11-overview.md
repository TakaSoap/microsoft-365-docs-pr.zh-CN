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
ms.openlocfilehash: 3365bd636ccf5825d842fb41c078cbcc67c6081f
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034685"
---
# <a name="microsoft-managed-desktop-and-windows-11"></a>Microsoft 托管桌面和 Windows 11

在通知Windows 11，你可能已开始规划Windows 11迁移，以作为使 Windows 10 设备保持最新状态的工作的一部分。 本文概述了重要注意事项，Microsoft 托管桌面如何支持环境中平稳过渡。 有关用户Windows 11的信息，请参阅Windows 11[概述](/windows/whats-new/windows-11)。

有关在 Windows 11 设备上Microsoft 托管桌面安装的具体步骤，请参阅预览和测试Windows 11[测试](../working-with-managed-desktop/test-win11-mmd.md)Microsoft 托管桌面。

## <a name="timeline-for-windows-11"></a>日程表Windows 11

Windows 11预览版本于 2021 年 6 月 28 日通过预览体验计划Windows[提供](/windows-insider/)。 我们希望在 2021 日历年结束时发布版本。

欢迎在设备上安装预览版本，无论它们是否由Microsoft 托管桌面管理。 我们将继续并行支持Windows 10，直到它获得企业支持结束。 请参阅[Windows 10生命周期信息的](/windows/release-health/release-information)发布信息。

当Windows 11版本时，我们将执行更多验证测试。 我们希望 2022 年 1 月是Windows 11标准部署组向Microsoft 托管桌面设备提供的最早时间。

我们将根据技术准备情况和业务注意事项，向管理员咨询并实施每个租户的迁移计划。

## <a name="assessing-pre-release-versions-of-windows-11"></a>评估预发布版本的Windows 11

超过 95% Microsoft 托管桌面设备有资格使用 Windows 11，因此你可能想要在生产部署之前在测试设备上预览升级。 有关系统Windows 11要求，请参阅Windows 11[要求](/windows/whats-new/windows-11-requirements)。 你可以从应用请求有关设备资格状态Microsoft 托管桌面。

对于Microsoft 托管桌面，你可以请求将测试设备添加到新式工作区 - Windows 11 **预发布测试设备组**。 此组接收Windows 11预览版本以及Microsoft 托管桌面配置。 Microsoft 托管桌面版本版本发布频率Windows 11，因此此设备组的成员接收更新的频率可能高于Windows 10组。

对于不由 Microsoft 托管桌面 管理的设备，你可以加入[Windows 预览](/windows-insider/)体验计划，下载预览版本并获取有关自己部署Windows 11指南。 如果你的设备在预Windows 11版本中运行，并且稍后在 Microsoft 托管桌面 中注册它们，它们将不会恢复为Windows 10。

## <a name="support-for-pre-release-windows-11-devices"></a>支持预发布Windows 11设备

任何平台的预发布版本应包含缺陷和应用程序兼容性问题，这些问题可在通用版本之前进行标识和解决。 因此，我们将运行 Windows 11 预发布版本的设备视为测试设备，但我们会将其与环境中的其余部分一起监视，以受到与其他 Microsoft 托管桌面 设备相同的安全警报响应。

由于我们致力于帮助你迁移到Windows 11，同时保持工作效率，我们鼓励你报告在预发布版本中遇到的缺陷。 我们确定缺陷的优先级，即广泛部署 Windows 11时阻止用户工作效率的缺陷，以及阻止用户Windows 10的缺陷。

## <a name="testing-application-compatibility"></a>测试应用程序兼容性

应用程序兼容性是任何平台迁移中最常见的问题之一，因为可能会中断工作效率。 我们正在使用几种主动和被动措施，帮助你确信应用能够顺利过渡到Windows 11。

### <a name="proactive-measures"></a>主动措施

**常见应用：** Microsoft 正在广泛测试在内部版本上部署的最常见企业Windows 11。 我们与外部软件发布者和内部产品团队合作，以解决在测试过程中发现的任何问题。 有关主动兼容性测试工作的详细信息，请参阅 [应用程序兼容性博客](https://blogs.windows.com/windowsexperience/2019/01/15/application-compatibility-in-the-windows-ecosystem/)。

[](https://www.microsoft.com/en-us/testbase)业务线应用：测试库是应用发布者和 IT 管理员可用于提交应用和测试用例的资源，Microsoft 可以在安全 Azure 环境中运行 Windows 11 内部版本运行的虚拟机上运行。 每次测试执行的结果、测试见解和回归分析都可供你在专用 Azure 门户上使用。 Microsoft 托管桌面将帮助你根据应用使用情况和可靠性数据确定业务线应用进行验证的优先级。 有关测试基础的信息，请参阅测试[基础Microsoft 365。](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/test-base-for-microsoft-365-microsoft-ignite-2021-updates/ba-p/2185566)

### <a name="reactive-measures"></a>反应措施
如果你在测试或生产环境中遇到应用兼容性问题，你可以根据情况通过吸引应用保证或FastTrack获得免费支持[](/fasttrack/products-and-capabilities#app-assure)。 例如Windows 11，这包括在最新操作系统Office上运行的 Office、Microsoft Edge、Teams 和业务线应用程序的任何功能。 应用保证直接与应用发布者合作，以优先处理和解决应用兼容性问题。

