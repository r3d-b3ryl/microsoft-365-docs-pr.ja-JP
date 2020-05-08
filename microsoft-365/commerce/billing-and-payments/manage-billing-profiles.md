---
title: 課金プロフィールを管理する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: 請求プロファイルが請求書をサポートする方法について説明します。
keywords: 課金プロファイル、請求書、料金、管理された費用
ms.openlocfilehash: f93ca5af11ba416fecd13fcceffe75055a776553
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140892"
---
# <a name="manage-billing-profiles"></a>課金プロフィールを管理する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターが変更されています。 ここに示されている詳細情報とは異なる場合は、「[新しい Microsoft 365 管理センターについ](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)て」を参照してください。

::: moniker-end

Microsoft の製品やサービスを購入している商用のお客様の場合、課金プロファイルを使用して、請求書に含めるアイテムをカスタマイズしたり、請求書に支払いを行ったりすることができます。

請求プロファイルには、次の情報が含まれます。

- **課金アカウント** &ndash;プロファイルが関連付けられている請求先アカウントの名前
- **支払い方法** &ndash;貸方またはデビットカード、銀行口座、小切手、または電信送金
- **連絡先情報** &ndash;請求先の住所と連絡先の名前
- **請求書の設定** &ndash;金額請求先アカウントの国に基づく通貨、オプションの PO 番号、および請求書を電子メールの添付ファイルとして受信するオプション
- 課金プロファイルの変更、支払い、請求プロファイルの支払い方法を使用して購入を行うことができる**アクセス** &ndash;許可のアクセス許可

請求プロファイルを使用して、購入を制御し、請求書をカスタマイズします。 月次請求書は、請求プロファイルを購入した製品に対して生成されます。 請求書は、[発注書番号] および [電子メールの請求書の設定を更新する] のようにカスタマイズできます。

最初の購入時に、課金プロファイルが自動的に請求アカウントに作成されます。 [<a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">課金プロファイル</a>] ページで請求プロファイルを作成し、さらに請求書を設定できます。 たとえば、組織内の部署ごとに購入するときに、さまざまな課金プロファイルを使用できます。 次の請求日に、請求プロファイルごとに請求書を受け取ります。

## <a name="billing-profile-roles"></a>課金プロファイルの役割

請求プロファイルの役割には、購入を制御し、請求書を表示および管理するためのアクセス許可があります。 これらの役割は、組織内の調達チームのメンバーと同様に、請求書を追跡、整理、および支払いするユーザーに割り当てます。

| Role                          | 説明                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| 課金プロファイルの所有者         | 課金プロファイルのすべてを管理する                                           |
| 課金プロファイル共同作成者   | 課金プロファイルのアクセス許可以外のすべてを管理する                         |
| 課金プロファイルリーダー        | 請求プロファイル内のすべての読み取り専用ビュー                                 |
| 請求書マネージャー               | 課金プロファイルに含まれるすべての情報を読み取り専用で表示および支払する   |

## <a name="view-billing-profiles"></a>課金プロファイルを表示する

1. 管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">請求と支払い</a>] ページの順に移動します。

2. [**課金プロファイル**] を選択し、リストから請求プロファイルを選択します。

    - [**概要**] タブでは、請求プロファイルの詳細を編集したり、請求書を電子メールで送信したりすることができます。

    - [**権限**] タブでは、請求書を支払いするためにユーザーに役割を割り当てることができます。

    - [ **Azure クレジットバランス**] タブでは、azure のお客様は、その請求書プロファイルで使用されている azure クレジットのトランザクションバランス履歴を確認できます。

    - [ **Azure クレジット**] タブでは、azure のお客様は、その請求プロファイルに関連付けられている azure クレジットの一覧と有効期限日を確認できます。

    > [!NOTE]
    > Azure クレジットをお持ちでない場合、[ **azure クレジットバランス**] タブまたは [ **azure**クレジット] タブは表示されません。

## <a name="need-help-contact-support"></a>サポートが必要な場合 サポートにお問い合わせください。

ご質問がある場合や Azure の料金についてサポートが必要な場合は、 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">azure サポートを使用してサポート要求を作成して</a>ください。

ご質問がある場合や、Microsoft 365 管理センターの課金プロファイルについてのヘルプが必要な場合は、[ビジネス製品のサポートにお問い合わせください](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)。
