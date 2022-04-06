---
title: Android 上Microsoft Defender for Endpoint的新增功能
description: 了解 Android 上旧版Microsoft Defender for Endpoint的主要更改。
keywords: microsoft， defender， Microsoft Defender for Endpoint， mac， 安装， macos， whatsnew
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: 48d6ef27e71f89f6a81ac3c77ea17cf60dc90ee1
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664559"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-android"></a>Android 上Microsoft Defender for Endpoint的新增功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

## <a name="microsoft-defender-for-endpoint-is-now-microsoft-defender-in-the-play-store"></a>Microsoft Defender for Endpoint现在是 Play 商店中的 Microsoft Defender

Microsoft Defender for Endpoint现已在游戏商店中作为 **Microsoft Defender** 提供。 通过此更新，该应用将作为预览版提供给 **美国区域中的使用者** - 根据你使用工作或个人帐户登录应用的方式，你将有权访问适用于Microsoft Defender for Endpoint的功能或适用于个人的 Microsoft Defender 功能。 有关更多详细信息，请参阅 [此博客](https://www.microsoft.com/en-us/microsoft-365/microsoft-defender-for-individuals) 。

## <a name="threat-and-vulnerability-management"></a>威胁和漏洞管理

2022 年 1 月 25 日，我们宣布在 Android 和 iOS 上正式推出威胁和漏洞管理。 有关详细信息，请参阅 [此处的 Techcommunity 帖子](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-general-availability-of-vulnerability-management/ba-p/3071663)。

## <a name="upcoming-permission-changes-for-microsoft-defender-for-endpoint-running-android-11-or-later-nov-2021"></a>2021 年 11 月 11 日 (运行 Android 11 或更高版本的Microsoft Defender for Endpoint即将进行的权限更改) 

发布版本：1.0.3501.0301 发布月：2021 年 11 月Microsoft Defender for Endpoint发布了 [Google](https://developer.android.com/distribute/play-policies#APILevel30) 升级到 Android API 30 所需的此更新。 对于运行 Android 11 或更高版本的设备，此更改将提示用户寻求 [对新存储权](https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play)限的访问权限。 用户在使用版本 1.0.3501.0301 或更高版本更新 Defender 应用后，需要接受此新的存储权限。 这将确保 Defender for Endpoint 的应用安全功能能够正常运行，而不会造成任何中断。 有关详细信息，请查看以下部分。

**这将如何影响你的组织：** 如果在运行 Android 11 或更高版本的设备上使用Microsoft Defender for Endpoint，并且更新了 Defender for Endpoint 以发布内部版本 1.0.3501.0301 或更高版本，这些更改将生效。

> [!NOTE]
> 管理员无法通过Microsoft Endpoint Manager将新的存储权限配置为"自动批准"。 用户需要采取措施来提供对此权限的访问权限。

- **用户体验：** 用户将收到一条通知，指示缺少应用安全权限。 如果用户拒绝此权限，"应用安全"功能将在设备上关闭。 如果用户不接受或拒绝权限，则在解锁设备或打开应用时，在获得批准之前，他们将继续收到提示。

> [!NOTE]
> 如果你的组织正在预览"篡改保护"功能，并且用户在更新到最新版本后的 7 天内未授予新的存储权限，则用户可能会失去对公司资源的访问权限。

**准备工作**：

通知用户和支持人员 (适用) 用户在更新 Defender for Endpoint 以生成 1.0.3501.0301 或更高版本后出现提示时，需要接受新权限。 若要接受权限，用户应：

1. 点击 Defender for Endpoint 应用内通知或打开 Defender for Endpoint 应用。 用户将看到一个屏幕，其中列出了所需的权限。 存储权限旁边将缺少绿色复选标记。

2. 点击 **"开始**"。

3. 点击" **允许访问"开关以管理所有文件。**

4. 设备现在受到保护。

  > [!NOTE]
  > 此权限允许Microsoft Defender for Endpoint访问用户设备上的存储，这有助于检测和删除恶意和不需要的应用。 Microsoft Defender for Endpoint仅访问/扫描 Android 应用包文件 (.apk) 。 在具有工作配置文件的设备上，Defender for Endpoint 仅扫描与工作相关的文件。
