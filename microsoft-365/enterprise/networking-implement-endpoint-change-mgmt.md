---
title: 步骤 4：计划 URL 和 IP 地址更改
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ''
ms.openlocfilehash: dacd2ad83bdeb106ae398e8223f457c66a12b598
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073222"
---
# <a name="step-4-plan-for-url-and-ip-address-changes"></a>步骤 4：计划 URL 和 IP 地址更改

** 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

>[!Note]
>此步骤需要完成[步骤 3](networking-configure-proxies-firewalls.md)。如果尚未完成步骤 3，请跳到[步骤 5](networking-optimize-tcp-performance.md)。
>

全局 Microsoft 365 网络所使用的 URL 和 IP 地址会随时间而更改，因此，请务必要计划这些终结点的更新。例如，可能需要针对以下情况重新配置安全外围设备：

- 需要不受阻碍地进行处理的新服务的新 URL
- 针对已弃用服务删除的 URL
- 针对 Internet 上的新 Microsoft 网络位置和服务器的新 IP 地址范围 
- 针对不同服务的 IP 地址范围中的更改

有关针对终结点中的更改建立实施计划的详细信息（包括通知更改），请参阅[管理 Office 365 终结点集成](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration)和[管理 Office 365 终结点代理](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies)。

作为临时检查点，请查看对应于此步骤的[退出条件](networking-exit-criteria.md#crit-networking-step4)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[优化客户端和 Office 365 服务性能](networking-optimize-tcp-performance.md)|
