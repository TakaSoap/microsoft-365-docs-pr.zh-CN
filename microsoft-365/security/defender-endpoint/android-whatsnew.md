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
- m365initiative-defender-endpoint
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: c29570668f6fcf542ef3336c8053b395331fcce2
ms.sourcegitcommit: 27bf284b3bfe334eb98847798734625bd2ffafb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2021
ms.locfileid: "60792540"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-android"></a>Android 版 Microsoft Defender for Endpoint 的新增功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

## <a name="upcoming-permission-changes-for-microsoft-defender-for-endpoint-running-android-11-or-later-nov-2021"></a>2021 年 11 月 (运行 Android 11 或更高版本的适用于终结点的 Microsoft Defender) 
发布版本：1.0.3501.0301 发布月：2021 年 11 月

Google 要求 Microsoft Defender for Endpoint [升级到](https://developer.android.com/distribute/play-policies#APILevel30) Android API 30。 此更改将提示为运行 Android 11 [或更高版本](https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play) 的设备提供新的存储权限。 用户使用版本 1.0.3501.0301 或更高版本更新 Defender 应用后，需要接受此新的存储权限。 这将确保 Defender 的"应用安全性"功能正常运行，且不会中断。 有关详细信息，请参阅以下各节中的详细信息。

**这将对组织产生怎样的影响：**

如果你正在运行 Android 11 或更高版本的设备上使用 Microsoft Defender for Endpoint 并更新了 Defender 以发布版本 1.0.3501.0301 或更高版本，这些更改将生效。 管理员无法通过管理程序配置Microsoft Endpoint Manager;由于上述 Google API 更改，用户将需要采取措施。

- **用户体验：** 用户将收到一条通知，指示缺少应用安全权限。 如果用户拒绝此权限，将在设备上关闭"应用安全性"功能。 如果用户不接受或拒绝权限，他们将继续在解锁设备或打开应用时收到提示，直到应用获得批准。

>[!NOTE] 
> 如果您的组织正在预览"防篡改保护"功能，并且用户未在更新到最新版本的 7 天内授予新的存储权限，则用户可能会失去对公司资源的访问权限。

**准备工作**：

通知用户 (支持人员) 在将 Defender 更新为内部版本 1.0.3501.0301 或更高版本后提示用户需要接受新权限。 若要接受权限，用户应：

1. 点击 Defender 应用内通知或打开 Microsoft Defender for Endpoint 应用。 用户将看到一个屏幕，其中列出了所需的权限。 该权限旁边将缺少绿色存储标记。

2. 点击 **开始**。

3. 点击"允许访问 **"的切换以管理所有文件。** 

4. 设备现在受保护。

  >[!NOTE] 
  >此权限允许 Microsoft Defender for Endpoint 访问用户设备上存储，这有助于检测和删除恶意和不需要的应用。 仅 Microsoft Defender for Endpoint 访问/扫描 Android (.apk) 文件。 在具有工作配置文件的设备上，Denender 仅扫描与工作相关的文件。







