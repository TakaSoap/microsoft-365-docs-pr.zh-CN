---
title: 配置设备发现
description: 了解如何使用基本或标准发现Microsoft 365 Defender设备发现
keywords: 基本， 标准， 配置终结点发现， 设备发现
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 77dbdb290a0f8643bd24e1a3c561b823e5c2e4b3
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330589"
---
# <a name="configure-device-discovery"></a>配置设备发现

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


发现可以配置为标准模式或基本模式。 使用标准选项主动查找网络中设备，这将更好地保证终结点的发现并提供更丰富的设备分类。

你可以自定义用于执行标准发现的设备列表。 你可以在所有也支持此功能的已载入设备上启用标准发现 (当前 - Windows 10 或更高版本以及 Windows Server 2019 或更高版本设备仅) ，或者通过指定设备的设备标记来选择设备的子集。

## <a name="set-up-device-discovery"></a>设置设备发现

若要设置设备发现，请执行 Microsoft 365 Defender<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">门户中的以下配置步骤</a>：

导航到 **设置** > **Device 发现**

1. 如果要将"基本"配置为在已载入的设备上使用的发现模式，请选择" **基本** "，然后选择"保存 **"**
2. 如果你已选择使用标准发现，请通过指定设备标记选择用于活动探测的设备：所有设备或子集，然后选择"保存 **"**

> [!NOTE]
>标准发现使用各种 PowerShell 脚本主动探测网络中设备。 这些 PowerShell 脚本由 Microsoft 签名，从以下位置执行： `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`。 例如，`C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`。

## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a>在标准发现中排除设备的活动探测器

如果网络上有些设备不应主动扫描 (例如，用作另一个安全工具) 的热点的设备，则还可以定义排除项列表以防止它们被扫描。 请注意，仍可使用基本发现模式发现设备，也可通过多播发现尝试发现设备。 将被动发现这些设备，但不主动探测器。

你可以配置要排除在排除 **项页面中** 的设备。

## <a name="select-networks-to-monitor"></a>选择要监视的网络

Microsoft Defender for Endpoint 分析网络，并确定它是需要监视的公司网络还是可忽略的非公司网络。 为了将网络标识为公司，我们将关联所有租户客户端的网络标识符，如果组织中的大多数设备报告它们连接到了相同的网络名称，并且具有相同的默认网关和 DHCP 服务器地址，则假设这是企业网络。 通常选择监视公司网络。 但是，可以通过选择监视找到已载入设备的非公司网络来替代此决定。

可以通过指定要监视的网络来配置设备发现执行位置。 当网络受到监视时，可以在它上执行设备发现。

可在其中执行设备发现的网络列表显示在"受监视网络 **"** 页中。

> [!NOTE]
> 该列表显示了标识为公司网络的网络。 如果少于 50 个网络被标识为公司网络，则列表最多显示 50 个具有最多载入设备的网络。

受监视网络列表根据最近 7 天内网络上看到的设备总数进行排序。

可以应用筛选器以查看以下任一网络发现状态：

- **受监视的网络** - 执行设备发现的网络。
- **忽略的网络** - 此网络将被忽略，并且不会对它执行设备发现。
- **All** - 将显示受监视和忽略的网络。

### <a name="configure-the-network-monitor-state"></a>配置网络监视器状态

控制设备发现发生的位置。 受监视的网络是执行设备发现的地方，通常是公司网络。 还可以选择忽略网络或在修改状态后选择初始发现分类。

选择初始发现分类意味着应用默认的系统创建网络监视器状态。 选择系统创建的默认网络监视器状态意味着，将监视标识为公司的网络，并自动忽略标识为非公司网络的网络。

1. 选择 **设置 >设备发现"**。
2. 选择 **"受监视的网络"**。
3. 查看网络列表。
4. 选择网络名称旁边的三个点。
5. 选择是监视、忽略还是使用初始发现分类。

    > [!WARNING]
    >
    > - 选择监视未由 Microsoft Defender for Endpoint 标识为企业网络的网络可能会导致设备在企业网络外部发现，因此可能会检测家庭或其他非公司设备。
    > - 选择忽略网络将停止监控和发现该网络中的设备。 已发现的设备不会从清单中删除，但将不再更新，详细信息将一直保留到 Defender for Endpoint 的数据保留期到期。
    > - 在选择监视非公司网络之前，必须确保你有权这样做。 <br>

6. 确认要更改。

## <a name="explore-devices-in-the-network"></a>浏览网络中设备

可以使用以下高级搜寻查询获取有关网络列表中描述的每个网络名称的更多上下文。 查询列出了最近 7 天内连接到特定网络的所有已载入设备。

```kusto
DeviceNetworkInfo
| where Timestamp > ago(7d)
| where ConnectedNetworks  != ""
| extend ConnectedNetworksExp = parse_json(ConnectedNetworks)
| mv-expand bagexpansion = array ConnectedNetworks=ConnectedNetworksExp
| extend NetworkName = tostring(ConnectedNetworks ["Name"]), Description = tostring(ConnectedNetworks ["Description"]), NetworkCategory = tostring(ConnectedNetworks ["Category"])
| where NetworkName == "<your network name here>"
| summarize arg_max(Timestamp, *) by DeviceId
```

## <a name="get-information-on-device"></a>获取有关设备的信息

可以使用以下高级搜寻查询获取特定设备上的最新完整信息。

```kusto
DeviceInfo
| where DeviceName == "<device name here>" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId
```

## <a name="see-also"></a>另请参阅

- [设备发现概述](device-discovery.md)
- [设备发现常见问题解答](device-discovery-faq.md)
