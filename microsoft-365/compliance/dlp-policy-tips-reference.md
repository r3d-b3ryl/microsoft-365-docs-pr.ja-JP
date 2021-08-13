---
title: データ損失防止ポリシーヒントのリファレンス
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
recommendations: false
description: データ損失防止 (DLP) ポリシーにポリシー ヒントを追加する方法について、DLP ポリシーと競合するコンテンツを操作しているユーザーに通知する方法について学習します。
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 785d7fad1cf35bab56594e5b0c11287c153eaa44aedcf2cf6b44a742ed93ee74
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53814461"
---
# <a name="data-loss-prevention-policy-tips-reference"></a>データ損失防止ポリシーヒントのリファレンス

Outlook Web Access の DLP ポリシー ヒントは、以下を除き、DLP ポリシー内の Exchange ワークロードに適用可能なすべての条件、例外、およびアクションでサポートされます。

**条件:**

- Sender Is
- Sender Domain Is
- 受信者が次のメンバーの場合
- ヘッダーには、単語または語句が含まれています
- ヘッダーがパターンと一致している
- ドキュメント のサイズが等しいか、またはより大きい
- メッセージの種類は次の値です。
- メッセージの重要度は、
- コンテンツ文字セットに単語が含まれている
- 件名または本文に単語または語句が含まれる
- 件名または本文がパターンと一致する
- コンテンツ文字セットに単語が含まれている
- コンテンツの受信
- 送信者がポリシー ヒントを上書きしました
- メッセージ サイズが等しいか、またはより大きい
- Sender AD属性に単語または語句が含まれている
- Sender AD属性がパターンと一致する
- ドキュメントコンテンツには、単語または語句が含まれる
- ドキュメント コンテンツがパターンと一致する

**アクション:**

- 承認のためにメッセージを送信者のマネージャーに転送する
- 承認のメッセージを特定の承認者に転送する
- メッセージを特定のユーザーにリダイレクトする
- 宛先ボックスに受信者を追加する
- Cc ボックスに受信者を追加する
- Bcc ボックスに受信者を追加する
- 送信者のマネージャーを受信者として追加する
- HTML 免責事項の追加
- 電子メールの件名の先頭に追加する
- O365 メッセージの暗号化と権限の保護を削除する

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a>Outlook 2013 以降では、一部の条件と例外に関するポリシー ヒントの表示がサポートされています

現在、Outlook 2013 以降では、以下の条件と対応する例外以外の条件や例外を含むポリシーに関するポリシー ヒントの表示がサポートされています。

- コンテンツが含まれる (機密情報の種類に対してのみ機能します)。 感度ラベルはサポートされていません)
- コンテンツが共有されている

すべての条件は、コンテンツと一致し、コンテンツに対して保護アクションを適用Outlookクライアント アプリで作成された電子メールに対して機能します。 ただし、ユーザーにポリシー ヒントを表示する方法は、上記の条件とは別に使用される条件ではサポートされていません。

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a>Outlook 2013 以降およびデスクトップ上Officeアプリの一部の機密情報の種類についてのみポリシー ヒントを表示するサポート

デスクトップ上の Outlook (2013 以降) および Office アプリ (Word、Excel、PowerPoint) で DLP ポリシー ヒントをデスクトップに表示するために検出される、既定の機密情報の種類の一覧を次に示します。

