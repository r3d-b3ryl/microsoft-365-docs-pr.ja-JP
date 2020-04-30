---
title: 請求書の内容を理解する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsInvoices
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Microsoft business 製品の請求書を読んで理解する方法について説明します。
keywords: 課金アカウント、組織情報、請求書
ms.openlocfilehash: 7b16af7c6ef39743aa8d0a4e927786f64f47c4cd
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942879"
---
# <a name="understand-your-invoice"></a>請求書の内容を理解する

請求書には、お客様の請求書の概要と支払い方法が記載されています。 [オンライン請求書](#view-your-online-invoice)は、Microsoft 365 管理センターで確認できます。 また、電子メールで送信するために、ポータブルドキュメント形式 (.pdf) でダウンロードすることもできます。

Microsoft 365 サブスクリプションのみを使用している場合は、「 [365 microsoft の請求書](understand-your-invoice2.md)について」を参照してください。

## <a name="understand-the-invoice-header"></a>請求書ヘッダーについて

最初のページの上部には、支払いの責任者、請求書の送付先、および請求書の概要が示されます。

| 用語 | Description |
| --- | --- |
| 販売先 |支払いを担当する法人の名前と住所を識別する請求先アカウント。 この情報は、[<a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">課金アカウント</a>] ページで管理できます。ここで、アカウントの使用規約を確認し、役割とアクセス許可を管理できます。 |
| 請求先 |請求書を受信するユーザーを識別します。 この情報は、[<a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">課金プロファイル</a>] ページで管理できます。 請求プロファイルは、[**請求書の概要**] セクションの [オンライン請求書] ページにも表示されます。 請求プロファイルの詳細と、それらを使用して組織にとってより柔軟な請求オプションを構築する方法については、「[課金プロファイルを管理](manage-billing-profiles.md)する」を参照してください。 |
| 課金プロファイル |Bill to、PO 番号、支払い条件などの請求書プロパティを定義するために使用される請求プロファイルの名前。 この情報は、[<a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">課金プロファイル</a>] ページで管理できます。 請求プロファイルの詳細と、それらを使用して組織にとってより柔軟な請求オプションを作成する方法については、「[課金プロファイルを管理](manage-billing-profiles.md)する」を参照してください。 |
| 請求書番号 |追跡目的で使用される、Microsoft で生成された一意の請求番号。 |
| 請求日 |請求書が生成される日付 (通常は、請求サイクルの終了後の 5 ~ 12 日)。 請求書の日付は、請求プロファイルの詳細ページで確認できます。 請求期間の終了と請求日の間に発生する諸費用は、次の請求期間に含まれているため、来月の請求書に含まれています。 各請求書の請求期間の開始日と終了日は、請求書の**上の**請求書 PDF に一覧表示されています。|
| 支払条件 |Microsoft bill の支払い方法。 *30 日*は、請求日から30日以内に、請求書に関する指示に従って支払いを行うことを意味します。 |

## <a name="understand-the-billing-summary"></a>請求書の概要を理解する

**請求書の概要**には、前の請求期間以降の諸費用、適用されたクレジット、税金、および合計金額の集計が表示されます。

| 用語 | Description |
| --- | --- |
| 料金|この請求期間に購入された製品の合計数と、それに関連する料金および税。 購入を集計して、請求書の簡潔なビューを提供します。 |
| 開発者情報 |返品から受け取ったクレジット |
| 適用された Azure クレジット |Azure に自動的に適用される Azure クレジットは、各請求期間に請求されます。 Azure クレジットがない場合、このフィールドは表示されません。 Azure クレジットの詳細については、「 [Microsoft カスタマーアグリーメントの azure クレジットバランスを追跡](https://docs.microsoft.com/azure/billing/billing-mca-check-azure-credits-balance)する」を参照してください。 |
| Subtotal |課税前金額 |
| 税 |請求プロファイルの国に応じて、支払う税額の種類と金額。 税金を支払う必要がない場合は、請求書に税金は表示されません。 |

### <a name="understand-your-charges"></a>課金内容を理解する

雑費ページには、製品別に細分化されたコストが表示されます。 Azure のお客様の場合は、請求書のセクションごとに料金が発生する場合があります。 Azure 製品での請求書セクションの使用方法の詳細については、「 [Microsoft カスタマーアグリーメントの課金アカウントで作業を開始](https://docs.microsoft.com/azure/billing/billing-mca-overview)する」の「[請求書」セクション](https://docs.microsoft.com/azure/billing/billing-mca-overview#invoice-sections)を参照してください。 各製品オーダー内では、コストはサービスファミリごとに分類されています。

| 用語 |Description |
| --- | --- |
| 単価 | 雑費の計算に使用されるサービスの有効な単価 (価格設定通貨)。 この価格は、製品、サービスファミリ、メーター、および申し出に対して一意です。 |
| 量 | 請求期間中に購入または消費される数量 |
| 料金/クレジット | クレジットまたは払戻が適用された後の費用の金額 |
| Azure クレジット | 料金/クレジットに適用される Azure クレジットの量 |
| 税率 | 国に応じた税率 |
| 課税金額 | 税率に基づいて、購入に適用される税の金額 |
| 合計 | 購入による合計金額 |

行アイテムの詳細は、請求する製品の種類によって異なります。 たとえば、Azure 製品の場合は、適用された Azure クレジットの量が表示されます。 座席表の製品には、単価と数量が表示されます。 請求書の詳細には、購入した製品、適用された割引またはクレジット、税率と金額、および品目の合計の概要が表示されます。

`Total = Charges - Azure Credit + Tax`

各サービスファミリの合計金額は、Azure クレジットをクレジットまたは料金から差し引くことによって算出され、税を追加します。

`Total = Charges/Credits - Azure Credit + Tax`

請求書に詳細情報を必要とする Azure の請求書がある場合は、「 [Microsoft カスタマーアグリーメントの請求書を確認](https://docs.microsoft.com/azure/cost-management-billing/understand/review-customer-agreement-bill)する」を参照してください。

## <a name="understand-the-last-invoice-page"></a>[最終請求書] ページについて

### <a name="payment-instructions"></a>支払い手順

請求書の下部には、請求書の支払い方法が記載されています。 ワイヤ、小切手、またはオンラインで支払うことができます。

### <a name="publisher-information"></a>発行元の情報

請求書にサードパーティのサービスがある場合は、各出版社の名前と住所が請求書の下部に表示されます。

## <a name="view-your-online-invoice"></a>オンライン請求書を表示する

請求書はオンラインで入手できます。 オンライン請求書へのリンクは、PDF 請求書および電子メール通知から入手できます。 オンライン請求書は展開可能なので、請求書の料金を確認し、各アイテムの詳細を確認できます。 オンライン請求書の内容は次のとおりです。

- **価格の詳細** &mdash;割引および製品価格に関する詳細を含む追加情報。

- **オンライン支払** &mdash;請求書からオンラインで支払いを行うことを選択できます。

- Azure の**コスト管理** &mdash; azure のお客様向けのオンライン請求書には、azure コスト管理へのリンクが含まれています。

### <a name="to-view-your-online-invoice"></a>オンライン請求書を表示するには

1. 管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">請求と支払い</a>] ページの順に移動します。

2. 請求書の .pdf バージョンをダウンロードするには、表示する請求書の行にある [**請求書の pdf をダウンロード**する] を選択します。

3. オンライン請求書を表示するには、リストから請求書を選択します。 [請求書の詳細] ページから .pdf をダウンロードすることもできます。

## <a name="need-help-contact-support"></a>サポートが必要な場合 サポートにお問い合わせください。

ご質問がある場合や Azure クレジットについてサポートが必要な場合は、 <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">azure サポートを使用してサポートリクエストを作成</a>してください。

Microsoft 365 管理センターで、請求書に関する質問がある場合や、サポートが必要な場合は、[ビジネス製品のサポートにお問い合わせください](../../admin/contact-support-for-business-products.md)。
