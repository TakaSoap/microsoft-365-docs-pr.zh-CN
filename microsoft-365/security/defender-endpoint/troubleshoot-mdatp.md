---
title: Microsoft Defender for Endpoint 服务疑难解答
description: 查找在尝试访问服务时出现服务器错误等已知问题的解决方案和解决方法。
keywords: 排查Microsoft Defender for Endpoint、服务器错误、拒绝访问、凭据无效、无数据、仪表板门户、允许、事件查看器
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: bcd0f5ba70d154c40972c0b8035d1617a9e71966
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665835"
---
# <a name="troubleshoot-service-issues"></a>服务疑难解答

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)。

本部分解决了使用Microsoft Defender for Endpoint服务时可能出现的问题。

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a>服务器错误 - 由于凭据无效，访问被拒绝

如果在尝试访问服务时遇到服务器错误，则需要更改浏览器 Cookie 设置。
将浏览器配置为允许 Cookie。

## <a name="elements-or-data-missing-on-the-portal"></a>门户上缺少的元素或数据

如果Microsoft 365 Defender缺少某些元素或数据，代理设置可能会阻止它。

请确保 `*.security.microsoft.com` 包含代理允许列表。

> [!NOTE]
> 添加以下终结点时，必须使用 HTTPS 协议。

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a>Microsoft Defender for Endpoint服务显示事件查看器中的事件或错误日志

有关Microsoft Defender for Endpoint服务报告的事件 ID 列表，请参阅使用事件查看器查看[事件和错误](event-error-codes.md)。 本文还包含事件错误的故障排除步骤。

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a>Microsoft Defender for Endpoint服务在重新启动后无法启动，并显示错误 577

如果载入设备已成功完成，但重新启动后Microsoft Defender for Endpoint未启动并显示错误 577，请检查策略是否未禁用Windows Defender。

有关详细信息，请参阅[确保策略不会禁用Microsoft Defender 防病毒](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)。

## <a name="known-issues-with-regional-formats"></a>区域格式的已知问题

### <a name="date-and-time-formats"></a>日期和时间格式

时间和日期格式存在一些已知问题。

支持以下日期格式：

- MM/dd/yyyy
- dd/MM/yyyy

目前不支持以下日期和时间格式：

- 日期格式 yyyy/MM/dd
- 日期格式 dd/MM/yy
- 带有 yy 的日期格式。 只会显示 yyyy。
- ) 不支持 12 小时 AM/PM 格式 (不支持时间格式 HH：mm：ss。 仅支持 24 小时格式。

### <a name="use-of-comma-to-indicate-thousand"></a>使用逗号指示千

不支持在数字中使用逗号作为分隔符。 一个数字用逗号分隔以指示一千个的区域，只会看到使用点作为分隔符。 例如，15，5K 显示为 15.5K。

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-troubleshoot-belowfoldlink)。

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a>Microsoft Defender for Endpoint租户是在欧洲自动创建的

使用Microsoft Defender for Cloud监视服务器时，会自动创建Microsoft Defender for Endpoint租户。 默认情况下，Microsoft Defender for Endpoint数据存储在欧洲。

## <a name="related-topics"></a>相关主题

- [排查Microsoft Defender for Endpoint载入问题](troubleshoot-onboarding.md)
- [使用事件查看器查看事件和错误](event-error-codes.md)
