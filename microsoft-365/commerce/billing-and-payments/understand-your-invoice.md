---
title: 課金内容または請求書の内容を理解する
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsInvoices
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
description: Microsoft ビジネス製品の課金内容または請求書の内容を読んで理解する方法について説明します。
keywords: 課金アカウント、組織情報、請求書
ms.date: 05/04/2021
ms.openlocfilehash: 3f6eaef9e26578f759a64fdf55dfeb6882be2458
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61371270"
---
# <a name="understand-your-bill-or-invoice"></a>課金内容または請求書の内容を理解する

請求書には、請求の概要と支払い方法が記載されています。 Microsoft 365 管理センターで[オンライン請求書を表示](#view-your-online-invoice)できます。 また、Portable Document Format (.pdf) でダウンロードして、メールで送信することもできます。

請求書を表示および印刷するには、次の方法を使用します。

1. [**課金情報**]  >  [<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">請求と支払い</a>] ページで、請求書の日付範囲を選択します。
2. 請求書を PDF 形式で印刷または保存するには、[**請求書 PDF のダウンロード**] を選択し、PDF を印刷します。

詳細については、「[課金内容または請求書を表示する](view-your-bill-or-invoice.md)」を参照してください。

Microsoft 365 サブスクリプションしかない場合は、「[Microsoft 365 for Business の課金内容または請求書の内容を理解する](understand-your-invoice2.md)」を参照してください。

## <a name="understand-the-invoice-header"></a>請求書のヘッダーを理解する

最初のページの上部には、支払いの責任者、請求書の送付先、請求の概要が示されています。

| 用語 | 説明 |
| --- | --- |
| 売却先 |支払いを担当する法人の名前と住所を示す課金アカウント。 この情報は、アカウント契約を検索し、役割とアクセス許可を管理できる [<a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">課金アカウント</a>] ページで管理できます。 |
| 請求先 |請求書を受け取る人を示します。 この情報は、[<a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">課金プロファイル</a>] ページで管理できます。 課金プロファイルは、オンライン請求書ページの [**請求書の概要**] セクションにも表示されます。 課金プロファイルの詳細と、それらを使用して組織のより柔軟な課金オプションを構築する方法については、「[課金プロファイルの管理](manage-billing-profiles.md)」を参照してください。 |
| 課金プロファイル |**請求先**、**PO 番号**、支払条件などの請求書プロパティを定義するために使用される課金プロファイルの名前。 この情報は、[<a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">課金プロファイル</a>] ページで管理できます。 課金プロファイルの詳細と、それらを使用して組織のより柔軟な課金オプションを構築する方法については、「[課金プロファイルの管理](manage-billing-profiles.md)」を参照してください。 |
| 請求書番号 |追跡目的で使用される、Microsoft が生成した一意の請求書番号。 |
| 請求日 |請求書が生成された日付。通常、請求サイクルの終了後 5 - 12 日です。 請求日は、課金プロファイルの詳細ページで確認できます。 請求期間の終了から請求日までの間に発生した料金は、次の請求期間であるため、翌月の請求に含まれます。 各請求書の請求期間の開始日と終了日は、**課金の概要** の上の請求書の PDF に記載されています。|
| 支払条件 |Microsoft の請求書の支払い方法。 *30 日以内に全額* とは、請求日から 30 日以内に、請求書の指示に従って支払うことを意味します。 |

## <a name="understand-the-billing-summary"></a>課金の概要を理解する

**課金の概要** には、前の請求期間以降の請求の概要、適用されたクレジット、税金、合計金額が表示されます。

| 用語 | 説明 |
| --- | --- |
| 料金|この請求期間中に購入された製品の総数、およびそれらに関連する料金と税金。 購入は、請求書の簡潔なビューを提供するために集約されます。 |
| クレジット |返品から受け取ったクレジット |
| 適用される Azure クレジット |Azure に自動的に適用される Azure クレジットは、請求期間ごとに課金されます。 Azure クレジットがない場合、このフィールドは非表示になります。 Azure クレジットの詳細については、「[Microsoft 顧客契約の Azure クレジット残高の追跡](/azure/billing/billing-mca-check-azure-credits-balance)」を参照してください。 |
| 小計 |税引前の金額 |
| 税 |課金プロファイルの国に応じて、支払う税金の種類と金額。 税金を支払う必要がない場合、請求書には税金は表示されません。 |

### <a name="understand-your-charges"></a>料金を理解する

料金ページには、製品ごとのコストの内訳が表示されます。 Azure のお客様の場合、料金は請求書セクションごとに整理される場合があります。 Azure 製品での請求書セクションの使用方法の詳細については、「[Microsoft 顧客契約の課金アカウントの使用を開始する](/azure/billing/billing-mca-overview)」の「[請求書セクション](/azure/billing/billing-mca-overview#invoice-sections)」を参照してください。 各製品の注文内で、コストはサービス ファミリごとに分類されます。

| 用語 |説明 |
| --- | --- |
| 単価 | 料金の計算に使用されるサービスの実効単価 (価格設定通貨)。 この価格は、製品、サービス ファミリ、メーター、オファーに固有のものです。 |
| 数量 | 請求期間中に購入または消費された数量 |
| 料金/クレジット | クレジット/払い戻しが適用された後の料金の正味金額 |
| Azure クレジット | 料金/クレジットに適用される Azure クレジットの金額 |
| 税率 | 国に応じた税率 |
| 課税額 | 税率に基づいて購入に適用される税額 |
| 合計 | 購入の合計金額 |

行項目の詳細は、請求対象の製品の種類によって異なります。 たとえば、Azure 製品の場合、適用された Azure クレジットの金額が表示されます。 シートベースの製品は、単価と数量を示しています。 請求書の詳細には、購入した製品、適用された割引またはクレジット、税率と金額、行項目の合計が表示されます。

> 合計 = 料金 - Azure クレジット + 税

各サービス ファミリの合計金額は、クレジット/料金から Azure クレジットを差し引き、税金を加算することによって計算されます:

> 合計 = 料金/クレジット - Azure クレジット + 税

請求書に詳細が必要な Azure の料金がある場合は、「[Microsoft 顧客契約の請求書を確認する](/azure/cost-management-billing/understand/review-customer-agreement-bill)」を参照してください。

## <a name="understand-the-last-invoice-page"></a>前回の請求書ページを理解する

### <a name="payment-instructions"></a>支払い手順

請求書の下部には、請求書の支払い方法に関する説明があります。 電信、小切手、またはオンラインで支払うことができます。

### <a name="publisher-information"></a>発行元の情報

請求書にサードパーティのサービスがある場合は、各発行元の名前と住所が請求書の下部に記載されています。

## <a name="view-your-online-invoice"></a>オンライン請求書を表示する

請求書はオンラインで利用可能です。 オンライン請求書へのリンクは、PDF 請求書およびメール通知から利用できます。 オンライン請求書は拡張可能であるため、請求書の料金を表示したり、各項目の詳細を確認したりできます。 オンライン請求書には次のものが含まれます:

- **価格の詳細**&mdash;割引や製品の価格に関する詳細を含む追加情報。
- **オンラインの支払い**&mdash;請求書からオンラインで支払いを行うことを選択できます。
- **Azure のコスト管理**&mdash;Azure のお客様の場合、オンライン請求書には Azure のコスト管理へのリンクが含まれています。

### <a name="to-view-your-online-invoice"></a>オンライン請求書を表示するには

1. 管理センターで、[**課金情報**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">請求と支払い</a>] ページの順に移動します。
2. 請求書の .pdf バージョンをダウンロードするには、表示する請求書の行にある [**請求書 PDF のダウンロード**] を選択します。
3. オンライン請求書を表示するには、リストから請求書を選択します。 請求書の詳細ページから .pdf をダウンロードすることもできます。

## <a name="invoice-faq"></a>請求書の FAQ

### <a name="when-is-my-invoice-available"></a>請求書はいつ利用できますか?

一部の請求書は、購入から 24 時間以内に生成されます。 その他の請求書は請求期間の終了時に生成され、その期間のすべての項目が含まれます。

### <a name="how-do-i-pay-the-amount-due-on-my-invoice"></a>請求書の金額を支払うにはどうすればよいですか?

支払い手順はお支払い方法によって異なり、請求書 PDF の下部に記載されています。 お支払い方法がクレジット カードの場合、請求日から 10 日以内に自動的に請求されます。 お支払い方法が小切手または電信送金の場合は、PDF の「**支払い手順**」の情報をご覧ください。

### <a name="whats-the-difference-between-sold-to-and-bill-to-addresses"></a>"売却先" 住所と "請求先" 住所の違いは何ですか?

- **売却先:** 支払いを担当し、請求書に記載されている法人。 ここに記載されている住所は、購入時に別の配送先住所を提供することを選択しない限り、税率を決定するために使用されます。 詳細については、「[税金情報](tax-information.md)」を参照してください。
- **請求先:** 該当する場合、物理的な請求書が送信される住所。 法人ごとに複数の **請求先** 住所が存在する可能性がありますが、課金プロファイルごとに 1 つの **請求先** 住所のみが存在します。

### <a name="what-are-billed-amount-and-amount-due"></a>"請求額" と "未払金額" とは何ですか?

- **請求額:** 購入した合計金額。
- **未払金額:** 支払うべき残高。

### <a name="what-is-the-difference-between-service-period-and-billing-period"></a>"サービス期間" と "請求期間" の違いは何ですか?

- **サービス期間:** サービスの利用について請求される期間。
- **請求期間:** 前回の請求日を起点とする期間。

### <a name="why-dont-i-see-azure-prepayment-as-a-payment-method"></a>お支払い方法として Azure の前払いが表示されないのはなぜですか?

Azure 前払は、対象となる Azure 製品およびサービスの支払い方法としてのみ利用できます。

## <a name="need-help-contact-support"></a>サポートが必要な場合 サポートにお問い合せください

Azure クレジットについて質問がある場合、またはサポートが必要な場合は、<a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">Azure サポートを使用してサポート要求を作成してください</a>。

Microsoft 365 管理センターの請求書について質問がある場合、またはサポートが必要な場合は、[ビジネス製品のサポートにお問い合わせください](../../admin/get-help-support.md)。

## <a name="related-content"></a>関連コンテンツ

[ビジネス向け請求書または請求書Microsoft 365を理解](understand-your-invoice2.md)する (記事)\
[Microsoft Customer Agreement Azure クレジット 残高の追跡](/azure/billing/billing-mca-check-azure-credits-balance) (記事)\
[Microsoft カスタマー 契約請求書](/azure/cost-management-billing/understand/review-customer-agreement-bill) (記事)を確認する\
[Microsoft Customer Agreement 請求アカウントの使用を開始する](/azure/billing/billing-mca-overview) (記事)
