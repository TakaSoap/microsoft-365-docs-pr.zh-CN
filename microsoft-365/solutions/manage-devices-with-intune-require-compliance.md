---
title: 步骤 4. 使用 Intune 需要正常且合规的设备
ms.author: bcarter
author: brendacarter
f1.keywords:
- Conditional access policy
- Microsoft Intune
- Intune device management
manager: dougeby
audience: ITPro
description: 在 Azure AD 中创建条件访问策略，以要求符合要求的设备，在用户从任何位置任何设备工作时确保公司数据的安全。
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- Conditional access policy
- Microsoft Intune
- Intune device management
- m365solution-managedevices
- m365solution-scenario
ms.custom: ''
ms.openlocfilehash: 3549dda4551c1a1e7facad1fd665867f8339bf8f
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61940802"
---
# <a name="step-4-require-healthy-and-compliant-devices-with-intune"></a>步骤 4. 使用 Intune 需要正常且合规的设备

条件访问在允许访问服务之前提供对设备状态的其他验证。 除非指定条件，否则条件访问不起作用。 在[第 3 步. 设置合规性策略](manage-devices-with-intune-compliance-policies.md)中，你定义了符合性策略，这些策略指定设备访问环境时必须满足的最低要求。 在本文中，你将在 Azure AD 中创建相应的条件访问策略，以要求符合要求的设备。 这有助于确保公司数据的安全，同时使用户能够从任何设备和任何位置工作。

设置设备符合性策略并将其分配给用户组后，Intune 会让 Azure AD 知道设备是否合规。 若要将此状态用作访问条件，必须与 Azure AD 管理员协作，以创建条件访问规则，以要求兼容的电脑和移动设备。


![管理设备的步骤](../media/devices/intune-mdm-step-3.png#lightbox)

建议的零信任标识和设备访问规则集包括此规则。 请参阅[要求兼容的电脑和移动设备](../security/office-365-security/identity-access-policies.md#require-compliant-pcs-and-mobile-devices)，如下所示。


[![零信任标识和设备访问策略](../media/devices/identity-device-require-compliance.png#lightbox)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/devices/identity-device-require-compliance.png)



请确保：
- 使用分配给条件访问策略的用户组来协调分配给合规性策略的用户组。
- 在完全分配条件访问策略之前，请使用 What If 和审核模式功能测试条件访问策略。 这有助于你了解策略的结果。
- 根据要访问的数据和/或应用的保密性设置宽限期。 
- 确保合规性策略不会干扰任何法规或其他合规性要求。 
- 了解符合性策略的设备签入间隔。
- 避免合规性策略和配置文件之间发生冲突。 如果选择，请了解后果。

若要排查 Intune 中的设备配置文件（包括策略之间的冲突），请参阅 [Microsoft Intune 中的设备策略和配置文件的常见问题和答案](/mem/intune/configuration/device-profile-troubleshoot)。

注意：如果首先需要符合要求的电脑，但不要求移动设备，请参阅[要求兼容的电脑（但不要求手机和平板电脑）](../security/office-365-security/identity-access-policies.md) 

## <a name="next-steps"></a>后续步骤

转到步骤 [5. 在 Microsoft Intune 中部署设备配置文件](manage-devices-with-intune-configuration-profiles.md)
