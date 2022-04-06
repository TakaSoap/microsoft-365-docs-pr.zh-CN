---
title: 网络钓鱼趋势和技术
ms.reviewer: ''
description: 了解如何发现网络钓鱼技术
keywords: 安全， 恶意软件， 网络钓鱼， 信息， 骗局， 社会工程， 诱饵， 诱惑， 保护， 趋势， 目标攻击， 鱼叉钓鱼， 捕鲸
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: c56478f4dbe496f7e2080e9c73d6466df0e2c5d7
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666737"
---
# <a name="phishing-trends-and-techniques"></a>网络钓鱼趋势和技术

网络钓鱼攻击是经常使用社会工程诱饵或引诱内容的骗局。 链接到网络钓鱼网站的合法通信（通常是电子邮件）是网络钓鱼攻击中最常见的方法之一。 网络钓鱼网站通常模拟需要用户输入凭据和帐户信息的登录页面。 然后，网络钓鱼网站在用户提供敏感信息后立即捕获该信息，使攻击者能够访问该信息。

下面是攻击者用来尝试窃取信息或获取设备访问权限的一些最常见的网络钓鱼技术。

## <a name="invoice-phishing"></a>发票网络钓鱼

在此骗局中，攻击者试图通过一封电子邮件来引诱你，指出你有来自已知供应商或公司的未结发票。 然后，他们提供一个链接，供你访问并支付发票费用。 当你访问该网站时，攻击者准备窃取你的个人信息和资金。

## <a name="paymentdelivery-scam"></a>付款/送货诈骗

系统要求你提供信用卡或其他个人信息，以便可以使用常用的供应商或供应商更新付款信息。 系统会请求更新，以便你可以交付已订购的商品。 一般情况下，你可能熟悉公司，并且过去可能与他们做过业务。 但是，你并不知道最近从中购买的任何项目。

## <a name="tax-themed-phishing-scams"></a>以税务为主题的网络钓鱼诈骗

常见的 IRS 网络钓鱼骗局正在收到一封紧急电子邮件信，指示你欠 IRS 钱。 如果无法及时访问网站并交税，电子邮件通常会威胁法律行动。 当你访问该网站时，攻击者可以窃取你的个人信用卡或银行信息，并耗尽你的帐户。

## <a name="downloads"></a>下载内容

攻击者发送欺诈性电子邮件，请求你打开或下载文档附件，例如 PDF。 附件通常包含一条消息，要求登录到另一个网站（如电子邮件或文件共享网站）以打开文档。 使用登录凭据访问这些网络钓鱼网站时，攻击者现在可以访问你的信息，并可以获取有关你的其他个人信息。

## <a name="phishing-emails-that-deliver-other-threats"></a>发送其他威胁的网络钓鱼电子邮件

网络钓鱼电子邮件通常有效，因此攻击者有时使用它们通过电子邮件中的链接或附件分发 [勒索软件](/security/compass/human-operated-ransomware) 。 运行时，勒索软件会加密文件并显示赎金说明，要求你支付一笔资金来访问文件。

我们还看到网络钓鱼电子邮件，其中包含 [指向技术支持诈骗](support-scams.md) 网站的链接。 这些网站使用各种恐吓策略来欺骗你拨打热线电话，并支付不必要的"技术支持服务"，据称可以解决精心策划的设备、平台或软件问题。

## <a name="spear-phishing"></a>Spear 网络钓鱼

鱼叉网络钓鱼是一种有针对性的网络钓鱼攻击，涉及高度自定义的诱惑内容。 攻击者通常通过调查社交媒体和其他有关其预期目标的信息源来执行侦查工作。

鱼叉网络钓鱼可能涉及欺骗你登录到假网站和泄露凭据。 我还可以通过单击自动安装恶意软件的链接来吸引你打开文档。 有了此恶意软件，攻击者可以远程操作受感染的计算机。

植入的恶意软件是更复杂的攻击的入口点，称为 APT)  (高级持久威胁。 APT 旨在建立长期控制和窃取数据。 攻击者可能会尝试部署更多隐蔽的黑客工具，横向移动到其他计算机，入侵或创建特权帐户，并定期从遭到入侵的网络中泄露信息。

## <a name="whaling"></a>捕 鲸

捕鲸是一种网络钓鱼形式，面向特定公司的高级或高级管理人员，以获取其凭据和/或银行信息。 电子邮件内容可以写入法律传票、客户投诉或其他行政问题。 此类攻击还可能导致组织内的 APT 攻击。

## <a name="business-email-compromise"></a>商业电子邮件泄露

商业电子邮件泄露 (BEC) 是一个复杂的骗局，针对那些经常与外国供应商合作或进行货币电汇的企业。 BEC 攻击者使用的最常见的方案之一是通过鱼叉网络攻击获取公司网络的访问权限。 攻击者创建类似于其目标公司的域，或欺骗其电子邮件以欺骗用户释放个人帐户信息以进行资金转移。

## <a name="more-information-about-phishing-attacks"></a>有关网络钓鱼攻击的详细信息

有关最新的网络钓鱼攻击、技术和趋势的信息，可以在 [Microsoft 安全博客](https://www.microsoft.com/security/blog/product/windows/)上阅读以下条目：

- [网络钓鱼者使用 PDF 附件释放简单但有效的社会工程技术](https://cloudblogs.microsoft.com/microsoftsecure/2017/01/26/phishers-unleash-simple-but-effective-social-engineering-techniques-using-pdf-attachments/?source=mmpc)
- [纳税主题网络钓鱼和恶意软件攻击在纳税申报季节激增](https://cloudblogs.microsoft.com/microsoftsecure/2017/03/20/tax-themed-phishing-and-malware-attacks-proliferate-during-the-tax-filing-season/?source=mmpc)
- [网络钓鱼（如电子邮件）导致技术支持骗局](https://cloudblogs.microsoft.com/microsoftsecure/2017/08/07/links-in-phishing-like-emails-lead-to-tech-support-scam/?source=mmpc)
