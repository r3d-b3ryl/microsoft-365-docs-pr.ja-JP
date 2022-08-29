---
title: データ損失防止ポリシーリファレンス
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
description: DLP ポリシー コンポーネントと構成リファレンス
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 1ddae6821c528d14b603668d943cc70abc069cdd
ms.sourcegitcommit: e6595be36bbaba244439bd59dbae935e2b258ded
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2022
ms.locfileid: "67450127"
---
# <a name="data-loss-prevention-policy-reference"></a>データ損失防止ポリシーリファレンス

Microsoft Purview データ損失防止 (DLP) ポリシーには、構成するコンポーネントが多数あります。 効果的なポリシーを作成するには、各コンポーネントの目的とその構成がポリシーの動作をどのように変更するかを理解する必要があります。 この記事では、DLP ポリシーの詳細な構造について説明します。

## <a name="policy-templates"></a>ポリシー テンプレート 

DLP ポリシー テンプレートは、次の 4 つのカテゴリに事前に並べ替えられています。

- **財務** 情報の種類を検出して保護できるもの。
- **医療情報と健康** 情報の種類を検出して保護できるもの。
- **プライバシー** 情報の種類を検出して保護できるもの。
- 他の 1 つが組織のニーズを満たしていない場合に、独自のポリシーを構築するために使用できる **カスタム** テンプレート。

次の表に、すべてのポリシー テンプレートとその対象となる機密情報の種類 (SIT) を示します。 

更新日: 2021 年 6 月 23 日