- ABA ルーティング番号
- アルゼンチンの国民識別 (DNI) 番号
- オーストラリアの銀行口座番号
- オーストラリアの医療口座番号
- オーストラリアのパスポート番号
- オーストラリアの納税者番号
- Azure DocumentDB Auth Key  
- Azure IAAS データベース接続文字列と Azure SQL接続文字列  
- Azure IoT接続文字列  
- Azure 発行設定パスワード  
- Azure Redis キャッシュ接続文字列  
- Azure SAS  
- Azure Service Bus接続文字列  
- Azure Storageアカウント キー  
- Azure Storageアカウント キー (汎用)  
- ベルギーの国民番号
- ブラジルの CPF 番号
- Brazil Legal Entity Number (CNPJ)
- 	ブラジルの国民識別カード (RG)
- カナダの銀行口座番号
- カナダの運転免許証番号
- カナダの健康保険番号
- カナダのパスポート番号
- カナダの個人保健識別番号 (PHIN)
- カナダの社会保険番号
- 	チリの身分証明書番号
- 	中国の居民身分証明書 (PRC) 番号
- クレジット カード番号
- クロアチアの身分証明書番号  
- クロアチアの個人識別 (OIB) 番号  
- チェコの個人 ID 番号  
- デンマークの個人識別番号
- 麻薬取締局 (DEA) 番号
- 欧州連合のデビット カード番号
- EU の運転免許証番号  
- EU の国民識別番号  
- EU パスポート番号  
- EU 社会保障番号 (SSN) または同等の ID  
- EU 税 ID 番号 (TIN)  
- フィンランドの国民 ID
- フィンランドのパスポート番号
- フランスの運転免許証番号
- フランスの国民識別カード (CNI)
- フランスのパスポート番号
- フランスの社会保障番号 (INSEE)
- ドイツの運転免許証番号
- ドイツのパスポート番号
- ドイツの身分証明書番号
- ギリシャの国民識別カード  
- 香港の ID カード (HKID) 番号
- インドの永久口座番号 (PAN)
- インドの固有識別 (Aadhaar) 番号
- インドネシアの身分証明書 (KTP) 番号
- 国際銀行口座番号 (IBAN)
- 国際分類の病気 (ICD-10-CM)  
- 国際疾病分類 (ICD-9-CM)  
- IP アドレス
- アイルランドの個人公共サービス (PPS) 番号 
- イスラエルの銀行口座番号
- イスラエルの国民 ID
- イタリアの運転免許証番号
- 日本の銀行口座番号
- 日本の運転免許証番号
- 日本のパスポート番号
- 日本の住民登録番号
- 日本の社会保険番号 (SIN)
- 日本の在留カード番号
- マレーシアの ID カード番号
- オランダの市民サービス (BSN) 番号  
- ニュージーランドの保健省番号
- ノルウェーの識別番号  
- フィリピンの汎用多目的 ID 番号
- ポーランドの ID カード
- ポーランドの国民 ID (PESEL)
- ポーランドのパスポート
- ポルトガルの市民カード番号
- サウジアラビアの国民 ID
- シンガポールの国民登録 ID カード (NRIC) 番号
- 南アフリカの識別番号  
- 韓国の住民登録番号
- スペインの社会保障番号 (SSN)
- SQL Server接続文字列  
- スウェーデンの国民 ID
- スウェーデンのパスポート番号
- SWIFT コード
- 台湾の国民 ID
- 	台湾のパスポート番号
- 台湾居住者証明書 (ARC/TARC)
- タイの人口識別コード
- トルコの国民識別番号
- 英国の運転免許証番号
- 英国の選挙登録番号
- 英国の国民健康保険番号
- 英国の国民保険番号 (NINO)
- 米国/英国のパスポート番号
- 米国の銀行口座番号
- 米国の運転免許証番号
- 米国の個人納税者識別番号 (ITIN)
- 米国の社会保障番号 (SSN)

カスタムの機密情報の種類は、上記の機密情報の種類に加えて、DLP ポリシー のヒントにもサポートされています。

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a>エンドポイント デバイスのデータ損失防止は、一部の機密情報の種類についてのみポリシー ヒントをサポートします

エンドポイント デバイスに存在するドキュメントで検出される、既定の機密情報の種類の一覧は次のとおりです。

