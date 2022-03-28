---
title: 启用 Microsoft Defender 标识评估环境
description: 在试用实验室或Microsoft 365 Defender环境中设置 Microsoft Defender for Identity，&配置传感器，并发现其他计算机上的本地管理员。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1be194035348bb8d414b37f16399fdcffe406063
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2022
ms.locfileid: "63755032"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a>启用 Microsoft Defender 标识评估环境

**适用于：**
- Microsoft 365 Defender

本文是设置 Microsoft Defender for Identity 评估环境过程中第 2 步（第 [2](eval-defender-identity-overview.md) 步）。 有关此过程详细信息，请参阅 [概述文章](eval-defender-identity-overview.md)。

使用以下步骤设置 Microsoft Defender for Identity 环境。 

:::image type="content" source="../../media/defender/m365-defender-identity-eval-enable-steps.png" alt-text="在 Microsoft Defender 评估环境中启用 Microsoft Defender 标识的步骤" lightbox="../../media/defender/m365-defender-identity-eval-enable-steps.png":::

- [步骤 1.设置 Defender for Identity 实例](#step-1-set-up-the-defender-for-identity-instance)
- [步骤 2.安装和配置传感器](#step-2-install-and-configure-the-sensor)
- [步骤 3.使用传感器在计算机中配置事件日志和代理设置](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [步骤 4.允许 Defender for Identity 识别其他计算机上的本地管理员](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a>步骤 1. 设置 Defender for Identity 实例

登录到 Defender for Identity 门户以创建实例，然后将此实例连接到 Active Directory 环境。 

|  步骤 | 说明     |更多信息  |
|---------|---------|---------|
|1     | 创建 Defender for Identity 实例        | [快速开始：创建 Microsoft Defender for Identity 实例](/defender-for-identity/install-step1)        |
|2     | 连接 Active Directory 林创建 Defender for Identity 实例   | [快速入门：连接 Active Directory 林](/defender-for-identity/install-step2)  |

## <a name="step-2-install-and-configure-the-sensor"></a>步骤 2. 安装和配置传感器

接下来，在本地环境的域控制器和 AD FS 服务器上下载、安装和配置 Defender for Identity 传感器。

|  步骤 | 说明     |更多信息  |
|---------|---------|---------|
|1     | 确定你需要多少个 Microsoft Defender for Identity 传感器。        | [为 Microsoft Defender for Identity 规划容量](/defender-for-identity/capacity-planning)   |
|2     | 下载传感器安装程序包  |  [快速入门：下载 Microsoft Defender for Identity 传感器安装程序包](/defender-for-identity/install-step3)   |
|3     | 安装 Defender for Identity 传感器    |  [快速入门：安装 Microsoft Defender for Identity 传感器](/defender-for-identity/install-step4)       |
|4     | 配置传感器       |  [配置 Microsoft Defender for Identity 传感器设置 ](/defender-for-identity/install-step5)   |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a>第 3 步。 使用传感器在计算机中配置事件日志和代理设置

在安装了传感器的计算机上安装，Windows事件日志集合和 Internet 代理设置以启用和增强检测功能。

|  步骤 | 说明     |更多信息  |
|---------|---------|---------|
|1     | 配置Windows事件日志集合         | [配置 Windows 事件集合](/defender-for-identity/configure-windows-event-collection)        |
|2     | 配置 Internet 代理设置        | [为 Microsoft Defender for Identity Sensor 配置终结点代理和 Internet 连接设置](/defender-for-identity/configure-proxy)        |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a>步骤 4. 允许 Defender for Identity 识别其他计算机上的本地管理员

Microsoft Defender for Identity 横向移动路径检测依赖于标识特定计算机上本地管理员的查询。 这些查询通过 SAM-R 协议使用 Defender for Identity Service 帐户执行。 

为了确保 Windows 客户端和服务器允许 Defender for Identity 帐户执行 SAM-R，除了网络访问策略中列出的配置帐户之外，还必须修改组策略以添加 Defender for Identity 服务帐户。 确保将组策略应用于除 **域控制器之外的所有计算机**。

有关如何执行此操作的说明，请参阅配置 [Microsoft Defender for Identity 以远程调用 SAM](/defender-for-identity/install-step8-samr)。 

## <a name="next-steps"></a>后续步骤

第 3 步（第 3 步/第 3 步 [：试用 Microsoft Defender 标识）](eval-defender-identity-pilot.md)

返回到评估 [Microsoft Defender 标识概述](eval-defender-identity-overview.md)

返回到评估和试点[计划概述Microsoft 365 Defender](eval-overview.md)
