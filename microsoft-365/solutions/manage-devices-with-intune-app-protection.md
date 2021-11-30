---
title: 步骤 1. 实现应用保护策略
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: dougeby
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
ms.custom: ''
keywords: ''
description: ''
ms.openlocfilehash: c6cee338f4f2f02d3d74da184be15c13d3230c00
ms.sourcegitcommit: 4af23696ff8b44872330202fe5dbfd2a69d9ddbf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2021
ms.locfileid: "61221084"
---
# <a name="step-1-implement-app-protection-policies"></a>步骤 1. 实现应用保护策略

Intune 应用保护策略 (APP) 有时称为移动应用程序管理 (MAM)，用于保护公司数据，即使设备本身并未托管也是如此。 使用此策略，能够在用户可能不愿意将其设备“注册”到管理中的工作上启用自带 (BYO) 和个人设备。 应用保护策略可确保不能将所指定应用中的公司数据复制并粘贴到设备上的其他应用。

![创建应用保护策略的步骤](../media/devices/intune-app-steps.png#lightbox)

在此图中：
- 借助 APP，Intune 在组织数据和个人数据之间创建了一道墙。 应用保护策略定义允许哪些应用访问你的数据。
- 如果用户使用其组织凭据登录，Intune 会在应用层应用策略，以防止将组织数据复制并粘贴到个人应用，并要求提供 PIN 才能访问此数据。
- 创建应用保护策略后，使用条件访问策略强制实施数据保护。 

此配置极大地提高了你的安全状况，并且几乎不会对用户体验造成任何影响。  员工可以使用他们了解和喜爱的 Office 和 Microsoft Teams 等应用，同时你的组织可以保护应用和设备中包含的数据。

如果你有需要保护的自定义业务线应用程序，目前可以使用应用包装工具来启用这些应用程序的 APP。 或者，可以使用 Intune App SDK 进行集成。 在你的应用使用了应用保护策略后，可由 Intune 进行管理，并可由 Intune 识别为托管应用。 有关使用 Intune 保护业务线应用程序的详细信息，请参阅 [使用 Microsoft Intune 为移动应用程序管理准备应用](/mem/intune/developer/apps-prepare-mobile-application-management)。

## <a name="configuring-mobile-app-protection"></a>配置移动应用保护

本指南与建议的 [零信任标识和设备访问策略](../security/office-365-security/microsoft-365-policies-configurations.md) 紧密协调。 在 Intune 中创建移动应用保护策略后，请与标识团队协作，以在强制实施移动应用保护的 Azure AD 中配置条件访问策略。 

此图突出显示了这两个策略（此图下面的表中也对此进行了说明）。

[![零信任标识和设备访问策略](../media/devices/identity-device-starting-point.png#lightbox)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/devices/identity-device-starting-point.png)

要配置这些策略，请使用 [零信任标识和设备访问策略](../security/office-365-security/microsoft-365-policies-configurations.md) 中规定的推荐指南和设置。 下表直接链接到在 Intune 和 Azure AD 中配置这些策略的说明。


|步骤  |策略  |更多信息  |授权  |
|---------|---------|---------|---------|
|1   |  [使用应用程序保护策略 (APP) 数据保护](../security/office-365-security/identity-access-policies.md#apply-app-data-protection-policies)       | 每个平台一个 Intune 应用保护策略（Windows、iOS/iPadOS、Android）。        | Microsoft 365 E3 或 E5        |
|2     | [需要经过批准的应用和应用保护](../security/office-365-security/identity-access-policies.md#require-approved-apps-and-app-protection)       |  使用 iOS、iPadOS 或 Android 对手机和平板电脑强制实施移动应用保护。   |  Microsoft 365 E3 或 E5       |
| | | | |

## <a name="next-steps"></a>后续步骤

转到“[第 2 步 - 使用 Intune 将设备注册到管理](manage-devices-with-intune-enroll.md)”。 