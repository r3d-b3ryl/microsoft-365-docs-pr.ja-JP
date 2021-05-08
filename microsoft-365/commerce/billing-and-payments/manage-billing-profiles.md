---
title: 課金プロファイルを理解する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
- PPM_jmueller
search.appverid: MET150
description: 請求プロファイルが請求書をサポートする方法について学習します。
ms.date: 04/02/2021
ms.openlocfilehash: 57786df370246c2b4fda556a9c48eb828db1cb4f
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52280789"
---
# <a name="understand-billing-profiles"></a>課金プロファイルを理解する

Microsoft から製品やサービスを購入する商用顧客の場合、請求プロファイルを使用すると、請求書に含まれるアイテムと請求書の支払い方法をカスタマイズできます。

課金プロファイルには、次の情報が含まれます。

- **課金アカウント** &ndash; プロファイルが関連付けされている請求先アカウントの名前
- **支払い方法** &ndash; クレジット カードまたはデビット カード、銀行口座、チェック、または電信送金
- **連絡先情報** &ndash; 請求先住所と連絡先名
- **請求書の設定** &ndash; 請求先アカウントの国、オプションの PO 番号、および電子メールの添付ファイルとして請求書を受け取るオプションに基づく通貨
- **アクセス許可** &ndash; 請求プロファイルの変更、請求書の支払い、または請求プロファイルの支払い方法を使用して購入を行う権限

課金プロファイルを使用して、購入を制御し、請求書をカスタマイズします。 請求プロファイルを使用して購入した製品に対して、月次請求書が生成されます。 発注書番号の更新や電子メールの請求書の設定など、請求書をカスタマイズできます。

最初の購入時に、請求アカウントの請求プロファイルが自動的に作成されます。 [請求プロファイル] ページで請求プロファイルを <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">作成して</a> 、より多くの請求書を設定できます。 たとえば、組織内の各部門に対して購入を行う際に、異なる請求プロファイルを使用できます。 次の請求日に、請求プロファイルごとに請求書を受け取る予定です。

## <a name="billing-profile-roles"></a>課金プロファイルの役割

課金プロファイルのロールには、購入を制御し、請求書を表示および管理するためのアクセス許可があります。 組織内の調達チームのメンバーなど、請求書を追跡、整理、支払うユーザーにこれらの役割を割り当てます。

| Role                         | 説明                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| 課金プロファイルの所有者        | 課金プロファイルに関するすべてを管理する                                          |
| 課金プロファイル投稿者  | 課金プロファイルのアクセス許可を除くすべてを管理する                        |
| 課金プロファイル リーダー       | 課金プロファイル内のすべてのデータの読み取り専用ビュー                                |
| 請求書マネージャー              | 請求書の表示と支払い、および請求プロファイル内のすべての情報の読み取り専用ビュー  |

## <a name="view-billing-profiles"></a>請求プロファイルの表示

1. 管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">請求と支払い</a>] ページの順に移動します。
2. [ **課金プロファイル] を** 選択し、一覧から請求プロファイルを選択します。

    - [概要 **] タブ** で、請求プロファイルの詳細を編集し、電子メールによる請求書の送信をオンまたはオフにできます。
    - [アクセス許可 **] タブ** で、請求書を支払う役割をユーザーに割り当てることができます。
    - [Azure クレジット **残高] タブ** で、Azure のお客様は、その請求プロファイルで使用される Azure クレジットのトランザクション残高履歴を確認できます。
    - Azure の **[クレジット] タブ** で、Azure のお客様は、その請求プロファイルに関連付けられている Azure クレジットの一覧と有効期限を確認できます。

    > [!NOTE]
    > Azure クレジットを持ってない場合は、[Azure クレジット残高] タブまたは **[Azure** クレジット] **タブは表示** されません。

## <a name="need-help-contact-support"></a>サポートが必要な場合 サポートに連絡する

Azure の料金に関する質問やサポートが必要な場合は、Azure サポートを <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">使用してサポート 要求を作成します</a>。

管理センターで請求プロファイルに関する質問やサポートが必要なMicrosoft 365、ビジネス製品の[サポートにお問い合わせください](../../business-video/get-help-support.md)。
