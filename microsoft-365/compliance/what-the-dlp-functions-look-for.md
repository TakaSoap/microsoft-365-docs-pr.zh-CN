---
title: DLP (功能) 查找哪些数据丢失防护
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
recommendations: false
description: 了解 DLP (函数) 数据丢失防护功能。
ms.openlocfilehash: 94e7ec97083a8e914ba2155d087d1c7820336805
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201777"
---
# <a name="what-the-dlp-functions-look-for"></a>DLP 函数查找的内容

DLP 策略 (数据丢失) 可以使用敏感信息类型来标识敏感项目。 信用卡号和欧盟借记卡号是敏感信息类型的示例。 敏感信息类型查找特定模式。 敏感信息类型通过查看数据的格式、校验和来验证数据，并查找相关的关键字或其他信息。 某些功能由内部函数执行。 例如，信用卡号敏感信息类型使用 函数查找格式设置为到期日期的日期。 这有助于确定数字是信用卡号。

本文介绍这些函数查找的功能，以帮助您了解预定义敏感信息类型如何工作。 有关详细信息，请参阅 [敏感信息类型实体定义](sensitive-information-type-entity-definitions.md)

## <a name="table-of-functions"></a>函数表

<br>

****

|函数名称|函数操作|是验证程序|
|---|---|:---:|
|Func_Argentina_Unique_Tax_Key|检测并验证阿根廷唯一税单|否|
|Func_aba_routing|检测 ABA 路由号码|是|
|Func_alabama_drivers_license_number|检测 Alabama 驾驶证号码|否|
|Func_alaska_delaware_oregon_drivers_license_number|检测波特兰、Delaware、俄勒冈州驾驶证号码|否|
|Func_alaska_drivers_license_number|检测 Driver's license number|否|
|Func_alberta_drivers_license_number|检测 Alberta 驱动程序的许可证号|否|
|Func_Argentina_Unique_Tax_Key|检测阿根廷唯一税单|否|
|Func_arizona_drivers_license_number|检测 Driver's license number|否|
|Func_arkansas_drivers_license_number|检测 Arkansas 驾驶证号码|否|
|Func_australian_business_number|检测澳大利亚商务号码|否|
|Func_Australian_Company_Number|检测澳大利亚公司编号|否|
|Func_australian_medical_account_number|检测澳大利亚医疗帐号|否|
|Func_australian_tax_file_number|检测澳大利亚税号|是|
|Func_austria_eu_ssn_or_equivalent|检测奥地利社会保险号|否|
|Func_austria_eu_tax_file_number|检测奥地利税号|否|
|Func_Austria_Value_Added_Tax|检测奥地利增值税|否|
|Func_belgium_national_number|检测比利时国家/区号码|否|
|Func_belgium_value_added_tax_number|检测比利时增值税编号|否|
|Func_brazil_cnpj|检测 CNPJ (巴西法律) |是|
|Func_brazil_cpf|检测巴西 CPF|是|
|Func_brazil_rg|检测巴西 RG|否|
|Func_british_columbia_drivers_license_number|检测 British Driver's license number|否|
|Func_bulgaria_eu_national_id_card|检测保加利亚统一编号|否|
|Func_california_drivers_license_number|检测加州驾驶证号码|否|
|Func_canadian_sin|检测 Canada sin|是|
|Func_chile_id_card|检测智利 ID 卡|否|
|Func_china_resident_id|检测中国居民 ID|否|
|Func_colorado_drivers_license_number|检测 Colorado driver's license number|否|
|Func_connecticut_drivers_license_number|检测 Connect一线驾驶证号码|否|
|Func_credit_card|检测信用卡|是|
|Func_croatia_id_card|检测克罗地亚 ID 卡|否|
|Func_croatia_oib_number|检测克罗地亚 OIB 号码|否|
|Func_cyprus_eu_tax_file_number|检测塞浦路斯税号|否|
|Func_czech_id_card|检测捷克语 ID 卡|否|
|Func_czech_id_card_new_format|检测新格式的捷克语 ID 卡|否|
|Func_dea_number|检测 DEA 号码|是|
|Func_denmark_eu_tax_file_number|检测丹麦个人标识号|否|
|Func_district_of_columbia_drivers_license_number|检测学区驾驶证号码|否|
|Func_estonia_eu_national_id_card|检测爱沙尼亚个人标识代码|否|
|Func_eu_debit_card|检测欧盟借记卡|否|
|Func_finnish_national_id|检测芬兰国家/区 ID|否|
|Func_florida_drivers_license_number|检测 Driver's license number|否|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|检测明尼达州、底特律、明尼达州驾驶证号码|否|
|Func_formatted_itin|检测格式化 US ITIN|是|
|Func_fr_insee|检测法国 INSEE|否|
|Func_fr_passport|检测法国护照|否|
|Func_france_eu_tax_file_number|检测法国税务文件编号|否|
|Func_france_value_added_tax_number|检测法国增值税编号|否|
|Func_french_drivers_license|检测法国驾驶证|否|
|Func_french_insee|检测法语 INSEE|否|
|Func_georgia_drivers_license_number|检测格鲁吉亚驾驶证号码|否|
|Func_german_drivers_license|检测德国驾驶证|否|
|Func_german_passport|检测德国护照|否|
|Func_german_passport_data|检测德国护照|否|
|Func_germany_eu_tax_file_number|检测德国税务文件编号|否|
|Func_germany_value_added_tax_number|检测德国增值税编号|否|
|Func_greece_eu_ssn|检测希腊 sin (AMKA) |否|
|Func_hawaii_drivers_license_number|检测太平洋驾驶证号码|否|
|Func_hong_kong_id_card|检测香港 ID 卡|否|
|Func_hungarian_value_added_tax_number|检测匈牙利增值税编号|否|
|Func_hungary_eu_national_id_card|检测匈牙利个人标识号|否|
|Func_hungary_eu_ssn_or_equivalent|检测匈牙利社会保险号|否|
|Func_hungary_eu_tax_file_number|检测匈牙利税号|否|
|Func_iban|检测 IBAN|是|
|Func_idaho_drivers_license_number|检测 Idaho 驾驶证号码|否|
|Func_illinois_drivers_license_number|检测 Driver's license number|否|
|Func_india_aadhaar|检测印度 aadhaar|是|
|Func_indiana_drivers_license_number|检测 Driver's license number|否|
|Func_iowa_drivers_license_number|检测 Driver's license number|否|
|Func_ireland_pps|检测爱尔兰 PPS|否|
|Func_israeli_national_id_number|检测以色列国民身份证号码|否|
|Func_italy_eu_national_id_card|检测意大利财政代码|否|
|Func_italy_value_added_tax_number|检测意大利增值税编号|否|
|Func_japanese_my_number_corporate|检测日本我的号码公司|是|
|Func_japanese_my_number_personal|检测日本我的个人编号|是|
|Func_jp_bank_account|检测日本银行帐户|否|
|Func_jp_bank_account_branch_code|检测日本银行帐户分支代码|否|
|Func_jp_drivers_license_number|检测日本驾驶证号码|否|
|Func_jp_passport|检测日本护照|否|
|Func_jp_resident_registration_number|检测日本居民注册号码|否|
|Func_jp_sin|检测日本 SIN|否|
|Func_jp_sin_pre_1997|检测日本 1997 年之前|否|
|Func_kansas_drivers_license_number|检测用户驾驶证号码|否|
|Func_kentucky_drivers_license_number|检测Ucksucky 驾驶证号码|否|
|Func_kentucky_massachusetts_virginia_drivers_license_number|检测 Driveruckucky， Massachusetts， Driver's license number|否|
|Func_latvia_eu_national_id_card|检测拉脱维亚个人代码|否|
|Func_lithuania_eu_tax_file_number|检测立陶宛个人代码|否|
|Func_louisiana_drivers_license_number|检测用户驾驶证号码|否|
|Func_luxemburg_eu_tax_file_number|检测位于该 (的) |否|
|Func_luxemburg_eu_tax_file_number_non_natural|检测非自然人 (的百分号) |否|
|Func_maine_drivers_license_number|检测 Maine 驾驶证号码|否|
|Func_manitoba_drivers_license_number|检测 Manitoba 驾驶证号码|否|
|Func_maryland_drivers_license_number|检测 Driver's license number|否|
|Func_massachusetts_drivers_license_number|检测 Massachusetts 驾驶证号码|否|
|Func_mexico_population_registry_code|检测墨西哥总体注册表代码|否|
|Func_michigan_minnesota_drivers_license_number|检测明尼达州驾驶证号码|否|
|Func_minnesota_drivers_license_number|检测明尼达驾驶证号码|否|
|Func_mississippi_oklahoma_drivers_license_number|检测为一位用户，一位用户，一位|否|
|Func_missouri_drivers_license_number|检测 Miss一驱动程序的许可证号|否|
|Func_montana_drivers_license_number|检测 Montana 驾驶证号码|否|
|Func_nebraska_drivers_license_number|检测 Nebraska 驾驶证号码|否|
|Func_netherlands_bsn|检测荷兰 BSN|否|
|Func_netherlands_eu_tax_file_number|检测荷兰税务文件编号|否|
|Func_netherlands_value_added_tax_number|检测荷兰增值税编号|否|
|Func_nevada_drivers_license_number|检测 Driver 的许可证号|否|
|Func_new_brunswick_drivers_license_number|检测新的 Bruns一 驱动程序的许可证编号|否|
|Func_new_hampshire_drivers_license_number|检测新剑桥郡驾驶证号码|否|
|Func_new_jersey_drivers_license_number|检测 New Jersey 驾驶证号码|否|
|Func_new_mexico_drivers_license_number|检测新墨西哥驾驶证号码|否|
|Func_new_york_drivers_license_number|检测纽约驾驶证号码|否|
|Func_new_zealand_bank_account_number|检测新西兰银行帐号|否|
|Func_new_zealand_inland_revenue_number|检测新西兰的收入数字|否|
|Func_new_zealand_ministry_of_health_number|检测新西兰卫生服务号码|否|
|Func_newfoundland_labrador_drivers_license_number|检测 Newfoundland Labrador 驾驶证号码|否|
|Func_newzealand_driver_license_number|检测新西兰驾驶证号码|否|
|Func_newzealand_social_welfare_number|检测新西兰社会电话号码|否|
|Func_north_carolina_drivers_license_number|检测 North Driver's driver's license number|否|
|Func_north_dakota_drivers_license_number|检测 North Dakota 驾驶证号码|否|
|Func_norway_id_number|检测挪威 ID 号|否|
|Func_nova_scotia_drivers_license_number|检测 Nova Scotia 驾驶证号码|否|
|Func_ohio_drivers_license_number|检测 Driver's license number|否|
|Func_ontario_drivers_license_number|检测 On一一驱动程序的许可证号|否|
|Func_pennsylvania_drivers_license_number|检测 Driver's license number|否|
|Func_pesel_identification_number|检测波兰国家/ (PESEL) |否|
|Func_poland_eu_tax_file_number|检测波兰税号|否|
|Func_polish_national_id|检测波兰身份证|否|
|Func_polish_passport_number|检测波兰护照号码|否|
|Func_polish_regon_number|检测波兰 REGON 号码|否|
|Func_portugal_eu_tax_file_number|检测葡萄牙税务标识号|否|
|Func_prince_edward_island_drivers_license_number|检测都斯万岛驾驶证号码|否|
|Func_quebec_drivers_license_number|检测 Driver's license number|否|
|Func_randomized_formatted_ssn|检测随机格式化 US SSN|是|
|Func_randomized_unformatted_ssn|检测随机的无格式 US SSN|是|
|Func_rhode_island_drivers_license_number|检测太平洋岛驾驶证号码|否|
|Func_romania_eu_national_id_card|检测 CNP (罗马尼亚个人) |否|
|Func_saskatchewan_drivers_license_number|检测 Saskatchewan 驾驶证号码|否|
|Func_slovakia_eu_national_id_card|检测斯洛伐克个人号码|否|
|Func_slovenia_eu_national_id_card|检测斯洛文尼亚唯一主公民编号|否|
|Func_slovenia_eu_tax_file_number|检测斯洛文尼亚税号|否|
|Func_south_africa_identification_number|检测南非标识号|是|
|Func_south_carolina_drivers_license_number|检测 South为 Driver's license number|否|
|Func_south_dakota_drivers_license_number|检测 South Dakota 驾驶证号码|否|
|Func_south_korea_resident_number|检测韩国居民号码|否|
|Func_spain_eu_DL_and_NI_number_citizen|检测西班牙 DL 和 NI number citizen|否|
|Func_spain_eu_DL_and_NI_number_foreigner|检测西班牙 DL 和 NI 号码检测|否|
|Func_spain_eu_driver s_license_number|检测西班牙驾驶证号码|否|
|Func_spain_eu_tax_file_number|检测西班牙税务文件编号|否|
|Func_spanish_social_security_number|检测西班牙语社会保险号|否|
|Func_ssn|检测非随机格式 US SSN 的函数|是|
|Func_sweden_eu_tax_file_number|检测瑞典税号|否|
|Func_swedish_national_identifier|检测瑞典语国家/区标识符|是|
|Func_swiss_social_security_number_ahv|检测瑞士社会保险号 AHV|否|
|Func_taiwanese_national_id|检测中国台湾地区 ID|否|
|Func_tennessee_drivers_license_number|检测用户驾驶证号码|否|
|Func_texas_drivers_license_number|检测德克萨斯州驾驶证号码|否|
|Func_Thai_Citizen_Id|检测泰语公民 ID|否|
|Func_Turkish_National_Id|检测土耳其国家/区 ID|是|
|Func_uk_drivers_license|检测英国驾驶证|否|
|Func_uk_eu_tax_file_number|检测英国唯一的纳税号码|否|
|Func_uk_nhs_number|检测英国 NHS 号码|是|
|Func_uk_nino|检测英国 NINO|否|
|Func_unformatted_canadian_sin|检测无格式加拿大 SIN|否|
|Func_unformatted_itin|检测无格式 US ITIN|是|
|Func_unformatted_ssn|检测非随机的无格式 US SSN|是|
|Func_usa_uk_passport|检测美国和英国护照|是|
|Func_utah_drivers_license_number|检测 提供驱动程序的许可证号|否|
|Func_vermont_drivers_license_number|检测 Vermont 驾驶证号码|否|
|Func_virginia_drivers_license_number|检测 Driver's license number|否|
|Func_washington_drivers_license_number|检测 Washington 驾驶证号码|否|
|Func_west_virginia_drivers_license_number|检测 West 的 Driver's license number|否|
|Func_wisconsin_drivers_license_number|检测 Driver's license number|否|
|Func_wyoming_drivers_license_number|检测 Wyoming driver's license number|否|
|

