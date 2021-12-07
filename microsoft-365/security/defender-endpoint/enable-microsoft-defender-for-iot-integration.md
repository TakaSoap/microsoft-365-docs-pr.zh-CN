---
title: 在 Microsoft Defender for Endpoint 中启用 Microsoft Defender for IoT 集成
description: 启用 Microsoft Defender for IoT 集成，以在未部署 MDE 的网络区域关注 IoT/OT 设备
keywords: 启用 siem 连接器， siem， 连接器， 安全信息和事件
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 540273109d0168e14b2f87b328b57f65d53b4c22
ms.sourcegitcommit: 6b24f65c987e5ca06e6d5f4fc10804cdbe68b034
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2021
ms.locfileid: "61320751"
---
# <a name="enable-microsoft-defender-for-iot-integration"></a>启用 Microsoft Defender for IoT 集成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)。

Microsoft Defender for Endpoint 现在可以与 Microsoft Defender for IoT 集成。 此集成通过 Microsoft Defender for IoT 提供的无代理监视功能扩展了设备发现功能。 这将帮助保护连接到 IT 网络的企业 IoT 设备，例如 Ip 语音 (VoIP) 设备、打印机和相机。 它允许组织利用一个可保护其所有 IoT 和操作技术 (OT) 解决方案。 有关详细信息，请参阅Enterprise [IoT 网络保护](/azure/defender-for-iot/organizations/overview-eiot.md)。

启用此集成后，适用于终结点的 Microsoft Defender 将增强可见性，以帮助查找、标识并保护网络中 IoT 设备。 由 Microsoft Defender for IoT 或 Microsoft Defender for Endpoint 发现的 IoT 设备将在两个门户之间自动同步。 这将提供完整 OT/IoT 清单的单个统一视图，以及其他 IT 设备 (工作站、服务器和移动) 。

Microsoft Defender for IoT 还包括可提供额外数据源的可部署网络传感器。 在集成中设置网络传感器可为你提供 IoT 和 OT 设备的最完整视图，特别是对于不存在 Microsoft Defender for Endpoint 传感器的网段，以及员工远程访问信息时。

## <a name="prerequisites"></a>先决条件

若要启用 Microsoft Defender for IoT，用户必须具有以下角色：

- 租户中的租户全局Azure Active Directory
- 将用于 Microsoft Defender for IoT 集成的 Azure 订阅的安全管理员

## <a name="enabling-the-microsoft-defender-for-iot-integration"></a>启用 Microsoft Defender for IoT 集成

1. 在门户的导航窗格中 [https://security.microsoft.com](https://security.microsoft.com/) ，选择设置 \>  \> **设备发现 Microsoft Defender for IoT"。**

    ![IoT 集成设置的图像。](images/enable-defender-for-iot.png)

2. **Select an Azure subscription** from the dropdown list of available subscriptions in your Azure Active Directory tenant and select **Save**.

## <a name="set-up-a-network-sensor"></a>设置网络传感器

选择 Azure 订阅后，可以添加网络传感器。

若要添加网络传感器，在"设置 **网络** 传感器"下，选择 **Microsoft Defender for IoT** 链接。 这会将你带到 Azure 门户中的载入传感器设置过程。 有关详细信息，请参阅在 Azure 门户中通过 [Defender for IoT 管理传感器](/azure/defender-for-iot/organizations/how-to-manage-sensors-on-the-cloud)。

## <a name="turn-off-subscription-integration"></a>关闭订阅集成

你可以从门户中的 Microsoft Defender for IoT 设置页面关闭 Azure 订阅 [https://security.microsoft.com](https://security.microsoft.com/) 集成。 关闭订阅后，你将不会再在 Microsoft Defender for Endpoint 设备清单中看到由 Microsoft Defender for IoT 发现的 IoT 设备。

## <a name="see-also"></a>另请参阅

- [设备发现概述](configure-device-discovery.md)
- [设备发现常见问题](device-discovery-faq.md)
