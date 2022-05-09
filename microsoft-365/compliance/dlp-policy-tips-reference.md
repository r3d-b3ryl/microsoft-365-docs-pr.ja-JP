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
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
recommendations: false
description: データ損失防止 (DLP) ポリシーにポリシー ヒントを追加して、DLP ポリシーと競合するコンテンツを操作していることをユーザーに通知する方法について説明します。
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: f9702916831839ac384cd262854fd0a88f90a8ea
ms.sourcegitcommit: e911dd506ea066795e418daf7b84c1e11381a21c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64953663"
---
# <a name="data-loss-prevention-policy-tips-reference"></a>データ損失防止ポリシーヒントのリファレンス

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Outlook Web Access の DLP ポリシーヒントは、DLP ポリシーのExchangeワークロードに適用されるすべての条件、例外、およびアクションに対してサポートされています。次を除きます。

**条件：**

- 受信者が次のメンバーの場合
- ヘッダーに単語または語句が含まれている
- ヘッダーがパターンと一致している
- メッセージの種類は次の形式です。
- コンテンツ文字セットに単語が含まれている
- 送信者がポリシー ヒントをオーバーライドしました
- メッセージ サイズが等しいか、またはそれより大きい
- Sender AD 属性に単語または語句が含まれている
- Sender AD 属性がパターンと一致する
- 送信者 IP 範囲
- Recipient AD 属性に単語または語句が含まれている
- 受信者 AD 属性がパターンと一致する
- ドキュメント名に単語または語句が含まれている
- ドキュメント名がパターンと一致する
- ドキュメント コンテンツに単語または語句が含まれている
- ドキュメント コンテンツがパターンと一致する

**アクション：**

- 送信者のマネージャーに承認メッセージを転送する
- 承認メッセージを特定の承認者に転送する
- 特定のユーザーにメッセージをリダイレクトする
- 宛先ボックスに受信者を追加する
- Cc ボックスに受信者を追加する
- Bcc Box に受信者を追加する
- 送信者のマネージャーを受信者として追加する
- HTML 免責事項を追加する
- メール件名の先頭に追加する
- O365 メッセージの暗号化と権利保護を削除する

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a>Outlook 2013 以降では、一部の条件と例外についてのみポリシーヒントを表示できます

現在、Outlook 2013 以降では、以下の条件と対応する例外を除き、条件や例外を含まないポリシーのポリシー ヒントの表示がサポートされています。

- コンテンツに含まれるもの (機密情報の種類に対してのみ機能します。 秘密度ラベルはサポートされていません)
- コンテンツが共有されている

すべての条件は、Outlook クライアント アプリで作成された電子メールに対して機能し、コンテンツと一致し、コンテンツに対して保護アクションが適用されることに注意してください。 ただし、上記以外の条件では、ユーザーにポリシーヒントを表示することはサポートされていません。

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a>Outlook 2013 以降およびデスクトップ上のOffice アプリでは、一部の機密情報の種類についてのみポリシーヒントを示すサポート

Desktop (2013 以降) のOutlookとデスクトップ上のOffice アプリ (Word、Excel、PowerPoint) で DLP ポリシーのヒントを表示するために検出される、既定の機密情報の種類の一覧は次のとおりです。

- ABA ルーティング番号
- アルゼンチンの国民識別 (DNI) 番号
- オーストラリアの銀行口座番号
- オーストラリアの医療口座番号
- オーストラリアのパスポート番号
- オーストラリアの納税者番号
- Azure DocumentDB 認証キー  
- Azure IAAS データベース接続文字列とAzure SQL接続文字列  
- Azure IoT接続文字列  
- Azure Publish Setting Password  
- Azure Redis Cache 接続文字列  
- Azure SAS  
- Azure Service Bus接続文字列  
- Azure Storage アカウント キー  
- Azure Storage アカウント キー (汎用)  
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
- EU 税識別番号 (TIN)  
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
- 国際分類の病気 (ICD-9-CM)  
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
- 日本の居住カード番号
- マレーシア ID カード番号
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
- トルコ国民識別番号
- 英国の運転免許証番号
- 英国の選挙登録番号
- 英国の国民健康保険番号
- 英国の国民保険番号 (NINO)
- 米国/英国のパスポート番号
- 米国の銀行口座番号
- 米国の運転免許証番号
- 米国の個人納税者識別番号 (ITIN)
- 米国の社会保障番号 (SSN)

