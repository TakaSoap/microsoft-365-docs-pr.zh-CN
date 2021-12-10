---
title: 设备的 Microsoft 安全功能分数
description: 你的设备分数显示设备在应用程序、操作系统、网络、帐户和安全控件中的统一安全配置状态。
keywords: Microsoft 设备安全分数，Microsoft Defender for Endpoint Microsoft 设备安全分数，安全分数，配置分数，危险和漏洞管理，安全控制，改进机会，一段时间的安全配置分数，安全状况，基线
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
ms.openlocfilehash: ccd5164839244250c5e2d908f41c35a706e0f49d
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61165554"
---
# <a name="microsoft-secure-score-for-devices"></a>设备的 Microsoft 安全功能分数

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威胁和漏洞管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)。

> [!NOTE]
> 配置分数现在是 Microsoft 危险和漏洞管理 Microsoft 安全分数的一部分。

你的设备分数显示在 危险和漏洞管理[门户](tvm-dashboard-insights.md)的 Microsoft 365 Defender 仪表板中。 设备的 Microsoft 安全分数越高，你的终结点就更能够抵御网络安全威胁攻击。 它反映你的设备跨以下类别的安全配置状态：

- 应用程序
- 操作系统
- 网络
- 帐户
- 安全控制措施

选择类别以转到" [**安全建议"页**](tvm-security-recommendation.md) 并查看相关建议。

## <a name="turn-on-the-microsoft-secure-score-connector"></a>打开 Microsoft 安全分数连接器

转发 Microsoft Defender for Endpoint 信号，使 Microsoft 安全分数能够查看设备安全状态。 转发数据的存储和处理位置与 Microsoft 安全分数数据位于同一位置。

更改可能需要几个小时才能反映在仪表板中。

1. 在导航窗格中，**转到"设置** \>  \> **终结点""常规** \> **高级功能"**

2. 向下滚动到 **Microsoft 安全分数**，将设置切换为 **"打开"。**

3. 选择“**保存首选项**”。

## <a name="how-it-works"></a>如何工作

> [!NOTE]
> Microsoft 设备安全分数当前支持通过组策略设置的配置。 由于当前部分 Intune 支持，可能通过 Intune 设置的配置可能会显示为错误配置。 如果你的组织使用 Intune 进行安全配置管理，请与 IT 管理员联系以验证实际配置状态。

Microsoft 设备安全分数卡中的数据是不断发现漏洞的过程的产品。 它将与配置发现评估聚合，持续：

- 将收集的配置与收集的基准进行比较以发现配置不当的资产
- 将配置映射到可修正或部分修正的漏洞 (风险) 
- 收集和维护最佳做法配置基准 (供应商、安全源、内部研究团队) 
- 收集并监视来自所有资产的安全控制配置状态更改

## <a name="improve-your-security-configuration"></a>改进安全配置

通过修正安全建议列表中的问题来改进安全配置。 当你这样做时，你的 Microsoft 设备安全分数会提高，并且你的组织可以更加抵御网络安全威胁和漏洞。

1. 从仪表板中的"Microsoft 设备安全分数"危险和漏洞管理，选择其中一个类别。 您将查看与类别相关的建议列表。 它将你访问" [**安全建议"**](tvm-security-recommendation.md) 页。 如果要查看所有安全建议，在进入"安全建议"页面后，清除搜索字段。

2. 在列表中选择一个项。 该飞出面板将打开，并包含与建议相关的详细信息。 选择 **修正选项**。

   :::image type="content" alt-text="安全控制相关的安全建议。" source="images/security-controls.png":::

3. 阅读说明，了解问题的上下文以及下一步要执行哪些操作。 选择截止日期、添加备注，然后选择"将所有修正 **活动** 数据导出到 CSV"，以便你可以将其附加到电子邮件进行跟踪。

4. **提交请求**。 你将看到一条确认消息，表明已创建修正任务。

   :::image type="content" alt-text="修正任务创建确认。" source="images/remediation-task-created.png":::

5. 保存 CSV 文件。

   :::image type="content" alt-text="保存 csv 文件。" source="images/tvm_save_csv_file.png":::

6. 向 IT 管理员发送后续电子邮件，并允许分配修正时间在系统中传播。

7. 再次查看 **仪表板上的 Microsoft 设备** 安全分数卡。 安全控制建议的数量将减少。 选择"**安全控件**"返回到"安全建议"页时，已解决的项目不会再列出。 你的 Microsoft 设备安全分数应增加。

> [!IMPORTANT]
>若要提高漏洞评估检测速率，请下载以下必需的安全更新，并部署在网络中：
>
> - 19H1 客户| [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)
> - RS5 客户| [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> - RS4 客户| [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
> - RS3 客户| [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
>
> 若要下载安全更新，请执行以下措施：
>
> 1. 转到 [Microsoft 更新目录](https://www.catalog.update.microsoft.com/home.aspx)。
> 2. 输入需要下载的安全更新 KB 编号，然后单击"搜索 **"。**

## <a name="related-topics"></a>相关主题

- [威胁和漏洞管理概述](next-gen-threat-and-vuln-mgt.md)
- [仪表板](tvm-dashboard-insights.md)
- [风险评分](tvm-exposure-score.md)
- [安全性建议](tvm-security-recommendation.md)
