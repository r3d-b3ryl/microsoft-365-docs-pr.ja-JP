---
title: 商用顧客向けの Payment Services ディレクティブ 2 と強力な顧客認証
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: jamitche, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_billing
- AdminSurgePortfolio
search.appverid: MET150
description: 2019 年 9 月 14 日の時点で、ヨーロッパ経済地域の 31 か国の銀行は、支払いを処理する前にオンライン購入を行っているユーザーの身元を確認する必要があります。
ms.date: 11/03/2020
ms.openlocfilehash: 72b0ab8c118d0fa94e3ced5fe2748a11247335ca
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63321111"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a>商用顧客向けの Payment Services ディレクティブ 2 と強力な顧客認証

2019 年 9 月 14 日の時点で、ヨーロッパ経済地域の 31 か国の銀行は、支払いを処理する前にオンライン購入を行っているユーザーの身元を確認する必要があります。 この検証では、オンライン購入の安全性と保護を確保するために多要素認証が必要です。 この検証要件の日付は、一部の国で延期されます。

詳細については、「 [Payment Services ディレクティブ 2 および強力な顧客認証に関する Microsoft FAQ」](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication)を参照してください。

## <a name="when-is-multi-factor-authentication-required"></a>多要素認証はいつ必要ですか?

現在、多要素認証を使用するこのディレクティブの検証要件は、ヨーロッパ経済地域の 31 か国の銀行のクレジット カードを使用する顧客にのみ適用されます。 実行したアクションが原因で顧客にメッセージが表示される場合があります。また、既存のサブスクリプションまたはサービスのイベントが原因でプロンプトが表示される場合があります。

### <a name="customer-actions"></a>顧客アクション

銀行では、多要素認証による検証が必要になる場合があります。 以下に例を挙げます。

- 新しいサブスクリプションにサインアップする
- サブスクリプションへのライセンスの追加
- サブスクリプションまたはサービスの支払いに使用されるクレジット カードを追加または置き換える
- 課金プロファイルでのクレジット カードの追加または置き換え
- アプリの購入

### <a name="subscription-lifecycle-events"></a>サブスクリプション ライフサイクル イベント

定期的な支払いの料金が失敗する可能性があります。 その場合は、従う手順が記載された電子メールが届きます。 確認要求に応答し、現在の支払いを行うよう求められます。

## <a name="need-more-help"></a>サポートが必要な場合

金融機関は、次のシナリオに最適な連絡先です。

- 確認コードが届きませんでした。  
- 確認コードを送信した後、検証プロセスが機能しませんでした。
- クレジット カードの連絡先情報が正しいかどうかは不明です。
