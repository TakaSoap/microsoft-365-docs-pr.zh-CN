---
title: 数据丢失防护策略参考
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 03/02/2022
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
recommendations: false
description: DLP 策略组件和配置参考
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: d6bc24f313d1998979a460bcd41e87ccbe8abc5c
ms.sourcegitcommit: 5c9137f98e688ab23c144e75687399e390bb2601
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2022
ms.locfileid: "64704914"
---
# <a name="data-loss-prevention-policy-reference"></a>数据丢失防护策略参考

数据丢失防护 (DLP) 策略有许多组件需要配置。 若要创建有效的策略，需要了解每个组件的用途及其配置如何更改策略的行为。 本文提供 DLP 策略的详细解剖。

## <a name="policy-templates"></a>策略模板 

DLP 策略模板预排序为四个类别：

- 可以检测和保护 **财务** 信息类型的信息。
- 可以检测和保护医疗 **和健康** 信息类型的信息。
- 可以检测和保护 **隐私** 信息类型的信息。
- 一个 **自定义** 模板，如果其他模板之一不能满足组织的需求，则可以使用该模板来生成自己的策略。

下表列出了所有策略模板及其所涵盖的 (SIT) 敏感信息类型。 

更新时间：2021/06/23

|类别| 模板 | 坐 |
|---------|---------|---------|
|金融| 澳大利亚财务数据| - [SWIFT 代码](sensitive-information-type-entity-definitions.md#swift-code) </br> - [澳大利亚税务文件号](sensitive-information-type-entity-definitions.md#australia-tax-file-number) </br> - [澳大利亚银行帐号](sensitive-information-type-entity-definitions.md#australia-bank-account-number) </br> - [信用卡号](sensitive-information-type-entity-definitions.md#credit-card-number)|
|金融| 加拿大财务数据 |- [信用卡号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [加拿大银行帐号](sensitive-information-type-entity-definitions.md#canada-bank-account-number)|
|金融| 法国金融数据 |- [信用卡号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [EU 借记卡号](sensitive-information-type-entity-definitions.md#eu-debit-card-number)|
|金融| 德国财务数据 |- [信用卡号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [EU 借记卡号](sensitive-information-type-entity-definitions.md#eu-debit-card-number)|
|金融| 以色列财务数据 |- [以色列银行帐号](sensitive-information-type-entity-definitions.md#israel-bank-account-number) </br> - [SWIFT 代码](sensitive-information-type-entity-definitions.md#swift-code) </br> - [信用卡号](sensitive-information-type-entity-definitions.md#credit-card-number)|
|金融| 日本财务数据 |- [日本银行帐号](sensitive-information-type-entity-definitions.md#japan-bank-account-number) </br> - [信用卡号](sensitive-information-type-entity-definitions.md#credit-card-number)|
|金融| PCI 数据安全标准 (PCI DSS)|- [信用卡号](sensitive-information-type-entity-definitions.md#credit-card-number)|
|金融| 沙特阿拉伯反网络犯罪法|- [SWIFT 代码](sensitive-information-type-entity-definitions.md#swift-code) </br> - [国际银行帐户编号 (IBAN) ](sensitive-information-type-entity-definitions.md#international-banking-account-number-iban) |
|金融| 沙特阿拉伯财务数据 |- [信用卡号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [SWIFT 代码](sensitive-information-type-entity-definitions.md#swift-code) </br> - [国际银行帐户编号 (IBAN) ](sensitive-information-type-entity-definitions.md#international-banking-account-number-iban)|
|金融| 英国金融数据|- [信用卡号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [EU 借记卡号](sensitive-information-type-entity-definitions.md#eu-debit-card-number) </br> - [SWIFT 代码](sensitive-information-type-entity-definitions.md#swift-code)|
|金融| 美国金融数据|- [信用卡号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [美国银行帐号](sensitive-information-type-entity-definitions.md#us-bank-account-number)</br> - [ABA 路由编号](sensitive-information-type-entity-definitions.md#aba-routing-number)|
|金融| 美国联邦贸易委员会 (FTC) 消费者规则|- [信用卡号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [美国银行帐号](sensitive-information-type-entity-definitions.md#us-bank-account-number)</br> - [ABA 路由编号](sensitive-information-type-entity-definitions.md#aba-routing-number)|
|金融| 美国格拉姆-利奇-布利利法案 (GLBA) 增强|- [信用卡号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [美国银行帐号](sensitive-information-type-entity-definitions.md#us-bank-account-number)</br> - [ITIN (美国个人纳税人标识号) ](sensitive-information-type-entity-definitions.md#us-individual-taxpayer-identification-number-itin)  </br> - [美国社会保障号码 (SSN) ](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn)</br> - [美国/英国护照号码](sensitive-information-type-entity-definitions.md#usuk-passport-number) </br> -[美国驾照号](sensitive-information-type-entity-definitions.md#us-drivers-license-number)</br> - [所有全名](sensitive-information-type-entity-definitions.md#all-full-names)</br> - [美国物理地址](sensitive-information-type-entity-definitions.md#us-physical-addresses)|
|金融| 格雷姆-里奇-比利雷法案 (GLBA)|- [信用卡号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [美国银行帐号](sensitive-information-type-entity-definitions.md#us-bank-account-number)</br> - [ITIN (美国个人纳税人标识号) ](sensitive-information-type-entity-definitions.md#us-individual-taxpayer-identification-number-itin)  </br> - [美国社会保障号码 (SSN) ](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn)|
|医疗和健康| 澳大利亚健康记录法 (HRIP 法案) 增强 |- [澳大利亚税务文件号](sensitive-information-type-entity-definitions.md#australia-tax-file-number) </br> - [澳大利亚医疗帐号](sensitive-information-type-entity-definitions.md#australia-medical-account-number) </br> - [所有全名](sensitive-information-type-entity-definitions.md#all-full-names) </br> - [所有医疗条款和条件](sensitive-information-type-entity-definitions.md#all-medical-terms-and-conditions) </br> - [澳大利亚物理地址](sensitive-information-type-entity-definitions.md#australia-physical-addresses)|
|医疗和健康| 澳大利亚健康记录法案（HRIP 法案）|- [澳大利亚税务文件号](sensitive-information-type-entity-definitions.md#australia-tax-file-number) </br> - [澳大利亚医疗帐号](sensitive-information-type-entity-definitions.md#australia-medical-account-number)|
|医疗和健康| 加拿大健康信息法案 (HIA) |- [加拿大护照号码](sensitive-information-type-entity-definitions.md#canada-passport-number)</br> - [加拿大社会保险号码](sensitive-information-type-entity-definitions.md#canada-social-insurance-number) </br> - [加拿大健康服务号码](sensitive-information-type-entity-definitions.md#canada-health-service-number) </br> - [加拿大个人健康标识号](sensitive-information-type-entity-definitions.md#canada-personal-health-identification-number-phin)|
|医疗和健康| 加拿大《个人健康信息法》 (PHIA) 马尼托巴省|- [加拿大社会保险号码](sensitive-information-type-entity-definitions.md#canada-social-insurance-number) </br> - [加拿大健康服务号码](sensitive-information-type-entity-definitions.md#canada-health-service-number) </br> - [加拿大个人健康标识号](sensitive-information-type-entity-definitions.md#canada-personal-health-identification-number-phin)|
|医疗和健康| 加拿大个人健康法 (PHIPA) 安大略 |- [加拿大护照号码](sensitive-information-type-entity-definitions.md#canada-passport-number)</br> - [加拿大社会保险号码](sensitive-information-type-entity-definitions.md#canada-social-insurance-number) </br> - [加拿大健康服务号码](sensitive-information-type-entity-definitions.md#canada-health-service-number) </br> - [加拿大个人健康标识号](sensitive-information-type-entity-definitions.md#canada-personal-health-identification-number-phin)|
|医疗和健康| 英国获取医疗报告法案|- [英国国家卫生服务号码](sensitive-information-type-entity-definitions.md#uk-national-health-service-number) </br> - [英国国民保险号码 (尼诺) ](sensitive-information-type-entity-definitions.md#uk-national-insurance-number-nino)|
|医疗和健康| 美国健康保险法 (HIPAA) 增强|</br> - [ICD-9-CM (疾病的国际分类) ](sensitive-information-type-entity-definitions.md#international-classification-of-diseases-icd-9-cm) </br> - [ICD-10-CM (疾病的国际分类) ](sensitive-information-type-entity-definitions.md#international-classification-of-diseases-icd-10-cm) </br> - [所有全名](sensitive-information-type-entity-definitions.md#all-full-names) </br> - [所有医疗条款和条件](sensitive-information-type-entity-definitions.md#all-medical-terms-and-conditions) </br> - [美国物理地址](sensitive-information-type-entity-definitions.md#us-physical-addresses)|
|医疗和健康| 美国健康保险法案 (HIPAA)| - [ICD-9-CM (疾病的国际分类) ](sensitive-information-type-entity-definitions.md#international-classification-of-diseases-icd-9-cm) </br> - [ICD-10-CM (疾病的国际分类) ](sensitive-information-type-entity-definitions.md#international-classification-of-diseases-icd-10-cm)|
|隐私| 澳大利亚隐私法增强|- [澳大利亚驾驶执照号码](sensitive-information-type-entity-definitions.md#australia-drivers-license-number) </br> - [澳大利亚护照号码](sensitive-information-type-entity-definitions.md#australia-passport-number) </br> - [所有全名](sensitive-information-type-entity-definitions.md#all-full-names) </br> - [所有医疗条款和条件](sensitive-information-type-entity-definitions.md#all-medical-terms-and-conditions) </br> - [澳大利亚物理地址](sensitive-information-type-entity-definitions.md#australia-physical-addresses)|
|隐私| 澳大利亚隐私法案|- [澳大利亚驾驶执照号码](sensitive-information-type-entity-definitions.md#australia-drivers-license-number) </br> - [澳大利亚护照号码](sensitive-information-type-entity-definitions.md#australia-passport-number)|
|隐私| 澳大利亚个人身份信息 (PII) 数据|- [澳大利亚税务文件号](sensitive-information-type-entity-definitions.md#australia-tax-file-number) </br> - [澳大利亚驾驶执照号码](sensitive-information-type-entity-definitions.md#australia-drivers-license-number)|
|隐私| 加拿大个人身份信息 (PII) 数据|- [加拿大驾驶执照号码](sensitive-information-type-entity-definitions.md#canada-drivers-license-number)</br> - [加拿大银行帐号](sensitive-information-type-entity-definitions.md#canada-bank-account-number) </br> - [加拿大护照号码](sensitive-information-type-entity-definitions.md#canada-passport-number)</br> - [加拿大社会保险号码](sensitive-information-type-entity-definitions.md#canada-social-insurance-number) </br> - [加拿大健康服务号码](sensitive-information-type-entity-definitions.md#canada-health-service-number) </br> - [加拿大个人健康标识号](sensitive-information-type-entity-definitions.md#canada-personal-health-identification-number-phin)|
|隐私| 加拿大个人信息保护法案 (PIPA)|- [加拿大护照号码](sensitive-information-type-entity-definitions.md#canada-passport-number)</br> - [加拿大社会保险号码](sensitive-information-type-entity-definitions.md#canada-social-insurance-number) </br> - [加拿大健康服务号码](sensitive-information-type-entity-definitions.md#canada-health-service-number) </br> - [加拿大个人健康标识号](sensitive-information-type-entity-definitions.md#canada-personal-health-identification-number-phin)|
|隐私| 加拿大个人信息保护法案 (PIPEDA)|- [加拿大驾驶执照号码](sensitive-information-type-entity-definitions.md#canada-drivers-license-number) </br> - [加拿大银行帐号](sensitive-information-type-entity-definitions.md#canada-bank-account-number) </br> - [加拿大护照号码](sensitive-information-type-entity-definitions.md#canada-passport-number)</br> - [加拿大社会保险号码](sensitive-information-type-entity-definitions.md#canada-social-insurance-number) </br> - [加拿大健康服务号码](sensitive-information-type-entity-definitions.md#canada-health-service-number) </br> - [加拿大个人健康标识号](sensitive-information-type-entity-definitions.md#canada-personal-health-identification-number-phin)|
|隐私| 法国数据保护法案|- [法国国家身份证 (CNI) ](sensitive-information-type-entity-definitions.md#france-national-id-card-cni) </br> - [法国社保号码 (INSEE) ](sensitive-information-type-entity-definitions.md#france-social-security-number-insee)|
|隐私| 法国个人身份信息 (PII) 数据|- [法国社保号码 (INSEE) ](sensitive-information-type-entity-definitions.md#france-social-security-number-insee) </br> - [法国驾照号](sensitive-information-type-entity-definitions.md#france-drivers-license-number) </br> - [法国护照号码](sensitive-information-type-entity-definitions.md#france-passport-number) </br> - [法国国家身份证 (CNI) ](sensitive-information-type-entity-definitions.md#france-national-id-card-cni)|
|隐私| 一般数据保护条例 (增强了 GDPR) |- [奥地利物理地址](sensitive-information-type-entity-definitions.md#austria-physical-addresses) </br> - [比利时物理地址](sensitive-information-type-entity-definitions.md#belgium-physical-addresses)</br> - [保加利亚物理地址](sensitive-information-type-entity-definitions.md#bulgaria-physical-addresses)</br> - [克罗地亚物理地址](sensitive-information-type-entity-definitions.md#croatia-physical-addresses)</br> - [塞浦路斯物理地址](sensitive-information-type-entity-definitions.md#cyprus-physical-addresses)</br> - [捷克共和国物理地址](sensitive-information-type-entity-definitions.md#czech-republic-physical-addresses)</br> - [丹麦物理地址](sensitive-information-type-entity-definitions.md#denmark-physical-addresses)</br> - [爱沙尼亚物理地址](sensitive-information-type-entity-definitions.md#estonia-physical-addresses)</br> - [芬兰物理地址](sensitive-information-type-entity-definitions.md#finland-physical-addresses)</br> - [法国物理地址](sensitive-information-type-entity-definitions.md#france-physical-addresses)</br> - [德国物理地址](sensitive-information-type-entity-definitions.md#germany-physical-addresses)</br> - [希腊物理地址](sensitive-information-type-entity-definitions.md#greece-physical-addresses)</br> - [匈牙利物理地址](sensitive-information-type-entity-definitions.md#hungary-physical-addresses)</br> - [爱尔兰物理地址](sensitive-information-type-entity-definitions.md#ireland-physical-addresses)</br> - [意大利物理地址](sensitive-information-type-entity-definitions.md#italy-physical-addresses)</br> - [拉脱维亚物理地址](sensitive-information-type-entity-definitions.md#latvia-physical-addresses)</br> - [立陶宛物理地址](sensitive-information-type-entity-definitions.md#lithuania-physical-addresses)</br> - [卢森堡物理地址](sensitive-information-type-entity-definitions.md#luxemburg-physical-addresses)</br> - [马耳他物理地址](sensitive-information-type-entity-definitions.md#malta-physical-addresses)</br> - [荷兰物理地址](sensitive-information-type-entity-definitions.md#netherlands-physical-addresses)</br> - [波兰物理地址](sensitive-information-type-entity-definitions.md#poland-physical-addresses)</br> - [葡萄牙文物理地址](sensitive-information-type-entity-definitions.md#portugal-physical-addresses)</br> - [罗马尼亚物理地址](sensitive-information-type-entity-definitions.md#romania-physical-addresses)</br> - [斯洛伐克物理地址](sensitive-information-type-entity-definitions.md#slovakia-physical-addresses)</br> - [斯洛文尼亚物理地址](sensitive-information-type-entity-definitions.md#slovenia-physical-addresses)</br> - [西班牙物理地址](sensitive-information-type-entity-definitions.md#spain-physical-addresses)</br> - [瑞典物理地址](sensitive-information-type-entity-definitions.md#sweden-physical-addresses)</br> - [奥地利社会保障号码](sensitive-information-type-entity-definitions.md#austria-social-security-number)</br> - [法国社保号码 (INSEE) ](sensitive-information-type-entity-definitions.md#france-social-security-number-insee)</br> - [希腊社会保障号码 (AMKA) ](sensitive-information-type-entity-definitions.md#greece-social-security-number-amka)</br> - [匈牙利社会保障号码 (泰姬) ](sensitive-information-type-entity-definitions.md#hungary-social-security-number-taj)</br> - [西班牙社保号码 (SSN) ](sensitive-information-type-entity-definitions.md#spain-social-security-number-ssn)</br> - [奥地利身份证](sensitive-information-type-entity-definitions.md#austria-identity-card)</br> - [塞浦路斯身份证](sensitive-information-type-entity-definitions.md#cyprus-identity-card)</br> - [德国身份证号码](sensitive-information-type-entity-definitions.md#germany-identity-card-number)</br> - [马耳他身份证号码](sensitive-information-type-entity-definitions.md#malta-identity-card-number)</br> - [法国国家身份证 (CNI) ](sensitive-information-type-entity-definitions.md#france-national-id-card-cni)</br> - [希腊国家身份证](sensitive-information-type-entity-definitions.md#greece-national-id-card)</br> - [芬兰国家 ID](sensitive-information-type-entity-definitions.md#finland-national-id)</br> - [波兰国家 ID (PESEL) ](sensitive-information-type-entity-definitions.md#poland-national-id-pesel)</br> - [瑞典国家 ID](sensitive-information-type-entity-definitions.md#sweden-national-id)</br> - [克罗地亚个人身份 (OIB) 编号](sensitive-information-type-entity-definitions.md#croatia-personal-identification-oib-number)</br> - [捷克个人标识号](sensitive-information-type-entity-definitions.md#czech-personal-identity-number)</br> - [丹麦个人标识号](sensitive-information-type-entity-definitions.md#denmark-personal-identification-number)</br> - [爱沙尼亚个人身份识别码](sensitive-information-type-entity-definitions.md#estonia-personal-identification-code)</br> - [匈牙利个人标识号](sensitive-information-type-entity-definitions.md#hungary-personal-identification-number)</br> - [卢森堡国家身份证号码 (自然人) ](sensitive-information-type-entity-definitions.md#luxemburg-national-identification-number-natural-persons)</br> - [卢森堡国家身份证号码 (非自然人) ](sensitive-information-type-entity-definitions.md#luxemburg-national-identification-number-non-natural-persons)</br> - [意大利财政法典](sensitive-information-type-entity-definitions.md#italy-fiscal-code)</br> - [拉脱维亚个人代码](sensitive-information-type-entity-definitions.md#latvia-personal-code)</br> - [立陶宛个人代码](sensitive-information-type-entity-definitions.md#lithuania-personal-code)</br> - [罗马尼亚个人数字代码 (CNP) ](sensitive-information-type-entity-definitions.md#romania-personal-numeric-code-cnp)</br> - [荷兰公民服务 (BSN) 编号](sensitive-information-type-entity-definitions.md#netherlands-citizens-service-bsn-number)</br> - [爱尔兰个人公共服务 (PPS) 编号](sensitive-information-type-entity-definitions.md#ireland-personal-public-service-pps-number)</br> - [保加利亚统一民号](sensitive-information-type-entity-definitions.md#bulgaria-uniform-civil-number)</br> - [比利时国家编号](sensitive-information-type-entity-definitions.md#belgium-national-number)</br> - [西班牙 DNI](sensitive-information-type-entity-definitions.md#spain-dni)</br> - [斯洛文尼亚唯一的主公民号码](sensitive-information-type-entity-definitions.md#slovenia-unique-master-citizen-number)</br> - [斯洛伐克个人号码](sensitive-information-type-entity-definitions.md#slovakia-personal-number)</br> - [葡萄牙公民卡号](sensitive-information-type-entity-definitions.md#portugal-citizen-card-number)</br> - [马耳他税务 ID 号](sensitive-information-type-entity-definitions.md#malta-tax-identification-number)</br> - [奥地利税务标识号](sensitive-information-type-entity-definitions.md#austria-tax-identification-number)</br> - [塞浦路斯税务标识号](sensitive-information-type-entity-definitions.md#cyprus-tax-identification-number)</br> - [法国税务标识号 (numéro SPI.) ](sensitive-information-type-entity-definitions.md#france-tax-identification-number)</br> - [德国税务标识号](sensitive-information-type-entity-definitions.md#germany-tax-identification-number)</br> - [希腊语税务标识号](sensitive-information-type-entity-definitions.md#greece-tax-identification-number)</br> - [匈牙利税务标识号](sensitive-information-type-entity-definitions.md#hungary-tax-identification-number)</br> - [荷兰税务标识号](sensitive-information-type-entity-definitions.md#netherlands-tax-identification-number)</br> - [波兰税务标识号](sensitive-information-type-entity-definitions.md#poland-tax-identification-number)</br> - [葡萄牙税务标识号](sensitive-information-type-entity-definitions.md#portugal-tax-identification-number)</br> - [斯洛文尼亚税务标识号](sensitive-information-type-entity-definitions.md#slovenia-tax-identification-number)</br> - [西班牙税务标识号](sensitive-information-type-entity-definitions.md#spain-tax-identification-number)</br> - [瑞典税务标识号](sensitive-information-type-entity-definitions.md#sweden-tax-identification-number)</br> - [奥地利驾驶执照](sensitive-information-type-entity-definitions.md#austria-drivers-license-number)</br> - [比利时驾驶执照号码](sensitive-information-type-entity-definitions.md#belgium-drivers-license-number)</br> - [保加利亚驾驶执照号码](sensitive-information-type-entity-definitions.md#bulgaria-drivers-license-number)</br> - [克罗地亚驾驶执照号码](sensitive-information-type-entity-definitions.md#croatia-drivers-license-number)</br> - [塞浦路斯驾驶执照号码](sensitive-information-type-entity-definitions.md#cyprus-drivers-license-number)</br> - [捷克驾驶执照号码](sensitive-information-type-entity-definitions.md#czech-drivers-license-number)</br> - [丹麦驾驶执照号码](sensitive-information-type-entity-definitions.md#denmark-drivers-license-number)</br> - [爱沙尼亚驾驶执照号码](sensitive-information-type-entity-definitions.md#estonia-drivers-license-number)</br> - [芬兰驾驶执照号码](sensitive-information-type-entity-definitions.md#finland-drivers-license-number)</br> - [法国驾驶执照号码](sensitive-information-type-entity-definitions.md#france-drivers-license-number)</br> - [德国驾驶执照编号](sensitive-information-type-entity-definitions.md#germany-drivers-license-number)</br> - [希腊驾驶执照号码](sensitive-information-type-entity-definitions.md#greece-drivers-license-number)</br> - [匈牙利驾驶执照号码](sensitive-information-type-entity-definitions.md#hungary-drivers-license-number)</br> - [爱尔兰驾驶执照号码](sensitive-information-type-entity-definitions.md#ireland-drivers-license-number)</br> - [意大利驾驶执照号码](sensitive-information-type-entity-definitions.md#italy-drivers-license-number)</br> - [拉脱维亚驾驶执照号码](sensitive-information-type-entity-definitions.md#latvia-drivers-license-number)</br> - [立陶宛驾驶执照号码](sensitive-information-type-entity-definitions.md#lithuania-drivers-license-number)</br> - [卢森堡驾驶执照号码](sensitive-information-type-entity-definitions.md#luxemburg-drivers-license-number)</br> - [马耳他驾驶执照号码](sensitive-information-type-entity-definitions.md#malta-drivers-license-number)</br> - [荷兰驾驶执照号码](sensitive-information-type-entity-definitions.md#netherlands-drivers-license-number)</br> - [波兰驾驶执照号码](sensitive-information-type-entity-definitions.md#poland-drivers-license-number)</br> - [葡萄牙驾驶执照号码](sensitive-information-type-entity-definitions.md#portugal-drivers-license-number)</br> - [罗马尼亚驾驶执照号码](sensitive-information-type-entity-definitions.md#romania-drivers-license-number)</br> - [斯洛伐克驾驶执照号码](sensitive-information-type-entity-definitions.md#slovakia-drivers-license-number)</br> - [斯洛文尼亚驾驶执照号码](sensitive-information-type-entity-definitions.md#slovenia-drivers-license-number)</br> - [西班牙驾驶执照号码](sensitive-information-type-entity-definitions.md#spain-drivers-license-number)</br> - [瑞典驾驶执照号码](sensitive-information-type-entity-definitions.md#sweden-drivers-license-number)</br> - [奥地利护照号码](sensitive-information-type-entity-definitions.md#austria-passport-number)</br> - [比利时护照号码](sensitive-information-type-entity-definitions.md#belgium-passport-number)</br> - [保加利亚护照号码](sensitive-information-type-entity-definitions.md#bulgaria-passport-number)</br> - [克罗地亚护照号码](sensitive-information-type-entity-definitions.md#croatia-passport-number)</br> - [塞浦路斯护照号码](sensitive-information-type-entity-definitions.md#cyprus-passport-number)</br> - [捷克共和国护照号码](sensitive-information-type-entity-definitions.md#czech-passport-number)</br> - [丹麦护照号码](sensitive-information-type-entity-definitions.md#denmark-passport-number)</br> - [爱沙尼亚护照号码](sensitive-information-type-entity-definitions.md#estonia-passport-number)</br> - [芬兰护照号码](sensitive-information-type-entity-definitions.md#finland-passport-number)</br> - [法国护照号码](sensitive-information-type-entity-definitions.md#france-passport-number)</br> - [德国护照号码](sensitive-information-type-entity-definitions.md#germany-passport-number)</br> - [希腊护照号码](sensitive-information-type-entity-definitions.md#greece-passport-number)</br> - [匈牙利护照号码](sensitive-information-type-entity-definitions.md#hungary-passport-number)</br> - [爱尔兰护照号码](sensitive-information-type-entity-definitions.md#ireland-passport-number)</br> - [意大利护照号码](sensitive-information-type-entity-definitions.md#italy-passport-number)</br> - [拉脱维亚护照号码](sensitive-information-type-entity-definitions.md#latvia-passport-number)</br> - [立陶宛护照号码](sensitive-information-type-entity-definitions.md#lithuania-passport-number)</br> - [卢森堡护照号码](sensitive-information-type-entity-definitions.md#luxemburg-passport-number)</br> - [马耳他护照号码](sensitive-information-type-entity-definitions.md#malta-passport-number)</br> - [荷兰护照号码](sensitive-information-type-entity-definitions.md#netherlands-passport-number)</br> - [波兰护照](sensitive-information-type-entity-definitions.md#poland-passport-number)</br> - [葡萄牙护照号码](sensitive-information-type-entity-definitions.md#portugal-passport-number)</br> - [罗马尼亚护照号码](sensitive-information-type-entity-definitions.md#romania-passport-number)</br> - [斯洛伐克护照号码](sensitive-information-type-entity-definitions.md#slovakia-passport-number)</br> - [斯洛文尼亚护照号码](sensitive-information-type-entity-definitions.md#slovenia-passport-number)</br> - [西班牙护照号码](sensitive-information-type-entity-definitions.md#spain-passport-number)</br> - [瑞典护照号码](sensitive-information-type-entity-definitions.md#sweden-passport-number)</br> - [EU 借记卡号](sensitive-information-type-entity-definitions.md#eu-debit-card-number)</br> - [所有全名](sensitive-information-type-entity-definitions.md#all-full-names)|
|隐私| 一般数据保护条例 (GDPR)|- [EU 借记卡号](sensitive-information-type-entity-definitions.md#eu-debit-card-number) </br> - [欧盟驾照号](sensitive-information-type-entity-definitions.md#eu-drivers-license-number) </br> - [欧盟国家标识号](sensitive-information-type-entity-definitions.md#eu-national-identification-number)</br> - [欧盟护照号码](sensitive-information-type-entity-definitions.md#eu-passport-number) </br> - [欧盟社会保障号码或等效标识](sensitive-information-type-entity-definitions.md#eu-social-security-number-or-equivalent-identification)</br> - [欧盟税务标识号](sensitive-information-type-entity-definitions.md#eu-tax-identification-number)|
|隐私| 德国个人身份信息 (PII) 数据|- [德国驾照号](sensitive-information-type-entity-definitions.md#germany-drivers-license-number) </br> - [德国护照号码](sensitive-information-type-entity-definitions.md#germany-passport-number)| 
|隐私| 以色列个人身份信息 (PII) 数据|- [以色列国家标识号](sensitive-information-type-entity-definitions.md#israel-national-identification-number)| 
|隐私| 以色列隐私保护|- [以色列国家标识号](sensitive-information-type-entity-definitions.md#israel-national-identification-number)</br> - [以色列银行帐号](sensitive-information-type-entity-definitions.md#israel-bank-account-number)|
|隐私| 日本个人身份信息 (PII) 数据增强|- [日本社会保险号码 (SIN) ](sensitive-information-type-entity-definitions.md#japan-social-insurance-number-sin)</br> - [日本我的号码 - 个人](sensitive-information-type-entity-definitions.md#japan-my-number---personal)</br> - [日本护照号码](sensitive-information-type-entity-definitions.md#japan-passport-number)</br> - [日本驾照号](sensitive-information-type-entity-definitions.md#japan-drivers-license-number)</br> - [所有全名](sensitive-information-type-entity-definitions.md#all-full-names)</br> - [日本物理地址](sensitive-information-type-entity-definitions.md#all-physical-addresses)|
|隐私| 日本个人身份信息 (PII) 数据|- [日本居民登记号](sensitive-information-type-entity-definitions.md#japan-resident-registration-number) </br> - [日本社会保险号码 (SIN) ](sensitive-information-type-entity-definitions.md#japan-social-insurance-number-sin)|
|隐私| 日本个人信息保护增强|- [日本社会保险号码 (SIN) ](sensitive-information-type-entity-definitions.md#japan-social-insurance-number-sin) </br> - [日本我的号码 - 个人](sensitive-information-type-entity-definitions.md#japan-my-number---personal)</br> - [日本护照号码](sensitive-information-type-entity-definitions.md#japan-passport-number) </br> - [日本驾照号](sensitive-information-type-entity-definitions.md#japan-drivers-license-number)</br> - [所有全名](sensitive-information-type-entity-definitions.md#all-full-names)</br> - [日本物理地址](sensitive-information-type-entity-definitions.md#all-physical-addresses)|
|隐私| 日本个人信息保护|- [日本居民登记号](sensitive-information-type-entity-definitions.md#japan-resident-registration-number)</br> - [日本社会保险号码 (SIN) ](sensitive-information-type-entity-definitions.md#japan-social-insurance-number-sin)|
|隐私| 沙特阿拉伯个人身份 (PII) 数据|- [沙特阿拉伯国家 ID](sensitive-information-type-entity-definitions.md#saudi-arabia-national-id)|
|隐私| 英国数据保护法案|- [英国国民保险号码 (尼诺) ](sensitive-information-type-entity-definitions.md#uk-national-insurance-number-nino) </br> - [美国/英国护照号码](sensitive-information-type-entity-definitions.md#usuk-passport-number) </br> - [SWIFT 代码](sensitive-information-type-entity-definitions.md#swift-code)|
|隐私| 英国隐私和电子通信规则|- [SWIFT 代码](sensitive-information-type-entity-definitions.md#swift-code)|
|隐私| 英国个人身份信息 (PII) 数据|- [英国国民保险号码 (尼诺) ](sensitive-information-type-entity-definitions.md#uk-national-insurance-number-nino) </br> - [美国/英国护照号码](sensitive-information-type-entity-definitions.md#usuk-passport-number)|
|隐私| 英国个人信息在线行为守则 (PIOCP)|- [英国国民保险号码 (尼诺) ](sensitive-information-type-entity-definitions.md#uk-national-insurance-number-nino) </br> - [英国国家卫生服务号码](sensitive-information-type-entity-definitions.md#uk-national-health-service-number) </br> - [SWIFT 代码](sensitive-information-type-entity-definitions.md#swift-code)|
|隐私| 美国爱国者法案增强|- [信用卡号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [美国银行帐号](sensitive-information-type-entity-definitions.md#us-bank-account-number)</br> - [ITIN (美国个人纳税人标识号) ](sensitive-information-type-entity-definitions.md#us-individual-taxpayer-identification-number-itin)  </br> - [美国社会保障号码 (SSN) ](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn)</br> - [所有全名](sensitive-information-type-entity-definitions.md#all-full-names)</br> - [美国物理地址](sensitive-information-type-entity-definitions.md#us-physical-addresses)|
|隐私| 美国爱国者法案|- [信用卡号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [美国银行帐号](sensitive-information-type-entity-definitions.md#us-bank-account-number)</br> - [ITIN (美国个人纳税人标识号) ](sensitive-information-type-entity-definitions.md#us-individual-taxpayer-identification-number-itin)  </br> - [美国社会保障号码 (SSN) ](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn)|
|隐私| 美国个人身份信息 (PII) 数据增强|- [ITIN (美国个人纳税人标识号) ](sensitive-information-type-entity-definitions.md#us-individual-taxpayer-identification-number-itin)  </br> - [美国社会保障号码 (SSN) ](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn)</br> - [美国/英国护照号码](sensitive-information-type-entity-definitions.md#usuk-passport-number)</br> - [所有全名](sensitive-information-type-entity-definitions.md#all-full-names)</br> - [美国物理地址](sensitive-information-type-entity-definitions.md#us-physical-addresses)|
|隐私| 美国个人身份信息 (PII) 数据|- [ITIN (美国个人纳税人标识号) ](sensitive-information-type-entity-definitions.md#us-individual-taxpayer-identification-number-itin)  </br> - [美国社会保障号码 (SSN) ](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn)</br> - [美国/英国护照号码](sensitive-information-type-entity-definitions.md#usuk-passport-number)|
|隐私| 增强了美国州违规通知法|- [信用卡号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [美国银行帐号](sensitive-information-type-entity-definitions.md#us-bank-account-number)</br> -[美国驾照号](sensitive-information-type-entity-definitions.md#us-drivers-license-number) </br> - [美国社会保障号码 (SSN) ](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn)</br> - [所有全名](sensitive-information-type-entity-definitions.md#all-full-names) </br> - [美国/英国护照号码](sensitive-information-type-entity-definitions.md#usuk-passport-number)</br> - [所有医疗条款和条件](sensitive-information-type-entity-definitions.md#all-medical-terms-and-conditions)|
|隐私| 美国国家违约通知法|- [信用卡号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [美国银行帐号](sensitive-information-type-entity-definitions.md#us-bank-account-number)</br> -[美国驾照号](sensitive-information-type-entity-definitions.md#us-drivers-license-number) </br> - [美国社会保障号码 (SSN) ](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn)|
|隐私| 美国国家社会保险号保密法|- [美国社会保障号码 (SSN) ](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn)|

## <a name="locations"></a>位置

DLP 策略可以查找和保护跨多个位置包含敏感信息的项。

|位置  |包括/排除范围  |数据状态  |其他先决条件 |
|---------|---------|---------|---------|
|联机Exchange电子邮件 |distribution group － 通讯组 | 移动中的数据| 否 |
|SharePoint联机网站   |sites       | 静态数据 </br> 正在使用的数据 | 否|
|OneDrive for Business 帐户| 帐户或通讯组 |静态数据 </br> 正在使用的数据|否|
|Teams 聊天和通道消息     | 帐户或通讯组 |移动中的数据 </br> 正在使用的数据 |  否       |
|Microsoft Defender for Cloud Apps   | 云应用实例       |静态数据         | - [对非 Microsoft 云应用使用数据丢失防护策略](dlp-use-policies-non-microsoft-cloud-apps.md#use-data-loss-prevention-policies-for-non-microsoft-cloud-apps)        |
|设备  |用户或组         |静态数据 </br>  正在使用的数据 </br>  移动中的数据         |- [了解Microsoft 365终结点数据丢失防护](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention) </br>- [使用终结点数据丢失防护开始](endpoint-dlp-getting-started.md#get-started-with-endpoint-data-loss-prevention) </br>- [为信息保护配置设备代理和 Internet 连接设置](device-onboarding-configure-proxy.md#configure-device-proxy-and-internet-connection-settings-for-information-protection) |
|本地存储库 (文件共享和SharePoint)     |存储 库         | 静态数据         | - [了解本地扫描程序Microsoft 365数据丢失防护](dlp-on-premises-scanner-learn.md#learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner) </br> - [使用本地扫描程序的数据丢失防护开始](dlp-on-premises-scanner-get-started.md#get-started-with-the-data-loss-prevention-on-premises-scanner)         |
|PowerBI| workspaces | 正在使用的数据 | 否|

如果选择将特定通讯组包含在 Exchange 中，则 DLP 策略的影响范围将仅限于该组的成员。 同样，排除通讯组将把该通讯组的所有成员从策略评估中排除。 可选择将策略的影响范围限定为通讯组列表、动态通讯组和安全组的成员。 一条 DLP 策略可包含不超过 50 个这种包含和排除。

如果你选择包含或排除特定的 SharePoint 网站或 OneDrive 帐户，则 DLP 策略可包含不超过 100 个此类包含和排除项。 尽管存在此限制，你可应用组织范围策略或位置整体策略来超出此限制。

如果你选择包括或排除特定 OneDrive 帐户或组，则 DLP 策略可包含不超过 100 个用户帐户或 50 个组作为包含项或排除项。

### <a name="location-support-for-how-content-can-be-defined"></a>对如何定义内容的位置支持

DLP 策略通过将敏感项匹配到敏感信息类型 (SIT) 、敏感度标签或保留标签来检测它们。 每个位置都支持定义敏感内容的不同方法。 合并策略中的位置时，内容的定义方式会因单个位置的定义方式而有所改变。 

> [!IMPORTANT]
> 为策略选择多个位置时，内容定义类别的"否"值优先于"是"值。 例如，仅选择SharePoint网站时，策略将支持按一个或多个 SIT、敏感度标签或保留标签检测敏感项。 但是，选择SharePoint网站 ***并*** Teams聊天和频道消息位置时，策略将仅支持通过 SIT 检测敏感项目。

|位置| 内容可由 SIT 定义| 内容可以定义敏感度标签| 内容可以由保留标签定义|
|---------|---------|---------|---------|
|联机Exchange电子邮件|是| 是| 否|
|SharePoint联机网站| 是| 是| 是|
|OneDrive for Business 帐户| 是| 是| 是|
|Teams聊天和频道消息 | 是| 否| 否|
|设备 |是 | 是|  否|
|Microsoft Defender for Cloud Apps | 是| 是| 是|
|本地存储库| 是| 是| 否|
|PowerBI|是 | 是| 否|

> [!NOTE]
> DLP 支持检测电子邮件和附件上的敏感度标签，请参阅， [使用敏感度标签作为 DLP 策略中的条件](dlp-sensitivity-label-as-condition.md#use-sensitivity-labels-as-conditions-in-dlp-policies)。

## <a name="rules"></a>Rules

<!--This section introduces the classifications of content that, when detected, can be protected. Link out to [Learn about sensitive information types]() and [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md#sensitive-information-type-entity-definitions) as well as labels (cross referenced by supporting workload). It will touch on the purpose of multiple conditions, confidence levels (link out to [more on confidence levels](sensitive-information-type-learn-about.md#more-on-confidence-levels)) and confidence levels video. How to use the confidence level to change the behavior of a policy in conjunction with the instance count.  eg. if you want your policy to trigger when it encounters situation DEF, set your conditions like HIJ.-->
<!--
- What is a rule in the context of a Policy?
- when and why should I have more than one rule?
- The purpose of rule groups
- How do I tune the behavior of a Policy through the tuning of rules
- what's in a rule-->

规则是 DLP 策略的业务逻辑。 它们包括：

- [**匹配**](#conditions) 时触发策略的条件
- [**条件的异常**](#exceptions)
- 触发策略 [**时要执行**](#actions)的操作
- [**用户通知**](#user-notifications-and-policy-tips) ，在用户执行触发策略的操作时通知用户，并帮助他们了解组织希望如何处理敏感信息
- 管理员配置用户 [**重写**](#user-overrides)时，允许用户有选择地替代阻止操作
- 发生规则匹配时通知管理员和其他关键利益干系人 [**的事件报告**](#incident-reports)
- [**其他选项**](#additional-options) ，用于定义规则评估的优先级，并可以停止进一步的规则和策略处理。

 策略包含一个或多个规则。 规则按顺序执行，从每个策略中优先级最高的规则开始。

### <a name="the-priority-by-which-rules-are-processed"></a>处理规则的优先级

#### <a name="hosted-service-workloads"></a>托管服务工作负荷

对于托管服务工作负荷（如 Exchange Online、SharePoint Online 和 OneDrive Entreprise），每个规则都按创建顺序分配优先级。 这意味着，创建的第一个规则具有优先级，创建的第二个规则具有第二个优先级，等等。 
  
![按优先级顺序排列的规则](../media/dlp-rules-in-priority-order.png)

对照规则评估内容时，按优先级顺序处理规则。 如果内容与多个规则匹配，则会强制执行具有 *最* 严格操作的第一个计算规则。 例如，如果内容与以下所有规则匹配，则强制执行 *规则 3* ，因为它是最高优先级、限制性最高的规则：
  
- 规则 1：仅通知用户
- 规则 2：通知用户、限制访问并允许用户替代
- *规则 3：通知用户、限制访问且不允许用户替代*
- 规则 4：限制访问

将评估规则 1、2 和 4，但不应用规则。 在此示例中，所有规则的匹配项记录在审核日志中，并显示在 DLP 报表中，即使只应用了最严格的规则。

可使用规则来满足特定保护要求，然后使用 DLP 策略将常见保护要求组合在一起，例如符合特定规则所需的所有规则。
  
例如，DLP 策略可能会帮助您检测是否存在受健康保险可携性与责任法案 (HIPAA) 约束的信息。 此 DLP 策略可以通过查找与你的组织外部人员共享的包含此敏感信息（条件）的任何文档，来帮助保护所有 SharePoint Online 站点和所有 OneDrive for Business 站点（位置）的 HIPAA 数据（对象），然后阻止对该文档的访问并发送通知（操作）。 这些要求存储为单个规则，并作为一项 DLP 策略组合在一起以简化管理和报告。
  
![图表显示了 DLP 策略包含位置和规则](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)

#### <a name="for-endpoints"></a>对于终结点

终结点上规则的优先级也会根据创建顺序分配。 这意味着，创建的第一个规则具有优先级，创建的第二个规则具有第二个优先级，等等。 

当终结点上的文件与多个 DLP 策略匹配时，在 [终结点活动中](endpoint-dlp-learn-about.md#endpoint-activities-you-can-monitor-and-take-action-on) 启用了限制性最高的第一条规则是对内容强制执行的规则。 例如，如果内容与以下所有规则匹配，则规则 2 优先于其他规则，因为它是限制最大的规则。

- 规则 1：仅审核所有活动 
- *规则 2：阻止所有活动*
- 规则 3：阻止所有活动，并使用选项让最终用户重写

在下面的示例中，规则 1 优先于其他匹配规则，因为它是限制最大的规则。

- *规则 1：阻止活动，不允许用户重写*
- 规则 2：阻止活动并允许用户重写
- 规则 3：仅审核所有活动
- 规则 4：不强制执行

会评估所有其他规则，但不会强制执行其操作。 审核日志将显示对文件应用的限制性最强的规则。 如果有多个规则匹配且限制性相同，则策略和规则优先级控制将在文件上应用的规则。

对于终结点，可以针对特定包含条件集的单个规则中的所有受支持活动配置 DLP 执行的操作。

### <a name="conditions"></a>条件

条件是包容性的，是定义要查找的规则和使用这些项的上下文的位置。 当您 *找到如下所* 示的项时，他们会告诉规则&#8212;&#8212;它是匹配项，并且策略中的其余操作应对其执行。 你可以使用条件向不同的风险级别分配不同操作。 例如，相较与组织外部人员共享的敏感信息，可在内部共享的敏感内容的风险更低、需要执行的操作更少。

> [!NOTE]
> 在主体组织的 Active Directory 或 Azure Active Directory 租户中具有非来宾帐户的用户是否被视为该组织内部人员。 

#### <a name="content-contains"></a>内容包含

 所有支持内容包含的位置 **都包含** 条件。 你可以选择每个内容类型的多个实例，并使用 **这些** (逻辑或) 或 **所有这些** (逻辑和) 运算符进一步优化条件：

- [敏感信息类型](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [敏感度标签](sensitivity-labels.md)
- [保留标签](retention.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)

根据选择将策略应用到的位置 [ () ](#location-support-for-how-content-can-be-defined) 。 

该规则将仅查找你选择的任何 **敏感度标签** 和 **保留标签** 。 

SIT 具有预定义 [**的置信度级别**](https://www.microsoft.com/videoplayer/embed/RE4Hx60) ，可根据需要进行更改。 有关详细信息，请参阅 [有关置信度级别的详细信息](sensitive-information-type-learn-about.md#more-on-confidence-levels)。 

> [!IMPORTANT]
> SIT 有两种不同的方法来定义最大唯一实例计数参数。 若要了解详细信息，请参阅[ SIT 的实例计数支持的值](create-a-custom-sensitive-information-type.md#instance-count-supported-values-for-sit)。

#### <a name="condition-context"></a>条件上下文

可用上下文选项根据所选位置而更改。 如果选择多个位置，则仅提供共同位置的条件。

##### <a name="conditions-exchange-supports"></a>条件Exchange支持

- 内容包含
- 内容从Microsoft 365共享
- 从中接收内容
- 发件人 IP 地址为
- 发件人已重写策略提示
- 发件人为
- 发件人域为
- 发件人地址包含单词
- 发件人地址包含模式
- 发件人 AD 属性包含字词或短语
- 发件人 AD 属性与模式匹配
- 发件人是其成员
- 无法扫描任何电子邮件附件的内容
- 任何电子邮件附件的内容均未完成扫描
- 附件受密码保护
- 文件扩展名为
- 收件人是其成员
- 收件人域为
- 收件人为
- 收件人地址包含字词
- 收件人地址与模式匹配
- 收件人 AD 属性包含单词或短语
- 收件人 AD 属性匹配模式
- 文档名称包含单词或短语
- 文档名称与模式匹配
- 文档属性为
- 文档大小等于或大于
- 文档内容包含单词或短语
- 文档内容与模式匹配
- 主题包含单词或短语
- 主题与模式匹配
- 主题或正文包含单词或短语
- 使用者或正文匹配模式
- 内容字符集包含单词
- 标头包含单词或短语
- 标题与模式匹配
- 消息大小等于或大于
- 消息类型为
- 消息重要性是

##### <a name="conditions-sharepoint-supports"></a>条件SharePoint支持
 
- 内容包含
- 内容从Microsoft 365共享
- 创建的文档
- 由成员创建的文档
- 文档名称包含单词或短语
- 文档名称与模式匹配
- 文档大小超过
- 文档属性为
- 文件扩展名为

##### <a name="conditions-onedrive-accounts-supports"></a>帐户支持的条件OneDrive

- 内容包含
- 内容从Microsoft 365共享
- 创建的文档
- 由成员创建的文档
- 文档名称包含单词或短语
- 文档名称与模式匹配
- 文档大小超过
- 文档属性为
- 文件扩展名为

##### <a name="conditions-teams-chat-and-channel-messages-supports"></a>聊天和频道消息Teams条件支持

- 内容包含
- 内容从Microsoft 365共享
- 发件人为 
- 发件人域为 
- 收件人域为 
- 收件人为 

##### <a name="conditions-devices-supports"></a>条件设备支持

- 内容包含
- 请参阅 [，可以监视和执行操作的终结点活动](endpoint-dlp-learn-about.md#endpoint-activities-you-can-monitor-and-take-action-on)

##### <a name="conditions-microsoft-defender-for-cloud-apps-supports"></a>条件Microsoft Defender for Cloud Apps支持

- 内容包含
- 内容从Microsoft 365共享

##### <a name="conditions-on-premises-repositories-supports"></a>本地存储库支持的条件

- 内容包含
- 文件扩展名为
- 文档属性为

##### <a name="conditions-powerbi-supports"></a>PowerBI 支持的条件

- 内容包含

#### <a name="condition-groups"></a>条件组

有时，你需要一个规则来仅识别一个内容，例如包含美国社会保障号码（由单个 SIT 定义）的所有内容。 但在许多情况下，尝试识别的项类型更复杂，因此难以定义，因此需要在定义条件时具有更大的灵活性。

例如，若要标识应遵循美国健康保险法案 (HIPAA) 的内容，需要查找：
  
- 包含特定类型敏感信息的内容，例如美国。社会安全号码或毒品管制局 (DEA) 号码。
    
    AND
    
- 更难以标识的内容，例如有关患者护理的通信，或者提供的医疗服务说明。 识别此内容需要匹配极为庞大的关键字列表中的关键字，如国际疾病分类（ICD-9-CM 或 ICD-10-CM）。
    
可以通过对条件进行分组并使用逻辑运算符 (AND 或在组之间) 来标识此类数据。
    
对于《 **美国健康保险法》 (HIPPA)**，条件按如下所示进行分组：

![HIPPA 策略条件](../media/dlp-rules-condition-groups-booleans.png)

第一组包含标识和单个的 SIT，第二组包含标识医学诊断的 SIT。

### <a name="exceptions"></a>例外

在规则中，异常定义用于从策略中排除项的条件。 从逻辑上讲，在包容性条件和上下文之后评估的独占条件。 当您发现一 *个如下所* 示且被 *使用为匹配* 项的项时，他们会告诉规则&#8212;，策略中的其余操作应对其执行， ***除非*** &#8212;... 

例如，根据 HIPPA 策略，我们可以修改规则以排除任何包含比利时驱动程序许可证号的项目，如下所示：

![具有排除项的 HIPPA 策略](../media/dlp-rule-exceptions.png)

位置支持的异常条件与所有包含条件相同，唯一的区别是每个受支持条件的"Except if"的前面。 如果规则仅包含异常，则该规则将应用于不符合排除条件的所有电子邮件或文件。

正如所有位置都支持包容性条件一样：

- 内容包含

异常为：

- **内容包含除外** 

### <a name="actions"></a>操作 

通过非独占 ***condition** _ 和排他 _*_异常筛选器_*_ 进行此操作的任何项都将具有应用到它的规则中定义的任何 _*_操作_*_ 。 必须配置所需的选项以支持该操作。 例如，如果选择具有 _ *Restrict 访问权限的Exchange或加密Microsoft 365位置* 操作中的内容*，则需要从以下选项中进行选择：

- 阻止用户访问共享SharePoint、OneDrive和Teams内容
    - 阻止所有人。 只有内容所有者、最后一个修饰符和网站管理员才能继续具有访问权限
    - 仅阻止组织外部的人员。 组织内的用户将继续拥有访问权限。
- 加密电子邮件（仅适用于 Exchange 中的内容）

规则中可用的操作取决于已选择的位置。 如果只选择要应用到的策略的一个位置，则下面列出了可用操作。

> [!IMPORTANT]
> 对于SharePoint联机和OneDrive Entreprise位置，无论是否共享文档，在检测到敏感信息后，将立即主动阻止文档，而内部用户将继续有权访问文档。

#### <a name="exchange-location-actions"></a>Exchange位置操作

- 限制访问或加密Microsoft 365位置中的内容
- 设置标头
- 删除标头
- 将消息重定向到特定用户
- 将要批准的消息转发给发件人的经理
- 将要批准的消息转发给特定审批者
- 将收件人添加到"收件人"框
- 将收件人添加到 Cc 框
- 将收件人添加到 Bcc 框
- 将发件人的经理添加为收件人
- 删除了 O365 消息加密和权限保护
- 预置电子邮件主题
- 修改电子邮件主题
- 添加 HTML 免责声明

#### <a name="sharepoint-sites-location-actions"></a>SharePoint站点位置操作

- 限制访问或加密Microsoft 365位置中的内容

#### <a name="onedrive-account-location-actions"></a>OneDrive帐户位置操作

- 限制访问或加密Microsoft 365位置中的内容

#### <a name="teams-chat-and-channel-messages-actions"></a>Teams聊天和频道消息操作

- 限制访问或加密Microsoft 365位置中的内容

#### <a name="devices-actions"></a>设备操作

- 审核或限制Windows设备上的活动

若要使用这些设置，必须在 **DLP 设置** 和要使用这些设置的策略中配置选项。 有关详细信息，请参阅 ["受限应用和应用组](dlp-configure-endpoint-settings.md#restricted-apps-and-app-groups) "。

设备位置提供许多子活动 (条件) 和操作。 若要了解详细信息，请参阅 [可监视和执行操作的终结点活动](endpoint-dlp-learn-about.md#endpoint-activities-you-can-monitor-and-take-action-on)。

选择 **审核或限制Windows设备上的活动** 时，可以通过服务域或浏览器限制用户活动，并限制 DLP 采取的操作范围：

- 所有应用
- 通过定义的受限应用列表
- 定义的受限应用组 (预览) 。

##### <a name="service-domain-and-browser-activities"></a>服务域和浏览器活动

配置 **"允许/阻止云服务域**"和 **"Unallowed 浏览器**"列表 (看到 [敏感数据) 的浏览器和域限制](dlp-configure-endpoint-settings.md#browser-and-domain-restrictions-to-sensitive-data)，并且用户尝试将受保护的文件上传到云服务域或从不受攻击的浏览器访问它时，可以将策略操作配置为`Audit only``Block with override`或`Block`配置活动。

##### <a name="file-activities-for-all-apps"></a>所有应用的文件活动

使用 **所有应用的文件活动** 选项，可以选择 **"不限制文件活动** "或 **"对特定活动应用限制**"。 当你选择对特定活动应用限制时，当用户访问受 DLP 保护的项时，将应用在此处选择的操作。 可以告知 DLP`Audit only`， `Block with override``Block` (这些用户活动中) 的操作：

- **复制到剪贴板**
- **复制到 USB 可移动驱动器** 
- **复制到网络共享**
- **Print**
- **使用未添加的蓝牙应用进行复制或移动**
- **远程桌面服务**


##### <a name="restricted-app-activities"></a>受限应用活动  

以前称为 Unallowed 应用，你在 Endpoint DLP 设置中定义要限制的应用列表。 当用户尝试使用列表中的应用访问受 DLP 保护的文件时，你可以 `Audit only`访问 `Block with override`或 `Block` 访问活动。 如果应用是受限应用组的成员，则会重写在 **受限应用活动中** 定义的 DLP 操作。 然后应用在受限应用组中定义的操作。

##### <a name="file-activities-for-apps-in-restricted-app-groups-preview"></a>受限应用组中应用的文件活动（预览）

在 Endpoint DLP 设置中定义受限制的应用组，并将受限制的应用组添加到策略。 将受限应用组添加到策略时，必须选择以下选项之一：

- 不限制文件活动
- 对所有活动应用限制
- 对特定活动应用限制

选择其中一个 *"应用限制*"选项，并且用户尝试使用受限应用组中的应用访问受 DLP 保护的文件时，`Block with override`可以`Audit only`访问或`Block`按活动访问。 在此处定义的 DLP 操作将替代 **在受限应用活动中** 定义的操作，以及应用 **的所有应用的文件活动** 。

有关详细信息，请参阅 ["受限应用和应用组](dlp-configure-endpoint-settings.md#restricted-apps-and-app-groups) "。 

#### <a name="microsoft-defender-for-cloud-apps-actions"></a>Microsoft Defender for Cloud Apps操作

- 限制访问或加密Microsoft 365位置中的内容
- 限制第三方应用

#### <a name="on-premises-repositories-actions"></a>本地存储库操作

- 限制访问或删除本地文件

#### <a name="powerbi-actions"></a>PowerBI 操作

- 使用电子邮件和策略提示通知用户
- 向管理员发送警报

#### <a name="actions-available-when-you-combine-locations"></a>组合位置时可用的操作

如果为要应用的策略选择Exchange和任何其他单个位置，

- 限制访问或加密Microsoft 365位置中的内容

和

- 非Exchange位置的所有操作

操作将可用。

如果为要应用的策略选择两个或多个非Exchange位置，

- 限制访问或加密Microsoft 365位置中的内容

AND

- 非Exchange位置的所有操作 

操作将可用。

例如，如果选择Exchange和设备作为位置，则这些操作将可用：

- 限制访问或加密Microsoft 365位置中的内容
- 审核或限制Windows设备上的活动

如果选择"设备"并Microsoft Defender for Cloud Apps，则会提供以下操作：

- 限制访问或加密Microsoft 365位置中的内容
- 审核或限制Windows设备上的活动
- 限制第三方应用

操作是否生效取决于如何配置策略的模式。 可以选择使用或不显示策略提示的测试模式下运行策略，方法是选择 **"先测试"** 选项。 通过选择"立即打开"选项，选择在创建策略一小时后立即选择运行 **策略** ，也可以选择只保存它，然后选择 **"禁用** "选项返回到该策略。 


<!-- This section needs to explain that the actions available depend on the locations selected AND that the observed behavior of a policy is produced through an interaction of the configured actions AND the configured status (off, test, apply) of a policy. It will detail the purpose of each of the available actions and the location/desired outcome interaction and provide examples eg. how to use the Restrict Third Party apps in the context of a policy that is applied to endpoints so that users can't use a upload content to a third party site or the interaction of on-premises scanner with restrict access or remove on-premises files.  Also what happens when I select multiple locations? provide abundant examples for most common scenarios-->


### <a name="user-notifications-and-policy-tips"></a>用户通知和策略提示

<!--This section introduces the business need for user notifications, what they are, their benefit, how to use them, how to customize them, and links out to 

- https://docs.microsoft.com/en-us/microsoft-365/compliance/use-notifications-and-policy-tips?view=o365-worldwide
- https://docs.microsoft.com/en-us/microsoft-365/compliance/dlp-policy-tips-reference?view=o365-worldwide

for where they are used/expected behavior-->

<!--You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.-->

当用户尝试对符合规则条件和异常的上下文中的敏感项执行操作时，可以通过用户通知电子邮件和上下文策略提示弹出窗口告知他们。 这些通知非常有用，因为它们可提高人们的认识，并帮助人们了解组织的 DLP 策略。

例如，OneDrive Entreprise网站上包含个人身份信息 (PII) 并与来宾共享的Excel工作簿等内容。

![消息栏在 Excel 2016 中显示策略提示](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)

> [!NOTE]
> 未受保护地发送通知电子邮件。

你还可以为用户提供 [替代策略](#user-overrides)的选项，以便在有有效的业务需求或策略检测到误报时，不会阻止他们。

用户通知和策略提示配置选项因所选的监视位置而异。 如果选择：

- Exchange
- SharePoint
- OneDrive
- Teams聊天和频道
- Defender for Cloud Apps


可以为各种 Microsoft 应用启用/禁用用户通知，请参阅 [数据丢失防护策略提示参考](dlp-policy-tips-reference.md#data-loss-prevention-policy-tips-reference)

- 可以使用策略提示在 **Office 365服务中** 启用/禁用通知用户。
    - 向发送、共享或上次修改内容 OR 的用户发送电子邮件通知
    - 通知特定人员

并自定义电子邮件文本、主题和策略提示文本。

![可用于Exchange、SharePoint、OneDrive、Teams聊天和频道以及Defender for Cloud应用的用户通知和策略提示配置选项](../media/dlp-user-notification-non-devices.png)

如果仅选择"设备"，则会获得可用于Exchange、SharePoint、OneDrive、Teams聊天和频道以及Defender for Cloud应用的所有相同选项，以及自定义Windows 10设备上显示的通知标题和内容的选项.

![适用于设备的用户通知和策略提示配置选项](../media/dlp-user-notification-devices.png)  

可以使用这些参数自定义文本的标题和正文。 正文文本支持以下内容：

|公用名  |参数  |示例
|---------|---------|---------|
|文件名     |%%FileName%% | Contoso doc 1 |
|进程名称     |%%ProcessName%% | Word |
|策略名称     |%%PolicyName%%| Contoso 高度机密 |
|action | %%AppliedActions%% | 将文档内容从剪贴板粘贴到另一个应用 |

**%%AppliedActions%% 将** 这些值替换为消息正文：


|操作公用名称 |替换为 %%AppliedActions%% 参数的值 |
|---------|---------|
|复制到可删除的存储    |*写入可移动存储*         |
|复制到网络共享     |*写入到网络共享*         |
|打印     |*印刷*         |
|从剪贴板粘贴  |*从剪贴板粘贴*         |
|通过蓝牙复制   |*通过蓝牙传输*         |
|使用未添加的应用打开     |*使用此应用打开*         |
|复制到远程桌面 (RDP)      |*传输到远程桌面*         |
|上传到不为人听的网站     |*上传到此网站*         |
|通过未添加的浏览器访问项目     |*使用此浏览器打开*         |

使用此自定义文本

*组织不允许通过 %%ProcessName%% 的 %%AppliedActions%% 文件名 %%FileName%% 。如果要绕过策略 %%PolicyName%%，请单击"允许"* 

在自定义通知中生成此文本：

*组织不允许通过WINWORD.EXE粘贴剪贴板文件名：Contoso 文档 1。如果要绕过策略 Contoso 高度机密，请单击"允许"按钮*
 

> [!NOTE]
> 用户通知和策略提示不适用于本地位置

> [!NOTE]
> 仅显示来自最高优先级、最具限制性的规则的策略提示。 例如，阻止访问内容的规则所提供的策略提示比起只是发送通知的规则所提供的策略提示，前者的显示优先级高于后者。 这会让用户看不到策略提示的级联方式。

若要详细了解用户通知和策略提示配置和使用，包括如何自定义通知和提示文本，请参阅 
- [发送电子邮件通知并显示 DLP 策略的策略提示](use-notifications-and-policy-tips.md#send-email-notifications-and-show-policy-tips-for-dlp-policies)。
  
<!--The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner. In addition, you can add or remove whomever you choose from the email notification.
  
In addition to sending an email notification, a user notification displays a policy tip:
  
- In Outlook and Outlook on the web.
    
- For the document on a SharePoint Online or OneDrive for Business site.
    
- In Excel, PowerPoint, and Word, when the document is stored on a site included in a DLP policy.
    
The email notification and policy tip explain why content conflicts with a DLP policy. If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification. This can help you educate users about your DLP policies and enforce them without preventing people from doing their work. Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.
  
Here's what a policy tip looks like in a OneDrive for Business account.
  
![Policy tip for a document in a OneDrive account](../media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 To learn more about user notifications and policy tips in DLP policies, see [Use notifications and policy tips](use-notifications-and-policy-tips.md).

> [!NOTE]
> The default behavior of a DLP policy, when there is no alert configured, is not to alert or trigger. This applies only to default information types. For custom information types, the system will alert even if there is no action defined in the policy.
-->

### <a name="user-overrides"></a>用户重写

**用户重写** 的目的是让用户能够绕过 DLP 策略阻止对Exchange、SharePoint、OneDrive 或Teams中的敏感项执行的操作，以便他们能够继续工作。 仅当启用了 **具有策略提示的Office 365服务中通知用户** 时，才启用用户替代，因此用户将使用通知和策略提示进行手动替代。 

![用户重写 DLP 策略的选项](../media/dlp-user-overrides.png)

> [!NOTE]
> 用户重写不适用于本地存储库位置。

通常，当你的组织首次推出策略时，用户替代非常有用。 从任何替代理由获取的反馈和识别误报有助于优化策略。 

<!-- This section covers what they are and how to best use them in conjunction with Test/Turn it on right away and link out to where to find the business justification for the override (DLP reports?  https://docs.microsoft.com/en-us/microsoft-365/compliance/view-the-dlp-reports?view=o365-worldwide)  https://docs.microsoft.com/en-us/microsoft-365/compliance/view-the-dlp-reports?view=o365-worldwide#view-the-justification-submitted-by-a-user-for-an-override-->

- 如果限制最严格的规则中的策略提示允许用户替换规则，那么替换此规则还会替换与此内容相匹配的所有其他规则。
 
<!--![User notifications and user overrides sections of DLP rule editor](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)-->
 
若要了解有关用户替代的详细信息，请参阅：

- [查看用户提交的替代理由](view-the-dlp-reports.md#view-the-justification-submitted-by-a-user-for-an-override)

### <a name="incident-reports"></a>事件报告

<!--DLP interacts with other M365 information protection services, like IR. Link this to a process outline for triaging/managing/resolving DLP incidents


https://docs.microsoft.com/en-us/microsoft-365/compliance/view-the-dlp-reports?view=o365-worldwide
https://docs.microsoft.com/en-us/microsoft-365/compliance/dlp-configure-view-alerts-policies?view=o365-worldwide-->

当项目与规则相匹配时，可向合规负责人（或所选的任何人员）发送包含事件详情的事件报告。 报表包含有关所匹配项的信息、与规则匹配的实际内容，以及上次修改内容的人员的姓名。 对于电子邮件，报告还将与 DLP 策略匹配的原始邮件包含为附件。

DLP 将事件信息馈送到其他Microsoft 365信息保护服务，例如[Microsoft 365中的预览体验成员风险管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)。 若要将事件信息获取到内部风险管理，必须将 **事件报告** 严重性级别设置为 **"高**"。

<!--![Page for configuring incident reports](../media/31c6da0e-981c-415e-91bf-d94ca391a893.png)-->

每次活动与规则匹配时，都可以发送警报，因为规则可能很嘈杂，或者可以根据一定时间段内的匹配项数或项目量将警报聚合到更少的警报中。

![每次规则匹配或聚合到更少的报表中时发送警报](../media/dlp-incident-reports-aggregation.png)

DLP 扫描电子邮件的方式与SharePoint联机或OneDrive Entreprise项不同。 在 SharePoint Online 和 OneDrive for business 中，DLP 可扫描现有项目以及新项目，并在找到匹配项时生成事件报告。 在 Exchange Online 中，DLP 仅扫描新电子邮件，并在存在策略匹配项时生成报告。 DLP ***不会*** 扫描或匹配邮箱或存档中存储的先前存在的电子邮件项目。

### <a name="additional-options"></a>其他选项

如果策略中有多个规则，则可以使用 **其他选项** 来控制进一步的规则处理（如果与正在编辑的规则匹配）以及设置规则评估的优先级。

## <a name="see-also"></a>另请参阅

- [了解数据丢失防护](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [规划数据丢失防护 (DLP) ](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [从模板创建 DLP 策略](create-a-dlp-policy-from-a-template.md#create-a-dlp-policy-from-a-template)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy)
