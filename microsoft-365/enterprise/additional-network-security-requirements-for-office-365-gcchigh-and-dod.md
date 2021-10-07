---
title: Office 365 GCC DoD 的其他网络安全要求
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 摘要：Office 365 GCC高和 DoD 具有其他网络安全要求
hideEdit: true
ms.openlocfilehash: c4fbfc52085b634329130c2785ce683109b8febe
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170363"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Office 365 GCC High和DOD的额外网络安全要求。

*本文适用于 Office 365 GCC、Office 365 DOD、Microsoft 365 GCC High 和 Microsoft 365 DOD。*

Office 365 GCC高和 DOD 是满足美国政府及其供应商和承包商需求的安全云环境。  对于允许服务访问的外部终结点，这些云环境具有其他网络限制。

GCC计划使用联合身份或混合共存的高和 DOD 客户可能需要 Microsoft 允许入站和/或出站访问现有本地部署。  这些活动的示例包括：

* 将联合身份与 Active Directory 联合 (或类似支持的 STS 服务一起) 
* 与本地部署或本地部署Exchange Server Skype for Business共存
* 从本地系统迁移现有用户内容

若要允许服务与本地终结点通信，你必须向工程团队发送Office 365更改的电子邮件。

> [!WARNING]
> 所有请求的 SLA 都 **为三周** ，由于需要安全与合规控制和部署管道，因此无法加快处理。  这包括初始载入网络请求，以及迁移到服务后的任何更改。  确保你的网络团队知道此时间线，并包括在你的规划周期中。

使用以下信息[Office 365 政府版 Allow-List](mailto:o365gwlt@microsoft.com)电子邮件发送到请求：

* **To**： [Office 365 政府版 Allow-List Requests](mailto:o365gwlt@microsoft.com)
* **From**：租户管理员 - 发送电子邮件 **必须与** 租户中的全局管理员联系人匹配
* **电子邮件主题**：Office 365 GCC高网络请求 - contoso.onmicrosoft.us (替换为租户名称) 

邮件正文应包含以下数据：

* 你的Microsoft Online Services租户 (例如，contoso.onmicrosoft.com、fabrikam.onmicrosoft.us) 
* 与 Microsoft 通信的电子邮件通讯组列表，用于与网络更改和/或跟踪无效子网相关的后续通信
* 指示是否计划将Microsoft Teams混合共存与本地部署一同使用
* 联合身份系统可从外部访问的 URL (例如，sts.contoso.com) CIDR 表示法中的 (IP 地址范围。 10.1.1.0/28) 
* CIDR 表示法中的本地 PKI 证书吊销列表 URL 和 IP 地址范围
* 使用 CIDR 表示法Exchange Server本地部署的可从外部访问的 URL 和 IP 地址范围
* 使用 CIDR 表示法Skype for Business本地部署的可从外部访问的 URL 和 IP 地址范围

出于安全性和合规性原因，请牢记对请求的以下限制：

* 每个租户有四个子网限制
* 子网必须用 CIDR 表示法 (例如，10.1.1.0/28) 
* 子网范围不能大于/24
* 我们 **不允许** 请求允许访问商业云服务 (商业Office 365 Google G-Suite、Amazon Web Services 等) 

一旦 Microsoft 收到并批准你的请求，将会有一个为期三周的 SLA 用于实施，并且无法加速。  当我们收到你的请求时，你将收到初始确认，完成确认后，你将收到最终确认。
