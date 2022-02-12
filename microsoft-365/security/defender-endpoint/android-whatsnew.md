---
title: Android 版 Microsoft Defender for Endpoint 的新增功能
description: 了解 Android 上早期版本的 Microsoft Defender for Endpoint 的主要更改。
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
ms.collection:
- m365-security-compliance
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: 1e235329fa57a703ab678049dd0da2d4f135de99
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2022
ms.locfileid: "62767349"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-android"></a>Android 版 Microsoft Defender for Endpoint 的新增功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

## <a name="microsoft-defender-for-endpoint-is-now-microsoft-defender-in-the-play-store"></a>Microsoft Defender for Endpoint 现在是 Play 应用商店中的 Microsoft Defender

Microsoft Defender for Endpoint 现已在游戏应用商店 **中作为 Microsoft Defender** 提供。 通过此更新，应用将在美国地区的消费者中作为预览 **提供 - 基于** 你使用你的工作或个人帐户登录应用，你将有权访问适用于终结点的 Microsoft Defender 功能或适用于个人 Microsoft Defender 的功能。 有关详细信息 [，请参阅此](https://www.microsoft.com/en-us/microsoft-365/microsoft-defender-for-individuals) 博客。

## <a name="threat-and-vulnerability-management"></a>威胁和漏洞管理

2022 年 1 月 25 日，我们宣布在 Android 和 iOS 上正式发布威胁和漏洞管理。 有关详细信息，请参阅此处 [的 techcommunity 文章](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-general-availability-of-vulnerability-management/ba-p/3071663)。

## <a name="upcoming-permission-changes-for-microsoft-defender-for-endpoint-running-android-11-or-later-nov-2021"></a>2021 年 11 月 2021 年 11 月 (适用于运行 Android 11 或更高版本的终结点的 Microsoft Defender) 

发布版本：1.0.3501.0301 发布月：2021 年 11 月 Microsoft Defender for Endpoint 已发布 [Google](https://developer.android.com/distribute/play-policies#APILevel30) 升级到 Android API 30 所需的此更新。 对于运行 Android 11 或更高版本的设备[](https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play)，此更改将提示用户寻找新存储权限的访问权限。 用户使用版本 1.0.3501.0301 或更高版本更新 Defender 应用后，需要接受此新的存储权限。 这将确保 Defender for Endpoint 的应用安全功能在没有任何中断的情况下正常运行。 有关详细信息，请查看以下部分。

**这将对组织产生怎样的影响：** 如果你正在运行 Android 11 或更高版本的设备上使用 Microsoft Defender for Endpoint 并更新了适用于 Endpoint 的 Defender 以发布版本 1.0.3501.0301 或更高版本，这些更改将生效。

> [!NOTE]
> 管理员无法将新的存储权限配置为"自动批准"，Microsoft Endpoint Manager。 用户需要采取措施才能提供对此权限的访问权限。

- **用户体验：** 用户将收到一条通知，指示缺少应用安全权限。 如果用户拒绝此权限，将在设备上关闭"应用安全性"功能。 如果用户不接受或拒绝权限，他们将继续在解锁设备或打开应用时收到提示，直到应用获得批准。

> [!NOTE]
> 如果您的组织正在预览"防篡改保护"功能，并且用户未在更新到最新版本的 7 天内授予新的存储权限，则用户可能会失去对公司资源的访问权限。

**准备工作**：

通知用户和技术支持 (如适用) 当用户将 Defender for Endpoint 更新为生成 1.0.3501.0301 或更高版本后，系统提示用户需要接受新权限。 若要接受权限，用户应：

1. 点击 Defender for Endpoint 应用内通知或打开 Defender for Endpoint 应用。 用户将看到一个屏幕，其中列出了所需的权限。 该权限旁边将缺少绿色存储标记。

2. 点击 **"开始"**。

3. 点击"允许访问 **"的切换以管理所有文件。**

4. 设备现在受保护。

  > [!NOTE]
  > 此权限允许 Microsoft Defender for Endpoint 访问用户设备上存储，这有助于检测和删除恶意和不需要的应用。 Microsoft Defender for Endpoint 仅访问/扫描 Android (.apk) 文件。 在具有工作配置文件的设备上，Defender for Endpoint 仅扫描与工作相关的文件。