|カテゴリ|テンプレート | SIT |
|---------|---------|---------|
|財務的| オーストラリアの金融データ| - [SWIFT コード](sit-defn-swift-code.md) </br> -  [オーストラリアの税ファイル番号](sit-defn-australia-tax-file-number.md) </br> - [オーストラリアの銀行口座番号](sit-defn-australia-bank-account-number.md) </br> - [クレジット カード番号](sit-defn-credit-card-number.md)|
|財務的| カナダ 財務データ |- [クレジット カード番号](sit-defn-credit-card-number.md) </br> - [カナダの銀行口座番号](sit-defn-canada-bank-account-number.md)|
|財務的| フランス 財務データ |- [クレジット カード番号](sit-defn-credit-card-number.md) </br> - [EU デビット カード番号](sit-defn-eu-debit-card-number.md)|
|財務的| ドイツの金融データ |- [クレジット カード番号](sit-defn-credit-card-number.md) </br> - [EU デビット カード番号](sit-defn-eu-debit-card-number.md)|
|財務的| イスラエルの金融データ |- [イスラエルの銀行口座番号](sit-defn-israel-bank-account-number.md) </br> - [SWIFT コード](sit-defn-swift-code.md) </br> - [クレジット カード番号](sit-defn-credit-card-number.md)|
|財務的| 日本の金融データ |- [日本の銀行口座番号](sit-defn-japan-bank-account-number.md)</br> - [クレジット カード番号](sit-defn-credit-card-number.md)|
|財務的| PCI データ セキュリティ基準 (PCI DSS)|- [クレジット カード番号](sit-defn-credit-card-number.md)|
|財務的| サウジアラビアのサイバー犯罪対策法|- [SWIFT コード](sit-defn-swift-code.md) </br> - [国際銀行口座番号 (IBAN)](sit-defn-international-banking-account-number.md)|
|財務的| サウジアラビアの金融データ |- [クレジット カード番号](sit-defn-credit-card-number.md) </br> - [SWIFT コード](sit-defn-swift-code.md) </br> - [国際銀行口座番号 (IBAN)](sit-defn-international-banking-account-number.md)|
|財務的| 英国財務データ|- [クレジット カード番号](sit-defn-credit-card-number.md) </br> - [EU デビット カード番号](sit-defn-eu-debit-card-number.md) </br> - [SWIFT コード](sit-defn-swift-code.md)|
|財務的| 米国財務データ|- [クレジット カード番号](sit-defn-credit-card-number.md) </br> - [米国の銀行口座番号](sit-defn-us-bank-account-number.md)</br> - [ABA ルーティング番号](sit-defn-aba-routing.md)|
|財務的| 米国連邦取引委員会 (FTC) の消費者保護規則|- [クレジット カード番号](sit-defn-credit-card-number.md) </br> - [米国の銀行口座番号](sit-defn-us-bank-account-number.md)</br> - [ABA ルーティング番号](sit-defn-aba-routing.md)|
|財務的| 米国グラムリーチ-ブリリー法 (GLBA) の強化|- [クレジット カード番号](sit-defn-credit-card-number.md) </br> - [米国の銀行口座番号](sit-defn-us-bank-account-number.md)</br> - [米国の個人納税者識別番号 (ITIN)](sit-defn-us-individual-taxpayer-identification-number.md)  </br> - [米国の社会保障番号 (SSN)](sit-defn-us-social-security-number.md)</br> - [米国/英国のパスポート番号](sit-defn-us-uk-passport-number.md) </br> -[米国の運転免許証番号](sit-defn-us-drivers-license-number.md)</br> - [すべてのフル ネーム](sit-defn-all-full-names.md)</br> - [米国の物理アドレス](sit-defn-us-physical-addresses.md)|
|財務的| 米国のグラム リーチ ブライリー法 (GLBA)|- [クレジット カード番号](sit-defn-credit-card-number.md) </br> - [米国の銀行口座番号](sit-defn-us-bank-account-number.md)</br> - [米国の個人納税者識別番号 (ITIN)](sit-defn-us-individual-taxpayer-identification-number.md)  </br> - [米国の社会保障番号 (SSN)](sit-defn-us-social-security-number.md)|
|医療と健康| オーストラリア健康記録法 (HRIP 法) の強化 |- [オーストラリアの税ファイル番号](sit-defn-australia-tax-file-number.md)</br> - [オーストラリアの医療アカウント番号](sit-defn-australia-medical-account-number.md)</br> - [すべてのフル ネーム](sit-defn-all-full-names.md) </br> - [すべての医療契約条件](sit-defn-all-medical-terms-conditions.md) </br> - [オーストラリアの物理アドレス](sit-defn-australia-physical-addresses.md)|
|医療と健康| オーストラリアの保健記録法 (HRIP 法)|- [オーストラリアの税ファイル番号](sit-defn-australia-tax-file-number.md) </br> - [オーストラリアの医療アカウント番号](sit-defn-australia-medical-account-number.md)|
|医療と健康| カナダの健康情報法 (HIA) |- [カナダのパスポート番号](sit-defn-canada-passport-number.md) </br> - [カナダの社会保険番号](sit-defn-canada-social-insurance-number.md) </br> - [カナダの正常性サービス番号](sit-defn-canada-health-service-number.md) </br> - [カナダの個人の健康識別番号](sit-defn-canada-personal-health-identification-number.md)|
|医療と健康| カナダ個人健康情報法 (PHIA) Manitoba|- [カナダの社会保険番号](sit-defn-canada-social-insurance-number.md) </br> - [カナダの正常性サービス番号](sit-defn-canada-health-service-number.md) </br> - [カナダの個人の健康識別番号](sit-defn-canada-personal-health-identification-number.md)|
|医療と健康| カナダ個人健康法 (PHIPA) Ontario |- [カナダのパスポート番号](sit-defn-canada-passport-number.md) </br> - [カナダの社会保険番号](sit-defn-canada-social-insurance-number.md) </br> - [カナダの正常性サービス番号](sit-defn-canada-health-service-number.md) </br> - [カナダの個人の健康識別番号](sit-defn-canada-personal-health-identification-number.md)|
|医療と健康| 英国 医療報告書法へのアクセス|- [英国の国民健康サービス番号](sit-defn-uk-national-health-service-number.md) </br> - [英国の国民保険番号 (NINO)](sit-defn-uk-national-insurance-number.md)|
|医療と健康| 米国医療保険法 (HIPAA) の強化|</br> - [病気の国際分類 (ICD-9-CM)](sit-defn-international-classification-of-diseases-icd-9-cm.md) </br> - [病気の国際分類 (ICD-10-CM)](sit-defn-international-classification-of-diseases-icd-10-cm.md) </br> - [すべてのフル ネーム](sit-defn-all-full-names.md) </br> - [すべての医療契約条件](sit-defn-all-medical-terms-conditions.md) </br> - [米国の物理アドレス](sit-defn-us-physical-addresses.md)|
|医療と健康| 米国の医療保険法 (HIPAA)| - [病気の国際分類 (ICD-9-CM)](sit-defn-international-classification-of-diseases-icd-9-cm.md) </br> - [病気の国際分類 (ICD-10-CM)](sit-defn-international-classification-of-diseases-icd-10-cm.md)|
|プライバシー| オーストラリアプライバシー法の強化|- [オーストラリアの運転免許証番号](sit-defn-australia-drivers-license-number.md) </br> - [オーストラリアのパスポート番号](sit-defn-australia-passport-number.md) </br> - [すべてのフル ネーム](sit-defn-all-full-names.md) </br> - [すべての医療契約条件](sit-defn-all-medical-terms-conditions.md) </br> - [オーストラリアの物理アドレス](sit-defn-australia-physical-addresses.md)|
|プライバシー| オーストラリアのプライバシー保護法|- [オーストラリアのドライバー ライセンス番号](sit-defn-australia-drivers-license-number.md)</br> - [オーストラリアのパスポート番号](sit-defn-australia-passport-number.md)|
|プライバシー| オーストラリアの個人情報 (PII) データ|- [オーストラリアの税ファイル番号](sit-defn-australia-tax-file-number.md) </br> - [オーストラリアの運転免許証番号](sit-defn-australia-drivers-license-number.md)|
|プライバシー| カナダの個人情報 (PII) データ|- [カナダの運転免許証番号](sit-defn-canada-drivers-license-number.md) </br> - [カナダの銀行口座番号](sit-defn-canada-bank-account-number.md) </br> - [カナダのパスポート番号](sit-defn-canada-passport-number.md) </br> - [カナダの社会保険番号](sit-defn-canada-social-insurance-number.md) </br> - [カナダの正常性サービス番号](sit-defn-canada-health-service-number.md) </br> - [カナダの個人の健康識別番号](sit-defn-canada-personal-health-identification-number.md)|
|プライバシー| カナダの個人情報保護法 (PIPA)|- [カナダのパスポート番号](sit-defn-canada-passport-number.md) </br> - [カナダの社会保険番号](sit-defn-canada-social-insurance-number.md) </br> - [カナダの正常性サービス番号](sit-defn-canada-health-service-number.md) </br> - [カナダの個人の健康識別番号](sit-defn-canada-personal-health-identification-number.md)|
|プライバシー| カナダの個人情報保護法 (PIPEDA)|- [カナダの運転免許証番号](sit-defn-canada-drivers-license-number.md) </br> - [カナダの銀行口座番号](sit-defn-canada-bank-account-number.md) </br> - [カナダのパスポート番号](sit-defn-canada-passport-number.md) </br> - [カナダの社会保険番号](sit-defn-canada-social-insurance-number.md) </br> - [カナダの正常性サービス番号](sit-defn-canada-health-service-number.md) </br> - [カナダの個人の健康識別番号](sit-defn-canada-personal-health-identification-number.md)|
|プライバシー| フランスのデータ保護法|- [フランスの国民 ID カード (CNI)](sit-defn-france-national-id-card.md)</br> - [フランスの社会保障番号 (INSEE)](sit-defn-france-social-security-number.md)|
|プライバシー| フランスの個人情報 (PII) データ|- [フランスの社会保障番号 (INSEE)](sit-defn-france-social-security-number.md) </br> - [フランスの運転免許証番号](sit-defn-france-drivers-license-number.md) </br> - [フランスのパスポート番号](sit-defn-france-passport-number.md) </br> - [フランスの国民 ID カード (CNI)](sit-defn-france-national-id-card.md)|
|プライバシー| 一般的なデータ保護規則 (GDPR) の強化|- [オーストリアの物理アドレス](sit-defn-austria-physical-addresses.md) </br> - [ベルギーの物理アドレス](sit-defn-belgium-physical-addresses.md) </br> - [ブルガリアの物理アドレス](sit-defn-bulgaria-physical-addresses.md) </br> - [クロアチアの物理アドレス](sit-defn-croatia-physical-addresses.md) </br> - [キプロスの物理アドレス](sit-defn-cyprus-physical-addresses.md) </br> - [チェコ共和国の物理アドレス](sit-defn-czech-republic-physical-addresses.md)</br> - [デンマークの物理アドレス](sit-defn-denmark-physical-addresses.md)</br> - [エストニアの物理アドレス](sit-defn-estonia-physical-addresses.md)</br> - [フィンランドの物理アドレス](sit-defn-finland-physical-addresses.md)</br> - [フランスの物理アドレス](sit-defn-france-physical-addresses.md)</br> - [ドイツの物理アドレス](sit-defn-germany-physical-addresses.md)</br> - [ギリシャの物理アドレス](sit-defn-greece-physical-addresses.md)</br> - [ハンガリーの物理アドレス](sit-defn-hungary-physical-addresses.md)</br> - [アイルランドの物理アドレス](sit-defn-ireland-physical-addresses.md)</br> - [イタリアの物理アドレス](sit-defn-italy-physical-addresses.md)</br> - [ラトビアの物理アドレス](sit-defn-latvia-physical-addresses.md)</br> - [リトアニアの物理アドレス](sit-defn-lithuania-physical-addresses.md)</br> - [ルクセンブルクの物理アドレス](sit-defn-luxemburg-physical-addresses.md)</br> - [マルタの物理アドレス](sit-defn-malta-physical-addresses.md)</br> - [オランダの物理アドレス](sit-defn-netherlands-physical-addresses.md)</br> - [ポーランドの物理アドレス](sit-defn-poland-physical-addresses.md)</br> - [ポルトガル語の物理アドレス](sit-defn-portugal-physical-addresses.md)</br> - [ルーマニアの物理アドレス](sit-defn-romania-physical-addresses.md)</br> - [スロバキアの物理アドレス](sit-defn-slovakia-physical-addresses.md)</br> - [スロベニアの物理アドレス](sit-defn-slovenia-physical-addresses.md)</br> - [スペインの物理アドレス](sit-defn-spain-physical-addresses.md)</br> - [スウェーデンの物理アドレス](sit-defn-sweden-physical-addresses.md)</br> - [オーストリア社会保障番号](sit-defn-austria-social-security-number.md) </br> - [フランス社会保障番号 (INSEE)](sit-defn-france-social-security-number.md)</br> - [ギリシャ社会保障番号 (AMKA)](sit-defn-greece-social-security-number.md)</br> - [ハンガリー社会保障番号 (TAJ)](sit-defn-hungary-social-security-number.md)</br> - [スペイン 社会保障番号 (SSN)](sit-defn-spain-social-security-number.md)</br> - [オーストリア ID カード](sit-defn-austria-identity-card.md) </br> - [キプロス ID カード](sit-defn-cyprus-identity-card.md) </br> - [ドイツ ID カード番号](sit-defn-germany-identity-card-number.md)</br> - [マルタ ID カード番号](sit-defn-malta-identity-card-number.md)</br> - [フランス国民 ID カード (CNI)](sit-defn-france-national-id-card.md)</br> - [ギリシャ国民 ID カード](sit-defn-greece-national-id-card.md)</br> - [フィンランドの国民 ID](sit-defn-finland-national-id.md)</br> - [ポーランド国民 ID (PESEL)](sit-defn-poland-national-id.md)</br> - [スウェーデンの国民 ID](sit-defn-sweden-national-id.md)</br> - [クロアチア個人識別 (OIB) 番号](sit-defn-croatia-personal-identification-number.md) </br> - [チェコの個人 ID 番号](sit-defn-czech-personal-identity-number.md)</br> - [デンマークの個人識別番号](sit-defn-denmark-personal-identification-number.md)</br> - [エストニアの個人識別コード](sit-defn-estonia-personal-identification-code.md)</br> - [ハンガリーの個人識別番号](sit-defn-hungary-personal-identification-number.md)</br> - [Luxemburg 国民識別番号の自然人](sit-defn-luxemburg-national-identification-number-natural-persons.md)</br> - [Luxemburg 国民識別番号 (非自然人)](sit-defn-luxemburg-national-identification-number-non-natural-persons.md)</br> - [イタリア会計コード](sit-defn-italy-fiscal-code.md)</br> - [ラトビアの個人コード](sit-defn-latvia-personal-code.md)</br> - [リトアニアの個人コード](sit-defn-lithuania-personal-code.md)</br> - [ルーマニア個人用数値コード (CNP)](sit-defn-romania-personal-numeric-code.md)</br> - [オランダ市民サービス (BSN) 番号](sit-defn-netherlands-citizens-service-number.md)</br> - [アイルランド個人公共サービス (PPS) 番号](sit-defn-ireland-personal-public-service-number.md)</br> - [ブルガリアの統一市民番号](sit-defn-bulgaria-uniform-civil-number.md) </br> - [ベルギーの国民番号](sit-defn-belgium-national-number.md) </br> - [スペイン DNI](sit-defn-spain-dni.md)</br> - [スロベニア 固有のマスター 市民番号](sit-defn-slovenia-unique-master-citizen-number.md)</br> - [スロバキアの個人番号](sit-defn-slovakia-personal-number.md)</br> - [ポルトガル 市民カード番号](sit-defn-portugal-citizen-card-number.md)</br> - [マルタ税 ID 番号](sit-defn-malta-tax-identification-number.md)</br> - [オーストリアの税識別番号](sit-defn-austria-tax-identification-number.md) </br> - [キプロス税識別番号](sit-defn-cyprus-tax-identification-number.md) </br> -[フランス税識別番号 (numéro SPI.)](sit-defn-france-tax-identification-number.md)</br> - [ドイツの税識別番号](sit-defn-germany-tax-identification-number.md)</br> - [ギリシャ語税識別番号](sit-defn-greece-tax-identification-number.md)</br> - [ハンガリー税識別番号](sit-defn-hungary-tax-identification-number.md)</br> - [オランダの税識別番号](sit-defn-netherlands-tax-identification-number.md)</br> - [ポーランドの納税者番号](sit-defn-poland-tax-identification-number.md)</br> - [ポルトガルの税識別番号](sit-defn-portugal-tax-identification-number.md)</br> - [スロベニアの納税者番号](sit-defn-slovenia-tax-identification-number.md)</br> - [スペインの納税者番号](sit-defn-spain-tax-identification-number.md)</br> - [スウェーデンの税識別番号](sit-defn-sweden-tax-identification-number.md)</br> - [オーストリア運転免許証](sit-defn-austria-drivers-license-number.md) </br> - [ベルギーの運転免許証番号](sit-defn-belgium-drivers-license-number.md) </br> - [ブルガリアの運転免許証番号](sit-defn-bulgaria-drivers-license-number.md) </br> - [クロアチアの運転免許証番号](sit-defn-croatia-drivers-license-number.md) </br> - [キプロスの運転免許証番号](sit-defn-cyprus-drivers-license-number.md) </br> - [チェコの運転免許証番号](sit-defn-czech-drivers-license-number.md) </br> - [デンマークの運転免許証番号](sit-defn-denmark-drivers-license-number.md)</br> - [エストニアの運転免許証番号](sit-defn-estonia-drivers-license-number.md)</br> - [フィンランドの運転免許証番号](sit-defn-finland-drivers-license-number.md)</br> - [フランスの運転免許証番号](sit-defn-france-drivers-license-number.md)</br> - [ドイツの運転免許証番号](sit-defn-germany-drivers-license-number.md)</br> - [ギリシャ の運転免許証番号](sit-defn-greece-drivers-license-number.md) </br> - [ハンガリーの運転免許証番号](sit-defn-hungary-drivers-license-number.md)</br> - [アイルランドの運転免許証番号](sit-defn-ireland-drivers-license-number.md)</br> - [イタリア の運転免許証番号](sit-defn-italy-drivers-license-number.md)</br> - [ラトビアの運転免許証番号](sit-defn-latvia-drivers-license-number.md)</br> - [リトアニアの運転免許証番号](sit-defn-lithuania-drivers-license-number.md)</br> - [Luxemburg ドライバーのライセンス番号](sit-defn-luxemburg-drivers-license-number.md)</br> - [マルタ運転免許証番号](sit-defn-malta-drivers-license-number.md)</br> - [オランダの運転免許証番号](sit-defn-netherlands-drivers-license-number.md)</br> - [ポーランドの運転免許証番号](sit-defn-poland-drivers-license-number.md)</br> - [ポルトガルの運転免許証番号](sit-defn-portugal-drivers-license-number.md)</br> - [ルーマニアの運転免許証番号](sit-defn-romania-drivers-license-number.md)</br> - [スロバキアの運転免許証番号](sit-defn-slovakia-drivers-license-number.md)</br> - [スロベニアの運転免許証番号](sit-defn-slovenia-drivers-license-number.md)</br> - [スペインの運転免許証番号](sit-defn-spain-drivers-license-number.md)</br> - [スウェーデンの運転免許証番号](sit-defn-sweden-drivers-license-number.md)</br> - [オーストリアのパスポート番号](sit-defn-austria-passport-number.md) </br> - [ベルギーのパスポート番号](sit-defn-belgium-passport-number.md) </br> - [ブルガリアのパスポート番号](sit-defn-bulgaria-passport-number.md) </br> - [クロアチアのパスポート番号](sit-defn-croatia-passport-number.md) </br> - [キプロスパスポート番号](sit-defn-cyprus-passport-number.md) </br> - [チェコ共和国のパスポート番号](sit-defn-czech-passport-number.md) </br> - [デンマークのパスポート番号](sit-defn-denmark-passport-number.md)</br> - [エストニアのパスポート番号](sit-defn-estonia-passport-number.md)</br> - [フィンランドのパスポート番号](sit-defn-finland-passport-number.md)</br> - [フランスのパスポート番号](sit-defn-france-passport-number.md)</br> - [ドイツのパスポート番号](sit-defn-germany-passport-number.md)</br> - [ギリシャパスポート番号](sit-defn-greece-passport-number.md)</br> - [ハンガリーのパスポート番号](sit-defn-hungary-passport-number.md)</br> - [アイルランドのパスポート番号](sit-defn-ireland-passport-number.md)</br> - [イタリア のパスポート番号](sit-defn-italy-passport-number.md)</br> - [ラトビアパスポート番号](sit-defn-latvia-passport-number.md)</br> - [リトアニアパスポート番号](sit-defn-lithuania-passport-number.md)</br> - [Luxemburg Passport Number](sit-defn-luxemburg-passport-number.md)</br> - [マルタパスポート番号](sit-defn-malta-passport-number.md)</br> - [オランダのパスポート番号](sit-defn-netherlands-passport-number.md)</br> - [ポーランド のパスポート](sit-defn-poland-passport-number.md)</br> - [ポルトガルパスポート番号](sit-defn-portugal-passport-number.md)</br> - [ルーマニアパスポート番号](sit-defn-romania-passport-number.md)</br> - [スロバキアパスポート番号](sit-defn-slovakia-passport-number.md)</br> - [スロベニアのパスポート番号](sit-defn-slovenia-passport-number.md)</br> - [スペインのパスポート番号](sit-defn-spain-passport-number.md)</br> - [スウェーデンのパスポート番号](sit-defn-sweden-passport-number.md)</br> - [EU デビット カード番号](sit-defn-eu-debit-card-number.md)</br> - [すべてのフル ネーム](sit-defn-all-full-names.md)|
|プライバシー| EU 一般データ保護規則 (GDPR)|- [EU デビット カード番号](sit-defn-eu-debit-card-number.md) </br> - [EU の運転免許証番号](sit-defn-eu-drivers-license-number.md) </br> - [EU の国民識別番号](sit-defn-eu-national-identification-number.md)</br> - [EU パスポート番号](sit-defn-eu-passport-number.md) </br> - [EU 社会保障番号または同等の ID](sit-defn-eu-social-security-number-equivalent-identification.md)</br> - [EU の税識別番号](sit-defn-eu-tax-identification-number.md)|
|プライバシー| ドイツの個人情報 (PII) データ|- [ドイツの運転免許証番号](sit-defn-germany-drivers-license-number.md) </br> - [ドイツのパスポート番号](sit-defn-germany-passport-number.md)| 
|プライバシー| イスラエルの個人情報 (PII) データ|- [イスラエルの国民識別番号](sit-defn-israel-national-identification-number.md)| 
|プライバシー| イスラエルのプライバシー保護|- [イスラエルの国民識別番号](sit-defn-israel-national-identification-number.md)</br> - [イスラエルの銀行口座番号](sit-defn-israel-bank-account-number.md)|
|プライバシー| 日本の個人を特定できる情報 (PII) データの強化|- [日本社会保険番号 (SIN)](sit-defn-japan-social-insurance-number.md)</br> - [Japan My Number - Personal](sit-defn-japan-my-number-personal.md)</br> - [日本のパスポート番号](sit-defn-japan-passport-number.md)</br> - [日本の運転免許証番号](sit-defn-japan-drivers-license-number.md)</br> - [すべてのフル ネーム](sit-defn-all-full-names.md)</br> - [日本の物理アドレス](sit-defn-all-physical-addresses.md)|
|プライバシー| 日本の個人情報 (PII) データ|- [日本居住者登録番号](sit-defn-japan-resident-registration-number.md) </br> - [日本社会保険番号 (SIN)](sit-defn-japan-social-insurance-number.md)|
|プライバシー| 日本の個人情報の保護強化|- [日本社会保険番号 (SIN)](sit-defn-japan-social-insurance-number.md) </br> - [Japan My Number - Personal](sit-defn-japan-my-number-personal.md)</br> - [日本のパスポート番号](sit-defn-japan-passport-number.md) </br> - [日本の運転免許証番号](sit-defn-japan-drivers-license-number.md)</br> - [すべてのフル ネーム](sit-defn-all-full-names.md)</br> - [日本の物理アドレス](sit-defn-all-physical-addresses.md)|
|プライバシー| 日本の個人情報保護|- [日本居住者登録番号](sit-defn-japan-resident-registration-number.md)</br> - [日本社会保険番号 (SIN)](sit-defn-japan-social-insurance-number.md)|
|プライバシー| サウジアラビア個人識別可能 (PII) データ|- [サウジアラビアの国民 ID](sit-defn-saudi-arabia-national-id.md)|
|プライバシー| 英国 データ保護法|- [英国の国民保険番号 (NINO)](sit-defn-uk-national-insurance-number.md) </br> - [米国/英国のパスポート番号](sit-defn-us-uk-passport-number.md) </br> - [SWIFT コード](sit-defn-swift-code.md)|
|プライバシー| 英国 プライバシーと電子通信に関する規則|- [SWIFT コード](sit-defn-swift-code.md)|
|プライバシー| 英国 個人を特定できる情報 (PII) データ|- [英国の国民保険番号 (NINO)](sit-defn-uk-national-insurance-number.md) </br> - [米国/英国のパスポート番号](sit-defn-us-uk-passport-number.md)|
|プライバシー| 英国 個人情報オンライン実践コード (PIOCP)|- [英国の国民保険番号 (NINO)](sit-defn-uk-national-insurance-number.md) </br> - [英国の国民健康サービス番号](sit-defn-uk-national-health-service-number.md) </br> - [SWIFT コード](sit-defn-swift-code.md)|
|プライバシー| 米国愛国者法の強化|- [クレジット カード番号](sit-defn-credit-card-number.md) </br> - [米国の銀行口座番号](sit-defn-us-bank-account-number.md)</br> - [米国の個人納税者識別番号 (ITIN)](sit-defn-us-individual-taxpayer-identification-number.md)  </br> - [米国の社会保障番号 (SSN)](sit-defn-us-social-security-number.md)</br> - [すべてのフル ネーム](sit-defn-all-full-names.md)</br> - [米国の物理アドレス](sit-defn-us-physical-addresses.md)|
|プライバシー| 米国の愛国者法|- [クレジット カード番号](sit-defn-credit-card-number.md) </br> - [米国の銀行口座番号](sit-defn-us-bank-account-number.md)</br> - [米国の個人納税者識別番号 (ITIN)](sit-defn-us-individual-taxpayer-identification-number.md)  </br> - [米国の社会保障番号 (SSN)](sit-defn-us-social-security-number.md)|
|プライバシー| 米国個人を特定できる情報 (PII) データの強化|- [米国の個人納税者識別番号 (ITIN)](sit-defn-us-individual-taxpayer-identification-number.md)  </br> - [米国の社会保障番号 (SSN)](sit-defn-us-social-security-number.md)</br> - [米国/英国のパスポート番号](sit-defn-us-uk-passport-number.md)</br> - [すべてのフル ネーム](sit-defn-all-full-names.md)</br> - [米国の物理アドレス](sit-defn-us-physical-addresses.md)|
|プライバシー| 米国の個人情報 (PII) データ|- [米国の個人納税者識別番号 (ITIN)](sit-defn-us-individual-taxpayer-identification-number.md)  </br> - [米国の社会保障番号 (SSN)](sit-defn-us-social-security-number.md)</br> - [米国/英国のパスポート番号](sit-defn-us-uk-passport-number.md)|
|プライバシー| 米国の州違反通知法の強化|- [クレジット カード番号](sit-defn-credit-card-number.md) </br> - [米国の銀行口座番号](sit-defn-us-bank-account-number.md)</br> -[米国の運転免許証番号](sit-defn-us-drivers-license-number.md) </br> - [米国の社会保障番号 (SSN)](sit-defn-us-social-security-number.md)</br> - [すべてのフル ネーム](sit-defn-all-full-names.md) </br> - [米国/英国のパスポート番号](sit-defn-us-uk-passport-number.md)</br> - [すべての医療契約条件](sit-defn-all-medical-terms-conditions.md)|
|プライバシー| 米国の個人情報漏洩の通知に関する州法|- [クレジット カード番号](sit-defn-credit-card-number.md) </br> - [米国の銀行口座番号](sit-defn-us-bank-account-number.md)</br> -[米国の運転免許証番号](sit-defn-us-drivers-license-number.md) </br> - [米国の社会保障番号 (SSN)](sit-defn-us-social-security-number.md)|
|プライバシー| 米国の社会保障番号の機密保持に関する州法|- [米国の社会保障番号 (SSN)](sit-defn-us-social-security-number.md)|

