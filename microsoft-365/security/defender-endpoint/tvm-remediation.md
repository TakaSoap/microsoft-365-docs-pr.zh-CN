---
title: 使用安全修复危险和漏洞管理
description: 修正通过安全建议发现的安全缺陷，并根据需要在安全危险和漏洞管理。
keywords: Microsoft Defender for Endpoint tvm 修正， Microsoft Defender for Endpoint tvm， 危险和漏洞管理， 威胁 & 漏洞管理， 威胁& 漏洞管理修正， tvm 修正 intune， tvm 修正 sccm
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8126021051f939a08fb0ea5ef6bd07d8f67c1662
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2021
ms.locfileid: "60883397"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a>使用安全修复危险和漏洞管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)。

## <a name="request-remediation"></a>请求修正

Microsoft Defender for Endpoint 中的 危险和漏洞管理 功能通过修正请求工作流填补了安全和 IT 管理员之间的空白。 安全管理员（如你可以请求 IT 管理员将漏洞从安全建议页面修正到Intune）

### <a name="enable-microsoft-intune-connection"></a>启用Microsoft Intune连接

若要使用此功能，请启用Microsoft Intune连接。 在 Microsoft 365 Defender 门户中，导航到 **设置** \> **高级** \> **功能"。** 向下滚动并查找Microsoft Intune **连接**。 默认情况下，切换处于关闭状态。 打开你的 **Microsoft Intune连接****切换。**

**注意**：如果启用了 Intune 连接，则创建修正请求时可以选择创建 Intune 安全任务。 如果未设置连接，则不显示此选项。

有关详细信息 [，请参阅使用 Intune 修正由 Microsoft Defender for Endpoint](/intune/atp-manage-vulnerabilities) 标识的漏洞。

### <a name="remediation-request-steps"></a>修正请求步骤

1. 转到安全 **门户中的"** 威胁和漏洞管理"导航Microsoft 365 Defender，**然后选择"推荐**[**安全建议"。**](tvm-security-recommendation.md)

2. 选择要请求修正的安全建议，然后选择"修正 **选项"。**

3. 填写表单，包括请求修正内容、适用的设备组、优先级、截止日期和可选注释。
    1. 如果选择"注意必需"修正选项，则选择截止日期将不可用，因为没有任何特定操作。

4. 选择 **"提交请求"。** 提交修正请求将在 危险和漏洞管理创建修正活动项，可用于监视此建议的修正进度。 这不会触发修正或对设备应用任何更改。

5. 将新请求通知 IT 管理员，让他们登录到 Intune 以批准或拒绝请求并启动程序包部署。

6. 转到" [**修正"**](tvm-remediation.md) 页以查看修正请求的状态。

如果你想要检查票证在 Intune 中的显示方式，请参阅使用 [Intune](/intune/atp-manage-vulnerabilities) 修正由 Microsoft Defender for Endpoint 标识的漏洞，了解详细信息。

> [!NOTE]
> 如果你的请求涉及修正超过 10，000 台设备，我们只能发送 10，000 台设备以修正 Intune。

确定组织的网络安全弱点并将其映射到可操作的安全建议后，开始创建安全任务。 [](tvm-security-recommendation.md) 通过与创建修正票证Microsoft Intune集成来创建任务。

通过修正安全建议，降低组织对漏洞的暴露程度，并增加安全配置。

## <a name="view-your-remediation-activities"></a>查看修正活动

当你从"安全建议"页提交修正请求时，它会启动修正活动。 将创建一个可在"修正危险和漏洞管理 **中** 跟踪的安全任务，并创建一个修正Microsoft Intune。

如果选择"注意必需"修正选项，则没有进度栏、票证状态或截止日期，因为我们可以监视任何实际操作。

进入"修正"页后，选择要查看的修正活动。 你可以按照修正步骤、跟踪进度、查看相关建议、导出到 CSV 或标记为完成。

:::image type="content" source="../../media/remediation-flyouteolswnew.png" lightbox="../../media/remediation-flyouteolswnew.png" alt-text="包含所选修正活动的&quot;修正&quot;页面示例，以及列出说明、IT 服务和设备管理工具以及设备修正的活动的飞出图":::

> [!NOTE]
> 已完成的修正活动保留期为 180 天。 若要使"修正"页以最佳方式执行，修正活动将在完成后 6 个月后删除。

### <a name="completed-by-column"></a>按列完成

使用"修正"页上的"完成者"列跟踪哪些人关闭了修正活动。

- **电子邮件地址**：手动完成任务的人的电子邮件
- **系统确认**：已修复所有设备 (任务已) 
- **N/A：** 信息不可用，因为我们不知道此旧任务的完成情况

:::image type="content" alt-text="由具有两行的列创建和完成。&quot;完成者&quot;的一行包含电子邮件示例，另一行显示系统确认。" source="images/tvm-completed-by.png":::

### <a name="top-remediation-activities-in-the-dashboard"></a>仪表板中的热门修正活动

查看 **威胁和** 漏洞管理 [仪表板中的 **热门修正** 活动](tvm-dashboard-insights.md)。 选择任意条目以转到"修正 **"** 页。 可以在 IT 管理员团队修正任务后将修正活动标记为已完成。

![Top 修正活动卡片示例，该表列出了根据安全建议生成的顶部活动。](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a>相关文章

- [威胁和漏洞管理概述](next-gen-threat-and-vuln-mgt.md)
- [仪表板](tvm-dashboard-insights.md)
- [安全性建议](tvm-security-recommendation.md)