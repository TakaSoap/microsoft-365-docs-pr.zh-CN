---
title: 配置托管安全服务提供商支持
description: 执行必要步骤以配置 MSSP 与 Microsoft Defender for Endpoint 的集成
keywords: 托管安全服务提供程序， mssp， 配置， 集成
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1a9a7e24bc08338549a78fcf9e9b2756701cd83f
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074578"
---
# <a name="configure-managed-security-service-provider-integration"></a>配置托管的安全服务提供商集成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)。

[!include[Prerelease information](../../includes/prerelease.md)]

您需要执行以下配置步骤以启用 MSSP 托管服务提供程序 (MSSP) 集成。

> [!NOTE]
> 本文中的以下术语用于区分服务提供商和服务使用者：
>
> - MSSP：提供监视和管理组织的安全设备的安全组织。
> - MSSP 客户：使用 MSSP 服务的组织。

该集成将允许 MSSP 执行以下操作：

- 获取对 MSSP 客户门户Microsoft 365 Defender的访问权限
- 获取电子邮件通知和
- 使用 SIEM 工具通过安全信息和事件管理 (警报) 警报

MSSP 客户需要授予对 Defender for Endpoint 租户的访问权限，以便 MSSP 可以访问门户，MSSP 客户才能执行这些操作。

通常，MSSP 客户执行初始配置步骤以向 MSSP 授予对安全中心租户Windows Defender访问权限。 授予访问权限后，MSSP 客户或 MSSP 可以执行其他配置步骤。

通常，需要执行以下配置步骤：

- **向 MSSP 授予对 Microsoft 365 Defender**

  此操作需要由 MSSP 客户执行。 它向 MSSP 客户授予对 MSSP 客户的 Defender for Endpoint 租户的访问权限。

- **配置发送到 MSSP 的警报通知**

  MSSP 客户或 MSSP 可以执行此操作。 这使 MSSP 知道需要为 MSSP 客户解决哪些警报。

- **将警报从 MSSP 客户的租户提取到 SIEM 系统**

  此操作由 MSSP 执行。 它允许 MSSP 在 SIEM 工具中获取警报。

- **使用 API 从 MSSP 客户的租户提取警报**

  此操作由 MSSP 执行。 它允许 MSSP 使用 API 获取警报。

## <a name="multi-tenant-access-for-mssps"></a>MSSP 的多租户访问

若要了解如何实现多租户委派访问，请参阅S [multi-tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)。

## <a name="related-topics"></a>相关主题

- [授予 MSSP 对门户的访问权限](grant-mssp-access.md)
- [访问 MSSP 客户门户](access-mssp-portal.md)
- [配置警报通知](configure-mssp-notifications.md)
- [从客户租户获取警报](fetch-alerts-mssp.md)