- ABA ルーティング番号 
- アルゼンチンの国民識別 (DNI) 番号 
- オーストラリアの銀行口座番号 
- オーストラリアの医療口座番号 
- オーストラリアのパスポート番号 
- オーストラリアの納税者番号 
- オーストラリアのビジネス番号 
- オーストラリアの会社番号 
- オーストリアの運転免許証番号 
- オーストリアの ID カード 
- オーストリアのパスポート番号 
- オーストリアの社会保障番号 
- オーストリアの納税者番号 
- オーストリア付加価値税 (VAT) 番号 
- Azure DocumentDB Auth Key 
- Azure IAAS データベース接続文字列と Azure SQL接続文字列 
- Azure IoT接続文字列 
- Azure 発行設定パスワード 
- Azure Redis キャッシュ接続文字列 
- Azure SAS 
- Azure Service Bus接続文字列 
- Azure Storageアカウント キー 
- Azure Storageアカウント キー (汎用) 
- ベルギーの運転免許証番号 
- ベルギーの国民番号 
- ベルギーのパスポート番号 
- ベルギーの付加価値税番号 
- ブラジルの CPF 番号 
- Brazil Legal Entity Number (CNPJ) 
- 	ブラジルの国民識別カード (RG) 
- ブルガリアの運転免許証番号 
- ブルガリアのパスポート番号 
- ブルガリアの統一市民番号 
- カナダの銀行口座番号 
- カナダの運転免許証番号 
- カナダの健康保険番号 
- カナダのパスポート番号 
- カナダの個人保健識別番号 (PHIN) 
- カナダの社会保険番号 
- 	チリの身分証明書番号 
- 	中国の居民身分証明書 (PRC) 番号 
- クレジットカード番号 
- クロアチア の運転免許証番号 
- クロアチアの身分証明書番号 
- クロアチアの国民 ID カード番号 
- クロアチアのパスポート番号 
- クロアチアの個人識別 (OIB) 番号 
- CSCAN-AZURE0060 Azure Storage共有アクセス署名 
- CSCAN-GENERAL0140 一般対称キー 
- キプロス の運転免許証番号 
- キプロスの ID カード 
- キプロスのパスポート番号 
- キプロスの納税者番号 
- チェコの運転免許証番号 
- チェコの個人 ID 番号 
- チェコ共和国のパスポート番号 
- デンマークの運転免許証番号 
- デンマークのパスポート番号 
- デンマークの個人識別番号 
- 麻薬取締局 (DEA) 番号 
- エストニア の運転免許証番号 
- エストニアのパスポート番号 
- エストニアの個人識別コード 
- 欧州連合のデビット カード番号 
- EU の運転免許証番号 
- EU の国民識別番号 
- EU パスポート番号 
- EU 社会保障番号 (SSN) または同等の ID 
- EU 税 ID 番号 (TIN) 
- フィンランド の運転免許証番号 
- フィンランド のヨーロッパの健康保険番号 
- フィンランドの国民 ID 
- フィンランドのパスポート番号 
- フランスの運転免許証番号 
- フランスの健康保険番号 
- フランスの国民識別カード (CNI) 
- フランスのパスポート番号 
- フランスの社会保障番号 (INSEE) 
- フランスの納税者番号 (numéro SPI.) 
- フランスの付加価値税番号 
- ドイツの運転免許証番号 
- ドイツのパスポート番号 
- ドイツの身分証明書番号 
- ドイツの納税者番号 
- ドイツの付加価値税番号 
- ギリシャの運転免許証番号 
- ギリシャの国民識別カード 
- ギリシャのパスポート番号 
- ギリシャの社会保障番号 (AMKA) 
- ギリシャ語の税の識別番号 
- 香港の ID カード (HKID) 番号 
- ハンガリーの社会保障番号 (TAJ) 
- ハンガリーの付加価値税番号 
- ハンガリー の運転免許証番号 
- ハンガリーのパスポート番号 
- ハンガリーの個人識別番号 
- ハンガリー 税の識別番号 
- インドの永久口座番号 (PAN) 
- インドの固有識別 (Aadhaar) 番号 
- インドネシアの身分証明書 (KTP) 番号 
- 国際銀行口座番号 (IBAN) 
- 国際分類の病気 (ICD-10-CM) 
- 国際疾病分類 (ICD-9-CM) 
- IP アドレス 
- アイルランドの運転免許証番号 
- アイルランドのパスポート番号 
- アイルランドの個人公共サービス (PPS) 番号 
- イスラエルの銀行口座番号 
- イスラエルの国民 ID 
- イタリアの運転免許証番号 
- イタリアの会計コード 
- イタリアのパスポート番号 
- イタリアの付加価値税番号 
- 日本の銀行口座番号 
- 日本の運転免許証番号 
- 日本のパスポート番号 
- 日本の住民登録番号 
- 日本の社会保険番号 (SIN) 
- 日本語 My Number Corporate 
- 日本語の個人用番号 
- 日本の在留カード番号 
- ラトビア の運転免許証番号 
- ラトビアのパスポート番号 
- ラトビアの個人コード 
- リトアニア の運転免許証番号 
- リトアニアのパスポート番号 
- リトアニア の個人用コード 
- ルクセンブルク 運転免許証番号 
- ルクセンブルク国民識別番号 (自然人) 
- ルクセンブルク国民識別番号 (非自然人) 
- ルクセンブルク パスポート番号 
- マレーシアの ID カード番号 
- マルタの運転免許証番号 
- マルタの ID カード番号 
- マルタのパスポート番号 
- マルタ税 ID 番号 
- オランダの市民サービス (BSN) 番号 
- オランダの運転免許証番号 
- オランダのパスポート番号 
- オランダの納税者番号 
- オランダの付加価値税番号 
- ニュージーランドの銀行口座番号 
- ニュージーランドの運転免許証番号 
- ニュージーランド 内陸の収益番号 
- ニュージーランドの保健省番号 
- ニュージーランドのソーシャル 福利厚生番号 
- ノルウェーの識別番号 
- フィリピンの汎用多目的 ID 番号 
- ポーランド の運転免許証番号 
- ポーランドの ID カード 
- ポーランドの国民 ID (PESEL) 
- ポーランドのパスポート 
- ポーランドの納税者番号 
- ポーランド語 REGON 番号 
- ポルトガルの市民カード番号 
- ポルトガルの運転免許証番号 
- ポルトガルのパスポート番号 
- ポルトガルの納税者番号 
- ルーマニアの運転免許証番号 
- ルーマニアのパスポート番号 
- ルーマニア の個人数値コード (CNP) 
- ロシアのパスポート番号 (国内) 
- ロシアのパスポート番号 (国際) 
- サウジアラビアの国民 ID 
- シンガポールの国民登録 ID カード (NRIC) 番号 
- スロバキアの運転免許証番号 
- スロバキアのパスポート番号 
- スロバキアの個人番号 
- スロベニア の運転免許証番号 
- スロベニアのパスポート番号 
- スロベニアの納税者番号 
- スロベニアの一意のマスター市民番号 
- 南アフリカの識別番号 
- 韓国の住民登録番号 
- スペイン DNI 
- スペインの運転免許証番号 
- スペインのパスポート番号 
- スペインの社会保障番号 (SSN) 
- スペインの納税者番号 
- SQL Server接続文字列 
- スウェーデンの運転免許証番号 
- スウェーデンの国民 ID 
- スウェーデンのパスポート番号 
- スウェーデンの納税者番号 
- SWIFT コード 
- スイスの社会保障番号 AHV 
- 台湾の国民 ID 
- 	台湾のパスポート番号 
- 台湾居住者証明書 (ARC/TARC) 
- タイの人口識別コード 
- トルコの国民識別番号 
- 英国の運転免許証番号 
- 英国の選挙登録番号 
- 英国の国民健康保険番号 
- 英国の国民保険番号 (NINO) 
- 英国 一意の納税者参照番号 
- 米国/英国のパスポート番号 
- 米国の銀行口座番号 
- 米国の運転免許証番号 
- 米国の個人納税者識別番号 (ITIN) 
- 米国の社会保障番号 (SSN) 
- ウクライナのパスポート番号 (国内) 
- ウクライナのパスポート番号 (国際) 
 
