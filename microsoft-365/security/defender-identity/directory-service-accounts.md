---
title: 在 Microsoft Defender 中为标识配置目录服务帐户
description: 了解如何配置 Microsoft Defender for Identity Directory Services 帐户Microsoft 365 Defender
ms.date: 08/15/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.openlocfilehash: 8928441e27215e75dc4456116c9a0e7890073852
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2021
ms.locfileid: "60962611"
---
# <a name="microsoft-defender-for-identity-directory-services-account-in-microsoft-365-defender"></a>Microsoft Defender for Identity Directory Services 帐户Microsoft 365 Defender

**适用于：**

- Microsoft 365 Defender
- Defender for Identity

本文介绍如何在 Microsoft 365 Defender 中配置[Microsoft Defender for Identity](/defender-for-identity) Directory Services[帐户](/microsoft-365/security/defender/overview-security-center)。

>[!IMPORTANT]
>作为与用户Microsoft 365 Defender的一部分，一些选项和详细信息从他们在 Defender for Identity 门户中的位置发生了更改。 请阅读下面的详细信息，了解在哪里可以找到熟悉的新功能和新功能。

## <a name="configure-directory-services-account"></a>配置目录服务帐户

若要将 [传感器与](sensor-health.md#add-a-sensor) Active Directory 域连接，需要配置目录服务帐户。

1. In <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender，</a>go to **设置** and then **Identities**.

    ![转到"设置"，然后转到"标识"。](../../media/defender-identity/settings-identities.png)

1. 选择 **"目录服务帐户"。** 你将看到哪些帐户与哪些域关联。

    ![目录服务帐户。](../../media/defender-identity/directory-service-accounts.png)

1. 如果您选择一个帐户，将打开一个包含该帐户设置的窗格。

    ![帐户设置。](../../media/defender-identity/account-settings.png)

1. 若要添加新的目录服务帐户，**请选择"创建新** 帐户"并填写"**帐户名称**"、"**域**"和"**密码"。** 还可以选择它是组托管服务帐户 ( gMSA) ，以及是否属于单标签 **域**。

    ![新建目录服务帐户。](../../media/defender-identity/new-directory-service-account.png)

1. 选择“**保存**”。

## <a name="see-also"></a>另请参阅

- [Microsoft Defender for Identity 传感器运行状况和设置](sensor-health.md)
