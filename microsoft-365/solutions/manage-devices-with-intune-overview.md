---
title: 使用 Intune for 管理设备
ms.author: bcarter
author: brendacarter
f1.keywords:
- enroll devices into Intune
- manage device endpoints
- zero trust deployment stack
- device management with zero trust
manager: dougeby
audience: ITPro
ms.topic: article
description: 将终结点设备作为零信任安全体系结构的一部分注册到 Microsoft Intune，在为远程工作者构建防护的同时防御勒索软件。
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-managedevices
- m365solution-overview
ms.custom: ''
keywords: ''
ms.openlocfilehash: 2ca980a3f4f66b1b2d0a838f16c6ac7f138bc979
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2022
ms.locfileid: "64570076"
---
# <a name="manage-devices-with-intune-overview"></a>使用 Intune Overview 管理设备

企业级安全性的核心组件包括管理和保护设备。 无论是构建零信任安全体系结构、针对勒索软件强化环境，还是构建保护来支持远程工作者，管理设备都是策略的一部分。
虽然 Microsoft 365 包含用于管理和保护设备的多种工具和方法，但本指南使用 Microsoft Intune 逐步讲解 Microsoft 的建议。 如果你有以下情况，则这是适合你的指南：

- 计划通过 Azure AD 联接（包括混合 Azure AD 联接）将设备注册到 Intune。
- 计划手动将设备注册到 Intune。
- 允许具有针对应用和数据实施保护的计划的 BYOD 设备，以及/或将这些设备注册到管理中。

另一方面，如果环境包括共同管理计划（包括 Microsoft Endpoint Configuration Manager），请参阅[共同管理文档](/mem/configmgr/comanage/)为组织安排最佳路径。 如果你的环境包括 Windows 365 云电脑的计划，请参阅 [Windows 365 企业版文档](/windows-365/enterprise/)为组织安排最佳路径。

## <a name="why-manage-endpoints"></a>为什么要管理终结点？

新式企业具有可访问其数据的丰富多样的终结点。 此设置会产生巨大的攻击面，因此，终结点很容易成为零信任安全策略中最弱的一环。

随着世界转向远程或混合工作模式，在必要性的驱动下，用户现在可以随时随地在任何设备上工作，这在历史上是不曾有过的。 攻击者正在快速调整其策略以利用此变化。 许多组织在应对这些新的业务挑战时都面临资源受限的问题。 几乎一夜之间，公司都加速了数字化转型。 简单地说，人们的工作方式已经变了–我们不再期望仅从办公室和公司的设备访问大量公司资源。

了解访问公司资源的终结点是零信任设备策略的第一步。 通常，公司会主动保护电脑免受漏洞和攻击，而移动设备通常不受监视且没有保护。 为了确保你没有将数据暴露在风险中，我们需要监视每个终结点是否存在风险，并使用精细的访问控制来根据组织策略提供适当的访问级别。 例如，如果个人设备已越狱，则可以阻止访问，以确保企业应用程序不会暴露于已知漏洞。

本系列文章逐步讲解了用于管理访问资源的设备的建议过程。 如果你按照建议的步骤操作，你的组织将为你的设备及其访问的资源实现非常复杂的保护。

## <a name="implementing-the-layers-of-protection-on-and-for-devices"></a>在设备上、为设备实现保护层

保护设备、设备上的应用和数据、设备本身是一个多层的过程。 可以在非托管设备上获得一些保护。 将设备注册到管理后，可以实现更复杂的控制。 在终结点中部署威胁防护时，你将获得更多见解，并能够自动修正某些攻击。 最后，如果你的组织已投入工作来识别敏感数据、应用分类和标签以及配置数据丢失防护策略，则可以为终结点上的数据获取更精细的保护。

下图演示了为 Microsoft 365 和其他引入此环境的 SaaS 应用实现零信任安全状况的构建基块。 与设备相关的元素编号为 1 到 7。 这些是设备管理员将与其他管理员协调完成的保护层。