上記の機密情報の種類に加えて、カスタムの機密情報の種類も検出されます。

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a>Microsoft アプリ全体の DLP ポリシー ヒントのサポート マトリックス

|**アプリとプラットフォーム**|**DLP ポリシー ヒントのサポート**|**サポートされる機密情報の種類**|**サポートされる述語とアクション**|**コメント**|
|:--|:--|:--|:--|:--|
|**OutlookWeb アクセス**|:::image type="icon" source="../media/rightmrk.png" border="false":::|すべて|Subset|「 [データ損失防止ポリシー のヒントリファレンス」を参照してください。](#data-loss-prevention-policy-tips-reference)|
|**OutlookWin32 (Outlook 2013 以降)**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Subset|Subset|Outlook Win32 での DLP ポリシー ヒントの表示にサポートされる機密情報の種類と DLP の条件とアクションのサポートの詳細については[、「Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions)以降では、一部の条件と例外に関するポリシー ヒントの表示と[Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types)以降およびデスクトップ上の Office アプリのサポート」を参照してください。|
|**Outlookモバイル (iOS、Android)/Outlook Mac**|:::image type="icon" source="../media/crsmrk.png" border="false":::|なし|なし|DLP ポリシー のヒントは、モバイルではOutlookされません|
|**Sharepoint Online/One Drive for Business Web クライアント**|:::image type="icon" source="../media/rightmrk.png" border="false":::|すべて|DLP のすべての SPO/ODB 述語とアクション||
|**Sharepoint Win32/ One Drive for Business Win32 クライアント**|:::image type="icon" source="../media/crsmrk.png" border="false":::|なし|なし|SHAREpoint またはデスクトップ クライアント アプリでは DLP ポリシーのヒントOneDriveサポートされていません|
|**Word、Excel、PowerPoint Web クライアント**|:::image type="icon" source="../media/rightmrk.png" border="false":::|すべて|DLP のすべての SPO/ODB 述語とアクション|DLP ポリシー ヒントは、ドキュメントが SPO または ODB Web アプリでホストされ、DLP ポリシーが既にスタンプされている場合にサポートされます。|
|**Word、Excel、PowerPoint Mobile クライアント**|:::image type="icon" source="../media/crsmrk.png" border="false":::|なし|なし|DLP ポリシー のヒントは、モバイル アプリではサポートされていません。Office。|
|**TeamsWeb/ Teams デスクトップ/ Teams Mobile/ Teams Mac**|:::image type="icon" source="../media/rightmrk.png" border="false":::|すべて|DLP ポリシー Teams述語のすべて|ポリシー ヒントは、メッセージに "このメッセージのフラグが設定されています" というフラグが付けらた場合に表示されます。 何が可能ですか? リンクをクリックすると、ユーザーは検出された機密情報の種類を確認し、管理者が許可した場合に問題を上書きまたは報告できます。ファイルに関するポリシー ヒントは表示されません。 受信者がドキュメントにアクセスしようとすると、許可されていない場合にアクセスが拒否される可能性があります。|
|**Win32 Endpoint Devices**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Subset|DLP ポリシーのすべてのエンドポイント DLP 述語とアクション|「 [エンドポイントのデータ損失防止は、一部の機密情報の種類についてのみポリシー ヒントをサポートしています」を参照してください。](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)|
|**Mac デバイス**|:::image type="icon" source="../media/crsmrk.png" border="false":::|なし|なし|データ損失防止ポリシーは、今日の Mac デバイスでは適用できません|
|**サードパーティのクラウド アプリ**|:::image type="icon" source="../media/crsmrk.png" border="false":::|なし|なし|データ損失防止ポリシーのヒントは、サードパーティのクラウド アプリではサポートされていません|
|**On-prem**|:::image type="icon" source="../media/crsmrk.png" border="false":::|なし|なし||
|**Word、Excel、Win32 PowerPointクライアント**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Subset|Subset|サポートされる[機密情報Outlook一](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types)覧については、一部の機密情報の種類に関するポリシー ヒントのみを示すデスクトップ 上の Office アプリとデスクトップ 上の Office アプリのサポートを参照してください。</br></br>WXP クライアント アプリのポリシー ヒントは、以下または DLP ポリシー内の条件またはアクションのサブセットを正確に持つすべての DLP ポリシーについて、Sharepoint Online または One Drive for Business Sites に保存されているドキュメントで機能します。</br> <ul><li>コンテンツには機密情報の種類が含まれる</li><li>Access Scope (コンテンツは内部/外部で共有されます)</li><li>ユーザーに通知する (ポリシー ヒント/ユーザー通知)</li><li>すべてのユーザーをブロックする</li><li>インシデント レポート</li></ul></br> その他の条件やアクションが存在する場合、そのポリシーの DLP ポリシー ヒントは Word、Excel、または PowerPoint のデスクトップ アプリには表示されません。</br>詳細[については、「Excel、PowerPoint、Word のポリシー ヒント」](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word)を参照してください。|
||||||
