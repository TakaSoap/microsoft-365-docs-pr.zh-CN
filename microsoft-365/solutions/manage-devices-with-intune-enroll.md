---
title: 步骤 2. 使用 Intune 将设备注册到管理
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: dougeby
audience: ITPro
description: 使用 Intune 和 Autopilot 将设备注册到管理，以确保在设备上运行的应用合规并防止公司数据泄露。
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- enroll devices into management
- enroll devices with Intune
- Intune mobile device platforms
ms.custom: ''
keywords: ''
ms.openlocfilehash: 56226aee898dad607d3dd85641b7736e764b2be2
ms.sourcegitcommit: 36a19d80fe3f053df0fec398a7ff2dfc777f9730
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/30/2021
ms.locfileid: "61645604"
---
# <a name="step-2-enroll-devices-into-management-with-intune"></a>步骤 2. 使用 Intune 将设备注册到管理

有多种方法可保护终结点，终结点是通常用于指代组合实体(包括设备、应用和用户标识)的术语。 必须在应用和设备本身上持续、可靠地强制实施安全策略。 将设备注册到管理并向云标识提供者(例如 Azure Active Directory)注册是很好的开始。

无论设备是个人所有的 BYOD 设备，还是公司所有的完全托管的设备，都最好了解访问组织资源的终结点，从而确保仅允许运行正常且合规的设备。 这包括在终结点上运行的移动和桌面应用的运行状况和可信度。 你希望确保这些应用正常且合规，并防止通过恶意意图或意外方式将企业数据泄漏到使用者应用或服务。

设备注册流程会在用户、设备和 Microsoft Intune 服务之间建立关系。 将 Microsoft Intune 用作独立服务便于使用单个基于 Web 的管理控制台以管理 Windows 电脑、macOS 和最热门的移动设备平台。

本文推荐了使用 Intune 将设备注册到管理的方法。 有关这些方法以及如何部署每个方法的详细信息，请参阅 [部署指南: 在 Microsoft Intune 中注册设备](/microsoft-365/security/defender/eval-overview)。

![管理设备的步骤](../media/devices/intune-mdm-steps-1.png#lightbox)

## <a name="windows-enrollment"></a>Windows 注册
有多种选项可用于注册 Windows 10 和 Windows 11 设备。 最常见的方法包含以下两种:

- Azure Active Directory (Azure AD)联接 - 将设备与Azure Active Directory 联接，并使用户能够使用其Azure AD 凭据登录到 Windows。 如果已启用自动注册，则设备会自动在 Intune 中注册。 自动注册的好处在于，用户可以单步执行过程。 否则，他们必须通过仅限 MDM 注册单独注册并重新输入其凭据。 用户在初始 Windows OOBE 或“设置”期间以这种方式注册。 设备在 Intune 中被标记为企业所有的设备。
- Autopilot - 自动执行 Azure AD 联接并将新的企业所有的设备注册到 Intune。 此方法简化了开箱即用体验，且无需将自定义操作系统映像应用于设备。 当管理员使用 Intune 管理 Autopilot 设备时，他们可以在注册后管理策略、配置文件、应用等内容。 有四种类型的 Autopilot 部署: 自部署模式(适用于展台、数字标牌或共享设备)、用户驱动模式(适用于传统用户)、适用于预配部署的 Windows Autopilot 使合作伙伴或 IT 人员能够预配运行 Windows 10 或 Windows 11 的电脑，以使其完全配置且可用于业务，以及适用于现有设备的 Autopilot 使你能够轻松地将最新版本的 Windows 部署到现有设备。

有关其他选项（包括注册 BYOD Windows 设备），请参阅 [在 Microsoft Intune 中注册 Windows 设备](/mem/intune/fundamentals/deployment-guide-enrollment-windows)。

## <a name="iosipados-and-ipados-enrollment"></a>iOS/iPadOS 和 iPadOS 注册

对于用户所有的(BYOD)设备，可以允许用户使用以下其中一种方法注册其个人设备以进行 Intune 管理。
- 设备注册是你可能认为的典型 BYOD 注册。 它为管理员提供各种管理选项。
- 用户注册是更简化的注册流程，为管理员提供设备管理选项子集。 此功能目前处于预览阶段。

对于为其用户购买设备的组织，Intune 支持以下 iOS/iPadOS 公司所有的设备注册方法:
- Apple 的自动设备注册 (ADE)
- Apple School Manager
- Apple Configurator 设置助理注册
- Apple Configurator 直接注册

有关详细信息，请参阅 [在 Microsoft Intune 中注册 iOS 和 iPadOS 设备](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)。

## <a name="android-enrollment"></a>Android 注册 

有多种选项可用于 Android 注册，具体取决于设备类型、要支持的注册类型，以及正在使用的 Android 版本甚至是制造商(特别是 Samsung)等内容。 大多数组织为其最终用户使用 Android 工作配置文件，尤其是在 BYOD 方案中。 

使用 Android 工作配置文件后，最终用户的信息会清楚地与数据容器以及供工作和个人使用的单独应用分开。 对于用户来说，要注册设备并仍然维护其自身数据的隐私和企业数据的安全性，这是一种理想的方式。 

但是，如果你的组织提供 Android 设备，则你可能会选择使用所谓的完全托管（用户关联）或专用（无用户关联）设备。

要了解有关 Android 注册的更多信息，请参阅 [在 Microsoft Intune 中注册 Android 设备](/mem/intune/fundamentals/deployment-guide-enrollment-android)。

## <a name="macos-enrollment"></a>macOS 注册

对于许多 IT 组织来说，macOS 注册可能是一个棘手的问题。 除非大多数用户都是 Mac 用户，否则可能无法在很大程度上管理这些类型的设备。 如果有少量 macOS 用户，则我们推荐仅限 Intune 注册。 如果有大量 macOS 用户，则我们推荐 Intune + Jamf 注册。  
- 仅限 Intune 注册 — 这适用于 macOS 设备的基本管理。 它需要执行手动流程，就像大多数其他基于用户的注册选项一样。 但是，如果有少量 Mac 设备，则这可能比仅为少数用户设置完整的自动化基础结构更简单。 使用仅限 Intune 注册能够部署证书、密码配置和应用程序等内容。 还可以配置合规性策略并启发条件访问以及强制执行加密和设备擦除的功能。 
- Intune 和 Jamf 注册 — 对于那些寻求对 Mac 管理的最深入支持的人员，我们凭借适用于条件访问的 Jamf + Intune 提供了一种出色的解决方案，它结合了 Jamf 的大量 Mac 管理功能和 Intune 合规性，以启用条件访问。 在此方案中，你仍然正在使用 Jamf 以完全托管设备，同时能够从 Jamf 接收这些信号以提高安全性。

要了解有关 macOS 注册的更多信息，请参阅 [在 Microsoft Intune 中注册 macOS 设备](/mem/intune/fundamentals/deployment-guide-enrollment-macos)。

## <a name="next-steps"></a>后续步骤

转到步骤 [3. 使用 Intune 设置设备的合规性策略](manage-devices-with-intune-compliance-policies.md)。