カスタムの機密情報の種類は、上記のすぐに使用できる機密情報の種類に加えて、DLP ポリシーのヒントでもサポートされることに注意してください。

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a>エンドポイント デバイスのデータ損失防止では、一部の機密情報の種類についてのみポリシー ヒントがサポートされます

エンドポイント デバイスに存在するドキュメントで検出される、すぐに使用できる機密情報の種類の一覧は次のとおりです。

- ABA ルーティング番号 
- アルゼンチンの国民識別 (DNI) 番号 
- オーストラリアの銀行口座番号 
- オーストラリアの医療口座番号 
- オーストラリアのパスポート番号 
- オーストラリアの納税者番号 
- オーストラリアのビジネス番号 
- オーストラリアの会社番号 
- オーストリアの運転免許証番号 
- オーストリア ID カード 
- オーストリアのパスポート番号 
- オーストリア社会保障番号 
- オーストリアの税識別番号 
- オーストリア付加価値税 (VAT) 番号 
- Azure DocumentDB 認証キー 
- Azure IAAS データベース接続文字列とAzure SQL接続文字列 
- Azure IoT接続文字列 
- Azure Publish Setting Password 
- Azure Redis Cache 接続文字列 
- Azure SAS 
- Azure Service Bus接続文字列 
- Azure Storage アカウント キー 
- Azure Storage アカウント キー (汎用) 
- ベルギーの運転免許証番号 
- ベルギーの国民番号 
- ベルギーのパスポート番号 
- ベルギー付加価値税番号 
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
- クロアチアの運転免許証番号 
- クロアチアの身分証明書番号 
- クロアチア国民 ID カード番号 
- クロアチアのパスポート番号 
- クロアチアの個人識別 (OIB) 番号 
- CSCAN-AZURE0060 Azure Storage アカウント共有アクセス署名 
- CSCAN-GENERAL0140 General Symmetric Key 
- キプロスの運転免許証番号 
- キプロス ID カード 
- キプロスパスポート番号 
- キプロス税識別番号 
- チェコの運転免許証番号 
- チェコの個人 ID 番号 
- チェコ共和国のパスポート番号 
- デンマークの運転免許証番号 
- デンマークのパスポート番号 
- デンマークの個人識別番号 
- 麻薬取締局 (DEA) 番号 
- エストニアの運転免許証番号 
- エストニアのパスポート番号 
- エストニアの個人識別コード 
- 欧州連合のデビット カード番号 
- EU の運転免許証番号 
- EU の国民識別番号 
- EU パスポート番号 
- EU 社会保障番号 (SSN) または同等の ID 
- EU 税識別番号 (TIN) 
- フィンランドの運転免許証番号 
- フィンランド - ヨーロッパの医療保険番号 
- フィンランドの国民 ID 
- フィンランドのパスポート番号 
- フランスの運転免許証番号 
- フランスの健康保険番号 
- フランスの国民識別カード (CNI) 
- フランスのパスポート番号 
- フランスの社会保障番号 (INSEE) 
- フランス税識別番号 (numéro SPI.) 
- フランス付加価値税番号 
- ドイツの運転免許証番号 
- ドイツのパスポート番号 
- ドイツの身分証明書番号 
- ドイツの税識別番号 
- ドイツ付加価値税番号 
- ギリシャ の運転免許証番号 
- ギリシャの国民識別カード 
- ギリシャパスポート番号 
- ギリシャ社会保障番号 (AMKA) 
- ギリシャ語税識別番号 
- 香港の ID カード (HKID) 番号 
- ハンガリー社会保障番号 (TAJ) 
- ハンガリー語の付加価値税番号 
- ハンガリーの運転免許証番号 
- ハンガリーのパスポート番号 
- ハンガリーの個人識別番号 
- ハンガリー税識別番号 
- インドの永久口座番号 (PAN) 
- インドの固有識別 (Aadhaar) 番号 
- インドネシアの身分証明書 (KTP) 番号 
- 国際銀行口座番号 (IBAN) 
- 国際分類の病気 (ICD-10-CM) 
- 国際分類の病気 (ICD-9-CM) 
- IP アドレス 
- アイルランドの運転免許証番号 
- アイルランドのパスポート番号 
- アイルランドの個人公共サービス (PPS) 番号 
- イスラエルの銀行口座番号 
- イスラエルの国民 ID 
- イタリアの運転免許証番号 
- イタリア会計コード 
- イタリア のパスポート番号 
- イタリア 付加価値税番号 
- 日本の銀行口座番号 
- 日本の運転免許証番号 
- 日本のパスポート番号 
- 日本の住民登録番号 
- 日本の社会保険番号 (SIN) 
- 日本語マイナンバー企業 
- 日本語 My Number Personal 
- 日本の居住カード番号 
- ラトビアの運転免許証番号 
- ラトビアパスポート番号 
- ラトビアの個人コード 
- リトアニアの運転免許証番号 
- リトアニアパスポート番号 
- リトアニアの個人コード 
- Luxemburg ドライバーのライセンス番号 
- Luxemburg 国民識別番号 (自然人) 
- Luxemburg 国民識別番号 (非自然人) 
- Luxemburg Passport Number 
- マレーシア ID カード番号 
- マルタ運転免許証番号 
- マルタ ID カード番号 
- マルタパスポート番号 
- マルタ税 ID 番号 
- オランダの市民サービス (BSN) 番号 
- オランダの運転免許証番号 
- オランダのパスポート番号 
- オランダの税識別番号 
- オランダ付加価値税番号 
- ニュージーランドの銀行口座番号 
- ニュージーランドの運転免許証番号 
- ニュージーランド内陸部収益番号 
- ニュージーランドの保健省番号 
- ニュージーランド社会保障番号 
- ノルウェーの識別番号 
- フィリピンの汎用多目的 ID 番号 
- ポーランドの運転免許証番号 
- ポーランドの ID カード 
- ポーランドの国民 ID (PESEL) 
- ポーランドのパスポート 
- ポーランドの納税者番号 
- ポーランド語 REGON 番号 
- ポルトガルの市民カード番号 
- ポルトガルの運転免許証番号 
- ポルトガルパスポート番号 
- ポルトガルの税識別番号 
- ルーマニアの運転免許証番号 
- ルーマニアパスポート番号 
- ルーマニア個人用数値コード (CNP) 
- ロシアパスポート番号 (国内) 
- ロシアパスポート番号 (国際) 
- サウジアラビアの国民 ID 
- シンガポールの国民登録 ID カード (NRIC) 番号 
- スロバキアの運転免許証番号 
- スロバキアパスポート番号 
- スロバキアの個人番号 
- スロベニアの運転免許証番号 
- スロベニアのパスポート番号 
- スロベニアの納税者番号 
- スロベニア 固有のマスター 市民番号 
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
- スウェーデンの税識別番号 
- SWIFT コード 
- スイス社会保障番号 AHV 
- 台湾の国民 ID 
- 	台湾のパスポート番号 
- 台湾居住者証明書 (ARC/TARC) 
- タイの人口識別コード 
- トルコ国民識別番号 
- 英国の運転免許証番号 
- 英国の選挙登録番号 
- 英国の国民健康保険番号 
- 英国の国民保険番号 (NINO) 
- 英国。 一意の納税者番号 
- 米国/英国のパスポート番号 
- 米国の銀行口座番号 
- 米国の運転免許証番号 
- 米国の個人納税者識別番号 (ITIN) 
- 米国の社会保障番号 (SSN) 
- ウクライナパスポート番号 (国内) 
- ウクライナパスポート番号 (国際) 
 
