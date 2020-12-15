---
title: 課金プロファイルについて
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
- Commerce
search.appverid:
- MET150
description: 請求プロファイルが請求書をサポートする方法について学習します。
ms.openlocfilehash: 708096b624caa9c23a40df4842ccfce856db048d
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667779"
---
# <a name="understand-billing-profiles"></a>課金プロファイルについて

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更されました。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。

::: moniker-end

Microsoft から製品やサービスを購入する商用のお客様の場合、課金プロファイルを使用すると、請求書に含めるアイテムや請求書の支払い方法をカスタマイズできます。

課金プロファイルには、次の情報が含まれます。

- **課金アカウント** &ndash; プロファイルが関連付けされている請求アカウントの名前
- **支払い方法** &ndash; クレジット カードまたはデビット カード、銀行口座、チェック、または電信送金
- **連絡先情報** &ndash; 請求先住所と連絡先名
- **請求書の設定** &ndash; 請求アカウントの国、オプションの PO 番号、および電子メールの添付ファイルとして請求書を受信するオプションに基づく通貨
- **アクセス許可** &ndash; 請求プロファイルの変更、請求書の支払い、または請求プロファイルの支払い方法を使用して購入を行えるアクセス許可

課金プロファイルを使用して購入を制御し、請求書をカスタマイズします。 請求プロファイルで購入した製品に対して月次請求書が生成されます。 発注書番号や電子メールの請求書の設定の更新など、請求書をカスタマイズできます。

最初の購入時に、請求アカウントの請求プロファイルが自動的に作成されます。 [課金プロファイル] ページで請求プロファイル <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">を作成</a> し、さらに請求書を設定できます。 たとえば、組織内の部署ごとに購入を行う場合は、異なる請求プロファイルを使用できます。 次回の請求日に、請求プロファイルごとに請求書が届く予定です。

## <a name="billing-profile-roles"></a>課金プロファイル ロール

課金プロファイルのロールには、購入を制御し、請求書を表示および管理するためのアクセス許可があります。 組織内の調達チームのメンバーなど、請求書を追跡、整理、支払うユーザーに、これらの役割を割り当てます。

| 役割                          | 説明                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| 課金プロファイルの所有者         | 課金プロファイルのすべてを管理する                                           |
| 課金プロファイル投稿者   | 課金プロファイルのアクセス許可以外のすべてを管理する                         |
| 課金プロファイル閲覧者        | 課金プロファイル内のすべてのデータの読み取り専用ビュー                                 |
| 請求書マネージャー               | 課金プロファイル内のすべての情報を読み取り専用で表示し、請求書を表示および支払う   |

## <a name="view-billing-profiles"></a>課金プロファイルの表示

1. 管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">請求と支払い</a>] ページの順に移動します。

2. [ **課金プロファイル] を** 選択し、一覧から請求プロファイルを選択します。

    - [概要 **] タブ** では、請求プロファイルの詳細を編集し、電子メールによる請求書の送信をオンまたはオフにできます。

    - [アクセス許可 **] タブでは** 、請求書を支払う役割をユーザーに割り当てることができます。

    - Azure の **[与信残高]** タブで、Azure のお客様は、その請求プロファイルで使用される Azure クレジットのトランザクション残高履歴を確認できます。

    - Azure の **[クレジット]** タブで、Azure のお客様は、その請求プロファイルに関連付けられている Azure クレジットの一覧と有効期限を確認できます。

    > [!NOTE]
    > Azure クレジットをお持ちない場合は **、Azure** クレジット残高タブまたは Azure クレジット **タブは表示** されません。

## <a name="need-help-contact-support"></a>サポートが必要な場合 サポートにお問い合わせください。

Azure の料金について質問がある場合やサポートが必要な場合は <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">、Azure サポートでサポートリクエストを作成します</a>。

Microsoft 365 管理センターで請求プロファイルに関する質問やサポートが必要な場合は、ビジネス製品の [サポートにお問い合わせください](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。