## <a name="func_us_date"></a>Func_us_date

Func_us_date查找采用通用美国格式的日期。 常用格式为"month/day/year"、"month-day-year"和"month day year"。 月份的名称或缩写不区分大小写。

示例：

- 2016 年 12 月 2 日
- 2016 年 12 月 2 日
- 2016 年 12 月 2 日
- 12/2/2016
- 12/02/16
- 2016 年 12 月 2 日
- 12-2-16

接受月份名称：

- 英语
  - 1 月、2 月、3 月、4 月、5 月、7 月、8 月、9 月、10 月、11 月、12 月
  - 1.2 月。3 月。4 月。6 月 8 月。9 月。11 月。12 月

## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates E.U 中查找日期 格式 (美国以外以及美国) ，例如"day/month/year"、"day-month-year"和"day month year"。 月份的名称或缩写不区分大小写。

示例：

- 2016 年 12 月 2 日
- 2016 年 12 月 2 日
- 12 月 16 日
- 2/12/2016
- 02/12/16
- 2016 年 12 月 2 日
- 2-12-16

接受月份名称：

- 英语
  - 1 月、2 月、3 月、4 月、5 月、7 月、8 月、9 月、10 月、11 月、12 月
  - 1.2 月。3 月。4 月。6 月 8 月。9 月。11 月。12 月
