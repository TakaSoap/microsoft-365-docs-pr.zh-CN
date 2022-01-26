---
title: 解决 Microsoft Defender for Endpoint 中的 SIEM 工具集成问题
description: 解决将 SIEM 工具与 Microsoft Defender for Endpoint 一同使用时可能出现的问题。
keywords: 疑难解答， siem， 客户端密码， 密码
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
ms.openlocfilehash: b6ed0342183734d9b4feb1c20a6c4059b77e64d6
ms.sourcegitcommit: 986ea76ecaceb5fe6b9616e553003e3c5b0df2e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2022
ms.locfileid: "62213949"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a>SIEM 工具集成问题疑难解答

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)。

在 SIEM 工具中拉取检测时，你可能需要解决问题。

此页面提供了解决可能遇到的问题的详细步骤。

## <a name="learn-how-to-get-a-new-client-secret"></a>了解如何获取新的客户端密码

如果你的客户端密码过期，或者如果你错位了启用 SIEM 工具应用程序时提供的副本，你将需要获取一个新密码。

1. 登录到 [Azure 管理门户](https://portal.azure.com)。

2. 选择“Azure Active Directory”。

3. 选择租户。

4. 单击 **"应用注册"。** 然后在"应用程序"列表中，选择应用程序。

5. 选择 **"&** 密码"部分，单击"新建客户端密码"，然后提供说明并指定有效期。

6. 单击“**保存**”。 将显示键值。

7. 复制值并将其保存在安全的位置。

## <a name="error-when-getting-a-refresh-access-token"></a>获取刷新访问令牌时出错

如果在使用威胁情报 API 或 SIEM 工具时尝试获取刷新令牌时遇到错误，则需要在 Azure Active Directory 中添加相关应用程序的回复 URL。

1. 登录到 [Azure 管理门户](https://ms.portal.azure.com)。

2. 选择“Azure Active Directory”。

3. 选择租户。

4. 单击 **"应用注册"。** 然后在"应用程序"列表中，选择应用程序。

5. 添加以下 URL：
   - 对于欧盟： `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`
   - 对于英国： `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`
   - 对于美国  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` ：。

6. 单击“**保存**”。

## <a name="error-while-enabling-the-siem-connector-application"></a>启用 SIEM 连接器应用程序时出错

如果在尝试启用 SIEM 连接器应用程序时遇到错误，请检查浏览器的弹出窗口阻止程序设置。 启用该功能时，它可能会阻止打开的新窗口。

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-troubleshootsiem-belowfoldlink)。

## <a name="related-topics"></a>相关主题

- [将检测拉取到 SIEM 工具](configure-siem.md)