## <a name="locations"></a>場所

DLP ポリシーは、複数の場所にわたって機密情報を含むアイテムを検索して保護できます。

|場所  |スコープを含める/除外する  |データの状態  |その他の前提条件 |
|---------|---------|---------|---------|
|Exchange 電子メール をオンラインで送信する |配布グループ | data-in-motion| 不要 |
|SharePoint オンライン サイト   |sites       | data-at-rest </br> data-in-use | 不要|
|OneDrive for Business アカウント| アカウントまたは配布グループ |data-at-rest </br> data-in-use|不要|
|Teams チャットおよびチャネル メッセージ     | アカウントまたは配布グループ |data-in-motion </br> data-in-use |  不要       |
|Microsoft Defender for Cloud Apps   | クラウド アプリ インスタンス       |data-at-rest         | - [Microsoft 以外のクラウド アプリにデータ損失防止ポリシーを使用する](dlp-use-policies-non-microsoft-cloud-apps.md#use-data-loss-prevention-policies-for-non-microsoft-cloud-apps)        |
|デバイス  |ユーザーまたはグループ         |data-at-rest </br>  data-in-use </br>  data-in-motion         |- [エンドポイントのデータ損失防止について学習する](endpoint-dlp-learn-about.md) </br>- [エンドポイントデータ損失防止の概要](endpoint-dlp-getting-started.md) </br>- [Information Protectionのデバイス プロキシとインターネット接続の設定を構成する](device-onboarding-configure-proxy.md#configure-device-proxy-and-internet-connection-settings-for-information-protection) |
|オンプレミス リポジトリ (ファイル共有と SharePoint)    |リポジトリ         | data-at-rest         | - [データ損失防止のオンプレミス スキャナーについて説明します](dlp-on-premises-scanner-learn.md) </br> - [データ損失防止のオンプレミス スキャナーの概要](dlp-on-premises-scanner-get-started.md#get-started-with-the-data-loss-prevention-on-premises-scanner)         |
|Power BI| ワークスペース | data-in-use | 不要|

Exchange に特定の配布グループを含めるように選択した場合、DLP ポリシーはそのグループのメンバーにのみ適用されます。 同様に、配布グループを除外すると、その配布グループのすべてのメンバーがポリシー評価から除外されます。 ポリシーを配布リストのメンバー、動的配布グループ、セキュリティ グループの範囲にすることができます。 DLP ポリシーには、このような追加および除外を 50 個まで含めることができます。

特定の SharePoint サイトまたは OneDrive アカウントを含めるか、除外するかを選択した場合、DLP ポリシーに含めることができるのは、100 を超えることはできません。 こうした制限はありますが、組織全体のポリシーまたは場所全体に適用されるポリシーを適用することで、この制限を超えることができます。

特定の OneDrive アカウントまたはグループを含めるか、除外するかを選択した場合、DLP ポリシーに含めることができるのは、ユーザー アカウントなら 100 までで、グループなら 50 までです。

### <a name="location-support-for-how-content-can-be-defined"></a>コンテンツを定義する方法に関する場所のサポート

DLP ポリシーでは、機密情報の種類 (SIT) または秘密度ラベル、または保持ラベルに一致させることで、機密アイテムを検出します。 各場所では、機密コンテンツを定義するさまざまな方法がサポートされています。 ポリシー内の場所を組み合わせると、コンテンツを定義する方法が、1 つの場所で定義される方法から変わる可能性があります。 

> [!IMPORTANT]
> ポリシーに複数の場所を選択すると、コンテンツ定義カテゴリの "no" 値が "yes" 値よりも優先されます。 たとえば、SharePoint サイトのみを選択した場合、ポリシーでは、1 つ以上の SIT、秘密度ラベル、または保持ラベルによる機密アイテムの検出がサポートされます。 ただし、SharePoint サイトと Teams チャット ***と*** チャネル メッセージの場所を選択すると、ポリシーでは SIT による機密アイテムの検出のみがサポートされます。

|場所| コンテンツは SIT で定義できます| コンテンツは秘密度ラベルを定義できます| コンテンツは保持ラベルで定義できます|
|---------|---------|---------|---------|
|Exchange 電子メール をオンラインで送信する|はい| はい| 不要|
|SharePoint オンライン サイト| はい| はい| はい|
|OneDrive for Business アカウント| はい| はい| はい|
|Teams チャットメッセージとチャネル メッセージ | はい| 不要| 不要|
|デバイス |はい | はい|  不要|
|Microsoft Defender for Cloud Apps | はい| はい| はい|
|オンプレミスのリポジトリ| はい| はい| いいえ|
|Power BI|はい | はい| 不要|

> [!NOTE]
> DLP では、機密性の高いドキュメントを検出する条件としてトレーニング可能な分類子を使用する (プレビュー段階で) サポートされます。 コンテンツは、Exchange Online、SharePoint Online サイト、OneDrive for Business アカウント、Teams チャットとチャネル、デバイスのトレーニング可能な分類子によって定義できます。 詳細については、「 [トレーニング可能な分類子](classifier-learn-about.md)」を参照してください。

> [!NOTE]
> DLP では、電子メールと添付ファイルの秘密度ラベルの検出がサポートされています。 詳細については、「 [DLP ポリシーの条件として秘密度ラベルを使用する](dlp-sensitivity-label-as-condition.md#use-sensitivity-labels-as-conditions-in-dlp-policies)」を参照してください。

## <a name="rules"></a>ルール

<!--This section introduces the classifications of content that, when detected, can be protected. Link out to [Learn about sensitive information types]() and [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md#sensitive-information-type-entity-definitions) as well as labels (cross referenced by supporting workload). It will touch on the purpose of multiple conditions, confidence levels (link out to [more on confidence levels](sensitive-information-type-learn-about.md#more-on-confidence-levels)) and confidence levels video. How to use the confidence level to change the behavior of a policy in conjunction with the instance count.  eg. if you want your policy to trigger when it encounters situation DEF, set your conditions like HIJ.-->
<!--
- What is a rule in the context of a Policy?
- when and why should I have more than one rule?
- The purpose of rule groups
- How do I tune the behavior of a Policy through the tuning of rules
- what's in a rule-->

ルールは DLP ポリシーのビジネス ロジックです。 次の要素で構成されます。

- 一致した場合にポリシーをトリガーする [**条件**](#conditions)
- 条件の [**例外**](#exceptions)
- ポリシーがトリガーされたときに実行する [**アクション**](#actions)
- ポリシーをトリガーする操作を行うときにユーザーに [**通知するユーザー通知**](#user-notifications-and-policy-tips)と、組織が機密情報の扱いを求める方法を教育するのに役立ちます。
- 管理者が構成した場合 [**のユーザー の上書き**](#user-overrides)、ユーザーがブロックアクションを選択的にオーバーライドできるようにする
- ルールの一致が発生したときに管理者やその他の主要な利害関係者に通知する [**インシデント レポート**](#incident-reports)
- ルールの評価の優先度を定義し、さらにルールとポリシーの処理を停止できる [**追加オプション**](#additional-options)。

 ポリシーには、1 つ以上のルールが含まれています。 ルールは、各ポリシー内の最も高位のルールから順に実行されます。

### <a name="the-priority-by-which-rules-are-processed"></a>処理するルールの優先度

#### <a name="hosted-service-workloads"></a>ホストされたサービス ワークロード

ホストされるサービス ワークロード (Exchange Online、SharePoint Online、OneDrive for Businessなど) の場合、各ルールには、作成された順序で優先順位が割り当てられます。 つまり、最初に作成されたルールには優先順位が優先され、2 番目に作成されたルールには 2 番目の優先度が設定されます。
  
![優先度順のルール](../media/dlp-rules-in-priority-order.png)

コンテンツがルールに対して評価されると、ルールは優先度順に処理されます。 コンテンツが複数のルールと一致する場合、 *最も* 制限の厳しいアクションを持つ最初のルールが適用されます。 たとえば、コンテンツが次のすべての規則と一致する場合、 *ルール 3* は最も優先度が高く、最も制限の厳しいルールであるため、適用されます。
  
- ルール 1: ユーザーに通知のみを行う
- ルール 2: ユーザーに通知する、アクセスを制限する、ユーザーによる上書きを許可する
- *規則 3: ユーザーに通知し、アクセスを制限し、ユーザーのオーバーライドを許可しない*
- 規則 4: アクセスを制限する

ルール 1、2、および 4 は評価されますが、適用されません。 この例では、最も制限の厳しい規則のみが適用されている場合でも、すべてのルールの一致が監査ログに記録され、DLP レポートに表示されます。

ルールを使用して特定の保護要件を満たし、DLP ポリシーを使用して一般的な保護要件をグループ化できます (たとえば、特定の規制に準拠する必要のあるすべてのルール)。
  
たとえば、Health Insurance Portability and Accountability Act (HIPAA) の対象となる情報の存在を検出する際に役立つ DLP ポリシーがあるとします。 この DLP ポリシーは、HIPAA データ (対象) をすべての SharePoint Online サイトと OneDrive for Business サイト (場所) で保護するために、組織外の人物と共有するこの機密情報が含まれるドキュメント (条件) を検出し、そのドキュメントに対するアクセスをブロックして通知を送信 (アクション) できます。 これらの要件は、個別のルールとして保存され、簡単に管理およびレポートする DLP ポリシーとしてまとめてグループ化されます。
  
![図は、DLP ポリシーに場所とルールが含まれていることを示しています。](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)

#### <a name="for-endpoints"></a>エンドポイントの場合

エンドポイントのルールの優先度も、エンドポイントの作成順序に従って割り当てられます。 つまり、最初に作成されたルールには優先順位が優先され、2 番目に作成されたルールには 2 番目の優先度が設定されます。 

エンドポイント上のファイルが複数の DLP ポリシーと一致する場合、 [エンドポイント アクティビティ](endpoint-dlp-learn-about.md#endpoint-activities-you-can-monitor-and-take-action-on) に対して最も制限の厳しい適用が有効になっている最初のルールは、コンテンツに適用されます。 たとえば、コンテンツが次のすべての規則と一致する場合、ルール 2 は最も制限が厳しいため、他のルールよりも優先されます。

- 規則 1: すべてのアクティビティのみを監査する
- *規則 2: すべてのアクティビティをブロックする*
- ルール 3: エンド ユーザーがオーバーライドするオプションを使用してすべてのアクティビティをブロックする

次の例では、ルール 1 は最も制限が厳しいため、他の一致するルールよりも優先されます。

- *ルール 1: アクティビティをブロックし、ユーザーのオーバーライドを許可しない*
- ルール 2: アクティビティをブロックし、ユーザーのオーバーライドを許可する
- 規則 3: すべてのアクティビティのみを監査する
- 規則 4: 適用なし

他のすべてのルールは評価されますが、そのアクションは適用されません。 監査ログには、ファイルに適用される最も制限の厳しい規則が表示されます。 一致するルールが複数あり、同じように制限が厳しい場合は、ポリシーとルールの優先順位によって、ファイルに適用されるルールが制御されます。

### <a name="conditions"></a>条件

条件は包括的であり、ルールで検索する内容と、それらの項目が使用されているコンテキストを定義する場所です。 *このような* アイテムが見つかるとルール&#8212;が表示され、一 *致&#8212;同様* に使用され、ポリシー内の残りのアクションを実行する必要があります。 条件を使用して、さまざまな操作をリスクレベル別に割り当てることができます。 たとえば、組織内で共有されている機密コンテンツは、組織外のユーザーと共有されている機密コンテンツよりリスク レベルが低く、必要なアクションを少なくする、といったことができます。

> [!NOTE]
> ホストの組織の Active Directory または Azure Active Directory のテナントにゲスト以外のアカウントを持っているユーザーは、組織内のユーザーと見なされます。 

#### <a name="content-contains"></a>コンテンツが含まれている

 **コンテンツに含まれる** 条件をサポートするすべての場所。 各コンテンツ タイプの複数のインスタンスを選択し、 **次のいずれかの** (論理 OR) 演算子または **すべての** (論理 AND) 演算子を使用して条件をさらに絞り込むことができます。

- [機密情報の種類](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [秘密度ラベル](sensitivity-labels.md)
- [保持ラベル](retention.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)
- [トレーニング可能な分類子](classifier-learn-about.md) (プレビュー段階) 

ポリシーを適用する [場所](#location-support-for-how-content-can-be-defined) によって異なります。

このルールでは、選択した **秘密度ラベル** と **保持ラベル** の存在のみが検索されます。

SIT には事前に定義された [**信頼レベル**](https://www.microsoft.com/videoplayer/embed/RE4Hx60) があり、必要に応じて変更できます。 詳細については、「 [信頼度レベルの詳細」を](sensitive-information-type-learn-about.md#more-on-confidence-levels)参照してください。

> [!IMPORTANT]
> SIT には、最大一意のインスタンス数パラメーターを定義する 2 つの異なる方法があります。 詳細については、「[SIT のインスタンス数のサポート値](sit-limits.md#instance-count-supported-values-for-sit)」を参照してください。

#### <a name="condition-context"></a>条件コンテキスト

使用可能なコンテキスト オプションは、選択した場所によって変わります。 複数の場所を選択した場合は、場所に共通する条件のみが使用できます。

##### <a name="conditions-exchange-supports"></a>Exchange がサポートする条件

- コンテンツが含まれている
- コンテンツは Microsoft 365 から共有されます
- コンテンツの受信元
- 送信者の IP アドレスが
- 送信者がポリシー ヒントをオーバーライドしました
- 送信者が
- 送信者のドメインが次の場合
- 送信者のアドレスに単語が含まれている
- 送信者のアドレスにパターンが含まれています
- Sender AD 属性に単語または語句が含まれている
- Sender AD 属性がパターンと一致する
- 送信者は次のメンバーです。
- メールの添付ファイルのコンテンツをスキャンできなかった
- メールの添付ファイルのコンテンツのスキャンが完了しなかった
- 添付ファイルがパスワードで保護されている
- ファイル拡張子は次の形式です。
- 受信者は次のメンバーです。
- 受信者ドメインが
- 受信者が
- 受信者のアドレスに単語が含まれている
- 受信者のアドレスがパターンと一致している
- Recipient AD 属性に単語または語句が含まれている
- 受信者 AD 属性がパターンと一致する
- ドキュメント名に単語または語句が含まれている
- ドキュメント名がパターンと一致する
- 文書のプロパティが
- ドキュメント サイズが等しいか、ドキュメント サイズより大きい
- ドキュメント コンテンツに単語または語句が含まれている
- ドキュメント コンテンツがパターンと一致する
- 件名に単語または語句が含まれている
- 件名がパターンと一致している
- 件名または本文に単語または語句が含まれている
- 件名または本文がパターンに一致する
- コンテンツ文字セットに単語が含まれている
- ヘッダーに単語または語句が含まれている
- ヘッダーがパターンと一致している
- メッセージ サイズが等しいか、またはそれより大きい
- メッセージの種類は次の形式です。
- メッセージの重要度は

##### <a name="conditions-sharepoint-supports"></a>SharePoint がサポートする条件
 
- コンテンツが含まれている
- コンテンツは Microsoft 365 から共有されます
- によって作成されたドキュメント
- のメンバーによって作成されたドキュメント
- ドキュメント名に単語または語句が含まれている
- ドキュメント名がパターンと一致する
- ドキュメント サイズを超える
- 文書のプロパティが
- ファイル拡張子は次の形式です。

##### <a name="conditions-onedrive-accounts-supports"></a>OneDrive アカウントがサポートする条件

- コンテンツが含まれている
- コンテンツは Microsoft 365 から共有されます
- によって作成されたドキュメント
- のメンバーによって作成されたドキュメント
- ドキュメント名に単語または語句が含まれている
- ドキュメント名がパターンと一致する
- ドキュメント サイズを超える
- 文書のプロパティが
- ファイル拡張子は次の形式です。

##### <a name="conditions-teams-chat-and-channel-messages-supports"></a>Teams チャットとチャネル メッセージがサポートする条件

- コンテンツが含まれている
- コンテンツは Microsoft 365 から共有されます
- 送信者が 
- 送信者のドメインが次の場合 
- 受信者ドメインが 
- 受信者が 

##### <a name="conditions-devices-supports"></a>デバイスがサポートする条件

- コンテンツが含まれている
- ユーザーは、Edge から機密性の高い Web サイトにアクセスしました。 詳細については、「 [シナリオ 6:機密サービス ドメインでのユーザー アクティビティを監視または制限する](endpoint-dlp-using.md#scenario-6-monitor-or-restrict-user-activities-on-sensitive-service-domains) 」を参照してください。
- ファイル拡張子は次の形式です。
- ファイルの種類は次の形式です。
- [監視およびアクションを実行できるエンドポイント アクティビティを](endpoint-dlp-learn-about.md#endpoint-activities-you-can-monitor-and-take-action-on)参照してください。

##### <a name="conditions-microsoft-defender-for-cloud-apps-supports"></a>Microsoft Defender for Cloud Appsがサポートする条件

- コンテンツが含まれている
- コンテンツは Microsoft 365 から共有されます

##### <a name="conditions-on-premises-repositories-supports"></a>オンプレミス リポジトリがサポートする条件

- コンテンツが含まれている
- ファイル拡張子は次の形式です。
- 文書のプロパティが

##### <a name="conditions-powerbi-supports"></a>PowerBI がサポートする条件

- コンテンツが含まれている

#### <a name="condition-groups"></a>条件グループ

場合によっては、1 つの SIT によって定義される米国社会保障番号を含むすべてのコンテンツのように、1 つだけを識別するルールが必要な場合があります。 しかし、多くのシナリオでは、特定しようとしている項目の種類がより複雑になり、定義が難しくなるため、条件の定義に柔軟性が必要になります。

たとえば、米国の健康保険法 (HIPAA) の適用対象のコンテンツを特定するには、次を検索する必要があります。
  
- 特定の種類の機密情報 (社会保障番号や麻薬取締局 (DEA) 番号など) を含んでいるコンテンツ。
    
    AND
    
- 特定がより難しいコンテンツ (患者の治療に関する通信記録や提供された医療サービスの説明など)。 コンテンツを特定するには、国際疾病分類 (ICD-9-CM または ICD-10-CM) などの大きなキーワード リストからキーワードを一致させる必要があります。
    
この種類のデータを識別するには、条件をグループ化し、グループ間で論理演算子 (AND、OR) を使用します。
    
**米国健康保険法 (HIPPA)** の場合、条件は次のようにグループ化されます。

![HIPPA ポリシーの条件](../media/dlp-rules-condition-groups-booleans.png)

最初のグループには識別および個別の SIT が含まれており、2 番目のグループには医療診断を識別する SIT が含まれます。

### <a name="exceptions"></a>例外

ルールでは、例外は、ポリシーから項目を除外するために使用される条件を定義します。 論理的には、包括的な条件とコンテキストの後に評価される排他的条件。 *次* のように見え、一 *致するように使用* されているアイテムが見つかるとルールに&#8212;を伝え、ポリシー内の残りのアクションは if.. を ***除いて*** 実行する必要があります。&#8212; 

たとえば、HIPPA ポリシーに従って、次のように、ベルギーのドライバー ライセンス番号を含むアイテムを除外するようにルールを変更できます。

![除外を含む HIPPA ポリシー](../media/dlp-rule-exceptions.png)

場所によってサポートされる例外条件は、すべての包含条件と同じですが、唯一の違いは、サポートされている各条件の先頭に "Except if" を付加することです。 ルールに例外のみが含まれている場合は、除外条件を満たしていないすべてのメールまたはファイルに適用されます。

すべての場所で包括的な条件がサポートされているのと同じように、

- コンテンツが含まれている

例外は次のようになります。

- コンテンツに含まれる **場合を除く** 

### <a name="actions"></a>Actions 

包括的な ***conditions** _ フィルターと排他 _*_例外_*_ フィルターを使用するアイテムには、ルールで定義されているすべての _*_アクション_*_ が適用されます。 アクションをサポートするために必要なオプションを構成する必要があります。 たとえば、_Restrict access を使用して Exchange を選択 *するか、Microsoft 365 locations* アクションのコンテンツを暗号化* する場合は、次のオプションから選択する必要があります。

- ユーザーが共有 SharePoint、OneDrive、Teams のコンテンツにアクセスできないようにする
    - すべてのユーザーをブロックします。 コンテンツ所有者、最後の修飾子、サイト管理者のみが引き続きアクセス権を持ちます
    - 組織外のユーザーのみをブロックします。 組織内のユーザーは引き続きアクセス権を持ちます。
- 電子メール メッセージを暗号化する (Exchange のコンテンツにのみ適用)

ルールで使用できるアクションは、選択された場所によって異なります。 適用するポリシーの場所を 1 つだけ選択した場合、使用可能なアクションを次に示します。

> [!IMPORTANT]
> SharePoint Online およびOneDrive for Business場所のドキュメントは、ドキュメントが共有されているかどうかに関係なく、機密情報を検出した直後にすべての外部ユーザーに対して積極的にブロックされますが、内部ユーザーは引き続きドキュメントにアクセスできます。

#### <a name="exchange-location-actions"></a>Exchange の場所のアクション

- Microsoft 365 の場所でコンテンツへのアクセスを制限または暗号化する
- ヘッダーを設定する
- ヘッダーを削除する
- 特定のユーザーにメッセージをリダイレクトする
- 送信者のマネージャーに承認メッセージを転送する
- 承認メッセージを特定の承認者に転送する
- [宛先] ボックスに受信者を追加する
- [Cc] ボックスに受信者を追加する
- [Bcc] ボックスに受信者を追加する
- 送信者のマネージャーを受信者として追加する
- O365 メッセージの暗号化と権利保護を削除しました
- 件名Email先頭に追加する
- 件名Email変更する
- HTML 免責事項を追加する

#### <a name="sharepoint-sites-location-actions"></a>SharePoint サイトの場所のアクション

- Microsoft 365 の場所でコンテンツへのアクセスを制限または暗号化する

#### <a name="onedrive-account-location-actions"></a>OneDrive アカウントの場所のアクション

- Microsoft 365 の場所でコンテンツへのアクセスを制限または暗号化する

#### <a name="teams-chat-and-channel-messages-actions"></a>Teams チャットとチャネル メッセージのアクション

- Microsoft 365 の場所でコンテンツへのアクセスを制限または暗号化する

#### <a name="devices-actions"></a>デバイスのアクション

<!-- - Restrict access or encrypt the content in Microsoft 365 locations-->
- ユーザーが Windows デバイス上の Microsoft Edge ブラウザーで機密性の高い Web サイトにアクセスする場合に、アクティビティを監査または制限します。 詳細については、「 [シナリオ 6:機密性の高いサービス ドメインでのユーザー アクティビティを監視または制限する」](endpoint-dlp-using.md#scenario-6-monitor-or-restrict-user-activities-on-sensitive-service-domains) を参照してください。
- Windows デバイス上のアクティビティを監査または制限する

使用 `Audit or restrict activities on Windows devices`するには、 **DLP 設定** と、それらを使用するポリシーでオプションを構成する必要があります。 詳細については、「 [制限付きアプリとアプリ グループ](dlp-configure-endpoint-settings.md#restricted-apps-and-app-groups) 」を参照してください。

デバイスの場所は、多くのサブアクティビティ (条件) とアクションを提供します。 詳細については、「 [監視してアクションを実行できるエンドポイント アクティビティ](endpoint-dlp-learn-about.md#endpoint-activities-you-can-monitor-and-take-action-on)」を参照してください。

**Windows デバイスでアクティビティを監査または制限** するを選択すると、サービス ドメインまたはブラウザーによってユーザー アクティビティを制限し、DLP が実行するアクションの範囲を指定できます。

- すべてのアプリ
- 定義する制限付きアプリの一覧
- 定義する制限付きアプリ グループ (プレビュー)。

##### <a name="service-domain-and-browser-activities"></a>サービス ドメインとブラウザーのアクティビティ

**クラウド サービス ドメインの許可/ブロック** と **未承認のブラウザー** の一覧 ([機密データに対するブラウザーとドメインの制限](dlp-configure-endpoint-settings.md#browser-and-domain-restrictions-to-sensitive-data)を参照) を構成し、ユーザーが保護されたファイルをクラウド サービス ドメインにアップロードするか、未承認のブラウザーからアクセスしようとすると、ポリシー アクションをアクティビティ `Block with override`(または`Block`アクティビティ) に`Audit only`構成できます。

##### <a name="file-activities-for-all-apps"></a>すべてのアプリ向けファイル アクティビティ

**[すべてのアプリのファイル アクティビティ**] オプションでは、[**ファイル アクティビティを制限しない**] または [特定のアクティビティ **に制限を適用する]** を選択します。 特定のアクティビティに制限を適用することを選択すると、ここで選択したアクションは、ユーザーが DLP で保護されたアイテムにアクセスしたときに適用されます。 次のユーザー アクティビティに対して DLP に対して `Audit only`、 `Block with override``Block` (アクション) を指示できます。

- **クリップボードにコピーする**
- **USB リムーバブル ドライブにコピーする** 
- **ネットワーク共有にコピーする**
- **印刷**
- **未変更の Bluetooth アプリを使用してコピーまたは移動する**
- **リモート デスクトップ サービス**


##### <a name="restricted-app-activities"></a>制限されたアプリのアクティビティ  

以前は未承認アプリと呼ばれ、制限を適用するエンドポイント DLP 設定でアプリの一覧を定義します。 ユーザーが一覧にあるアプリを使用して DLP で保護されたファイルにアクセスしようとすると、アクティビティ、または`Block`アクティビティ`Block with override`のいずれかを実行できます`Audit only`。 **制限付きアプリ アクティビティ** で定義された DLP アクションは、アプリが制限付きアプリ グループのメンバーである場合にオーバーライドされます。 その後、制限付きアプリ グループで定義されているアクションが適用されます。

##### <a name="file-activities-for-apps-in-restricted-app-groups-preview"></a>制限されたアプリ グループ内のアプリのファイル アクティビティ (プレビュー)

エンドポイント DLP 設定で制限付きアプリ グループを定義し、制限付きアプリ グループをポリシーに追加します。 制限付きアプリ グループをポリシーに追加する場合は、次のいずれかのオプションを選択する必要があります。

- ファイル アクティビティを制限しない
- すべてのアクティビティに制限を適用する
- 特定のアクティビティに制限を適用する

[*制限の適用]* オプションのいずれかを選択し、ユーザーが制限付きアプリ グループ内のアプリを使用して DLP で保護されたファイルにアクセスしようとすると、`Audit only``Block with override`アクティビティを使用できます`Block`。 ここで定義する DLP アクションは、 **アプリのすべてのアプリの制限付きアプリ アクティビティ** と **File アクティビティ** で定義されているアクションよりも優先されます。

詳細については、「 [制限付きアプリとアプリ グループ](dlp-configure-endpoint-settings.md#restricted-apps-and-app-groups) 」を参照してください。 

#### <a name="microsoft-defender-for-cloud-apps-actions"></a>Microsoft Defender for Cloud Appsアクション

- Microsoft 365 の場所でコンテンツへのアクセスを制限または暗号化する
- サード パーティ製アプリを制限する

#### <a name="on-premises-repositories-actions"></a>オンプレミスリポジトリのアクション

- オンプレミス ファイルへのアクセスの制限または削除

#### <a name="powerbi-actions"></a>PowerBI アクション

- メールおよびポリシー ヒントでユーザーに通知する
- 管理者にアラートを送信する

#### <a name="actions-available-when-you-combine-locations"></a>場所を結合するときに使用できるアクション

ポリシーを適用する Exchange とその他の単一の場所を選択した場合、

- Microsoft 365 の場所でコンテンツへのアクセスを制限または暗号化する

and

- Exchange 以外の場所のすべてのアクション

アクションが使用可能になります。

ポリシーを適用する Exchange 以外の場所を 2 つ以上選択した場合、

- Microsoft 365 の場所でコンテンツへのアクセスを制限または暗号化する

および

- Exchange 以外の場所のすべてのアクション 

アクションが使用可能になります。

たとえば、Exchange とデバイスを場所として選択した場合、次のアクションを使用できます。

- Microsoft 365 の場所でコンテンツへのアクセスを制限または暗号化する
- Windows デバイス上のアクティビティを監査または制限する

[デバイスとMicrosoft Defender for Cloud Apps] を選択すると、次のアクションを使用できます。

- Microsoft 365 の場所でコンテンツへのアクセスを制限または暗号化する
- Windows デバイス上のアクティビティを監査または制限する
- サード パーティ製アプリを制限する

アクションが有効かどうかは、ポリシーのモードを構成する方法によって異なります。 [最初のテスト] オプションを選択して、ポリシー ヒントを表示する場合と表示しない場合に、ポリシーを **テスト モードで** 実行することもできます。 [すぐに **有効にする** ] オプションを選択してポリシーが作成されてから 1 時間後にポリシーを実行するか、保存して後で [ **オフ** にする] オプションを選択してポリシーに戻ることを選択できます。 


<!-- This section needs to explain that the actions available depend on the locations selected AND that the observed behavior of a policy is produced through an interaction of the configured actions AND the configured status (off, test, apply) of a policy. It will detail the purpose of each of the available actions and the location/desired outcome interaction and provide examples eg. how to use the Restrict Third Party apps in the context of a policy that is applied to endpoints so that users can't use a upload content to a third party site or the interaction of on-premises scanner with restrict access or remove on-premises files.  Also what happens when I select multiple locations? provide abundant examples for most common scenarios-->


### <a name="user-notifications-and-policy-tips"></a>ユーザー通知とポリシーのヒント

<!--This section introduces the business need for user notifications, what they are, their benefit, how to use them, how to customize them, and links out to 

- https://docs.microsoft.com/en-us/microsoft-365/compliance/use-notifications-and-policy-tips?view=o365-worldwide
- https://docs.microsoft.com/en-us/microsoft-365/compliance/dlp-policy-tips-reference?view=o365-worldwide

for where they are used/expected behavior-->

<!--You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.-->

ユーザーがルールの条件と例外を満たすコンテキスト内の機密アイテムに対してアクションを試行した場合は、ユーザー通知の電子メールやコンテキスト ポリシーヒントポップアップを使用して、そのことを知らせることができます。 これらの通知は、認識を高め、組織の DLP ポリシーについてユーザーを教育するのに役立つため便利です。

たとえば、個人を特定できる情報 (PII) を含み、ゲストと共有される、OneDrive for Business サイト上の Excel ブックなどのコンテンツです。

![メッセージ バーに Excel 2016 のポリシー ヒントが表示される](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)

> [!IMPORTANT]
> - 通知メールは保護されていない状態で送信されます。
> - Email通知は、Microsoft 365 サービスでのみサポートされます。

#### <a name="email-notifications-support-by-selected-location"></a>選択した場所によるEmail通知のサポート

|選択した場所  |サポートされているEmail通知  |
|---------|---------|
|デバイス     |- サポートされていません         |
|Exchange + デバイス     |- Exchange でサポートされています </br>- デバイスではサポートされていません  |
|Exchange    |- サポートされている        |
|SharePoint + デバイス  |- SharePoint でサポートされている </br>- デバイスではサポートされていません         |
|SharePoint    |- サポートされている |
|Exchange + SharePoint    |- Exchange でサポートされています </br>- SharePoint でサポートされている  |
|デバイス + SharePoint + Exchange    |- デバイスではサポートされていません </br>- SharePoint でサポートされている </br> Exchange でサポートされています |
|Teams    |- サポートされていません |
|OneDrive for Business   |- サポートされている         |
|OneDrive for Business + デバイス     |- OneDrive for Businessでサポートされています </br>- デバイスではサポートされていません         |
|Power-BI|- サポートされていません|
|Microsoft Defender for Cloud Apps|- サポートされていません|
|オンプレミスのリポジトリ|- サポートされていません|

また、有効なビジネス ニーズがある場合やポリシーで誤検知が検出された場合にブロックされないように、 [ポリシーをオーバーライド](#user-overrides)するオプションをユーザーに付与することもできます。

ユーザー通知とポリシー ヒントの構成オプションは、選択した監視場所によって異なります。 選択した場合:

- Exchange
- SharePoint
- OneDrive
- Teams チャットとチャネル
- Defender for Cloud Apps





さまざまな Microsoft アプリのユーザー通知を有効または無効にすることができます。[データ損失防止ポリシーのヒントリファレンスを参照](dlp-policy-tips-reference.md#data-loss-prevention-policy-tips-reference)してください

- ポリシー ヒントを使用して、通知を有効または無効にすることができます。
    - コンテンツまたはコンテンツを送信、共有、または最後に変更したユーザーへの電子メール通知
    - 特定のユーザーに通知する

電子メール テキスト、件名、ポリシー ヒント テキストをカスタマイズします。

![Exchange、SharePoint、OneDrive、Teams チャットとチャネル、Defender for Cloud Apps で使用できるユーザー通知とポリシー ヒントの構成オプション](../media/dlp-user-notification-non-devices.png)

[デバイス] のみを選択した場合は、Exchange、SharePoint、OneDrive、Teams チャット、チャネル、Defender for Cloud Apps で使用できるオプションと、Windows 10 デバイスに表示される通知タイトルとコンテンツをカスタマイズするオプションがすべて表示されます。

![デバイスで使用できるユーザー通知とポリシー ヒントの構成オプション](../media/dlp-user-notification-devices.png)  

これらのパラメーターを使用して、テキストのタイトルと本文をカスタマイズできます。 本文テキストでは、次のものがサポートされています。

|共通名  |パラメーター  |例
|---------|---------|---------|
|ファイル名     |%%FileName%% | Contoso doc 1 |
|プロセス名     |%%ProcessName%% | Word |
|ポリシー名     |%%PolicyName%%| Contoso の機密性が高い |
|action | %%AppliedActions%% | クリップボードから別のアプリにドキュメント コンテンツを貼り付ける |

**%%AppliedActions%% は、** これらの値をメッセージ本文に置き換えます。


|action common name |%%AppliedActions%% パラメーターに置き換えられる値 |
|---------|---------|
|リムーバブル ストレージにコピーする    |*リムーバブル ストレージへの書き込み*         |
|ネットワーク共有にコピーする     |*ネットワーク共有への書き込み*         |
|印刷     |*印刷*         |
|クリップボードから貼り付ける  |*クリップボードからの貼り付け*         |
|bluetooth 経由でコピーする   |*Bluetooth 経由での転送*         |
|未承認のアプリで開く     |*このアプリで開く*         |
|リモート デスクトップ (RDP) にコピーする     |*リモート デスクトップに転送する*         |
|未承認の Web サイトへのアップロード     |*このサイトへのアップロード*         |
|未承認のブラウザーを使用してアイテムにアクセスする     |*このブラウザーで開く*         |

このカスタマイズされたテキストを使用する

*%%AppliedActions%% ファイル名 %%FileName%via %%ProcessName%% は、組織では許可されません。ポリシー %%PolicyName%% をバイパスする場合は、[許可] をクリックします* 

は、カスタマイズされた通知で次のテキストを生成します。

*クリップボードのファイル名からの貼り付け: WINWORD.EXE経由の Contoso doc 1 は、組織では許可されません。ポリシー Contoso の機密性の高いポリシーをバイパスする場合は、[許可] ボタンをクリックします*
 

> [!NOTE]
> ユーザー通知とポリシーヒントは、オンプレミスの場所では使用できません

> [!NOTE]
> 最も優先度が高く、制限が厳しいルールのポリシー ヒントのみが表示されます。 たとえば、単に通知を送信するルールのポリシー ヒントよりも、コンテンツへのアクセスを禁止するルールのポリシー ヒントの方が優先して表示されます。 これにより、ポリシー ヒントがカスケード表示されるのを防止します。

通知とヒント テキストをカスタマイズする方法など、ユーザー通知とポリシー ヒントの構成と使用方法の詳細については、「」を参照してください。 
- [電子メール通知を送信し、DLP ポリシーのポリシーヒントを表示します](use-notifications-and-policy-tips.md#send-email-notifications-and-show-policy-tips-for-dlp-policies)。
  
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

#### <a name="blocking-and-notifications-in-sharepoint-online-and-onedrive-for-business"></a>SharePoint Online とOneDrive for Businessでのブロックと通知

次の表に、SharePoint Online と OneDrive for Business にスコープ設定されたポリシーの DLP ブロックと通知の動作を示します。

|条件  |アクションの構成 |ユーザー通知の構成|インシデント レポートの構成 |ブロックと通知の動作|
|---------|---------|---------|---------|---------|
|- **コンテンツは Microsoft 365 から共有されます** </br>- **組織外のユーザーと**     |アクションが構成されていない         |- **ユーザー通知** が **[オン]** に設定されている </br>- **ポリシー ヒントが選択Office 365サービスのユーザーに通知** する </br>- **コンテンツを送信、共有、または最後に変更したユーザーに通知する**         |- **ルール一致が発生したときに管理者にアラートを送信** する </br>- **アクティビティがルールセットに一致するたびにアラートを送信****する** </br>- **電子メール インシデント レポートを使用して、ポリシー一致が発生したときに [****オン]** に設定されたときに通知する         |- 通知は、ファイルが外部ユーザーと共有され、外部ユーザーがファイルにアクセスした場合にのみ送信されます。  |
|- **コンテンツは Microsoft 365 から共有されます** </br>- **組織内のユーザーとのみ**        | アクションが構成されていない         |-  **ユーザー通知** が **[オン]** に設定されている   </br>- **ポリシー ヒントが選択Office 365サービスのユーザーに通知** する  </br>- **コンテンツを送信、共有、または最後に変更したユーザーに通知する**    |  - **ルール一致が発生したときに管理者にアラートを送信** する </br>- **アクティビティがルールと一致するたびにアラートを送信する** </br>- **電子メール インシデント レポートを使用して、ポリシー一致が発生したときに [****オン]** に設定されたときに通知する       |- ファイルのアップロード時に通知が送信される |
|- **コンテンツは Microsoft 365 から共有されます** </br>- **組織外のユーザーと**    | - **Microsoft 365 の場所でコンテンツへのアクセスを制限または暗号化** するが選択されている </br>- **ユーザーが電子メールを受信したり、共有 SharePoint、OneDrive、Teams ファイルにアクセスしたりできないようにする** </br>- **[組織外のユーザーのみをブロックする** ] が選択されている          |- **ユーザー通知** が **[オン]** に設定されている </br>- **ポリシー ヒントが選択Office 365サービスのユーザーに通知** する </br>- **コンテンツを送信、共有、または最後に変更したユーザーに通知する**  |  - **ルール一致が発生したときに管理者にアラートを送信** する </br>- **アクティビティがルールと一致するたびにアラートを送信する** </br>- **電子メール インシデント レポートを使用して、ポリシー一致が発生したときに [****オン]** に設定されたときに通知する             | - 機密ファイルへのアクセスは、アップロードされるとすぐにブロックされます </br>- コンテンツが Microsoft 365 から組織外のユーザーと共有されたときに送信される通知         |
|- **コンテンツは Microsoft 365 から共有されます** </br>- **組織外のユーザーと** |  - **Microsoft 365 の場所でコンテンツへのアクセスを制限または暗号化** するが選択されている </br>- **ユーザーが電子メールを受信したり、共有 SharePoint、OneDrive、Teams ファイルにアクセスしたりできないようにする** </br>- **[すべてのユーザーをブロック]** が選択されている        | - **ユーザー通知** が **[オン]** に設定されている </br>- **ポリシー ヒントが選択Office 365サービスのユーザーに通知** する </br>- **コンテンツを送信、共有、または最後に変更したユーザーに通知する**         | - **ルール一致が発生したときに管理者にアラートを送信** する </br>- **アクティビティがルールと一致するたびにアラートを送信する** </br>- **電子メール インシデント レポートを使用して、ポリシー一致が発生したときに [****オン]** に設定されたときに通知する        |通知は、ファイルが外部ユーザーと共有され、外部ユーザーがそのファイルにアクセスするときに送信されます。         |
|- **コンテンツは Microsoft 365 から共有されます** </br>- **組織外のユーザーと**     |- **Microsoft 365 の場所でコンテンツへのアクセスを制限または暗号化** するが選択されている </br>- **[リンクを持つすべてのユーザー] オプションを使用してコンテンツへのアクセス権を付与されたユーザーのみをブロック** します。         |  - **ユーザー通知** が **[オン]** に設定されている </br>- **ポリシー ヒントが選択Office 365サービスのユーザーに通知** します。  </br>- **コンテンツを送信、共有、または最後に変更したユーザーに通知する**     |- **ルール一致が発生したときに管理者にアラートを送信** する   </br>- **アクティビティがルールと一致するたびにアラートを送信する** </br>- **電子メール インシデント レポートを使用して、ポリシー一致が発生したときに [****オン]** に設定されたときに通知する       |ファイルがアップロードされるとすぐに通知が送信されます         |


### <a name="user-overrides"></a>ユーザー上書き

**ユーザーオーバーライド** の目的は、Exchange、SharePoint、OneDrive、Teams の機密アイテムに対するアクションを正当な理由でバイパスする方法をユーザーに提供することで、作業を継続できるようにすることです。 ユーザーのオーバーライドは、**ポリシー ヒントを使用してOffice 365 サービスのユーザーに通知** が有効になっている場合にのみ有効になるため、ユーザーのオーバーライドは通知とポリシーのヒントと連携します。 

![DLP ポリシーのユーザー オーバーライド オプション](../media/dlp-user-overrides.png)

> [!NOTE]
> ユーザーオーバーライドは、オンプレミスリポジトリの場所では使用できません。

通常、ユーザーのオーバーライドは、組織が最初にポリシーをロールアウトするときに役立ちます。 オーバーライドの理由から得られるフィードバックと誤検知の特定は、ポリシーのチューニングに役立ちます。 

<!-- This section covers what they are and how to best use them in conjunction with Test/Turn it on right away and link out to where to find the business justification for the override (DLP reports?  https://docs.microsoft.com/en-us/microsoft-365/compliance/view-the-dlp-reports?view=o365-worldwide)  https://docs.microsoft.com/en-us/microsoft-365/compliance/view-the-dlp-reports?view=o365-worldwide#view-the-justification-submitted-by-a-user-for-an-override-->

- 	最も制限の厳しいルールでユーザーにルールを上書きすることを許可している場合は、このルールを上書きすることで、コンテンツに一致した他のルールもすべて上書きされます。
 
<!--![User notifications and user overrides sections of DLP rule editor](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)-->
 
ユーザーのオーバーライドの詳細については、次を参照してください。

- [オーバーライドのためにユーザーによって送信された理由を表示する](view-the-dlp-reports.md#view-the-justification-submitted-by-a-user-for-an-override)

### <a name="incident-reports"></a>インシデント レポート

<!--DLP interacts with other M365 information protection services, like IR. Link this to a process outline for triaging/managing/resolving DLP incidents


https://docs.microsoft.com/en-us/microsoft-365/compliance/view-the-dlp-reports?view=o365-worldwide
https://docs.microsoft.com/en-us/microsoft-365/compliance/dlp-configure-view-alerts-policies?view=o365-worldwide-->

ルールが一致する場合は、イベントの詳細を含むインシデント レポートをコンプライアンス担当者 (または選択したユーザー) に送信できます。 レポートには、一致したアイテム、ルールに一致した実際のコンテンツ、コンテンツを最後に変更したユーザーの名前に関する情報が含まれます。 メール メッセージの場合、レポートには添付ファイルとして、DLP ポリシーに適合する元のメッセージも含まれます。

DLP は、 [インサイダー リスク管理](insider-risk-management.md)などの他の Microsoft Purview 情報保護サービスにインシデント情報をフィードします。 インサイダー リスク管理にインシデント情報を取得するには、 **インシデント レポート** の重大度レベルを **[高**] に設定する必要があります。

<!--![Page for configuring incident reports](../media/31c6da0e-981c-415e-91bf-d94ca391a893.png)-->

アクティビティがルールに一致するたびにアラートを送信できます。これはノイズが大きい場合や、一定の期間にわたる一致数または項目の量に基づいてアラートを集計する数を減らすことができます。

![ルールが一致するか、時間の経過と共に集計されるたびにアラートを送信し、レポート数を減らす](../media/dlp-incident-reports-aggregation.png)

DLP は、SharePoint Online やOneDrive for Businessアイテムとは異なる方法で電子メールをスキャンします。 SharePoint Online や OneDrive for Business では、DLP は新しいアイテムだけでなく既存のアイテムもスキャンして、一致が検出される場合は常にインシデント レポートを生成します。 Exchange Online では、DLP は新しいメール メッセージのみをスキャンして、ポリシーとの一致が検出されるとレポートを生成します。 DLP は、メールボックスやアーカイブに保存されている既存のメール アイテムについては、スキャンや一致検出を ***実行しません***。

### <a name="additional-options"></a>追加オプション

ポリシーに複数のルールがある場合は、[ **追加] オプション** を使用して、編集中のルールに一致するルールがある場合のルール処理をさらに制御したり、ルールの評価の優先度を設定したりできます。

## <a name="see-also"></a>関連項目

- [データ損失防止について](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [データ損失防止ポリシー (DLP) のサポート](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [テンプレートから DLP ポリシーを作成する](create-a-dlp-policy-from-a-template.md#create-a-dlp-policy-from-a-template)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy)
