---
title: Microsoft 365 for business の課金または請求書を理解する
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 0724b428-fb59-4962-8c37-6674166d7507
description: Microsoft 365 の請求書、請求書、および支払いに関する情報を解釈する方法、およびお客様の注文番号を変更する方法について説明します。
ms.openlocfilehash: a46f108766ccfec4f7f6abaa2d48d38137311707
ms.sourcegitcommit: 7f765670cb6970fdf7ddbad464ed3f8fe704bfaf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2020
ms.locfileid: "44909266"
---
# <a name="understand-your-bill-or-invoice-for-microsoft-365-for-business"></a>Microsoft 365 for business の課金または請求書を理解する

毎月または毎年 (サブスクリプションを購入したときに選択したオプションによって異なります)、新しい請求明細書が管理センターで利用可能であることを知らせる電子メールが送信されます。 「[一般法人向け Office 365 の課金内容または請求書を表示する](view-your-bill-or-invoice.md)」を参照してください。
  
Your invoice contains two pages. Page 1 is the invoice summary, and contains general information about the invoice, order, amount due, how to make a payment, and how to contact support.
  
![Page 1 of a sample invoice.](../../media/b2f2cf85-a005-4f8a-a7b7-bea231372025.png)
  
2 ページ目には、各サブスクリプションの課金処理に関する詳細が含まれています。
  
![Page 2 of a sample invoice.](../../media/808195cb-b1d2-4492-a748-29671ccecdd2.png)
  
