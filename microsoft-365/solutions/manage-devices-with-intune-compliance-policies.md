---
title: 第 3 步。 使用 Intune 设置设备的合规性策略
ms.author: bcarter
author: brendacarter
f1.keywords:
- Create compliance policies
- Intune device compliance policy
manager: dougeby
audience: ITPro
description: 了解如何创建设备符合性策略，以指定设备访问环境的最低要求。
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-managedevices
- m365solution-scenario
ms.custom: ''
keywords: ''
ms.openlocfilehash: f93642984ecb2439ab6e4ad484ea4f6f3303c0ce
ms.sourcegitcommit: a06bb81fbd727a790a8fe6a3746b8a3cf62a6b24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2022
ms.locfileid: "64651358"
---
# <a name="step-3-set-up-compliance-policies-for-devices-with-intune"></a>步骤 3. 使用 Intune 设置设备的合规性策略

将设备注册到Intune使你能够实现对环境中数据的更大安全性和控制。 [步骤 2.注册设备以Intune](manage-devices-with-intune-enroll.md)详细介绍如何使用Intune完成此操作。 本文介绍下一步，即配置设备符合性策略。 

![管理设备的步骤](../media/devices/intune-mdm-step-2.png#lightbox)

你希望确保访问应用和数据的设备满足最低要求，例如它们受密码或固定保护，并且操作系统是最新的。 合规性策略是定义设备必须满足的要求的方法。 MEM 使用这些符合性策略将设备标记为符合或不符合。此二进制状态将传递给 Azure AD，后者可以在条件访问规则中使用此状态来允许或阻止设备访问资源。 

## <a name="configuring-device-compliance-policies"></a>配置设备符合性策略

本指南与建议的[零信任标识和设备访问策略](../security/office-365-security/microsoft-365-policies-configurations.md)紧密协调。

此图突出显示了定义合规性策略的工作适合整个零信任建议策略集的位置。 

[![零信任标识和设备访问策略](../media/devices/identity-device-define-compliance.png#lightbox)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/devices/identity-device-define-compliance.png)

在此图中，定义设备符合性策略是实现零信任框架中建议的保护级别的依赖项。 

要配置设备合规性策略，请使用[零信任标识和设备访问策略](../security/office-365-security/microsoft-365-policies-configurations.md)中规定的推荐指南和设置。 下表直接链接到在 Intune 中配置这些策略的说明，包括每个平台的建议设置。


|策略 |更多信息  |授权 |
|---------|---------|---------|
|[定义设备合规性策略](../security/office-365-security/identity-access-policies.md#define-device-compliance-policies)   |  一个策略对应一个平台       |  Microsoft 365 E3 或 E5       |
|  |         |         |

## <a name="next-steps"></a>后续步骤

转到[第 4 步. 需要正常且合规的设备](manage-devices-with-intune-require-compliance.md)，获取有关如何在 Azure AD 中创建条件访问规则的说明。