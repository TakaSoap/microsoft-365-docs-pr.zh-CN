---
title: 配置自动调查和修正功能
description: 在 Microsoft Defender for Endpoint 中设置自动调查和修正功能。
keywords: 配置， 设置， 自动化， 调查， 检测， 警报， 修正， 响应
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: 87e27933d051a0e1ed8b69c9e7e7dbe37a9d11e5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211269"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中配置自动调查和修正功能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

如果你的组织使用[Microsoft Defender for Endpoint (](/windows/security/threat-protection/) Defender for Endpoint [](/microsoft-365/security/defender-endpoint/automated-investigations)) ，自动调查和修正功能可以节省你的安全操作团队时间和精力。 如本 [博客文章所述](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)，这些功能模拟安全分析师调查和修正威胁的理想步骤。 [详细了解自动调查和修正](/microsoft-365/security/defender-endpoint/automated-investigations)。

配置自动调查和修正：

1. [打开功能](#turn-on-automated-investigation-and-remediation);和
2. [设置设备组](#set-up-device-groups)。

## <a name="turn-on-automated-investigation-and-remediation"></a>启用自动调查和修正

1. 作为全局管理员或安全管理员，转到Microsoft Defender 安全中心 () <https://securitycenter.windows.com> 并登录。
2. 在导航窗格中，选择 **"设置"。**
3. 在"**常规"** 部分，选择"**高级功能"。**
4. 同时启用 **自动调查和****自动解决警报**。

## <a name="set-up-device-groups"></a>设置设备组

1. In the Microsoft Defender 安全中心 (<https://securitycenter.windows.com>) ， on the **设置** page， under **Permissions，** select **Device groups**.
2. 选择 **+ 添加设备组**。
3. 创建至少一个设备组，如下所示：
   - 为设备组指定名称和说明。
   - 在 **"自动化级别"列表中**，选择一个级别，例如"完全 **- 自动修正威胁"。** 自动化级别确定是自动执行修正操作，还是仅在批准后执行修正操作。 若要了解更多信息，请参阅 [自动化调查和修正中的自动化级别](automation-levels.md)。
   - 在 **"成员** "部分，使用一个或多个条件来标识和包括设备。
   - 在 **"用户访问"**[选项卡上，Azure Active Directory](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context)应有权访问所创建设备组的用户组。
4. 完成 **设备** 组的设置后，选择"完成"。

## <a name="next-steps"></a>后续步骤

- [访问操作中心以查看挂起和已完成的修正操作](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [审阅和批准挂起的操作](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a>另请参阅

- [解决 Microsoft Defender for Endpoint 中的误报/漏报](defender-endpoint-false-positives-negatives.md)
