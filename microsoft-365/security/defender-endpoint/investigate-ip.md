---
title: 调查与警报关联的 IP 地址
description: 使用调查选项检查设备和外部 IP 地址之间可能的通信。
keywords: 调查， 调查， IP 地址， 警报， Microsoft Defender for Endpoint， 外部 IP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 6ee90a1d39d873eb01eaf4c586b612bfe5a6fac8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192747"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a>调查与 Microsoft Defender for Endpoint 警报关联的 IP 地址

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)。

检查你的设备和外部 Internet 协议与 IP 地址 () 通信。

标识组织中与可疑或已知的恶意 IP 地址通信的所有设备，如命令和控制 (C2) 服务器，有助于确定潜在的泄露范围、关联的文件和受感染的设备。

您可以在 IP 地址视图中的以下部分中查找信息：

- 全球 IP
- 反向 DNS 名称
- 与此 IP 相关的警报
- 组织中 IP
- 普遍程度

## <a name="ip-worldwide-and-reverse-dns-names"></a>IP 全球和反向 DNS 名称

"IP 地址详细信息"部分显示 IP 地址的属性，如其 ASN 及其反向 DNS 名称。

## <a name="alerts-related-to-this-ip"></a>与此 IP 相关的警报

" **与此 IP 相关的警报** "部分提供了与该 IP 关联的警报列表。

## <a name="ip-in-organization"></a>组织中 IP

" **组织中的 IP"** 部分提供有关组织中 IP 地址的普遍程度的详细信息。

## <a name="prevalence"></a>普遍程度

" **普遍** 程度"部分显示已连接到此 IP 地址的设备数，以及第一次和最后一次看到 IP 时。 可以按时间段筛选此部分的结果;默认期限为 30 天。

## <a name="most-recent-observed-devices-with-ip"></a>最新观察到的具有 IP 的设备

" **最新观察到** 的具有 IP 的设备"部分提供有关在 IP 地址上观测到的事件和关联警报按时间顺序排列的视图。

**调查外部 IP：**

1. 从搜索栏 **下拉菜单中选择** **IP。**
2. 在"搜索"字段中 **输入** IP 地址。
3. 单击搜索图标或按 **Enter。**

将显示有关 IP 地址的详细信息，包括：注册详细信息 (（如果) 可用、反向 IP (例如域) 、在可选择的时间段) 内与此 IP 地址 (通信的组织中设备的普遍程度，以及组织中观测到与此 IP 地址通信的设备。

> [!NOTE]
> 将仅返回与组织中设备通信时观察到的 IP 地址的搜索结果。

使用搜索筛选器定义搜索条件。 您还可以使用时间线搜索框筛选组织中观测到与 IP 地址通信的所有设备的显示结果、与通信关联的文件和上次观测日期。

单击任何设备名称将进入该设备的视图，你可以继续调查报告的警报、行为和事件。

## <a name="related-topics"></a>相关主题

- [查看并组织 Microsoft Defender for Endpoint 警报队列](alerts-queue.md)
- [管理 Microsoft Defender for Endpoint 警报](manage-alerts.md)
- [调查 Microsoft Defender for Endpoint 警报](investigate-alerts.md)
- [调查与 Microsoft Defender for Endpoint 警报关联的文件](investigate-files.md)
- [调查 Microsoft Defender 终结点设备列表中的设备](investigate-machines.md)
- [调查与 Microsoft Defender for Endpoint 警报关联的域](investigate-domain.md)
- [调查 Microsoft Defender for Endpoint 中的用户帐户](investigate-user.md)
