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
ms.openlocfilehash: 4888569318fd24d25368dc1c923a1efced9f4126
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2022
ms.locfileid: "63675440"
---
# <a name="data-loss-prevention-policy-reference"></a>データ損失防止ポリシーリファレンス

データ損失防止 (DLP) ポリシーには、構成する多くのコンポーネントがあります。 効果的なポリシーを作成するには、各コンポーネントの目的と、その構成によってポリシーの動作がどのように変化するのかを理解する必要があります。 この記事では、DLP ポリシーの詳細な構造について説明します。

## <a name="policy-templates"></a>ポリシー テンプレート 

DLP ポリシー テンプレートは、次の 4 つのカテゴリに事前に並べ替えされています。

- 財務情報の種類を検出して **保護できる** 情報。
- 医療と健康に関する情報の種類を検出 **して保護できる** 情報。
- プライバシー情報の種類を検出して **保護できる** 情報。
- 他 **の** 1 つが組織のニーズを満たしない場合に独自のポリシーを作成するために使用できるカスタム テンプレート。

次の表に、すべてのポリシー テンプレートと機密情報の種類 (SIT) を示します。 

更新日: 2021/06/23

|カテゴリ| テンプレート | SIT |
|---------|---------|---------|
|財務的| オーストラリアの金融データ| - [SWIFT コード](sensitive-information-type-entity-definitions.md#swift-code) </br> - [オーストラリアの税ファイル番号](sensitive-information-type-entity-definitions.md#australia-tax-file-number) </br> - [オーストラリアの銀行口座番号](sensitive-information-type-entity-definitions.md#australia-bank-account-number) </br> - [クレジット カード番号](sensitive-information-type-entity-definitions.md#credit-card-number)|
|財務的| カナダ 財務データ |- [クレジット カード番号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [カナダの銀行口座番号](sensitive-information-type-entity-definitions.md#canada-bank-account-number)|
|財務的| フランス 財務データ |- [クレジット カード番号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [EU のデビットカード番号](sensitive-information-type-entity-definitions.md#eu-debit-card-number)|
|財務的| ドイツの金融データ |- [クレジット カード番号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [EU のデビットカード番号](sensitive-information-type-entity-definitions.md#eu-debit-card-number)|
|財務的| イスラエルの金融データ |- [イスラエルの銀行口座番号](sensitive-information-type-entity-definitions.md#israel-bank-account-number) </br> - [SWIFT コード](sensitive-information-type-entity-definitions.md#swift-code) </br> - [クレジット カード番号](sensitive-information-type-entity-definitions.md#credit-card-number)|
|財務的| 日本の金融データ |- [日本の銀行口座番号](sensitive-information-type-entity-definitions.md#japan-bank-account-number) </br> - [クレジット カード番号](sensitive-information-type-entity-definitions.md#credit-card-number)|
|財務的| PCI データ セキュリティ基準 (PCI DSS)|- [クレジット カード番号](sensitive-information-type-entity-definitions.md#credit-card-number)|
|財務的| サウジアラビアのサイバー犯罪防止法|- [SWIFT コード](sensitive-information-type-entity-definitions.md#swift-code) </br> - [国際銀行口座番号 (IBAN)](sensitive-information-type-entity-definitions.md#international-banking-account-number-iban) |
|財務的| サウジアラビアの金融データ |- [クレジット カード番号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [SWIFT コード](sensitive-information-type-entity-definitions.md#swift-code) </br> - [国際銀行口座番号 (IBAN)](sensitive-information-type-entity-definitions.md#international-banking-account-number-iban)|
|財務的| 英国の財務データ|- [クレジット カード番号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [EU のデビットカード番号](sensitive-information-type-entity-definitions.md#eu-debit-card-number) </br> - [SWIFT コード](sensitive-information-type-entity-definitions.md#swift-code)|
|財務的| 米国の財務データ|- [クレジット カード番号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [米国の銀行口座番号](sensitive-information-type-entity-definitions.md#us-bank-account-number)</br> - [ABA ルーティング番号](sensitive-information-type-entity-definitions.md#aba-routing-number)|
|財務的| 米国連邦取引委員会 (FTC) の消費者保護規則|- [クレジット カード番号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [米国の銀行口座番号](sensitive-information-type-entity-definitions.md#us-bank-account-number)</br> - [ABA ルーティング番号](sensitive-information-type-entity-definitions.md#aba-routing-number)|
|財務的| 米国の Gramm-Leach-Bliley 法 (GLBA) 拡張|- [クレジット カード番号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [米国の銀行口座番号](sensitive-information-type-entity-definitions.md#us-bank-account-number)</br> - [米国の個人納税者識別番号 (ITIN)](sensitive-information-type-entity-definitions.md#us-individual-taxpayer-identification-number-itin)  </br> - [米国の社会保障番号 (SSN)](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn)</br> - [米国/英国のパスポート番号](sensitive-information-type-entity-definitions.md#usuk-passport-number) </br> -[米国の運転免許証番号](sensitive-information-type-entity-definitions.md#us-drivers-license-number)</br> - [すべての完全な名前](sensitive-information-type-entity-definitions.md#all-full-names)</br> - [米国の物理アドレス](sensitive-information-type-entity-definitions.md#us-physical-addresses)|
|財務的| 米国のグラム リーチ ブライリー法 (GLBA)|- [クレジット カード番号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [米国の銀行口座番号](sensitive-information-type-entity-definitions.md#us-bank-account-number)</br> - [米国の個人納税者識別番号 (ITIN)](sensitive-information-type-entity-definitions.md#us-individual-taxpayer-identification-number-itin)  </br> - [米国の社会保障番号 (SSN)](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn)|
|医療と健康| オーストラリアの健康記録法 (HRIP 法) 拡張 |- [オーストラリアの税ファイル番号](sensitive-information-type-entity-definitions.md#australia-tax-file-number) </br> - [オーストラリアの医療アカウント番号](sensitive-information-type-entity-definitions.md#australia-medical-account-number) </br> - [すべての完全な名前](sensitive-information-type-entity-definitions.md#all-full-names) </br> - [すべての医療契約条件](sensitive-information-type-entity-definitions.md#all-medical-terms-and-conditions) </br> - [オーストラリアの物理アドレス](sensitive-information-type-entity-definitions.md#australia-physical-addresses)|
|医療と健康| オーストラリアの保健記録法 (HRIP 法)|- [オーストラリアの税ファイル番号](sensitive-information-type-entity-definitions.md#australia-tax-file-number) </br> - [オーストラリアの医療アカウント番号](sensitive-information-type-entity-definitions.md#australia-medical-account-number)|
|医療と健康| カナダの健康情報法 (HIA) |- [カナダのパスポート番号](sensitive-information-type-entity-definitions.md#canada-passport-number)</br> - [カナダの社会保険番号](sensitive-information-type-entity-definitions.md#canada-social-insurance-number) </br> - [カナダの正常性サービス番号](sensitive-information-type-entity-definitions.md#canada-health-service-number) </br> - [カナダの個人の健康識別番号](sensitive-information-type-entity-definitions.md#canada-personal-health-identification-number-phin)|
|医療と健康| カナダの個人情報法 (PHIA) マニトバ州|- [カナダの社会保険番号](sensitive-information-type-entity-definitions.md#canada-social-insurance-number) </br> - [カナダの正常性サービス番号](sensitive-information-type-entity-definitions.md#canada-health-service-number) </br> - [カナダの個人の健康識別番号](sensitive-information-type-entity-definitions.md#canada-personal-health-identification-number-phin)|
|医療と健康| カナダ個人健康法 (PHIPA) オンタリオ州 |- [カナダのパスポート番号](sensitive-information-type-entity-definitions.md#canada-passport-number)</br> - [カナダの社会保険番号](sensitive-information-type-entity-definitions.md#canada-social-insurance-number) </br> - [カナダの正常性サービス番号](sensitive-information-type-entity-definitions.md#canada-health-service-number) </br> - [カナダの個人の健康識別番号](sensitive-information-type-entity-definitions.md#canada-personal-health-identification-number-phin)|
|医療と健康| 英国の医療報告書の利用に関する法律|- [英国の国民保健サービス番号](sensitive-information-type-entity-definitions.md#uk-national-health-service-number) </br> - [英国の国民保険番号 (NINO)](sensitive-information-type-entity-definitions.md#uk-national-insurance-number-nino)|
|医療と健康| 米国健康保険法 (HIPAA) 拡張|</br> - [病気の国際分類 (ICD-9-CM)](sensitive-information-type-entity-definitions.md#international-classification-of-diseases-icd-9-cm) </br> - [病気の国際分類 (ICD-10-CM)](sensitive-information-type-entity-definitions.md#international-classification-of-diseases-icd-10-cm) </br> - [すべての完全な名前](sensitive-information-type-entity-definitions.md#all-full-names) </br> - [すべての医療契約条件](sensitive-information-type-entity-definitions.md#all-medical-terms-and-conditions) </br> - [米国の物理アドレス](sensitive-information-type-entity-definitions.md#us-physical-addresses)|
|医療と健康| 米国の医療保険法 (HIPAA)| - [病気の国際分類 (ICD-9-CM)](sensitive-information-type-entity-definitions.md#international-classification-of-diseases-icd-9-cm) </br> - [病気の国際分類 (ICD-10-CM)](sensitive-information-type-entity-definitions.md#international-classification-of-diseases-icd-10-cm)|
|プライバシー| オーストラリアのプライバシー法の強化|- [オーストラリアの運転免許証番号](sensitive-information-type-entity-definitions.md#australia-drivers-license-number) </br> - [オーストラリアのパスポート番号](sensitive-information-type-entity-definitions.md#australia-passport-number) </br> - [すべての完全な名前](sensitive-information-type-entity-definitions.md#all-full-names) </br> - [すべての医療契約条件](sensitive-information-type-entity-definitions.md#all-medical-terms-and-conditions) </br> - [オーストラリアの物理アドレス](sensitive-information-type-entity-definitions.md#australia-physical-addresses)|
|プライバシー| オーストラリアのプライバシー保護法|- [オーストラリアの運転免許証番号](sensitive-information-type-entity-definitions.md#australia-drivers-license-number) </br> - [オーストラリアのパスポート番号](sensitive-information-type-entity-definitions.md#australia-passport-number)|
|プライバシー| オーストラリアの個人情報 (PII) データ|- [オーストラリアの税ファイル番号](sensitive-information-type-entity-definitions.md#australia-tax-file-number) </br> - [オーストラリアの運転免許証番号](sensitive-information-type-entity-definitions.md#australia-drivers-license-number)|
|プライバシー| カナダの個人情報 (PII) データ|- [カナダの運転免許証番号](sensitive-information-type-entity-definitions.md#canada-drivers-license-number)</br> - [カナダの銀行口座番号](sensitive-information-type-entity-definitions.md#canada-bank-account-number) </br> - [カナダのパスポート番号](sensitive-information-type-entity-definitions.md#canada-passport-number)</br> - [カナダの社会保険番号](sensitive-information-type-entity-definitions.md#canada-social-insurance-number) </br> - [カナダの正常性サービス番号](sensitive-information-type-entity-definitions.md#canada-health-service-number) </br> - [カナダの個人の健康識別番号](sensitive-information-type-entity-definitions.md#canada-personal-health-identification-number-phin)|
|プライバシー| カナダの個人情報保護法 (PIPA)|- [カナダのパスポート番号](sensitive-information-type-entity-definitions.md#canada-passport-number)</br> - [カナダの社会保険番号](sensitive-information-type-entity-definitions.md#canada-social-insurance-number) </br> - [カナダの正常性サービス番号](sensitive-information-type-entity-definitions.md#canada-health-service-number) </br> - [カナダの個人の健康識別番号](sensitive-information-type-entity-definitions.md#canada-personal-health-identification-number-phin)|
|プライバシー| カナダの個人情報保護法 (PIPEDA)|- [カナダの運転免許証番号](sensitive-information-type-entity-definitions.md#canada-drivers-license-number) </br> - [カナダの銀行口座番号](sensitive-information-type-entity-definitions.md#canada-bank-account-number) </br> - [カナダのパスポート番号](sensitive-information-type-entity-definitions.md#canada-passport-number)</br> - [カナダの社会保険番号](sensitive-information-type-entity-definitions.md#canada-social-insurance-number) </br> - [カナダの正常性サービス番号](sensitive-information-type-entity-definitions.md#canada-health-service-number) </br> - [カナダの個人の健康識別番号](sensitive-information-type-entity-definitions.md#canada-personal-health-identification-number-phin)|
|プライバシー| フランスのデータ保護法|- [フランスの国民 ID カード (CNI)](sensitive-information-type-entity-definitions.md#france-national-id-card-cni) </br> - [フランスの社会保障番号 (INSEE)](sensitive-information-type-entity-definitions.md#france-social-security-number-insee)|
|プライバシー| フランスの個人情報 (PII) データ|- [フランスの社会保障番号 (INSEE)](sensitive-information-type-entity-definitions.md#france-social-security-number-insee) </br> - [フランスの運転免許証番号](sensitive-information-type-entity-definitions.md#france-drivers-license-number) </br> - [フランスのパスポート番号](sensitive-information-type-entity-definitions.md#france-passport-number) </br> - [フランスの国民 ID カード (CNI)](sensitive-information-type-entity-definitions.md#france-national-id-card-cni)|
|プライバシー| 一般データ保護規則 (GDPR) 拡張|- [オーストリアの物理アドレス](sensitive-information-type-entity-definitions.md#austria-physical-addresses) </br> - [ベルギーの物理アドレス](sensitive-information-type-entity-definitions.md#belgium-physical-addresses)</br> - [ブルガリアの物理アドレス](sensitive-information-type-entity-definitions.md#bulgaria-physical-addresses)</br> - [クロアチアの物理アドレス](sensitive-information-type-entity-definitions.md#croatia-physical-addresses)</br> - [キプロスの物理アドレス](sensitive-information-type-entity-definitions.md#cyprus-physical-addresses)</br> - [チェコ共和国の物理アドレス](sensitive-information-type-entity-definitions.md#czech-republic-physical-addresses)</br> - [デンマークの物理アドレス](sensitive-information-type-entity-definitions.md#denmark-physical-addresses)</br> - [エストニアの物理アドレス](sensitive-information-type-entity-definitions.md#estonia-physical-addresses)</br> - [フィンランドの物理アドレス](sensitive-information-type-entity-definitions.md#finland-physical-addresses)</br> - [フランスの物理アドレス](sensitive-information-type-entity-definitions.md#france-physical-addresses)</br> - [ドイツの物理アドレス](sensitive-information-type-entity-definitions.md#germany-physical-addresses)</br> - [ギリシャの物理アドレス](sensitive-information-type-entity-definitions.md#greece-physical-addresses)</br> - [ハンガリーの物理アドレス](sensitive-information-type-entity-definitions.md#hungary-physical-addresses)</br> - [アイルランドの物理アドレス](sensitive-information-type-entity-definitions.md#ireland-physical-addresses)</br> - [イタリアの物理アドレス](sensitive-information-type-entity-definitions.md#italy-physical-addresses)</br> - [ラトビアの物理アドレス](sensitive-information-type-entity-definitions.md#latvia-physical-addresses)</br> - [リトアニアの物理アドレス](sensitive-information-type-entity-definitions.md#lithuania-physical-addresses)</br> - [ルクセンブルクの物理アドレス](sensitive-information-type-entity-definitions.md#luxemburg-physical-addresses)</br> - [マルタの物理アドレス](sensitive-information-type-entity-definitions.md#malta-physical-addresses)</br> - [オランダの物理アドレス](sensitive-information-type-entity-definitions.md#netherlands-physical-addresses)</br> - [ポーランドの物理アドレス](sensitive-information-type-entity-definitions.md#poland-physical-addresses)</br> - [ポルトガル語の物理アドレス](sensitive-information-type-entity-definitions.md#portugal-physical-addresses)</br> - [ルーマニアの物理アドレス](sensitive-information-type-entity-definitions.md#romania-physical-addresses)</br> - [スロバキアの物理アドレス](sensitive-information-type-entity-definitions.md#slovakia-physical-addresses)</br> - [スロベニアの物理アドレス](sensitive-information-type-entity-definitions.md#slovenia-physical-addresses)</br> - [スペインの物理アドレス](sensitive-information-type-entity-definitions.md#spain-physical-addresses)</br> - [スウェーデンの物理アドレス](sensitive-information-type-entity-definitions.md#sweden-physical-addresses)</br> - [オーストリアの社会保障番号](sensitive-information-type-entity-definitions.md#austria-social-security-number)</br> - [フランスの社会保障番号 (INSEE)](sensitive-information-type-entity-definitions.md#france-social-security-number-insee)</br> - [ギリシャの社会保障番号 (AMKA)](sensitive-information-type-entity-definitions.md#greece-social-security-number-amka)</br> - [ハンガリーの社会保障番号 (TAJ)](sensitive-information-type-entity-definitions.md#hungary-social-security-number-taj)</br> - [スペインの社会保障番号 (SSN)](sensitive-information-type-entity-definitions.md#spain-social-security-number-ssn)</br> - [オーストリアの ID カード](sensitive-information-type-entity-definitions.md#austria-identity-card)</br> - [キプロスの ID カード](sensitive-information-type-entity-definitions.md#cyprus-identity-card)</br> - [ドイツの ID カード番号](sensitive-information-type-entity-definitions.md#germany-identity-card-number)</br> - [マルタの ID カード番号](sensitive-information-type-entity-definitions.md#malta-identity-card-number)</br> - [フランス国民 ID カード (CNI)](sensitive-information-type-entity-definitions.md#france-national-id-card-cni)</br> - [ギリシャの国民 ID カード](sensitive-information-type-entity-definitions.md#greece-national-id-card)</br> - [フィンランドの国民 ID](sensitive-information-type-entity-definitions.md#finland-national-id)</br> - [ポーランド国民 ID (PESEL)](sensitive-information-type-entity-definitions.md#poland-national-id-pesel)</br> - [スウェーデンの国民 ID](sensitive-information-type-entity-definitions.md#sweden-national-id)</br> - [クロアチアの個人識別 (OIB) 番号](sensitive-information-type-entity-definitions.md#croatia-personal-identification-oib-number)</br> - [チェコの個人 ID 番号](sensitive-information-type-entity-definitions.md#czech-personal-identity-number)</br> - [デンマークの個人識別番号](sensitive-information-type-entity-definitions.md#denmark-personal-identification-number)</br> - [エストニアの個人識別コード](sensitive-information-type-entity-definitions.md#estonia-personal-identification-code)</br> - [ハンガリーの個人識別番号](sensitive-information-type-entity-definitions.md#hungary-personal-identification-number)</br> - [ルクセンブルク国民識別番号 (自然人)](sensitive-information-type-entity-definitions.md#luxemburg-national-identification-number-natural-persons)</br> - [ルクセンブルク国民識別番号 (非自然人)](sensitive-information-type-entity-definitions.md#luxemburg-national-identification-number-non-natural-persons)</br> - [イタリアの会計コード](sensitive-information-type-entity-definitions.md#italy-fiscal-code)</br> - [ラトビアの個人コード](sensitive-information-type-entity-definitions.md#latvia-personal-code)</br> - [リトアニア の個人用コード](sensitive-information-type-entity-definitions.md#lithuania-personal-code)</br> - [ルーマニア の個人数値コード (CNP)](sensitive-information-type-entity-definitions.md#romania-personal-numeric-code-cnp)</br> - [オランダ市民サービス (BSN) 番号](sensitive-information-type-entity-definitions.md#netherlands-citizens-service-bsn-number)</br> - [アイルランドの個人公開サービス (PPS) 番号](sensitive-information-type-entity-definitions.md#ireland-personal-public-service-pps-number)</br> - [ブルガリアの統一市民番号](sensitive-information-type-entity-definitions.md#bulgaria-uniform-civil-number)</br> - [ベルギーの国番号](sensitive-information-type-entity-definitions.md#belgium-national-number)</br> - [スペイン DNI](sensitive-information-type-entity-definitions.md#spain-dni)</br> - [スロベニアの一意のマスター市民番号](sensitive-information-type-entity-definitions.md#slovenia-unique-master-citizen-number)</br> - [スロバキアの個人番号](sensitive-information-type-entity-definitions.md#slovakia-personal-number)</br> - [ポルトガルの市民カード番号](sensitive-information-type-entity-definitions.md#portugal-citizen-card-number)</br> - [マルタ税 ID 番号](sensitive-information-type-entity-definitions.md#malta-tax-identification-number)</br> - [オーストリアの納税者番号](sensitive-information-type-entity-definitions.md#austria-tax-identification-number)</br> - [キプロスの納税者番号](sensitive-information-type-entity-definitions.md#cyprus-tax-identification-number)</br> - [フランスの納税者番号 (numéro SPI.)](sensitive-information-type-entity-definitions.md#france-tax-identification-number)</br> - [ドイツの納税者番号](sensitive-information-type-entity-definitions.md#germany-tax-identification-number)</br> - [ギリシャ語の税の識別番号](sensitive-information-type-entity-definitions.md#greece-tax-identification-number)</br> - [ハンガリー 税の識別番号](sensitive-information-type-entity-definitions.md#hungary-tax-identification-number)</br> - [オランダの納税者番号](sensitive-information-type-entity-definitions.md#netherlands-tax-identification-number)</br> - [ポーランドの納税者番号](sensitive-information-type-entity-definitions.md#poland-tax-identification-number)</br> - [ポルトガルの納税者番号](sensitive-information-type-entity-definitions.md#portugal-tax-identification-number)</br> - [スロベニアの納税者番号](sensitive-information-type-entity-definitions.md#slovenia-tax-identification-number)</br> - [スペインの納税者番号](sensitive-information-type-entity-definitions.md#spain-tax-identification-number)</br> - [スウェーデンの納税者番号](sensitive-information-type-entity-definitions.md#sweden-tax-identification-number)</br> - [オーストリアの運転免許証](sensitive-information-type-entity-definitions.md#austria-drivers-license-number)</br> - [ベルギーの運転免許証番号](sensitive-information-type-entity-definitions.md#belgium-drivers-license-number)</br> - [ブルガリアの運転免許証番号](sensitive-information-type-entity-definitions.md#bulgaria-drivers-license-number)</br> - [クロアチア の運転免許証番号](sensitive-information-type-entity-definitions.md#croatia-drivers-license-number)</br> - [キプロス の運転免許証番号](sensitive-information-type-entity-definitions.md#cyprus-drivers-license-number)</br> - [チェコの運転免許証番号](sensitive-information-type-entity-definitions.md#czech-drivers-license-number)</br> - [デンマークの運転免許証番号](sensitive-information-type-entity-definitions.md#denmark-drivers-license-number)</br> - [エストニア の運転免許証番号](sensitive-information-type-entity-definitions.md#estonia-drivers-license-number)</br> - [フィンランド の運転免許証番号](sensitive-information-type-entity-definitions.md#finland-drivers-license-number)</br> - [フランス の運転免許証番号](sensitive-information-type-entity-definitions.md#france-drivers-license-number)</br> - [ドイツの運転免許証番号](sensitive-information-type-entity-definitions.md#germany-drivers-license-number)</br> - [ギリシャの運転免許証番号](sensitive-information-type-entity-definitions.md#greece-drivers-license-number)</br> - [ハンガリー の運転免許証番号](sensitive-information-type-entity-definitions.md#hungary-drivers-license-number)</br> - [アイルランドの運転免許証番号](sensitive-information-type-entity-definitions.md#ireland-drivers-license-number)</br> - [イタリアの運転免許証番号](sensitive-information-type-entity-definitions.md#italy-drivers-license-number)</br> - [ラトビア の運転免許証番号](sensitive-information-type-entity-definitions.md#latvia-drivers-license-number)</br> - [リトアニア の運転免許証番号](sensitive-information-type-entity-definitions.md#lithuania-drivers-license-number)</br> - [ルクセンブルク 運転免許証番号](sensitive-information-type-entity-definitions.md#luxemburg-drivers-license-number)</br> - [マルタの運転免許証番号](sensitive-information-type-entity-definitions.md#malta-drivers-license-number)</br> - [オランダの運転免許証番号](sensitive-information-type-entity-definitions.md#netherlands-drivers-license-number)</br> - [ポーランド の運転免許証番号](sensitive-information-type-entity-definitions.md#poland-drivers-license-number)</br> - [ポルトガルの運転免許証番号](sensitive-information-type-entity-definitions.md#portugal-drivers-license-number)</br> - [ルーマニアの運転免許証番号](sensitive-information-type-entity-definitions.md#romania-drivers-license-number)</br> - [スロバキアの運転免許証番号](sensitive-information-type-entity-definitions.md#slovakia-drivers-license-number)</br> - [スロベニア の運転免許証番号](sensitive-information-type-entity-definitions.md#slovenia-drivers-license-number)</br> - [スペインの運転免許証番号](sensitive-information-type-entity-definitions.md#spain-drivers-license-number)</br> - [スウェーデンの運転免許証番号](sensitive-information-type-entity-definitions.md#sweden-drivers-license-number)</br> - [オーストリアのパスポート番号](sensitive-information-type-entity-definitions.md#austria-passport-number)</br> - [ベルギーのパスポート番号](sensitive-information-type-entity-definitions.md#belgium-passport-number)</br> - [ブルガリアのパスポート番号](sensitive-information-type-entity-definitions.md#bulgaria-passport-number)</br> - [クロアチアのパスポート番号](sensitive-information-type-entity-definitions.md#croatia-passport-number)</br> - [キプロスのパスポート番号](sensitive-information-type-entity-definitions.md#cyprus-passport-number)</br> - [チェコ共和国のパスポート番号](sensitive-information-type-entity-definitions.md#czech-passport-number)</br> - [デンマークのパスポート番号](sensitive-information-type-entity-definitions.md#denmark-passport-number)</br> - [エストニアのパスポート番号](sensitive-information-type-entity-definitions.md#estonia-passport-number)</br> - [フィンランドのパスポート番号](sensitive-information-type-entity-definitions.md#finland-passport-number)</br> - [フランスのパスポート番号](sensitive-information-type-entity-definitions.md#france-passport-number)</br> - [ドイツのパスポート番号](sensitive-information-type-entity-definitions.md#germany-passport-number)</br> - [ギリシャのパスポート番号](sensitive-information-type-entity-definitions.md#greece-passport-number)</br> - [ハンガリーのパスポート番号](sensitive-information-type-entity-definitions.md#hungary-passport-number)</br> - [アイルランドのパスポート番号](sensitive-information-type-entity-definitions.md#ireland-passport-number)</br> - [イタリアのパスポート番号](sensitive-information-type-entity-definitions.md#italy-passport-number)</br> - [ラトビアのパスポート番号](sensitive-information-type-entity-definitions.md#latvia-passport-number)</br> - [リトアニアのパスポート番号](sensitive-information-type-entity-definitions.md#lithuania-passport-number)</br> - [ルクセンブルク パスポート番号](sensitive-information-type-entity-definitions.md#luxemburg-passport-number)</br> - [マルタのパスポート番号](sensitive-information-type-entity-definitions.md#malta-passport-number)</br> - [オランダのパスポート番号](sensitive-information-type-entity-definitions.md#netherlands-passport-number)</br> - [ポーランドのパスポート](sensitive-information-type-entity-definitions.md#poland-passport-number)</br> - [ポルトガルのパスポート番号](sensitive-information-type-entity-definitions.md#portugal-passport-number)</br> - [ルーマニアのパスポート番号](sensitive-information-type-entity-definitions.md#romania-passport-number)</br> - [スロバキアのパスポート番号](sensitive-information-type-entity-definitions.md#slovakia-passport-number)</br> - [スロベニアのパスポート番号](sensitive-information-type-entity-definitions.md#slovenia-passport-number)</br> - [スペインのパスポート番号](sensitive-information-type-entity-definitions.md#spain-passport-number)</br> - [スウェーデンのパスポート番号](sensitive-information-type-entity-definitions.md#sweden-passport-number)</br> - [EU のデビットカード番号](sensitive-information-type-entity-definitions.md#eu-debit-card-number)</br> - [すべての完全な名前](sensitive-information-type-entity-definitions.md#all-full-names)|
|プライバシー| EU 一般データ保護規則 (GDPR)|- [EU のデビットカード番号](sensitive-information-type-entity-definitions.md#eu-debit-card-number) </br> - [EU の運転免許証番号](sensitive-information-type-entity-definitions.md#eu-drivers-license-number) </br> - [EU の国民識別番号](sensitive-information-type-entity-definitions.md#eu-national-identification-number)</br> - [EU パスポート番号](sensitive-information-type-entity-definitions.md#eu-passport-number) </br> - [EU 社会保障番号または同等の ID](sensitive-information-type-entity-definitions.md#eu-social-security-number-or-equivalent-identification)</br> - [EU 税の識別番号](sensitive-information-type-entity-definitions.md#eu-tax-identification-number)|
|プライバシー| ドイツの個人情報 (PII) データ|- [ドイツの運転免許証番号](sensitive-information-type-entity-definitions.md#germany-drivers-license-number) </br> - [ドイツのパスポート番号](sensitive-information-type-entity-definitions.md#germany-passport-number)| 
|プライバシー| イスラエルの個人情報 (PII) データ|- [イスラエルの国民識別番号](sensitive-information-type-entity-definitions.md#israel-national-identification-number)| 
|プライバシー| イスラエルのプライバシー保護|- [イスラエルの国民識別番号](sensitive-information-type-entity-definitions.md#israel-national-identification-number)</br> - [イスラエルの銀行口座番号](sensitive-information-type-entity-definitions.md#israel-bank-account-number)|
|プライバシー| 日本の個人を特定できる情報 (PII) データの強化|- [日本社会保険番号 (SIN)](sensitive-information-type-entity-definitions.md#japan-social-insurance-number-sin)</br> - [日本のマイナンバー - 個人用](sensitive-information-type-entity-definitions.md#japan-my-number---personal)</br> - [日本のパスポート番号](sensitive-information-type-entity-definitions.md#japan-passport-number)</br> - [日本の運転免許証番号](sensitive-information-type-entity-definitions.md#japan-drivers-license-number)</br> - [すべての完全な名前](sensitive-information-type-entity-definitions.md#all-full-names)</br> - [日本の物理アドレス](sensitive-information-type-entity-definitions.md#all-physical-addresses)|
|プライバシー| 日本の個人情報 (PII) データ|- [日本居住者登録番号](sensitive-information-type-entity-definitions.md#japan-resident-registration-number) </br> - [日本社会保険番号 (SIN)](sensitive-information-type-entity-definitions.md#japan-social-insurance-number-sin)|
|プライバシー| 日本の個人情報保護の強化|- [日本社会保険番号 (SIN)](sensitive-information-type-entity-definitions.md#japan-social-insurance-number-sin) </br> - [日本のマイナンバー - 個人用](sensitive-information-type-entity-definitions.md#japan-my-number---personal)</br> - [日本のパスポート番号](sensitive-information-type-entity-definitions.md#japan-passport-number) </br> - [日本の運転免許証番号](sensitive-information-type-entity-definitions.md#japan-drivers-license-number)</br> - [すべての完全な名前](sensitive-information-type-entity-definitions.md#all-full-names)</br> - [日本の物理アドレス](sensitive-information-type-entity-definitions.md#all-physical-addresses)|
|プライバシー| 日本の個人情報保護|- [日本居住者登録番号](sensitive-information-type-entity-definitions.md#japan-resident-registration-number)</br> - [日本社会保険番号 (SIN)](sensitive-information-type-entity-definitions.md#japan-social-insurance-number-sin)|
|プライバシー| サウジアラビア 個人を特定できる (PII) データ|- [サウジアラビアの国民 ID](sensitive-information-type-entity-definitions.md#saudi-arabia-national-id)|
|プライバシー| 英国のデータ保護法|- [英国の国民保険番号 (NINO)](sensitive-information-type-entity-definitions.md#uk-national-insurance-number-nino) </br> - [米国/英国のパスポート番号](sensitive-information-type-entity-definitions.md#usuk-passport-number) </br> - [SWIFT コード](sensitive-information-type-entity-definitions.md#swift-code)|
|プライバシー| 英国のプライバシーおよび電子通信に関する規制|- [SWIFT コード](sensitive-information-type-entity-definitions.md#swift-code)|
|プライバシー| 英国の個人情報 (PII) データ|- [英国の国民保険番号 (NINO)](sensitive-information-type-entity-definitions.md#uk-national-insurance-number-nino) </br> - [米国/英国のパスポート番号](sensitive-information-type-entity-definitions.md#usuk-passport-number)|
|プライバシー| 英国のオンラインの個人情報に関する実務基準 (PIOCP)|- [英国の国民保険番号 (NINO)](sensitive-information-type-entity-definitions.md#uk-national-insurance-number-nino) </br> - [英国の国民保健サービス番号](sensitive-information-type-entity-definitions.md#uk-national-health-service-number) </br> - [SWIFT コード](sensitive-information-type-entity-definitions.md#swift-code)|
|プライバシー| 米国愛国者法の強化|- [クレジット カード番号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [米国の銀行口座番号](sensitive-information-type-entity-definitions.md#us-bank-account-number)</br> - [米国の個人納税者識別番号 (ITIN)](sensitive-information-type-entity-definitions.md#us-individual-taxpayer-identification-number-itin)  </br> - [米国の社会保障番号 (SSN)](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn)</br> - [すべての完全な名前](sensitive-information-type-entity-definitions.md#all-full-names)</br> - [米国の物理アドレス](sensitive-information-type-entity-definitions.md#us-physical-addresses)|
|プライバシー| 米国の愛国者法|- [クレジット カード番号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [米国の銀行口座番号](sensitive-information-type-entity-definitions.md#us-bank-account-number)</br> - [米国の個人納税者識別番号 (ITIN)](sensitive-information-type-entity-definitions.md#us-individual-taxpayer-identification-number-itin)  </br> - [米国の社会保障番号 (SSN)](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn)|
|プライバシー| 米国の個人を特定できる情報 (PII) データ拡張|- [米国の個人納税者識別番号 (ITIN)](sensitive-information-type-entity-definitions.md#us-individual-taxpayer-identification-number-itin)  </br> - [米国の社会保障番号 (SSN)](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn)</br> - [米国/英国のパスポート番号](sensitive-information-type-entity-definitions.md#usuk-passport-number)</br> - [すべての完全な名前](sensitive-information-type-entity-definitions.md#all-full-names)</br> - [米国の物理アドレス](sensitive-information-type-entity-definitions.md#us-physical-addresses)|
|プライバシー| 米国の個人情報 (PII) データ|- [米国の個人納税者識別番号 (ITIN)](sensitive-information-type-entity-definitions.md#us-individual-taxpayer-identification-number-itin)  </br> - [米国の社会保障番号 (SSN)](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn)</br> - [米国/英国のパスポート番号](sensitive-information-type-entity-definitions.md#usuk-passport-number)|
|プライバシー| 米国の州違反通知法の強化|- [クレジット カード番号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [米国の銀行口座番号](sensitive-information-type-entity-definitions.md#us-bank-account-number)</br> -[米国の運転免許証番号](sensitive-information-type-entity-definitions.md#us-drivers-license-number) </br> - [米国の社会保障番号 (SSN)](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn)</br> - [すべての完全な名前](sensitive-information-type-entity-definitions.md#all-full-names) </br> - [米国/英国のパスポート番号](sensitive-information-type-entity-definitions.md#usuk-passport-number)</br> - [すべての医療契約条件](sensitive-information-type-entity-definitions.md#all-medical-terms-and-conditions)|
|プライバシー| 米国の個人情報漏洩の通知に関する州法|- [クレジット カード番号](sensitive-information-type-entity-definitions.md#credit-card-number) </br> - [米国の銀行口座番号](sensitive-information-type-entity-definitions.md#us-bank-account-number)</br> -[米国の運転免許証番号](sensitive-information-type-entity-definitions.md#us-drivers-license-number) </br> - [米国の社会保障番号 (SSN)](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn)|
|プライバシー| 米国の社会保障番号の機密保持に関する州法|- [米国の社会保障番号 (SSN)](sensitive-information-type-entity-definitions.md#us-social-security-number-ssn)|

## <a name="locations"></a>場所

DLP ポリシーは、複数の場所にわたって機密情報を含むアイテムを検索して保護できます。

|場所  |範囲を含める/除外する  |データ状態  |その他の前提条件 |
|---------|---------|---------|---------|
|Exchangeメールをオンラインで送信する |配布グループ | data-in-motion| いいえ |
|SharePointサイト   |sites       | data-at-rest </br> data-in-use | いいえ|
|OneDrive for Business アカウント| アカウントまたは配布グループ |data-at-rest </br> data-in-use|いいえ|
|Teams チャットおよびチャネル メッセージ     | アカウントまたは配布グループ |data-in-motion </br> data-in-use |  いいえ       |
|Microsoft Defender for Cloud Apps   | クラウド アプリ インスタンス       |data-at-rest         | - [Microsoft 以外のクラウド アプリでデータ損失防止ポリシーを使用する](dlp-use-policies-non-microsoft-cloud-apps.md#use-data-loss-prevention-policies-for-non-microsoft-cloud-apps)        |
|デバイス  |ユーザーまたはグループ         |data-at-rest </br>  data-in-use </br>  data-in-motion         |- [エンドポイントのデータMicrosoft 365防止の詳細](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention) </br>- [エンドポイントのデータ損失防止の使用を開始する](endpoint-dlp-getting-started.md#get-started-with-endpoint-data-loss-prevention) </br>- [情報保護のデバイス プロキシとインターネット接続の設定を構成する](device-onboarding-configure-proxy.md#configure-device-proxy-and-internet-connection-settings-for-information-protection) |
|オンプレミスリポジトリ (ファイル共有とSharePoint)    |リポジトリ         | data-at-rest         | - [データ損失防止Microsoft 365オンプレミス スキャナーの詳細](dlp-on-premises-scanner-learn.md#learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner) </br> - [データ損失防止オンプレミス スキャナーの使用を開始する](dlp-on-premises-scanner-get-started.md#get-started-with-the-data-loss-prevention-on-premises-scanner)         |
|PowerBI| ワークスペース | data-in-use | いいえ|

Exchange に特定の配布グループを含めるように選択した場合、DLP ポリシーはそのグループのメンバーにのみ適用されます。 同様に、配布グループを除外すると、その配布グループのすべてのメンバーがポリシー評価から除外されます。 ポリシーを配布リストのメンバー、動的配布グループ、セキュリティ グループの範囲にすることができます。 DLP ポリシーには、このような追加および除外を 50 個まで含めることができます。

特定の SharePoint サイトまたは OneDrive アカウントを含めるか、除外するかを選択した場合、DLP ポリシーに含めることができるのは、100 を超えることはできません。 こうした制限はありますが、組織全体のポリシーまたは場所全体に適用されるポリシーを適用することで、この制限を超えることができます。

特定の OneDrive アカウントまたはグループを含めるか、除外するかを選択した場合、DLP ポリシーに含めることができるのは、ユーザー アカウントなら 100 までで、グループなら 50 までです。

### <a name="location-support-for-how-content-can-be-defined"></a>コンテンツの定義方法に関する場所のサポート

DLP ポリシーは、機密情報の種類 (SIT)、機密ラベル、または保持ラベルに一致することで、機密アイテムを検出します。 各場所では、機密性の高いコンテンツを定義するさまざまな方法がサポートされています。 ポリシー内の場所を組み合わせると、コンテンツの定義方法が 1 つの場所で定義される方法と異なる場合があります。 

> [!IMPORTANT]
> ポリシーに複数の場所を選択すると、コンテンツ定義カテゴリの "no" 値が "yes" 値よりも優先されます。 たとえば、サイトのみを選択SharePointポリシーは、1 つ以上の SIT、機密ラベル、または保持ラベルによる機密アイテムの検出をサポートします。 ただし、チャットとチャネル ***SharePointの場所*** Teamsを選択すると、ポリシーは SIT による機密性の高いアイテムの検出のみをサポートします。

|場所| コンテンツは SIT で定義できます| コンテンツは、感度ラベルを定義できます| コンテンツは保持ラベルで定義できます|
|---------|---------|---------|---------|
|Exchangeメールをオンラインで送信する|はい| はい| いいえ|
|SharePointサイト| はい| はい| はい|
|OneDrive for Business アカウント| はい| はい| はい|
|Teamsおよびチャネル メッセージ | はい| いいえ| いいえ|
|デバイス |はい | はい|  いいえ|
|Microsoft Defender for Cloud Apps | はい| はい| はい|
|オンプレミス リポジトリ| はい| はい| いいえ|
|PowerBI|はい | はい| いいえ|

> [!NOTE]
> DLP は、電子メールと添付ファイルの感度ラベルの検出をサポートしています。「DLP ポリシーで感度ラベルを条件として使用する [」を参照してください](dlp-sensitivity-label-as-condition.md#use-sensitivity-labels-as-conditions-in-dlp-policies)。

## <a name="rules"></a>ルール

<!--This section introduces the classifications of content that, when detected, can be protected. Link out to [Learn about sensitive information types]() and [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md#sensitive-information-type-entity-definitions) as well as labels (cross referenced by supporting workload). It will touch on the purpose of multiple conditions, confidence levels (link out to [more on confidence levels](sensitive-information-type-learn-about.md#more-on-confidence-levels)) and confidence levels video. How to use the confidence level to change the behavior of a policy in conjunction with the instance count.  eg. if you want your policy to trigger when it encounters situation DEF, set your conditions like HIJ.-->
<!--
- What is a rule in the context of a Policy?
- when and why should I have more than one rule?
- The purpose of rule groups
- How do I tune the behavior of a Policy through the tuning of rules
- what's in a rule-->

ルールは DLP ポリシーのビジネス ロジックです。 これらは、次の要素で構成されます。

- [**一**](#conditions) 致した場合にポリシーをトリガーする条件
- [**条件**](#exceptions) の例外
- [**ポリシー**](#actions) がトリガーされた場合に実行するアクション
- [**ユーザーが**](#user-notifications-and-policy-tips) ポリシーをトリガーする何かを行っているときにユーザーに通知し、組織が機密情報の処理方法を教育する際に役立つユーザー通知
- [**管理者が構成した**](#user-overrides) 場合のユーザーの上書き、ユーザーがブロック操作を選択的に上書きできる
- [**ルールの一**](#incident-reports) 致が発生した場合に管理者や他の主要関係者に通知するインシデント レポート
- [**ルール評価の**](#additional-options) 優先度を定義し、ルールとポリシーの処理をさらに停止できる追加オプション。

 ポリシーには、1 つ以上のルールが含まれる。 ルールは、各ポリシー内の最も高位のルールから順に実行されます。

### <a name="the-priority-by-which-rules-are-processed"></a>処理するルールの優先度

#### <a name="hosted-service-workloads"></a>ホストされたサービスのワークロード

ホストされているサービス ワークロード (Exchange Online、SharePoint Online、OneDrive for Business など) の場合、各ルールには、作成順に優先度が割り当てられます。 つまり、最初に作成されたルールには第 1 優先順位、2 番目に作成されたルールには第 2 の優先度が設定されます。 
  
![優先度順のルール](../media/dlp-rules-in-priority-order.png)

コンテンツがルールに対して評価されると、ルールは優先度順に処理されます。 コンテンツが複数のルールに一致する場合、最も制限の厳しいアクションを持つ最初のルールが適用されます。 たとえば、コンテンツが次のすべてのルールと一致する場合、ルール *3* は優先度が最も高く、最も制限の厳しいルールなので適用されます。
  
- ルール 1: ユーザーに通知のみを行う
- ルール 2: ユーザーに通知する、アクセスを制限する、ユーザーによる上書きを許可する
- *ルール 3: ユーザーに通知する、アクセスを制限する、ユーザーによる上書きを許可しない*
- ルール 4: アクセスを制限する

ルール 1、2、および 4 は評価されますが、適用されません。 この例では、最も制限の厳しいルールだけが適用されている場合でも、すべてのルールの一致が監査ログに記録され、DLP レポートに表示されます。

ルールを使用して特定の保護要件を満たし、DLP ポリシーを使用して一般的な保護要件をグループ化できます (たとえば、特定の規制に準拠する必要のあるすべてのルール)。
  
たとえば、Health Insurance Portability and Accountability Act (HIPAA) の対象となる情報の存在を検出する際に役立つ DLP ポリシーがあるとします。 この DLP ポリシーは、HIPAA データ (対象) をすべての SharePoint Online サイトと OneDrive for Business サイト (場所) で保護するために、組織外の人物と共有するこの機密情報が含まれるドキュメント (条件) を検出し、そのドキュメントに対するアクセスをブロックして通知を送信 (アクション) できます。 これらの要件は、個別のルールとして保存され、簡単に管理およびレポートする DLP ポリシーとしてまとめてグループ化されます。
  
![図は、DLP ポリシーに場所とルールが含まれていることを示しています。](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)

#### <a name="for-endpoints"></a>エンドポイントの場合

エンドポイントのルールの優先度も、エンドポイントの作成順序に従って割り当てられます。 つまり、最初に作成されたルールには第 1 優先順位、2 番目に作成されたルールには第 2 の優先度が設定されます。 

エンドポイント上のファイルが複数の DLP ポリシーと一致する場合、制限で有効になっている最初のルールは、コンテンツに適用されるルールです。 たとえば、コンテンツが次のすべてのルールと一致する場合、制限付きに構成されている優先度の高いルールなので、ルール *2 が適用されます*。
  
- ルール 1: ユーザーに通知のみを行う
- *ルール 2: ユーザーに通知する、アクセスを制限する、ユーザーによる上書きを許可する*
- ルール 3: ユーザーに通知する、アクセスを制限する、ユーザーによる上書きを許可しない
- ルール 4: アクセスを制限する

ルール 1、3、および 4 は評価されますが、適用されません。 この例では、制限付き最初のルールだけが適用されている場合でも、すべてのルールの一致が監査ログに記録され、DLP レポートに表示されます。

エンドポイントに適用されるルールの場合は、ルールの優先度を再順序付けして、適用する制限が適用されるのを確認できます。

### <a name="conditions"></a>条件

条件は包括的であり、ルールで何を探すのか、およびそれらのアイテムが使用されているコンテキストを定義する場所です。 *このようなアイテム* を見つけ、&#8212; のように使用されているアイテムを見つけると、ルール &#8212; が一致し、ポリシー内の残りのアクションを実行する必要があります。 条件を使用して、さまざまな操作をリスクレベル別に割り当てることができます。 たとえば、組織内で共有されている機密コンテンツは、組織外のユーザーと共有されている機密コンテンツよりリスク レベルが低く、必要なアクションを少なくする、といったことができます。

> [!NOTE]
> ホストの組織の Active Directory または Azure Active Directory のテナントにゲスト以外のアカウントを持っているユーザーは、組織内のユーザーと見なされます。 

#### <a name="content-contains"></a>コンテンツが含まれている

 コンテンツに含まれるすべての **場所に条件** が含まれているのがサポートされています。 各コンテンツ タイプの複数のインスタンスを選択し、次 **の (論理** OR) 演算子または **すべての (論理** AND) 演算子を使用して条件をさらに絞り込みできます。

- [機密情報の種類](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [秘密度ラベル](sensitivity-labels.md)
- [保持ラベル](retention.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)

ポリシーを適用 [する場所](#location-support-for-how-content-can-be-defined) に応じて異なる場合があります。 

ルールは、選択した感度ラベルと保持ラベル **の有無のみを** 探します。 

SIT には事前に定義された信頼 [**度が設定されています**](https://www.microsoft.com/videoplayer/embed/RE4Hx60) 。必要に応じて変更できます。 詳細については、「信頼度の [詳細」を参照してください](sensitive-information-type-learn-about.md#more-on-confidence-levels)。 

> [!IMPORTANT]
> 一意のインスタンス数の最大パラメーターを定義するには、2 つの異なる方法があります。 詳細については、「[SIT のインスタンス数のサポート値](create-a-custom-sensitive-information-type.md#instance-count-supported-values-for-sit)」を参照してください。

#### <a name="condition-context"></a>条件コンテキスト

使用可能なコンテキスト オプションは、選択した場所に応じて変わります。 複数の場所を選択すると、その場所に共通する条件だけが使用できます。

##### <a name="conditions-exchange-supports"></a>サポートExchange条件

- コンテンツが含まれている
- コンテンツは、ユーザーから共有Microsoft 365
- コンテンツの受信
- 送信者の IP アドレスが
- 送信者がポリシー ヒントを上書きしました
- 送信者が
- 送信者のドメインが次の場合
- 送信者アドレスに単語が含まれている
- 送信者アドレスにパターンが含まれている
- Sender AD属性に単語または語句が含まれている
- Sender AD属性がパターンと一致する
- 送信者は、次のメンバーです。
- メールの添付ファイルのコンテンツをスキャンできなかった
- メールの添付ファイルのコンテンツのスキャンが完了しなかった
- 添付ファイルがパスワードで保護されている
- ファイル拡張子は
- 受信者がメンバーである
- 受信者ドメインが
- 受信者が
- 受信者のアドレスに単語が含まれている
- 受信者のアドレスがパターンと一致している
- 受信者AD属性には、単語または語句が含まれる
- 受信者AD属性がパターンと一致する
- ドキュメント名には、単語または語句が含まれる
- ドキュメント名がパターンと一致する
- 文書のプロパティが
- ドキュメント のサイズが等しいか、またはより大きい
- ドキュメントコンテンツには、単語または語句が含まれる
- ドキュメント コンテンツがパターンと一致する
- 件名には、単語または語句が含まれている
- 件名がパターンと一致している
- 件名または本文に単語または語句が含まれる
- 件名または本文がパターンと一致する
- コンテンツ文字セットに単語が含まれている
- ヘッダーには、単語または語句が含まれています
- ヘッダーがパターンと一致している
- メッセージ サイズが等しいか、またはより大きい
- メッセージの種類は次の値です。
- メッセージの重要度は、

##### <a name="conditions-sharepoint-supports"></a>サポートSharePoint条件
 
- コンテンツが含まれている
- コンテンツは、ユーザーから共有Microsoft 365
- ファイル拡張子は
- 文書のプロパティが

##### <a name="conditions-onedrive-accounts-supports"></a>アカウントOneDriveサポートされる条件

- コンテンツが含まれている
- コンテンツは、ユーザーから共有Microsoft 365
- ファイル拡張子は
- 文書のプロパティが

##### <a name="conditions-teams-chat-and-channel-messages-supports"></a>チャットTeamsチャネル メッセージがサポートする条件

- コンテンツが含まれている
- コンテンツは、ユーザーから共有Microsoft 365
- Sender is (Preview)
- 送信者ドメインは (プレビュー)
- 受信者ドメインは (プレビュー)
- 受信者は (プレビュー)

##### <a name="conditions-devices-supports"></a>デバイスがサポートする条件

- コンテンツが含まれている
- 「監視 [およびアクションを実行できるエンドポイント アクティビティ」を参照してください。](endpoint-dlp-learn-about.md#endpoint-activities-you-can-monitor-and-take-action-on)

##### <a name="conditions-microsoft-defender-for-cloud-apps-supports"></a>Microsoft Defender for Cloud Apps がサポートする条件

- コンテンツが含まれている
- コンテンツは、ユーザーから共有Microsoft 365

##### <a name="conditions-on-premises-repositories-supports"></a>オンプレミス リポジトリがサポートする条件

- コンテンツが含まれている
- ファイル拡張子は
- 文書のプロパティが

##### <a name="conditions-powerbi-supports"></a>PowerBI がサポートする条件

- コンテンツが含まれている

#### <a name="condition-groups"></a>条件グループ

1 つの SIT で定義されている米国の社会保障番号を含むすべてのコンテンツなど、1 つのことを識別するためのルールが必要な場合があります。 ただし、特定しようとしているアイテムの種類が複雑で定義が困難な多くのシナリオでは、条件の定義に柔軟性が必要になります。

たとえば、米国の健康保険法 (HIPAA) の適用対象のコンテンツを特定するには、次を検索する必要があります。
  
- 特定の種類の機密情報 (社会保障番号や麻薬取締局 (DEA) 番号など) を含んでいるコンテンツ。
    
    AND
    
- 特定がより難しいコンテンツ (患者の治療に関する通信記録や提供された医療サービスの説明など)。 コンテンツを特定するには、国際疾病分類 (ICD-9-CM または ICD-10-CM) などの大きなキーワード リストからキーワードを一致させる必要があります。
    
この種類のデータは、条件をグループ化し、グループ間で論理演算子 (AND、 OR) を使用して識別できます。
    
米国健康保険 **法 (HIPPA)** の場合、条件は次のようにグループ化されます。

![HIPPA ポリシーの条件](../media/dlp-rules-condition-groups-booleans.png)

最初のグループには、個人を識別する T を含み、2 番目のグループには医療診断を識別する T を含む。

### <a name="exceptions"></a>例外

ルールでは、例外はポリシーからアイテムを除外するために使用される条件を定義します。 論理的には、包括的な条件とコンテキストの後に評価される排他的な条件。 ルール &#8212; は、このようなアイテムが見つから、それが一致し、ポリシー内の残りのアクションが ***if..*** を除いて実行される必要があるように使用されている場合に、ルール &#8212; に伝えます。&#8212; 

たとえば、HIPPA ポリシーに従って、ベルギーのドライバーライセンス番号を含むアイテムを除外するルールを変更できます。次のようにします。

![除外を含む HIPPA ポリシー](../media/dlp-rule-exceptions.png)

場所でサポートされる例外条件は、すべての包含条件と同じです。唯一の違いは、サポートされている各条件に対して "If を除く" の事前保留です。 ルールに例外だけが含まれている場合、除外条件を満たしていないすべての電子メールまたはファイルに適用されます。

すべての場所が包括的な条件をサポートしているのと同じ方法です。

- コンテンツが含まれている

例外は次の場合です。

- **コンテンツが含** まれている場合を除く 

### <a name="actions"></a>Actions 

包括的な ***conditions** _ フィルターと排他例外フィルターを使用 _**_ するアイテムには、ルールで _**_ 定義されているアクションが適用されます。 アクションをサポートするために必要なオプションを構成する必要があります。 たとえば、_ *Restrict* access を使用Exchangeを選択した場合、または Microsoft 365 場所* アクションでコンテンツを暗号化する場合は、次のオプションから選択する必要があります。

- ユーザーが共有コンテンツ、SharePoint、OneDrive、Teamsをブロックする
    - すべてのユーザーをブロックします。 コンテンツ所有者、最終修飾子、およびサイト管理者だけが引き続きアクセス権を持つ
    - 組織外からのユーザーのみをブロックします。 組織内のユーザーは引き続きアクセスできます。
- 電子メール メッセージを暗号化する (Exchange のコンテンツにのみ適用)

ルールで使用できるアクションは、選択されている場所によって異なります。 ポリシーを適用する場所を 1 つのみ選択した場合、使用可能なアクションを以下に示します。

> [!IMPORTANT]
> SharePoint Online および OneDrive for Business の場所のドキュメントは、ドキュメントが共有されるかどうかに関係なく、機密情報を検出した直後に、すべての外部ユーザーに対して積極的にブロックされ、内部ユーザーは引き続きドキュメントにアクセスできます。

#### <a name="exchange-location-actions"></a>Exchange場所の操作

- アクセスを制限するか、または場所内のコンテンツMicrosoft 365する
- ヘッダーの設定
- ヘッダーの削除
- メッセージを特定のユーザーにリダイレクトする
- 承認のためにメッセージを送信者のマネージャーに転送する
- 承認のメッセージを特定の承認者に転送する
- [宛先] ボックスに受信者を追加する
- [Cc] ボックスに受信者を追加する
- [Bcc] ボックスに受信者を追加する
- 送信者のマネージャーを受信者として追加する
- O365 メッセージの暗号化と権限の保護を削除しました
- 電子メールの件名の先頭に追加する
- メールの件名を変更する
- HTML 免責事項の追加

#### <a name="sharepoint-sites-location-actions"></a>SharePoint場所の操作

- アクセスを制限するか、または場所内のコンテンツMicrosoft 365する

#### <a name="onedrive-account-location-actions"></a>OneDriveの場所の操作

- アクセスを制限するか、または場所内のコンテンツMicrosoft 365する

#### <a name="teams-chat-and-channel-messages-actions"></a>Teamsおよびチャネル メッセージの操作

- アクセスを制限するか、または場所内のコンテンツMicrosoft 365する

#### <a name="devices-actions"></a>デバイスアクション

- デバイスのアクティビティを監査またはWindowsする

これらの設定を使用するには、DLP 設定および **それらを** 使用するポリシーでオプションを構成する必要があります。 詳細については、「 [制限付きアプリとアプリ グループ](dlp-configure-endpoint-settings.md#restricted-apps-and-app-groups) 」を参照してください。

デバイスの場所には、多くのサブアクティブ (条件) とアクションが提供されます。 詳細については、「監視およびアクション [を実行できるエンドポイント アクティビティ」を参照してください](endpoint-dlp-learn-about.md#endpoint-activities-you-can-monitor-and-take-action-on)。

[監査] **または [** Windows デバイスでのアクティビティの制限] を選択すると、サービス ドメインまたはブラウザー別にユーザー アクティビティを制限し、DLP が実行するアクションの範囲を指定できます。

- すべてのアプリ
- 定義する制限付きアプリの一覧
- 定義した制限付きアプリ グループ (プレビュー) を指定します。

##### <a name="service-domain-and-browser-activities"></a>サービス ドメインとブラウザーのアクティビティ

[クラウド サービス ドメインの許可 **と** ブロック] と [許可しない [ブラウザー] リスト](dlp-configure-endpoint-settings.md#browser-and-domain-restrictions-to-sensitive-data) (「機密データに対するブラウザーとドメインの制限」を参照) `Audit only``Block with override``Block` を構成し、保護されたファイルをクラウド サービス ドメインにアップロードするか、許可されていないブラウザーからアクセスしようとすると、ポリシー アクションを 、アクティビティに構成できます。

##### <a name="file-activities-for-all-apps"></a>すべてのアプリのファイル アクティビティ

[すべての **アプリのファイル アクティビティ**] オプションを使用して、[ファイル アクティビティを制限しない] または [特定のアクティビティに制限を適用する **] を選択します**。 特定のアクティビティに制限を適用する場合、ここで選択したアクションは、ユーザーが DLP で保護されたアイテムにアクセスした場合に適用されます。 DLP には、次の `Audit only`ユーザー `Block with override`アクティビティに対 `Block` して 、(アクション) を指定できます。

- **クリップボードにコピー**
- **USB リムーバブル ドライブへのコピー** 
- **ネットワーク共有へのコピー**
- **Print**
- **許可されていないアプリを使用してコピーまたはBluetoothする**
- **リモート デスクトップ サービス**


##### <a name="restricted-app-activities"></a>制限付きアプリアクティビティ  

以前は「許可されていないアプリ」と呼ばばがありましたが、制限を適用するエンドポイント DLP 設定でアプリの一覧を定義します。 ユーザーが一覧にあるアプリを使用して DLP `Audit only``Block with override`で保護されたファイルにアクセスしようとすると、アクティビティを`Block`使用できます。 制限付きアプリ アクティビティ **で定義されている DLP アクションは** 、アプリが制限付きアプリ グループのメンバーである場合に上書きされます。 その後、制限付きアプリ グループで定義されているアクションが適用されます。

##### <a name="file-activities-for-apps-in-restricted-app-groups-preview"></a>制限付きアプリ グループ内のアプリのファイル アクティビティ (プレビュー)

制限付きアプリ グループは、エンドポイント DLP 設定で定義し、制限付きアプリ グループをポリシーに追加します。 制限付きアプリ グループをポリシーに追加する場合は、次のいずれかのオプションを選択する必要があります。

- ファイルアクティビティを制限しない
- すべてのアクティビティに制限を適用する
- 特定のアクティビティに制限を適用する

[制限の適用] オプションのいずれかを選択し、ユーザーが制限付きアプリ グループ内のアプリを使用して DLP `Audit only``Block with override``Block` 保護ファイルにアクセスしようとすると、アクティビティ別に 、または、どちらかを指定できます。 ここで定義する DLP アクションは、アプリのすべてのアプリの制限付きアプリ アクティビティとファイル アクティビティで定義されている **アクション** を上書きします。

詳細については、「 [制限付きアプリとアプリ グループ](dlp-configure-endpoint-settings.md#restricted-apps-and-app-groups) 」を参照してください。 

#### <a name="microsoft-defender-for-cloud-apps-actions"></a>Microsoft Defender for Cloud Apps アクション

- アクセスを制限するか、または場所内のコンテンツMicrosoft 365する
- サード パーティ製アプリの制限

#### <a name="on-premises-repositories-actions"></a>オンプレミスリポジトリのアクション

- アクセスの制限またはオンプレミス ファイルの削除

#### <a name="powerbi-actions"></a>PowerBI アクション

- メールおよびポリシー ヒントでユーザーに通知する
- 管理者にアラートを送信する

#### <a name="actions-available-when-you-combine-locations"></a>場所を結合するときに使用できるアクション

ポリシーを適用するExchangeその他の単一の場所を選択した場合は、

- アクセスを制限するか、または場所内のコンテンツMicrosoft 365する

and

- ユーザー以外の場所に対Exchangeアクション

アクションが使用可能になります。

ポリシーを適用する 2 つ以上Exchangeの場所を選択すると、

- アクセスを制限するか、または場所内のコンテンツMicrosoft 365する

AND

- ユーザー以外の場所に対Exchangeアクション 

アクションが使用可能になります。

たとえば、[デバイス] と [Exchange] を場所として選択すると、次のアクションを使用できます。

- アクセスを制限するか、または場所内のコンテンツMicrosoft 365する
- デバイスのアクティビティを監査またはWindowsする

[デバイス] と [Microsoft Defender for Cloud Apps] を選択した場合、次のアクションを使用できます。

- アクセスを制限するか、または場所内のコンテンツMicrosoft 365する
- デバイスのアクティビティを監査またはWindowsする
- サード パーティ製アプリの制限

アクションが有効かどうかは、ポリシーのモードの構成方法によって異なります。 [最初にテストする] オプションを選択すると、ポリシー ヒントを表示する場合と表示せずに、テスト モードでポリシー **を実行できます** 。 [すぐに有効にする] オプションを選択して、ポリシーの作成から 1 時間後にポリシーを実行するか、保存して後で [オフにする] オプションを選択してポリシーに戻す方法を **選択** できます。 


<!-- This section needs to explain that the actions available depend on the locations selected AND that the observed behavior of a policy is produced through an interaction of the configured actions AND the configured status (off, test, apply) of a policy. It will detail the purpose of each of the available actions and the location/desired outcome interaction and provide examples eg. how to use the Restrict Third Party apps in the context of a policy that is applied to endpoints so that users can't use a upload content to a third party site or the interaction of on-premises scanner with restrict access or remove on-premises files.  Also what happens when I select multiple locations? provide abundant examples for most common scenarios-->


### <a name="user-notifications-and-policy-tips"></a>ユーザー通知とポリシーヒント

<!--This section introduces the business need for user notifications, what they are, their benefit, how to use them, how to customize them, and links out to 

- https://docs.microsoft.com/en-us/microsoft-365/compliance/use-notifications-and-policy-tips?view=o365-worldwide
- https://docs.microsoft.com/en-us/microsoft-365/compliance/dlp-policy-tips-reference?view=o365-worldwide

for where they are used/expected behavior-->

<!--You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.-->

ユーザーがルールの条件と例外を満たすコンテキストで機密性の高いアイテムに対してアクションを試みる場合は、ユーザー通知メールとコンテキスト ポリシー ヒント ポップアップを使用して、そのアイテムについて知らせできます。 これらの通知は、意識を高め、組織の DLP ポリシーに関する人々の教育に役立つため便利です。

たとえば、個人を特定できる情報 (PII) Excel含み、ゲストと共有される OneDrive for Business サイト上のブックのようなコンテンツ。

![メッセージ バーに Excel 2016 のポリシー ヒントが表示される](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)

> [!NOTE]
> 通知メールは保護されていない状態で送信されます。

また、有効なビジネス上の必要[](#user-overrides)がある場合やポリシーが誤検知を検出した場合にブロックされない状態で、ポリシーを上書きするオプションをユーザーに提供することもできます。

ユーザー通知とポリシー ヒントの構成オプションは、選択した監視場所によって異なります。 選択した場合:

- Exchange
- SharePoint
- OneDrive
- Teamsチャットとチャネル
- Defender for Cloud Apps


さまざまな Microsoft アプリのユーザー通知を有効または無効にできます。「データ損失防止ポリシーのヒント [リファレンス」を参照してください。](dlp-policy-tips-reference.md#data-loss-prevention-policy-tips-reference)

- ポリシー ヒントを使用して、Office 365ユーザーに通知 **を** 有効または無効にできます。
    - コンテンツを送信、共有、または最後に変更したユーザーへの電子メール通知 OR
    - 特定のユーザーに通知する

をクリックし、電子メール テキスト、件名、ポリシー ヒント テキストをカスタマイズします。

![Exchange、SharePoint、OneDrive、Teams チャットとチャネル、および Defender for Cloud Apps で使用可能なユーザー通知とポリシー ヒントの構成オプション](../media/dlp-user-notification-non-devices.png)

[デバイスのみ] を選択した場合、Exchange、SharePoint、OneDrive、Teams チャット、チャネル、Defender for Cloud Apps で使用可能なすべての同じオプションと、Windows 10 デバイスに表示される通知タイトルとコンテンツをカスタマイズするオプションが表示されます。

![デバイスで使用できるユーザー通知とポリシー ヒントの構成オプション](../media/dlp-user-notification-devices.png)  

これらのパラメーターを使用して、テキストのタイトルと本文をカスタマイズできます。 本文のテキストは、次の機能をサポートします。

|共通名  |パラメーター  |例
|---------|---------|---------|
|ファイル名     |%%FileName%% | Contoso doc 1 |
|プロセス名     |%%ProcessName%% | Word |
|ポリシー名     |%%PolicyName%%| Contoso の機密性の高い |
|action | %%AppliedActions%% | クリップボードから別のアプリにドキュメントコンテンツを貼り付ける |

**%%AppliedActions%% は、次** の値をメッセージ本文に置き換える。


|アクションの共通名 |%%AppliedActions%% パラメーターで置換された値 |
|---------|---------|
|削除可能な記憶域にコピーする    |*リムーバブル 記憶域への書き込み*         |
|ネットワーク共有にコピーする     |*ネットワーク共有への書き込み*         |
|print     |*印刷*         |
|クリップボードから貼り付ける  |*クリップボードからの貼り付け*         |
|bluetooth 経由でコピーする   |*を介して転送Bluetooth*         |
|許可されていないアプリで開く     |*このアプリで開く*         |
|リモート デスクトップ (RDP) へのコピー     |*リモート デスクトップへの転送*         |
|許可されていない Web サイトへのアップロード     |*このサイトへのアップロード*         |
|許可されていないブラウザーを介してアイテムにアクセスする     |*このブラウザーで開く*         |

このカスタマイズされたテキストの使用

*%%AppliedActions%% ファイル名 %%FileName%% via %%ProcessName%%は、組織では許可されません。ポリシー %%PolicyName%% をバイパスする場合は、[許可] をクリックします。* 

カスタマイズされた通知で次のテキストを生成します。

*クリップボードから貼り付けるファイル名: Contoso doc 1 を使用WINWORD.EXE組織では許可されません。Contoso の機密性の高いポリシーをバイパスする場合は、[許可] ボタンをクリックします。*
 

> [!NOTE]
> ユーザー通知とポリシー ヒントは、オンプレミスの場所では使用できません

> [!NOTE]
> 最も優先度が高く、制限が厳しいルールのポリシー ヒントのみが表示されます。 たとえば、単に通知を送信するルールのポリシー ヒントよりも、コンテンツへのアクセスを禁止するルールのポリシー ヒントの方が優先して表示されます。 これにより、ポリシー ヒントがカスケード表示されるのを防止します。

ユーザー通知とポリシー ヒントの構成と使用の詳細については、「通知とヒント テキストをカスタマイズする方法」を参照してください。 
- [電子メール通知を送信し、DLP ポリシーのポリシー ヒントを表示します](use-notifications-and-policy-tips.md#send-email-notifications-and-show-policy-tips-for-dlp-policies)。
  
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

### <a name="user-overrides"></a>ユーザーの上書き

ユーザーオーバーライドの目的は、ユーザーが作業を続行できるよう、Exchange、SharePoint、OneDrive、または Teams の機密性の高いアイテムに対する DLP ポリシーブロックアクションを正当化してバイパスする方法をユーザーに与える方法です。 ユーザーの上書きは、Office 365  サービスのユーザーにポリシー ヒントを通知するが有効になっている場合にのみ有効になっているので、ユーザーの上書きは通知とポリシーのヒントと手をつないで行きます。 

![DLP ポリシーのユーザーオーバーライド オプション](../media/dlp-user-overrides.png)

> [!NOTE]
> ユーザーの上書きは、オンプレミスリポジトリの場所では使用できません。

通常、ユーザーの上書きは、組織が最初にポリシーを展開するときに役立ちます。 オーバーライドの正当性と誤検知の識別から得たフィードバックは、ポリシーの調整に役立ちます。 

<!-- This section covers what they are and how to best use them in conjunction with Test/Turn it on right away and link out to where to find the business justification for the override (DLP reports?  https://docs.microsoft.com/en-us/microsoft-365/compliance/view-the-dlp-reports?view=o365-worldwide)  https://docs.microsoft.com/en-us/microsoft-365/compliance/view-the-dlp-reports?view=o365-worldwide#view-the-justification-submitted-by-a-user-for-an-override-->

- 	最も制限の厳しいルールでユーザーにルールを上書きすることを許可している場合は、このルールを上書きすることで、コンテンツに一致した他のルールもすべて上書きされます。
 
<!--![User notifications and user overrides sections of DLP rule editor](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)-->
 
ユーザーオーバーライドの詳細については、以下を参照してください。

- [ユーザーがオーバーライドのために送信した位置合わせを表示する](view-the-dlp-reports.md#view-the-justification-submitted-by-a-user-for-an-override)

### <a name="incident-reports"></a>インシデント レポート

<!--DLP interacts with other M365 information protection services, like IR. Link this to a process outline for triaging/managing/resolving DLP incidents


https://docs.microsoft.com/en-us/microsoft-365/compliance/view-the-dlp-reports?view=o365-worldwide
https://docs.microsoft.com/en-us/microsoft-365/compliance/dlp-configure-view-alerts-policies?view=o365-worldwide-->

ルールが一致する場合は、イベントの詳細を含むインシデント レポートをコンプライアンス担当者 (または選択したユーザー) に送信できます。 レポートには、一致したアイテム、ルールに一致した実際のコンテンツ、およびコンテンツを最後に変更したユーザーの名前に関する情報が含まれます。 メール メッセージの場合、レポートには添付ファイルとして、DLP ポリシーに適合する元のメッセージも含まれます。

DLP は、インシデント情報を他Microsoft 365情報保護サービス (インサイダー リスク管理など) [に](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)フィードMicrosoft 365。 インサイダー リスク管理にインシデント情報を取得するには、インシデント レポートの重大度レベルを High に設定する必要 **があります**。

<!--![Page for configuring incident reports](../media/31c6da0e-981c-415e-91bf-d94ca391a893.png)-->

アクティビティがルールに一致する度にアラートを送信できます。これは、ノイズが多い場合や、一定の期間のアイテムの一致数または量に基づいて、より少ないアラートに集約できます。

![ルールが一致するか、時間の間に少ないレポートに集約されるごとにアラートを送信する](../media/dlp-incident-reports-aggregation.png)

DLP は、オンラインまたは他のアイテムと異SharePointメールをOneDrive for Businessします。 SharePoint Online や OneDrive for Business では、DLP は新しいアイテムだけでなく既存のアイテムもスキャンして、一致が検出される場合は常にインシデント レポートを生成します。 Exchange Online では、DLP は新しいメール メッセージのみをスキャンして、ポリシーとの一致が検出されるとレポートを生成します。 DLP は、メールボックスやアーカイブに保存されている既存のメール アイテムについては、スキャンや一致検出を ***実行しません***。

### <a name="additional-options"></a>追加オプション

ポリシーに複数のルールがある場合は、[追加] オプションを使用して、編集中のルールに一致する場合の追加のルール処理を制御し、ルールの評価の優先度を設定できます。

## <a name="see-also"></a>関連項目

- [データ損失防止について](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [データ損失防止 (DLP) の計画](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [テンプレートから DLP ポリシーを作成する](create-a-dlp-policy-from-a-template.md#create-a-dlp-policy-from-a-template)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy)
