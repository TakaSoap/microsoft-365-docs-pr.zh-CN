---
title: 使用 Microsoft 咨询服务
description: 使用 MCS 打包应用的准备工作和后续步骤
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 5dd6bf62625d6b22a0585645abbeb24dabd6c9fd
ms.sourcegitcommit: cafca45069819a44c7cf8c67f6c1e105de1b3393
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2022
ms.locfileid: "62520447"
---
# <a name="working-with-microsoft-consulting-services"></a>使用 Microsoft 咨询服务

你可以与 Microsoft 咨询服务 (MCS) ，以打包应用以用于Microsoft 托管桌面。 有关详细信息，请与你的帐户代表一起联系 MCS，查看你的特定应用打包项目。

## <a name="roles-and-responsibilities"></a>角色和职责

| 角色 | 职责 |
| ------ | ------ |
| 你 | 若要使用 MCS 应用打包 **，必须提供以下元素**： <ul><li> 源安装程序文件 (，例如setup.exe或.msi) 。</li><li>指定最终安装外观的详细信息的安装说明。 例如，应用应该有桌面快捷方式吗？ 应用的可见性应该是什么？ 应用应该连接到服务器，如果是，应该连接到哪一台服务器？ 有关详细信息，请参阅应用程序 [打包请求模板](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)。</li><li>必须执行自己的验收测试，以验证应用是否在你的环境中正常工作。</li><ul> |
| Microsoft 咨询服务 (MCS)  | **MCS 将处理以下操作：** <ul><li>检查应用在安全环境中是被禁止Microsoft 托管桌面限制。</li><li>测试应用的安装、启动和卸载以确保与 Windows 10。 如果 MCS 发现兼容性问题，他们会将应用交到应用 [保证计划](/fasttrack/products-and-capabilities#app-assure) 进行修正。</li><li>将应用打包到规范中，然后使用 Microsoft Intune。</li><ul>

## <a name="app-delivery-schedule"></a>应用交付计划

将应用信息上载到应用门户，开始Microsoft 托管桌面过程。 打包团队每周四审查新提交。 在查看和打包后，打包的应用在下面的星期五交付。 每周最多可以打包五个应用以启动，但服务可以扩展以满足你的需求。

![显示此示例中) 21 日（星期四）应用流入的日历、第二天的媒体验证、 (年 25 日) 的星期一打包以及下一个 (年 2) 9 日 (日的应用交付。 (](../../media/MCS-cal.png)

应用传递后，你将收到通知。 此时，你有 21 天的时间执行验收测试，并批准 Microsoft 托管桌面工作。 如果在验收测试期间发现应用存在问题，请拒绝应用在 Microsoft 托管桌面 门户。 你将通过电子邮件与 Microsoft 咨询服务部门 (MCS) 程序进行连接，以理解并解决问题。

## <a name="testing-accounts-and-environment"></a>测试帐户和环境

为了使打包团队完成到 Microsoft Intune 迁移，建议您提供以下特定权限：

- 访问Microsoft Intune程序的应用部署功能，以添加和分配应用。
- 测试组、用户帐户和许可证，使包装程序能够测试应用。

MCS 将使用这些权限执行以下操作：

- 确保应用适用于为虚拟机配置的Microsoft 托管桌面。
- Upload应用Microsoft Intune以部署到用户。

如果没有这些权限，MCS 可能会前进，但他们无法将应用程序上载到您的环境。
