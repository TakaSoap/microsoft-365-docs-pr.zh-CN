---
title: 第 3 步。 使用 Intune 设置设备的合规性策略
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
- m365solution-managedevices
- m365solution-scenario
ms.custom: ''
keywords: ''
description: ''
ms.openlocfilehash: 2207f7ef3988c83a527cbd046ad059ca225d411d
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61301350"
---
# <a name="step-3-set-up-compliance-policies-for-devices-with-intune"></a>步骤 3. 使用 Intune 设置设备的合规性策略

通过将设备注册到管理中，可以实现更高的安全性和对环境中数据的控制。 [第 2 步. 将设备注册到管理](manage-devices-with-intune-enroll.md)详细介绍了如何使用 Intune 和 Autopilot 完成此操作。 本文介绍下一步，即配置设备符合性策略。 

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