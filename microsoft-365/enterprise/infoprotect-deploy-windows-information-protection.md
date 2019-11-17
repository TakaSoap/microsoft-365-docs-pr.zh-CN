---
title: 步骤 4：配置 Windows 信息保护
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 理解并部署 Microsoft 365 中的 Windows 信息保护。
ms.openlocfilehash: 23c3298545a288b459fd3bb858bb7c1d1714ee75
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627378"
---
# <a name="step-4-configure-windows-information-protection"></a>步骤 4：配置 Windows 信息保护

*此步骤可选，它适用于 Microsoft 365 企业版的 E3 和 E5 版本*

![第 6 阶段：信息保护](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

随着越来越多的个人设备被用于工作，应用和设备泄露私人组织数据的风险增加。 例如，员工无意中将未来产品的市场营销计划图片发送到社交媒体网站，或将包含高度机密信息的文件保存到其公有云存储。 

Windows 信息保护 (WIP) 有助于防止 Windows 10 设备上的这些类型的数据泄露。 有关详细信息，请参阅[使用 WIP 保护企业数据](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)。

在 Microsoft 365 企业版中，WIP 是 Windows 10 企业版和 Microsoft Intune 的组合，包括在订阅中。 

若要使用 Microsoft 365 企业版在组织中部署 WIP：

1. 在 Intune 中注册 Windows 设备。 你应该已经在[阶段 5：移动设备管理](mobility-infrastructure.md)过程中完成了此操作。
2. 创建[WIP 的 Intune 策略](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)。
  - 确保已填写“受保护应用列表”。
  - 选择 WIP 保护等级。

还可以将 WIP 与 [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm) 结合使用。 

请参阅 [WIP 最佳做法]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip)以获取详细信息。

作为临时检查点，请查看对应于此步骤的[退出条件](infoprotect-exit-criteria.md#crit-infoprotect-step4)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![第 5 步](./media/stepnumbers/Step5.png)|[配置 Office 365 数据丢失防护](infoprotect-data-loss-prevention.md)|


