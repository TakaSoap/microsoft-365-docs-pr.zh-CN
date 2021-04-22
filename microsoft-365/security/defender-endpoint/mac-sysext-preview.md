---
title: 'Mac 版 Microsoft Defender for Endpoint - 系统扩展 (预览) '
description: 本文包含有关在 Mac 上尝试 Microsoft Defender for Endpoint 的系统扩展功能的说明。 此功能目前处于公共预览阶段。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 内核， 系统， 扩展， 加泰罗尼亚语
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: cc148bcc0b2623eaaa8d31ef50708174264fa3b2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934941"
---
# <a name="microsoft-defender-for-endpoint-on-macos---system-extensions-public-preview"></a>macOS 上的 Microsoft Defender for Endpoint - 系统扩展公共预览) 

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

为了与 macOS 演变保持一致，我们正在准备利用系统扩展而非内核扩展的 Mac 上的 Defender for Endpoint 更新。 此更新仅适用于 macOS 10 (10.15.4) macOS 的更高版本。

此功能目前处于公共预览阶段。 本文介绍了如何在设备上启用此功能。 可以在自己的设备上本地试用此功能，或者通过管理工具远程配置它。

这些步骤假定你已在设备上运行 Defender for Endpoint。 有关详细信息，请参阅此[此页面](microsoft-defender-endpoint-mac.md)。

## <a name="known-issues"></a>已知问题

- 我们已收到网络扩展干扰 Apple SSO Kerberos 扩展的报告。
- 产品的当前版本仍安装内核扩展。 内核扩展仅用作回退机制，将在此功能达到公共预览版之前删除。
- 我们仍在开发在 macOS 11 Big Sur 上正确部署和功能的产品版本。

## <a name="deployment-prerequisites"></a>部署先决条件

- 最低 macOS 操作系统版本 **：10.15.4**
- 最低产品版本 **：101.03.73**
- 你的设备必须在预览体验 **成员快速更新频道中**。 可以使用以下命令检查更新频道：

  ```bash
  mdatp health --field release_ring
  ```

  如果你的设备尚未在预览体验成员快速更新频道中，请从终端执行以下命令。 频道更新将在产品下次启动时生效 (安装下一个产品更新时，或设备在下次启动时) 。

  ```bash
  defaults write com.microsoft.autoupdate2 ChannelName -string Beta
  ```

  或者，如果你使用 JAMF 或 Intune (托管) ，你可以远程配置更新通道。 有关详细信息，请参阅在 Mac 上部署 Microsoft Defender for Endpoint 的更新 [：设置通道名称](mac-updates.md#set-the-channel-name)。

## <a name="deployment-steps"></a>部署步骤

请按照环境对应的部署步骤以及您尝试此功能的首选方法操作。

### <a name="manual-deployment"></a>手动部署

#### <a name="approve-the-system-extensions-and-enable-the-network-extension"></a>批准系统扩展并启用网络扩展

1. 满足所有部署先决条件后，重启设备以启动系统扩展审批和激活过程。

   你将看到一系列批准 Defender for Endpoint 系统扩展的系统提示。 必须批准 **系列** 的所有提示，因为 macOS 需要针对 Mac 上的 Defender for Endpoint 在设备上安装的每个扩展进行显式审批。
   
   对于每个审批，选择 **"打开安全首选项"，** 然后选择" **允许** "以允许系统扩展运行。

   > [!IMPORTANT]
   > 必须在后续审批之间关闭并重新打开系统首选项  >  **&隐私** 窗口。 否则，macOS 将不会显示下一个审批。

   > [!IMPORTANT]
   > 产品在返回到内核扩展之前有一分钟超时。 这可确保设备受到保护。
   >
   > 如果超过一分钟，请重新启动设备或使用 再次触发审批流来重新启动 `sudo killall -9 wdavdaemon` 守护程序。

   ![系统扩展审批弹出窗口](images/mac-system-extension-approval.png)

   ![系统扩展审批窗口](images/mac-system-extension-pref.png)

1. 批准系统扩展后，macOS 将提示批准以允许筛选网络流量。 单击"**允许"。**

   ![网络扩展审批弹出窗口](images/mac-system-extension-filter.png)

#### <a name="grant-full-disk-access-to-the-endpoint-security-system-extension"></a>授予对终结点安全系统扩展的完全磁盘访问权限

打开"**系统首选项**  >  **安全&**  >  **隐私"** 选项卡，并授予 Microsoft  Defender 终结点安全扩展的"完全磁盘 **访问权限"。**

![终结点安全系统扩展的完全磁盘访问](images/mac-system-extension-fda.png)

#### <a name="reboot-your-device"></a>重新启动设备

为了使更改生效，必须重新启动设备。

#### <a name="verify-that-the-system-extensions-are-running"></a>验证系统扩展是否正在运行

从终端运行以下命令：

```bash
mdatp health --field real_time_protection_subsystem
```

终端 `endpoint_security_extension` 输出指示产品正在使用系统扩展功能。

### <a name="managed-deployment"></a>托管部署

有关必须[为此新功能部署的新配置文件，请参阅 macOS Catalina 的新配置文件和较新版本的 macOS：JAMF。](mac-sysext-policies.md#jamf)

除了这些配置文件之外，请确保将目标设备配置为在预览体验成员快速更新频道中，如部署 [先决条件中所述](#deployment-prerequisites)。

在满足所有先决条件且已部署新配置文件的设备上，运行以下命令：

```bash
$ mdatp health --field real_time_protection_subsystem
```

如果此命令打印 `endpoint_security_extension` ，则产品正在使用系统扩展功能。

## <a name="validate-basic-scenarios"></a>验证基本方案

1. 测试欧洲计算机防病毒研究 (EICAR) 检测。 在终端窗口中，运行以下命令：

   ```bash
   curl -o eicar.txt https://secure.eicar.org/eicar.com.txt
   ```

   验证 EICAR 文件是否被隔离。 可以在用户界面中的"保护历史记录"页上，或通过使用以下命令从命令行验证文件的状态：

    ```bash
    mdatp threat list
    ```

2. 测试 EDR 和 DIY (终结点) 和响应。 在终端窗口中，运行以下命令：

   ```bash
   curl -o "MDATP MacOS DIY.zip" https://aka.ms/mdatpmacosdiy
   ```

   验证在计算机页面上针对 EICAR 和 EDR DIY 方案在门户中弹出的两个警报。

## <a name="frequently-asked-questions"></a>常见问题解答

- 问：为什么运行时 `kernel_extension` 仍看到 `mdatp health --field real_time_protection_subsystem` ？

    答：请重新参阅 [部署先决条件](#deployment-prerequisites) 部分，并仔细检查是否满足所有先决条件。 如果满足所有先决条件，请重启设备并再次检查。

- 问：macOS 11 Big Sur 何时受支持？

    答：我们正在努力添加对 macOS 11 的支持。 我们将向"新增功能" [页面发布更多信息](mac-whatsnew.md) 。