上記の機密情報の種類に加えて、カスタムの機密情報の種類も検出されることに注意してください

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a>Microsoft アプリ全体の DLP ポリシーヒントのサポート マトリックス

|**アプリとプラットフォーム**|**DLP ポリシー ヒントのサポート**|**サポートされている機密情報の種類**|**サポートされている述語とアクション**|**コメント**|
|:--|:--|:--|:--|:--|
|**Outlook On the Web**|:::image type="icon" source="../media/rightmrk.png" border="false":::|すべて|サブセット||
|**Outlook Win32 (ver. 2105 build 14026.20000 および半期チャネル ver. 2102 build 13801.20862)**|:::image type="icon" source="../media/rightmrk.png" border="false":::|サブセット|サブセット|[Outlook 2013 以降では、一部の条件と例外についてのみポリシー ヒントを表示](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions)できます。[また、2013 以降のOutlook 2013 以降 Officeのアプリと、機密情報の種類のサポートの詳細については、一部の機密情報の種類についてのみポリシー ヒント](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types)と、Outlookに対する DLP ポリシーのヒントを表示するためにサポートされるアクションを示すポリシー ヒントがサポートされています。 Win32。|
|**Outlook Mobile (iOS、Android)/Outlook Mac**|:::image type="icon" source="../media/crsmrk.png" border="false":::|none|none|DLP ポリシーのヒントは、Outlook モバイルではサポートされていません|
|**SharePoint Online/OneDrive for Business Web クライアント**|:::image type="icon" source="../media/rightmrk.png" border="false":::|すべて|DLP のすべての SPO/ODB 述語とアクション||
|**SharePoint Win32/ OneDrive for Business Win32 クライアント**|:::image type="icon" source="../media/crsmrk.png" border="false":::|none|none|DLP ポリシーのヒントは、デスクトップ クライアント アプリSharePointまたはOneDriveではサポートされていません|
|**Word、Excel、PowerPoint Web クライアント**|:::image type="icon" source="../media/rightmrk.png" border="false":::|すべて|DLP のすべての SPO/ODB 述語とアクション|ドキュメントが SPO または ODB Web アプリでホストされていて、DLP ポリシーが既にスタンプされている場合は、DLP ポリシー ヒントがサポートされます。|
|**Word、Excel、PowerPoint Mobile クライアント**|:::image type="icon" source="../media/crsmrk.png" border="false":::|none|none|Office用のモバイル アプリでは、DLP ポリシーのヒントはサポートされていません。|
|**Teams Web/Teams Desktop/Teams Mobile/Teams Mac**|:::image type="icon" source="../media/rightmrk.png" border="false":::|すべて|DLP ポリシーのすべてのTeams述語|ポリシーヒントは、メッセージに "このメッセージにフラグが設定されました。 何ができますか? リンクをクリックすると、ユーザーは検出された機密情報の種類を確認し、管理者が許可した場合に問題をオーバーライドまたは報告できます。ファイルに対するポリシー ヒントは表示されません。 受信者がドキュメントにアクセスしようとすると、許可されていない場合はアクセスが拒否される可能性があります。|
|**Win32 エンドポイント デバイス**|:::image type="icon" source="../media/rightmrk.png" border="false":::|サブセット|DLP ポリシー内のすべてのエンドポイント DLP 述語とアクション|[エンドポイントでのデータ損失防止で、一部の機密情報の種類についてのみポリシー ヒントをサポートする方法に関する説明を](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)参照してください|
|**macOS デバイス**|既定のヒントのみ|すべて|サブセット|データ損失防止ポリシーは、macOS デバイスで適用できます。 カスタム ポリシーのヒントはサポートされていません。|
|**サード パーティのクラウド アプリ**|:::image type="icon" source="../media/crsmrk.png" border="false":::|none|none|データ損失防止ポリシーのヒントは、サード パーティのクラウド アプリではサポートされていません|
|**On-prem**|:::image type="icon" source="../media/crsmrk.png" border="false":::|none|none||
|**Word、Excel、PowerPoint Win32 クライアント**|:::image type="icon" source="../media/crsmrk.png" border="false":::|サブセット|サブセット|[2013 以降Outlookを参照してください。デスクトップ のアプリのサポートOffice、サポートされている機密情報の種類の一覧の機密情報の種類についてのみポリシーヒントを示してください](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types)</br></br>WXP クライアント アプリのポリシー ヒントは、DLP ポリシー内の条件またはアクションの正確な下またはサブセットを持つすべての DLP ポリシーの SharePoint Online または OneDrive for Business サイトに保存されているドキュメントに対して機能します。</br> <ul><li>コンテンツには機密情報の種類が含まれています</li><li>アクセス スコープ (コンテンツは内部または外部で共有されます)</li><li>ユーザーに通知する (ポリシーヒント/ユーザー通知)</li><li>すべてのユーザーをブロックする</li><li>インシデント レポート</li></ul></br> その他の条件またはアクションが存在する場合、そのポリシーの DLP ポリシー ヒントは、Word、Excel、またはPowerPointのデスクトップ アプリには表示されません。</br>詳細については、「[Excel、PowerPoint、Word のポリシーのヒント](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word)」を参照してください。|
||||||
