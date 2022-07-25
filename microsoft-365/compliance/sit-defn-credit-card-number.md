---
title: クレジット カード番号エンティティ定義
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: クレジット カード番号の機密情報の種類エンティティ定義。
ms.openlocfilehash: 0d75c0af6c67c1d617db9f7f28fbc63c27e4d05a
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2022
ms.locfileid: "66996052"
---
# <a name="credit-card-number"></a>クレジット カード番号

## <a name="format"></a>フォーマット

書式設定または書式設定解除が可能な 14 ~ 19 桁の数字 (dddd) で、Luhn テストに合格する必要があります。

## <a name="pattern"></a>パターン

Visa、MasterCard、Discover Card、JCB、American Express、ギフト カード、ダイナーカード、Rupay、China UnionPay など、世界中のすべての主要ブランドのカードを検出します。

## <a name="checksum"></a>チェックサム

はい。Luhn チェック

## <a name="definition"></a>定義

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという高い信頼を持っています。

- 関数 `Func_credit_card` がパターンに一致するコンテンツを検出した。
- 次のいずれかの条件が当てはまります。
  - `Keyword_cc_verification` のキーワードを検出した。
  - `Keyword_cc_name` のキーワードを検出した。
  - 関数 `Func_expiration_date` は、適切な日付形式で日付を検索します。
- チェックサムが渡される。

DLP ポリシーは、300 文字の近くにある場合に、この種類の機密情報が検出されたという信頼度が低くなります。

- 関数 `Func_credit_card` がパターンに一致するコンテンツを検出した。
- チェックサムが渡される。

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

## <a name="keywords"></a>キーワード

### <a name="keyword_cc_verification"></a>Keyword_cc_verification

- card verification
- card identification number
- Cvn
- cid
- cvc2
- cvv2
- pin block
- security code
- security number
- security no
- issue number
- issue no
- cryptogramme
- numéro de sécurité
- numero de securite
- kreditkartenprüfnummer
- kreditkartenprufnummer
- prüfziffer
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- タラ。 sicurezza
- cod sicurezza
- n autorizzazione
- código
- codigo
- タラ。 ワンセグ
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- cód. segurança
- タラ。 seguranca
- タラ。 segurança
- cód. seguranca
- cód segurança
- cod seguranca
- cod segurança
- cód seguranca
- número de verificação
- numero de verificacao
- ablauf
- gültig bis
- gültigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadenza
- data scad
- fecha de expiracion
- fecha de venc
- vencimiento
- válido hasta
- valido hasta
- vto
- data de expiração
- data de expiracao
- data em que expira
- validade
- 勇気
- vencimento
- トランザクション
- トランザクション番号
- 参照番号
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

### <a name="keyword_cc_name"></a>Keyword_cc_name

- アメックス
- american express
- americanexpress
- americano espresso
- ビザ
- マスター
- master card
- Mc
- mastercards
- master cards
- diner's Club
- diners club
- dinersclub
- 発見
- discover card
- discovercard
- discover cards
- JCB
- BrandSmart
- japanese card bureau
- carte blanche
- carteblanche
- credit card
- Cc#
- cc#:

- expiration date
- exp date
- expiry date
- date d'expiration
- date d'exp
- date expiration
- bank card
- bankcard
- card number
- card num
- cardnumber
- cardnumbers
- card numbers
- creditcard
- credit cards
- クレジット カード
- Ccn
- card holder
- カード
- card holders
- 会員
- check card
- checkcard
- check cards
- checkcards
- debit card
- デビットカード
- debit cards
- デビットカード
- atm card
- atmcard
- atm cards
- atmcards
- 途中
- en route
- card type
- Cardmember Acct
- cardmember アカウント
- Cardno
- 企業カード
- 企業カード
- カードの種類
- カード アカウント番号
- カード メンバー アカウント
- Cardmember Acct.
- card no.
- card no
- card number
- carte bancaire
- carte de crédit
- carte de credit
- numéro de carte
- numero de carte
- nº de la carte
- nº de carte
- kreditkarte
- karte
- kartenハバー
- kartenってberbers
- kreditkartenハバー
- kreditkarteninstitut
- kreditkartentyp
- eigentümername
- kartennr
- kartennummer
- kreditkartennummer
- kreditkarten-nummer
- carta di credito
- carta credito
- N。 carta
- n carta
- Nr。 carta
- nr carta
- numero carta
- numero della carta
- numero di carta
- tarjeta credito
- tarjeta de credito
- tarjeta crédito
- tarjeta de crédito
- tarjeta de atm
- tarjeta atm
- tarjeta debito
- tarjeta de debito
- tarjeta débito
- tarjeta de débito
- nº de tarjeta
- いいえ。 de tarjeta
- no de tarjeta
- numero de tarjeta
- número de tarjeta
- tarjeta no
- tarjetahabiente
- cartão de crédito
- cartão de credito
- cartao de crédito
- cartao de credito
- cartão de débito
- cartao de débito
- cartão de debito
- cartao de debito
- débito automático
- debito automatico
- número do cartão
- numero do cartão
- número do cartao
- numero do cartao
- número de cartão
- numero de cartão
- número de cartao
- numero de cartao
- nº do cartão
- nº do cartao
- nº。 do cartão
- no do cartão
- no do cartao
- いいえ。 do cartão
- いいえ。 do cartao
- rupay
- ユニオンの支払い
- unionpay
- diner's
- ダイナー
- クレジットカード番号
- クレジットカードナンバー
- クレジットカード＃
- クレジットカード
- クレジット
- クレカ
- カード番号
- カードナンバー
- カード＃
- アメックス
- アメリカンエクスプレス
- アメリカン エクスプレス
- Visa カード
- Visa カード
- マスターカード
- マスター カード
- マスター
- ダイナースクラブ
- ダイナース クラブ
- ダイナース
- 有効期限
- 期限
- キャッシュカード
- キャッシュ カード
- カード名義人
- カードの名義人
- カードの名義
- デビット カード
- デビットカード
- 中国银联
- 银联