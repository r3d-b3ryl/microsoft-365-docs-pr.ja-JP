---
title: 税金情報
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: '各地域において一般法人向け Office 365 サブスクリプションに課せられる税額について説明します。 '
ms.custom: okr_SMB
ms.openlocfilehash: 88997eb69cbbee1b7ec4520773c167609434e0a4
ms.sourcegitcommit: 01ead889086ecc7dcf5d10244bcf67c5a33c8114
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "42710560"
---
# <a name="tax-information"></a>税金情報

マイクロソフトによる microsoft 365 管理センターの購入に関する税金は、お客様の会社の住所、または配送先住所によって異なります。 米国の場合は、連邦雇用機関の識別番号 (FEIN) を指定する必要があります。

これらの国の企業は、次のような VAT 番号を提供できます。

:::row:::
    :::column:::
- オーストリア
- ベルギー
- ブルガリア
- クロアチア
- キプロス
- チェコ共和国
- デンマーク
- エストニア
- フィンランド
- フランス
- ドイツ
- ギリシャ
- ハンガリー
- アイルランド
- イタリア
- ラトビア
    :::column-end:::
    :::column:::
- リヒテンシュタイン
- リトアニア
- ルクセンブルク
- マルタ
- モナコ
- オランダ
- ノルウェー
- ポーランド
- ポルトガル
- ルーマニア
- スロバキア
- 南アフリカ
- スペイン
- スウェーデン
- スイス
- 英国
    :::column-end:::
:::row-end:::

これらの国では、課金アカウント情報に VAT 番号またはローカルの同等物を提供できます。

|市販| 税識別子 |
|------|----------------|
| オーストラリア | ABN (省略可能) |
| ブラジル | CNPJ (必須) |
| インド | GSTIN (省略可能)、PAN ID (必須) |
| マン島 | VAT ID (オプション) |
| ニュージーランド | GST 登録番号 (オプション) |
| モナコ | VAT ID (オプション) |
| 台湾 | VAT ID (オプション) |

> [!Note]
> サポートに連絡する必要がある場合は、サポートエージェントに提供するために、お客様の FEIN VAT 番号、またはローカルの同等の準備が整っている必要があります。

## <a name="what-tax-will-i-be-charged"></a>請求される税金

ここでは、下記の各地域で課せられる税について説明します。適切な文書をサポートに提出すると、[税金控除ステータスを申請する](apply-for-tax-exempt-status.md)こともできます。
  
### <a name="europe-the-middle-east-and-africa-emea"></a>ヨーロッパ、中東、アフリカ (EMEA)

欧州連合 (EU) 域内で Office 365 のサービスを購入すると、その購入は付加価値税 (VAT) の対象となります。
  
- 購入者が EU 加盟国に所在しているが、その国での有効な VAT ID を提示しなかった場合は、Microsoft Ireland Operations Ltd. によって、アカウントが設定されている請求先の国に基づいて、その時点の地域の VAT 税率が適用されます。

- 購入者がスイスまたはリヒテンシュタインに所在している場合は、VAT ID 提示の有無にかかわらず、その時点のスイスの VAT 税率が適用されます。

- 基本的に、購入者が EU 加盟国、スイス、リヒテンシュタイン以外の EMEA の国に所在している場合は、Microsoft Ireland Operations Ltd. によって VAT が課されることはありません。

- Microsoft が購入者の VAT ID を確認できるのは、その ID が VAT Information Exchange System (VIES) で確認できる状態である場合に限られます。VAT ID が確認不可能の場合は、その地域の税務当局に問い合わせてください。

次の場合は、VAT ゼロ税率となることがあります。
  
- **アイルランド以外の EU 加盟国に所在している場合:** 所在国での有効な VAT ID を提示してください。これで、Microsoft Ireland Operations Ltd. との取引は VAT ゼロ税率の対象となります。ただし、所在国での VAT 会計義務が存在する可能性があるため、不明な点がある場合は税務顧問に確認してください。手順については、次の「VAT ID を追加する (EU 加盟国のみ)」を参照してください。

- **アイルランドに所在し、関係する有効な VAT 免税証明書がある場合:** Microsoft Ireland Operations Ltd. との取引は VAT 免税にできることがあります。免税証明書がない場合は、購入者の VAT ID 提示の有無にかかわらず、Microsoft Ireland Operations Ltd. によってその時点のアイルランドの VAT 率が適用されます。

::: moniker range="o365-worldwide"

#### <a name="add-your-vat-id-eu-countries-only"></a>VAT ID を追加する (EU 加盟国のみ)

1. 管理センターで、[**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品とサービス</a>] ページに移動します。

2. 更新するサブスクリプションのサブスクリプション カードを検索します。

3. **[設定とアクション]** セクションで、**[サービスの利用先住所の編集]** を選択します。

4. **[サービスの利用先住所の編集]** ページで、VAT ID を **[VAT 番号]** ボックスに入力して **[保存]** を選択します。

::: moniker-end

::: moniker range="o365-germany"

#### <a name="add-your-vat-id-eu-countries-only"></a>VAT ID を追加する (EU 加盟国のみ)
  
1. 管理センターの [**課金**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">サブスクリプション</a>] ページに移動します。

2. サブスクリプション名を選択して、**[その他の操作]**\>**[VAT 番号の編集]** の順に選択します。
  
3. **[サービスの利用先住所の編集]** ページで、VAT ID を **[VAT 番号]** ボックスに入力して **[送信]** を選択します。

::: moniker-end

### <a name="asia-pacific-countries-apac"></a>アジア太平洋地域 (APAC)

請求元が Microsoft Regional Sales オフィスの場合は、請求書に "Microsoft Regional Sales" と明記されており、通常は消費税や付加価値税 (VAT) が課せられることはありません。ただし、同一国内での販売である場合を除きます。
  
それ以外からの請求の場合は、その時点でのその国の課税対象となり、次のように[請求書に記載されます](view-your-bill-or-invoice.md)。
  
- シンガポールからシンガポール

- 韓国から韓国

- 日本から日本

- 台湾から台湾

### <a name="north-central-and-south-america"></a>北、中央、南アメリカ

アメリカ合衆国とカナダでは、所在場所に応じて、さまざまな税率が適用されます。プエルトリコでは、ローカルな付加価値税 (VAT) 額が適用されます。
  
請求元が Microsoft Corporation で ([請求書に記載されています](view-your-bill-or-invoice.md))、購入者が Office 365 へのサインアップをアメリカ合衆国、カナダ、プエルトリコ以外の国で行った場合は、基本的に課税対象外となります。

## <a name="how-taxes-are-calculated"></a>税の計算方法

売上税は、単価に対して計算されてから集計されます。

次に例を示します。

>*(単価 X 税率)X 数量 = 総売上税*

または

>($1.29 X 0.095)X 100 = $12.25

## <a name="apply-for-tax-exempt-status"></a>非課税状態に適用する

市場の免税資格を得る場合は、[サービスリクエストを開始](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)して、組織の課税控除状態を設定します。

次のドキュメントを準備しておく必要があります。

|国または地域 | ドキュメント |
|------------------|----------------|
| 米国 | 売上税の免税証明書 |
| カナダ | 適用除外の証明書 (または同等の承認状) |
| アイルランド | 13B/56A 非課税証明書|
| 免税が適用される国際組織 | 地方税務当局からの証明書/レターの確認 |
| プエルトリコ | Certificado de Compras Exentas |
  
## <a name="related-articles"></a>関連記事
  
[課金内容を表示する](view-your-bill-or-invoice.md)
  
[請求書を把握する](understand-your-invoice.md)