---
title: 确保设备配置正确
description: 正确配置设备以提升抵御威胁的整体复原能力，并增强检测和响应攻击的能力。
keywords: 载入， Intune 管理， Microsoft Defender for Endpoint， Microsoft Defender， Windows Defender， 攻击面减少， ASR， 安全基线
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5f5f3066f16a5f9cf39b2fcf4677b4906758fbe1
ms.sourcegitcommit: 87d994407fb69a747239b8589ad11ddf9b47e527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2021
ms.locfileid: "53595890"
---
# <a name="ensure-your-devices-are-configured-properly"></a>确保设备配置正确

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)。

借助正确配置的设备，你可以提升抵御威胁的整体复原能力，并增强检测和响应攻击的能力。 安全配置管理有助于确保你的设备：

- 加入到 Microsoft Defender for Endpoint
- 满足或超过 Defender for Endpoint 安全基线配置
- 已制定战略攻击面缓解措施

单击 **导航菜单中** 的"配置管理"以打开"设备配置管理"页。

![安全配置管理页](images/secconmgmt_main.png)

*设备配置管理页*

可以通过指向 Microsoft Intune 和 Microsoft 365 安全中心上的设备管理页面的直接深层链接，在组织级别跟踪配置状态并快速采取措施，以响应载入范围不佳、合规性问题以及攻击面缓解的不优化情况。

在执行此操作时，您将受益于：

- 设备上事件的全面可见性
- 用于处理原始事件和识别泄露活动和威胁指示器的强大威胁情报和强大的设备学习技术
- 配置为有效停止安装恶意攻击、劫持系统文件和进程、数据外脏及其他威胁活动的完整安全功能堆栈
- 优化了攻击面缓解，最大程度地提高了威胁活动的战略防御能力，同时最大限度地减少了对工作效率的影响

## <a name="enroll-devices-to-intune-management"></a>将设备注册到 Intune 管理

设备配置管理与 Intune 设备管理密切合作，以建立组织中设备的清单和基线安全配置。 你将能够在 Intune 托管的设备上跟踪和管理Windows 10问题。

在确保设备配置正确之前，请将其注册到 Intune 管理。 Intune 注册很可靠，并且具有多个适用于Windows 10注册选项。 有关 Intune 注册选项的详细信息，请阅读有关为设备Windows[注册的信息](/intune/windows-enroll)。

> [!NOTE]
> 若要Windows设备注册到 Intune，管理员必须已分配有许可证。 [阅读有关分配设备注册许可证的信息](/intune/licenses-assign)。

> [!TIP]
> 若要通过 Intune 优化设备管理， [请将 Intune 连接到 Defender for Endpoint](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)。

## <a name="obtain-required-permissions"></a>获取所需权限

默认情况下，只有已分配有 Azure AD 上的全局管理员或 Intune 服务管理员角色的用户才能管理和分配载入设备和部署安全基线所需的设备配置文件。

如果已分配有其他角色，请确保你拥有必要的权限：

- 设备配置的完整权限
- 对安全基线的完全权限
- 读取设备合规性策略的权限
- 读取对组织的权限

![intune 上所需的权限](images/secconmgmt_intune_permissions.png)

*Intune 上的设备配置权限*

> [!TIP]
> 若要了解有关在 Intune 上分配权限有关详细信息，[请阅读有关创建自定义角色。](/intune/create-custom-role#to-create-a-custom-role)

## <a name="in-this-section"></a>本节内容

主题|说明
:---|:---
[将设备载入到 Defender for Endpoint](configure-machines-onboarding.md)|跟踪 Intune 托管设备的载入状态，并通过 Intune 载入更多设备。 
[提高 Defender for Endpoint 安全基线的合规性](configure-machines-security-baseline.md)|跟踪基线合规性和不符合情况。 将安全基线部署到更多 Intune 托管的设备。
[优化 ASR 规则部署和检测](configure-machines-asr.md)|查看规则部署，然后使用安全中心内的影响分析工具Microsoft 365检测。

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)。
