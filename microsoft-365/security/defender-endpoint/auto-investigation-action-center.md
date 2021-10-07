---
title: 访问操作中心以查看修正操作
description: 使用操作中心查看自动调查后的详细信息和结果
keywords: 操作， 中心， autoir， 自动化， 调查， 响应， 修正
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: ce55054e921d3c97133dc1cdf3660e32f6b73d92
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60163140"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a>访问操作中心以查看修正操作

在自动调查期间和之后，将确定威胁检测的修正操作。 根据特定威胁以及 Microsoft [Defender for Endpoint](/windows/security/threat-protection) 如何为组织配置，将自动执行一些修正操作，而其他一些需要审批。 如果你是组织的安全运营团队的一员，可以在操作中心中查看挂起和已完成的 **修正操作**。 [](manage-auto-investigation.md#remediation-actions)


**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a> (新建！) 统一操作中心


我们很高兴宣布新的统一操作中心 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () ！

:::image type="content" source="images/mde-action-center-unified.png" alt-text="安全中心Microsoft 365中心。":::

下表将新的统一操作中心与以前的操作中心进行比较。

|新的统一操作中心  |以前的操作中心  |
|---------|---------|
|在一个位置列出设备和电子邮件的挂起和已完成操作 <br/> (Microsoft [Defender for Endpoint 和](microsoft-defender-endpoint.md) [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp)) |列出设备的挂起和已完成操作 <br/>  (Microsoft [Defender for Endpoint) ](microsoft-defender-endpoint.md)   |
|位于：<br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |位于：<br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| 在安全Microsoft 365，选择"**操作中心"。** <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="导航到安全中心Microsoft 365中心。"::: | In the Microsoft Defender 安全中心， choose **Automated investigations**  >  **Action center**. <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="从操作中心导航到Microsoft Defender 安全中心。":::  |

统一操作中心将跨 Defender for Endpoint 和 Defender for Office 365。 它定义所有修正操作的共同语言，并提供统一的调查体验。

如果您具有适当的权限以及以下一个或多个订阅，可以使用统一操作中心：

- [Defender for Endpoint](microsoft-defender-endpoint.md)
- [Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp)
- [Microsoft 365 Defender](/microsoft-365/security/mtp/microsoft-threat-protection)

> [!TIP]
> 若要了解更多信息，请参阅 [要求](/microsoft-365/security/mtp/prerequisites)。

## <a name="using-the-action-center"></a>使用操作中心

若要访问改进的安全中心的统一Microsoft 365中心：

1. 转到安全Microsoft 365中心 <https://security.microsoft.com> () 登录。
2. 在导航窗格中，选择操作 **中心**。

当你访问操作中心时，你将看到两个选项卡：**挂起的操作和****历史记录**。 下表总结了您将在每个选项卡上看到的内容：

|选项卡|说明|
|---|---|
|**挂起**|显示需要关注的操作的列表。 可以一次批准或拒绝一个操作，也可以选择多个操作（如果他们的操作类型与隔离文件 (相同) 。  <p> **提示**： [确保尽快审阅](manage-auto-investigation.md) (批准或拒绝) 挂起的操作，以便可以及时完成自动调查。|
|**历史记录**|充当审核日志的操作的一个组，例如： <ul><li>由于自动调查而采取的修正操作</li><li>安全运营团队批准的修正操作</li><li>运行的命令和在实时响应会话期间应用的修正操作</li><li>Microsoft Defender 防病毒 中威胁防护功能采取的修正Microsoft Defender 防病毒</li></ul> <p> 提供了一种撤消某些操作 (请参阅[Undo completed actions) 。](manage-auto-investigation.md#undo-completed-actions)|

可以在操作中心中自定义、排序、筛选和导出数据。

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="操作中心中的列和筛选器。":::

- 选择列标题以按升序或降序对项目进行排序。
- 使用时间段筛选器查看过去一天、一周、30 天或 6 个月的数据。
- 选择要查看的列。
- 指定要包含在每个数据页上的项目数。
- 使用筛选器仅查看要查看的项目。
- 选择 **"** 导出"将结果导出到.csv文件。

## <a name="next-steps"></a>后续步骤

- [查看和批准修正操作](manage-auto-investigation.md)
- [请参阅交互式指南：使用 Microsoft Defender for Endpoint 调查和修正威胁](https://aka.ms/MDATP-IR-Interactive-Guide)

## <a name="see-also"></a>另请参阅

- [解决 Microsoft Defender for Endpoint 中的误报/漏报](defender-endpoint-false-positives-negatives.md)
