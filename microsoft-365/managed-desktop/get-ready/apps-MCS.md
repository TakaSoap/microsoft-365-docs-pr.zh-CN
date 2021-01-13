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
ms.openlocfilehash: f8c4e427c536577ea2fc768d4930b9d4db6ac697
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841419"
---
# <a name="working-with-microsoft-consulting-services"></a>使用 Microsoft 咨询服务

你可以与 Microsoft 咨询服务部门 (MCS) ，以打包应用以与 Microsoft 托管桌面一同使用。 有关确切详细信息，请与你的帐户代表联系 MCS，并确定你的特定应用打包项目的范围。

## <a name="roles-and-responsibilities"></a>角色和职责

若要使用 MCS 应用打包 **，你必须提供以下元素**：

- 源安装程序文件 (例如，setup.exe .msi) 。
- 安装说明，指定有关最终安装外观的详细信息。 例如，应用应该有桌面快捷方式吗？ 应用的可见性应该是什么？ 应用应连接到服务器，如果是，应连接到哪一台服务器？ 有关详细信息，请参阅应用程序 [打包请求模板](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)。
- 你必须执行自己的验收测试，以验证应用是否在你的环境中能够正常工作。

**MCS 将处理以下操作：**

- 检查 Microsoft 托管桌面环境中是禁止应用还是限制应用。
- 测试应用的安装、启动和卸载以确保与 Windows 10 兼容。 如果 MCS 发现兼容性问题，他们将应用上手到 [桌面应用保证](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) 计划进行修正。
- 将应用打包到规范中，然后使用 Microsoft Intune 测试应用部署。

## <a name="app-delivery-schedule"></a>应用交付计划

将应用信息上载到 Microsoft 托管桌面门户，开始打包过程。 打包团队每周四审查新提交。 查看并打包后，打包的应用将于下个星期五交付。 每周最多可以打包五个应用以启动，但服务可以扩展以满足你的需求。

![显示此示例) 中第 21 个星期四 (应用流入的日历、第二天的媒体验证、 (25) 的第二个星期一打包，以及 29 日 (星期五的应用交付) ](../../media/MCS-cal.png)

应用送达后，你将收到通知。 此时，你有 21 天的时间在 Microsoft 托管桌面门户中执行验收测试和批准工作。 如果在验收测试期间发现应用存在问题，请拒绝 Microsoft 托管桌面门户中的应用，你将通过电子邮件与 MCS 包装程序进行连接，以了解并解决问题。

## <a name="testing-accounts-and-environment"></a>测试帐户和环境

若要让打包团队完成到 Microsoft Intune 的迁移，我们建议你提供某些权限：
 
-   访问 Microsoft Intune 的应用部署功能，让包装器添加和分配应用 
-   测试组、用户帐户和许可证，使包装器能够测试应用

MCS 将使用这些权限执行以下操作：
 
-   确保应用适用于为 Microsoft 托管桌面配置的虚拟机
-   将应用上载到 Microsoft Intune 以部署到用户

如果没有这些权限，MCS 可以继续工作，但无法将应用程序上载到您的环境。