請求書に含まれるフィールドと用語の説明については、この記事で後述する「[請求書のフィールドの用語集](#invoice-field-glossary)」を参照してください。
  
## <a name="understand-billing-concepts"></a>課金の概念を理解する

請求書を表示する前に、課金に関する重要な概念をいくつか理解することをお勧めします。
  
### <a name="invoice-balance-vs-order-balance"></a>請求書残高と注文残高

 **請求書残高** は請求書に表示される金額で、特定の課金期間に対する請求額にすぎません。 合計の **注文残高** は、未払いの請求書の合計です。 注文残高は、管理センターの [**課金**] セクションで確認できます。
  
### <a name="billing-frequency-vs-invoice-frequency"></a>請求頻度と請求書頻度

 **請求頻度**は、請求の頻度を示します。 サブスクリプションは、サブスクリプションの購入時に選択したオプションに応じて、月または年ごとに請求されます。 **請求頻度**は、請求書を受信する頻度を表します。 年次請求書を選択した場合は、サブスクリプションの処理に請求書またはクレジットが必要でない限り、1年あたり1つの請求書を受信することになります。
  
注文が複数ある場合、注文ごとに請求書が届きます。
  
## <a name="invoice-field-glossary"></a>請求書のフィールドの用語集

The following table describes the fields you might see on your invoice. Some fields listed here might not appear in your invoice, depending on whether you pay by invoice or by credit card or bank account.
  
> [!NOTE]
> 一部の国または地域では、銀行口座引き落としによる支払いを利用できません。
  
|**[名前]**|**説明**|
|:-----|:-----|
|年間価格|サブスクリプションは、月次または年次で課金されます。 サブスクリプションの購入時に年次請求書を選択した場合は、請求書に年間ライセンス料金が反映されます。 請求頻度を変更する場合は、サブスクリプションをキャンセルして、新しい請求頻度で再度購入する必要があります。|
|課金期間|Billing Period is the time period since the last invoice date. Service Period is the time period during which you are charged to use the service.|
|請求先|これは請求部門の住所で、通常は販売先の住所と同じです。 請求先住所を更新するには、「[請求先](change-your-billing-addresses.md)住所を変更する」を参照してください。|
|料金|Page 1 of your invoice summarizes all charges for the invoice Billing Period. Page 2 shows the detailed charges for each subscription.|
|小切手|If you pay by invoice and check payment is offered in your country, the bottom of page 1 includes information about where to send your payment. Please reference the invoice number on your check.|
|クレジット|Page 1 of your invoice summarizes all credits for the invoice Billing Period. Page 2 shows the detailed credits for each subscription.|
|お客様の PO 番号|Your Purchase Order (PO) number. If you update the PO number, future invoices will include it. [Change your purchase order number](#change-your-purchase-order-number). <br/> **メモ**既存の請求書に PO 番号を追加することはできません。           |
|日数|Each billing transaction is associated with a Service Period. The Days column indicates the number of days in that service period.|
|割引|Page 1 of your invoice summarizes all discounts for the invoice Billing Period. Page 2 shows the detailed discounts for each subscription.|
|期限|The date when payment is due for the invoice. If your subscription is paid with a credit card or bank account, we will charge your credit card or banking account the day after the Invoice Date. <br/> **メモ**銀行口座による支払いは、一部の国や地域では使用できません。           |
|電子資金移動|サブスクリプションの支払い方法として [請求書] を選択した場合、ページ1には、電子情報 (有線、その他、SEPA など) の支払いに関する Microsoft 銀行口座の情報が含まれています。 通常、銀行は支払いの送信時に入力される参照フィールドを受け取ることになります。 このフィールドに表示される請求書番号を記載してください。|
|総計|この行には、請求書に記載されているすべてのサブスクリプションのすべての料金、割引、クレジット、小計、税、合計列の合計が含まれています。|
|請求日|The date the invoice was created. The invoice date is the day after the end of your Billing Period. For example, if your Billing Period is Jan 15 - Feb 14, your Invoice Date is Feb 15.|
|請求書番号|The unique number assigned to your invoice. Please reference the Invoice Number with your payment.|
|月額|サブスクリプションは、月次または年次で課金されます。 サブスクリプションの購入時に月次課金を選択した場合は、請求書に月次ライセンス料金が反映されます。 請求頻度を変更する場合は、サブスクリプションをキャンセルして、新しい請求頻度で再度購入する必要があります。|
|注文番号|Every time you buy a new subscription, an order is created. Every month, you'll receive an invoice for each order.|
|支払い手順|If you pay by credit card, you'll see "Do not pay - charged to credit card on file." If you pay by invoice, you'll see instructions for paying by Electronic Funds Transfer (EFT) and check (if applicable).|
|支払条件|The number of days from the Invoice Date when payment is due. The standard is 30 days.|
|製品|On page 1 of your invoice, "Online Services" is the generic term used to describe your subscriptions. On page 2 , you'll see the individual subscription names.|
|数量|サービス期間中に購入したライセンスの数です。|
|サービス期間|Service Period is the time period during which you are charged to use the service. A Billing Period is the time period since the last invoice date.|
|サービスの利用先住所|サービスが使用されているアドレス。通常は、販売先の住所と同じです。 サービス利用状況の住所を更新するには、「[請求先住所を変更](change-your-billing-addresses.md)する」を参照してください。|
|販売先|Your company name and address. To update this information, see [Change your organization's address, technical contact email, and other information](../../admin/manage/change-address-contact-and-more.md).|
|代金|請求書に記載されている各サブスクリプションには、そのサブスクリプションのすべての料金、割引、クレジット、小計、税、合計列の個別の小計行があります。|
|税|Page 1 of your invoice shows the total tax. Page 2 shows the tax rate applied, and the total tax amount for each line item. If your invoice contains taxes and your company is tax exempt, please [contact support](../../admin/contact-support-for-business-products.md).|
|合計|請求書の課金期間の請求額です。|

## <a name="change-your-purchase-order-number"></a>発注書番号を変更する

請求書による支払いの場合は、サブスクリプションの発注書 (PO) 番号の追加または変更が可能です。
  
> [!NOTE]
> You can't add a PO number to an existing invoice. The PO number will appear on all future invoices.

::: moniker range="o365-worldwide"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">お使いの製品</a>] ページの順に移動します。

2. **表**形式のビューの場合は、[**カード**] を選択してビューを切り替えます。

3. 変更するサブスクリプションを見つけます。

4. [請求 **] セクションで**、[**請求書**] の横にある [**編集**] を選択します。

5. [**支払い詳細の編集**] ウィンドウの下部で、PO 番号を入力し、[**保存**] を選択します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。

2. 変更するサブスクリプションを選択し、[**支払い方法**] セクションで [**支払いの詳細の変更**] を選択します。

3. [**支払い詳細の変更**] ウィンドウの下部で、PO 番号を入力し、[**送信**] を選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">サブスクリプション</a>] ページに移動します。

2. 変更するサブスクリプションを選択し、[**支払い方法**] セクションで [**支払いの詳細の変更**] を選択します。

3. [**支払い詳細の変更**] ウィンドウの下部で、PO 番号を入力し、[**送信**] を選択します。

::: moniker-end

## <a name="related-articles"></a>関連記事

[一般法人向け Microsoft 365 サブスクリプションを支払う](pay-for-your-subscription.md)

[Minecraft: Education Edition の支払いオプション](https://go.microsoft.com/fwlink/p/?linkid=838761)