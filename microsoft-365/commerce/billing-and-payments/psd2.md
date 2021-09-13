---
title: 商用顧客向け Payment Services ディレクティブ 2 と強力な顧客認証
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jamitche, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
search.appverid: MET150
description: 2019 年 9 月 14 日現在、欧州経済地域の 31 か国の銀行は、支払いを処理する前に、オンライン購入を行う人物の身元を確認する必要があります。
keywords: payment services ディレクティブ 2、強力な顧客認証、多要素認証
ms.date: 11/03/2020
ms.openlocfilehash: bbbbe9f53c11fcae9c35cda1fd4e7d4b51a9c767
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59219144"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a>商用顧客向け Payment Services ディレクティブ 2 と強力な顧客認証

2019 年 9 月 14 日現在、欧州経済地域の 31 か国の銀行は、支払いを処理する前に、オンライン購入を行う人物の身元を確認する必要があります。 この検証では、オンライン購入の安全性と保護を確保するために多要素認証が必要です。 この検証要件の日付は、一部の国では遅れる予定です。

詳細については、「Payment Services ディレクティブ 2」および「強力な顧客認証」に関する Microsoft [FAQ を参照してください](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication)。

## <a name="when-is-multi-factor-authentication-required"></a>多要素認証が必要な場合

現在、多要素認証を使用したこのディレクティブの検証要件は、欧州経済地域の 31 か国の銀行のクレジット カードを使用しているお客様にのみ適用されます。 ユーザーが実行したアクションが理由でメッセージが表示される場合や、既存のサブスクリプションまたはサービスのイベントのためにメッセージが表示される場合があります。

### <a name="customer-actions"></a>顧客のアクション

銀行では、多要素認証による検証が必要な場合があります。 以下に例を挙げます。

- 新しいサブスクリプションにサインアップする
- サブスクリプションへのライセンスの追加
- サブスクリプションまたはサービスの支払いに使用するクレジット カードの追加または交換
- 請求プロファイルでのクレジット カードの追加または置き換え
- アプリの購入

### <a name="subscription-lifecycle-events"></a>サブスクリプション ライフサイクル イベント

定期的な支払いの料金が失敗する場合があります。 その場合は、フォローする指示が記載されたメールが届きます。 確認要求に応答し、現在の支払いを行うメッセージが表示されます。

## <a name="need-more-help"></a>ヘルプを表示

金融機関は、次のシナリオに最適な連絡先です。

- 確認コードを受け取りなかった。  
- 確認コードを送信した後、検証プロセスが機能しなかった。
- クレジット カードの連絡先情報が正しいかは不明です。
