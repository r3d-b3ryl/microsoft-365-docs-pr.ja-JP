---
title: 一般法人向けお客様向けのお支払いサービス指令2および強力な顧客認証
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: 2019年9月14日以降に、欧州経済地域の31国の銀行は、支払いを処理する前にオンライン購入を行うユーザーの身元を確認する必要があります。
keywords: 支払いサービスディレクティブ2、強力な顧客認証、多要素認証
ms.openlocfilehash: f59808d3735f10b57ed5c0cd279b6703b24a44a4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594708"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a>一般法人向けお客様向けのお支払いサービス指令2および強力な顧客認証

2019年9月14日以降に、欧州経済地域の31国の銀行は、支払いを処理する前にオンライン購入を行うユーザーの身元を確認する必要があります。 この検証では、オンライン購入が安全で保護されていることを確認するために、多要素認証が必要になります。 この検証要件の日付は、一部の国では遅延されます。 

詳細については、「Microsoft FAQ」を参照してください。[支払いサービスディレクティブ2と強力な顧客認証について説明](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication)します。

## <a name="when-is-multi-factor-authentication-required"></a>多要素認証が必要になるのはいつですか?

現時点では、多要素認証を使用したこのディレクティブの検証要件は、欧州経済地域の31か国の銀行のクレジットカードを使用しているお客様にのみ適用されます。 場合によっては、ユーザーが実行したアクションのためにユーザーにメッセージが表示され、既存のサブスクリプションまたはサービスに対するイベントによってメッセージが表示されることがあります。

### <a name="customer-actions"></a>顧客のアクション

銀行が多要素認証を使用して検証する必要がある場合があります。 次に例を示します。
- 新しいサブスクリプションにサインアップする
- サブスクリプションにライセンスを追加する
- サブスクリプションまたはサービスの支払いに使用するクレジットカードを追加または置換する
- 課金プロファイルのクレジットカードを追加または置換する
- アプリの購入

### <a name="subscription-lifecycle-events"></a>サブスクリプションライフサイクルイベント

定期的な支払いに対する請求は失敗する可能性があります。 その場合は、手順に従って電子メールを受信します。 確認要求に応答して、現在の支払いを行うように求めるメッセージが表示されます。

## <a name="need-more-help"></a>サポートが必要な場合

これらのシナリオでは、金融機関が最適な連絡先です。
- 確認コードを受信していません。  
- 検証コードを送信した後、検証プロセスが正常に実行されませんでした。
- クレジットカードの連絡先情報が正しいかどうかがわからない。