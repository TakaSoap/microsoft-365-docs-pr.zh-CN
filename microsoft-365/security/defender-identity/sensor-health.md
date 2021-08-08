---
title: Microsoft Defender for Identity 传感器运行状况和Microsoft 365 Defender
description: 了解如何配置 Microsoft Defender for Identity 传感器并监视其Microsoft 365 Defender
ms.date: 06/07/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: 0c2d8fd75b33903696682e6fd196ef4ce12ab2ca101cfe32e23fbce0614dd8a5
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53844469"
---
# <a name="microsoft-defender-for-identity-sensor-health-and-settings-in-microsoft-365-defender"></a>Microsoft Defender for Identity 传感器运行状况和Microsoft 365 Defender

**适用于：**

- Microsoft 365 Defender
- Defender for Identity

本文介绍如何在 Microsoft 365 Defender 中配置和监视[Microsoft Defender for Identity](/defender-for-identity) [Microsoft 365 Defender。](/microsoft-365/security/defender/overview-security-center)

>[!IMPORTANT]
>作为与用户Microsoft 365 Defender的一部分，一些选项和详细信息从他们在 Defender for Identity 门户中的位置发生了更改。 请阅读下面的详细信息，了解在哪里可以找到熟悉的新功能和新功能。

## <a name="view-defender-for-identity-sensor-settings-and-status"></a>查看 Defender for Identity 传感器设置和状态

1. In [Microsoft 365 Defender，](https://security.microsoft.com/)go to **设置** and then **Identities**.

    ![转到"设置"，然后转到"标识"](../../media/defender-identity/settings-identities.png)

1. 选择 **"传感器"** 页，其中显示所有 Defender for Identity 传感器。 对于每个传感器，你将看到其名称、域成员身份、版本号、如果更新应延迟、服务状态、更新状态、运行状况状态、运行状况问题的数量以及创建传感器的时间。

    [![传感器页面](../../media/defender-identity/sensor-page.png)](../../media/defender-identity/sensor-page.png#lightbox)

    >[!NOTE]
    >在 Defender for Identity 门户中，传感器设置和运行状况信息位于单独的位置。 请注意，Microsoft 365 Defender它们现在在同一页面上。

1. 如果选择" **筛选器"，** 可以选择哪些筛选器可用。 然后，对于每个筛选器，你可以选择要显示的传感器。

    [![传感器筛选器](../../media/defender-identity/sensor-filters.png)](../../media/defender-identity/sensor-filters.png#lightbox)

    ![筛选的传感器](../../media/defender-identity/filtered-sensor.png)

1. 如果选择其中一个传感器，将显示一个窗格，其中显示有关该传感器及其运行状况状态的信息。

    [![传感器详细信息](../../media/defender-identity/sensor-details.png)](../../media/defender-identity/sensor-details.png#lightbox)

1. 如果您选择任何运行状况问题，您将获得一个包含有关这些问题的更多详细信息的窗格。 如果您选择已关闭的问题，可以从此处重新打开它。

    ![问题详细信息](../../media/defender-identity/issue-details.png)

1. 如果选择" **管理传感器"，** 将打开一个窗格，可在其中配置传感器详细信息。

    ![管理传感器](../../media/defender-identity/manage-sensor.png)

    ![配置传感器详细信息](../../media/defender-identity/configure-sensor-details.png)

1. 在 **"传感器"** 页中，可以通过选择"导出"将传感器列表导出到.csv **文件。**

    ![导出传感器列表](../../media/defender-identity/export-sensors.png)

## <a name="add-a-sensor"></a>添加传感器

在 **"传感器"** 页面中，可以添加新的传感器。

1. 选择 **"添加传感器"。**

    ![添加传感器](../../media/defender-identity/add-sensor.png)

1. 将打开一个窗格，为您提供下载传感器安装程序的按钮和生成的访问密钥。

    ![下载安装程序和访问键](../../media/defender-identity/installer-access-key.png)

1. 选择 **"下载** 安装程序"以本地保存程序包。 zip 文件包括以下文件：

    - Defender for Identity 传感器安装程序

    - 包含连接到 Defender for Identity 云服务所需信息的配置设置文件

1. 复制 **访问键**。 Defender for Identity 传感器需要访问密钥才能连接到 Defender for Identity 实例。 访问密钥是一个一次密码，用于传感器部署，之后所有通信均使用证书进行身份验证和 TLS 加密。 如果需要 **重新生成新的访问键** ，请使用"重新生成密钥"按钮。 它不会影响以前部署的任何传感器，因为它仅用于传感器的初始注册。

1. 将程序包复制到要安装 Defender for Identity 传感器的专用服务器或域控制器。

## <a name="configure-directory-services-account"></a>配置目录服务帐户

若要将传感器与 Active Directory 域连接，需要配置目录服务帐户。

1. In [Microsoft 365 Defender，](https://security.microsoft.com/)go to **设置** and then **Identities**.

    ![转到"设置"，然后转到"标识"](../../media/defender-identity/settings-identities.png)

1. 选择 **"目录服务帐户"。** 你将看到哪些帐户与哪些域关联。

    ![目录服务帐户](../../media/defender-identity/directory-service-accounts.png)

1. 如果您选择一个帐户，将打开一个包含该帐户设置的窗格。

    ![帐户设置](../../media/defender-identity/account-settings.png)

1. 若要添加新的目录服务帐户，**请选择"创建新** 帐户"并填写"**帐户名称**"、"**域**"和"**密码"。** 还可以选择它是组托管服务帐户 ( gMSA) ，以及是否属于 **单标签域**。

    ![新目录服务帐户](../../media/defender-identity/new-directory-service-account.png)

1. 选择“**保存**”。

## <a name="see-also"></a>另请参阅

- [管理 Defender for Identity 安全警报](manage-security-alerts.md)
