---
title: 将非Windows设备载入 Microsoft Defender for Endpoint 服务
description: 配置非Windows设备，以便它们可以将传感器数据发送到 Microsoft Defender for Endpoint 服务。
keywords: 载入非Windows设备， macos， linux， 设备管理， 为终结点设备配置 Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c1c8e5fa990e37f4812b8e5429fdbf2fcbfa7b71
ms.sourcegitcommit: d78553deeba23d2f8238f10e64c2e27f235dc37f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2021
ms.locfileid: "60124729"
---
# <a name="onboard-non-windows-devices"></a>载入非 Windows 设备

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**平台**
- macOS
- Linux

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-nonwindows-abovefoldlink)。

Defender for Endpoint 为非安全平台Windows集中式安全Windows体验。 你将能够查看来自各种受支持操作系统 (操作系统或操作系统) 警报Microsoft 365 Defender更好地保护组织的网络。

你需要了解与 Defender for Endpoint 兼容的确切的 Linux 发行版和 macOS 版本，集成工作。 有关详细信息，请参阅：

- [Linux 上的 Microsoft Defender for Endpoint 系统要求](microsoft-defender-endpoint-linux.md#system-requirements)
- [macOS 上的 Microsoft Defender for Endpoint 系统要求](microsoft-defender-endpoint-mac.md#system-requirements)。

## <a name="onboarding-non-windows-devices"></a>载入非Windows设备

你需要执行以下步骤来载入非Windows设备：

1. 选择你的首选载入方法：

   - 对于 macOS 设备，你可以选择通过 Microsoft Defender for Endpoint 或第三方解决方案载入。 有关详细信息，请参阅 Mac 上的[Microsoft Defender for Endpoint。](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)

   - 对于其他非Windows设备，选择"通过第三Windows集成载入 **非集成设备"。**
    1. 在导航窗格中，选择"**合作伙伴和 API** \> **合作伙伴应用程序"。** 确保列出了第三方解决方案。
    2. 在 **"合作伙伴应用程序"** 页中，选择支持非Windows合作伙伴。
    3. 单击 **"** 查看"打开合作伙伴的页面。 按照页面上提供的说明进行操作。
    4. 创建帐户或订阅合作伙伴解决方案后，应进入一个阶段，要求贵组织的租户全局管理员接受来自合作伙伴应用程序的权限请求。 仔细阅读权限请求，确保它与所需的服务保持一致。

2. 按照第三方解决方案的说明运行检测测试。

## <a name="offboard-non-windows-devices"></a>载出非Windows设备

1. 按照第三方文档将第三方解决方案与 Microsoft Defender for Endpoint 断开连接。

2. 删除 Azure AD 租户中第三方解决方案的权限。
   1. 登录到 [Azure 门户](https://portal.azure.com)。
   2. 选择 **Azure Active Directory > Enterprise应用程序"。**
   3. 选择要离开的应用程序。
   4. 选择" **删除"** 按钮。

## <a name="related-topics"></a>相关主题

- [载入Windows设备](configure-endpoints.md)
- [载入服务器](configure-server-endpoints.md)
- [配置代理和 Internet 连接设置](configure-proxy-internet.md)
- [Microsoft Defender 终结点载入问题疑难解答](troubleshoot-onboarding.md)
