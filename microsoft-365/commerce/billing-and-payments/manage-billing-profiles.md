---
title: 課金プロファイルを理解する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
- AdminTemplateSet
search.appverid: MET150
description: 請求プロファイルが請求書をサポートする方法について学習します。
ms.date: 04/02/2021
ms.openlocfilehash: 8407e3855a8e497c730925a424b999ed07da6228
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60188555"
---
# <a name="understand-billing-profiles"></a>課金プロファイルを理解する

請求プロファイルには、支払い方法、請求先情報、その他の請求書設定 (発注書番号、電子メール請求書の設定など) が含まれる。 請求プロファイルを使用して、Microsoft から購入した製品の支払いを行います。 課金プロファイルは、ユーザーがセルフサービス購入を行う際に自動的に作成されます。 各請求プロファイルは個別に請求されます。

> [!NOTE]
>
> 請求プロファイルは、製品とサービスを購入する顧客は、Microsoft.com の [サービスの購入] ページではMicrosoft 365 管理センター。

## <a name="what-are-billing-profile-roles"></a>課金プロファイルの役割とは

課金プロファイルのロールには、購入を制御し、請求書を表示および管理するためのアクセス許可があります。 これらの役割を、請求書の追跡、整理、支払いを行うユーザーに割り当てます。 たとえば、組織内の調達チームのメンバーです。

| 役割                         | 説明                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| 課金プロファイルの所有者        | 課金プロファイルに関するすべてを管理する                                          |
| 課金プロファイル投稿者  | 課金プロファイルのアクセス許可を除くすべてを管理する                        |
| 課金プロファイル リーダー       | 課金プロファイル内のすべてのデータの読み取り専用ビュー                                |
| 請求書マネージャー              | 請求書の表示と支払い、および請求プロファイル内のすべての情報の読み取り専用ビュー  |

## <a name="view-my-billing-profiles"></a>請求プロファイルを表示する

> [!NOTE]
>
> これらの手順に従い、請求プロファイルの一覧が空の場合は、請求プロファイルを持たなかったり、この機能を使用できないという意味です。

1. 管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">請求と支払い</a>] ページの順に移動します。
2. [請求プロファイル **] タブを** 選択し、一覧から請求プロファイルを選択します。

各請求プロファイルには、次の情報が含まれます。

- **課金プロファイルの名前と状態** &ndash; 請求プロファイルの一意の名前と、課金プロファイルが購入に対してアクティブか無効かを指定します。
- **請求書の設定** &ndash; 請求先アカウントの国に基づく通貨、請求書の頻度と日付に関する情報、電子メールの添付ファイルとして請求書を受信するオプション、およびオプションの PO 番号フィールド
- **支払い方法** &ndash; プロファイルのプライマリ支払い方法とバックアップ支払い方法がある場合は、その支払い方法を表示します。
- **課金アカウント** &ndash; プロファイルが関連付けされている請求先アカウントの名前。 課金アカウントの詳細については、「請求アカウントについて [」を参照してください](../manage-billing-accounts.md)。
- **連絡先情報** &ndash; 請求先住所と連絡先名と電子メール アドレス
- **課金プロファイルの役割** &ndash; そのプロファイルの処理を行う請求プロファイル の役割の 1 つが割り当てられているユーザーの一覧。 たとえば、請求書の支払い、PO 番号の追加、または購入に使用される支払い方法の置換を行います。

> [!NOTE]
>
> 請求プロファイルの役割は、組織内のユーザーにのみ割り当てることができます。

## <a name="need-help-contact-support"></a>お困りの際は、 サポートにお問い合せください

Azure の料金に関する質問やサポートが必要な場合は、Azure サポートを <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">使用してサポート 要求を作成します</a>。

請求プロファイルに関する質問やサポートが必要な場合はMicrosoft 365 管理センター[サポートにお問い合わせください](../../business-video/get-help-support.md)。

## <a name="related-content"></a>関連コンテンツ

[課金プロファイルを使用してサブスクリプションの支払い](pay-for-subscription-billing-profile.md) 方法 (記事)\
[請求先アカウント](../manage-billing-accounts.md) について (記事)\
[支払い方法の管理](manage-payment-methods.md) (記事)
