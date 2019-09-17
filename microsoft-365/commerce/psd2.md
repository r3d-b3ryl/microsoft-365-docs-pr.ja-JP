---
title: 一般法人向けお客様向けのお支払いサービス指令2および強力な顧客認証
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration <!-- need to figure out what this value should be -->
localization_priority: Normal
ms.collection:
- commerce <!-- probably need to change this -->
ms.custom: ''
search.appverid:
- MET150
description: 2019年9月14日以降に、欧州経済地域の31国の銀行は、支払いを処理する前にオンライン購入を行うユーザーの身元を確認する必要があります。
keywords: 支払いサービスディレクティブ2、強力な顧客認証、多要素認証
ms.openlocfilehash: c5047198a87b895a9e4cb7ffd0fb438980ee2d6c
ms.sourcegitcommit: a7edd3840226e67e82126bb9dee423b3458fef4d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2019
ms.locfileid: "36994068"
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