![Microsoft 365 零信任部署堆叠](../media/devices/m365-zero-trust-deployment-stack-devices.png#lightbox)

在此图中：

|&nbsp;|步骤|说明|许可要求|
|---|---|---|---|
|1|配置起始点零信任标识和设备访问策略|请与标识管理员合作[实现级别 2 应用保护策略 (APP) 数据保护](manage-devices-with-intune-app-protection.md)。 这些策略不需要管理设备。 在 Intune 中配置 APP 策略。 标识管理员将条件访问策略配置为需要批准的应用。|E3、E5、F1、F3、F5|
|2|将设备注册到管理中|此任务需要更多规划和时间来实现。 Microsoft 建议使用 Intune 注册设备，因为此工具提供最佳集成。 可通过多个选项注册设备，具体取决于平台。 例如，可以使用 Azure AD Join 或 Autopilot 注册 Windows 设备。 你需要查看每个平台的选项，并确定哪个注册选项最适合你的环境。 请参阅[步骤 3–将设备注册到管理](manage-devices-with-intune-enroll.md)以了解详细信息。|E3、E5、F1、F3、F5|
|3|配置符合性策略|你希望确保访问应用和数据的设备满足最低要求，例如设备受密码或固定保护，并且操作系统是最新的。 合规性策略是定义设备必须满足的要求的方法。 [3. 设置合规性策略](manage-devices-with-intune-compliance-policies.md)可帮助你配置这些策略。|E3、E5、F3、F5|
|4|配置企业（推荐）零信任标识和设备访问策略|现在，你的设备已注册，你可以与标识管理员合作，[优化条件访问策略来要求正常和合规的设备](manage-devices-with-intune-require-compliance.md)。|E3、E5、F3、F5|
|5|部署配置文件|与仅根据你配置的条件将设备标记为合规或不符合的设备符合性策略相反，配置文件实际上会更改设备上的设置配置。 可以使用配置策略来强化设备免受网络威胁。 请参阅[第 5 步. 部署配置文件](manage-devices-with-intune-configuration-profiles.md)。|E3、E5、F3、F5|
|6 |监视设备风险和对安全基线的符合性|在此步骤中，将 Intune 连接到 Microsoft Defender for Endpoint。 通过此集成，可以监视设备风险作为访问条件。 被发现处于风险状态的设备将被阻止。 还可以监视对安全基线的符合性。 转到[第 6 步. 监视设备风险和对安全基线的符合性](manage-devices-with-intune-monitor-risk.md)。|E5、F5|
|7 |使用信息保护功能实现数据丢失防护（DLP）|如果你的组织已投入工作来识别敏感数据和标记文档，则可以与信息保护管理员合作，[保护设备上的敏感信息和文档](manage-devices-with-intune-dlp-mip.md)。|E5，F5 符合性添加项|

## <a name="coordinating-endpoint-management-with-zero-trust-identity-and-device-access-policies"></a>使用零信任标识和设备访问策略协调终结点管理

本指南与建议的[零信任标识和设备访问策略](../security/office-365-security/microsoft-365-policies-configurations.md)紧密协调。 你将与标识团队合作，在 Azure AD 中将使用 Intune 配置的保护实施到条件访问策略中。

下面是建议的策略集的插图，其中包含将在 Intune/MEM 中执行的工作的步骤标注，以及你将帮助在 Azure AD 中协调的相关条件访问策略。

[![零信任标识和设备访问策略](../media/devices/identity-device-overview-steps.png#lightbox)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/devices/identity-device-overview-steps.png)

在此图中：

- 在步骤 1 中，[实现级别 2 应用保护策略 (APP)](manage-devices-with-intune-app-protection.md) 使用 APP 策略配置建议的数据保护级别。 然后，与标识团队合作，将相关的条件访问规则配置为需要使用此保护。
- 在步骤 2、3 和 4 中，使用 Intune/MEM 将设备注册到管理中，定义设备符合性策略，然后与标识团队协调，将相关的条件访问规则配置为仅允许访问合规设备。

<!---
## Managing change with users
--->

## <a name="enrolling-devices-vs-onboarding-devices"></a>注册设备与载入设备

如果遵循本指南，则将使用 Intune（或其他工具）将设备注册到管理中，你将载入设备以获取两项服务：

- Defender for Endpoint
- 终结点 DLP

下图详细说明了如何使用 Intune。

![注册和载入设备的过程](../media/devices/devices-enroll-onboard-process.png#lightbox)

在此图中：

1. 使用 Intune 将设备注册到管理。
2. 使用 Intune 将设备载入 Defender for Endpoint。
3. 载入到 Defender for Endpoint 的设备也已加入，以获取 Microsoft 365 符合性功能，包括终结点 DLP。

请注意，只有 Intune 正在管理设备。 载入是指设备能够与特定服务共享信息。 下表汇总了将设备注册到管理和载入特定服务的设备之间的差异。

|&nbsp;|注册|载入|
|---|---|---|
|Description|注册适用于管理设备。 注册设备后，可以使用 Intune 或配置服务器进行管理。|载入会将设备配置为使用 Microsoft 365 中的一组特定功能。 目前，载入适用于 Microsoft Defender for Endpoint 和 Microsoft 合规性功能。 <br/><br/> 在 Windows 设备上，载入涉及在 Windows Defender 中切换设置，该设置允许 Defender 连接到联机服务并接受应用于设备的策略。|
|范围|这些设备管理工具管理整个设备，包括将设备配置为满足特定目标，例如安全性。|载入仅影响应用的服务。|
|推荐的方法|Azure Active Directory 联接会自动将设备注册到 Intune。|Intune 是将设备载入到 Windows Defender for Endpoint 的首选方法，也是获取 Microsoft 365 合规性功能的首选。 <br/><br/> 请注意，使用其他方法载入到 Microsoft 365 合规性功能的设备不会自动注册 Defender for Endpoint。|
|其他方法|其他注册方法取决于设备的平台，以及设备是 BYOD 还是由组织管理。|其他用于载入设备的方法包括（按顺序建议）： <ul><li>配置管理器</li><li>其他移动设备管理工具（如果设备由某个工具管理）</li><li>本地脚本</li><li>用于载入非持久性虚拟桌面基础结构 (VDI) 设备的 VDI 配置包</li><li>组策略</li></ul>|

## <a name="learning-for-administrators"></a>面向管理员的学习

以下资源可帮助管理员了解有关使用 MEM 和 Intune 的概念。

[使用 Microsoft Endpoint Manager](/learn/modules/simplify-device-management-with-microsoft-endpoint-manager/) 简化设备管理说明：了解新式管理和 Microsoft Endpoint Manager 以及 Microsoft 365 中的业务管理工具如何简化所有设备的管理。

[设置 Microsoft Intune](/learn/modules/set-up-microsoft-intune/) 说明：Microsoft Intune 是 Microsoft Endpoint Manager 的一部分，可帮助你保护组织中人员用来提高工作效率的设备、应用、数据。 完成此模块后，你将设置 Microsoft Intune。 设置包括查看支持的配置、注册 Intune、添加用户和组、向用户分配许可证、授予管理员权限以及设置 MDM 机构。
