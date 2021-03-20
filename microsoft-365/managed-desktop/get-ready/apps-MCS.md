---
title: 使用 Microsoft 咨询服务
description: 准备和后续步骤以使用 MCS 打包应用
keywords: Microsoft 托管桌面， Microsoft 365， 服务， 文档， 应用， MCS， 打包
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 04b0c7905c83be2afa46abcfb2d4bb5cd9735e06
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909222"
---
# <a name="working-with-microsoft-consulting-services"></a>使用 Microsoft 咨询服务

你可以与 Microsoft 咨询服务 (MCS) ，以打包应用以与 Microsoft 托管桌面一同使用。 有关确切详细信息，请与你的帐户代表联系 MCS，并确定特定应用打包项目的范围。

## <a name="roles-and-responsibilities"></a>角色和职责

若要使用 MCS 应用打包 **，必须提供以下元素**：

- 源安装程序文件 (例如，setup.exe .msi) 。
- 安装说明，指定最终安装的外观的详细信息。 例如，应用应该有桌面快捷方式吗？ 应用的可见性应该是什么？ 应用应连接到服务器，如果是，应连接到哪一台服务器？ 有关详细信息，请参阅应用程序 [打包请求模板](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)。
- 你必须执行自己的验收测试，以验证应用是否可像你需要在你的环境中一样工作。

**MCS 将处理以下操作：**

- 检查 Microsoft 托管桌面环境中是否禁止或限制应用。
- 测试应用的安装、启动和卸载以确保与 Windows 10 兼容。 如果 MCS 发现兼容性问题，他们将将应用交到 [桌面应用保证计划](/fasttrack/win-10-desktop-app-assure) 进行修正。
- 将应用打包到规范中，然后使用 Microsoft Intune 测试应用部署。

## <a name="app-delivery-schedule"></a>应用交付计划

将应用信息上载到 Microsoft 托管桌面门户，开始打包过程。 打包团队每周四审查新提交。 在查看和打包后，打包的应用在下面的星期五交付。 每周最多可以打包五个应用以启动，但服务可以扩展以满足你的需求。

![显示应用在此示例) 中周四 (21 日的日历、第二天的媒体验证、 (年 25 日) 周一打包，以及下一个周五 (29 日) ](../../media/MCS-cal.png)

应用传递后，你将收到通知。 此时，你有 21 天的时间在 Microsoft 托管桌面门户中执行验收测试和批准工作。 如果在验收测试期间发现应用的一些问题，在 Microsoft 托管桌面门户中拒绝该应用，你将通过电子邮件与 MCS 包装程序进行连接，以了解并解决该问题。

## <a name="testing-accounts-and-environment"></a>测试帐户和环境

若要让打包团队完成到 Microsoft Intune 的迁移，我们建议你提供某些权限：
 
-   访问 Microsoft Intune 的应用部署功能，让包装程序添加和分配应用 
-   测试组、用户帐户和许可证，使包装程序能够测试应用

MCS 将使用这些权限执行以下操作：
 
-   确保应用适用于为 Microsoft 托管桌面配置的虚拟机
-   将应用上传到 Microsoft Intune 以部署到用户

如果没有这些权限，MCS 可能会前进，但无法将应用程序上载到您的环境。