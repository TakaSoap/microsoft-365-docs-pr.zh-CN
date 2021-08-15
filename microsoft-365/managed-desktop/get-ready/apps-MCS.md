---
title: 使用 Microsoft 咨询服务
description: 使用 MCS 打包应用的准备工作和后续步骤
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 4470ce4bc2ee671a24c319b817162b10cb89dbb4917feda51010147bb46fd814
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53854540"
---
# <a name="working-with-microsoft-consulting-services"></a>使用 Microsoft 咨询服务

你可以与 Microsoft 咨询服务 (MCS) ，以打包应用以用于Microsoft 托管桌面。 有关确切详细信息，请与你的帐户代表联系 MCS，并确定特定应用打包项目的范围。

## <a name="roles-and-responsibilities"></a>角色与责任

若要使用 MCS 应用打包 **，必须提供以下元素**：

- 源安装程序文件 (，例如setup.exe或.msi) 。
- 安装说明，指定最终安装的外观的详细信息。 例如，应用应该有桌面快捷方式吗？ 应用的可见性应该是什么？ 应用应连接到服务器，如果是，应连接到哪一台服务器？ 有关详细信息，请参阅应用程序 [打包请求模板](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)。
- 你必须执行自己的验收测试，以验证应用是否可像你需要在你的环境中一样工作。

**MCS 将处理以下操作：**

- 检查应用在安全环境中是被禁止Microsoft 托管桌面限制。
- 测试应用的安装、启动和卸载以确保与 Windows 10。 如果 MCS 发现兼容性问题，他们将向应用保证计划提供该应用进行[](/fasttrack/products-and-capabilities#app-assure)修正。
- 将应用打包到规范中，然后使用 Microsoft Intune。

## <a name="app-delivery-schedule"></a>应用交付计划

将应用信息上载到应用门户，开始Microsoft 托管桌面过程。 打包团队每周四审查新提交。 在查看和打包后，打包的应用在下面的星期五交付。 每周最多可以打包五个应用以启动，但服务可以扩展以满足你的需求。

![显示应用在此示例) 中周四 (21 日的日历、第二天的媒体验证、 (年 25 日) 周一打包，以及下一个周五 (29 日) ](../../media/MCS-cal.png)

应用传递后，你将收到通知。 此时，你有 21 天的时间执行验收测试，并批准 Microsoft 托管桌面工作。 如果在验收测试期间发现应用的一些问题，在 Microsoft 托管桌面 门户中拒绝该应用，你将通过电子邮件与 MCS 包装程序进行连接，以了解并解决该问题。

## <a name="testing-accounts-and-environment"></a>测试帐户和环境

若要让打包团队完成到 Microsoft Intune 的迁移，建议您提供以下特定权限：

- 访问Microsoft Intune程序的应用部署功能，以添加和分配应用
- 测试组、用户帐户和许可证，使包装程序能够测试应用

MCS 将使用这些权限执行以下操作：

- 确保应用适用于为虚拟机配置的Microsoft 托管桌面
- 将应用上载到Microsoft Intune以部署到用户

如果没有这些权限，MCS 可能会前进，但无法将应用程序上载到您的环境。