- 荷兰语
  - januari、februari、maart、April、mei、juni、augusti、augustus、September、ocktober、October、November、December
  - jan feb maart apr mei jun 7 月 8 月 9 月 oct okt nov dec
- 法语
  - janvier、février、mars、avril、mai、juin juillet、ao以t、9embre、octobre、novembre、décembre
  - janv。 févr。 mars avril mai juin juil. ao9 月。 oct. nov. déc.
- 德语
  - jnuar、februar、mrrz、April、mai、juni augusti、August、September、oktober、November、dezember
  - Jan./J以n。 2 月：Mrrz Apr. Mai Juni Juni Juni Augi，9 月。正常。 11 月，Dez.
- 意大利语
  - gennaio， febbraio， marzo， aprile， mag一， giugno， luglio， agosto， settembre， ottobre， novembre， dicembre
  - genn。 febbr. mar. apr. 洋红色。 giugno luglio ag. sett。 ott。 nov. dic.
- 葡萄牙语
  - jane一、一切、março、marto、abril、maio、junho、7ho、agosto、setembro、outubro、novembro、dezembro
  - jan fev mar abr mai jun 七月前设置 nov dez
- 西班牙语
  - enero、febrero、marzo、abril、mayo、junio、mayio、agosto、juniembre、octubre、no一mbre、diciembre
  - enero 2 月。 marzo abr。 mayo jun. 7。 agosto9./set。 oct. nov. dic.

## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (弃) 

> [!NOTE]
> 此函数已弃用，因为它仅支持葡萄牙语月份名称，现在该名称已包含在上面的  `Func_eu_date` 函数中。

此函数查找在葡萄牙语中常用的格式的日期。 此函数的格式与 相同，  `Func_eu_date` 仅在所使用的语言中不同。

示例：

- 2 Dez 2016
- 02 dez 2016
- 2 Dez 16
- 2/12/2016
- 02/12/16
- 2-Dez-2016
- 2-12-16

接受月份名称：

- 葡萄牙语
  - jane一、一切、março、marto、abril、maio、junho、7ho、agosto、setembro、outubro、novembro、dezembro
  - jan fev mar abr mai jun 七月前设置 nov dez

## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (弃用) 

> [!NOTE]
> 此函数已弃用，因为它仅支持荷兰语月份名称，这些月份名称现在包含在上面的  `Func_eu_date` 函数中。

此函数查找常用的荷兰语格式的日期。 此函数的格式与 相同，  `Func_eu_date` 仅在所使用的语言中不同。

示例：

- 2 Mei 2016
- 02 mei 2016
- 2 Mei 16
- 2/12/2016
- 02/12/16
- 2-Mei-2016
- 2-12-16

接受月份名称：

- 荷兰语
  - januari、februari、maart、April、mei、juni、augusti、augustus、September、ocktober、October、November、December
  - jan feb maart apr mei jun 7 月 9 月 9 月 out okt nov dec

## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date查找采用信用卡和借记卡常用格式的日期。 此函数将匹配格式为"month/year"、"month-year"、"[month name] year"和"[month abbreviation] year"的日期。 月份的名称或缩写不区分大小写。

示例：

- MM/YY -- 例如，01/11 或 1/11
- MM/YYYY -- 例如，01/2011 或 1/2011
- MM-YY - 例如，01-22 或 1-11
- MM-YYYY - 例如，01-2000 或 1-2000

以下格式支持 YY 或 YYYY：

- Month-YYYY - 例如 Jan-2010、january-2010、Jan-10 或 january-10
- 月 YYYY - 例如，"january 2010"或"Jan 2010"或"january 10"或"Jan 10"
- MonthYYYY - 例如，"january2010"或"Jan2010"或"january10"或"Jan10"
- Month/YYYY - 例如，"january/2010"或"Jan/2010"或"january/10"或"Jan/10"

接受月份名称：

- 英语
  - 1 月、2 月、3 月、4 月、5 月、7 月、8 月、9 月、10 月、11 月、12 月
  - 1 月 3 月 3 月 4 月 6 月 8 月 11 月

## <a name="func_us_address"></a>Func_us_address

Func_us_address查找美国州名称或邮政编码，后跟有效的邮政编码。 邮政编码必须是与美国州名称或缩写相关联的正确邮政编码之一。 美国州名称和邮政编码不能用标点符号或字母分隔。

示例：

- Washington 98052
- Washington 98052-9998
- WA 98052
- WA 98052-9998
